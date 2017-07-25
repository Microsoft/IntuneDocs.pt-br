---
title: Acesso condicional com o Intune
titleSuffix: Intune on Azure
description: "Saiba como definir as condições que os usuários e dispositivos devem atender para acessar os recursos da empresa no Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3e6b720eeed65c81e5f3a4dbf06890ea8fd09ce
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="5d3ba-103">O que é o acesso condicional?</span><span class="sxs-lookup"><span data-stu-id="5d3ba-103">What's conditional access?</span></span>
<a id="whats-conditional-access" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="5d3ba-104">Este tópico descreve o Acesso condicional, conforme ele se aplica ao EMS (Enterprise Mobility + Security) e apresenta, em seguida, cenários comuns do Acesso condicional ao usar o Intune.</span><span class="sxs-lookup"><span data-stu-id="5d3ba-104">This topic describes Conditional access as it applies to Enterprise Mobility + Security (EMS), and follows that with Conditional access common scenarios when using Intune.</span></span>

<span data-ttu-id="5d3ba-105">O Acesso Condicional do EMS (Enterprise Mobility + Security) não é um produto autônomo, mas uma solução que integra todos os serviços e produtos que fazem parte do EMS.</span><span class="sxs-lookup"><span data-stu-id="5d3ba-105">Enterprise Mobility + Security (EMS) Conditional Access is not a standalone product, it’s a solution that takes part on all services and products that are part of the EMS.</span></span> <span data-ttu-id="5d3ba-106">Ele fornece controle de acesso granular para proteger os dados da empresa, ao mesmo tempo que oferece aos usuários uma experiência que lhes permite fazer o melhor trabalho em qualquer dispositivo e em qualquer localização.</span><span class="sxs-lookup"><span data-stu-id="5d3ba-106">It provides granular access control to keep your corporate data secure, while giving users an experience that allows them to do their best work from any device, and from any location.</span></span>

<span data-ttu-id="5d3ba-107">Você pode definir condições que fornecem acesso aos dados corporativos com base na localização, no dispositivo, no estado do usuário e na sensibilidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5d3ba-107">You can define conditions that gate access to your corporate data based on location, device, user state, and application sensitivity.</span></span>

> [!NOTE] 
> <span data-ttu-id="5d3ba-108">O Acesso Condicional também estende suas funcionalidades aos [serviços do Office 365](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).</span><span class="sxs-lookup"><span data-stu-id="5d3ba-108">Conditional Access also extends its capabilities to [Office 365 services](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).</span></span>

![Diagrama de arquitetura do acesso condicional](./media/ca-diagram-1.png)

## <span data-ttu-id="5d3ba-110">Acesso condicional com o Intune</span><span class="sxs-lookup"><span data-stu-id="5d3ba-110">Conditional access with Intune</span></span>
<a id="conditional-access-with-intune" class="xliff"></a>

<span data-ttu-id="5d3ba-111">O Intune adiciona funcionalidades de conformidade e gerenciamento de dispositivo móvel para dar suporte à solução Acesso Condicional do EMS.</span><span class="sxs-lookup"><span data-stu-id="5d3ba-111">Intune adds mobile device compliance and mobile application management capabilities to support the EMS Conditional Access solution.</span></span>

![Intune e acesso condicional durante o uso do EMS](./media/intune-with-ca-1.png)

<span data-ttu-id="5d3ba-113">Maneiras de usar o acesso condicional com o Intune:</span><span class="sxs-lookup"><span data-stu-id="5d3ba-113">Ways to use conditional access with Intune:</span></span>

-   <span data-ttu-id="5d3ba-114">**Acesso condicional baseado no dispositivo**</span><span class="sxs-lookup"><span data-stu-id="5d3ba-114">**Device-based conditional access**</span></span>

    -   <span data-ttu-id="5d3ba-115">Acesso condicional para o Exchange Local</span><span class="sxs-lookup"><span data-stu-id="5d3ba-115">Conditional access for Exchange on-premises</span></span>

    -   <span data-ttu-id="5d3ba-116">Acesso condicional baseado em controle de acesso à rede</span><span class="sxs-lookup"><span data-stu-id="5d3ba-116">Conditional access based on network access control</span></span>

    -   <span data-ttu-id="5d3ba-117">Acesso condicional baseado nos riscos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="5d3ba-117">Conditional access based on device risk</span></span>

    -   <span data-ttu-id="5d3ba-118">Acesso condicional para computadores Windows</span><span class="sxs-lookup"><span data-stu-id="5d3ba-118">Conditional access for Windows PCs</span></span>

        -   <span data-ttu-id="5d3ba-119">De propriedade corporativa</span><span class="sxs-lookup"><span data-stu-id="5d3ba-119">Corporate-owned</span></span>

        -   <span data-ttu-id="5d3ba-120">BYOD (Traga seu próprio dispositivo)</span><span class="sxs-lookup"><span data-stu-id="5d3ba-120">Bring your own device (BYOD)</span></span>

-   <span data-ttu-id="5d3ba-121">**Acesso condicional baseado no aplicativo**</span><span class="sxs-lookup"><span data-stu-id="5d3ba-121">**App-based conditional access**</span></span>

## <span data-ttu-id="5d3ba-122">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5d3ba-122">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="5d3ba-123">Maneiras comuns de usar o acesso condicional com o Intune</span><span class="sxs-lookup"><span data-stu-id="5d3ba-123">Common ways to use conditional access with Intune</span></span>](conditional-access-intune-common-ways-use.md)