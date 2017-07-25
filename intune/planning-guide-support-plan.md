---
title: Desenvolver um plano de suporte
description: "Este artigo ajuda a desenvolver um plano de suporte do Intune para uma implantação do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b9428769-4333-4778-b677-f23dea1f74da
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 87ae4378be21c81b675e847b907aca6368070ea3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="db2d2-103">Desenvolver um plano de suporte</span><span class="sxs-lookup"><span data-stu-id="db2d2-103">Develop a support plan</span></span>
<a id="develop-a-support-plan" class="xliff"></a>

<span data-ttu-id="db2d2-104">Ter um plano de suporte do Intune pode ajudar a identificar e resolver problemas relacionados ao Intune com mais eficácia.</span><span class="sxs-lookup"><span data-stu-id="db2d2-104">Having an Intune support plan can help you identify and resolve Intune related issues more effectively.</span></span> <span data-ttu-id="db2d2-105">Isso, por sua vez, melhora a experiência geral dos usuários do Intune.</span><span class="sxs-lookup"><span data-stu-id="db2d2-105">This, in turn, improves your users' overall Intune experience.</span></span> <span data-ttu-id="db2d2-106">Estas são algumas perguntas a serem consideradas ao desenvolver o plano de suporte do Intune:</span><span class="sxs-lookup"><span data-stu-id="db2d2-106">Here are some questions to consider as you develop your Intune support plan:</span></span>

-   <span data-ttu-id="db2d2-107">Quais equipes serão responsáveis por fornecer suporte do Intune?</span><span class="sxs-lookup"><span data-stu-id="db2d2-107">Which teams will be responsible for providing Intune support?</span></span>

-   <span data-ttu-id="db2d2-108">Qual processo será usado para fornecer suporte do Intune?</span><span class="sxs-lookup"><span data-stu-id="db2d2-108">What process will be used to provide Intune support?</span></span>

-   <span data-ttu-id="db2d2-109">Como você planeja fornecer treinamento de suporte do Intune?</span><span class="sxs-lookup"><span data-stu-id="db2d2-109">How you plan to provide Intune support training?</span></span>

-   <span data-ttu-id="db2d2-110">Quais são as oportunidades para envolver a equipe de suporte no início do processo de implantação do Intune?</span><span class="sxs-lookup"><span data-stu-id="db2d2-110">What are the opportunities to involve the support team early in the Intune deployment process?</span></span>

<span data-ttu-id="db2d2-111">Vamos examinar cada área mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="db2d2-111">Let’s review each area in more detail.</span></span>

## <span data-ttu-id="db2d2-112">Quais equipes são responsáveis por fornecer suporte?</span><span class="sxs-lookup"><span data-stu-id="db2d2-112">Which teams are responsible for providing support?</span></span>
<a id="which-teams-are-responsible-for-providing-support" class="xliff"></a>

<span data-ttu-id="db2d2-113">As organizações podem ter diferentes camadas ou níveis (1-3) de suporte.</span><span class="sxs-lookup"><span data-stu-id="db2d2-113">Organizations may have different tiers or levels (1-3) of support.</span></span> <span data-ttu-id="db2d2-114">Por exemplo, as camadas 1 e 2 podem fazer parte da equipe de suporte, enquanto a camada 3 inclui membros da equipe de MDM responsável pela implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="db2d2-114">For example, tier 1 and 2 may be part of the support team, and tier 3 include members of the MDM team responsible for the deployment of Intune.</span></span>

<span data-ttu-id="db2d2-115">A camada 1 costuma ser o primeiro nível de suporte e é, geralmente, a primeira camada a ser contatada pelo usuário para solicitações de suporte.</span><span class="sxs-lookup"><span data-stu-id="db2d2-115">Tier 1 is normally the first level of support and typically the first tier to be contacted by the user for support requests.</span></span> <span data-ttu-id="db2d2-116">Se a camada 1 não puder resolver o problema do usuário final, ele será encaminhado para a camada 2.</span><span class="sxs-lookup"><span data-stu-id="db2d2-116">If tier 1 is unable to resolve the end user’s issue, they escalate it to tier 2.</span></span> <span data-ttu-id="db2d2-117">A camada 2 escalará para a camada 3 se necessário.</span><span class="sxs-lookup"><span data-stu-id="db2d2-117">Tier 2 escalates it to tier 3 if needed.</span></span> <span data-ttu-id="db2d2-118">Além disso, o Suporte da Microsoft pode ser considerado como a camada 4.</span><span class="sxs-lookup"><span data-stu-id="db2d2-118">In addition, Microsoft support may be considered as tier 4.</span></span>

<span data-ttu-id="db2d2-119">Saiba mais sobre o [suporte do Intune](/intune/get-support).</span><span class="sxs-lookup"><span data-stu-id="db2d2-119">Learn more about [Intune support](/intune/get-support).</span></span>

## <span data-ttu-id="db2d2-120">O que é o processo de suporte?</span><span class="sxs-lookup"><span data-stu-id="db2d2-120">What is the support process?</span></span>
<a id="what-is-the-support-process" class="xliff"></a>

<span data-ttu-id="db2d2-121">Para as fases iniciais de distribuição de produção, todas as três camadas podem participar de uma teleconferência ou chamada por Skype.</span><span class="sxs-lookup"><span data-stu-id="db2d2-121">For the initial production rollout phases, you could have all three tiers participating in a bridge or Skype call.</span></span> <span data-ttu-id="db2d2-122">Aqui temos um exemplo de como uma organização poderá implementar seus fluxos de trabalho de suporte de TI ou assistência técnica:</span><span class="sxs-lookup"><span data-stu-id="db2d2-122">Here’s one example of how an organization could implement their IT support or helpdesk work-flows:</span></span>

1.  <span data-ttu-id="db2d2-123">O usuário final contata a camada 1 de suporte de TI ou assistência técnica com um problema de registro.</span><span class="sxs-lookup"><span data-stu-id="db2d2-123">End-user contacts IT support or helpdesk tier 1 with an enrollment issue.</span></span>

2.  <span data-ttu-id="db2d2-124">A camada 1 de suporte de TI ou assistência técnica não consegue determinar a causa raiz e escala o problema para a camada 2.</span><span class="sxs-lookup"><span data-stu-id="db2d2-124">IT support or helpdesk tier 1 is unable to determine the root cause and escalates to tier 2.</span></span>

3.  <span data-ttu-id="db2d2-125">A camada 2 de suporte de TI ou assistência técnica investiga o problema, mas não consegue resolvê-lo e o escala para a camada 3, fornecendo mais informações para ajudar com a investigação.</span><span class="sxs-lookup"><span data-stu-id="db2d2-125">IT support or helpdesk tier 2 investigates, but is unable to resolve the issue and escalates to tier 3, providing additional information to assist with the investigation.</span></span>

4.  <span data-ttu-id="db2d2-126">A camada 3 de suporte técnico ou de TI investiga com mais detalhes, determina a causa raiz e comunica a resolução para as camadas 1 e 2.</span><span class="sxs-lookup"><span data-stu-id="db2d2-126">IT support or helpdesk tier 3 investigates further, determines the root cause, and communicates the resolution to tier 2 and 1.</span></span>

5.  <span data-ttu-id="db2d2-127">Em seguida, a camada 1 de suporte de TI/assistência técnica contata o cliente e resolve o problema.</span><span class="sxs-lookup"><span data-stu-id="db2d2-127">IT support/helpdesk tier 1 then contacts the customer and resolves their issue.</span></span>

<span data-ttu-id="db2d2-128">Esse tipo de abordagem, especialmente nos estágios iniciais da distribuição do Intune, traz várias vantagens, incluindo:</span><span class="sxs-lookup"><span data-stu-id="db2d2-128">This type of approach, especially in early stages of the Intune rollout, adds many benefits, including:</span></span>

-   <span data-ttu-id="db2d2-129">Auxiliar no aprendizado e incremento da tecnologia.</span><span class="sxs-lookup"><span data-stu-id="db2d2-129">Assisting in technology learning and ramp up.</span></span>

-   <span data-ttu-id="db2d2-130">Identificar rapidamente os problemas e a resolução.</span><span class="sxs-lookup"><span data-stu-id="db2d2-130">Quickly identifying issues and resolution.</span></span>

-   <span data-ttu-id="db2d2-131">Melhorar a experiência geral do usuário.</span><span class="sxs-lookup"><span data-stu-id="db2d2-131">Improving the overall user experience.</span></span>

## <span data-ttu-id="db2d2-132">Como você planeja fornecer treinamento de suporte do Intune?</span><span class="sxs-lookup"><span data-stu-id="db2d2-132">How you plan to provide Intune support training?</span></span>
<a id="how-you-plan-to-provide-intune-support-training" class="xliff"></a>

<span data-ttu-id="db2d2-133">É importante fornecer treinamento técnico do Intune para sua equipe de suporte técnico ou de TI, o qual deve ser de nível adequado e aplicar-se à camada de suporte específica e suas responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="db2d2-133">It’s important to provide Intune technical training for your IT support or helpdesk staff so that the training is at an appropriate level and applies to the specific support tier and their responsibilities.</span></span> <span data-ttu-id="db2d2-134">A equipe de MDM do Intune pode realizar esse treinamento para os líderes de suporte (treinando o treinador) para que eles possam fornecer esse treinamento posteriormente aos membros da sua equipe de suporte.</span><span class="sxs-lookup"><span data-stu-id="db2d2-134">You could have the Intune MDM team conduct this training to the support leads (training the trainer), then have the leads provide this training to their support team members.</span></span> <span data-ttu-id="db2d2-135">Em geral, esse treinamento pode ser fornecido em 2 a 3 horas e inclui palestra e oficinas.</span><span class="sxs-lookup"><span data-stu-id="db2d2-135">This training can typically be provided in 2-3 hours, and it includes lecture and labs.</span></span>

<span data-ttu-id="db2d2-136">Um exemplo de uma agenda de treinamento de suporte do Intune é fornecida abaixo.</span><span class="sxs-lookup"><span data-stu-id="db2d2-136">An example of an Intune support training agenda is provided below.</span></span>

-   <span data-ttu-id="db2d2-137">Análise do plano de suporte do Intune</span><span class="sxs-lookup"><span data-stu-id="db2d2-137">Intune support plan review</span></span>

-   <span data-ttu-id="db2d2-138">Visão geral do Intune</span><span class="sxs-lookup"><span data-stu-id="db2d2-138">Intune overview</span></span>

-   <span data-ttu-id="db2d2-139">Solução de problemas comuns</span><span class="sxs-lookup"><span data-stu-id="db2d2-139">Troubleshooting common issues</span></span>

-   <span data-ttu-id="db2d2-140">Ferramentas e recursos</span><span class="sxs-lookup"><span data-stu-id="db2d2-140">Tools and resources</span></span>

-   <span data-ttu-id="db2d2-141">Perguntas e Respostas</span><span class="sxs-lookup"><span data-stu-id="db2d2-141">Q & A</span></span>

<span data-ttu-id="db2d2-142">A [Documentação do Intune](https://docs.microsoft.com/intune/) fornece uma visão geral do Intune, descrições detalhadas dos recurso e algumas informações de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="db2d2-142">The [Intune documentation](https://docs.microsoft.com/intune/) provides an Intune overview,  detailed feature descriptions, and some troubleshooting information.</span></span> <span data-ttu-id="db2d2-143">O [Fórum do Intune](https://social.technet.microsoft.com/Forums/en-US/home) é um recurso baseado na comunidade para dúvidas e tópicos não abordados na documentação do Intune.</span><span class="sxs-lookup"><span data-stu-id="db2d2-143">The [Intune forum](https://social.technet.microsoft.com/Forums/en-US/home) is a community-based resource for questions and topics not covered in the Intune documentation.</span></span>

## <span data-ttu-id="db2d2-144">Quais são as oportunidades para envolver a equipe de suporte nos estágios iniciais?</span><span class="sxs-lookup"><span data-stu-id="db2d2-144">What opportunities are there to involve the support team earlier?</span></span>
<a id="what-opportunities-are-there-to-involve-the-support-team-earlier" class="xliff"></a>

<span data-ttu-id="db2d2-145">Envolver sua equipe de suporte técnico/de TI nos estágios iniciais dos esforços de planejamento e piloto da implantação do Intune pode melhorar a implantação do Intune e a adoção do usuário final.</span><span class="sxs-lookup"><span data-stu-id="db2d2-145">Involving your IT support/helpdesk staff in early stages of Intune deployment planning and pilot efforts can improve your Intune deployment and end-user adoption.</span></span> <span data-ttu-id="db2d2-146">O envolvimento inicial proporciona à sua equipe de suporte contato com o Intune e experiências valiosas desde o início.</span><span class="sxs-lookup"><span data-stu-id="db2d2-146">Early involvement provides your support staff with exposure to Intune and valuable experience from the beginning.</span></span> <span data-ttu-id="db2d2-147">Isso também ajuda a preparar a equipe de suporte técnico/de TI para dar suporte à distribuição de produção completa da organização.</span><span class="sxs-lookup"><span data-stu-id="db2d2-147">This helps prepare your IT support/helpdesk staff for supporting the organization's full production rollout.</span></span>

## <span data-ttu-id="db2d2-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="db2d2-148">Next step</span></span>
<a id="next-step" class="xliff"></a>

<span data-ttu-id="db2d2-149">A próxima seção fornece diretrizes sobre [como desenvolver o Intune](planning-guide-design.md).</span><span class="sxs-lookup"><span data-stu-id="db2d2-149">The next section provides guidance on [designing Intune](planning-guide-design.md).</span></span>
=======
# Desenvolver um plano de suporte
<a id="develop-a-support-plan" class="xliff"></a>

Ter um plano de suporte do Intune pode ajudar a identificar e resolver problemas relacionados ao Intune com mais eficácia. Isso, por sua vez, melhora a experiência geral dos usuários do Intune. Estas são algumas perguntas a serem consideradas ao desenvolver o plano de suporte do Intune:

-   Quais equipes serão responsáveis por fornecer suporte do Intune?

-   Qual processo será usado para fornecer suporte do Intune?

-   Como você planeja fornecer treinamento de suporte do Intune?

-   Quais são as oportunidades para envolver a equipe de suporte no início do processo de implantação do Intune?

Vamos examinar cada área mais detalhadamente.

## Quais equipes são responsáveis por fornecer suporte?
<a id="which-teams-are-responsible-for-providing-support" class="xliff"></a>

As organizações podem ter diferentes camadas ou níveis (1-3) de suporte. Por exemplo, as camadas 1 e 2 podem fazer parte da equipe de suporte, enquanto a camada 3 inclui membros da equipe de MDM responsável pela implantação do Intune.

A camada 1 costuma ser o primeiro nível de suporte e é, geralmente, a primeira camada a ser contatada pelo usuário para solicitações de suporte. Se a camada 1 não puder resolver o problema do usuário final, ele será encaminhado para a camada 2. A camada 2 escalará para a camada 3 se necessário. Além disso, o Suporte da Microsoft pode ser considerado como a camada 4.

Saiba mais sobre o [suporte do Intune](/intune/get-support).

## O que é o processo de suporte?
<a id="what-is-the-support-process" class="xliff"></a>

Para as fases iniciais de distribuição de produção, todas as três camadas podem participar de uma teleconferência ou chamada por Skype. Aqui temos um exemplo de como uma organização poderá implementar seus fluxos de trabalho de suporte de TI ou assistência técnica:

1.  O usuário final contata a camada 1 de suporte de TI ou assistência técnica com um problema de registro.

2.  A camada 1 de suporte de TI ou assistência técnica não consegue determinar a causa raiz e escala o problema para a camada 2.

3.  A camada 2 de suporte de TI ou assistência técnica investiga o problema, mas não consegue resolvê-lo e o escala para a camada 3, fornecendo mais informações para ajudar com a investigação.

4.  A camada 3 de suporte técnico ou de TI investiga com mais detalhes, determina a causa raiz e comunica a resolução para as camadas 1 e 2.

5.  Em seguida, a camada 1 de suporte de TI/assistência técnica contata o cliente e resolve o problema.

Esse tipo de abordagem, especialmente nos estágios iniciais da distribuição do Intune, traz várias vantagens, incluindo:

-   Auxiliar no aprendizado e incremento da tecnologia.

-   Identificar rapidamente os problemas e a resolução.

-   Melhorar a experiência geral do usuário.

## Como você planeja fornecer treinamento de suporte do Intune?
<a id="how-you-plan-to-provide-intune-support-training" class="xliff"></a>

É importante fornecer treinamento técnico do Intune para sua equipe de suporte técnico ou de TI, o qual deve ser de nível adequado e aplicar-se à camada de suporte específica e suas responsabilidades. A equipe de MDM do Intune pode realizar esse treinamento para os líderes de suporte (treinando o treinador) para que eles possam fornecer esse treinamento posteriormente aos membros da sua equipe de suporte. Em geral, esse treinamento pode ser fornecido em 2 a 3 horas e inclui palestra e oficinas.

Um exemplo de uma agenda de treinamento de suporte do Intune é fornecida abaixo.

-   Análise do plano de suporte do Intune

-   Visão geral do Intune

-   Solução de problemas comuns

-   Ferramentas e recursos

-   Perguntas e Respostas

A [Documentação do Intune](https://docs.microsoft.com/intune/) fornece uma visão geral do Intune, descrições detalhadas dos recurso e algumas informações de solução de problemas. O [Fórum do Intune](https://social.technet.microsoft.com/Forums/en-US/home) é um recurso baseado na comunidade para dúvidas e tópicos não abordados na documentação do Intune.

## Quais são as oportunidades para envolver a equipe de suporte nos estágios iniciais?
<a id="what-opportunities-are-there-to-involve-the-support-team-earlier" class="xliff"></a>

Envolver sua equipe de suporte técnico/de TI nos estágios iniciais dos esforços de planejamento e piloto da implantação do Intune pode melhorar a implantação do Intune e a adoção do usuário final. O envolvimento inicial proporciona à sua equipe de suporte contato com o Intune e experiências valiosas desde o início. Isso também ajuda a preparar a equipe de suporte técnico/de TI para dar suporte à distribuição de produção completa da organização.

## Próximas etapas
<a id="next-step" class="xliff"></a>

A próxima seção fornece diretrizes sobre [como desenvolver o Intune](planning-guide-design.md).
>>>>>>> live
