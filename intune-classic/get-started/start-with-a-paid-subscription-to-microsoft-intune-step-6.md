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
# <span data-ttu-id="74460-103">Criar políticas e publicar aplicativos</span><span class="sxs-lookup"><span data-stu-id="74460-103">Create policies and publish apps</span></span>
<a id="create-policies-and-publish-apps" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="74460-104">Este tópico informa os administradores do Intune como eles podem criar políticas e publicar aplicativos que eles podem implantar em dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="74460-104">This topic tells Intune administrators how they can create policies and publish apps that they can then deploy to managed devices.</span></span>

<span data-ttu-id="74460-105">Antes de começar a registrar aplicativos no Intune, você poderá habilitar as configurações de política e os aplicativos que serão implantados assim que esses dispositivos entrarem em gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="74460-105">Before you start enrolling apps into Intune, you can enable policy settings and apps that will be deployed as soon as those devices come into management.</span></span> <span data-ttu-id="74460-106">As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="74460-106">Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications.</span></span> <span data-ttu-id="74460-107">Você pode configurar a política, adicionar aplicativos e implantar esses aplicativos para que os dispositivos recebam as configurações e aplicativos assim que se registrarem no Intune.</span><span class="sxs-lookup"><span data-stu-id="74460-107">You can configure policy, add apps, and deploy those apps so that devices receive settings and apps as soon as they enroll in Intune.</span></span>

<span data-ttu-id="74460-108">As políticas e os aplicativos são específicos da plataforma.</span><span class="sxs-lookup"><span data-stu-id="74460-108">Policies and apps are platform-specific.</span></span>

## <span data-ttu-id="74460-109">Gerenciar configurações do dispositivo</span><span class="sxs-lookup"><span data-stu-id="74460-109">Manage device settings</span></span>
<a id="manage-device-settings" class="xliff"></a>

 <span data-ttu-id="74460-110">As configurações de política de dispositivo são configuradas e gerenciadas por plataforma.</span><span class="sxs-lookup"><span data-stu-id="74460-110">Device policy settings are configured and managed on a per-platform basis.</span></span> <span data-ttu-id="74460-111">Os links a seguir fornecem listas de configurações disponíveis para suas respectivas plataformas:</span><span class="sxs-lookup"><span data-stu-id="74460-111">The following links provide lists of available settings for their respective platforms:</span></span>

- [<span data-ttu-id="74460-112">iOS</span><span class="sxs-lookup"><span data-stu-id="74460-112">iOS</span></span>](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-113">Android e Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="74460-113">Android and Samsung KNOX Standard</span></span>](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-114">Android for Work</span><span class="sxs-lookup"><span data-stu-id="74460-114">Android for Work</span></span>](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-115">Windows 10 (computador e móvel)</span><span class="sxs-lookup"><span data-stu-id="74460-115">Windows 10  (PC and mobile)</span></span>](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="74460-116">Windows 8.1</span></span>](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-117">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="74460-117">Windows Phone 8.1</span></span>](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-118">Equipe do Windows</span><span class="sxs-lookup"><span data-stu-id="74460-118">Windows Team</span></span>](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="74460-119">Computadores Windows que executam o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="74460-119">Windows PCs running Intune software client</span></span>](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

<span data-ttu-id="74460-120">Você pode aprender mais sobre como [Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span><span class="sxs-lookup"><span data-stu-id="74460-120">You can learn more about how to [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span></span>

## <span data-ttu-id="74460-121">Adicione e implante aplicativos</span><span class="sxs-lookup"><span data-stu-id="74460-121">Add and deploy apps</span></span>
<a id="add-and-deploy-apps" class="xliff"></a>

<span data-ttu-id="74460-122">Você pode adicionar aplicativos ao Intune e, em seguida, implantá-los em dispositivos gerenciados de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="74460-122">You can add apps to Intune and then deploy them to managed devices in two ways:</span></span>
- <span data-ttu-id="74460-123">**Instalação necessária** – Os aplicativos instalam automaticamente o aplicativo para dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="74460-123">**Required install** - Apps automatically installs the app to managed devices</span></span>
- <span data-ttu-id="74460-124">**Instalação disponível** – Os aplicativos aparecem no Portal da Empresa do Intune para que os usuários possam optar por instalá-los em seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="74460-124">**Available install** - Apps appear in the Intune Company Portal so that users can choose whether to install them on their devices</span></span>

### <span data-ttu-id="74460-125">Adicionar aplicativos</span><span class="sxs-lookup"><span data-stu-id="74460-125">Add apps</span></span>
<a id="add-apps" class="xliff"></a>

<span data-ttu-id="74460-126">Primeiro, você deve disponibilizar aplicativos do Intune por um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="74460-126">First you must make apps available in Intune by one of the following methods:</span></span>
- [<span data-ttu-id="74460-127">Adicionar aplicativos para dispositivos registrados</span><span class="sxs-lookup"><span data-stu-id="74460-127">Add apps for enrolled devices</span></span>](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [<span data-ttu-id="74460-128">Adicionar aplicativos para PCs do cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="74460-128">Add apps for Intune software client PCs</span></span>](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <span data-ttu-id="74460-129">Implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="74460-129">Deploy apps</span></span>
<a id="deploy-apps" class="xliff"></a>

<span data-ttu-id="74460-130">Agora que o aplicativo está disponível no Intune, você pode implantá-lo em dispositivos gerenciados:</span><span class="sxs-lookup"><span data-stu-id="74460-130">Now that the app is availabile in Intune, you can deploy it to managed devices:</span></span>
- [<span data-ttu-id="74460-131">Implantar aplicativos em dispositivos</span><span class="sxs-lookup"><span data-stu-id="74460-131">Deploy apps to devices</span></span>](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- <span data-ttu-id="74460-132">Implantar aplicativos comprados por volume:</span><span class="sxs-lookup"><span data-stu-id="74460-132">Deploy volume-purchased apps:</span></span>
    - [<span data-ttu-id="74460-133">iOS – Programa de compra por volume</span><span class="sxs-lookup"><span data-stu-id="74460-133">iOS - Volume-purchase Program</span></span>](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [<span data-ttu-id="74460-134">Windows Store para Empresas</span><span class="sxs-lookup"><span data-stu-id="74460-134">Windows Store for Business</span></span>](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [<span data-ttu-id="74460-135">Android for Work</span><span class="sxs-lookup"><span data-stu-id="74460-135">Android for Work</span></span>](/intune-classic/deploy-use/android-for-work-apps)

    <span data-ttu-id="74460-136">Depois que configurar os aplicativos para implantação, você pode [configurar aplicativos](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="74460-136">Once you have configured apps for deployment you can [configure apps](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).</span></span>

>[!div class="step-by-step"]

>[<span data-ttu-id="74460-137">&larr; **Organizar usuários e dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Personalizar o Portal da Empresa** &rarr;</span><span class="sxs-lookup"><span data-stu-id="74460-137">&larr; **Organize users and devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Customize Company Portal** &rarr;</span></span>](/intune/company-portal-customize)  
