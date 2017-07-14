---
title: "Determinar os requisitos de cenários de caso de uso"
description: "Este artigo ajuda você a determinar os requisitos de cenários de casos de uso e subcasos de uso do Intune para uma implementação somente em nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 032427a9965f368d7be17339e3cbe5b426800347
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2017
---
# <span data-ttu-id="60607-103">Determinar os requisitos de cenários de caso de uso</span><span class="sxs-lookup"><span data-stu-id="60607-103">Determine use-case scenario requirements</span></span>
<a id="determine-use-case-scenario-requirements" class="xliff"></a>

<span data-ttu-id="60607-104">Nesta seção, você determina os requisitos para cada grupo organizacional em cada cenário de caso de uso.</span><span class="sxs-lookup"><span data-stu-id="60607-104">In this section, you determine the requirements for each organizational group within each use-case scenario.</span></span> <span data-ttu-id="60607-105">Esse processo ajuda você a se preparar para as outras áreas de planejamento de implantação do Intune, como arquitetura e design, integração e distribuição.</span><span class="sxs-lookup"><span data-stu-id="60607-105">This process helps you prepare for the other Intune deployment planning areas like architecture and design, onboarding, and rollout.</span></span> <span data-ttu-id="60607-106">Ele também pode ajudar a identificar possíveis falhas e os desafios relacionados ao seu projeto de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="60607-106">It can also help identify potential gaps and challenges related to your Intune deployment project.</span></span>

<span data-ttu-id="60607-107">Talvez você tenha diferentes conjuntos de requisitos para cada um dos cenários de casos de uso e subcasos de uso e seus grupos organizacionais e as plataformas de dispositivos móveis associadas.</span><span class="sxs-lookup"><span data-stu-id="60607-107">You might have different sets of requirements for each of your use-case and sub-use-case scenarios, and their associated organizational groups and mobile device platforms.</span></span> <span data-ttu-id="60607-108">Por exemplo, seus requisitos de cenários de casos de uso corporativos podem exigir que os dispositivos se registrem no Intune com um conjunto mais restritivo de configurações de dispositivo, como um PIN de 6 caracteres ou com o backup na nuvem desabilitado.</span><span class="sxs-lookup"><span data-stu-id="60607-108">For example, your corporate use-case scenario requirements might require devices to enroll into Intune with a more restrictive set of device settings, like a PIN of 6 characters or disabled cloud backup.</span></span> <span data-ttu-id="60607-109">O cenário de caso de uso BYOD “Traga seu próprio dispositivo” pode ser menos restritivo e permite um PIN de 4 caracteres e o backup na nuvem.</span><span class="sxs-lookup"><span data-stu-id="60607-109">Your "bring your own device" (BYOD) use-case scenario, may be less restrictive and allow a 4-character PIN and cloud backup.</span></span>

<span data-ttu-id="60607-110">Você também pode ter grupos organizacionais para o cenário de caso de uso corporativo que têm diferentes conjuntos de requisitos (por exemplo, configurações de PIN, perfil de Wi-Fi ou VPN, aplicativos implantados).</span><span class="sxs-lookup"><span data-stu-id="60607-110">You may also have organizational groups for the corporate use-case scenario that have different sets of requirements (for example, PIN settings, Wi-Fi or VPN profile, apps deployed).</span></span> <span data-ttu-id="60607-111">Seus requisitos também podem ser determinados pelas funcionalidades da plataforma de dispositivo móvel (por exemplo, leitor de impressão digital, perfil de email).</span><span class="sxs-lookup"><span data-stu-id="60607-111">Your requirements may also be determined by the capabilities of the mobile device platform (for example, finger print reader, email profile).</span></span>

<span data-ttu-id="60607-112">Estes são alguns exemplos de requisitos de casos de uso de uma organização, mostrando diferentes conjuntos de requisitos para cada cenário de caso de uso e subcaso de uso, grupo organizacional e plataforma de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="60607-112">Here are a few examples of an organization’s use-case requirements showing different sets of requirements for each use-case and sub-use-case scenario, organizational group, and mobile device platform.</span></span> <span data-ttu-id="60607-113">Também é possível usar a seguinte tabela para inserir os requisitos de caso de uso de sua organização:</span><span class="sxs-lookup"><span data-stu-id="60607-113">You can also use the following table to enter your organization’s use-case requirements:</span></span>

| <span data-ttu-id="60607-114">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="60607-114">**Use cases**</span></span> | <span data-ttu-id="60607-115">**Subcasos de uso**</span><span class="sxs-lookup"><span data-stu-id="60607-115">**Sub-use cases**</span></span> | <span data-ttu-id="60607-116">**Grupos**</span><span class="sxs-lookup"><span data-stu-id="60607-116">**Groups**</span></span> | <span data-ttu-id="60607-117">**Plataformas de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="60607-117">**Device platforms**</span></span> | <span data-ttu-id="60607-118">**Requirements**</span><span class="sxs-lookup"><span data-stu-id="60607-118">**Requirements**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="60607-119">Corporativo</span><span class="sxs-lookup"><span data-stu-id="60607-119">Corporate</span></span> | <span data-ttu-id="60607-120">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="60607-120">Information worker</span></span> | <span data-ttu-id="60607-121">RH, Finanças</span><span class="sxs-lookup"><span data-stu-id="60607-121">HR, Finance</span></span> | <span data-ttu-id="60607-122">iOS</span><span class="sxs-lookup"><span data-stu-id="60607-122">iOS</span></span> | <span data-ttu-id="60607-123">Email seguro, configurações de dispositivo, perfis, aplicativos</span><span class="sxs-lookup"><span data-stu-id="60607-123">Secure e-mail, device settings, profiles, apps</span></span> |                                                          
| <span data-ttu-id="60607-124">Corporativo</span><span class="sxs-lookup"><span data-stu-id="60607-124">Corporate</span></span> | <span data-ttu-id="60607-125">Executivos</span><span class="sxs-lookup"><span data-stu-id="60607-125">Executives</span></span> | <span data-ttu-id="60607-126">RH, Finanças</span><span class="sxs-lookup"><span data-stu-id="60607-126">HR, Finance</span></span> | <span data-ttu-id="60607-127">iOS</span><span class="sxs-lookup"><span data-stu-id="60607-127">iOS</span></span> | <span data-ttu-id="60607-128">Email seguro, configurações de dispositivo, perfis, aplicativos</span><span class="sxs-lookup"><span data-stu-id="60607-128">Secure e-mail, device settings, profiles, apps</span></span> |                                                         
| <span data-ttu-id="60607-129">Corporativo</span><span class="sxs-lookup"><span data-stu-id="60607-129">Corporate</span></span> | <span data-ttu-id="60607-130">Quiosque</span><span class="sxs-lookup"><span data-stu-id="60607-130">Kiosk</span></span> | <span data-ttu-id="60607-131">Varejo</span><span class="sxs-lookup"><span data-stu-id="60607-131">Retail</span></span> | <span data-ttu-id="60607-132">Android</span><span class="sxs-lookup"><span data-stu-id="60607-132">Android</span></span> | <span data-ttu-id="60607-133">Configurações de dispositivo, perfis, aplicativos</span><span class="sxs-lookup"><span data-stu-id="60607-133">Device settings, profiles, apps</span></span> |
| <span data-ttu-id="60607-134">BYOD</span><span class="sxs-lookup"><span data-stu-id="60607-134">BYOD</span></span> | <span data-ttu-id="60607-135">Operador de informações</span><span class="sxs-lookup"><span data-stu-id="60607-135">Information worker</span></span> | <span data-ttu-id="60607-136">Marketing, Vendas</span><span class="sxs-lookup"><span data-stu-id="60607-136">Marketing, Sales</span></span> | <span data-ttu-id="60607-137">iOS</span><span class="sxs-lookup"><span data-stu-id="60607-137">iOS</span></span> | <span data-ttu-id="60607-138">Email seguro, configurações de dispositivo, perfis, aplicativos</span><span class="sxs-lookup"><span data-stu-id="60607-138">Secure e-mail, device settings, profiles, apps</span></span> |                                                         
| <span data-ttu-id="60607-139">BYOD</span><span class="sxs-lookup"><span data-stu-id="60607-139">BYOD</span></span> | <span data-ttu-id="60607-140">Executivos</span><span class="sxs-lookup"><span data-stu-id="60607-140">Executives</span></span> | <span data-ttu-id="60607-141">Marketing, Vendas</span><span class="sxs-lookup"><span data-stu-id="60607-141">Marketing, Sales</span></span> | <span data-ttu-id="60607-142">iOS</span><span class="sxs-lookup"><span data-stu-id="60607-142">iOS</span></span> | <span data-ttu-id="60607-143">Email seguro, configurações de dispositivo, perfis, aplicativos</span><span class="sxs-lookup"><span data-stu-id="60607-143">Secure e-mail, device settings, profiles, apps</span></span> |

<span data-ttu-id="60607-144">[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para inserir os requisitos de casos de uso e subcasos de uso de sua organização.</span><span class="sxs-lookup"><span data-stu-id="60607-144">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to enter your organization’s use-case and sub-use-case requirements.</span></span>


## <span data-ttu-id="60607-145">Exemplos de requisitos</span><span class="sxs-lookup"><span data-stu-id="60607-145">Examples of requirements</span></span>
<a id="examples-of-requirements" class="xliff"></a>

<span data-ttu-id="60607-146">Estes são mais alguns exemplos que podem ser usados na coluna “Requisitos”:</span><span class="sxs-lookup"><span data-stu-id="60607-146">Here are a few more examples that can be used in the "Requirements" column:</span></span>

- <span data-ttu-id="60607-147">**Email seguro**</span><span class="sxs-lookup"><span data-stu-id="60607-147">**Secure e-mail**</span></span>
    - <span data-ttu-id="60607-148">Acesso condicional para o Exchange Online/Local</span><span class="sxs-lookup"><span data-stu-id="60607-148">Conditional access for Exchange Online / on-premises</span></span>
    - <span data-ttu-id="60607-149">Políticas de proteção do aplicativo do Outlook</span><span class="sxs-lookup"><span data-stu-id="60607-149">Outlook app protection policies</span></span>

- <span data-ttu-id="60607-150">**Configurações do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="60607-150">**Device settings**</span></span>
    - <span data-ttu-id="60607-151">Configuração de PIN com quatro, seis caracteres</span><span class="sxs-lookup"><span data-stu-id="60607-151">PIN setting with four, six characters</span></span>
    - <span data-ttu-id="60607-152">Restringir o backup na nuvem</span><span class="sxs-lookup"><span data-stu-id="60607-152">Restrict cloud backup</span></span>

- <span data-ttu-id="60607-153">**Perfis**</span><span class="sxs-lookup"><span data-stu-id="60607-153">**Profiles**</span></span>
    - <span data-ttu-id="60607-154">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="60607-154">Wi-Fi</span></span>
    - <span data-ttu-id="60607-155">VPN</span><span class="sxs-lookup"><span data-stu-id="60607-155">VPN</span></span>
    - <span data-ttu-id="60607-156">Email (Windows 10 Mobile)</span><span class="sxs-lookup"><span data-stu-id="60607-156">Email (Windows 10 mobile)</span></span>

- <span data-ttu-id="60607-157">**Apps**</span><span class="sxs-lookup"><span data-stu-id="60607-157">**Apps**</span></span>
    - <span data-ttu-id="60607-158">Office 365 com políticas de proteção do aplicativo</span><span class="sxs-lookup"><span data-stu-id="60607-158">Office 365 with app protection policies</span></span>
    - <span data-ttu-id="60607-159">LOB (linha de negócios) com políticas de proteção do aplicativo</span><span class="sxs-lookup"><span data-stu-id="60607-159">Line of business (LOB) with app protection policies</span></span>

## <span data-ttu-id="60607-160">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="60607-160">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="60607-161">A próxima seção fornece diretrizes sobre [como desenvolver um plano de distribuição do Intune](planning-guide-rollout-plan.md).</span><span class="sxs-lookup"><span data-stu-id="60607-161">The next section provides guidance on [how to develop an Intune rollout plan](planning-guide-rollout-plan.md).</span></span>
