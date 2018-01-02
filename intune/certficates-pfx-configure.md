---
title: Configurar e gerenciar certificados PKCS com o Intune
titleSuffix: Intune on Azure
description: Criar e atribuir certificados PKCS com o Intune."
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b72c4899debb0bbb7cb755327606cad1e239c611
ms.sourcegitcommit: 6d5c919286b0e285f709d9b918624b927f99f979
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Configurar e gerenciar certificados PKCS com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Requisitos

Para usar certificados PKCS com o Intune, você precisa ter a seguinte infraestrutura:

* Um domínio do AD DS (Active Directory Domain Services) configurado.
 
  Se você precisar de mais informações sobre como instalar e configurar o AD DS, confira este artigo [Design e planejamento do AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Uma AC (autoridade de certificação) corporativa configurada.

  Se você precisar de mais informações sobre como instalar e configurar o AD CS (Serviços de Certificados do Active Directory), confira o artigo [Guia passo a passo dos Serviços de Certificado do Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > O Intune exige que você execute o AD CS com uma AC (Autoridade de Certificação) Corporativa, não com uma AC Autônoma.

* Um cliente que tenha conectividade com a AC Corporativa.
* Uma cópia exportada de seu certificado raiz de sua AC Corporativa.
* O Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) baixado do seu Portal do Intune.
* Um Windows Server disponível para hospedar o Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportar o certificado raiz da AC Corporativa

Você precisa de um certificado raiz ou de AC intermediária em cada dispositivo para autenticação com VPN, Wi-Fi e outros recursos. As etapas a seguir explicam como obter o certificado necessário de sua AC Corporativa.

1. Faça logon em sua AC Corporativa com uma conta que tenha privilégios administrativos.
2. Abra um prompt de comando como administrador.
3. Exporte o Certificado de AC Raiz para um local onde você possa acessá-lo mais tarde.

   Por exemplo:

   `certutil -ca.cert certnew.cer`

   Para saber mais, veja [Tarefas do Certutil para gerenciar certificados](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).


## <a name="configure-certificate-templates-on-the-certification-authority"></a>Configurar modelos de certificado na autoridade de certificação

1. Faça logon em sua AC Corporativa com uma conta que tenha privilégios administrativos.
2. Abra o console da **Autoridade de Certificação**.
3. Clique com o botão direito em **Modelos de Certificado** e escolha **Gerenciar**.
4. Localize o modelo de certificado do **Usuário**, clique duas vezes nele e escolha **Duplicar Modelo**. Uma janela é aberta, **Propriedades do Novo Modelo**.
5. Na guia **Compatibilidade**
   * Defina **Autoridade de Certificação** como **Windows Server 2008 R2**
   * Defina **Destinatário do certificado** como **Windows 7/Server 2008 R2**
6. Na guia **Geral** :
   * Defina **Nome de exibição do modelo** como algo significativo para você.

   > [!WARNING]
   > **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*. Anote o nome do modelo para uso posterior.

7. Na guia **Tratamento de Solicitação**, marque a caixa **Permitir que a chave privada seja exportada**.
8. Na guia **Criptografia**, confirme se o **Tamanho mínimo da chave** está definido como 2048.
9. Na guia **Nome da Entidade**, escolha o botão de opção **Fornecer na solicitação**.
10. Na guia **Extensões**, confirme a existência de Encrypting File System, Email Seguro e Autenticação de Cliente em **Políticas de Aplicativo**.
    
      > [!IMPORTANT]
      > Para modelos de certificado do iOS e macOS, na guia **Extensões**, edite **Uso da Chave** e verifique se a opção **A assinatura é uma prova de origem** não está selecionada.

11. Na guia **Segurança**, adicione a Conta de Computador do servidor onde você instala o Microsoft Intune Certificate Connector.
    * Atribua as permissões **Leitura** e **Inscrição** à essa conta.
12. Clique em **Aplicar**, depois clique em **OK** para salvar o modelo de certificado.
13. Feche o **Console de Modelos de Certificado**.
14. No console da **Autoridade de Certificação**, clique com o botão direito em **Modelos de Certificado**, **Novo** e em **Modelo de certificado a ser emitido**.
    * Escolha o modelo que você criou nas etapas anteriores e clique em **OK**.
15. Para o servidor gerenciar certificados em nome de usuários e dispositivos inscritos no Intune, execute estas etapas:

    a. Clique com o botão direito na Autoridade de Certificação e escolha **Propriedades**.

    b. Na guia Segurança, adicione a Conta do Computador do servidor onde você executa o Microsoft Intune Certificate Connector.
      * Conceda as permissões **Emitir e Gerenciar Certificados** e **Solicitar Certificados** à conta de computador.
16. Faça logoff da AC Corporativa.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Baixar, instalar e configurar o Microsoft Intune Certificate Connector

![ConnectorDownload][ConnectorDownload]

1. No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Na folha **Intune**, escolha **Configuração do Dispositivo**. 
3. Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**. 
4. Clique em **Adicionar** e selecione **Baixar arquivo do Conector**. Salve o download em um local em que você possa acessá-lo pelo servidor no qual você vai instalá-lo. 
5.  Faça logon no servidor onde você instalará o Microsoft Intune Certificate Connector.
6.  Execute o instalador e aceite o local padrão. Ele instala o conector em C:\Arquivos de Programas\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.
    1. Na página Opções do Instalador escolha **Distribuição PFX** e clique em **Avançar**.
    2. Clique em **Instalar** e aguarde a conclusão da instalação.
    3. Na página Conclusão, marque a caixa denominada **Inicializar Conector do Intune** e clique em **Concluir**.
7.  A janela do Conector NDES agora deve abrir a guia **Inscrição**. Para habilitar a conexão com o Intune, clique em **Entrar** e forneça uma conta com permissões administrativas.
8.  Na guia **Avançado**, você pode deixar o botão de opção **Usar a conta SISTEMA deste computador (padrão)** selecionado.
9.  Clique em **Aplicar** e em **Fechar**.
10. Agora volte ao Portal do Azure. Depois de alguns minutos, você deverá ver uma marca de seleção verde e a palavra **Ativo** em **Status da conexão** em **Intune** > **Configuração do Dispositivo** > **Autoridade de Certificação**. Essa confirmação avisa que o servidor do conector pode se comunicar com o Intune.


## <a name="create-a-device-configuration-profile"></a>Criar um perfil de configuração do dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Navegue até **Intune**, **Configuração do dispositivo**, **Perfis** e clique em **Criar perfil**.

   ![NavigateIntune][NavigateIntune]

3. Preencha as seguintes informações:
   * **Nome** do perfil
   * Opcionalmente, defina uma descrição
   * **Plataforma** na qual implantar o perfil
   * Defina o **Tipo de perfil** como **Certificado confiável**
4. Navegue até **Configurações** e forneça o arquivo .cer do Certificado de AC Raiz exportado anteriormente.

   > [!NOTE]
   > Dependendo da plataforma que você escolheu na **Etapa 3**, você poderá ou não ter a opção de escolher o **Armazenamento de destino** do certificado.

   ![ProfileSettings][ProfileSettings]

5. Clique em **OK**, depois em **Criar** para salvar o perfil.
6. Para atribuir o novo perfil a um ou mais dispositivos, consulte [Como atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de Certificado PKCS

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Navegue até **Intune**, **Configuração do dispositivo**, **Perfis** e clique em **Criar perfil**.
3. Preencha as seguintes informações:
   * **Nome** do perfil
   * Opcionalmente, defina uma descrição
   * **Plataforma** na qual implantar o perfil
   * Defina o **Tipo de perfil** como **Certificado PKCS**
4. Navegue até **Configurações** e forneça as seguintes informações:
   * **Limite de renovação (%)** - O recomendado é de 20%.
   * **Período de validade do certificado** - Se você não alterou o modelo de certificado, essa opção deve ser definida como um ano.
   * **Autoridade de certificação** - Esta opção é o FQDN (nome de domínio totalmente qualificado) interno da sua AC Corporativa.
   * **Nome da autoridade de certificação** - Esta opção é o nome de sua AC Corporativa e pode ser diferente do item anterior.
   * **Nome do modelo de certificado** - Esta opção é o nome do modelo criado anteriormente. Lembre-se de que **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*.
   * **Formato do nome da entidade** - Defina essa opção como um **Nome comum**, a menos que seja necessário de outra forma.
   * **Nome alternativo da entidade** - Defina essa opção como **Nome UPN**, a menos que seja necessário de outra forma.
   * **Uso estendido da chave** - Desde que você tenha usado as configurações padrão na Etapa 10 na seção anterior **Configurar modelos de certificado na autoridade de certificação**, adicione os seguintes **Valores predefinidos** na caixa de seleção:
      * **Qualquer Objetivo**
      * **Autenticação do Cliente**
      * **Email Seguro**
   * **Certificado Raiz** - (para Perfis Android) essa opção é o arquivo .cer exportado na Etapa 3 na seção anterior [Exportar o certificado raiz da AC Corporativa](#export-the-root-certificate-from-the-enterprise-ca).

5. Clique em **OK**, depois em **Criar** para salvar o perfil.
6. Para atribuir o novo perfil a um ou mais dispositivos, consulte o artigo [Como atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navegar até o Intune no Portal do Azure e criar um novo perfil para um certificado confiável"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Criar um perfil e carregar um certificado confiável"
[ConnectorDownload]: ./media/certificates-download-connector.png "Baixar o conector de certificado do Portal do Azure"  
