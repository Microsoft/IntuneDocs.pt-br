---
title: "Guia de migração de gerenciamento de dispositivo móvel do Intune"
description: "A finalidade deste guia é mostrar aos clientes os diversos detalhes envolvidos na migração de um provedor de MDM de terceiros para o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9e86f342413a0f31c51d7a56f862986c433309eb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="92103-103">Guia de migração do Intune</span><span class="sxs-lookup"><span data-stu-id="92103-103">Intune migration guide</span></span>
<a id="intune-migration-guide" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

![Arte do guia de migração de MDM do Intune](./media/MDM-migration-guide-art.PNG)

<span data-ttu-id="92103-105">Uma migração bem-sucedida para o Intune começa com um plano sólido que considera o ambiente atual de MDM (gerenciamento de dispositivo móvel), as metas de negócios e os requisitos técnicos.</span><span class="sxs-lookup"><span data-stu-id="92103-105">A successful migration to Intune starts with a solid plan that factors in the current mobile device management (MDM) environment, business goals and technical requirements.</span></span> <span data-ttu-id="92103-106">Além disso, você precisa contar com as principais partes interessadas que oferecerão suporte e colaborarão com seu plano de migração.</span><span class="sxs-lookup"><span data-stu-id="92103-106">Additionally, you need to have the key stakeholders whose will support and collaborate with your migration plan.</span></span>

<span data-ttu-id="92103-107">A finalidade deste guia é mostrar a você os diversos detalhes envolvidos na migração de um provedor de MDM de terceiros para o Intune.</span><span class="sxs-lookup"><span data-stu-id="92103-107">The purpose of this guide is to step you through the various details involved in migrating from a third-party MDM provider to Intune.</span></span>

## <span data-ttu-id="92103-108">O que está incluído neste guia?</span><span class="sxs-lookup"><span data-stu-id="92103-108">What’s included in this guide?</span></span>
<a id="whats-included-in-this-guide" class="xliff"></a>

<span data-ttu-id="92103-109">Este guia inclui duas fases, e as duas incluem tarefas, estratégias e orientações táticas que ajudarão você a percorrer o processo de migração de MDM de ponta a ponta para o Intune.</span><span class="sxs-lookup"><span data-stu-id="92103-109">This guide includes two phases, both of which include tasks, strategies, and tactical guidance that will help you step through the end to end process of migrating to Intune MDM.</span></span>

-   <span data-ttu-id="92103-110">[Fase 1: Preparar o Intune para o Gerenciamento de dispositivo móvel] (migration-guide-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="92103-110">[Phase 1: Prepare Intune for Mobile device management] (migration-guide-prepare.md)</span></span>

    -   [<span data-ttu-id="92103-111">Avaliar seus requisitos de migração de MDM</span><span class="sxs-lookup"><span data-stu-id="92103-111">Assess your MDM migration requirements</span></span>](migration-guide-prepare.md#assess-mdm-requirements)

    -   [<span data-ttu-id="92103-112">Configuração básica</span><span class="sxs-lookup"><span data-stu-id="92103-112">Basic setup</span></span>](migration-guide-setup.md)

    -   [<span data-ttu-id="92103-113">Configurar políticas de gerenciamento de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="92103-113">Configure device and app management policies</span></span>](migration-guide-configure-policies.md)

    -   <span data-ttu-id="92103-114">[Configurar políticas de proteção de aplicativo] (migration-guide-app-protection-policies.md)</span><span class="sxs-lookup"><span data-stu-id="92103-114">[Configure app protection policies] (migration-guide-app-protection-policies.md)</span></span>

    -   [<span data-ttu-id="92103-115">Considerações especiais de migração</span><span class="sxs-lookup"><span data-stu-id="92103-115">Special migration considerations</span></span>](migration-guide-considerations.md)

-   [<span data-ttu-id="92103-116">Fase 2: Campanha de migração</span><span class="sxs-lookup"><span data-stu-id="92103-116">Phase 2: Migration campaign</span></span>](migration-guide-campaign.md)

    -   [<span data-ttu-id="92103-117">Plano de comunicação</span><span class="sxs-lookup"><span data-stu-id="92103-117">Communication Plan</span></span>](migration-guide-communication-plan.md)

    -   [<span data-ttu-id="92103-118">Gerar adoção de usuário final com acesso condicional</span><span class="sxs-lookup"><span data-stu-id="92103-118">Drive end-user adoption with conditional access</span></span>](migration-guide-drive-adoption.md)
    
    -   [<span data-ttu-id="92103-119">Ciclo de migração típico</span><span class="sxs-lookup"><span data-stu-id="92103-119">Typical Migration Cycle</span></span>](migration-guide-cycle.md)
        -   [<span data-ttu-id="92103-120">Monitoramento da migração</span><span class="sxs-lookup"><span data-stu-id="92103-120">Monitoring migration</span></span>](migration-guide-cycle.md#monitoring-migration)
        -   [<span data-ttu-id="92103-121">Pós-migração</span><span class="sxs-lookup"><span data-stu-id="92103-121">Post migration</span></span>](migration-guide-cycle.md#post-migration)

## <span data-ttu-id="92103-122">Suposições</span><span class="sxs-lookup"><span data-stu-id="92103-122">Assumptions</span></span>
<a id="assumptions" class="xliff"></a>

-   <span data-ttu-id="92103-123">Você já avaliou o Intune em um ambiente de PoC (prova de conceito) e decidiu usá-lo como a solução de MDM em sua organização.</span><span class="sxs-lookup"><span data-stu-id="92103-123">You've already evaluated Intune in a proof of concept (PoC) environment, and have decided to use it as the MDM solution in your organization.</span></span>

-   <span data-ttu-id="92103-124">Você já está familiarizado com o Intune e seus recursos.</span><span class="sxs-lookup"><span data-stu-id="92103-124">You are already familiar with Intune and its features.</span></span> 

> [!NOTE]
> <span data-ttu-id="92103-125">Confira o [guia de avaliação do Intune](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune) se quiser se familiarizar mais com o Intune antes de migrar.</span><span class="sxs-lookup"><span data-stu-id="92103-125">Check out the [Intune evaluation guide](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune), if you want to get more familiar with Intune before you migrate.</span></span>

## <span data-ttu-id="92103-126">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="92103-126">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="92103-127">É importante reconhecer que a nova implantação do Intune pode ser diferente de sua implantação de MDM antiga.</span><span class="sxs-lookup"><span data-stu-id="92103-127">It's important to recognize that your new Intune deployment might be different from your old MDM deployment.</span></span> <span data-ttu-id="92103-128">Ao contrário dos serviços de MDM tradicionais, o Intune centraliza no controle de acesso baseado em identidades e, portanto, não exige um dispositivo de proxy de rede para controlar o acesso a dados corporativos de dispositivos móveis fora do perímetro da rede da organização.</span><span class="sxs-lookup"><span data-stu-id="92103-128">Unlike traditional MDM services, Intune centers on identity-driven access control, and so does not require a network proxy appliance to control access to corporate data from mobile devices outside the organization's network perimeter.</span></span> <span data-ttu-id="92103-129">A Microsoft oferece soluções para proteger os serviços de dados na própria nuvem por meio de um conjunto integrado de serviços de nuvem, coletivamente chamado de oferta Cliente Empresarial + Segurança.</span><span class="sxs-lookup"><span data-stu-id="92103-129">Microsoft offers solutions to secure data services within the cloud itself via a suite of tightly integrated cloud services, collectively referred to as the Enterprise Client + Security offering.</span></span>

-   <span data-ttu-id="92103-130">Examine as [formas comuns para usar o Intune](migration-guide-prepare.md#assess-mdm-requirements).</span><span class="sxs-lookup"><span data-stu-id="92103-130">Review the [common ways to use Intune](migration-guide-prepare.md#assess-mdm-requirements).</span></span>

## <span data-ttu-id="92103-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="92103-131">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="92103-132">[Fase 1: Preparar o Intune para o gerenciamento de dispositivo móvel] (migration-guide-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="92103-132">[Phase 1: Prepare Intune for mobile device management] (migration-guide-prepare.md)</span></span>
