---
<<<<<<< HEAD
title: "<span data-ttu-id=\"e69c9-101\">Como funciona um ciclo de migração típico do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"e69c9-101\">How a typical Intune migration cycle works</span></span>"
description: "<span data-ttu-id=\"e69c9-102\">Este artigo explica como funciona um ciclo de migração do Intune e dar exemplos de como você pode lidar com os ciclos de migração.</span><span class=\"sxs-lookup\"><span data-stu-id=\"e69c9-102\">This article explains how an Intune migration cycle works, and give examples on how you can handle the migration cycles.</span></span>"
=======
title: "Como funciona um ciclo de migração típico do Intune"
description: "Este artigo explica como funciona um ciclo de migração do Intune e dar exemplos de como você pode lidar com os ciclos de migração."
>>>>>>> live
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 34e748e16449a99bad4c1f3e96c22dda6d8f3018
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="typical-migration-cycle"></a><span data-ttu-id="e69c9-103">Ciclo de migração típico</span><span class="sxs-lookup"><span data-stu-id="e69c9-103">Typical migration cycle</span></span>

<<<<<<< HEAD
<span data-ttu-id="e69c9-104">Normalmente, as organizações começam sua migração no Intune com um pequeno projeto piloto, visando um subconjunto de seus usuários no departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="e69c9-104">It’s common for an organization to start their Intune migration with a small pilot by targeting a subset of their users in the IT department.</span></span> <span data-ttu-id="e69c9-105">Além disso, talvez sua organização precise discutir fatores como a disposição do grupo em mudar, o número de usuários, a complexidade, os requisitos, o local e os riscos comerciais, a fim de ajudar a determinar o cronograma da migração.</span><span class="sxs-lookup"><span data-stu-id="e69c9-105">Additionally, your organization may need to discuss such factors as the group’s willingness for change, number of users, complexity, requirements, location, and business risk to assist in determining the migration time-frame.</span></span>

<span data-ttu-id="e69c9-106">Veja um exemplo de como os grupos-alvo poderão ser agendados:</span><span class="sxs-lookup"><span data-stu-id="e69c9-106">Here’s an example of how your target groups could be scheduled:</span></span>
=======
Normalmente, as organizações começam sua migração no Intune com um pequeno projeto piloto, visando um subconjunto de seus usuários no departamento de TI. Além disso, talvez sua organização precise discutir fatores como a disposição do grupo em mudar, o número de usuários, a complexidade, os requisitos, o local e os riscos comerciais, a fim de ajudar a determinar o cronograma da migração.
>>>>>>> live

  | <span data-ttu-id="e69c9-107">**Grupos-alvo da migração**</span><span class="sxs-lookup"><span data-stu-id="e69c9-107">**Migration targeted groups**</span></span> | <span data-ttu-id="e69c9-108">**Período 1**</span><span class="sxs-lookup"><span data-stu-id="e69c9-108">**Time period 1**</span></span> | <span data-ttu-id="e69c9-109">**Período 2**</span><span class="sxs-lookup"><span data-stu-id="e69c9-109">**Time period 2**</span></span> | <span data-ttu-id="e69c9-110">**Período 3**</span><span class="sxs-lookup"><span data-stu-id="e69c9-110">**Time period 3**</span></span> | <span data-ttu-id="e69c9-111">**Período 4**</span><span class="sxs-lookup"><span data-stu-id="e69c9-111">**Time period 4**</span></span> | <span data-ttu-id="e69c9-112">**...**</span><span class="sxs-lookup"><span data-stu-id="e69c9-112">**...**</span></span>
|:---:|:---:|:---:|:---:|:---:|:---:|
<<<<<<< HEAD
| <span data-ttu-id="e69c9-113">Organização de TI piloto limitada (50 usuários)</span><span class="sxs-lookup"><span data-stu-id="e69c9-113">Limited Pilot IT org (50 users)</span></span> | <span data-ttu-id="e69c9-114">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="e69c9-114">Announce Plan</span></span> | <span data-ttu-id="e69c9-115">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="e69c9-115">Instruct to enroll</span></span> | <span data-ttu-id="e69c9-116">Definir prazo</span><span class="sxs-lookup"><span data-stu-id="e69c9-116">Give deadline</span></span> | <span data-ttu-id="e69c9-117">Impor acesso condicional</span><span class="sxs-lookup"><span data-stu-id="e69c9-117">Enforce conditional access</span></span> |  |                                                        
| <span data-ttu-id="e69c9-118">Organização de TI piloto expandida (200 usuários)</span><span class="sxs-lookup"><span data-stu-id="e69c9-118">Expanded Pilot IT org (200 users)</span></span> |  | <span data-ttu-id="e69c9-119">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="e69c9-119">Announce Plan</span></span> | <span data-ttu-id="e69c9-120">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="e69c9-120">Instruct to enroll</span></span> | <span data-ttu-id="e69c9-121">Definir prazo</span><span class="sxs-lookup"><span data-stu-id="e69c9-121">Give deadline</span></span> | <span data-ttu-id="e69c9-122">Impor acesso condicional</span><span class="sxs-lookup"><span data-stu-id="e69c9-122">Enforce conditional access</span></span> |
| <span data-ttu-id="e69c9-123">Usuários com conhecimentos técnicos da fase 1 de migração (2000)</span><span class="sxs-lookup"><span data-stu-id="e69c9-123">Migration phase 1 Tech-savvy users (2000)</span></span> |  |  | <span data-ttu-id="e69c9-124">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="e69c9-124">Announce Plan</span></span> | <span data-ttu-id="e69c9-125">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="e69c9-125">Instruct to enroll</span></span> | <span data-ttu-id="e69c9-126">Definir prazo</span><span class="sxs-lookup"><span data-stu-id="e69c9-126">Give deadline</span></span> |
| <span data-ttu-id="e69c9-127">Fase 2 da migração, Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="e69c9-127">Migration phase 2 Eastern US</span></span> |  |  |  | <span data-ttu-id="e69c9-128">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="e69c9-128">Announce Plan</span></span> | <span data-ttu-id="e69c9-129">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="e69c9-129">Instruct to enroll</span></span> |
| <span data-ttu-id="e69c9-130">Todas as regiões</span><span class="sxs-lookup"><span data-stu-id="e69c9-130">All Regions</span></span> |  |  |  |  | <span data-ttu-id="e69c9-131">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="e69c9-131">Announce Plan</span></span> |
=======
| Organização de TI piloto limitada (50 usuários) | Anunciar plano | Instruir para o registro | Definir prazo | Impor acesso condicional |  |                                                        
| Organização de TI piloto expandida (200 usuários) |  | Anunciar plano | Instruir para o registro | Definir prazo | Impor acesso condicional |
| Usuários com conhecimentos técnicos da fase 1 de migração (2000) |  |  | Anunciar plano | Instruir para o registro | Definir prazo |
| Fase 2 da migração, Leste dos EUA |  |  |  | Anunciar plano | Instruir para o registro |
| Todas as regiões |  |  |  |  | Anunciar plano |
>>>>>>> live

## <a name="customer-migration-case-study"></a><span data-ttu-id="e69c9-132">Estudo de caso de migração do cliente</span><span class="sxs-lookup"><span data-stu-id="e69c9-132">Customer migration case study</span></span>

### <a name="adatum-corporation"></a><span data-ttu-id="e69c9-133">Adatum Corporation</span><span class="sxs-lookup"><span data-stu-id="e69c9-133">Adatum Corporation</span></span>

<<<<<<< HEAD
<span data-ttu-id="e69c9-134">Confira como a [Adatum Corporation passou pelo processo de migração de um provedor de MDM de terceiros para o Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span><span class="sxs-lookup"><span data-stu-id="e69c9-134">Check out [how Adatum Corporation went through the process of migration from a third-party MDM provider to Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span></span>
=======
Confira como a [Adatum Corporation passou pelo processo de migração de um provedor de MDM de terceiros para o Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).
>>>>>>> live

## <a name="monitoring-migration"></a><span data-ttu-id="e69c9-135">Monitorando a migração</span><span class="sxs-lookup"><span data-stu-id="e69c9-135">Monitoring migration</span></span>

<<<<<<< HEAD
<span data-ttu-id="e69c9-136">O Intune fornece várias maneiras de monitorar a migração:</span><span class="sxs-lookup"><span data-stu-id="e69c9-136">Intune provides several ways that you can monitor your migration:</span></span>

* <span data-ttu-id="e69c9-137">Exibições de grupo de usuários do Intune</span><span class="sxs-lookup"><span data-stu-id="e69c9-137">Intune user group views</span></span>

* <span data-ttu-id="e69c9-138">Conjunto de relatórios internos</span><span class="sxs-lookup"><span data-stu-id="e69c9-138">Set of built-in reports</span></span>

* <span data-ttu-id="e69c9-139">Alertas no console</span><span class="sxs-lookup"><span data-stu-id="e69c9-139">In-console alerts</span></span>

<span data-ttu-id="e69c9-140">Controle quantos usuários registraram dispositivos após cada fase para que você possa:</span><span class="sxs-lookup"><span data-stu-id="e69c9-140">Track how many users have enrolled devices after each phase so that you can:</span></span>
=======
O Intune fornece várias maneiras de monitorar a migração:

* Exibições de grupo de usuários do Intune

* Conjunto de relatórios internos

* Alertas no console

Controle quantos usuários registraram dispositivos após cada fase para que você possa:
>>>>>>> live

-   <span data-ttu-id="e69c9-141">Avaliar a eficiência de seu plano de comunicação.</span><span class="sxs-lookup"><span data-stu-id="e69c9-141">Evaluate the effectiveness of your communication plan.</span></span>

-   <span data-ttu-id="e69c9-142">Estimar o impacto da aplicação do acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="e69c9-142">Estimate the impact of enforcing conditional access.</span></span>


## <a name="post-migration"></a><span data-ttu-id="e69c9-143">Pós-migração</span><span class="sxs-lookup"><span data-stu-id="e69c9-143">Post-migration</span></span>

<<<<<<< HEAD
<span data-ttu-id="e69c9-144">Desativar o provedor de MDM anterior e cancelar a assinatura do serviço após a migração para o Intune.</span><span class="sxs-lookup"><span data-stu-id="e69c9-144">Retire the previous MDM provider and unsubscribe from the service after migrating to Intune.</span></span> <span data-ttu-id="e69c9-145">Além disso, remover quaisquer requisitos de infraestrutura desnecessários seguindo as instruções do provedor de MDM.</span><span class="sxs-lookup"><span data-stu-id="e69c9-145">Additionally, remove any unneeded infrastructure requirements by following the MDM provider’s instructions.</span></span>
=======
Desativar o provedor de MDM anterior e cancelar a assinatura do serviço após a migração para o Intune. Além disso, remover quaisquer requisitos de infraestrutura desnecessários seguindo as instruções do provedor de MDM.
>>>>>>> live
