---
title: "Iniciar uma campanha de migração do Intune"
description: "A finalidade deste artigo é fornecer orientações sobre como iniciar uma campanha de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9690572fd5f17fece0de7b533c98bfc52d77615b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="e5f77-103">Fase 2: Campanha de migração</span><span class="sxs-lookup"><span data-stu-id="e5f77-103">Phase 2: Migration Campaign</span></span>
<a id="phase-2-migration-campaign" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="e5f77-104">As organizações devem usar abordagens de migração mais adequadas às suas necessidades e ajustar as táticas de implementação com base em suas necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="e5f77-104">Organizations should a migration approaches which is most suitable for their needs and adjust implementation tactics based on their specific requirements.</span></span> <span data-ttu-id="e5f77-105">O restante deste guia fornecerá a você as ferramentas necessárias para atingir o objetivo de registrar os dispositivos de usuários no Intune.</span><span class="sxs-lookup"><span data-stu-id="e5f77-105">The remainder of this guide will equip you with the tools you need to achieve the goal of getting your user’s devices enrolled into Intune.</span></span>

## <span data-ttu-id="e5f77-106">Segredos para uma migração bem-sucedida</span><span class="sxs-lookup"><span data-stu-id="e5f77-106">Keys to a successful migration</span></span>
<a id="keys-to-a-successful-migration" class="xliff"></a>

<span data-ttu-id="e5f77-107">Estas são as principais lições aprendidas durante a migração de um provedor de MDM de terceiros para o Intune:</span><span class="sxs-lookup"><span data-stu-id="e5f77-107">These are the key lessons learned when migrating from a third-party MDM provide to Intune:</span></span>

-   <span data-ttu-id="e5f77-108">A comunicação é essencial para minimizar o tempo de inatividade e a satisfação do usuário final.</span><span class="sxs-lookup"><span data-stu-id="e5f77-108">Communication is key to minimize end-user downtime and satisfaction.</span></span>

-   <span data-ttu-id="e5f77-109">Tenha instruções de migração específicas e concretas.</span><span class="sxs-lookup"><span data-stu-id="e5f77-109">Be sure to have specific and concrete migration instructions.</span></span>

-   <span data-ttu-id="e5f77-110">Todos os dispositivos gerenciados devem ter seu registro cancelado no provedor de MDM existente antes do registro no Intune.</span><span class="sxs-lookup"><span data-stu-id="e5f77-110">All managed devices must be un-enrolled from your existing MDM provider prior to enrolling in Intune.</span></span>

-   <span data-ttu-id="e5f77-111">Forneça aos usuários finais a orientação do provedor de MDM existente sobre como cancelar o registro de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e5f77-111">Provide guidance from the existing MDM provider to end-users for how to un-enroll their devices.</span></span>

-   <span data-ttu-id="e5f77-112">Use uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="e5f77-112">Use a phased approach.</span></span> <span data-ttu-id="e5f77-113">Comece com um pequeno grupo de usuários piloto e adicione aos poucos mais grupos de usuários até atingir a implantação completa.</span><span class="sxs-lookup"><span data-stu-id="e5f77-113">Start with a small group of pilot users and incrementally add more groups of users until you reach full scale deployment.</span></span>

-   <span data-ttu-id="e5f77-114">Monitore a carga do suporte técnico e o sucesso do registro de cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="e5f77-114">Monitor the Help-desk load and enrollment success of each cycle.</span></span> <span data-ttu-id="e5f77-115">Reserve um tempo na agenda para garantir que os critérios de sucesso possam ser avaliados para cada grupo antes de migrar o próximo.</span><span class="sxs-lookup"><span data-stu-id="e5f77-115">Leave time in the schedule to ensure success criteria can be evaluated for each group before migrating the next.</span></span> <span data-ttu-id="e5f77-116">Sua implantação piloto deve validar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e5f77-116">Your pilot deployment should validate the following:</span></span>

    -   <span data-ttu-id="e5f77-117">Se as taxas de êxito e falha de registro estão dentro das expectativas.</span><span class="sxs-lookup"><span data-stu-id="e5f77-117">Enrollment success and failure rates are within expectations.</span></span>

    -   <span data-ttu-id="e5f77-118">Produtividade do usuário:</span><span class="sxs-lookup"><span data-stu-id="e5f77-118">User productivity:</span></span>

        -   <span data-ttu-id="e5f77-119">Se os recursos corporativos, como VPN, Wi-Fi, email e certificados, estão funcionando.</span><span class="sxs-lookup"><span data-stu-id="e5f77-119">Corporate resources such as VPN, Wi-Fi, email, and certificates are working.</span></span>

        -   <span data-ttu-id="e5f77-120">Se os aplicativos provisionados podem ser acessados.</span><span class="sxs-lookup"><span data-stu-id="e5f77-120">Provisioned Apps are accessible.</span></span>

    -   <span data-ttu-id="e5f77-121">Segurança de dados:</span><span class="sxs-lookup"><span data-stu-id="e5f77-121">Data security:</span></span>

        -   <span data-ttu-id="e5f77-122">Relatório de conformidade</span><span class="sxs-lookup"><span data-stu-id="e5f77-122">Compliance reporting</span></span>

        -   <span data-ttu-id="e5f77-123">Proteções de aplicativo móvel impostas</span><span class="sxs-lookup"><span data-stu-id="e5f77-123">Mobile app protections enforced</span></span>

-   <span data-ttu-id="e5f77-124">Quando você estiver satisfeito com a primeira fase da migração, repita o Ciclo de migração (descrito abaixo em Ciclo típico de migração) para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="e5f77-124">When you are satisfied with the first phase of migrations, repeat the Migration Cycle (described below under Typical Migration cycle) for next phase.</span></span>

-   <span data-ttu-id="e5f77-125">Repita os ciclos em fases até que todos os usuários sejam migrados para o Intune.</span><span class="sxs-lookup"><span data-stu-id="e5f77-125">Repeat phased cycles until all users are migrated to Intune.</span></span>

-   <span data-ttu-id="e5f77-126">Certifique-se de que a equipe de suporte técnico esteja pronta para dar suporte a usuários finais durante toda a campanha de migração.</span><span class="sxs-lookup"><span data-stu-id="e5f77-126">Ensure Help-desk team is ready to support end-users throughout the migration campaign.</span></span> <span data-ttu-id="e5f77-127">Execute uma migração voluntária até que você possa estimar a carga de trabalho de chamada de suporte.</span><span class="sxs-lookup"><span data-stu-id="e5f77-127">Run a voluntary migration until you can estimate support call workload.</span></span>

-   <span data-ttu-id="e5f77-128">Não defina prazos para o registro até que a população restante possa ser atendida por seu suporte técnico</span><span class="sxs-lookup"><span data-stu-id="e5f77-128">Don’t set deadlines for enrollment until remaining population can be handled by your Help-desk</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="e5f77-129">Não configure o Intune e sua solução existente de MDM de terceiros para aplicar os controles de acesso aos recursos, como o Exchange ou SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="e5f77-129">Do not configure both Intune and your existing third party MDM solution to apply access controls to resources such as Exchange or SharePoint Online.</span></span> <span data-ttu-id="e5f77-130">Além disso, os dispositivos só devem ser registrados em uma solução por vez.</span><span class="sxs-lookup"><span data-stu-id="e5f77-130">Additionally, devices should only be enrolled in one solution at a time.</span></span>

## <span data-ttu-id="e5f77-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="e5f77-131">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="e5f77-132">Plano de comunicação</span><span class="sxs-lookup"><span data-stu-id="e5f77-132">Communication plan</span></span>](migration-guide-communication-plan.md)
