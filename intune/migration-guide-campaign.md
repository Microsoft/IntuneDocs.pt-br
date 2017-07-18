---
title: "<span data-ttu-id=\"7d219-101\">Iniciar uma campanha de migração do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"7d219-101\">Start an Intune migration campaign</span></span>"
description: "<span data-ttu-id=\"7d219-102\">Este artigo fornece diretrizes de como iniciar uma campanha de migração.</span><span class=\"sxs-lookup\"><span data-stu-id=\"7d219-102\">This article provides guidance for how to start a migration campaign.</span></span>"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: a272d9c822a2c17592d7800c20278ce222d615bd
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="phase-2-migration-campaign"></a><span data-ttu-id="7d219-103">Fase 2: campanha de migração</span><span class="sxs-lookup"><span data-stu-id="7d219-103">Phase 2: Migration campaign</span></span>

<span data-ttu-id="7d219-104">Escolha uma abordagem de migração mais adequada às suas necessidades e ajuste as táticas de implementação com base em seus requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="7d219-104">Choose a migration approach that is most suitable for your organization's needs and adjust implementation tactics based on your specific requirements.</span></span> <span data-ttu-id="7d219-105">O restante deste guia fornecerá a você as ferramentas necessárias para atingir a meta de registrar os dispositivos de usuários no Intune.</span><span class="sxs-lookup"><span data-stu-id="7d219-105">The remainder of this guide will equip you with the tools you need to achieve the goal of getting your users’ devices enrolled into Intune.</span></span>

## <a name="keys-to-a-successful-migration"></a><span data-ttu-id="7d219-106">Segredos para uma migração bem-sucedida</span><span class="sxs-lookup"><span data-stu-id="7d219-106">Keys to a successful migration</span></span>

<span data-ttu-id="7d219-107">Estas são as chaves para migrar com êxito de um provedor de MDM de terceiros para o Intune:</span><span class="sxs-lookup"><span data-stu-id="7d219-107">These are the keys to migrating successfully from a third-party MDM provider to Intune:</span></span>

-   <span data-ttu-id="7d219-108">Comunicação clara e útil pode minimizar a insatisfação e o tempo de inatividade do usuário final.</span><span class="sxs-lookup"><span data-stu-id="7d219-108">Clear and helpful communication can minimize end-user downtime and dissatisfaction.</span></span>

-   <span data-ttu-id="7d219-109">Tenha instruções de migração específicas e concretas.</span><span class="sxs-lookup"><span data-stu-id="7d219-109">Be sure to have specific and concrete migration instructions.</span></span>

-   <span data-ttu-id="7d219-110">Todos os dispositivos gerenciados devem ter seu registro cancelado no provedor de MDM existente antes que possam ser registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="7d219-110">All managed devices must be unenrolled from your existing MDM provider before they can be enrolled in Intune.</span></span>

-   <span data-ttu-id="7d219-111">Forneça aos usuários finais a orientação do seu provedor de MDM existente sobre como cancelar o registro de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="7d219-111">Provide guidance from your existing MDM provider to end-users for how to unenroll their devices.</span></span>

-   <span data-ttu-id="7d219-112">Use uma abordagem em fases.</span><span class="sxs-lookup"><span data-stu-id="7d219-112">Use a phased approach.</span></span> <span data-ttu-id="7d219-113">Comece com um pequeno grupo de usuários piloto e adicione aos poucos mais grupos de usuários até atingir a implantação completa.</span><span class="sxs-lookup"><span data-stu-id="7d219-113">Start with a small group of pilot users and incrementally add more groups of users until you reach full scale deployment.</span></span>

-   <span data-ttu-id="7d219-114">Monitore o carregamento do suporte técnico e o sucesso do registro de cada ciclo.</span><span class="sxs-lookup"><span data-stu-id="7d219-114">Monitor the helpdesk load and enrollment success of each cycle.</span></span> <span data-ttu-id="7d219-115">Reserve um tempo na agenda para garantir que os critérios de sucesso possam ser avaliados para cada grupo antes de migrar o próximo.</span><span class="sxs-lookup"><span data-stu-id="7d219-115">Leave time in the schedule to ensure success criteria can be evaluated for each group before migrating the next.</span></span> <span data-ttu-id="7d219-116">Sua implantação piloto deve validar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d219-116">Your pilot deployment should validate the following:</span></span>

    -   <span data-ttu-id="7d219-117">Se as taxas de êxito e falha de registro estão dentro das expectativas.</span><span class="sxs-lookup"><span data-stu-id="7d219-117">Enrollment success and failure rates are within expectations.</span></span>

    -   <span data-ttu-id="7d219-118">Produtividade do usuário:</span><span class="sxs-lookup"><span data-stu-id="7d219-118">User productivity:</span></span>

        -   <span data-ttu-id="7d219-119">Se os recursos corporativos, como VPN, Wi-Fi, email e certificados, estão funcionando.</span><span class="sxs-lookup"><span data-stu-id="7d219-119">Corporate resources such as VPN, Wi-Fi, email, and certificates are working.</span></span>

        -   <span data-ttu-id="7d219-120">Os aplicativos provisionados podem ser acessados.</span><span class="sxs-lookup"><span data-stu-id="7d219-120">Provisioned apps are accessible.</span></span>

    -   <span data-ttu-id="7d219-121">Segurança de dados:</span><span class="sxs-lookup"><span data-stu-id="7d219-121">Data security:</span></span>

        -   <span data-ttu-id="7d219-122">O relatório de conformidade está ocorrendo.</span><span class="sxs-lookup"><span data-stu-id="7d219-122">Compliance reporting is occurring.</span></span>

        -   <span data-ttu-id="7d219-123">As proteções de aplicativo móvel são impostas.</span><span class="sxs-lookup"><span data-stu-id="7d219-123">Mobile app protections are enforced.</span></span>

<span data-ttu-id="7d219-124">Quando você estiver satisfeito com a primeira fase da migração, repita o [ciclo de migração](migration-guide-cycle.md) para a próxima fase.</span><span class="sxs-lookup"><span data-stu-id="7d219-124">When you are satisfied with the first phase of migrations, repeat the [migration cycle](migration-guide-cycle.md) for the next phase.</span></span>

-   <span data-ttu-id="7d219-125">Repita os ciclos em fases até que todos os usuários sejam migrados para o Intune.</span><span class="sxs-lookup"><span data-stu-id="7d219-125">Repeat phased cycles until all users are migrated to Intune.</span></span>

-   <span data-ttu-id="7d219-126">Verifique se a equipe de suporte técnico está pronta para dar suporte a usuários finais durante toda a campanha de migração.</span><span class="sxs-lookup"><span data-stu-id="7d219-126">Ensure the helpdesk team is ready to support end users throughout the migration campaign.</span></span> <span data-ttu-id="7d219-127">Execute uma migração voluntária até que você possa estimar a carga de trabalho de chamada de suporte.</span><span class="sxs-lookup"><span data-stu-id="7d219-127">Run a voluntary migration until you can estimate support call workload.</span></span>

-   <span data-ttu-id="7d219-128">Não defina prazos para o registro até que a população restante possa ser atendida por seu suporte técnico</span><span class="sxs-lookup"><span data-stu-id="7d219-128">Don’t set deadlines for enrollment until the remaining population can be handled by your helpdesk</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d219-129">Não configure o Intune e sua solução existente de MDM de terceiros para aplicar os controles de acesso aos recursos, como o Exchange ou SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="7d219-129">Do not configure both Intune and your existing third party MDM solution to apply access controls to resources such as Exchange or SharePoint Online.</span></span> <span data-ttu-id="7d219-130">Além disso, os dispositivos só devem ser registrados em uma solução por vez.</span><span class="sxs-lookup"><span data-stu-id="7d219-130">Additionally, devices should only be enrolled in one solution at a time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7d219-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7d219-131">Next steps</span></span>

<span data-ttu-id="7d219-132">Crie seu [plano de comunicação](migration-guide-communication-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7d219-132">Create your [communication plan](migration-guide-communication-plan.md).</span></span>
