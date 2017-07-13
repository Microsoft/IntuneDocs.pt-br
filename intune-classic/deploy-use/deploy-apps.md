---
title: Implantar aplicativos
description: "Este tópico explica conceitos que você precisará compreender antes de iniciar a implantação de aplicativos com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 13c4046ed431dc25bda9a2facc59dbcb6d3e5ab5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="45a9c-103">Implantar aplicativos com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="45a9c-103">Deploy apps with Microsoft Intune</span></span>
<a id="deploy-apps-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="45a9c-104">Este tópico explica alguns dos conceitos que você precisa compreender antes de iniciar a implantação de aplicativos com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="45a9c-104">This topic explains some of the concepts you need to understand before you start deploying apps with Microsoft Intune.</span></span>


## <span data-ttu-id="45a9c-105">Ações de implantação de aplicativo</span><span class="sxs-lookup"><span data-stu-id="45a9c-105">App deployment actions</span></span>
<a id="app-deployment-actions" class="xliff"></a>
<span data-ttu-id="45a9c-106">Quando você implanta aplicativos, pode escolher uma das seguintes ações de implantação:</span><span class="sxs-lookup"><span data-stu-id="45a9c-106">When you deploy apps, you can choose from one of the following deployment actions:</span></span>

-   <span data-ttu-id="45a9c-107">**Instalação obrigatória** – O aplicativo está instalado no dispositivo, sem necessidade de intervenção do usuário.</span><span class="sxs-lookup"><span data-stu-id="45a9c-107">**Required install** – The app is installed onto the device with no user intervention required.</span></span>

    > [!TIP]
    > <span data-ttu-id="45a9c-108">Para dispositivos iOS que não estão no modo supervisionado, e para todos os dispositivos Android, o usuário deve aceitar a oferta do aplicativo antes que ele seja instalado.</span><span class="sxs-lookup"><span data-stu-id="45a9c-108">For iOS devices that are not in supervised mode, and for all Android devices, the user must accept the app offer before it is installed.</span></span>
    >
    >  <span data-ttu-id="45a9c-109">Se um usuário desinstalar um aplicativo implantado como instalação obrigatória, o Intune reinstalará automaticamente o aplicativo após o próximo ciclo de inventário, que normalmente ocorre a cada sete dias.</span><span class="sxs-lookup"><span data-stu-id="45a9c-109">If a user uninstalls an app that you deployed as a required install, Intune automatically reinstalls the app after the next inventory cycle, which typically occurs every seven days.</span></span>

-   <span data-ttu-id="45a9c-110">**Instalação disponível** – O aplicativo é exibido no portal da empresa e os usuários podem instalá-lo sob demanda.</span><span class="sxs-lookup"><span data-stu-id="45a9c-110">**Available install** – The app is displayed in the company portal, and users can install it on demand.</span></span>

-   <span data-ttu-id="45a9c-111">**Desinstalar** – O aplicativo é desinstalado do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="45a9c-111">**Uninstall** – The app is uninstalled from the device.</span></span>

-   <span data-ttu-id="45a9c-112">**Não aplicável** – O aplicativo não será exibido no portal da empresa e não está instalado em nenhum dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="45a9c-112">**Not applicable** – The app is not displayed in the company portal and is not installed on any devices.</span></span>

#### <span data-ttu-id="45a9c-113">Entender quais ações de implantação estão disponíveis para cada tipo de instalador</span><span class="sxs-lookup"><span data-stu-id="45a9c-113">Understand which deployment actions are available for each installer type</span></span>
<a id="understand-which-deployment-actions-are-available-for-each-installer-type" class="xliff"></a>

|<span data-ttu-id="45a9c-114">Tipo de instalador</span><span class="sxs-lookup"><span data-stu-id="45a9c-114">Installer type</span></span>|<span data-ttu-id="45a9c-115">Instalação requerida</span><span class="sxs-lookup"><span data-stu-id="45a9c-115">Required install</span></span>|<span data-ttu-id="45a9c-116">Instalação disponível</span><span class="sxs-lookup"><span data-stu-id="45a9c-116">Available install</span></span>|<span data-ttu-id="45a9c-117">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="45a9c-117">Uninstall</span></span>|<span data-ttu-id="45a9c-118">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="45a9c-118">Not applicable</span></span>|
|------------------|--------------------|---------------------|-------------|------------------|
|<span data-ttu-id="45a9c-119">Pacote de aplicativos do Windows (implantado em um grupo de usuários)</span><span class="sxs-lookup"><span data-stu-id="45a9c-119">Windows app package (deployed to a user group)</span></span>|<span data-ttu-id="45a9c-120">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-120">Yes</span></span>|<span data-ttu-id="45a9c-121">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-121">Yes</span></span>|<span data-ttu-id="45a9c-122">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-122">Yes</span></span>|<span data-ttu-id="45a9c-123">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-123">Yes</span></span>|
|<span data-ttu-id="45a9c-124">Pacote do aplicativo do Windows (implantado em um grupo de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="45a9c-124">Windows app package (deployed to a device group)</span></span>|<span data-ttu-id="45a9c-125">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-125">Yes</span></span>|<span data-ttu-id="45a9c-126">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-126">No</span></span>|<span data-ttu-id="45a9c-127">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-127">Yes</span></span>|<span data-ttu-id="45a9c-128">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-128">Yes</span></span>|
|<span data-ttu-id="45a9c-129">Pacote de aplicativos para dispositivos móveis (implantado em um grupo de usuários)</span><span class="sxs-lookup"><span data-stu-id="45a9c-129">App package for mobile devices (deployed to a user group)</span></span>|<span data-ttu-id="45a9c-130">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-130">Yes</span></span>|<span data-ttu-id="45a9c-131">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-131">Yes</span></span>|<span data-ttu-id="45a9c-132">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-132">Yes</span></span>|<span data-ttu-id="45a9c-133">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-133">Yes</span></span>|
|<span data-ttu-id="45a9c-134">Pacote de aplicativos para dispositivos móveis (implantado em um grupo de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="45a9c-134">App package for mobile devices (deployed to a device group)</span></span>|<span data-ttu-id="45a9c-135">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-135">Yes</span></span>|<span data-ttu-id="45a9c-136">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-136">No</span></span>|<span data-ttu-id="45a9c-137">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-137">Yes</span></span>|<span data-ttu-id="45a9c-138">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-138">Yes</span></span>|
|<span data-ttu-id="45a9c-139">Windows Installer (implantado em um grupo de usuários)</span><span class="sxs-lookup"><span data-stu-id="45a9c-139">Windows Installer (deployed to a user group)</span></span>|<span data-ttu-id="45a9c-140">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-140">No</span></span>|<span data-ttu-id="45a9c-141">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-141">Yes</span></span>|<span data-ttu-id="45a9c-142">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-142">No</span></span>|<span data-ttu-id="45a9c-143">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-143">Yes</span></span>|
|<span data-ttu-id="45a9c-144">Windows Installer (implantado em um grupo de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="45a9c-144">Windows Installer (deployed to a device group)</span></span>|<span data-ttu-id="45a9c-145">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-145">Yes</span></span>|<span data-ttu-id="45a9c-146">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-146">No</span></span>|<span data-ttu-id="45a9c-147">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-147">Yes</span></span>|<span data-ttu-id="45a9c-148">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-148">Yes</span></span>|
|<span data-ttu-id="45a9c-149">Link externo (implantado em um grupo de usuários)</span><span class="sxs-lookup"><span data-stu-id="45a9c-149">External link (deployed to a user group)</span></span>|<span data-ttu-id="45a9c-150">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-150">No</span></span>|<span data-ttu-id="45a9c-151">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-151">Yes</span></span>|<span data-ttu-id="45a9c-152">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-152">No</span></span>|<span data-ttu-id="45a9c-153">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-153">Yes</span></span>|
|<span data-ttu-id="45a9c-154">Link externo (implantado em um grupo de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="45a9c-154">External link (deployed to a device group)</span></span>|<span data-ttu-id="45a9c-155">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-155">No</span></span>|<span data-ttu-id="45a9c-156">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-156">No</span></span>|<span data-ttu-id="45a9c-157">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-157">No</span></span>|<span data-ttu-id="45a9c-158">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-158">No</span></span>|
|<span data-ttu-id="45a9c-159">Aplicativo iOS gerenciado da loja de aplicativos (implantado em um grupo de usuários)</span><span class="sxs-lookup"><span data-stu-id="45a9c-159">Managed iOS app from the app store (deployed to a user group)</span></span>|<span data-ttu-id="45a9c-160">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-160">Yes</span></span>|<span data-ttu-id="45a9c-161">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-161">Yes</span></span>|<span data-ttu-id="45a9c-162">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-162">Yes</span></span>|<span data-ttu-id="45a9c-163">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-163">Yes</span></span>|
|<span data-ttu-id="45a9c-164">Aplicativo iOS gerenciado da loja de aplicativos (implantado em um grupo de dispositivos)</span><span class="sxs-lookup"><span data-stu-id="45a9c-164">Managed iOS app from the app store (deployed to a device group)</span></span>|<span data-ttu-id="45a9c-165">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-165">Yes</span></span>|<span data-ttu-id="45a9c-166">Não</span><span class="sxs-lookup"><span data-stu-id="45a9c-166">No</span></span>|<span data-ttu-id="45a9c-167">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-167">Yes</span></span>|<span data-ttu-id="45a9c-168">Sim</span><span class="sxs-lookup"><span data-stu-id="45a9c-168">Yes</span></span>|
> [!TIP]
> <span data-ttu-id="45a9c-169">Ao implantar aplicativos, se você selecionar usuários e grupos de dispositivos, poderá implantar o aplicativo apenas como uma **Instalação disponível**.</span><span class="sxs-lookup"><span data-stu-id="45a9c-169">When you deploy apps, if you select both user and device groups, you can only deploy the app as an **Available install**.</span></span>

## <span data-ttu-id="45a9c-170">Conflitos de implantação</span><span class="sxs-lookup"><span data-stu-id="45a9c-170">Deployment conflicts</span></span>
<a id="deployment-conflicts" class="xliff"></a>
<span data-ttu-id="45a9c-171">Quando duas implantações com a mesma ação de implantação são recebidas por um dispositivo, as seguintes regras se aplicam:</span><span class="sxs-lookup"><span data-stu-id="45a9c-171">When two deployments with the same deployment action are received by a device, the following rules apply:</span></span>

-   <span data-ttu-id="45a9c-172">Implantações em um grupo de dispositivos têm precedência sobre as implantações para um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="45a9c-172">Deployments to a device group take precedence over deployments to a user group.</span></span> <span data-ttu-id="45a9c-173">No entanto, se um aplicativo for implantado em um grupo de usuários com a ação de implantação **disponível** e o mesmo aplicativo também for implantado em um grupo de dispositivos com uma ação de implantação de **não aplicável**, o aplicativo será disponibilizado no portal da empresa para os usuários instalarem.</span><span class="sxs-lookup"><span data-stu-id="45a9c-173">However, if an app is deployed to a user group with a deployment action of **Available**, and the same app is also deployed to a device group with a deployment action of **Not Applicable**, the app will be made available in the company portal for users to install.</span></span>

-   <span data-ttu-id="45a9c-174">Uma ação de instalação tem precedência sobre uma ação de desinstalação.</span><span class="sxs-lookup"><span data-stu-id="45a9c-174">An install action takes precedence over an uninstall action.</span></span>

-   <span data-ttu-id="45a9c-175">Se uma instalação obrigatória e uma instalação disponível forem recebidas por um dispositivo, as ações serão combinadas.</span><span class="sxs-lookup"><span data-stu-id="45a9c-175">If both a required and an available install are received by a device, the actions are combined.</span></span> <span data-ttu-id="45a9c-176">Em outras palavras, o usuário pode instalar o aplicativo disponível do portal da empresa antes de iniciar a instalação obrigatória.</span><span class="sxs-lookup"><span data-stu-id="45a9c-176">In other words, the user can install the available app from the company portal before the required install begins.</span></span>


## <span data-ttu-id="45a9c-177">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="45a9c-177">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="45a9c-178">Saiba como [implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="45a9c-178">Learn how to [deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>
