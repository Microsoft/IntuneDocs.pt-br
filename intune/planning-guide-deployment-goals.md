---
title: "Determinar as metas, os objetivos e os desafios de implantação"
description: "Este artigo ajuda a determinar as metas, os objetivos e os desafios de implantação para uma implementação somente na nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ce26c68916867929e7e1fb17e25bc1a4d9c3beab
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="9764d-103">Determinar as metas, os objetivos e os desafios de implantação</span><span class="sxs-lookup"><span data-stu-id="9764d-103">Determine deployment goals, objectives, and challenges</span></span>
<a id="determine-deployment-goals-objectives-and-challenges" class="xliff"></a>

<span data-ttu-id="9764d-104">Ter um bom plano de implantação começa primeiro com a identificação das metas e dos objetivos de implantação de sua organização, juntamente com os desafios potenciais.</span><span class="sxs-lookup"><span data-stu-id="9764d-104">Having a good deployment plan begins with first identifying your organization’s deployment goals and objectives, along with potential challenges.</span></span> <span data-ttu-id="9764d-105">Vamos discutir cada área mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="9764d-105">Let’s discuss each area in more detail.</span></span>

## <span data-ttu-id="9764d-106">Metas de implantação</span><span class="sxs-lookup"><span data-stu-id="9764d-106">Deployment goals</span></span>
<a id="deployment-goals" class="xliff"></a>

<span data-ttu-id="9764d-107">Metas de implantação são realizações a longo prazo que você pretende obter ao implantar o Intune em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9764d-107">Deployment goals are the long-term achievements you intend to gain by deploying Intune in your organization.</span></span> <span data-ttu-id="9764d-108">Veja abaixo uma lista de alguns exemplos dessas metas, junto com a descrição e o valor comercial de cada um.</span><span class="sxs-lookup"><span data-stu-id="9764d-108">Listed below are some examples of such goals along with the description and business value for each.</span></span>

-   <span data-ttu-id="9764d-109">**Ser integrado com o Office 365 e dar suporte ao uso de aplicativos móveis do Office**</span><span class="sxs-lookup"><span data-stu-id="9764d-109">**Integrate with Office 365 and support the use of Office mobile apps**</span></span>

    -   <span data-ttu-id="9764d-110">**Descrição:** fornecer integração total com o Office 365 e o uso de aplicativos móveis do Office com proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9764d-110">**Description:** Provide tight integration with Office 365 and the use of Office mobile applications with application protection.</span></span>

    -   <span data-ttu-id="9764d-111">**Valor de negócios:** experiência do usuário segura e aprimorada, permitindo que os usuários usem seus aplicativos preferenciais e aqueles com os quais estão familiarizados.</span><span class="sxs-lookup"><span data-stu-id="9764d-111">**Business value:** Secure and improved user experience by allowing users to use apps they are familiar with and prefer.</span></span>

-   <span data-ttu-id="9764d-112">**Habilitar o acesso a serviços corporativos internos em dispositivos móveis**</span><span class="sxs-lookup"><span data-stu-id="9764d-112">**Enable access to internal corporate services on mobile devices**</span></span>

    -   <span data-ttu-id="9764d-113">**Descrição:** permitir que os funcionários sejam produtivos onde quer que precisem trabalhar e com qualquer dispositivo que seja mais apropriado para eles.</span><span class="sxs-lookup"><span data-stu-id="9764d-113">**Description:** Enable employees to be productive wherever they need to work from, and with whichever device is most appropriate for them.</span></span> <span data-ttu-id="9764d-114">Esse projeto deve buscar permitir a produtividade móvel e o acesso a dados corporativos de maneira segura.</span><span class="sxs-lookup"><span data-stu-id="9764d-114">This project should look to enable mobile productivity and access to corporate data in a safe manner.</span></span>

    -   <span data-ttu-id="9764d-115">**Valor comercial:** permitir que os funcionários sejam ágeis e trabalhem onde quer que precisem, além de permitir que a empresa seja mais competitiva e forneça um ambiente de trabalho mais gratificante.</span><span class="sxs-lookup"><span data-stu-id="9764d-115">**Business value:** Enabling employees to be agile and work from where they need allows the business to be more competitive and to provide a more rewarding working environment.</span></span>

-   <span data-ttu-id="9764d-116">**Fornecer proteção de dados em dispositivos móveis**</span><span class="sxs-lookup"><span data-stu-id="9764d-116">**Provide data protection on mobile devices**</span></span>

    -   <span data-ttu-id="9764d-117">**Descrição:** o local em que os dados são armazenados em um dispositivo móvel deve ser protegido contra perda ou compartilhamento acidental e mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="9764d-117">**Description:** When data is stored on a mobile device, it should be protected from malicious and accidental loss or sharing.</span></span>

    -   <span data-ttu-id="9764d-118">**Valor de negócios:** a proteção de dados é essencial para garantir que permaneçamos competitivos e tratemos nossos clientes e seus dados com o máximo cuidado.</span><span class="sxs-lookup"><span data-stu-id="9764d-118">**Business value:** Data protection is vital to ensure that we remain competitive, and that we treat our clients and their data with the utmost diligence.</span></span>

-   <span data-ttu-id="9764d-119">**Reduzir os custos**</span><span class="sxs-lookup"><span data-stu-id="9764d-119">**Reduce costs**</span></span>

    -   <span data-ttu-id="9764d-120">**Descrição:** quando possível, o projeto reduz os custos operacionais e de implantação.</span><span class="sxs-lookup"><span data-stu-id="9764d-120">**Description:** When possible, the project reduces deployment and operating costs.</span></span>

    -    <span data-ttu-id="9764d-121">**Valor de negócios:** o uso eficiente de recursos permite que a empresa invista em outras áreas, tenha uma competitividade mais efetiva e ofereça um melhor serviço aos clientes.</span><span class="sxs-lookup"><span data-stu-id="9764d-121">**Business value:** The efficient use of resources enables the business to invest in other areas, compete more effectively, and provide better service to clients.</span></span>

## <span data-ttu-id="9764d-122">Objetivos de implantação</span><span class="sxs-lookup"><span data-stu-id="9764d-122">Deployment objectives</span></span>
<a id="deployment-objectives" class="xliff"></a>

<span data-ttu-id="9764d-123">Objetivos de implantação são as medidas que sua organização pode tomar para alcançar suas metas de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="9764d-123">Deployment objectives are the actions your organization can take to reach its Intune deployment goals.</span></span> <span data-ttu-id="9764d-124">Veja abaixo uma lista de alguns exemplos de objetivos de implantação e como cada um deles será alcançado.</span><span class="sxs-lookup"><span data-stu-id="9764d-124">Below are listed some examples of deployment objectives, and how each would be accomplished.</span></span>

-   <span data-ttu-id="9764d-125">**Reduzir o número de soluções de gerenciamento de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="9764d-125">**Reduce the number of device management solutions**</span></span>

    -   <span data-ttu-id="9764d-126">**Implementação:** consolidar em uma única solução de gerenciamento de dispositivo móvel: Microsoft Intune para a proteção de dados corporativos de aplicativos e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9764d-126">**Implementation:** Consolidate to a single mobile device management solution: Microsoft Intune for corporate data protection of apps and devices.</span></span>

-   <span data-ttu-id="9764d-127">**Fornecer acesso seguro ao Exchange e ao SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="9764d-127">**Provide secure access to Exchange and SharePoint Online**</span></span>

    -   <span data-ttu-id="9764d-128">**Implementação:** aplicar o acesso condicional para o Exchange e SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="9764d-128">**Implementation:** Apply conditional access for Exchange and SharePoint Online.</span></span>

-   <span data-ttu-id="9764d-129">**Impedir que dados corporativos sejam armazenados ou encaminhados para serviços não corporativos no dispositivo móvel**</span><span class="sxs-lookup"><span data-stu-id="9764d-129">**Prevent corporate data from being stored or forwarded to non-corporate services on the mobile device**</span></span>

    -   <span data-ttu-id="9764d-130">**Implementação:** aplicar políticas de Proteção de Aplicativo do Intune a aplicativos do Microsoft Office e de linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="9764d-130">**Implementation:** Apply Intune app protection policies for Microsoft Office and line-of-business apps.</span></span>

-   <span data-ttu-id="9764d-131">**Fornecer a capacidade de apagar dados corporativos do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="9764d-131">**Provide capability to wipe corporate data from the device**</span></span>

    -   <span data-ttu-id="9764d-132">**Implementação:** registrar dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="9764d-132">**Implementation:** Enroll devices into Intune.</span></span> <span data-ttu-id="9764d-133">Isso fornece a capacidade de realizar um apagamento remoto de dados e recursos corporativos quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="9764d-133">This gives you the capability to perform a remote wipe of corporate data and resources when appropriate.</span></span>

## <span data-ttu-id="9764d-134">Desafios de implantação</span><span class="sxs-lookup"><span data-stu-id="9764d-134">Deployment challenges</span></span>
<a id="deployment-challenges" class="xliff"></a>

<span data-ttu-id="9764d-135">Desafios de implantação são problemas prioritários de uma organização e que podem ter um impacto negativo na implantação.</span><span class="sxs-lookup"><span data-stu-id="9764d-135">Deployment challenges are issues that are top of mind for an organization and that may have a negative impact on deployment.</span></span> <span data-ttu-id="9764d-136">Às vezes, eles estão relacionados a problemas que já ocorreram em projetos anteriores e que você gostaria de evitar ou a novos problemas relacionados ao esforço de implantação atual.</span><span class="sxs-lookup"><span data-stu-id="9764d-136">Sometimes they are related to past issues from previous projects that you would like to avoid or new issues related to the current deployment effort.</span></span> <span data-ttu-id="9764d-137">Veja abaixo uma lista de alguns exemplos de desafios de implantação do Intune, juntamente com as possíveis mitigações.</span><span class="sxs-lookup"><span data-stu-id="9764d-137">Listed below are some examples of Intune deployment challenges along with potential mitigations.</span></span>

-   <span data-ttu-id="9764d-138">A preparação de suporte e a experiência do usuário final não estão incluídos em um escopo do projeto inicial.</span><span class="sxs-lookup"><span data-stu-id="9764d-138">Support readiness and end-user experience are not included in an initial project scope.</span></span> <span data-ttu-id="9764d-139">Isso leva à adoção insatisfatória do usuário final e a desafios para sua organização de suporte.</span><span class="sxs-lookup"><span data-stu-id="9764d-139">This leads to poor end-user adoption and challenges for your support organization.</span></span>

    -   <span data-ttu-id="9764d-140">**Mitigação:** incorporar o treinamento de suporte.</span><span class="sxs-lookup"><span data-stu-id="9764d-140">**Mitigation:** Incorporate support training.</span></span> <span data-ttu-id="9764d-141">Valide a experiência do usuário final com as métricas de sucesso em seu plano de implantação.</span><span class="sxs-lookup"><span data-stu-id="9764d-141">Validate the end-user experience with success metrics in your deployment plan.</span></span>

-   <span data-ttu-id="9764d-142">A ausência de metas bem definidas e métricas de sucesso leva a resultados intangíveis.</span><span class="sxs-lookup"><span data-stu-id="9764d-142">Lack of clearly defined goals and success metrics leads to intangible results.</span></span> <span data-ttu-id="9764d-143">Ela também poderá mudar sua organização para o modo reativo quando surgirem problemas.</span><span class="sxs-lookup"><span data-stu-id="9764d-143">It may also shift your organization into reactive mode when issues arise.</span></span>

    -   <span data-ttu-id="9764d-144">**Mitigação:** defina as metas e métricas de sucesso no início do escopo do projeto e use esses pontos de dados para desenvolver as outras fases de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9764d-144">**Mitigation:** Define your goals and success metrics early in your project scope, and use these data points to flesh out your other rollout phases.</span></span> <span data-ttu-id="9764d-145">Garanta que as metas são SMART (Específicas, Mensuráveis, Atingíveis, Realistas e Oportunas).</span><span class="sxs-lookup"><span data-stu-id="9764d-145">Make sure goals are SMART (Specific, Measurable, Attainable, Realistic, and Timely).</span></span> <span data-ttu-id="9764d-146">Planeje uma avaliação em relação às metas em cada fase e garanta que o projeto de distribuição permanece no controle.</span><span class="sxs-lookup"><span data-stu-id="9764d-146">Plan to measure against your goals at each phase and to ensure your rollout project stays on track.</span></span>

-   <span data-ttu-id="9764d-147">Você não consegue criar, validar nem compartilhar de forma agressiva uma proposta de valor clara que reflete os desejos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="9764d-147">You neglect to create, validate, and aggressively share a clear value proposition that resonates for your organization.</span></span> <span data-ttu-id="9764d-148">Isso geralmente leva à adoção limitada e à falta de ROI (retorno sobre o investimento).</span><span class="sxs-lookup"><span data-stu-id="9764d-148">This often leads to limited adoption and a lack of return on investment (ROI).</span></span>

    -   <span data-ttu-id="9764d-149">**Mitigação:** embora você possa estar animado para começar o projeto agora mesmo, verifique se você definiu com clareza suas metas e seus objetivos.</span><span class="sxs-lookup"><span data-stu-id="9764d-149">**Mitigation:** While you may be excited to jump into your project, ensure you have clearly-defined your goals and objectives.</span></span> <span data-ttu-id="9764d-150">Inclua-os em todas as atividades de treinamento e reconhecimento para ajudar a garantir que os usuários entendem o motivo pelo qual sua organização escolheu o Intune.</span><span class="sxs-lookup"><span data-stu-id="9764d-150">Include these in all awareness and training activities to help ensure users understand why your organization selected Intune.</span></span>

## <span data-ttu-id="9764d-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="9764d-151">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="9764d-152">Agora que você identificou as metas e os objetivos de implantação, bem como seus possíveis desafios, vamos passar para a próxima seção: [Identificar os cenários de caso de uso](planning-guide-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="9764d-152">Now that you have identified your deployment goals, objectives, and potential challenges, let’s move to the next section: [Identify use case scenarios](planning-guide-scenarios.md).</span></span>
