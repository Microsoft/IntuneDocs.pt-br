---
title: "Como os usuários Android podem obter aplicativos"
description: "Métodos para disponibilizar aplicativos do Android para usuários finais"
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4f0364750edf2e97e2b621c27fb25bea8e0f537c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3fadf-103">Como os usuários Android podem obter aplicativos</span><span class="sxs-lookup"><span data-stu-id="3fadf-103">How your Android users get their apps</span></span>
<a id="how-your-android-users-get-their-apps" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="3fadf-104">Use estas informações para entender como e onde os usuários finais do Android obtêm os aplicativos que você distribui por meio do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3fadf-104">Use this information to understand how and where your Android end users get the apps that you distribute through Microsoft Intune.</span></span> <span data-ttu-id="3fadf-105">As informações podem variar de acordo com o tipo de dispositivo (dispositivos Android nativos ou Samsung Knox Standard).</span><span class="sxs-lookup"><span data-stu-id="3fadf-105">The information can vary by device type (native Android devices or Samsung Knox Standard devices).</span></span>

## <span data-ttu-id="3fadf-106">Dispositivos Android nativos (que não são Samsung Knox Standard)</span><span class="sxs-lookup"><span data-stu-id="3fadf-106">Native (non-Samsung Knox Standard) Android devices</span></span>
<a id="native-non-samsung-knox-standard-android-devices" class="xliff"></a>

| <span data-ttu-id="3fadf-107">Tipo de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3fadf-107">App type</span></span> | <span data-ttu-id="3fadf-108">Aplicativos LOB (Linha de negócios)</span><span class="sxs-lookup"><span data-stu-id="3fadf-108">Line-of-business (LOB) apps</span></span> | <span data-ttu-id="3fadf-109">Aplicativos da Play Store</span><span class="sxs-lookup"><span data-stu-id="3fadf-109">Play Store apps</span></span>  |
| ------------- |-------------| -----|
| <span data-ttu-id="3fadf-110">Aplicativos disponíveis</span><span class="sxs-lookup"><span data-stu-id="3fadf-110">Available apps</span></span>      | <span data-ttu-id="3fadf-111">Os usuários tocam em **instalar** no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="3fadf-111">Users tap **install** in the Company Portal.</span></span> <span data-ttu-id="3fadf-112">É exibida uma notificação, que os usuários tocam para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3fadf-112">A notification appears, which users then tap to start the installation.</span></span> <span data-ttu-id="3fadf-113">Após a instalação ser bem-sucedida, a notificação desaparece.</span><span class="sxs-lookup"><span data-stu-id="3fadf-113">After the installation is successful, the notification disappears.</span></span> | <span data-ttu-id="3fadf-114">Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3fadf-114">Users tap the app in the Company Portal and are taken to an app page in the Play Store, where they can start the installation.</span></span>|
| <span data-ttu-id="3fadf-115">Required apps</span><span class="sxs-lookup"><span data-stu-id="3fadf-115">Required apps</span></span>      | <span data-ttu-id="3fadf-116">Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3fadf-116">Users are shown a notification, which they cannot dismiss, indicating that they need to install an app.</span></span> <span data-ttu-id="3fadf-117">Os usuários tocam a notificação para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3fadf-117">Users tap the notification to start the installation.</span></span> <span data-ttu-id="3fadf-118">Após a instalação ser bem-sucedida, a notificação desaparece.</span><span class="sxs-lookup"><span data-stu-id="3fadf-118">After the installation is successful, the notification disappears.</span></span>    | <span data-ttu-id="3fadf-119">Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3fadf-119">Users are shown a notification, which they cannot dismiss, indicating that they need to install an app.</span></span> <span data-ttu-id="3fadf-120">Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3fadf-120">Users tap the notification and are taken to an app page in the Play Store, where they can start the installation.</span></span> <span data-ttu-id="3fadf-121">Após a instalação ser bem-sucedida, a notificação desaparece.</span><span class="sxs-lookup"><span data-stu-id="3fadf-121">After the installation is successful, the notification disappears.</span></span> |

## <span data-ttu-id="3fadf-122">Dispositivos Samsung Knox Standard Android</span><span class="sxs-lookup"><span data-stu-id="3fadf-122">Samsung Knox Standard Android devices</span></span>
<a id="samsung-knox-standard-android-devices" class="xliff"></a>

| <span data-ttu-id="3fadf-123">Tipo de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3fadf-123">App type</span></span> | <span data-ttu-id="3fadf-124">Aplicativos LOB (Linha de negócios)</span><span class="sxs-lookup"><span data-stu-id="3fadf-124">Line-of-business (LOB) apps</span></span> | <span data-ttu-id="3fadf-125">Aplicativos da Play Store</span><span class="sxs-lookup"><span data-stu-id="3fadf-125">Play Store apps</span></span>  |
| ------------- |-------------| -----|
| <span data-ttu-id="3fadf-126">Aplicativos disponíveis</span><span class="sxs-lookup"><span data-stu-id="3fadf-126">Available apps</span></span>      | <span data-ttu-id="3fadf-127">Os usuários tocam em **instalar** no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="3fadf-127">Users tap **install** in the Company Portal.</span></span> <span data-ttu-id="3fadf-128">O aplicativo é instalado sem outras intervenções do usuário.</span><span class="sxs-lookup"><span data-stu-id="3fadf-128">The app installs without further user intervention.</span></span> | <span data-ttu-id="3fadf-129">Os usuários tocam no aplicativo no Portal da Empresa e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3fadf-129">Users tap the app in the Company Portal and are taken to an app page in the Play Store, where they can start the installation.</span></span>|
| <span data-ttu-id="3fadf-130">Required apps</span><span class="sxs-lookup"><span data-stu-id="3fadf-130">Required apps</span></span>      | <span data-ttu-id="3fadf-131">O aplicativo é instalado sem nenhuma outra intervenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="3fadf-131">The app is installed without any user intervention.</span></span>    | <span data-ttu-id="3fadf-132">Os usuários veem uma notificação, que não podem ignorar, indicando que eles precisam instalar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3fadf-132">Users are shown a notification, which they cannot dismiss, indicating that they need to install an app.</span></span> <span data-ttu-id="3fadf-133">Os usuários tocam na notificação e são levados para uma página do aplicativo na Play Store, em que podem iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="3fadf-133">Users tap the notification and are taken to an app page in the Play Store, where they can start the installation.</span></span> <span data-ttu-id="3fadf-134">Após a instalação ser bem-sucedida, a notificação desaparece.</span><span class="sxs-lookup"><span data-stu-id="3fadf-134">After the installation is successful, the notification disappears.</span></span> |

<span data-ttu-id="3fadf-135">Aplicativos podem ser gerenciados ou não gerenciados, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="3fadf-135">Apps can be managed or unmanaged, as described below.</span></span> <span data-ttu-id="3fadf-136">O processo de criação de aplicativos gerenciados é o mesmo para todos os tipos de dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="3fadf-136">The process of making apps managed is the same for all types of Android devices.</span></span>

<span data-ttu-id="3fadf-137">**Aplicativos gerenciados** – Aplicativos que podem ser gerenciados por meio de políticas.</span><span class="sxs-lookup"><span data-stu-id="3fadf-137">**Managed apps** - These are apps that can be managed through policies.</span></span> <span data-ttu-id="3fadf-138">Eles foram “encapsulados” pelo Intune ou criados com o SDK (Software Development Kit) do MAM (Mobile Application Management) do Intune.</span><span class="sxs-lookup"><span data-stu-id="3fadf-138">They have been "wrapped" by Intune or built with the Intune Mobile Application Management (MAM) Software Development Kit (SDK).</span></span> <span data-ttu-id="3fadf-139">Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.</span><span class="sxs-lookup"><span data-stu-id="3fadf-139">These apps can be managed by Intune, and application policies can be applied to them.</span></span>

<span data-ttu-id="3fadf-140">**Aplicativos não gerenciados** – Aplicativos que não podem ser gerenciados por meio de políticas.</span><span class="sxs-lookup"><span data-stu-id="3fadf-140">**Unmanaged apps** - These are apps that cannot be managed through policies.</span></span> <span data-ttu-id="3fadf-141">Eles não foram encapsulados pelo Intune ou não incorporam o SDK do MAM do Intune.</span><span class="sxs-lookup"><span data-stu-id="3fadf-141">They have not been wrapped by Intune or do not incorporate the Intune MAM SDK.</span></span> <span data-ttu-id="3fadf-142">Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3fadf-142">Application policies cannot be applied to these apps.</span></span>

### <span data-ttu-id="3fadf-143">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3fadf-143">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="3fadf-144">Adicionar aplicativos com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3fadf-144">Add apps with Microsoft Intune</span></span>](apps-add.md)

[<span data-ttu-id="3fadf-145">Como usuários do iOS podem obter aplicativos</span><span class="sxs-lookup"><span data-stu-id="3fadf-145">How your iOS users get their apps</span></span>](end-user-apps-ios.md)

[<span data-ttu-id="3fadf-146">Como os usuários do Windows podem obter aplicativos</span><span class="sxs-lookup"><span data-stu-id="3fadf-146">How your Windows users get their apps</span></span>](end-user-apps-windows.md)
