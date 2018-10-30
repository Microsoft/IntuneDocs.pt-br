---
title: Usar certificados PKCS com o Microsoft Intune – Azure | Micrososft Docs
description: Adicione ou crie certificados de Public Key Cryptography Standards com o Microsoft Intune, incluindo as etapas para exportar um certificado raiz, configure o modelo do certificado, baixe e instale o Microsoft Intune Certificate Connector (NDES), crie um perfil de configuração de dispositivo, crie um perfil de Certificado PKCS no Azure e sua Autoridade de Certificação.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 573cdf8746b9eaf593a33cd943b69a2dd83030ae
ms.sourcegitcommit: 2e88ec7a412a2db35034d30a70d20a5014ddddee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2018
ms.locfileid: "49391596"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configurar e usar certificados PKCS com o Intune

> [!IMPORTANT]
> Estamos fazendo algumas melhorias no recurso S/MIME descrito neste artigo. Como resultado, o recurso S/MIME foi temporariamente removido do Intune. Quando este recurso for liberado, removeremos esta nota.

Os certificados autenticam e protegem o acesso aos recursos corporativos, como uma VPN ou a rede WiFi. Este artigo mostra como exportar um certificado PKCS e, em seguida, adicionar o certificado a um perfil do Intune.

## <a name="requirements"></a>Requisitos

Para usar certificados PKCS com o Intune, verifique se você tem a seguinte infraestrutura:

- **Domínio do Active Directory**: todos os servidores listados nesta seção precisam ser ingressados no Domínio do Active Directory.

  Para obter mais informações sobre como instalar e configurar o AD DS, consulte [Design e planejamento do AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **AC** (Autoridade de Certificação): uma AC (autoridade de certificação corporativa)

  Para ver mais informações sobre como instalar e configurar o AD CS (Serviços de Certificados do Active Directory), consulte o artigo [Guia passo a passo dos Serviços de Certificados do Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > O Intune exige que você execute o AD CS com uma AC (Autoridade de Certificação) Corporativa, não com uma AC Autônoma.

- **Um cliente**: para se conectar à AC corporativa

- **Certificado raiz**: uma cópia exportada do certificado raiz da AC corporativa

- **Microsoft Intune Certificate Connector**: use o portal do Azure para baixar o instalador do **Certificate Connector** (**NDESConnectorSetup.exe**). 

  O conector processa as solicitações de certificado PKCS usadas para autenticação ou autenticação de email S/MIME.

  O conector do Certificado NDES também dá suporte ao modo do padrão FIPS. O FIPS não é necessário, mas você pode emitir e revogar certificados quando ele está habilitado.

- **Conector do Certificado PFX do Microsoft Intune**: se você pretende usar a criptografia de email S/MIME, use o portal do Azure para baixar o instalador do **Conector do Certificado PFX do Microsoft Intune** (**PfxCertificateConnectorBootstrapper.exe**). O conector processa as solicitações para arquivos PFX importados no Intune para criptografia de email S/MIME de um usuário específico.

- **Windows Server**: hospeda o:

  - Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) para cenários de autenticação e autenticação de email S/MIME
  - Conector do Certificado PFX do Microsoft Intune (PfxCertificateConnectorBootstrapper.exe) para cenários de criptografia de email S/MIME.

  Você pode executar ambos os conectores (**Microsoft Intune Certificate Connector** e **Conector do Certificado PFX do Microsoft Intune**) no mesmo servidor.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportar o certificado raiz da AC Corporativa

Para autenticação com VPN, WiFi ou outros recursos, é necessário ter um Certificado de Autoridade de Certificação raiz ou intermediária em cada dispositivo. As etapas a seguir explicam como obter o certificado necessário de sua AC Corporativa.

1. Entre na sua AC corporativa com uma conta que tenha privilégios administrativos.
2. Abra um prompt de comando como administrador.
3. Exporte o Certificado de Autoridade de Certificação Raiz (.cer) para um local em que você possa acessá-lo mais tarde.
4. Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.

   `certutil -ca.cert certnew.cer`

   Para saber mais, veja [Tarefas do Certutil para gerenciar certificados](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Configurar modelos de certificado na autoridade de certificação

1. Entre na sua AC corporativa com uma conta que tenha privilégios administrativos.
2. Abra o console da **Autoridade de Certificação**, clicar com o botão direito do mouse em **Modelos de Certificado** e selecione **Gerenciar**.
3. Localize o modelo de certificado do **Usuário**, clique nele com o botão direito do mouse e escolha **Duplicar Modelo**. **Propriedades do Novo Modelo** se abre.

    > [!NOTE]
    > Para os cenários de autenticação e criptografia de email S/MIME, muitos administradores usam certificados separados para autenticação e criptografia. Caso esteja usando os Serviços de Certificados do Microsoft Active Directory, use o modelo **Trocar Somente Assinatura** para certificados de autenticação de email S/MIME e o modelo **Trocar Usuário** para certificados de criptografia S/MIME.  Caso esteja usando uma autoridade de certificação de terceiros, é recomendável examinar suas diretrizes para configurar modelos de autenticação e criptografia.

4. Na guia **Compatibilidade**:

  - Defina **Autoridade de Certificação** como **Windows Server 2008 R2**
  - Defina **Destinatário do certificado** como **Windows 7/Server 2008 R2**

5. Na guia **Geral**, defina **Nome de exibição do modelo** como algo significativo para você.

    > [!WARNING]
    > **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*. Observe o nome do modelo, pois ele será necessário mais tarde.

6. Em **Tratamento de Solicitação**, selecione **Permitir que a chave privada seja exportada**.
7. Em **Criptografia**, confirme se o **Tamanho mínimo da chave** está definido como 2048.
8. Em **Nome da Entidade**, escolha **Fornecer na solicitação**.
9. Em **Extensões**, confirme a existência de Encrypting File System, Email Seguro e Autenticação de Cliente em **Políticas de Aplicativo**.

    > [!IMPORTANT]
    > Para modelos de certificado do iOS, na guia **Extensões**, atualize **Uso da Chave** e confirme se a opção **A assinatura é uma prova de origem** não está selecionada.

10. Em **Segurança**, adicione a Conta de Computador do servidor de instalação do Microsoft Intune Certificate Connector. Atribua as permissões **Leitura** e **Inscrição** à essa conta.
11. Selecione **Aplicar** > **OK** para salvar o modelo de certificado. Feche o **Console de Modelos de Certificado**.
12. No console da **Autoridade de Certificação**, clique com o botão direito em **Modelos de Certificados** > **Novo** > **Modelo de certificado a ser emitido**. Escolha o modelo que você criou nas etapas anteriores. Selecione **OK**.
13. Para o servidor gerenciar certificados em nome de usuários e dispositivos registrados no Intune, use as seguintes etapas:

    1. Clique com o botão direito na Autoridade de Certificação e escolha **Propriedades**.
    2. Na guia Segurança, adicione a conta de Computador do servidor em que você executa os conectores (**Microsoft Intune Certificate Connector** ou **Conector do Certificado PFX do Microsoft Intune**). Conceda as permissões **Emitir e Gerenciar Certificados** e **Solicitar Certificados** à conta de computador.

14. Saia da AC corporativa.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Baixar, instalar e configurar os conectores de certificado

### <a name="microsoft-intune-certificate-connector"></a>Conector de Certificado do Microsoft Intune

> [!IMPORTANT] 
> O Microsoft Intune Certificate Connector **deve** ser instalado em um servidor Windows separado. Ele não pode ser instalado na Autoridade de Certificação (CA) emissora.

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Autoridade de certificação** > **Adicionar**.
3. Faça o download e salve o arquivo do conector. Salve-o em um local acessível a partir do servidor no qual você instalará o conector.

    ![ConnectorDownload][ConnectorDownload]

4. Após a conclusão do download, entre no servidor. Em seguida:

    1. Verifique se o .NET 4.5 Framework ou superior está instalado, pois ele é necessário para o conector do Certificado NDES. O .NET 4.5 Framework é automaticamente incluído no Windows Server 2012 R2 e versões mais recentes.
    2. Execute o instalador (NDESConnectorSetup.exe) e aceite a localização padrão. Ele instala o conector para `\Program Files\Microsoft Intune\NDESConnectorUI`. Nas Opções do Instalador, selecione **Distribuição de PFX**. Continue e conclua a instalação.
    3. Por padrão, o serviço do conector é executado na conta Sistema Local. Se for necessário usar um proxy para acessar a Internet, confirme se a conta de serviço local pode acessar as configurações de proxy no servidor.

5. O Conector NDES abrirá a guia **Registro**. Para habilitar a conexão com o Intune, selecione **Entrar** e insira uma conta com permissões administrativas globais.
6. Na guia **Avançado**, recomenda-se deixar a opção **Usar a conta SISTEMA deste computador (padrão)** selecionada.
7. **Aplicar** > **Fechar**
8. Retorne para o Portal do Azure (**Intune** > **Configuração do Dispositivo** > **Autoridade de Certificação**). Depois de alguns minutos, uma marca de seleção verde é exibida e o **Status da conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.

> [!NOTE]
> O suporte ao TLS 1.2 está incluído no Microsoft Intune Certificate Connector. Portanto, se o servidor com o Microsoft Intune Certificate Connector instalado dá suporte ao TLS 1.2, o TLS 1.2 é usado. Se o servidor não dá suporte ao TLS 1.2, o TLS 1.1 é usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Conector do Certificado PFX do Microsoft Intune

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Autoridade de certificação** > **Adicionar**
3. Faça o download e salve o Conector de Certificado PFX do Microsoft Intune. Salve-o em um local acessível a partir do servidor no qual você instalará o conector.
4. Após a conclusão do download, entre no servidor. Em seguida:

    1. Verifique se o .NET 4.6 Framework ou superior está instalado, pois ele é necessário para o Conector do Certificado PFX do Microsoft Intune. Se o .NET Framework 4.6 não estiver instalado, o instalador o instalará automaticamente.
    2. Execute o instalador (PfxCertificateConnectorBootstrapper.exe) e aceite a localização padrão. Ele instala o conector para `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. O serviço do conector é executado na conta Sistema Local. Se for necessário usar um proxy para acesso à Internet, confirme se a conta de serviço local pode acessar as configurações de proxy no servidor.

5. O Conector do Certificado PFX do Microsoft Intune abre a guia **Registro** após a instalação. Para habilitar a conexão com o Intune, **Entre** e insira uma conta com permissões de administrador do Intune ou administrador global do Azure.
6. Feche a janela.
7. Retorne para o Portal do Azure (**Intune** > **Configuração do Dispositivo** > **Autoridade de Certificação**). Depois de alguns minutos, uma marca de seleção verde é exibida e o **Status da conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.

## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

1. No [portal do Azure](https://portal.azure.com), acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil**.

   ![NavigateIntune][NavigateIntune]

2. Digite as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina o **Tipo de perfil** como **Certificado confiável**

3. Acesse **Configurações** e insira o arquivo .cer do Certificado de Autoridade de Certificação Raiz exportado anteriormente.

   > [!NOTE]
   > Dependendo da plataforma escolhida na **Etapa 3**, você poderá ou não ter a opção de escolher o **Armazenamento de destino** do certificado.

   ![ProfileSettings][ProfileSettings]

4. Selecione **OK** > **Criar** para salvar seu perfil.
5. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de certificado PKCS

1. No [portal do Azure](https://portal.azure.com), acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
2. Digite as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina o **Tipo de perfil** como **Certificado PKCS**

3. Acesse **Configurações** e digite as seguintes propriedades:

    - **Limite de renovação (%)**: o recomendado é 20%.
    - **Período de validade do certificado**: se você não alterou o modelo de certificado, essa opção pode ser definida como um ano.
    - **KSP (provedor de armazenamento de chaves)**: para o Windows, selecione o local em que armazenar as chaves no dispositivo.
    - **Autoridade de certificação**: exibe o FQDN (nome de domínio totalmente qualificado) interno da AC corporativa.
    - **Nome da autoridade de certificação**: lista o nome da AC corporativa, como "Autoridade de Certificação da Contoso".
    - **Nome do modelo de certificado**: o nome do modelo criado anteriormente. Lembre-se de que **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*.
    - **Formato do nome da entidade**: defina essa opção como um **Nome comum**, a menos que seja exigido o contrário.
    - **Nome alternativo da entidade**: defina essa opção como **Nome UPN**, a menos que seja exigido o contrário.

4. Selecione **OK** > **Criar** para salvar seu perfil.
5. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-imported-certificate-profile"></a>Criar um perfil de certificado PKCS importado

Você pode importar o certificado emitido anteriormente para um usuário específico em qualquer autoridade de certificação para o Intune. Os certificados importados são instalados em cada dispositivo registrado por um usuário. A criptografia de email S/MIME é o cenário mais comum para importar os certificados PFX existentes para o Intune. Um usuário pode ter vários certificados para criptografar o email. As chaves privadas desses certificados precisam existir em todos os dispositivos de um usuário, de modo que eles possam descriptografar os emails criptografados anteriormente.

Para importar certificados no Intune, use os [cmdlets do PowerShell fornecidos no GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Depois de importar os certificados para o Intune, crie um perfil de **certificado importado PKCS** e atribua-o aos grupos do Azure Active Directory.

1. No [portal do Azure](https://portal.azure.com), acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
2. Digite as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina **Tipo de perfil** como **Certificado PKCS importado**

3. Acesse **Configurações** e digite as seguintes propriedades:

    - **Finalidade pretendida**: a finalidade pretendida dos certificados que são importados para esse perfil. Um administrador pode ter certificados importados com finalidades pretendidas diferentes (por exemplo, autenticação, autenticação S/MIME ou criptografia S/MIME). A finalidade pretendida selecionada no perfil de certificado corresponde ao perfil de certificado com os certificados corretos importados.
    - **Período de validade do certificado**: se você não alterou o modelo de certificado, essa opção pode ser definida como um ano.
    - **KSP (provedor de armazenamento de chaves)**: para o Windows, selecione o local em que armazenar as chaves no dispositivo.

4. Selecione **OK** > **Criar** para salvar seu perfil.
5. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="next-steps"></a>Próximas etapas
[Usar certificados SCEP](certificates-scep-configure.md) ou [emitir certificados PKCS em um serviço Web do Symantec PKI Manager](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navegar até o Intune no Portal do Azure e criar um novo perfil para um certificado confiável"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Criar um perfil e carregar um certificado confiável"
[ConnectorDownload]: ./media/certificates-download-connector.png "Baixar o conector de certificado do Portal do Azure"  
