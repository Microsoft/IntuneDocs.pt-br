---
title: Como atribuir aplicativos aos grupos
titleSuffix: Intune on Azure
description: "Depois de adicionar um aplicativo ao Intune, ele deverá ser atribuído a grupos de usuários ou dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 059c6d2c65c78b6a94f93c26d606abe0451edbbb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="9d23b-103">Como atribuir aplicativos a grupos com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9d23b-103">How to assign apps to groups with Microsoft Intune</span></span>
=======
# Como atribuir aplicativos a grupos com o Microsoft Intune
>>>>>>> live
<a id="how-to-assign-apps-to-groups-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="9d23b-104">Depois de adicionar um aplicativo ao Intune, ele poderá ser atribuído para usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9d23b-104">Once you've added an app to Intune, you can assign it to users and devices.</span></span>
=======
Depois de adicionar um aplicativo ao Intune, ele poderá ser atribuído para usuários e dispositivos.
>>>>>>> live

<span data-ttu-id="9d23b-105">Aplicativos podem ser atribuídos aos dispositivos sejam eles gerenciados pelo Intune ou não.</span><span class="sxs-lookup"><span data-stu-id="9d23b-105">Apps can be assigned to devices whether or not they are managed by Intune.</span></span> <span data-ttu-id="9d23b-106">Use a tabela a seguir para ajudar a compreender as várias opções para atribuir aplicativos a usuários e dispositivos:</span><span class="sxs-lookup"><span data-stu-id="9d23b-106">Use the following table to help you understand the various options for assigning apps to users and devices:</span></span>

||||
|-|-|-|-|
|&nbsp;|<span data-ttu-id="9d23b-107">Dispositivos registrados com o Intune</span><span class="sxs-lookup"><span data-stu-id="9d23b-107">Devices enrolled with Intune</span></span>|<span data-ttu-id="9d23b-108">Dispositivos não registrados com o Intune</span><span class="sxs-lookup"><span data-stu-id="9d23b-108">Devices not enrolled with Intune</span></span>|
|<span data-ttu-id="9d23b-109">Atribuir a usuários</span><span class="sxs-lookup"><span data-stu-id="9d23b-109">Assign to users</span></span>|<span data-ttu-id="9d23b-110">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-110">Yes</span></span>|<span data-ttu-id="9d23b-111">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-111">Yes</span></span>|
|<span data-ttu-id="9d23b-112">Atribuir a dispositivos</span><span class="sxs-lookup"><span data-stu-id="9d23b-112">Assign to devices</span></span>|<span data-ttu-id="9d23b-113">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-113">Yes</span></span>|<span data-ttu-id="9d23b-114">Não</span><span class="sxs-lookup"><span data-stu-id="9d23b-114">No</span></span>|
|<span data-ttu-id="9d23b-115">Atribuir aplicativos encapsulados ou aqueles que incorporam o SDK do Intune (para políticas de proteção de aplicativo)</span><span class="sxs-lookup"><span data-stu-id="9d23b-115">Assign wrapped apps, or apps incorporating the Intune SDK (for app protection policies)</span></span>|<span data-ttu-id="9d23b-116">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-116">Yes</span></span>|<span data-ttu-id="9d23b-117">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-117">Yes</span></span>|
|<span data-ttu-id="9d23b-118">Atribuir aplicativos conforme a disponibilidade</span><span class="sxs-lookup"><span data-stu-id="9d23b-118">Assign apps as Available</span></span>|<span data-ttu-id="9d23b-119">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-119">Yes</span></span>|<span data-ttu-id="9d23b-120">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-120">Yes</span></span>|
|<span data-ttu-id="9d23b-121">Atribuir aplicativos conforme necessário</span><span class="sxs-lookup"><span data-stu-id="9d23b-121">Assign apps as Required</span></span>|<span data-ttu-id="9d23b-122">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-122">Yes</span></span>|<span data-ttu-id="9d23b-123">Não</span><span class="sxs-lookup"><span data-stu-id="9d23b-123">No</span></span>|
|<span data-ttu-id="9d23b-124">Desinstalar aplicativos</span><span class="sxs-lookup"><span data-stu-id="9d23b-124">Uninstall apps</span></span>|<span data-ttu-id="9d23b-125">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-125">Yes</span></span>|<span data-ttu-id="9d23b-126">Não</span><span class="sxs-lookup"><span data-stu-id="9d23b-126">No</span></span>|
|<span data-ttu-id="9d23b-127">Os usuários finais instalam aplicativos disponíveis do aplicativo de Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="9d23b-127">End users install available apps from Company Portal app</span></span>|<span data-ttu-id="9d23b-128">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-128">Yes</span></span>|<span data-ttu-id="9d23b-129">Não</span><span class="sxs-lookup"><span data-stu-id="9d23b-129">No</span></span>|
|<span data-ttu-id="9d23b-130">Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web</span><span class="sxs-lookup"><span data-stu-id="9d23b-130">End users install available apps from web-based Company Portal</span></span>|<span data-ttu-id="9d23b-131">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-131">Yes</span></span>|<span data-ttu-id="9d23b-132">Sim</span><span class="sxs-lookup"><span data-stu-id="9d23b-132">Yes</span></span>|

> [!NOTE]
<<<<<<< HEAD
> <span data-ttu-id="9d23b-133">No momento, é possível atribuir aplicativos iOS e Android (tanto linha de negócios quanto comprados na loja) a dispositivos que não são registrados com o Intune.</span><span class="sxs-lookup"><span data-stu-id="9d23b-133">Currently, you can assign iOS and Android apps (both line of business and store-purchased) to devices that are not enrolled with Intune.</span></span>

## <span data-ttu-id="9d23b-134">Como atribuir um aplicativo</span><span class="sxs-lookup"><span data-stu-id="9d23b-134">How to assign an app</span></span>
<a id="how-to-assign-an-app" class="xliff"></a>

1. <span data-ttu-id="9d23b-135">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="9d23b-135">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="9d23b-136">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9d23b-136">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="9d23b-137">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="9d23b-137">On the **Intune** blade, choose **Mobile apps**.</span></span>
1. <span data-ttu-id="9d23b-138">Na carga de trabalho **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="9d23b-138">In the **Mobile Apps** workload, choose **Manage** > **Apps**.</span></span>
2. <span data-ttu-id="9d23b-139">Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="9d23b-139">On the list of apps blade, click the app you want to assign.</span></span>
3. <span data-ttu-id="9d23b-140">Na folha <*nome do aplicativo*> – **Visão Geral**, escolha **Gerenciar** > **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="9d23b-140">On the <*app name*> - **Overview** blade, choose **Manage** > **Assignments**.</span></span>
4. <span data-ttu-id="9d23b-141">Escolha **Selecionar Grupos** e, na folha **Selecionar grupos**, escolha os grupos do Azure AD aos quais você deseja atribuir o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9d23b-141">Choose **Select Groups** then, on the **Select groups** blade, choose the Azure AD groups to which you want to assign the app.</span></span>
5. <span data-ttu-id="9d23b-142">Para cada aplicativo que você escolher, selecione um **tipo de atribuição** para o aplicativo dentre:</span><span class="sxs-lookup"><span data-stu-id="9d23b-142">For each app you choose, choose an **assignment type** for the app from:</span></span>
    - <span data-ttu-id="9d23b-143">**Disponível** – Os usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="9d23b-143">**Available** - Users install the app from the Company Portal app or website.</span></span>
    - <span data-ttu-id="9d23b-144">**Não Aplicável** – O aplicativo não é instalado nem é mostrado no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="9d23b-144">**Not Applicable** - The app is not installed or shown in the Company Portal.</span></span>
    - <span data-ttu-id="9d23b-145">**Obrigatório** – O aplicativo é instalado nos dispositivos dos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="9d23b-145">**Required** - The app is installed on devices in the selected groups.</span></span>
    - <span data-ttu-id="9d23b-146">**Desinstalar** – O aplicativo é desinstalado dos dispositivos nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="9d23b-146">**Uninstall** - The app is uninstalled from devices in the selected groups.</span></span>
    - <span data-ttu-id="9d23b-147">**Disponível com ou sem registro** – Atribua este aplicativo a grupos de usuários cujos dispositivos não são registrados com o Intune.</span><span class="sxs-lookup"><span data-stu-id="9d23b-147">**Available with or without enrollment** - Assign this app to groups of users whose devices are not enrolled with Intune.</span></span>
6. <span data-ttu-id="9d23b-148">Quando terminar, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9d23b-148">Once you are done, choose **Save**.</span></span>

<span data-ttu-id="9d23b-149">Agora o aplicativo foi atribuído ao grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="9d23b-149">The app is now assigned to the group you selected.</span></span>

## <span data-ttu-id="9d23b-150">Como são resolvidos os conflitos entre as intenções de aplicativo</span><span class="sxs-lookup"><span data-stu-id="9d23b-150">How conflicts between app intents are resolved</span></span>
<a id="how-conflicts-between-app-intents-are-resolved" class="xliff"></a>

<span data-ttu-id="9d23b-151">Às vezes, o mesmo aplicativo é atribuído a vários grupos, mas com intenções diferentes.</span><span class="sxs-lookup"><span data-stu-id="9d23b-151">Sometimes, the same app is assigned to multiple groups, but with different intents.</span></span> <span data-ttu-id="9d23b-152">Nesses casos, use essa tabela para entender a intenção resultante.</span><span class="sxs-lookup"><span data-stu-id="9d23b-152">In these cases, use this table to understand the resulting intent.</span></span>

||||
|-|-|-|
|<span data-ttu-id="9d23b-153">Intenção do grupo 1</span><span class="sxs-lookup"><span data-stu-id="9d23b-153">Group 1 intent</span></span>|<span data-ttu-id="9d23b-154">Intenção do grupo 2</span><span class="sxs-lookup"><span data-stu-id="9d23b-154">Group 2 intent</span></span>|<span data-ttu-id="9d23b-155">Intenção resultante</span><span class="sxs-lookup"><span data-stu-id="9d23b-155">Resulting intent</span></span>|
|<span data-ttu-id="9d23b-156">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-156">User Required</span></span>|<span data-ttu-id="9d23b-157">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-157">User Available</span></span>|<span data-ttu-id="9d23b-158">Necessária e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-158">Required and Available</span></span>|
|<span data-ttu-id="9d23b-159">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-159">User Required</span></span>|<span data-ttu-id="9d23b-160">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-160">User Not Available</span></span>|<span data-ttu-id="9d23b-161">Necessária</span><span class="sxs-lookup"><span data-stu-id="9d23b-161">Required</span></span>|
|<span data-ttu-id="9d23b-162">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-162">User Required</span></span>|<span data-ttu-id="9d23b-163">Desinstalação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-163">User Uninstall</span></span>|<span data-ttu-id="9d23b-164">Necessária</span><span class="sxs-lookup"><span data-stu-id="9d23b-164">Required</span></span>|
|<span data-ttu-id="9d23b-165">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-165">User Available</span></span>|<span data-ttu-id="9d23b-166">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-166">User Not Available</span></span>|<span data-ttu-id="9d23b-167">Não disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-167">Not Available</span></span>|
|<span data-ttu-id="9d23b-168">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-168">User Available</span></span>|<span data-ttu-id="9d23b-169">Desinstalação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-169">User Uninstall</span></span>|<span data-ttu-id="9d23b-170">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="9d23b-170">Uninstall</span></span>|
|<span data-ttu-id="9d23b-171">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-171">User Not Available</span></span>|<span data-ttu-id="9d23b-172">Desinstalação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-172">User Uninstall</span></span>|<span data-ttu-id="9d23b-173">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="9d23b-173">Uninstall</span></span>
|<span data-ttu-id="9d23b-174">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-174">User Required</span></span>|<span data-ttu-id="9d23b-175">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-175">Device Required</span></span>|<span data-ttu-id="9d23b-176">Ambos, mas o Gateway trata como necessário</span><span class="sxs-lookup"><span data-stu-id="9d23b-176">Both exists, Gateway treats required</span></span> 
|<span data-ttu-id="9d23b-177">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-177">User Required</span></span>|<span data-ttu-id="9d23b-178">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-178">Device Uninstall</span></span>|<span data-ttu-id="9d23b-179">Ambos, mas o Gateway resolve como necessário</span><span class="sxs-lookup"><span data-stu-id="9d23b-179">Both exists, Gateway resolves required</span></span> 
|<span data-ttu-id="9d23b-180">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-180">User Available</span></span>|<span data-ttu-id="9d23b-181">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-181">Device Required</span></span>|<span data-ttu-id="9d23b-182">Ambos, mas o Gateway resolve como necessário (Necessário e Disponível)</span><span class="sxs-lookup"><span data-stu-id="9d23b-182">Both exists, Gateway resolves required (Required and Available)</span></span>
|<span data-ttu-id="9d23b-183">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-183">User Available</span></span>|<span data-ttu-id="9d23b-184">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-184">Device Uninstall</span></span>|<span data-ttu-id="9d23b-185">Ambos, mas o Gateway resolve como Disponível.</span><span class="sxs-lookup"><span data-stu-id="9d23b-185">Both exists, Gateway resolves Available.</span></span><br><span data-ttu-id="9d23b-186">O aplicativo aparece no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="9d23b-186">App shows up in Company Portal.</span></span><br><span data-ttu-id="9d23b-187">Se o aplicativo já estiver instalado (como aplicativo necessário com intenção anterior), então o aplicativo será desinstalado.</span><span class="sxs-lookup"><span data-stu-id="9d23b-187">In case if the app is already installed(as required app with previous intent) then the app gets uninstalled.</span></span><br><span data-ttu-id="9d23b-188">Contudo, se o usuário clicar em instalar no portal da empresa, então o aplicativo será instalado e a intenção de desinstalar não é cumprida.</span><span class="sxs-lookup"><span data-stu-id="9d23b-188">But if the user clicks install from the company portal then the app gets installed and uninstall intent is not honored.</span></span>|
|<span data-ttu-id="9d23b-189">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-189">User Not Available</span></span>|<span data-ttu-id="9d23b-190">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-190">Device Required</span></span>|<span data-ttu-id="9d23b-191">Necessária</span><span class="sxs-lookup"><span data-stu-id="9d23b-191">Required</span></span>|
|<span data-ttu-id="9d23b-192">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-192">User Not Available</span></span>|<span data-ttu-id="9d23b-193">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-193">Device Uninstall</span></span>|<span data-ttu-id="9d23b-194">Desinstalar</span><span class="sxs-lookup"><span data-stu-id="9d23b-194">Uninstall</span></span>|
|<span data-ttu-id="9d23b-195">Desinstalação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-195">User Uninstall</span></span>|<span data-ttu-id="9d23b-196">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-196">Device Required</span></span>|<span data-ttu-id="9d23b-197">Ambos, mas o Gateway resolve como Necessário</span><span class="sxs-lookup"><span data-stu-id="9d23b-197">Both exists, Gateway resolves Required</span></span>|
|<span data-ttu-id="9d23b-198">Desinstalação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-198">User Uninstall</span></span>|<span data-ttu-id="9d23b-199">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-199">Device Uninstall</span></span>|<span data-ttu-id="9d23b-200">Ambos, mas o Gateway resolve como Desinstalação</span><span class="sxs-lookup"><span data-stu-id="9d23b-200">Both exist, Gateway resolves Uninstall</span></span>|
|<span data-ttu-id="9d23b-201">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-201">Device Required</span></span>|<span data-ttu-id="9d23b-202">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-202">Device Uninstall</span></span>|<span data-ttu-id="9d23b-203">Necessária</span><span class="sxs-lookup"><span data-stu-id="9d23b-203">Required</span></span>|
|<span data-ttu-id="9d23b-204">Necessário e Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-204">User Required And Available</span></span>|<span data-ttu-id="9d23b-205">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-205">User Available</span></span>|<span data-ttu-id="9d23b-206">Necessária e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-206">Required and Available</span></span>|
|<span data-ttu-id="9d23b-207">Necessário e Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-207">User Required And Available</span></span>|<span data-ttu-id="9d23b-208">Desinstalação do usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-208">User Uninstall</span></span>|<span data-ttu-id="9d23b-209">Necessária e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-209">Required and Available</span></span>|
|<span data-ttu-id="9d23b-210">Necessário e Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-210">User Required And Available</span></span>|<span data-ttu-id="9d23b-211">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-211">User Not Available</span></span>|<span data-ttu-id="9d23b-212">Necessária e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-212">Required and Available</span></span>|
|<span data-ttu-id="9d23b-213">Necessário e Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-213">User Required And Available</span></span>|<span data-ttu-id="9d23b-214">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-214">Device Required</span></span>|<span data-ttu-id="9d23b-215">Ambos Necessário e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-215">Both exists Required and Available</span></span>
|<span data-ttu-id="9d23b-216">Necessário e Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-216">User Required And Available</span></span>|<span data-ttu-id="9d23b-217">Não disponível para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-217">Device Not Available</span></span>|<span data-ttu-id="9d23b-218">Necessária e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-218">Required and Available</span></span>|
|<span data-ttu-id="9d23b-219">Necessário e Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-219">User Required And Available</span></span>|<span data-ttu-id="9d23b-220">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-220">Device Uninstall</span></span>|<span data-ttu-id="9d23b-221">Ambos, mas o gateway resolve como necessário.</span><span class="sxs-lookup"><span data-stu-id="9d23b-221">Both exists, gateway resolves required.</span></span> <span data-ttu-id="9d23b-222">Necessário + Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-222">Required + Available</span></span>
|<span data-ttu-id="9d23b-223">Não Disponível para o Usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-223">User Not Available</span></span>|<span data-ttu-id="9d23b-224">Não disponível para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-224">Device Not Available</span></span>|<span data-ttu-id="9d23b-225">Não disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-225">Not Available</span></span>|
|<span data-ttu-id="9d23b-226">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-226">User Available</span></span>|<span data-ttu-id="9d23b-227">Não disponível para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-227">Device Not Available</span></span>|<span data-ttu-id="9d23b-228">Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-228">Available</span></span>|
|<span data-ttu-id="9d23b-229">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-229">User Required</span></span>|<span data-ttu-id="9d23b-230">Não disponível para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-230">Device Not Available</span></span>|<span data-ttu-id="9d23b-231">Necessária</span><span class="sxs-lookup"><span data-stu-id="9d23b-231">Required</span></span>|
|<span data-ttu-id="9d23b-232">Disponível para o Usuário Sem Registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-232">User Available Without enrollment</span></span>|<span data-ttu-id="9d23b-233">Necessário e disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-233">User Required and Available</span></span>|<span data-ttu-id="9d23b-234">Necessária e Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-234">Required and Available</span></span>
|<span data-ttu-id="9d23b-235">Disponível para o usuário sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-235">User Available without enrollment</span></span>|<span data-ttu-id="9d23b-236">Necessário para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-236">User Required</span></span>|<span data-ttu-id="9d23b-237">Necessária</span><span class="sxs-lookup"><span data-stu-id="9d23b-237">Required</span></span>
|<span data-ttu-id="9d23b-238">Disponível para o usuário sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-238">User Available without enrollment</span></span>|<span data-ttu-id="9d23b-239">Não disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-239">User Not available</span></span>|<span data-ttu-id="9d23b-240">Não disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-240">Not Available</span></span>
|<span data-ttu-id="9d23b-241">Disponível para o usuário sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-241">User Available without enrollment</span></span>|<span data-ttu-id="9d23b-242">Disponível para o usuário</span><span class="sxs-lookup"><span data-stu-id="9d23b-242">User Available</span></span>|<span data-ttu-id="9d23b-243">Disponível</span><span class="sxs-lookup"><span data-stu-id="9d23b-243">Available</span></span>|
|<span data-ttu-id="9d23b-244">Disponível para o usuário sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-244">User Available without enrollment</span></span>|<span data-ttu-id="9d23b-245">Necessário para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-245">Device Required</span></span>|<span data-ttu-id="9d23b-246">Necessário e Disponível sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-246">Required and Available without enrollment</span></span>|
|<span data-ttu-id="9d23b-247">Disponível para o usuário sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-247">User Available without enrollment</span></span>|<span data-ttu-id="9d23b-248">Não disponível para o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-248">Device Not Available</span></span>|<span data-ttu-id="9d23b-249">Disponível sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-249">Available without enrollment</span></span>|
|<span data-ttu-id="9d23b-250">Disponível para o usuário sem registro</span><span class="sxs-lookup"><span data-stu-id="9d23b-250">User Available without enrollment</span></span>|<span data-ttu-id="9d23b-251">Desinstalação do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d23b-251">Device Uninstall</span></span>|<span data-ttu-id="9d23b-252">Desinstalação e Disponível sem registro.</span><span class="sxs-lookup"><span data-stu-id="9d23b-252">Uninstall and Available without enrollment.</span></span><br><span data-ttu-id="9d23b-253">Se o usuário não instalou o aplicativo do portal da empresa, a desinstalação será cumprida.</span><span class="sxs-lookup"><span data-stu-id="9d23b-253">If the user didn’t install the app from the company portal then the uninstall will be honored.</span></span><br><span data-ttu-id="9d23b-254">Se o usuário instalar o aplicativo do portal da empresa, a instalação terá prioridade sobre a desinstalação.</span><span class="sxs-lookup"><span data-stu-id="9d23b-254">If the user installs the app from  the company portal then the install will be prioritized over the uninstall.</span></span>|

>[!NOTE]
><span data-ttu-id="9d23b-255">Apenas para aplicativos da loja do iOS gerenciados, quando você os adiciona ao Intune e os atribui como Necessários, eles são criados automaticamente com as intenções Necessária e Disponível.</span><span class="sxs-lookup"><span data-stu-id="9d23b-255">For managed iOS store apps only, when you add these to Intune and assign them as Required, they are automatically created with both Required, and Available intents.</span></span>

## <span data-ttu-id="9d23b-256">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="9d23b-256">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="9d23b-257">Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9d23b-257">See [How to monitor apps](apps-monitor.md) for information to help you monitor app assignments.</span></span>
=======
> No momento, é possível atribuir aplicativos iOS e Android (tanto linha de negócios quanto comprados na loja) a dispositivos que não são registrados com o Intune.

## Como atribuir um aplicativo
<a id="how-to-assign-an-app" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na carga de trabalho **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir.
3. Na folha <*nome do aplicativo*> – **Visão Geral**, escolha **Gerenciar** > **Atribuições**.
4. Escolha **Selecionar Grupos** e, na folha **Selecionar grupos**, escolha os grupos do Azure AD aos quais você deseja atribuir o aplicativo.
5. Para cada aplicativo que você escolher, selecione um **tipo de atribuição** para o aplicativo dentre:
    - **Disponível** – Os usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa.
    - **Não Aplicável** – O aplicativo não é instalado nem é mostrado no Portal da Empresa.
    - **Obrigatório** – O aplicativo é instalado nos dispositivos dos grupos selecionados.
    - **Desinstalar** – O aplicativo é desinstalado dos dispositivos nos grupos selecionados.
    - **Disponível com ou sem registro** – Atribua este aplicativo a grupos de usuários cujos dispositivos não são registrados com o Intune.
6. Quando terminar, escolha **Salvar**.

Agora o aplicativo foi atribuído ao grupo selecionado.

## Como são resolvidos os conflitos entre as intenções de aplicativo
<a id="how-conflicts-between-app-intents-are-resolved" class="xliff"></a>

Às vezes, o mesmo aplicativo é atribuído a vários grupos, mas com intenções diferentes. Nesses casos, use essa tabela para entender a intenção resultante.

||||
|-|-|-|
|Intenção do grupo 1|Intenção do grupo 2|Intenção resultante|
|Necessário para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário para o usuário|Não Disponível para o Usuário|Necessária|
|Necessário para o usuário|Desinstalação do usuário|Necessária|
|Disponível para o usuário|Não Disponível para o Usuário|Não disponível|
|Disponível para o usuário|Desinstalação do usuário|Desinstalar|
|Não Disponível para o Usuário|Desinstalação do usuário|Desinstalar
|Necessário para o usuário|Necessário para o dispositivo|Ambos, mas o Gateway trata como necessário 
|Necessário para o usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como necessário 
|Disponível para o usuário|Necessário para o dispositivo|Ambos, mas o Gateway resolve como necessário (Necessário e Disponível)
|Disponível para o usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como Disponível.<br>O aplicativo aparece no Portal da Empresa.<br>Se o aplicativo já estiver instalado (como aplicativo necessário com intenção anterior), então o aplicativo será desinstalado.<br>Contudo, se o usuário clicar em instalar no portal da empresa, então o aplicativo será instalado e a intenção de desinstalar não é cumprida.|
|Não Disponível para o Usuário|Necessário para o dispositivo|Necessária|
|Não Disponível para o Usuário|Desinstalação do dispositivo|Desinstalar|
|Desinstalação do usuário|Necessário para o dispositivo|Ambos, mas o Gateway resolve como Necessário|
|Desinstalação do usuário|Desinstalação do dispositivo|Ambos, mas o Gateway resolve como Desinstalação|
|Necessário para o dispositivo|Desinstalação do dispositivo|Necessária|
|Necessário e Disponível para o usuário|Disponível para o usuário|Necessária e Disponível|
|Necessário e Disponível para o usuário|Desinstalação do usuário|Necessária e Disponível|
|Necessário e Disponível para o usuário|Não Disponível para o Usuário|Necessária e Disponível|
|Necessário e Disponível para o usuário|Necessário para o dispositivo|Ambos Necessário e Disponível
|Necessário e Disponível para o usuário|Não disponível para o dispositivo|Necessária e Disponível|
|Necessário e Disponível para o usuário|Desinstalação do dispositivo|Ambos, mas o gateway resolve como necessário. Necessário + Disponível
|Não Disponível para o Usuário|Não disponível para o dispositivo|Não disponível|
|Disponível para o usuário|Não disponível para o dispositivo|Disponível|
|Necessário para o usuário|Não disponível para o dispositivo|Necessária|
|Disponível para o Usuário Sem Registro|Necessário e disponível para o usuário|Necessária e Disponível
|Disponível para o usuário sem registro|Necessário para o usuário|Necessária
|Disponível para o usuário sem registro|Não disponível para o usuário|Não disponível
|Disponível para o usuário sem registro|Disponível para o usuário|Disponível|
|Disponível para o usuário sem registro|Necessário para o dispositivo|Necessário e Disponível sem registro|
|Disponível para o usuário sem registro|Não disponível para o dispositivo|Disponível sem registro|
|Disponível para o usuário sem registro|Desinstalação do dispositivo|Desinstalação e Disponível sem registro.<br>Se o usuário não instalou o aplicativo do portal da empresa, a desinstalação será cumprida.<br>Se o usuário instalar o aplicativo do portal da empresa, a instalação terá prioridade sobre a desinstalação.|

>[!NOTE]
>Apenas para aplicativos da loja do iOS gerenciados, quando você os adiciona ao Intune e os atribui como Necessários, eles são criados automaticamente com as intenções Necessária e Disponível.

## Próximas etapas
<a id="next-steps" class="xliff"></a>

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.
>>>>>>> live
