---
title: "Introdução ao planejamento e design do Intune"
description: "Este artigo é uma introdução a todas as seções de planejamento, design e implementação do Intune. Ferramentas para ajudá-lo a determinar as metas, os cenários de casos de uso e requisitos, criar planos de distribuição e comunicação, bem como planos de suporte, teste e validação."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a65efa6e-4a48-47f3-8f6e-34a85ca64ced
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ceee7a766fa8f60b91d3a84b6577223e1bfd652e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="211cc-104">Guia de planejamento de implantação, design e implementação do Intune</span><span class="sxs-lookup"><span data-stu-id="211cc-104">Intune deployment planning, design, and implementation guide</span></span>
<a id="intune-deployment-planning-design-and-implementation-guide" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="211cc-105">Uma implantação bem-sucedida do Intune começa com um bom plano e design.</span><span class="sxs-lookup"><span data-stu-id="211cc-105">A successful Intune deployment starts with having a good plan and design.</span></span> <span data-ttu-id="211cc-106">A finalidade deste guia é orientá-lo durante o processo de desenvolvimento de um plano de implantação, criação de um design, integração do Intune e realização de uma distribuição de produção.</span><span class="sxs-lookup"><span data-stu-id="211cc-106">The purpose of this guide is to step you through the process of developing a deployment plan, creating a design, onboarding Intune, and conducting a production rollout.</span></span>

## <span data-ttu-id="211cc-107">O que está incluído neste guia?</span><span class="sxs-lookup"><span data-stu-id="211cc-107">What’s included in this guide?</span></span>
<a id="whats-included-in-this-guide" class="xliff"></a>

<span data-ttu-id="211cc-108">Este guia inclui as seções que orientarão você pelo processo de ponta a ponta de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="211cc-108">This guide includes sections that will walk you through the end-to-end process of deploying Intune.</span></span> <span data-ttu-id="211cc-109">Comece na Seção 1 para esclarecer as metas, os objetivos e os desafios.</span><span class="sxs-lookup"><span data-stu-id="211cc-109">Start with Section 1 to clarify your goals, objectives, and challenges.</span></span> <span data-ttu-id="211cc-110">Depois, vá para as Seções 2 a 7 na ordem que melhor atenda às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="211cc-110">Then move on to Sections 2 – 7 in the order that best meets your needs.</span></span> <span data-ttu-id="211cc-111">Você não precisa percorrer essas seções na sequência; é possível conclui-las em paralelo.</span><span class="sxs-lookup"><span data-stu-id="211cc-111">You don't need to work through these sections sequentially; you can complete them in parallel.</span></span>

-   [<span data-ttu-id="211cc-112">Seção 1: Determinar as metas, os objetivos e os desafios de implantação</span><span class="sxs-lookup"><span data-stu-id="211cc-112">Section 1: Determine deployment goals, objectives, and challenges</span></span>](planning-guide-deployment-goals.md)

-   [<span data-ttu-id="211cc-113">Seção 2: Identificar os cenários de caso de uso</span><span class="sxs-lookup"><span data-stu-id="211cc-113">Section 2: Identify use case scenarios</span></span>](planning-guide-scenarios.md)

-   [<span data-ttu-id="211cc-114">Seção 3: Determinar os requisitos de caso de uso</span><span class="sxs-lookup"><span data-stu-id="211cc-114">Section 3: Determine use case requirements</span></span>](planning-guide-requirements.md)

-   [<span data-ttu-id="211cc-115">Seção 4: Desenvolver um plano de distribuição</span><span class="sxs-lookup"><span data-stu-id="211cc-115">Section 4: Develop a rollout plan</span></span>](planning-guide-rollout-plan.md)

-   [<span data-ttu-id="211cc-116">Seção 5: Desenvolver um plano de comunicação pra a distribuição</span><span class="sxs-lookup"><span data-stu-id="211cc-116">Section 5: Develop a rollout communication plan</span></span>](planning-guide-communication-plan.md)

-   [<span data-ttu-id="211cc-117">Seção 6: Desenvolver um plano de suporte</span><span class="sxs-lookup"><span data-stu-id="211cc-117">Section 6: Develop a support plan</span></span>](planning-guide-support-plan.md)

-   [<span data-ttu-id="211cc-118">Seção 7: Criar um design do Intune</span><span class="sxs-lookup"><span data-stu-id="211cc-118">Section 7: Create an Intune design</span></span>](planning-guide-design.md)

-   [<span data-ttu-id="211cc-119">Seção 8: Implementação do Intune</span><span class="sxs-lookup"><span data-stu-id="211cc-119">Section 8: Intune implementation</span></span>](planning-guide-onboarding.md)

-   [<span data-ttu-id="211cc-120">Seção 9: Teste e validação</span><span class="sxs-lookup"><span data-stu-id="211cc-120">Section 9: Testing and validation</span></span>](planning-guide-test-validation.md)

<span data-ttu-id="211cc-121">Este guia também fornece outras informações técnicas e modelos de tabela que podem ser usados para ajudá-lo com o processo de planejamento de implantação, design e implementação do Intune.</span><span class="sxs-lookup"><span data-stu-id="211cc-121">This guide also provides additional technical information and table templates that can be used to assist you with the Intune deployment planning, design, and implementation process.</span></span>

-   [<span data-ttu-id="211cc-122">Recursos adicionais: Links e modelos de tabela</span><span class="sxs-lookup"><span data-stu-id="211cc-122">Additional resources: Links and table templates</span></span>](planning-guide-resources.md)

## <span data-ttu-id="211cc-123">Suposições</span><span class="sxs-lookup"><span data-stu-id="211cc-123">Assumptions</span></span>
<a id="assumptions" class="xliff"></a>

-   <span data-ttu-id="211cc-124">Você já avaliou o Intune em um ambiente de POC (prova de conceito) e decidiu usá-lo como a solução de gerenciamento de dispositivo móvel em sua organização.</span><span class="sxs-lookup"><span data-stu-id="211cc-124">You've already evaluated Intune in a proof of concept (PoC) environment, and have decided to use it as the mobile device management solution in your organization.</span></span>

-   <span data-ttu-id="211cc-125">Você já está familiarizado com o Intune e seus recursos.</span><span class="sxs-lookup"><span data-stu-id="211cc-125">You're already familiar with Intune and its features.</span></span>

## <span data-ttu-id="211cc-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="211cc-126">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="211cc-127">Vamos começar com a primeira seção: [Determinar as metas, os objetivos e os desafios de implantação](planning-guide-deployment-goals.md).</span><span class="sxs-lookup"><span data-stu-id="211cc-127">Let’s get started with the first section: [Determine deployment goals, objectives, and challenges](planning-guide-deployment-goals.md).</span></span>
