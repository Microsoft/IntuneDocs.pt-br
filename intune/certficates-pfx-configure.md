---
title: Usar certificados PKCS com o Microsoft Intune – Azure | Micrososft Docs
description: Adicione ou crie certificados de Public Key Cryptography Standards com o Microsoft Intune, incluindo as etapas para exportar um certificado raiz, configure o modelo do certificado, baixe e instale o Microsoft Intune Certificate Connector (NDES), crie um perfil de configuração de dispositivo, crie um perfil de Certificado PKCS no Azure e sua Autoridade de Certificação.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b3bfe76173eff76a3175952bef5c6e23ad5e429
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271534"
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configurar e usar certificados PKCS com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Certificados são usados para autenticar e proteger o acesso aos recursos corporativos, como uma VPN ou sua rede Wi-Fi. Este artigo mostra como exportar um certificado PKCS e, em seguida, adicionar o certificado a um perfil do Intune. 

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

  O conector do Certificado NDES também dá suporte ao modo do padrão FIPS. O FIPS não é necessário, mas você pode emitir e revogar certificados quando ele está habilitado.

- **Windows Server**: hospeda o Microsoft Intune Certificate Connector (NDESConnectorSetup.exe)

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportar o certificado raiz da AC Corporativa

Para autenticação com VPN, WiFi e outros recursos, é necessário ter um certificado raiz ou de AC intermediária em cada dispositivo. As etapas a seguir explicam como obter o certificado necessário de sua AC Corporativa.

1. Entre na sua AC corporativa com uma conta que tenha privilégios administrativos.
2. Abra um prompt de comando como administrador.
3. Exporte o Certificado de Autoridade de Certificação Raiz (.cer) para um local em que você possa acessá-lo mais tarde.

   Por exemplo:

4. Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.

   `certutil -ca.cert certnew.cer`

   Para saber mais, veja [Tarefas do Certutil para gerenciar certificados](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Configurar modelos de certificado na autoridade de certificação

1. Entre na sua AC corporativa com uma conta que tenha privilégios administrativos.
2. Abra o console da **Autoridade de Certificação**, clicar com o botão direito do mouse em **Modelos de Certificado** e selecione **Gerenciar**.
3. Localize o modelo de certificado do **Usuário**, clique nele com o botão direito do mouse e escolha **Duplicar Modelo**. **Propriedades do Novo Modelo** se abre.
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
11. Clique em **Aplicar** e em **OK** para salvar o modelo de certificado.
12. Feche o **Console de Modelos de Certificado**.
13. No console da **Autoridade de Certificação**, clique com o botão direito em **Modelos de Certificado**, **Novo** e em **Modelo de certificado a ser emitido**. Escolha o modelo que você criou nas etapas anteriores e selecione **OK**.
14. Para o servidor gerenciar certificados em nome de usuários e dispositivos inscritos no Intune, execute estas etapas:

    1. Clique com o botão direito na Autoridade de Certificação e escolha **Propriedades**.
    2. Na guia Segurança, adicione a Conta do Computador do servidor onde você executa o Microsoft Intune Certificate Connector. Conceda as permissões **Emitir e Gerenciar Certificados** e **Solicitar Certificados** à conta de computador.

15. Saia da AC corporativa.

## <a name="download-install-and-configure-the-certificate-connector"></a>Baixar, instalar e configurar o conector de certificado

![ConnectorDownload][ConnectorDownload]

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** e, em seguida, selecione **Autoridade de Certificação**.
4. Selecione **Adicionar** e **Baixar o arquivo do Conector**. Salve o download em um local em que você possa acessá-lo pelo servidor no qual você vai instalá-lo.
5. Após a conclusão do download, entre no servidor. Em seguida:

    1. Verifique se o .NET 4.5 Framework está instalado, pois ele é necessário para o conector do Certificado NDES. O .NET 4.5 Framework é automaticamente incluído no Windows Server 2012 R2 e versões mais recentes.
    2. Execute o instalador (NDESConnectorSetup.exe) e aceite a localização padrão. Ele instala o conector para `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`. Nas Opções do Instalador, selecione **Distribuição de PFX**. Continue e conclua a instalação.

6. O Conector NDES abrirá a guia **Registro**. Para habilitar a conexão com o Intune, selecione **Entrar** e insira uma conta com permissões administrativas globais.
7. Na guia **Avançado**, deixe **Usar a conta SISTEMA deste computador (padrão)** selecionado.
8. **Aplicar** e, em seguida, **Fechar**.
9. Retorne para o Portal do Azure (**Intune** > **Configuração do Dispositivo** > **Autoridade de Certificação**). Depois de alguns minutos, uma marca de seleção verde é exibida e o **Status da conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.

> [!NOTE]
> O suporte ao TLS 1.2 é incluído no conector do Certificado NDES. Se o servidor com o conector do Certificado NDES instalado dá suporte ao TLS 1.2, o protocolo TLS 1.2 é usado. Se o servidor não dá suporte ao TLS 1.2, o TLS 1.1 é usado. Atualmente, o TLS 1.1 é usado para autenticação entre os dispositivos e o servidor.

## <a name="create-a-device-configuration-profile"></a>Criar um perfil de configuração do dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Acesse **Intune** > **Configuração de Dispositivo** > **Perfis** > **Criar perfil**.

   ![NavigateIntune][NavigateIntune]

3. Digite as seguintes propriedades:

  - **Nome** do perfil
  - Opcionalmente, defina uma descrição
  - **Plataforma** na qual implantar o perfil
  - Defina o **Tipo de perfil** como **Certificado confiável**

4. Acesse **Configurações** e insira o arquivo .cer do Certificado de Autoridade de Certificação Raiz exportado anteriormente.

   > [!NOTE]
   > Dependendo da plataforma escolhida na **Etapa 3**, você poderá ou não ter a opção de escolher o **Armazenamento de destino** do certificado.

   ![ProfileSettings][ProfileSettings]

5. Selecione **OK** e, em seguida, **Criar** para salvar o perfil.
6. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de Certificado PKCS

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Acesse **Intune** > **Configuração de Dispositivo** > **Perfis** > **Criar perfil**.
3. Digite as seguintes propriedades:

  - **Nome** do perfil
  - Opcionalmente, defina uma descrição
  - **Plataforma** na qual implantar o perfil
  - Defina o **Tipo de perfil** como **Certificado PKCS**

4. Acesse **Configurações** e digite as seguintes propriedades:

  - **Limite de renovação (%)** - O recomendado é de 20%.
  - **Período de validade do certificado** – Se você não alterou o modelo de certificado, essa opção pode ser definida como um ano.
  - **Autoridade de certificação** – Exibe o FQDN (nome de domínio totalmente qualificado) interno da sua AC corporativa.
  - **Nome da autoridade de certificação** – Lista o nome da sua AC corporativa e pode ser diferente do item anterior.
  - **Nome do modelo de certificado** – O nome do modelo criado anteriormente. Lembre-se de que **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*.
  - **Formato do nome da entidade** - Defina essa opção como um **Nome comum**, a menos que seja necessário de outra forma.
  - **Nome alternativo da entidade** - Defina essa opção como **Nome UPN**, a menos que seja necessário de outra forma.
  - **Uso avançado de chave** – Desde que você tenha usado as configurações padrão na Etapa 10 na seção [Configurar modelos de certificado na autoridade de certificação](#configure-certificate-templates-on-the-certification-authority) (neste artigo), adicione os seguintes **Valores predefinidos** da seleção:
    - **Qualquer Objetivo**
    - **Autenticação do Cliente**
    - **Email Seguro**
  - **Certificado Raiz** – (para Perfis Android) Lista o arquivo .cer exportado na Etapa 3 na seção [Exportar o certificado raiz da AC Corporativa](#export-the-root-certificate-from-the-enterprise-ca) (neste artigo).

5. Selecione **OK** e, em seguida, **Criar** para salvar o perfil.
6. Para atribuir o novo perfil a um ou mais dispositivos, confira [Atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="next-steps"></a>Próximas etapas
[Usar certificados SCEP](certificates-scep-configure.md) ou [emitir certificados PKCS em um serviço Web do Symantec PKI Manager](certificates-symantec-configure.md).

[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navegar até o Intune no Portal do Azure e criar um novo perfil para um certificado confiável"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Criar um perfil e carregar um certificado confiável"
[ConnectorDownload]: ./media/certificates-download-connector.png "Baixar o conector de certificado do Portal do Azure"  
