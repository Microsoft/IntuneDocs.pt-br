---
title: "Implantar políticas e aplicativos"
description: "É possível habilitar as configurações de política e implantar aplicativos que serão aplicados assim que os dispositivos forem registrados no gerenciamento."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cf86d82fe636d2641f82ca951e508bea93abf683
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="create-policies-and-publish-apps"></a>Criar políticas e publicar aplicativos

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Este tópico informa os administradores do Intune como eles podem criar políticas e publicar aplicativos que eles podem implantar em dispositivos gerenciados.

Antes de começar a registrar aplicativos no Intune, você poderá habilitar as configurações de política e os aplicativos que serão implantados assim que esses dispositivos entrarem em gerenciamento. As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos. Você pode configurar a política, adicionar aplicativos e implantar esses aplicativos para que os dispositivos recebam as configurações e aplicativos assim que se registrarem no Intune.

As políticas e os aplicativos são específicos da plataforma.

## <a name="manage-device-settings"></a>Gerenciar configurações do dispositivo

 As configurações de política de dispositivo são configuradas e gerenciadas por plataforma. Os links a seguir fornecem listas de configurações disponíveis para suas respectivas plataformas:

- [iOS](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [Android e Samsung KNOX Standard](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [Android for Work](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [Windows 10 (computador e móvel)](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [Windows 8.1](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [Windows Phone 8.1](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [Equipe do Windows](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [Computadores Windows que executam o cliente de software do Intune](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

Você pode aprender mais sobre como [Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).

## <a name="add-and-deploy-apps"></a>Adicione e implante aplicativos

Você pode adicionar aplicativos ao Intune e, em seguida, implantá-los em dispositivos gerenciados de duas maneiras:
- **Instalação necessária** – Os aplicativos instalam automaticamente o aplicativo para dispositivos gerenciados
- **Instalação disponível** – Os aplicativos aparecem no Portal da Empresa do Intune para que os usuários possam optar por instalá-los em seus dispositivos

### <a name="add-apps"></a>Adicionar aplicativos

Primeiro, você deve disponibilizar aplicativos do Intune por um dos seguintes métodos:
- [Adicionar aplicativos para dispositivos registrados](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [Adicionar aplicativos para PCs do cliente de software do Intune](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a>Implantar aplicativos

Agora que o aplicativo está disponível no Intune, você pode implantá-lo em dispositivos gerenciados:
- [Implantar aplicativos em dispositivos](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- Implantar aplicativos comprados por volume:
    - [iOS – Programa de compra por volume](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [Windows Store para Empresas](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [Android for Work](/intune-classic/deploy-use/android-for-work-apps)

    Depois que configurar os aplicativos para implantação, você pode [configurar aplicativos](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).

>[!div class="step-by-step"]

>[&larr; **Organizar usuários e dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personalizar o Portal da Empresa** &rarr;](/intune/company-portal-customize)  
