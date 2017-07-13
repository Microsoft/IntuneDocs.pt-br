---
title: "Preparar o Intune para o gerenciamento de dispositivo móvel"
description: "A finalidade deste artigo é ajudar os leitores a avaliar seus requisitos comerciais e técnicos antes de migrar para o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 65e3bb4b6a4e6e8dcfa1dd16738ae47758f4fb9b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="92fe7-103">Fase 1: Preparar o Intune para o MDM (gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="92fe7-103">Phase 1: Prepare Intune for mobile device management (MDM)</span></span>
<a id="phase-1-prepare-intune-for-mobile-device-management-mdm" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="92fe7-104">Antes de entrar nos detalhes da configuração do Intune, vamos analisar os requisitos de gerenciamento de dispositivos móveis de sua organização.</span><span class="sxs-lookup"><span data-stu-id="92fe7-104">Before diving into the details of setting up Intune, let’s review the mobile device management requirements of your organization.</span></span> <span data-ttu-id="92fe7-105">Talvez seja útil executar relatórios de usuários ativos em seu provedor de MDM atual, a fim de identificar os grupos de usuário críticos. Depois, você pode começar a responder as perguntas na [seção Avaliar requisitos de MDM](migration-guide-prepare.md#assess-mdm-requirements).</span><span class="sxs-lookup"><span data-stu-id="92fe7-105">It might be helpful to run reports of active users in your current MDM provider to identify the critical user groups, then you can begin addressing the questions under the [Assess MDM requirements section](migration-guide-prepare.md#assess-mdm-requirements).</span></span>

## <span data-ttu-id="92fe7-106">Avaliar os requisitos de MDM</span><span class="sxs-lookup"><span data-stu-id="92fe7-106">Assess MDM requirements</span></span>
<a id="assess-mdm-requirements" class="xliff"></a>

### <span data-ttu-id="92fe7-107">Quais os tipos de dispositivos que você precisa gerenciar?</span><span class="sxs-lookup"><span data-stu-id="92fe7-107">What kinds of devices do you need to manage?</span></span>
<a id="what-kinds-of-devices-do-you-need-to-manage" class="xliff"></a>

-   <span data-ttu-id="92fe7-108">A quais [plataformas](/intune-classic/get-started/supported-mobile-devices-and-computers) você precisa oferecer suporte?</span><span class="sxs-lookup"><span data-stu-id="92fe7-108">Which [platforms](/intune-classic/get-started/supported-mobile-devices-and-computers) do you need to support?</span></span>

-   <span data-ttu-id="92fe7-109">Os dispositivos para os quais você precisa oferecer suporte são corporativos ou BYOD?</span><span class="sxs-lookup"><span data-stu-id="92fe7-109">Are the devices you need to support corporate or BYOD?</span></span>

-   <span data-ttu-id="92fe7-110">Qual é o tipo de conectividade usado?</span><span class="sxs-lookup"><span data-stu-id="92fe7-110">What kind of connectivity is used?</span></span> <span data-ttu-id="92fe7-111">Wi-Fi, celular, VPN?</span><span class="sxs-lookup"><span data-stu-id="92fe7-111">Wi-Fi, cellular, VPN?</span></span>

### <span data-ttu-id="92fe7-112">O que seus usuários precisam fazer nos dispositivos gerenciados?</span><span class="sxs-lookup"><span data-stu-id="92fe7-112">What do your users need to do on managed devices?</span></span>
<a id="what-do-your-users-need-to-do-on-managed-devices" class="xliff"></a>

-   <span data-ttu-id="92fe7-113">Você precisa provisionar aplicativos para seus usuários finais?</span><span class="sxs-lookup"><span data-stu-id="92fe7-113">Do you need to provision apps to your end-users?</span></span>

-   <span data-ttu-id="92fe7-114">Você usa aplicativos de linha de negócios personalizados?</span><span class="sxs-lookup"><span data-stu-id="92fe7-114">Do you use custom line-of-business apps?</span></span> <span data-ttu-id="92fe7-115">Ou, você só precisa de aplicativos de armazenamento público?</span><span class="sxs-lookup"><span data-stu-id="92fe7-115">Or do you only need public store apps?</span></span>

-   <span data-ttu-id="92fe7-116">Você precisa provisionar contas de email?</span><span class="sxs-lookup"><span data-stu-id="92fe7-116">Do you need to provision email accounts?</span></span>

### <span data-ttu-id="92fe7-117">Quais tipos de usuários?</span><span class="sxs-lookup"><span data-stu-id="92fe7-117">What kinds of users?</span></span>
<a id="what-kinds-of-users" class="xliff"></a>

-   <span data-ttu-id="92fe7-118">Quantos usuários usarão um único dispositivo?</span><span class="sxs-lookup"><span data-stu-id="92fe7-118">How many users will use a single device?</span></span>

-   <span data-ttu-id="92fe7-119">De quais Termos de Uso você precisa?</span><span class="sxs-lookup"><span data-stu-id="92fe7-119">What Terms of Use do you need?</span></span>

    -   <span data-ttu-id="92fe7-120">Envolva o departamento jurídico o quanto antes nesta questão.</span><span class="sxs-lookup"><span data-stu-id="92fe7-120">Make sure to involve your legal department early in this.</span></span>

    -   <span data-ttu-id="92fe7-121">Qual localização é necessária?</span><span class="sxs-lookup"><span data-stu-id="92fe7-121">What localization is required?</span></span>

-   <span data-ttu-id="92fe7-122">Os usuários estão familiarizados com tecnologia e TI em geral?</span><span class="sxs-lookup"><span data-stu-id="92fe7-122">Are the users familiar with technology and IT in general?</span></span>

### <span data-ttu-id="92fe7-123">Qual é sua política de segurança de dispositivo?</span><span class="sxs-lookup"><span data-stu-id="92fe7-123">What is your device security policy?</span></span>
<a id="what-is-your-device-security-policy" class="xliff"></a>

-   <span data-ttu-id="92fe7-124">Você precisa de criptografia no nível do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="92fe7-124">Do you need device-level encryption?</span></span>

-   <span data-ttu-id="92fe7-125">Comprimentos do código pin/senha do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="92fe7-125">Device passcode/pin code lengths?</span></span>

-   <span data-ttu-id="92fe7-126">Você precisa desativar recursos do dispositivo, ou restringir determinados comportamentos do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="92fe7-126">Do you need to disable device features, or restrict certain device behaviors?</span></span>

    -   <span data-ttu-id="92fe7-127">Você pode controlar várias configurações específicas à plataforma com perfis de configuração do dispositivo, por exemplo: desabilitar a câmera, bloqueio no modo de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="92fe7-127">You can control a variety of platform-specific settings with device configuration profiles, for example: Disable camera, Lock to single-app mode.</span></span>
<br></br>
-   <span data-ttu-id="92fe7-128">Para quais tipos de autenticação você precisa dar suportar?</span><span class="sxs-lookup"><span data-stu-id="92fe7-128">What kinds of authentication must you support?</span></span>

    -   <span data-ttu-id="92fe7-129">Se você precisar da autenticação baseada em certificado, quais são os tipos de certificados que devem ser provisionados?</span><span class="sxs-lookup"><span data-stu-id="92fe7-129">If you need cert-based authentication, what kinds of certificates must be provisioned?</span></span>

        -   <span data-ttu-id="92fe7-130">O Intune pode provisionar certificados com os perfis de acesso aos recursos dos dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="92fe7-130">Intune can provision certificates with resource access profiles for enrolled devices.</span></span>
<br></br>
    -   <span data-ttu-id="92fe7-131">Para qual tipo de infraestrutura de PKI (Infraestrutura de chave pública) você precisa oferecer suporte?</span><span class="sxs-lookup"><span data-stu-id="92fe7-131">What kind of Public Key Infrastructure (PKI) infra do you need to support?</span></span>
<br></br>
-   <span data-ttu-id="92fe7-132">Você precisa oferecer suporte à VPN (Rede virtual privada) no nível do aplicativo ou dispositivo?</span><span class="sxs-lookup"><span data-stu-id="92fe7-132">Do you need to support Virtual Private Network (VPN) at the device or app level?</span></span>

    -   <span data-ttu-id="92fe7-133">O Intune pode provisionar as configurações de VPN para provedores de VPN de terceiros.</span><span class="sxs-lookup"><span data-stu-id="92fe7-133">Intune can provision VPN configurations for third-party VPN providers.</span></span>
<br></br>
-   <span data-ttu-id="92fe7-134">É possível fazer exceções temporárias para certos requisitos a fim de evitar o tempo de inatividade?</span><span class="sxs-lookup"><span data-stu-id="92fe7-134">Can temporary exceptions be made for certain requirements to avoid down time?</span></span> <span data-ttu-id="92fe7-135">Ou os dispositivos com acesso sempre devem atender a todos os requisitos de segurança?</span><span class="sxs-lookup"><span data-stu-id="92fe7-135">Or must devices with access always comply with all security requirements?</span></span>

## <span data-ttu-id="92fe7-136">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="92fe7-136">Additional information</span></span>
<a id="additional-information" class="xliff"></a>

-   <span data-ttu-id="92fe7-137">Para obter mais exemplos, veja os [estudos de caso](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) de setores diferentes da indústria para ver como as organizações avaliaram seus requisitos de gerenciamento de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="92fe7-137">For more detailed examples, review these [case studies](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) from different industry sectors to see how organizations assessed their requirements for mobile device management.</span></span>

## <span data-ttu-id="92fe7-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="92fe7-138">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="92fe7-139">Configuração Básica</span><span class="sxs-lookup"><span data-stu-id="92fe7-139">Basic Setup</span></span>](migration-guide-setup.md)
