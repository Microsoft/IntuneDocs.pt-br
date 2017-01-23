---
title: "Implantar políticas e aplicativos | Microsoft Docs"
description: "É possível habilitar as configurações de política e implantar aplicativos que serão aplicados assim que os dispositivos forem registrados no gerenciamento."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 9f75020a6d8a3e2aeb278fb99f54516253abf3dd


---

# <a name="create-policies-and-publish-apps"></a>Criar políticas e publicar aplicativos

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Antes de começar a registrar aplicativos no Intune, você poderá habilitar as configurações de política e os aplicativos que serão implantados assim que esses dispositivos entrarem em gerenciamento. As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos. Você pode configurar a política, adicionar aplicativos e implantar esses aplicativos para que os dispositivos recebam as configurações e aplicativos assim que se registrarem no Intune.

As políticas e os aplicativos são específicos da plataforma.

## <a name="manage-device-settings"></a>Gerenciar configurações do dispositivo

 As configurações de política de dispositivo são configuradas e gerenciadas por plataforma. É possível configurar a política para as seguintes plataformas:

- [iOS](https://docs.microsoft.com/intune/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android e Samsung KNOX Standard](https://docs.microsoft.com/intune/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](https://docs.microsoft.com/intune/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (PCs e Mobile)](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](https://docs.microsoft.com/intune/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](https://docs.microsoft.com/intune/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Equipe do Windows](https://docs.microsoft.com/intune/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Computadores Windows que executam o cliente de software do Intune](https://docs.microsoft.com/intune/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Você pode aprender mais sobre como [Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Adicione e implante aplicativos

Você pode adicionar aplicativos ao Intune e, em seguida, implantá-los em dispositivos gerenciados de duas maneiras:
- **Instalação necessária** – Os aplicativos instalam automaticamente o aplicativo para dispositivos gerenciados
- **Instalação disponível** – Os aplicativos aparecem no Portal da Empresa do Intune para que os usuários possam optar por instalá-los em seus dispositivos

### <a name="add-apps"></a>Adicionar aplicativos

Primeiro, você deve disponibilizar aplicativos do Intune por um dos seguintes métodos:
- [Adicionar aplicativos para dispositivos registrados](https://docs.microsoft.com/intune/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Adicionar aplicativos para PCs do cliente de software do Intune](https://docs.microsoft.com/intune/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Implantar aplicativos

Agora que o aplicativo está disponível no Intune, você pode implantá-lo em dispositivos gerenciados:
- [Implantar aplicativos em dispositivos](https://docs.microsoft.com/intune/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Implantar aplicativos comprados por volume:
    - [iOS – Programa de compra por volume](https://docs.microsoft.com/intune/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Windows Store para Empresas](https://docs.microsoft.com/intune/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](https://docs.microsoft.com/en-us/Intune/deploy-use/android-for-work-apps)

    Depois que configurar os aplicativos para implantação, você pode [configurar aplicativos](https://docs.microsoft.com/intune/deploy-use/update-apps-using-microsoft-intune) e [monitorar aplicativos](https://docs.microsoft.com/intune/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Organizar usuários e dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personalizar o Portal da Empresa** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-7.md)  



<!--HONumber=Dec16_HO2-->


