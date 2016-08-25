---
title: Restringir o acesso ao SharePoint Online | Microsoft Intune
description: Proteja e controle o acesso aos dados da empresa no SharePoint Online com acesso condicional.
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: be1ebcdf2514e45d383dd49890e0e21acf6ede44
ms.openlocfilehash: d233ea540d7db00d9df5b5ed1f5db2cff6cd7b9e


---

# Restringir o acesso ao SharePoint Online com o Microsoft Intune
Use o acesso condicional [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] para controlar o acesso a arquivos localizados no SharePoint Online.
O acesso condicional tem dois componentes:
- A política de conformidade do dispositivo, com que o dispositivo deve estar em conformidade para ser considerado compatível.
- A política de acesso condicional, na qual você especifica as condições que o dispositivo deve atender para acessar o serviço.
Para saber mais sobre como o acesso condicional funciona, leia o tópico [Restrict access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (Restringir acesso a email, O365 e outros serviços).

As políticas de acesso condicional e conformidade são implantadas para o usuário. Qualquer dispositivo que o usuário utiliza para acessar os serviços é verificado quanto à conformidade com as políticas.

Quando um usuário tenta se conectar a um arquivo usando um aplicativo com suporte assim como o OneDrive em seu dispositivo, ocorre a seguinte avaliação:

![Diagrama para mostrar os pontos de decisão usados para determinar se um dispositivo tem acesso permitido ou bloqueado acesso ao SharePoint ](../media/ConditionalAccess8-6.png)

>[!IMPORTANT]
>O acesso condicional para computadores e dispositivos Windows 10 Mobile com aplicativos usando autenticação moderna atualmente não está disponível para todos os clientes do Intune. Se você já estiver usando esses recursos, você não precisará realizar nenhuma ação. Você pode continuar a usá-los.

>Se não tiver criado políticas de acesso condicional para computadores ou Windows 10 Mobile para aplicativos usando a autenticação moderna e quiser fazer isso, você precisará enviar uma solicitação.  Você pode encontrar mais informações sobre problemas conhecidos e sobre como obter acesso a esse recurso no [site do Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

**Antes** de configurar uma política de acesso condicional para o SharePoint Online, você precisa:
- Ter uma **assinatura do SharePoint Online**, e os usuários devem ser licenciados para o SharePoint Online.
- Ter uma assinatura do **Enterprise Mobility Suite** ou do **Azure Active Directory Premium**.

  Para conectar-se aos arquivos necessários, o dispositivo precisa:
-   Estar **registrado** no [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ou em um computador ingressado no domínio.

-   **Registre o dispositivo** no Azure Active Directory (isso ocorre automaticamente quando o dispositivo for registrado com o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]).


-   Ser compatível com qualquer política de conformidade do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] implantada

O estado do dispositivo é armazenado no Active Directory do Azure que concede ou bloqueia o acesso a arquivos, com base nas condições que você especifica.

Se uma condição não for atendida, o usuário receberá uma das seguintes mensagens de erro ao fazer logon:

-   Se o dispositivo não estiver registrado no [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa e registrá-lo.

-   Se o dispositivo não for compatível, será exibida uma mensagem que direciona o usuário ao site do Portal da Empresa [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], no qual ele pode encontrar informações sobre o problema e como corrigi-lo.

**O acesso condicional é aplicado a todos os sites do SharePoint e o compartilhamento externo é bloqueado**

>[!NOTE]
>Se você habilitar o acesso condicional para o SharePoint Online, recomendamos que desabilite o domínio na lista, conforme descrito no tópico [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/en-us/library/dn917451.aspx).  
## Suporte para dispositivos móveis
- iOS 7.1 e posterior
- Android 4.0 e posterior, Samsung Knox Standard 4.0 ou posterior
- Windows Phone 8.1 e posterior

Você pode restringir o acesso ao SharePoint Online quando acessado por um navegador em dispositivos **iOS** e **Android**.  O acesso será permitido somente de navegadores com suporte em dispositivos compatíveis:
* Safari (iOS)
* Chrome (Android)
* Navegador gerenciado (iOS e Android)

**Navegadores sem suporte serão bloqueados**.

## Suporte para computadores
- Windows 8.1 e posterior (quando registrado no Intune)
- Windows 7.0 ou Windows 8.1 (quando ingressado no domínio)

  - Computadores ingressados no domínio devem ser configurados [registrarem-se automaticamente](https://azure.microsoft.com/en-us/documentation/articles/active-directory-conditional-access-automatic-device-registration/) no Azure Active Directory.
O AAD DRS será ativado automaticamente para clientes do Intune e do Office 365. Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local.

  - Se a política estiver definida para exigir o ingresso no domínio e o computador não tiver ingressado no domínio, uma mensagem será exibida para que o usuário entre em contato com o administrador de TI.

  - Se a política estiver definida para exigir ingresso no domínio ou compatibilidade e o computador não atender a nenhum dos dois requisitos, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa e realizar o registro.
-    [A autenticação moderna do Office 365 deve estar habilitada](https://support.office.com/en-US/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) e ter todas as atualizações mais recentes do Office.

    A autenticação moderna leva as credenciais baseadas na ADAL (Active Directory Authentication Library) para os clientes Windows com Office 2013 e permite mais segurança como a **autenticação multifator** e a **autenticação baseada em certificado**.


## Configurar o acesso condicional para o SharePoint Online

### Etapa 1: Configurar grupos de segurança do Active Directory
Antes de começar, configure os grupos de segurança do Active Directory do Azure para a política de acesso condicional. Você pode configurar esses grupos no **Centro de administração do Office 365**ou no **Portal de conta do Intune**. Esses grupos serão usados para afetar ou isentar os usuários da política. Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.

Você pode especificar dois tipos de grupo em uma política do SharePoint Online:

-   **Grupos de destino** – contém grupos de usuários aos quais a política será aplicada.

-   **Grupos isentos** – contém grupos de usuários isentos da política.

Se um usuário estiver nos dois grupos, ele ficará isento da política.

### Etapa 2: Configurar e implantar uma política de conformidade
Se ainda não tiver feito isso, crie e implante uma política de conformidade para todos os usuários aos quais a política do SharePoint Online se destinará.

> [!NOTE]
> Enquanto as políticas de conformidade são implantadas em grupos [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], as políticas de acesso condicional são destinadas a grupos de segurança do Azure Active Directory.

Para obter detalhes sobre como configurar a política de conformidade, consulte [create a compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md) (criar uma política de conformidade).

> [!IMPORTANT]
> Se você não tiver implantado uma política de conformidade, os dispositivos serão tratados como compatíveis.

Quando estiver pronto, continue na **Etapa 3**.

### Etapa 3: Configurar a política do SharePoint Online
Em seguida, configure a política para exigir que somente dispositivos gerenciados e compatíveis possam acessar o SharePoint Online. Essa política será armazenada no Active Directory do Azure.

#### <a name="bkmk_spopolicy"></a>

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Acesso Condicional** > **Política do SharePoint Online**.
![Instantâneo da página de Política do SharePoint Online](../media/mdm-ca-spo-policy-configuration.png)

2.  Selecione **Habilitar política de acesso condicional para o SharePoint Online**.

3.  Em **Acesso ao aplicativo**, você pode optar por aplicar a política de acesso condicional a:

    -   **Todas as plataformas**

        Isso requer que qualquer dispositivo usado para acessar o **SharePoint Online** seja registrado no Intune e esteja compatível com as políticas.  Qualquer aplicativo cliente usando a **autenticação moderna** está sujeito à política de acesso condicional. Se a plataforma não tiver suporte do Intune, o acesso ao **SharePoint Online** será bloqueado.

        Selecionar a opção **Todas as plataformas** significa que o Azure Active Directory aplicará essa política a todas as solicitações de autenticação, independentemente da plataforma relatada pelo aplicativo cliente.  Todas as plataformas precisarão ser registradas e tornam-se compatíveis, exceto para:
        *   Dispositivos Windows precisarão ser registrados e compatíveis, ingressados no domínio com o Active Directory local ou ambos
        * Plataformas sem suporte, como Mac.  No entanto, os aplicativos que usam autenticação moderna provenientes dessas plataformas ainda estarão bloqueados.
        >[!TIP]
        >Você não encontrará essa opção se você não estiver usando o acesso condicional para computadores.  Em vez disso, use **Plataformas específicas**. O acesso condicional para computadores não está disponível no momento para todos os clientes do Intune.   Você pode encontrar mais informações sobre problemas conhecidos e como obter acesso a esse recurso no [site do Microsoft Connect](http://go.microsoft.com/fwlink/?LinkId=761472).

    -   **Plataformas específicas**

         A política de acesso condicional se aplicará a qualquer aplicativo cliente que usar a autenticação moderna nas plataformas que você especificar.

     Para computadores Windows, o computador deve estar ingressado no domínio ou ser compatível e estar registrado em [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Você pode definir os seguintes requisitos:

     -   **Os dispositivos devem ter domínio associado ou compatível.** Escolha essa opção se quiser que os computadores estejam ingressados no domínio ou sejam compatíveis com as políticas definidas em [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Se o computador não atender a esses requisitos, será solicitado que o usuário registre o dispositivo com [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

     -   **Os dispositivos devem ter domínio associado.** Escolha essa opção para exigir que os computadores estejam ingressados no domínio para acessar o Exchange Online. Se o computador não estiver ingressado no domínio, o acesso ao email será bloqueado e será solicitado que o usuário entre em contato com o administrador de TI.

     -   **Os dispositivos devem ser compatíveis.** Escolha essa opção para exigir que os computadores sejam compatíveis e estejam registrados em [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Se o computador não estiver registrado, será exibida uma mensagem com instruções sobre como registrá-lo.

4.   Em **Acesso do navegador** ao SharePoint Online e OneDrive for Business, você pode optar por permitir o acesso ao Exchange Online somente por meio de navegadores com suporte: Safari (iOS) e Chrome (Android). O acesso de outros navegadores será bloqueado.  As mesmas restrições de plataforma que você selecionou para acesso de aplicativo para OneDrive também se aplicam aqui.

  Em dispositivos **Android**, os usuários devem habilitar o acesso do navegador.  Para isso, os usuários finais devem habilitar a opção "Habilitar Acesso do Navegador" no dispositivo registrado da seguinte maneira:
  1.    Inicie o **aplicativo do Portal da Empresa**.
  2.    Vá para a página **Configurações** por meio dos três pontos (...) ou do botão de menu do hardware.
  3.    Pressione o botão **Habilitar Acesso do Navegador**.
  4.  No navegador Chrome, saia do Office 365 e reinicie o Chrome.

  Em plataformas **iOS e Android**, para identificar o dispositivo usado para acessar o serviço, o Azure Active Directory emitirá um certificado de protocolo TLS para o dispositivo.  O dispositivo exibe o certificado com um prompt ao usuário final para selecionar o certificado conforme visto nas capturas de tela abaixo. O usuário final deve selecionar este certificado antes de continuar usando o navegador.

  **iOS**

  ![captura de tela da solicitação de certificado em um ipad](../media/mdm-browser-ca-ios-cert-prompt.png)

  **Android**

  ![captura de tela da solicitação de certificado em um dispositivo Android](../media/mdm-browser-ca-android-cert-prompt.png)
5.  Em **Grupos de Destino**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory aos quais a política será aplicada. Você pode escolher aplicar isso a todos os usuários ou apenas a um grupos seleto de usuários.

6.  Opcionalmente, em **Grupos Isentos**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory que são isentos dessa política.

6.  Quando terminar, selecione **Salvar**.

Você não precisa implantar a política de acesso condicional, ele entra em vigor imediatamente.

### Etapa 4: monitorar políticas de acesso condicional e conformidade
No espaço de trabalho **Grupos**, você pode exibir o status de seus dispositivos.

Selecione qualquer grupo de dispositivos móveis e então, na guia **Dispositivos** , selecione um dos seguintes **Filtros**:

-   **Dispositivos que não estão registrados no AAD** – esses dispositivos estão bloqueados do SharePoint Online.

-   **Dispositivos que não são compatíveis** – esses dispositivos estão bloqueados do SharePoint Online.

-   **Dispositivos que estão registrados no AAD e são compatíveis** – esses dispositivos podem acessar o SharePoint Online.

### Consulte também
[Restringir o acesso a email e serviços do O365 com o Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO5-->


