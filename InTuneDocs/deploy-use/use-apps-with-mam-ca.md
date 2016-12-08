---
title: Usando aplicativos com AC de MAM | Microsoft Intune
description: "Entenda como o AC para MAM pode ajudar a controlar os aplicativos que têm acesso aos serviços do O365."
keywords: 
author: karthikaraman
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: df77e1473532399056c3e0c1b4c4db3c7b6ba995
ms.openlocfilehash: 0fc24f1c93cfcdb86c2a66c9a027b4ed9c516dab


---
# <a name="what-to-expect-when-using-an-app-with-mam-ca"></a>O que esperar ao usar um aplicativo com AC do MAM
O AC de MAM verifica a identidade do aplicativo aprovado por meio de um aplicativo agente, que deve estar presente no dispositivo:
*  No **iOS**, o **aplicativo Microsoft Authenticator** é o aplicativo agente.
* No **Android**, o **aplicativo do Portal da Empresa do Intune** é o aplicativo agente. 

Quando os usuários finais entram pela primeira vez em um aplicativo em que há suporte para AC de MAM, como o OneDrive ou o Outlook, eles são solicitados a instalar o aplicativo agente e a registrar o dispositivo com o Azure AD. O registro de dispositivos no Azure AD (anteriormente conhecido como Ingresso no Local de Trabalho) criará um registro de dispositivo e um certificado no qual os tokens serão emitidos.  Esse processo **não** é igual ao **registro do MDM**. Não há perfis de gerenciamento ou políticas aplicadas e não há nenhum inventário de aplicativos do dispositivo.  O processo de instalação do aplicativo agente e de registro do dispositivo só ocorrerá quando o aplicativo gerenciado for usado pela primeira vez.

A seguir, temos uma lista de propriedades que são derivadas diretamente do dispositivo:

* alternativeSecurityIds (hash de chave pública e impressão digital do certificado do Azure Active Directory)
* deviceOSType
* deviceOSVersion
* displayName

## <a name="to-remove-a-device-from-azure-ad-registration"></a>Para remover um dispositivo do registro no Azure AD.
É possível remover o registro do dispositivo usando o console de administração do Azure AD, o que normalmente é feito pelo administrador de TI.  Isso também pode ser feito pelo usuário final no próprio dispositivo.

* **Console de administração do Azure AD**: no console de administração do Azure AD**, exclua o dispositivo que deseja remover.
* **Dispositivo iOS**: abra o aplicativo Microsoft Authenticator, passe o dedo para a esquerda na conta e escolha Cancelar registro.  
* **Dispositivo Android**: desinstale o aplicativo do Portal da Empresa ou remova a conta das **Configurações do sistema**.



## <a name="mam-ca-with-conditional-access-based-on-device-compliance"></a>AC do MAM com acesso condicional baseado na conformidade do dispositivo  

Você pode configurar o [Acesso condicional baseado na conformidade do dispositivo](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (**AC do Dispositivo**) no [console do administrador do Intune](https://manage.microsoft.com) ou no [console de gerenciamento do Azure AD Premium] (https://manage.windowsazure.com). O AC do dispositivo exige que os usuários se conectem ao Exchange Online somente por meio de dispositivos gerenciados pelo Intune que estejam em conformidade com a política de conformidade do dispositivo do Intune ou computadores de domínio associado.  Se um usuário pertencer a um ou mais grupos de segurança destinados a políticas de AC de MAM e de AC do dispositivo, o usuário deverá atender a um dos dois requisitos:
* O aplicativo usado para acessar o serviço é móvel com suporte do AC do MAM e o dispositivo no qual aplicativo está sendo executado tem um **Autenticador iOS (para dispositivos iOS)** ou o **aplicativo do Portal da Empresa (para dispositivos Android)** instalados.
* O dispositivo utilizado para acessar o serviço é **compatível e gerenciado pelo Intune** com a política de conformidade do dispositivo do Intune ou é um **computador de domínio associado**.  Aqui estão alguns exemplos para ajudar a ilustrar essa situação:
  * Se um usuário tentar se conectar por meio do **aplicativo de email nativo do iOS**, ele deverá usar um **dispositivo gerenciado e compatível**, pois não há suporte do AC do MAM para o aplicativo de email nativo.
  * Se um usuário tentar se conectar por meio de um **computador doméstico Windows**, a **política de AC do dispositivo** será aplicada, exigindo que o usuário use um computador de domínio associado.




## <a name="next-steps"></a>Próximas etapas
[Criar uma política do Exchange Online para aplicativos MAM](mam-ca-for-exchange-online.md)

[Bloquear aplicativos que não têm autenticação moderna](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a>Consulte também

[Proteger dados de aplicativos com políticas de MAM](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Nov16_HO2-->

