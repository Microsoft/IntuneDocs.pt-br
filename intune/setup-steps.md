---
title: Configurar Intune
description: "Requisitos e pré-requisitos para começar a usar sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d158503c-1276-422b-ab81-5f66c1cd7e7a
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 966183f0da7a48148a193a1823f74b9e416f4004
ms.sourcegitcommit: bee30f4c9e04129d70305fcafc4152c6e062a8b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2017
---
# <span data-ttu-id="92add-103">Configurar Intune</span><span class="sxs-lookup"><span data-stu-id="92add-103">Set up Intune</span></span>
<a id="set-up-intune" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="92add-104">As etapas de configuração preparam o ambiente para o gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="92add-104">The set-up steps prepare your environment for mobile device management.</span></span>  

<span data-ttu-id="92add-105">Caso esteja usando o Microsoft System Center Configuration Manager para gerenciar computadores e servidores, é possível [estender o Configuration Manager para gerenciar dispositivos móveis](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).</span><span class="sxs-lookup"><span data-stu-id="92add-105">If you're currently using Microsoft System Center Configuration Manager to manage computers and servers, you can [extend Configuration Manager to manage mobile devices](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management).</span></span>

>[!TIP]
><span data-ttu-id="92add-106">Você pode usar o *Benefício do FastTrack Center* ao comprar no mínimo 150 licenças para o Intune em um plano qualificado.</span><span class="sxs-lookup"><span data-stu-id="92add-106">If you purchase at least 150 licenses for Intune in an eligible plan, you can use the *FastTrack Center Benefit*.</span></span> <span data-ttu-id="92add-107">Com esse serviço, os especialistas da Microsoft trabalharão junto a você para deixar o ambiente pronto para o Intune.</span><span class="sxs-lookup"><span data-stu-id="92add-107">With this service, Microsoft specialists work with you to get your environment ready for Intune.</span></span> <span data-ttu-id="92add-108">Consulte [Benefício do FastTrack Center para o EMS (Enterprise Mobility + Security)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).</span><span class="sxs-lookup"><span data-stu-id="92add-108">See [FastTrack Center Benefit for Enterprise Mobility + Security (EMS)](https://docs.microsoft.com/enterprise-mobility-security/Solutions/enterprise-mobility-fasttrack-program).</span></span>

| <span data-ttu-id="92add-109">Etapas</span><span class="sxs-lookup"><span data-stu-id="92add-109">Steps</span></span> | <span data-ttu-id="92add-110">Status</span><span class="sxs-lookup"><span data-stu-id="92add-110">Status</span></span>  |
| ------------- |-------------|
| <span data-ttu-id="92add-111">1</span><span class="sxs-lookup"><span data-stu-id="92add-111">1</span></span>  | <span data-ttu-id="92add-112">[Pré-requisitos](supported-devices-browsers.md) – Informações necessárias antes de começar</span><span class="sxs-lookup"><span data-stu-id="92add-112">[Prerequisites](supported-devices-browsers.md) - Need-to-know info before you start</span></span>|
| <span data-ttu-id="92add-113">2</span><span class="sxs-lookup"><span data-stu-id="92add-113">2</span></span> |  <span data-ttu-id="92add-114">[Entrar no Intune](account-sign-up.md) – Entre na sua assinatura de avaliação ou crie uma nova assinatura</span><span class="sxs-lookup"><span data-stu-id="92add-114">[Sign in to Intune](account-sign-up.md) - Sign in to your trial subscription or create a new subscription</span></span> |  
| <span data-ttu-id="92add-115">3</span><span class="sxs-lookup"><span data-stu-id="92add-115">3</span></span> | <span data-ttu-id="92add-116">[Configurar nome de domínio](custom-domain-name-configure.md) – Defina o registro de DNS para conectar o nome de domínio da sua empresa com o Intune</span><span class="sxs-lookup"><span data-stu-id="92add-116">[Configure domain name](custom-domain-name-configure.md) - Set DNS registration to connect your company's domain name with Intune</span></span>  |
| <span data-ttu-id="92add-117">4</span><span class="sxs-lookup"><span data-stu-id="92add-117">4</span></span> | <span data-ttu-id="92add-118">[Adicionar usuários](users-add.md) – Adicione usuários manualmente ou conecte o Active Directory para sincronizar usuários com o Intune</span><span class="sxs-lookup"><span data-stu-id="92add-118">[Add users](users-add.md) - Manually add users or connect Active Directory to synchronize users with Intune</span></span>  |
| <span data-ttu-id="92add-119">5</span><span class="sxs-lookup"><span data-stu-id="92add-119">5</span></span> | <span data-ttu-id="92add-120">[Atribuir licenças](licenses-assign.md) – Forneça aos usuários a permissão para usar o Intune</span><span class="sxs-lookup"><span data-stu-id="92add-120">[Assign licenses](licenses-assign.md) - Give users permission to use Intune</span></span>|
| <span data-ttu-id="92add-121">6</span><span class="sxs-lookup"><span data-stu-id="92add-121">6</span></span> |  <span data-ttu-id="92add-122">[Adicionar grupos](groups-add.md) – Use grupos de usuários e de dispositivos para simplificar as tarefas de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="92add-122">[Add groups](groups-add.md) - Use user and device groups to simplify management tasks</span></span> |
| <span data-ttu-id="92add-123">7</span><span class="sxs-lookup"><span data-stu-id="92add-123">7</span></span> | <span data-ttu-id="92add-124">[Adicionar aplicativos](apps-add.md) – habilite as configurações e os aplicativos que podem ser implantados em usuários</span><span class="sxs-lookup"><span data-stu-id="92add-124">[Add apps](apps-add.md) - Enable settings and apps that can be deployed to users</span></span> |
| <span data-ttu-id="92add-125">8</span><span class="sxs-lookup"><span data-stu-id="92add-125">8</span></span> | <span data-ttu-id="92add-126">[Configurar dispositivos](device-profiles.md) – Configure os perfis que gerenciam dispositivos e o acesso aos recursos da empresa</span><span class="sxs-lookup"><span data-stu-id="92add-126">[Configure devices](device-profiles.md) - Set up profiles that manage devices and access to company resources</span></span> |
| <span data-ttu-id="92add-127">9</span><span class="sxs-lookup"><span data-stu-id="92add-127">9</span></span> | <span data-ttu-id="92add-128">[Personalizar o Portal da Empresa](company-portal-app.md) – Personalize o Portal da empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="92add-128">[Customize Company Portal](company-portal-app.md) - Customize the Intune Company Portal</span></span>   |
| <span data-ttu-id="92add-129">10</span><span class="sxs-lookup"><span data-stu-id="92add-129">10</span></span> | <span data-ttu-id="92add-130">[Habilitar o registro de dispositivo](mdm-authority-set.md) – Habilite o gerenciamento do Intune de dispositivos iOS, Windows, Android e Mac</span><span class="sxs-lookup"><span data-stu-id="92add-130">[Enable device enrollment](mdm-authority-set.md) - Enable Intune management of iOS, Windows, Android, and Mac devices</span></span> |
