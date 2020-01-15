---
title: Adicionar aplicativos de Defesa contra Ameaças Móveis a dispositivos não registrados
titleSuffix: Microsoft Intune
description: Adicionar aplicativos de Defesa contra Ameaças Móveis a dispositivos não registrados por usuários.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: e1cf0a3d8b30955be8413b376acd223a924be843
ms.sourcegitcommit: 06dce5c8111592ad774247e86e539dd3128117e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/30/2019
ms.locfileid: "75545915"
---
# <a name="add-mobile-threat-defense-apps-to-unenrolled-devices"></a>Adicionar aplicativos de Defesa contra Ameaças Móveis a dispositivos não registrados

Por padrão, ao usar políticas de proteção de aplicativo do Intune com a Defesa contra Ameaças Móveis, o Intune faz o trabalho de orientar o usuário final em seu dispositivo a instalar e entrar em todos os aplicativos necessários para habilitar as conexões com os serviços relevantes.

Os usuários finais precisam do Microsoft Authenticator (iOS) para registrar seu dispositivo e da Defesa contra Ameaças Móveis (Android e iOS) para receber notificações quando uma ameaça é identificada em seus dispositivos móveis e para receber orientações para corrigir as ameaças.

Opcionalmente, você também pode usar o Intune para adicionar e implantar os aplicativos do Microsoft Authenticator e da MTD (Defesa contra Ameaças Móveis).

> [!NOTE] 
> Este artigo aplica-se a todos os parceiros de Defesa contra Ameaças Móveis que dão suporte a políticas de proteção de aplicativo: Better Mobile (Android), Zimperium (Android, iOS), Lookout for Work (Android/iOS).
> 
> Para dispositivos não registrados, você **não precisa de uma política de configuração de aplicativos iOS** que configura o aplicativo de Defesa contra Ameaças Móveis para iOS que você usa com o Intune. Essa é uma diferença importante em comparação com dispositivos registrados no Intune. 

## <a name="configure-microsoft-authenticator-for-ios-via-intune-optional"></a>Configurar o Microsoft Authenticator para iOS usando o Intune (opcional)
Ao usar as políticas de proteção de aplicativo do Intune com a Defesa contra Ameaças Móveis, o Intune orientará o usuário final a instalar, entrar e registrar seu dispositivo no Microsoft Authenticator (iOS).

No entanto, se desejar disponibilizar o aplicativo para os usuários finais por meio do Portal da Empresa do Intune, confira as instruções para [adicionar aplicativos da iOS store ao Microsoft Intune](../apps/store-apps-ios.md). Use esta [URL da App Store do Microsoft Authenticator – iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) ao concluir a seção **Configurar informações de aplicativo**. Não se esqueça de [atribuir o aplicativo a grupos com o Intune](../apps/apps-deploy.md) como a etapa final.

> [!NOTE] 
> Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD. O Portal da Empresa do Intune funciona como o agente em dispositivos Android, de modo que os usuários possam ter suas identidades verificadas pelo Azure AD.

## <a name="making-mobile-threat-defense-apps-available-via-intune-optional"></a>Disponibilizar aplicativos de Defesa contra Ameaças Móveis usando o Intune (opcional)
Ao usar as políticas de proteção de aplicativo do Intune com a Defesa contra Ameaças Móveis, o Intune orientará o usuário final a instalar e entrar no aplicativo cliente necessário de Defesa contra Ameaças Móveis. 

No entanto, se quiser disponibilizar o aplicativo para os usuários finais por meio do Portal da Empresa do Intune, siga as etapas abaixo no [portal do Azure](https://portal.azure.com/). Verifique se que você está familiarizado com o processo de:

- [Adicionar um aplicativo no Intune](../apps/apps-add.md).
- [Atribuindo um aplicativo com o Intune](../apps/apps-deploy.md).

### <a name="making-lookout-for-work-available-to-end-users"></a>Disponibilizar o Lookout for Work para os usuários finais
- **Android**  
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](../apps/store-apps-android.md). Use esta [URL da Play Store do Lookout for Work iOS](https://play.google.com/store/apps/details?id=com.lookout.enterprise) ao concluir a seção **Configurar informações de aplicativo**.

- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](../apps/store-apps-ios.md). Use esta [URL da App Store do Lookout for Work – iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) ao concluir a seção **Configurar informações de aplicativo**.

<!-- ### Making Symantec Endpoint Protection Mobile available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). When completing the **Configure app information** section, use this [SEP Mobile app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure). For **Minimum operating system**, select **Android 4.0 (Ice Cream Sandwich)**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [SEP Mobile - App Store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) when completing the **Configure app information** section.

### Making Check Point SandBlast Mobile available to end users
- **Android**  
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Check Point SandBlast Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) when completing the **Configure app information** section. 

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Check Point SandBlast Mobile - App Store URL](https://apps.apple.com/us/app/sandblast-mobile-protect/id1006390797) when completing the **Configure app information** section. -->

### <a name="making-zimperium-available-to-end-users"></a>Disponibilizar o Zimperium para os usuários finais
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](../apps/store-apps-android.md). Use esta [URL da Play Store do Zimperium](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) ao concluir a seção **Configurar informações de aplicativos**.
- **iOS**
  - Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](../apps/store-apps-ios.md). Use esta [URL da App Store do Zimperium](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) ao concluir a seção **Configurar informações de aplicativo**.
 
<!-- ### Making Pradeo available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Pradeo - Play Store URL](https://play.google.com/store/apps/details?id=net.pradeo.service&hl=en_US) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Pradeo - App Store URL](https://itunes.apple.com/us/app/pradeo-agent/id547979360?mt=8) when completing the **Configure app information** section. -->

### <a name="making-better-mobile-available-to-end-users"></a>Disponibilizar o Better Mobile para os usuários finais 
- **Android**
  - Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](../apps/store-apps-android.md). Use esta [URL da Play Store do Active Shield](https://play.google.com/store/apps/details?id=com.better.active.shield.enterprise) ao concluir a seção **Configurar informações de aplicativo**.
<!-- - **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/activeshield/id980234260?mt=8&uo=4) when completing the **Configure app information** section. -->

<!-- ### Making Sophos available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Sophos - Play Store URL](https://play.google.com/store/apps/details?id=com.sophos.smsec) when completing the **Configure app information** section.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [ActiveShield - App Store URL](https://itunes.apple.com/us/app/sophos-mobile-security/id1086924662?mt=8) when completing the **Configure app information** section.

### Making Wandera available to end users
- **Android**
  - See the instructions for [adding Android store apps to Microsoft Intune](../apps/store-apps-android.md). Use this [Wandera Mobile - Play Store URL](https://play.google.com/store/apps/details?id=com.wandera.android) when completing the **Configure app information** section. For **Minimum operating system**, select **Android 5.0**.

- **iOS**
  - See the instructions for [adding iOS store apps to Microsoft Intune](../apps/store-apps-ios.md). Use this [Wandera Mobile - - App Store URL](https://itunes.apple.com/app/wandera/id605469330) when completing the **Configure app information** section. -->

## <a name="next-steps"></a>Próximas etapas  

- [Habilitar o conector de Defesa contra Ameaças Móveis no Intune para dispositivos não registrados](~/protect/mtd-enable-unenrolled-devices.md)

