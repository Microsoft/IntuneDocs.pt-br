---
title: Usar certificados de chave pública e privada no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie certificados PKCS (Public Key Cryptography Standards) com o Microsoft Intune, incluindo as etapas para exportar um certificado raiz, configure o modelo de certificado, baixe e instale o NDES (Intune Certificate Connector), crie um perfil de configuração do dispositivo e crie um perfil de Certificado PKCS no Azure e a Autoridade de Certificação.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 08/15/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 330bfa319ca0202a5edc09d8f27e40c18ce89d39
ms.sourcegitcommit: 6b5907046f920279bbda3ee6c93e98594624c05c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69582938"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configurar e usar certificados PKCS com o Intune

O Intune dá suporte ao uso de certificados de par de chaves privadas e públicas (PCKS). Este artigo pode ajudá-lo a configurar a infraestrutura necessária, como conectores de certificado locais, exportar um certificado PKCS e, em seguida, adicioná-lo a um perfil de configuração do dispositivo do Intune.

O Microsoft Intune inclui configurações internas de uso de certificados PKCS para acesso e autenticação nos recursos de sua organização. Os certificados autenticam e protegem o acesso aos recursos corporativos como uma VPN ou uma rede WiFi. Implante essas configurações em dispositivos usando perfis de configuração do dispositivo no Intune.


## <a name="requirements"></a>Requisitos

Para usar certificados PKCS com o Intune, será necessária a seguinte infraestrutura:

- **Domínio do Active Directory**:  
  Todos os servidores listados nesta seção precisam ser ingressados no domínio do Active Directory.

  Para saber mais sobre como instalar e configurar o AD DS (Active Directory Domain Services), confira [Planejamento e Design do AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

- **Autoridade de certificação**:  
   uma AC (autoridade de certificação corporativa).

  Para saber mais sobre como instalar e configurar o AD CS (Serviços de Certificados do Active Directory), confira [Guia passo a passo dos Serviços de Certificados do Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]  
  > O Intune exige que você execute o AD CS com uma AC (Autoridade de Certificação) Corporativa, não com uma AC Autônoma.

- **Um cliente**:  
  para se conectar à AC corporativa.

- **Certificado raiz**:  
  Uma cópia exportada de seu certificado raiz de sua AC Corporativa.

- O **Microsoft Intune Certificate Connector** (também chamado de *Certificate Connector NDES*):  
  No portal do Intune, acesse **Configuração do dispositivo** > **Conectores do Certificado** > **Adicionar** e siga as *Etapas para instalar o conector para PKCS n º 12*. Use o link de download no portal para começar o download do instalador do conector do certificado **NDESConnectorSetup.exe**.  

  O Intune tem suporte para até 100 instâncias desse conector por locatário, com cada instância em um servidor Windows separado. Você pode instalar uma instância desse conector no mesmo servidor de uma instância do Certificate Connector PFX do Microsoft Intune. Quando você usa vários conectores, a infraestrutura do conector tem suporte para alta disponibilidade e balanceamento de carga, já que qualquer instância de conector disponível pode processar suas solicitações de certificado PKCS. 

  Esse conector processa solicitações de certificado PCKS usadas para autenticação ou assinatura de email S/MIME.

  O Microsoft Intune Certificate Connector também é compatível com o modo do padrão FIPS. O FIPS não é necessário, mas você poderá emitir e revogar certificados quando estiver habilitado.

- **Conector do Certificado PFX do Microsoft Intune**:  
  se você planeja usar a criptografia de email S/MIME, use o portal do Intune para baixar o conector para *Certificados PFX importados*.  Acesse **Configuração do dispositivo** > **Conectores do Certificado** > **Adicionar** e siga as *Etapas para instalar o conector para Certificados PFX importados*. Use o link de download no portal para começar o download do instalador **PfxCertificateConnectorBootstrapper.exe**. 

  Cada locatário do Intune tem suporte para uma única instância desse conector. É possível instalar esse conector no mesmo servidor de uma instância do Microsoft Intune Certificate Connector.

  Este conector manipula as solicitações para arquivos PFX importados para o Intune para criptografia de email S/MIME de um usuário específico.  

  Este conector poderá atualizar-se automaticamente quando novas versões forem disponibilizadas. Para usar a funcionalidade de atualização, faça é necessário:
  - baixar e instalar o Conector do Certificado PFX para o Microsoft Intune em seu servidor.
  - Para receber automaticamente atualizações importantes, verifique se os firewalls estão abertos que permitem que o conector contate **autoupdate.msappproxy.net** na porta **443**.  


- **Windows Server**:  
  use um Windows Server para hospedar:

  - Microsoft Intune Certificate Connector – para cenários de autenticação e assinatura de email S/MIME
  - Conector do Certificado PFX do Microsoft Intune – para cenários de criptografia de email S/MIME.

  É possível instalar os dois conectores (*Microsoft Intune Certificate Connector* e *Conector do Certificado PFX*) no mesmo servidor.

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportar o certificado raiz da AC Corporativa

Para autenticar um dispositivo com VPN, WiFi ou outros recursos, um dispositivo precisa de um certificado de Autoridade de Certificação raiz ou intermediário. As etapas a seguir explicam como obter o certificado necessário de sua AC Corporativa.

**Usar uma linha de comando**:  
1. faça logon no servidor da Autoridade de Certificação Raiz com a Conta Administrador.
 
2. Acesse **Iniciar** > **Executar** e, em seguida, insira **Cmd** para abrir o prompt de comando. 
    
3. Especifique **certutil -ca.cert ca_name.cer** para exportar o certificado raiz como um arquivo chamado *ca_name.cer*.



## <a name="configure-certificate-templates-on-the-ca"></a>Configurar modelos de certificado na AC

1. Entre na sua AC corporativa com uma conta que tenha privilégios administrativos.
2. Abra o console da **Autoridade de Certificação**, clicar com o botão direito do mouse em **Modelos de Certificado** e selecione **Gerenciar**.
3. Localize o modelo de certificado do **Usuário**, clique nele com o botão direito do mouse e escolha **Duplicar Modelo**. **Propriedades do Novo Modelo** se abre.

    > [!NOTE]
    > Para os cenários de autenticação e criptografia de email S/MIME, muitos administradores usam certificados separados para autenticação e criptografia. Caso esteja usando os Serviços de Certificados do Microsoft Active Directory, use o modelo **Trocar Somente Assinatura** para certificados de autenticação de email S/MIME e o modelo **Trocar Usuário** para certificados de criptografia S/MIME.  Caso esteja usando uma autoridade de certificação de terceiros, é recomendável examinar suas diretrizes para configurar modelos de autenticação e de criptografia.

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
13. Para que o servidor gerencie certificados de usuários e dispositivos registrados, use as seguintes etapas:

    1. Clique com o botão direito na Autoridade de Certificação e escolha **Propriedades**.
    2. Na guia Segurança, adicione a conta de Computador do servidor em que você executa os conectores (**Microsoft Intune Certificate Connector** ou **Conector do Certificado PFX do Microsoft Intune**). 
    3. Conceda as permissões **Emitir e Gerenciar Certificados** e **Solicitar Certificados** à conta de computador.

14. Saia da AC corporativa.

## <a name="download-install-and-configure-the-certificate-connectors"></a>Baixar, instalar e configurar os conectores de certificado

### <a name="microsoft-intune-certificate-connector"></a>Conector de Certificado do Microsoft Intune

> [!IMPORTANT]  
> O Microsoft Intune Certificate Connector não pode ser instalado na AC (Autoridade de Certificação) emissora; em vez disso, deve ser instalado em um servidor Windows separado.  

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Conectores de Certificação** > **Adicionar**.
3. Baixe e salve o arquivo do conector em um local que possa ser acessado do servidor em que o conector será instalado.

    ![Baixar o Microsoft Intune Certificate Connector](media/certificates-pfx-configure/download-ndes-connector.png)
 

4. Após a conclusão do download, entre no servidor. Em seguida:

    1. Verifique se o .NET 4.5 Framework ou superior está instalado, pois ele é necessário para o conector do Certificado NDES. O .NET 4.5 Framework é automaticamente incluído no Windows Server 2012 R2 e versões mais recentes.
    2. Execute o instalador (NDESConnectorSetup.exe) e aceite a localização padrão. Ele instala o conector para `\Program Files\Microsoft Intune\NDESConnectorUI`. Nas Opções do Instalador, selecione **Distribuição de PFX**. Continue e conclua a instalação.
    3. Por padrão, o serviço do conector é executado na conta Sistema Local. Se for necessário usar um proxy para acessar a Internet, confirme se a conta de serviço local pode acessar as configurações de proxy no servidor.

5. O Microsoft Intune Certificate Connector abre a guia **Registro**. Para habilitar a conexão com o Intune, selecione **Entrar** e insira uma conta com permissões administrativas globais.
6. Na guia **Avançado**, recomenda-se deixar a opção **Usar a conta SISTEMA deste computador (padrão)** selecionada.
7. **Aplicar** > **Fechar**
8. Retorne para o portal do Intune (**Intune** > **Configuração do Dispositivo** > **Conectores de Certificação**). Depois de alguns minutos, uma marca de seleção verde é exibida e o **Status da conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.
9. Se você tiver um proxy da Web em seu ambiente de rede, talvez seja necessário configurações adicionais para habilitar o funcionamento do conector. Para obter mais informações, consulte [Trabalhar com servidores de proxy locais existentes](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers) na documentação do Azure Active Directory.

> [!NOTE]  
> O Microsoft Intune Certificate Connector é compatível com o TLS 1.2. Se o TLS 1.2 estiver instalado no servidor que hospeda o conector, este usará o TLS 1.2. Caso contrário, o TLS 1.1 será usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

### <a name="pfx-certificate-connector-for-microsoft-intune"></a>Conector do Certificado PFX do Microsoft Intune

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Conectores de Certificação** > **Adicionar**
3. Faça o download e salve o Conector de Certificado PFX do Microsoft Intune. Salve-o em uma localização acessível por meio do servidor no qual você instalará o conector.
4. Após a conclusão do download, entre no servidor. Em seguida:

    1. Verifique se o .NET 4.6 Framework ou superior está instalado, pois ele é necessário para o Conector do Certificado PFX do Microsoft Intune. Se o .NET Framework 4.6 não estiver instalado, o instalador o instalará automaticamente.
    2. Execute o instalador (PfxCertificateConnectorBootstrapper.exe) e aceite o local padrão, que instala o conector em `Program Files\Microsoft Intune\PFXCertificateConnector`.
    3. O serviço do conector é executado na conta Sistema Local. Se for necessário usar um proxy para acesso à Internet, confirme se a conta de serviço local pode acessar as configurações de proxy no servidor.

5. O Conector do Certificado PFX do Microsoft Intune abre a guia **Registro** após a instalação. Para habilitar a conexão com o Intune, **Entre** e insira uma conta com permissões de administrador do Intune ou administrador global do Azure.
6. Feche a janela.
7. Retorne para o portal do Azure (**Intune** > **Configuração do Dispositivo** > **Conectores de Certificação**). Depois de alguns minutos, uma marca de seleção verde é exibida e o **Status da conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.

## <a name="create-a-trusted-certificate-profile"></a>Criar um perfil de certificado confiável

1. No [portal do Azure](https://portal.azure.com), acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
    ![Navegue até o Intune e crie um perfil para um certificado confiável](media/certificates-pfx-configure/certificates-pfx-configure-profile-new.png)

2. Insira as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina o **Tipo de perfil** como **Certificado confiável**

3. Acesse **Configurações** e insira o arquivo .cer do Certificado de Autoridade de Certificação Raiz exportado anteriormente.

   > [!NOTE]
   > Dependendo da plataforma escolhida na **Etapa 2**, você poderá ou não ter a opção de escolher o **Armazenamento de destino** do certificado.

   ![Criar um perfil e carregar um certificado confiável](media/certificates-pfx-configure/certificates-pfx-configure-profile-fill.png) 

4. Selecione **OK** > **Criar** para salvar seu perfil.
5. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de certificado PKCS

1. No [portal do Azure](https://portal.azure.com), acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
2. Insira as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina o **Tipo de perfil** como **Certificado PKCS**

3. Acesse **Configurações** e digite as seguintes propriedades:

    - **Limite de renovação (%)** : O recomendado é 20%.
    - **Período de validade do certificado**: Se você não alterou o modelo de certificado, essa opção pode ser definida como um ano.
    - **KSP (provedor de armazenamento de chaves)** : Para o Windows, selecione o local em que as chaves serão armazenadas no dispositivo.
    - **Autoridade de certificação**: Exibe o FQDN (nome de domínio totalmente qualificado) interno da AC corporativa.
    - **Nome da autoridade de certificação**: Lista o nome da AC corporativa, como "Autoridade de Certificação da Contoso".
    - **Nome do modelo de certificado**: O nome do modelo criado anteriormente. Lembre-se de que **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*.
    - **Formato de nome de entidade**: Defina essa opção como **Nome comum**, a menos que seja exigido o contrário.
    - **Nome alternativo da entidade**: Defina essa opção como **Nome UPN**, a menos que seja exigido o contrário.

4. Selecione **OK** > **Criar** para salvar seu perfil.
5. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

   > [!NOTE]
   > Em dispositivos com um perfil do Android Enterprise, os certificados instalados por meio de um perfil de certificado PKCS não ficam visíveis no dispositivo. Para confirmar se o certificado foi implantado com êxito, verifique o status do perfil no console do Microsoft Intune.

## <a name="create-a-pkcs-imported-certificate-profile"></a>Criar um perfil de certificado PKCS importado

Você pode importar os certificados emitidos anteriormente para um usuário específico em qualquer AC para o Intune. Os certificados importados são instalados em cada dispositivo registrado por um usuário. A criptografia de email S/MIME é o cenário mais comum para importar os certificados PFX existentes para o Intune. Um usuário pode ter muitos certificados para criptografar emails. As chaves privadas desses certificados precisam existir em todos os dispositivos de um usuário, de modo que eles possam descriptografar os emails criptografados anteriormente.

Para importar certificados no Intune, use os [cmdlets do PowerShell fornecidos no GitHub](https://github.com/Microsoft/Intune-Resource-Access).

Depois de importar os certificados para o Intune, crie um perfil de **certificado importado PKCS** e atribua-o aos grupos do Azure Active Directory.

1. No [portal do Azure](https://portal.azure.com), acesse **Intune** > **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
2. Insira as seguintes propriedades:

    - **Nome** do perfil
    - Opcionalmente, defina uma descrição
    - **Plataforma** na qual implantar o perfil
    - Defina **Tipo de perfil** como **Certificado PKCS importado**

3. Acesse **Configurações** e digite as seguintes propriedades:

    - **Finalidade pretendida**: A finalidade pretendida dos certificados que são importados para esse perfil. Um administrador pode ter certificados importados com finalidades pretendidas diferentes (por exemplo, autenticação, autenticação S/MIME ou criptografia S/MIME). A finalidade pretendida selecionada no perfil de certificado corresponde ao perfil de certificado com os certificados corretos importados.
    - **Período de validade do certificado**: Se você não alterou o modelo de certificado, essa opção pode ser definida como um ano.
    - **KSP (provedor de armazenamento de chaves)** : Para o Windows, selecione o local em que as chaves serão armazenadas no dispositivo.

4. Selecione **OK** > **Criar** para salvar seu perfil.
5. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="whats-new-for-connectors"></a>Novidades nos Conectores
São lançadas periodicamente atualizações para os dois conectores de certificado. Quando atualizamos um conector, é possível ler sobre as mudanças aqui. 

O *Conector de Certificados PFX do Microsoft Intune* [dá suporte a atualizações automáticas](#requirements), enquanto o *Intune Certificate Connector* é atualizado manualmente.

### <a name="may-17-2019"></a>17 de maio de 2019  
- **Conector do Certificado PFX do Microsoft Intune – versão 6.1905.0.404**  
  Alterações nessa versão:  
  - Correção de um problema em que os certificados PFX existentes continuam a ser reprocessados, o que faz com que o conector pare de processar novas solicitações. 

### <a name="may-6-2019"></a>6 de maio de 2019  
- **Conector do Certificado PFX do Microsoft Intune – versão 6.1905.0.402**  
  Alterações nessa versão:  
  - O intervalo de sondagem para o conector é reduzido de 5 minutos para 30 segundos.
 
### <a name="april-2-2019"></a>2 de abril de 2019  
- **Conector do certificado Intune – versão 6.1904.1.0**  
  Alterações nessa versão:  
  - correção de um problema em que o conector poderia não conseguir se registrar no Intune após se conectar ao conector com uma conta de administrador global.  
  - Inclui correções de confiabilidade para revogação de certificado.  
  - Inclui correções de desempenho para aumentar a rapidez com que as solicitações de certificados PKCS são processadas.  

- **Conector do Certificado PFX do Microsoft Intune – versão 6.1904.0.401**
  > [!NOTE]  
  > A atualização automática para essa versão do conector PFX não estará disponível até 11 de abril de 2019.  

  Alterações nessa versão:  
  - correção de um problema em que o conector poderia não conseguir se registrar no Intune após se conectar ao conector com uma conta de administrador global.  


## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

[Use certificados SCEP](certificates-scep-configure.md) ou [emita certificados PKCS em um serviço Web do Digicert PKI Manager](certificates-digicert-configure.md).


