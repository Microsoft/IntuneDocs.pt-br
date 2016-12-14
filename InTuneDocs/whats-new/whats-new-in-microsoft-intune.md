---
title: Novidades | Microsoft Intune
description: "Descubra as novidades deste mês e os lançamentos anteriores do Microsoft Intune"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/30/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fab51ee0-638d-4dd4-8d8f-1f263bc11e5c
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 8ef3b7e4eec5a520c93fb3f70c8e5b6ee7d2c3aa
ms.openlocfilehash: e0b0c7eb3ddc07f05fc0c2e4caa6726ed052c9d8


---
# <a name="whats-new-in-microsoft-intune---november-2016"></a>Novidades do Microsoft Intune – novembro de 2016
Conheça as novidades nesta versão do Microsoft Intune. Você também pode descobrir sobre alterações futuras que você deve estar planejando, bem como informações sobre versões anteriores.

> [!Note]
> Todos esses recursos eventualmente terão suporte para implantações híbridas de clientes (Configuration Manager com o Intune). Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](https://docs.microsoft.com/en-us/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).

## <a name="new-capabilities"></a>Novos recursos

<!--### View App States for All Platforms in Real Time
App installation status is now shown in real-time in the console. When you previously deployed an app, you had to wait for a targeted device to report back before the app install status was displayed in the Intune console.

### Streamline iOS App Management for your End Users
Intune can now automatically take over management of the previously installed app and no end user action is required.

Previously, if the end user of an enrolled iOS device installed an app from the App Store before you deployed that same app with a deployment action of __Available__, then the end user had to:

1. Open the __Company Portal__.
2. Select the app.
3. Tap __Install__ to enable Intune to take over management of the app.-->

__Novo Portal da Empresa do Microsoft Intune disponível para dispositivos Windows 10__ A Microsoft lançou um novo [aplicativo de Portal da Empresa do Microsoft Intune para dispositivos Windows 10](https://www.microsoft.com/store/apps/9wzdncrfj3pz). Esse aplicativo, que aproveita o novo formato do Windows 10 Universal, fornecerá ao usuário uma experiência de usuário atualizada dentro do aplicativo e experiências idênticas em todos os dispositivos Windows 10, sejam eles PCs ou dispositivos móveis, habilitando ainda todas as mesmas funcionalidades que eles estão usando atualmente.

O novo aplicativo também permitirá que os usuários aproveitem os recursos de plataforma adicionais como SSO (logon único) e autenticação baseada em certificado em dispositivos Windows 10. O aplicativo ficará disponível como uma atualização para as instalações existentes do Portal da Empresa do Windows 8.1 e do Portal da Empresa do Windows Phone 8.1 da Windows Store. Para obter mais detalhes, acesse [aka.ms/intunecp_universalapp](http://aka.ms/intunecp_universalapp).

<!--### Support for Windows Store for Business Apps Being Deployed as Available
You can now deploy apps you synchronized from the Windows Store for Business (WSfB) with a deployment action of __Available__ or __Required__. After syncing WSfB apps into Intune, administrators will be able to target those apps as available installs to groups of users. End users will see the deployed WSfB apps as available for install in the Universal Company Portal, where they can choose whether they would like to acquire the apps.

### Conditional Access for MAM with SharePoint Online

You can block apps that are not supported by Intune mobile app management (MAM) policies from accessing SharePoint online.  You can get started in Intune mobile app management via the Azure portal. Look for the  Conditional Access section in the “Settings” blade which now includes the option for SharePoint online.-->

> [!IMPORTANT]

> __Uma atualização no Intune e no Android for Work__

> Embora possa implantar aplicativos do Android for Work com uma ação __Necessária__, você só pode implantar aplicativos como __Disponível__ se os grupos do Intune tiverem sido migrados para a nova experiência de grupos do Azure AD.

### <a name="intune-app-sdk-for-cordova-plugin-now-supports-mam-without-enrollment"></a>Agora, o Plug-in Cordova do SDK de Aplicativo do Intune dá suporte ao MAM sem registro
Os desenvolvedores de aplicativos podem usar o Plug-in Cordova do SDK de Aplicativo do Intune a fim de habilitar a funcionalidade de MAM sem registro do dispositivo em seus aplicativos baseados no Cordova para Android e iOS. Encontre o Plug-in Cordova do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam).

### <a name="intune-app-sdk-xamarin-component-now-supports-mam-without-enrollment"></a>Agora, o Componente Xamarin do SDK de Aplicativo do Intune dá suporte a MAM sem registro
Os desenvolvedores de aplicativos podem usar o Componente Xamarin do SDK de Aplicativo do Intune a fim de habilitar a funcionalidade do MAM sem registro do dispositivo em seus aplicativos com base no Xamarin para Android e iOS. Encontre o Componente Xamarin do SDK de Aplicativo do Intune [aqui](https://github.com/msintuneappsdk/intune-app-sdk-xamarin).

## <a name="notices"></a>Avisos

### <a name="symantec-signing-certificate-no-longer-requires-signed-windows-phone-8-company-portal-for-upload"></a>O certificado de assinatura da Symantec não exige mais um Portal da Empresa do Windows Phone 8 assinado para upload
O carregamento do certificado de assinatura da Symantec não exigirá mais um aplicativo de Portal da Empresa do Windows Phone 8 assinado. O certificado pode ser carregado de forma independente.

## <a name="deprecations"></a>Recursos preteridos

### <a name="support-for-the-windows-phone-8-company-portal"></a>Suporte para o Portal da Empresa do Windows Phone 8
O suporte para o Portal da Empresa do Windows Phone 8 será preterido. O suporte para as plataformas Windows Phone 8 e WinRT foi preterido em outubro de 2016. O suporte para o Portal da Empresa do Windows 8 também foi preterido em outubro de 2016.


### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](http://www.microsoft.com/en-us/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Versões anteriores do Intune](whats-new-archive.md)



<!--HONumber=Dec16_HO1-->


