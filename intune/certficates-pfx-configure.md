---
title: Usar certificados PKCS com o Microsoft Intune – Azure | Micrososft Docs
description: Adicionar ou criar certificados de Public Key Cryptography Standards com o Microsoft Intune, incluindo as etapas para exportar um certificado raiz, configurar o modelo do certificado, baixar e instalar o Microsoft Intune Certificate Connector, criar um perfil de configuração de dispositivo, criar um perfil de Certificado PKCS no Azure e sua Autoridade de Certificação
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61a190be2b4685030438988dab0d0134a8fa9f9b
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="configure-and-use-pkcs-certificates-with-intune"></a>Configurar e usar certificados PKCS com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Certificados são usados para autenticar e proteger o acesso aos recursos corporativos, como uma VPN ou sua rede Wi-Fi. Este artigo mostra como exportar um certificado PKCS e, em seguida, adicionar o certificado a um perfil do Intune. 

## <a name="requirements"></a>Requisitos

Para usar certificados PKCS com o Intune, verifique se você tem a seguinte infraestrutura:

* Um domínio do AD DS (Active Directory Domain Services) configurado.
 
  Para obter mais informações sobre como instalar e configurar o AD DS, consulte [Design e planejamento do AD DS](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Uma AC (autoridade de certificação) corporativa configurada.

  Para ver mais informações sobre como instalar e configurar o AD CS (Serviços de Certificados do Active Directory), consulte o artigo [Guia passo a passo dos Serviços de Certificados do Active Directory](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > O Intune exige que você execute o AD CS com uma AC (Autoridade de Certificação) Corporativa, não com uma AC Autônoma.

* Um cliente que tenha conectividade com a AC Corporativa.
* Uma cópia exportada de seu certificado raiz de sua AC Corporativa.
* O Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) baixado do seu Portal do Intune.
* Um Windows Server para hospedar o Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportar o certificado raiz da AC Corporativa

Para autenticação com VPN, Wi-Fi e outros recursos, é necessário ter um certificado raiz ou de Autoridade de Certificação intermediário em cada dispositivo. As etapas a seguir explicam como obter o certificado necessário de sua AC Corporativa.

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
   * Defina **Autoridade de Certificação** como **Windows Server 2008 R2**
   * Defina **Destinatário do certificado** como **Windows 7/Server 2008 R2**
5. Na guia **Geral** :
   * Defina **Nome de exibição do modelo** como algo significativo para você.

   > [!WARNING]
   > **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*. Observe o nome do modelo, pois ele será necessário mais tarde.

6. Em **Tratamento de Solicitação**, selecione **Permitir que a chave privada seja exportada**.
7. Em **Criptografia**, confirme se o **Tamanho mínimo da chave** está definido como 2048.
8. Em **Nome da Entidade**, escolha **Fornecer na solicitação**.
9. Em **Extensões**, confirme a existência de Encrypting File System, Email Seguro e Autenticação de Cliente em **Políticas de Aplicativo**.
    
      > [!IMPORTANT]
      > Para modelos de certificado do iOS, na guia **Extensões**, atualize **Uso da Chave** e confirme se a opção **A assinatura é uma prova de origem** não está selecionada.

10. Em **Segurança**, adicione a Conta de Computador do servidor de instalação do Microsoft Intune Certificate Connector.
    * Atribua as permissões **Leitura** e **Inscrição** à essa conta.
11. Clique em **Aplicar** e em **OK** para salvar o modelo de certificado.
12. Feche o **Console de Modelos de Certificado**.
13. No console da **Autoridade de Certificação**, clique com o botão direito em **Modelos de Certificado**, **Novo** e em **Modelo de certificado a ser emitido**.
    * Escolha o modelo que você criou nas etapas anteriores e selecione **OK**.
14. Para o servidor gerenciar certificados em nome de usuários e dispositivos inscritos no Intune, execute estas etapas:

    a. Clique com o botão direito na Autoridade de Certificação e escolha **Propriedades**.

    b. Na guia Segurança, adicione a Conta do Computador do servidor onde você executa o Microsoft Intune Certificate Connector.
      * Conceda as permissões **Emitir e Gerenciar Certificados** e **Solicitar Certificados** à conta de computador.
15. Saia da AC corporativa.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Baixar, instalar e configurar o Microsoft Intune Certificate Connector

![ConnectorDownload][ConnectorDownload]

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** e filtre por **Intune**. Selecione **Microsoft Intune** e, em seguida, **Configuração do dispositivo**. 
2. Selecione **Autoridade de Certificação**, **Adicionar** e, em seguida, **Baixar o arquivo do Connector**. Salve o download em um local que pode ser acessado do servidor no qual ele será instalado. 
3. Entre neste servidor e execute o instalador: 

    1. Aceite o local padrão. Ele instala o conector para `\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe`.
    2. Nas Opções do Instalador, selecione **Distribuição de PFX** e **Avançar**.
    3. **Instalar** e aguarde a conclusão da instalação.
    4. Quando for concluído, verifique **Inicialização do conector do Intune** e, em seguida, **Concluir**.

4. A janela do Conector NDES deverá abrir a guia **Registro**. Para habilitar a conexão com o Intune, selecione **Entrar** e digite uma conta com permissões administrativas globais.
5. Na guia **Avançado**, deixe **Usar a conta SISTEMA deste computador (padrão)** selecionado.
6. **Aplicar** e, em seguida, **Fechar**.
7. Retorne para o Portal do Azure (**Intune** > **Configuração do Dispositivo** > **Autoridade de Certificação**). Depois de alguns minutos, um tique verde é exibido e o **Status de conexão** fica **Ativo**. O servidor do conector agora pode se comunicar com o Intune.

## <a name="create-a-device-configuration-profile"></a>Criar um perfil de configuração do dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Acesse **Intune**, **Configuração de dispositivo**, **Perfis** e selecione **Criar perfil**.

   ![NavigateIntune][NavigateIntune]

3. Digite as seguintes propriedades:
   * **Nome** do perfil
   * Opcionalmente, defina uma descrição
   * **Plataforma** na qual implantar o perfil
   * Defina o **Tipo de perfil** como **Certificado confiável**

4. Acesse **Configurações** e insira o arquivo .cer do Certificado de Autoridade de Certificação Raiz exportado anteriormente.

   > [!NOTE]
   > Dependendo da plataforma escolhida na **Etapa 3**, você poderá ou não ter a opção de escolher o **Armazenamento de destino** do certificado.

   ![ProfileSettings][ProfileSettings]

5. Selecione **OK** e, em seguida, **Criar** para salvar o perfil.
6. Para atribuir o novo perfil a um ou mais dispositivos, consulte [Como atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Criar um perfil de Certificado PKCS

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Acesse **Intune**, **Configuração de dispositivo**, **Perfis** e selecione **Criar perfil**.
3. Digite as seguintes propriedades:
   * **Nome** do perfil
   * Opcionalmente, defina uma descrição
   * **Plataforma** na qual implantar o perfil
   * Defina o **Tipo de perfil** como **Certificado PKCS**
4. Acesse **Configurações** e digite as seguintes propriedades:
   * **Limite de renovação (%)** - O recomendado é de 20%.
   * **Período de validade do certificado** – Se você não alterou o modelo de certificado, essa opção pode ser definida como um ano.
   * **Autoridade de certificação** – Exibe o FQDN (nome de domínio totalmente qualificado) interno da sua AC corporativa.
   * **Nome da autoridade de certificação** – Lista o nome da sua AC corporativa e pode ser diferente do item anterior.
   * **Nome do modelo de certificado** – O nome do modelo criado anteriormente. Lembre-se de que **Nome do modelo** é, por padrão, o mesmo que o **Nome de exibição do modelo** *sem espaços*.
   * **Formato do nome da entidade** - Defina essa opção como um **Nome comum**, a menos que seja necessário de outra forma.
   * **Nome alternativo da entidade** - Defina essa opção como **Nome UPN**, a menos que seja necessário de outra forma.
   * **Uso avançado de chave** – Desde que você tenha usado as configurações padrão na Etapa 10 na seção [Configurar modelos de certificado na autoridade de certificação](#configure-certificate-templates-on-the-certification-authority) (neste artigo), adicione os seguintes **Valores predefinidos** da seleção:
      * **Qualquer Objetivo**
      * **Autenticação do Cliente**
      * **Email Seguro**
   * **Certificado Raiz** – (para Perfis Android) Lista o arquivo .cer exportado na Etapa 3 na seção [Exportar o certificado raiz da AC Corporativa](#export-the-root-certificate-from-the-enterprise-ca) (neste artigo).

5. Selecione **OK** e, em seguida, **Criar** para salvar o perfil.
6. Para atribuir o novo perfil a um ou mais dispositivos, consulte o artigo [Como atribuir perfis de dispositivo do Microsoft Intune](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Navegar até o Intune no Portal do Azure e criar um novo perfil para um certificado confiável"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Criar um perfil e carregar um certificado confiável"
[ConnectorDownload]: ./media/certificates-download-connector.png "Baixar o conector de certificado do Portal do Azure"  
