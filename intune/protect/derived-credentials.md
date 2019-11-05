---
title: Usar credenciais derivadas para dispositivos móveis no Microsoft Intune – Azure | Microsoft Docs
description: Use credenciais derivadas em dispositivos móveis como um método de autenticação para VPN do Intune, email, perfis Wi-Fi, aplicativos e S/MIME e criptografia. As credenciais derivadas são uma implementação das diretrizes do NIST para Publicação Especial 800-157.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: lacranda
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1716da820fd0d9a4b6d1bbc5024440cfb141c5a1
ms.sourcegitcommit: 0d6f323152ec62f7d383891cce12ea0a4289cd8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2019
ms.locfileid: "72889560"
---
# <a name="use-derived-credentials-in-microsoft-intune"></a>Usar credenciais derivadas no Microsoft Intune

*Este artigo se aplica a dispositivos que executam o iOS*

Em um ambiente em que cartões inteligentes são necessários para autenticação ou criptografia e assinatura, agora você pode usar o Intune para provisionar dispositivos móveis com um certificado derivado do cartão inteligente de um usuário. Esse certificado é chamado de *credencial derivada*. O Intune [dá suporte a vários emissores de credenciais derivadas](#supported-issuers), embora você possa usar apenas um único emissor por locatário por vez. 

As credenciais derivadas são uma implementação das diretrizes do NIST (National Institute of Standards and Technology) para as credenciais de PIV (Verificação de Identidade Pessoal Derivada) como parte da SP (Publicação Especial) 800-157.  

**Com a implementação do Intune**:  

- o administrador do Intune configura seu locatário para trabalhar com um emissor de credencial derivada com suporte. Você não precisa definir nenhuma configuração específica do Intune no sistema do emissor de credenciais derivadas.

- O administrador do Intune especifica a **Credencial derivada** como o *método de autenticação* para os seguintes objetos:  

  - Tipos de perfil comuns como Wi-Fi, VPN e Email, que inclui o aplicativo de email nativo do iOS 

  - Autenticação de aplicativo

  - Criptografia e assinatura S/MIME 

- Os usuários obtêm uma credencial derivada usando seu cartão inteligente e um computador para autenticar-se no emissor de credenciais derivadas. O emissor emite para o dispositivo móvel um certificado derivado de seu cartão inteligente. 

- Depois que o dispositivo recebe a credencial derivada, ela é usada para autenticação para assinatura e criptografia S/MIME quando os perfis de acesso de aplicativos ou de um recurso exigem a credencial derivada. 

## <a name="prerequisites"></a>Pré-requisitos

Examine as seguintes informações antes de configurar seu locatário para usar credenciais derivadas.

### <a name="supported-platforms"></a>Plataformas com Suporte

O Intune dá suporte a credenciais derivadas nas seguintes plataformas de sistema operacional:
- iOS/iPadOS
 
### <a name="supported-issuers"></a>Emissores com suporte

O Intune dá suporte a um único emissor de credenciais derivadas por locatário. Você pode configurar o Intune para trabalhar com os seguintes emissores:  

- **DISA Purebred**: https://cyber.mil/pki-pke/purebred/ 
- **Entrust Datacard**: https://www.entrustdatacard.com/
- **Intercede**: https://www.intercede.com/

Para obter detalhes importantes sobre o uso de diferentes emissores, confira as orientações do emissor<!-- , including the issuers end-user workflow-->. Para obter mais informações, confira [Planejar credenciais derivadas](#plan-for-derived-credentials) neste artigo.

> [!IMPORTANT]  
> Se você excluir um emissor de credenciais derivadas do seu locatário, as credenciais derivadas configuradas por meio desse emissor não funcionarão mais.  
> 
> Confira [Alterar o emissor de credenciais derivadas](#change-the-derived-credential-issuer) posteriormente neste artigo.   

### <a name="company-portal-app"></a>Aplicativo do Portal da Empresa

Planeje implantar o aplicativo Portal da Empresa do Intune em dispositivos que serão registrados para uma credencial derivada. Os usuários do dispositivo usam o aplicativo Portal da Empresa para iniciar o processo de registro de credenciais. 

Para dispositivos iOS, confira [Adicionar aplicativos da iOS Store ao Microsoft Intune](../apps/store-apps-ios.md).

## <a name="plan-for-derived-credentials"></a>Planejar credenciais derivadas

Entenda as considerações a seguir antes de configurar um emissor de credenciais derivados.  

### <a name="1-review-the-documentation-for-your-chosen-derived-credential-issuer"></a>1) Examine a documentação do emissor de credenciais derivadas escolhido  

Antes de configurar um emissor, examine a documentação dele para entender como o sistema entrega credenciais derivadas a dispositivos.  

Dependendo do emissor escolhido, talvez seja necessário que a equipe esteja disponível no momento do registro para ajudar os usuários a concluir o processo. Você também deve examinar suas configurações atuais do Intune para garantir que elas não bloqueiem o acesso necessário para dispositivos ou usuários concluírem a solicitação de credencial. 

Por exemplo, você pode usar o acesso condicional para bloquear o acesso a email para dispositivos sem conformidade. Se você depender de notificações por email para informar o usuário para iniciar o processo de registro de credenciais derivadas, seus usuários poderão não receber essas instruções até que estejam em conformidade com a política.  

Da mesma forma, alguns fluxos de trabalho de solicitação de credenciais derivadas exigem o uso da câmera do dispositivo para digitalizar um código QR na tela. Esse código vincula esse dispositivo à solicitação de autenticação que ocorreu no emissor de credenciais derivadas com as credenciais de cartão inteligente do usuário. Se as políticas de configuração do dispositivo bloquearem o uso da câmera, o usuário não poderá concluir a solicitação de registro de credenciais derivadas.  

Informações gerais:  

- Você pode configurar apenas um único emissor por locatário por vez. Esse emissor está disponível para todos os usuários e dispositivos com suporte em seu locatário.

- Os usuários não serão notificados de que devem se registrar para credenciais derivadas até que você os direcione com uma política que requeira credenciais derivadas.

- A notificação pode ser feita por meio de notificação de aplicativo para o Portal da Empresa, por email ou ambos. Se você optar por usar notificações por email e usar o acesso condicional habilitado, os usuários poderão não receber a notificação por email se seu dispositivo não estiver em conformidade.

### <a name="2-review-the-end-user-workflow-for-your-chosen-issuer"></a>2) Examine o fluxo de trabalho de usuário final para o emissor escolhido

A seguir estão as principais considerações para cada parceiro com suporte<!--  , and links to that issuers end-user workflow -->.  Familiarize-se com essas informações para poder garantir que suas políticas e configurações do Intune não impeçam que usuários e dispositivos concluam com êxito o registro para uma credencial derivada desse emissor.

#### <a name="disa-purebred"></a>DISA Purebred

Entenda o fluxo de trabalho do usuário final e os principais requisitos:  
<!-- TEMP EDIT - preceeding line to be replaced with the following once user content is ready. 
Review the [user workflow for DISA Purebred](https://docs.microsoft.com/intune-user-help/enroll-ios-device-disa-purebred). Key requirements for this workflow include:  
-->

- Os usuários precisam de acesso a um computador ou KIOSK em que eles podem usar seu cartão inteligente para se autenticar no emissor. 

- Os dispositivos que serão registrados para uma credencial derivada devem instalar o aplicativo Portal da Empresa do Intune.

- Use o Intune para [implantar o aplicativo DISA Purebred](#deploy-the-disa-purebred-app) em dispositivos que serão registrados para uma credencial derivada. Esse aplicativo deve ser implantado pelo Intune para ser gerenciado e pode funcionar com o aplicativo Portal da Empresa do Intune. Este aplicativo é usado por usuários do dispositivo para concluir a solicitação de credenciais derivadas. 

- O aplicativo DISA Purebred requer um [VPN por aplicativo](../configuration/vpn-settings-configure.md) para garantir que o aplicativo possa acessar o DISA Purebred durante o registro para a credencial derivada. 

- Os usuários do dispositivo devem trabalhar com um agente em tempo real durante o processo de registro. Durante o registro, são fornecidas senhas avulsos por tempo limitado ao usuário conforme ele avança no processo de registro.   

Para obter informações sobre como baixar e configurar o aplicativo DISA Purebred, confira [Implantar o aplicativo DISA Purebred](#deploy-the-disa-purebred-app) mais adiante neste artigo.  

#### <a name="entrust-datacard"></a>Entrust Datacard  

Entenda o fluxo de trabalho do usuário final e os principais requisitos:  
<!-- TEMP EDIT - preceeding line to be replaced with the following once user content is ready. 
Review the [user workflow for Entrust Datacard](https://docs.microsoft.com/intune-user-help/enroll-ios-device-entrust). Key requirements for this workflow include: 
--> 
- Os usuários precisam de acesso a um computador ou KIOSK em que eles podem usar seu cartão inteligente para se autenticar no emissor. 

- Os dispositivos que serão registrados para uma credencial derivada devem instalar o aplicativo Portal da Empresa do Intune.

- O uso de uma câmera de dispositivo para digitalizar um código QR que vincula a solicitação de autenticação à solicitação de credencial derivada do dispositivo móvel.

#### <a name="intercede"></a>Intercede

Entenda o fluxo de trabalho do usuário final e os principais requisitos:  
<!-- TEMP EDIT - preceeding line to be replaced with the following once user content is ready. 
Review the [user workflow for Intercede](https://docs.microsoft.com/intune-user-help/enroll-ios-device-intercede). Key requirements for this workflow include: 
-->
- Os usuários precisam de acesso a um computador ou KIOSK em que eles podem usar seu cartão inteligente para se autenticar no emissor. 

- Os dispositivos que serão registrados para uma credencial derivada devem instalar o aplicativo Portal da Empresa do Intune.

- O uso de uma câmera de dispositivo para digitalizar um código QR que vincula a solicitação de autenticação à solicitação de credencial derivada do dispositivo móvel.

### <a name="3-deploy-a-trusted-root-certificate-to-devices"></a>3) Implantar um certificado raiz confiável em dispositivos 

Um certificado raiz confiável é usado com credenciais derivadas para verificar se a cadeia de certificados de credencial derivada é válida e confiável. Mesmo quando não for diretamente referenciado por uma política, um certificado raiz confiável será necessário. Confira [Configurar um perfil de certificado para seus dispositivos no Microsoft Intune](certificates-configure.md).

### <a name="4-provide-end-user-instructions-for-how-to-get-the-derived-credential"></a>4) Fornecer instruções do usuário final sobre como obter a credencial derivada 

Crie e forneça diretrizes para seus usuários sobre como iniciar o processo de registro de credenciais derivadas e navegar você pelo fluxo de trabalho de registro de credenciais derivadas para seu emissor escolhido. 

Recomendamos que você forneça uma URL que hospedará suas diretrizes. Especifique esta URL quando você configurar o emissor de credenciais derivadas do seu locatário e se ela for disponibilizada de dentro do aplicativo Portal da Empresa. Se você não especificar sua própria URL, o Intune fornecerá um link para detalhes genéricos. Esses detalhes não podem abordar todos os cenários e podem não ser precisos para seu ambiente. 

### <a name="5-deploy-intune-policies-that-require-derived-credentials"></a>5) Implantar políticas do Intune que exigem credenciais derivadas 

Crie políticas ou edite políticas existentes para usar credenciais derivadas. As credenciais derivadas substituem outros métodos de autenticação para a autenticação de aplicativo, Wi-Fi, VPN, email e para assinatura e criptografia S/MIME. 

Evite exigir o uso de uma credencial derivada para acessar um processo que você usará como parte do processo de obter a credencial derivada, pois isso pode impedir usuários de concluir a solicitação. 

## <a name="set-up-a-derived-credential-issuer"></a>Configurar um emissor de credenciais derivadas

Antes de criar políticas que exijam o uso de uma credencial derivada, configure um emissor de credenciais no console do Intune. Um emissor de credenciais derivadas é uma configuração de todo o locatário. Os locatários dão suporte apenas a um único emissor por vez. 

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse **Configuração do Dispositivo** > **Credenciais Derivadas**.  

   ![Configurar credenciais derivadas no console](./media/derived-credentials/configure-provider.png)   

2. Especifique um **Nome de exibição** amigável para a política do emissor de credenciais derivadas.  Esse nome não é mostrado para seus usuários do dispositivo.

3. Para o **Emissor de credenciais derivadas**, selecione o emissor de credenciais derivadas que você escolheu para seu locatário:
   - DISA Purebred
   - Entrust Datacard
   - Intercede  

4. Especifique uma **URL de ajuda de credencial derivada** para fornecer um link para uma localização que inclui instruções personalizadas para ajudar os usuários a obterem credenciais derivadas para sua organização. As instruções devem ser específicas da sua organização e do fluxo de trabalho necessário para obter uma credencial do seu emissor escolhido. O link é exibido no aplicativo Portal da Empresa e deve ser acessível do dispositivo. 

   Se você não especificar sua própria URL, o Intune fornecerá um link para detalhes genéricos que não podem abranger todos os cenários. Essas diretrizes genéricas podem não ser precisas para seu ambiente.

5. Selecione uma ou mais opções para o **Tipo de notificação**. Os tipos de notificação são os métodos que você usa para informar os usuários sobre os seguintes cenários:

   - Registrar um dispositivo com um emissor para obter uma nova credencial derivada. 
   - Obter uma nova credencial derivada quando a credencial atual estiver perto da expiração. 
   - Usar uma credencial derivada com uma política para Wi-Fi, VPN, email ou autenticação de aplicativo e para assinatura e criptografia S/MIME. 

6. Quando estiver pronto, selecione **Salvar** para concluir a configuração do emissor de credenciais derivadas. 

Após salvar a configuração, você poderá fazer alterações em todos os campos, exceto pelo *Emissor de credenciais derivadas*.  Para alterar o emissor, confira [Alterar o emissor de credenciais derivadas](#change-the-derived-credential-issuer). 

## <a name="deploy-the-disa-purebred-app"></a>Implantar o aplicativo DISA Purebred

*Esta seção aplica-se apenas quando você usa o DISA Purebred*.

Para usar o **DISA Purebred** como seu emissor de credenciais derivadas para o Intune, você deve obter o aplicativo DISA Purebred e usar o Intune para implantar o aplicativo em dispositivos. Os usuários do dispositivo usam o aplicativo em seu dispositivo para solicitar a credencial derivada do DISA Purebred. 

Além de implantar o aplicativo com o Intune, configure um VPN por aplicativo do Intune para o aplicativo DISA Purebred. 

**Conclua as tarefas a seguir**: 
  
1. Baixar o [aplicativo DISA Purebred](https://cyber.mil/pki-pke/purebred/).
2. Implantar o aplicativo DISA Purebred no Intune.  Confira [Adicionar um aplicativo de linha de negócios iOS ao Microsoft Intune](../apps/lob-apps-ios.md).
3. [Criar um VPN por aplicativo](../configuration/vpn-settings-configure.md) para o aplicativo DISA Purebred.

## <a name="use-derived-credentials-for-authentication-and-smime-signing-and-encryption"></a>Usar credenciais derivadas para autenticação e assinatura e criptografia S/MIME

Você pode especificar uma **Credencial derivada** para os seguintes tipos de perfil e finalidades:  
- [Aplicativos](#use-derived-credentials-for-app-authentication)
- [Email](../configuration/email-settings-ios.md)
- [VPN](../configuration/vpn-settings-ios.md)
- [Criptografia e assinatura S/MIME](certificates-s-mime-encryption-sign.md)
- [Wi-Fi](../configuration/wi-fi-settings-ios.md)

  Para perfis Wi-Fi, o *Método de autenticação* está disponível apenas quando o **tipo de EAP** está definido como um dos seguintes valores: 
  - EAP – TLS
  - EAP-TTLS
  - PEAP

### <a name="use-derived-credentials-for-app-authentication"></a>Usar credenciais derivadas para autenticação do aplicativo

Use credenciais derivadas para autenticação baseada em certificado para sites e aplicativos. Para entregar uma credencial derivada para a autenticação do aplicativo, siga estas etapas no console do Intune:  

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse a **Configuração do Dispositivo** > **Perfis** e selecione **Criar Perfil**.

2. Insira um nome amigável para o perfil em **Nome**.

3. Selecione **Plataforma** para **iOS**.

4. Para **Tipo de perfil**, selecione **Credencial derivada**.

5. Selecione **OK** e clique em **Criar**.

6. Selecione **Atribuições** para escolher quais grupos devem receber a política.
 
Os usuários recebem a notificação pelo aplicativo ou por email dependendo das configurações especificadas quando você configurou o emissor de credenciais derivadas. A notificação solicita que o usuário inicie o Portal da Empresa para que as políticas de credenciais derivadas possam ser processadas.

## <a name="renew-a-derived-credential"></a>Renovar uma credencial derivada

As credenciais derivadas não podem ser estendidas ou renovadas. Em vez disso, os usuários devem usar o fluxo de trabalho de solicitação de credencial para solicitar uma nova credencial derivada para seu dispositivo.

Se você configurar um ou mais métodos para **Tipo de notificação**, o Intune notificará os usuários automaticamente quando a credencial derivada atual atingir 80% do seu tempo de vida útil. A notificação direciona os usuários a passar pelo processo de solicitação de credencial para obter uma nova credencial derivada. 

Depois que um dispositivo recebe uma nova credencial derivada, as políticas que usam credenciais derivadas são reimplantadas nesse dispositivo. 


## <a name="change-the-derived-credential-issuer"></a>Alterar o emissor de credenciais derivadas

No nível do locatário, você pode alterar seu emissor de credenciais, embora apenas um emissor tenha suporte para um locatário por vez. 

Depois de alterar o emissor, os usuários devem obter uma nova credencial derivada do novo emissor. Eles devem fazer isso antes que possam usar uma credencial derivada para autenticação.

### <a name="change-the-issuer-for-your-tenant"></a>Alterar o emissor para seu locatário

> [!IMPORTANT]  
> Se você excluir um emissor e reconfigurar imediatamente esse mesmo emissor, você ainda deverá atualizar perfis e dispositivos para usar credenciais derivadas desse emissor. As credenciais derivadas que foram obtidas antes de você excluir o emissor não são mais válidas. 

1. Entre no [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse **Configuração do Dispositivo** > **Credenciais Derivadas**.

2. Selecione **Excluir** para remover o emissor de credenciais derivadas atual.

3. Configure um novo emissor. 


### <a name="update-profiles-that-use-derived-credentials"></a>Atualizar perfis que usam credenciais derivadas

Depois de excluir um emissor e adicionar um novo, edite cada perfil que usa credenciais derivadas. Essa regra será aplicável mesmo se você restaurar o emissor anterior. Qualquer edição do perfil disparará uma atualização, incluindo uma edição simples no perfil *Descrição*.

### <a name="update-derived-credentials-on-devices"></a>Atualizar credenciais derivadas em dispositivos

Depois de excluir um emissor e adicionar um novo, os usuários do dispositivo deverão solicitar uma nova credencial derivada. Essa regra é aplicável mesmo quando você adiciona o mesmo emissor que removeu. O processo de solicitar a nova credencial derivada é o mesmo para registrar um novo dispositivo ou renovar uma credencial existente. 

## <a name="next-steps"></a>Próximas etapas

[Criar perfis de configuração de dispositivo](../configuration/device-profile-create.md)


 