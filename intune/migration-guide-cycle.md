---
title: "Como funciona um ciclo de migração típico do Intune"
description: "A finalidade deste artigo é explicar como funciona um ciclo de migração do Intune e dar exemplos de como o cliente lida com os ciclos de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70aa7155e050450a2d786a1f16e42ce2a3c77f9e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="a2c23-103">Ciclo de migração típico</span><span class="sxs-lookup"><span data-stu-id="a2c23-103">Typical migration cycle</span></span>
<a id="typical-migration-cycle" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="a2c23-104">Normalmente, as organizações começam sua migração no Intune com um pequeno projeto piloto, visando um subconjunto de seus usuários no departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="a2c23-104">It’s common for an organization to start their Intune migration with a small pilot by targeting a subset of their users in the IT department.</span></span> <span data-ttu-id="a2c23-105">Além disso, talvez sua organização precise discutir fatores como a disposição do grupo em mudar, o número de usuários, a complexidade, os requisitos, o local e os riscos comerciais, a fim de ajudar a determinar o cronograma da migração.</span><span class="sxs-lookup"><span data-stu-id="a2c23-105">Additionally, your organization may need to discuss such factors as the group’s willingness for change, number of users, complexity, requirements, location, and business risk to assist in determining the migration time-frame.</span></span>

<span data-ttu-id="a2c23-106">Veja um exemplo de como os grupos-alvo poderão ser agendados:</span><span class="sxs-lookup"><span data-stu-id="a2c23-106">Here’s an example of how your target groups could be scheduled:</span></span>

  | <span data-ttu-id="a2c23-107">**Grupos-alvo da migração**</span><span class="sxs-lookup"><span data-stu-id="a2c23-107">**Migration targeted groups**</span></span> | <span data-ttu-id="a2c23-108">**Período 1**</span><span class="sxs-lookup"><span data-stu-id="a2c23-108">**Time period 1**</span></span> | <span data-ttu-id="a2c23-109">**Período 2**</span><span class="sxs-lookup"><span data-stu-id="a2c23-109">**Time period 2**</span></span> | <span data-ttu-id="a2c23-110">**Período 3**</span><span class="sxs-lookup"><span data-stu-id="a2c23-110">**Time period 3**</span></span> | <span data-ttu-id="a2c23-111">**Período 4**</span><span class="sxs-lookup"><span data-stu-id="a2c23-111">**Time period 4**</span></span> | <span data-ttu-id="a2c23-112">**...**</span><span class="sxs-lookup"><span data-stu-id="a2c23-112">**...**</span></span>
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="a2c23-113">Organização de TI piloto limitada (50 usuários)</span><span class="sxs-lookup"><span data-stu-id="a2c23-113">Limited Pilot IT org (50 users)</span></span> | <span data-ttu-id="a2c23-114">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="a2c23-114">Announce Plan</span></span> | <span data-ttu-id="a2c23-115">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="a2c23-115">Instruct to enroll</span></span> | <span data-ttu-id="a2c23-116">Definir prazo</span><span class="sxs-lookup"><span data-stu-id="a2c23-116">Give deadline</span></span> | <span data-ttu-id="a2c23-117">Impor acesso condicional</span><span class="sxs-lookup"><span data-stu-id="a2c23-117">Enforce conditional access</span></span> |  |                                                        
| <span data-ttu-id="a2c23-118">Organização de TI piloto expandida (200 usuários)</span><span class="sxs-lookup"><span data-stu-id="a2c23-118">Expanded Pilot IT org (200 users)</span></span> |  | <span data-ttu-id="a2c23-119">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="a2c23-119">Announce Plan</span></span> | <span data-ttu-id="a2c23-120">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="a2c23-120">Instruct to enroll</span></span> | <span data-ttu-id="a2c23-121">Definir prazo</span><span class="sxs-lookup"><span data-stu-id="a2c23-121">Give deadline</span></span> | <span data-ttu-id="a2c23-122">Impor acesso condicional</span><span class="sxs-lookup"><span data-stu-id="a2c23-122">Enforce conditional access</span></span> | 
| <span data-ttu-id="a2c23-123">Usuários com conhecimentos técnicos da fase 1 de migração (2000)</span><span class="sxs-lookup"><span data-stu-id="a2c23-123">Migration phase 1 Tech-savvy users (2000)</span></span> |  |  | <span data-ttu-id="a2c23-124">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="a2c23-124">Announce Plan</span></span> | <span data-ttu-id="a2c23-125">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="a2c23-125">Instruct to enroll</span></span> | <span data-ttu-id="a2c23-126">Definir prazo</span><span class="sxs-lookup"><span data-stu-id="a2c23-126">Give deadline</span></span> | 
| <span data-ttu-id="a2c23-127">Fase 2 da migração, Leste dos EUA</span><span class="sxs-lookup"><span data-stu-id="a2c23-127">Migration phase 2 Eastern US</span></span> |  |  |  | <span data-ttu-id="a2c23-128">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="a2c23-128">Announce Plan</span></span> | <span data-ttu-id="a2c23-129">Instruir para o registro</span><span class="sxs-lookup"><span data-stu-id="a2c23-129">Instruct to enroll</span></span> | 
| <span data-ttu-id="a2c23-130">Todas as regiões</span><span class="sxs-lookup"><span data-stu-id="a2c23-130">All Regions</span></span> |  |  |  |  | <span data-ttu-id="a2c23-131">Anunciar plano</span><span class="sxs-lookup"><span data-stu-id="a2c23-131">Announce Plan</span></span> | 

## <span data-ttu-id="a2c23-132">Estudo de caso de migração do cliente</span><span class="sxs-lookup"><span data-stu-id="a2c23-132">Customer migration case study</span></span>
<a id="customer-migration-case-study" class="xliff"></a>

### <span data-ttu-id="a2c23-133">Adatum Corporation</span><span class="sxs-lookup"><span data-stu-id="a2c23-133">Adatum Corporation</span></span>
<a id="adatum-corporation" class="xliff"></a>

- <span data-ttu-id="a2c23-134">Confira como a [Adatum Corporation passou pelo processo de migração de um provedor de MDM de terceiros para o Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span><span class="sxs-lookup"><span data-stu-id="a2c23-134">Check out [how Adatum Corporation went through the process of migration from a third-party MDM provider to Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span></span>

## <span data-ttu-id="a2c23-135">Monitorando a migração</span><span class="sxs-lookup"><span data-stu-id="a2c23-135">Monitoring migration</span></span>
<a id="monitoring-migration" class="xliff"></a>

<span data-ttu-id="a2c23-136">O Microsoft Intune fornece várias maneiras de monitorar a migração:</span><span class="sxs-lookup"><span data-stu-id="a2c23-136">Microsoft Intune provides several ways that you can monitor your migration:</span></span>

1.  <span data-ttu-id="a2c23-137">Exibições de grupo de usuários do Intune</span><span class="sxs-lookup"><span data-stu-id="a2c23-137">Intune user group views</span></span>

2.  <span data-ttu-id="a2c23-138">Conjunto de relatórios internos, e</span><span class="sxs-lookup"><span data-stu-id="a2c23-138">Set of built-in reports, and</span></span>

3.  <span data-ttu-id="a2c23-139">Alertas no console.</span><span class="sxs-lookup"><span data-stu-id="a2c23-139">In-console alerts.</span></span>

<span data-ttu-id="a2c23-140">Você deve controlar quantos usuários registraram dispositivos após cada fase para que você possa:</span><span class="sxs-lookup"><span data-stu-id="a2c23-140">You should track how many users have enrolled devices after each phase so that you can:</span></span>

-   <span data-ttu-id="a2c23-141">Avaliar a eficiência de seu plano de comunicação.</span><span class="sxs-lookup"><span data-stu-id="a2c23-141">Evaluate the effectiveness of your communication plan.</span></span>

-   <span data-ttu-id="a2c23-142">Estimar o impacto da aplicação do acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="a2c23-142">Estimate the impact of enforcing conditional access.</span></span>


## <span data-ttu-id="a2c23-143">Pós-migração</span><span class="sxs-lookup"><span data-stu-id="a2c23-143">Post-migration</span></span>
<a id="post-migration" class="xliff"></a>

<span data-ttu-id="a2c23-144">Você precisará desativar o provedor de MDM anterior e cancelar a assinatura do serviço após a migração para o Intune.</span><span class="sxs-lookup"><span data-stu-id="a2c23-144">You’ll need to retire the previous MDM provider and unsubscribe from the service after migrating to Intune.</span></span> <span data-ttu-id="a2c23-145">Além disso, será necessário remover quaisquer requisitos de infraestrutura desnecessários seguindo as instruções do provedor de MDM.</span><span class="sxs-lookup"><span data-stu-id="a2c23-145">Additionally, you’ll need to remove any unneeded infrastructure requirements by following the MDM provider’s instructions.</span></span>
