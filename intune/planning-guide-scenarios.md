---
title: "Identificar os cenários de caso de uso"
description: "Este artigo ajuda você a identificar cenários de casos de uso e subcasos de uso do Intune para uma implementação somente na nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e17fe40fc50f40bf8adefa6dfdc4d4583cc6cc80
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="4cb45-103">Identificar cenários de casos de uso do gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="4cb45-103">Identify mobile device management use-case scenarios</span></span>
<a id="identify-mobile-device-management-use-case-scenarios" class="xliff"></a>

<span data-ttu-id="4cb45-104">Identificar os cenários de casos de uso é uma parte importante do processo de planejamento para uma implantação bem-sucedida do Intune.</span><span class="sxs-lookup"><span data-stu-id="4cb45-104">Identifying your use-case scenarios is an important part of the planning process for a successful Intune deployment.</span></span> <span data-ttu-id="4cb45-105">Os cenários de casos de uso são úteis, pois permitem segmentar os usuários em grupos gerenciáveis por tipo de usuário ou função e pela propriedade do dispositivo do usuário (por exemplo, da empresa ou pessoal).</span><span class="sxs-lookup"><span data-stu-id="4cb45-105">Use-case scenarios are helpful because they let you segment your users into manageable groups by user type or role, and the ownership of the user's device (for example, company or personal).</span></span>

<span data-ttu-id="4cb45-106">Vejamos alguns exemplos para ajudar sua organização a identificar os cenários de casos de uso do Intune, bem como os grupos organizacionais e as plataformas de dispositivos móveis associadas a cada caso de uso.</span><span class="sxs-lookup"><span data-stu-id="4cb45-106">Let’s discuss a few examples to help your organization identify Intune use-case scenarios, as well as organizational groups, and mobile device platforms associated with each use case.</span></span>

## <span data-ttu-id="4cb45-107">Propriedade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="4cb45-107">Device ownership</span></span>
<a id="device-ownership" class="xliff"></a>
<span data-ttu-id="4cb45-108">Comece consultando as metas e os objetivos de implantação do Intune de sua organização, a fim de ajudar a identificar os principais cenários de casos de uso de sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4cb45-108">You can begin by referring to your organization's Intune deployment goals and objectives to help identity the main use-case scenarios for your deployment.</span></span> <span data-ttu-id="4cb45-109">Dentro do escopo do plano de implantação do Intune, responda às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="4cb45-109">Within the scope of your Intune deployment plan, answer the following questions:</span></span>

-   <span data-ttu-id="4cb45-110">Você planeja dar suporte a dispositivos de propriedade corporativa?</span><span class="sxs-lookup"><span data-stu-id="4cb45-110">Are you planning to support corporate owned devices?</span></span>

-   <span data-ttu-id="4cb45-111">Você planeja dar suporte a dispositivos BYOD (pessoais)?</span><span class="sxs-lookup"><span data-stu-id="4cb45-111">Are you planning to support personally owned devices (BYOD)?</span></span>

<span data-ttu-id="4cb45-112">Elas não são do tipo opções e/ou.</span><span class="sxs-lookup"><span data-stu-id="4cb45-112">These are not either/or options.</span></span> <span data-ttu-id="4cb45-113">Você pode achar necessário dar suporte a ambas as formas de propriedade do dispositivo para atender às suas metas organizacionais.</span><span class="sxs-lookup"><span data-stu-id="4cb45-113">You may find you need to support both forms of device ownership to meet your organizational goals.</span></span> <span data-ttu-id="4cb45-114">Os subcasos de uso ajudarão a esclarecer os locais em que devem ser aplicadas diferentes políticas de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4cb45-114">The sub-use-cases will help clarify where to apply the different device management policies.</span></span>

### <span data-ttu-id="4cb45-115">Tipo de usuário ou função do dispositivo</span><span class="sxs-lookup"><span data-stu-id="4cb45-115">User type or device role</span></span>
<a id="user-type-or-device-role" class="xliff"></a>

<span data-ttu-id="4cb45-116">Determine se cada cenário de caso de uso também inclui subcasos de uso.</span><span class="sxs-lookup"><span data-stu-id="4cb45-116">Determine if each use-case scenario also includes sub-use-cases.</span></span> <span data-ttu-id="4cb45-117">Por exemplo, sua organização pode ter identificado requisitos para dar suporte a um cenário de caso de uso corporativo que inclui subcasos de uso adicionais com base no tipo de usuário ou na função do dispositivo, como:</span><span class="sxs-lookup"><span data-stu-id="4cb45-117">For example, your organization may have identified requirements to support a corporate use-case scenario that includes additional sub-use-cases based on user type or device role, such as:</span></span>

-   <span data-ttu-id="4cb45-118">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-118">Information worker</span></span>

-   <span data-ttu-id="4cb45-119">Executivo</span><span class="sxs-lookup"><span data-stu-id="4cb45-119">Executive</span></span>

-   <span data-ttu-id="4cb45-120">Quiosque</span><span class="sxs-lookup"><span data-stu-id="4cb45-120">Kiosk</span></span>

<span data-ttu-id="4cb45-121">Estes são alguns exemplos de cenários de casos de uso e subcasos de uso:</span><span class="sxs-lookup"><span data-stu-id="4cb45-121">Here are a few examples of use-case and sub-use-case scenarios:</span></span>

| <span data-ttu-id="4cb45-122">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="4cb45-122">**Use cases**</span></span> | <span data-ttu-id="4cb45-123">**Subcasos de uso**</span><span class="sxs-lookup"><span data-stu-id="4cb45-123">**Sub-use cases**</span></span> |
|:---:|:---:|
| <span data-ttu-id="4cb45-124">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-124">Corporate</span></span> | <span data-ttu-id="4cb45-125">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-125">Information worker</span></span> |              
| <span data-ttu-id="4cb45-126">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-126">Corporate</span></span> | <span data-ttu-id="4cb45-127">Executivos</span><span class="sxs-lookup"><span data-stu-id="4cb45-127">Executives</span></span> |           
| <span data-ttu-id="4cb45-128">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-128">Corporate</span></span> | <span data-ttu-id="4cb45-129">Quiosque</span><span class="sxs-lookup"><span data-stu-id="4cb45-129">Kiosk</span></span> |
| <span data-ttu-id="4cb45-130">BYOD</span><span class="sxs-lookup"><span data-stu-id="4cb45-130">BYOD</span></span> | <span data-ttu-id="4cb45-131">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-131">Information worker</span></span> |           
| <span data-ttu-id="4cb45-132">BYOD</span><span class="sxs-lookup"><span data-stu-id="4cb45-132">BYOD</span></span> | <span data-ttu-id="4cb45-133">Executivos</span><span class="sxs-lookup"><span data-stu-id="4cb45-133">Executives</span></span> |

<span data-ttu-id="4cb45-134">[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para inserir os cenários de casos de uso e subcasos de uso de sua organização.</span><span class="sxs-lookup"><span data-stu-id="4cb45-134">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to enter your organization’s use-case and sub-use-case scenarios.</span></span>

## <span data-ttu-id="4cb45-135">Grupos organizacionais para seus cenários</span><span class="sxs-lookup"><span data-stu-id="4cb45-135">Organizational groups for your scenarios</span></span>
<a id="organizational-groups-for-your-scenarios" class="xliff"></a>

<span data-ttu-id="4cb45-136">Agora você precisa identificar os grupos organizacionais associados a cada cenário de caso de uso e subcaso de uso.</span><span class="sxs-lookup"><span data-stu-id="4cb45-136">Now you need to identify the organizational groups that are associated with each use-case and sub-use-case scenario.</span></span> <span data-ttu-id="4cb45-137">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4cb45-137">For example:</span></span>

| <span data-ttu-id="4cb45-138">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="4cb45-138">**Use cases**</span></span> | <span data-ttu-id="4cb45-139">**Subcasos de uso**</span><span class="sxs-lookup"><span data-stu-id="4cb45-139">**Sub-use cases**</span></span> | <span data-ttu-id="4cb45-140">**Grupos organizacionais**</span><span class="sxs-lookup"><span data-stu-id="4cb45-140">**Organizational groups**</span></span> |
|:---:|:---:|:---:|
| <span data-ttu-id="4cb45-141">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-141">Corporate</span></span> | <span data-ttu-id="4cb45-142">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-142">Information worker</span></span> | <span data-ttu-id="4cb45-143">RH, Finanças</span><span class="sxs-lookup"><span data-stu-id="4cb45-143">HR, Finance</span></span> |               
| <span data-ttu-id="4cb45-144">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-144">Corporate</span></span> | <span data-ttu-id="4cb45-145">Executivo</span><span class="sxs-lookup"><span data-stu-id="4cb45-145">Executive</span></span> | <span data-ttu-id="4cb45-146">RH, Finanças</span><span class="sxs-lookup"><span data-stu-id="4cb45-146">HR, Finance</span></span> |            
| <span data-ttu-id="4cb45-147">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-147">Corporate</span></span> | <span data-ttu-id="4cb45-148">Quiosque</span><span class="sxs-lookup"><span data-stu-id="4cb45-148">Kiosk</span></span> | <span data-ttu-id="4cb45-149">Varejo</span><span class="sxs-lookup"><span data-stu-id="4cb45-149">Retail</span></span> |
| <span data-ttu-id="4cb45-150">BYOD</span><span class="sxs-lookup"><span data-stu-id="4cb45-150">BYOD</span></span> | <span data-ttu-id="4cb45-151">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-151">Information worker</span></span> | <span data-ttu-id="4cb45-152">Marketing, Vendas</span><span class="sxs-lookup"><span data-stu-id="4cb45-152">Marketing, Sales</span></span> |            
| <span data-ttu-id="4cb45-153">BYOD</span><span class="sxs-lookup"><span data-stu-id="4cb45-153">BYOD</span></span> | <span data-ttu-id="4cb45-154">Executivo</span><span class="sxs-lookup"><span data-stu-id="4cb45-154">Executive</span></span> | <span data-ttu-id="4cb45-155">Marketing, Vendas</span><span class="sxs-lookup"><span data-stu-id="4cb45-155">Marketing, Sales</span></span> |


## <span data-ttu-id="4cb45-156">Plataformas de dispositivos móveis para seus cenários</span><span class="sxs-lookup"><span data-stu-id="4cb45-156">Mobile device platforms for your scenarios</span></span>
<a id="mobile-device-platforms-for-your-scenarios" class="xliff"></a>

<span data-ttu-id="4cb45-157">A próxima etapa é identificar as plataformas de dispositivos móveis associadas a cada cenário de caso de uso.</span><span class="sxs-lookup"><span data-stu-id="4cb45-157">The next step is to identify the mobile device platforms associated with each use-case scenario.</span></span> <span data-ttu-id="4cb45-158">Pode haver mais de uma.</span><span class="sxs-lookup"><span data-stu-id="4cb45-158">There may be more than one.</span></span>

<span data-ttu-id="4cb45-159">Por exemplo, seu cenário de caso de uso corporativo pode dar suporte a plataformas de dispositivos iOS e Android Samsung KNOX.</span><span class="sxs-lookup"><span data-stu-id="4cb45-159">For example, your corporate use-case scenario may support iOS and Android Samsung KNOX device platforms.</span></span> <span data-ttu-id="4cb45-160">Sua política BYOD pode incluir suporte para plataformas de dispositivos móveis adicionais como Android (não Samsung KNOX) e Windows 10 Mobile.</span><span class="sxs-lookup"><span data-stu-id="4cb45-160">Your BYOD policy may include support for additional mobile device platforms like Android (non-Samsung KNOX) and Windows 10 Mobile.</span></span> <span data-ttu-id="4cb45-161">Aproveitando os exemplos anteriores, associamos as plataformas de dispositivos móveis a cada cenário de caso de uso.</span><span class="sxs-lookup"><span data-stu-id="4cb45-161">Building on the preceding examples, we've associated mobile device platforms with each use-case scenario.</span></span>

| <span data-ttu-id="4cb45-162">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="4cb45-162">**Use cases**</span></span> | <span data-ttu-id="4cb45-163">**Subcasos de uso**</span><span class="sxs-lookup"><span data-stu-id="4cb45-163">**Sub-use cases**</span></span> | <span data-ttu-id="4cb45-164">**Grupos**</span><span class="sxs-lookup"><span data-stu-id="4cb45-164">**Groups**</span></span> | <span data-ttu-id="4cb45-165">**Plataformas de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="4cb45-165">**Device platforms**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="4cb45-166">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-166">Corporate</span></span> | <span data-ttu-id="4cb45-167">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-167">Information worker</span></span> | <span data-ttu-id="4cb45-168">RH, Finanças</span><span class="sxs-lookup"><span data-stu-id="4cb45-168">HR, Finance</span></span> | <span data-ttu-id="4cb45-169">iOS</span><span class="sxs-lookup"><span data-stu-id="4cb45-169">iOS</span></span> |                                                           
| <span data-ttu-id="4cb45-170">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-170">Corporate</span></span> | <span data-ttu-id="4cb45-171">Executivos</span><span class="sxs-lookup"><span data-stu-id="4cb45-171">Executives</span></span> | <span data-ttu-id="4cb45-172">RH, Finanças</span><span class="sxs-lookup"><span data-stu-id="4cb45-172">HR, Finance</span></span> | <span data-ttu-id="4cb45-173">iOS</span><span class="sxs-lookup"><span data-stu-id="4cb45-173">iOS</span></span> |                                                           
| <span data-ttu-id="4cb45-174">Corporativo</span><span class="sxs-lookup"><span data-stu-id="4cb45-174">Corporate</span></span> | <span data-ttu-id="4cb45-175">Quiosque</span><span class="sxs-lookup"><span data-stu-id="4cb45-175">Kiosk</span></span> | <span data-ttu-id="4cb45-176">Varejo</span><span class="sxs-lookup"><span data-stu-id="4cb45-176">Retail</span></span> | <span data-ttu-id="4cb45-177">Android</span><span class="sxs-lookup"><span data-stu-id="4cb45-177">Android</span></span> |
| <span data-ttu-id="4cb45-178">BYOD</span><span class="sxs-lookup"><span data-stu-id="4cb45-178">BYOD</span></span> | <span data-ttu-id="4cb45-179">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="4cb45-179">Information worker</span></span> | <span data-ttu-id="4cb45-180">Marketing, Vendas</span><span class="sxs-lookup"><span data-stu-id="4cb45-180">Marketing, Sales</span></span> | <span data-ttu-id="4cb45-181">iOS</span><span class="sxs-lookup"><span data-stu-id="4cb45-181">iOS</span></span> |                                                           
| <span data-ttu-id="4cb45-182">BYOD</span><span class="sxs-lookup"><span data-stu-id="4cb45-182">BYOD</span></span> | <span data-ttu-id="4cb45-183">Executivos</span><span class="sxs-lookup"><span data-stu-id="4cb45-183">Executives</span></span> | <span data-ttu-id="4cb45-184">Marketing, Vendas</span><span class="sxs-lookup"><span data-stu-id="4cb45-184">Marketing, Sales</span></span> | <span data-ttu-id="4cb45-185">iOS</span><span class="sxs-lookup"><span data-stu-id="4cb45-185">iOS</span></span> |

## <span data-ttu-id="4cb45-186">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4cb45-186">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="4cb45-187">A próxima seção fornece diretrizes sobre [como identificar os requisitos do Intune para cada cenário de caso de uso](planning-guide-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cb45-187">The next section provides guidance on [how to identify the Intune requirements for each use case scenario](planning-guide-requirements.md).</span></span>
