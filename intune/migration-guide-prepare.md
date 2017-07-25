---
<<<<<<< HEAD
title: "<span data-ttu-id=\"a033b-101\">Preparar o Intune para o gerenciamento de dispositivo móvel</span><span class=\"sxs-lookup\"><span data-stu-id=\"a033b-101\">Prepare Intune for mobile device management</span></span>"
description: "<span data-ttu-id=\"a033b-102\">Avalie seus requisitos comerciais e técnicos antes de migrar para o Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"a033b-102\">Evaluate your business and technical requirements before migrating to Intune.</span></span>"
=======
title: "Preparar o Intune para o gerenciamento de dispositivo móvel"
description: "Avalie seus requisitos comerciais e técnicos antes de migrar para o Intune."
>>>>>>> live
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
ms.openlocfilehash: 9e935531c785a1c907454d563550f237ebffdb13
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a><span data-ttu-id="a033b-103">Fase 1: Preparar o Intune para o MDM (gerenciamento de dispositivo móvel)</span><span class="sxs-lookup"><span data-stu-id="a033b-103">Phase 1: Prepare Intune for mobile device management (MDM)</span></span>

<<<<<<< HEAD
<span data-ttu-id="a033b-104">Antes de entrar nos detalhes da configuração do Intune, vamos analisar os requisitos de gerenciamento de dispositivos móveis de sua organização.</span><span class="sxs-lookup"><span data-stu-id="a033b-104">Before diving into the details of setting up Intune, let’s review the mobile device management requirements of your organization.</span></span> <span data-ttu-id="a033b-105">Pode ser útil executar relatórios de usuários ativos no seu provedor de MDM atual para identificar os grupos de usuários críticos.</span><span class="sxs-lookup"><span data-stu-id="a033b-105">It might be helpful to run reports of active users in your current MDM provider to identify the critical user groups.</span></span> <span data-ttu-id="a033b-106">Em seguida, você pode começar a abordar as perguntas na seção [Avaliar os requisitos de MDM](migration-guide-prepare.md#assess-mdm-requirements).</span><span class="sxs-lookup"><span data-stu-id="a033b-106">Then you can begin addressing the questions in the [Assess MDM requirements ](migration-guide-prepare.md#assess-mdm-requirements) section.</span></span>

## <a name="assess-mdm-requirements"></a><span data-ttu-id="a033b-107">Avaliar os requisitos de MDM</span><span class="sxs-lookup"><span data-stu-id="a033b-107">Assess MDM requirements</span></span>
=======
Antes de entrar nos detalhes da configuração do Intune, vamos analisar os requisitos de gerenciamento de dispositivos móveis de sua organização. Pode ser útil executar relatórios de usuários ativos no seu provedor de MDM atual para identificar os grupos de usuários críticos. Em seguida, você pode começar a abordar as perguntas na seção [Avaliar os requisitos de MDM](migration-guide-prepare.md#assess-mdm-requirements).
>>>>>>> live

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a><span data-ttu-id="a033b-108">Quais os tipos de dispositivos que você precisa gerenciar?</span><span class="sxs-lookup"><span data-stu-id="a033b-108">What kinds of devices do you need to manage?</span></span>

-   <span data-ttu-id="a033b-109">A quais [plataformas](supported-devices-browsers.md) você precisa oferecer suporte?</span><span class="sxs-lookup"><span data-stu-id="a033b-109">Which [platforms](supported-devices-browsers.md) do you need to support?</span></span>

<<<<<<< HEAD
-   <span data-ttu-id="a033b-110">Os dispositivos para os quais você precisa dar suporte são propriedade corporativa ou pessoais?</span><span class="sxs-lookup"><span data-stu-id="a033b-110">Are the devices you need to support corporate-owned or personal devices?</span></span>

-   <span data-ttu-id="a033b-111">Qual é o tipo de conectividade usado?</span><span class="sxs-lookup"><span data-stu-id="a033b-111">What kind of connectivity do you use?</span></span> <span data-ttu-id="a033b-112">Wi-Fi, celular, VPN?</span><span class="sxs-lookup"><span data-stu-id="a033b-112">Wi-Fi, cellular, VPN?</span></span>
=======
-   A quais [plataformas](supported-devices-browsers.md) você precisa oferecer suporte?

-   Os dispositivos para os quais você precisa dar suporte são propriedade corporativa ou pessoais?
>>>>>>> live

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a><span data-ttu-id="a033b-113">O que seus usuários precisam fazer nos dispositivos gerenciados?</span><span class="sxs-lookup"><span data-stu-id="a033b-113">What do your users need to do on managed devices?</span></span>

-   <span data-ttu-id="a033b-114">Você precisa provisionar aplicativos para seus usuários finais?</span><span class="sxs-lookup"><span data-stu-id="a033b-114">Do you need to provision apps to your end-users?</span></span>

-   <span data-ttu-id="a033b-115">Você usa aplicativos de linha de negócios personalizados?</span><span class="sxs-lookup"><span data-stu-id="a033b-115">Do you use custom line-of-business apps?</span></span> <span data-ttu-id="a033b-116">Ou, você só precisa de aplicativos de armazenamento público?</span><span class="sxs-lookup"><span data-stu-id="a033b-116">Or do you only need public store apps?</span></span>

-   <span data-ttu-id="a033b-117">Você precisa provisionar contas de email?</span><span class="sxs-lookup"><span data-stu-id="a033b-117">Do you need to provision email accounts?</span></span>

### <a name="what-kinds-of-users"></a><span data-ttu-id="a033b-118">Quais tipos de usuários?</span><span class="sxs-lookup"><span data-stu-id="a033b-118">What kinds of users?</span></span>

-   <span data-ttu-id="a033b-119">Quantos usuários usarão um único dispositivo?</span><span class="sxs-lookup"><span data-stu-id="a033b-119">How many users will use a single device?</span></span>

-   <span data-ttu-id="a033b-120">De quais termos de uso você precisa?</span><span class="sxs-lookup"><span data-stu-id="a033b-120">What terms of use do you need?</span></span>

<<<<<<< HEAD
    -   <span data-ttu-id="a033b-121">Envolva o departamento jurídico o quanto antes nesta questão.</span><span class="sxs-lookup"><span data-stu-id="a033b-121">Make sure to involve your legal department early in this.</span></span>
    -   <span data-ttu-id="a033b-122">Qual localização é necessária?</span><span class="sxs-lookup"><span data-stu-id="a033b-122">What localization is required?</span></span>

-   <span data-ttu-id="a033b-123">Os usuários estão familiarizados com tecnologia e TI em geral?</span><span class="sxs-lookup"><span data-stu-id="a033b-123">Are the users familiar with technology and IT in general?</span></span>

### <a name="what-is-your-device-security-policy"></a><span data-ttu-id="a033b-124">Qual é sua política de segurança de dispositivo?</span><span class="sxs-lookup"><span data-stu-id="a033b-124">What is your device security policy?</span></span>
=======
-   De quais termos de uso você precisa?

    -   Envolva o departamento jurídico o quanto antes nesta questão.
    -   Qual localização é necessária?
>>>>>>> live

-   <span data-ttu-id="a033b-125">Você precisa de criptografia no nível do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="a033b-125">Do you need device-level encryption?</span></span>

-   <span data-ttu-id="a033b-126">Quais são seus comprimentos de código PIN/senha do dispositivo atuais?</span><span class="sxs-lookup"><span data-stu-id="a033b-126">What are your current device passcode/pin code lengths?</span></span>

-   <span data-ttu-id="a033b-127">Você precisa desativar recursos do dispositivo, ou restringir determinados comportamentos do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="a033b-127">Do you need to disable device features, or restrict certain device behaviors?</span></span> <span data-ttu-id="a033b-128">Você pode controlar várias configurações específicas à plataforma com perfis de configuração do dispositivo, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a033b-128">You can control a variety of platform-specific settings with device configuration profiles, for example:</span></span>
      - <span data-ttu-id="a033b-129">Desabilitar a câmera</span><span class="sxs-lookup"><span data-stu-id="a033b-129">Disable camera</span></span>
      - <span data-ttu-id="a033b-130">Bloqueio para o modo de aplicativo único</span><span class="sxs-lookup"><span data-stu-id="a033b-130">Lock to single-app mode</span></span><br/>

<<<<<<< HEAD
-   <span data-ttu-id="a033b-131">Para quais tipos de autenticação você precisa dar suportar?</span><span class="sxs-lookup"><span data-stu-id="a033b-131">What kinds of authentication must you support?</span></span> <span data-ttu-id="a033b-132">Se você precisar da autenticação baseada em certificado, quais são os tipos de certificados que devem ser provisionados?</span><span class="sxs-lookup"><span data-stu-id="a033b-132">If you need certificate-based authentication, what kinds of certificates must be provisioned?</span></span>
  - <span data-ttu-id="a033b-133">O Intune pode provisionar certificados com os perfis de acesso aos recursos dos dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="a033b-133">Intune can provision certificates with resource access profiles for enrolled devices.</span></span>
    -   <span data-ttu-id="a033b-134">Para qual tipo de infraestrutura de PKI (Infraestrutura de chave pública) você precisa oferecer suporte?</span><span class="sxs-lookup"><span data-stu-id="a033b-134">What kind of Public Key Infrastructure (PKI) infra do you need to support?</span></span>
<br></br>
-   <span data-ttu-id="a033b-135">Você precisa oferecer suporte à VPN (Rede virtual privada) no nível do aplicativo ou dispositivo?</span><span class="sxs-lookup"><span data-stu-id="a033b-135">Do you need to support Virtual Private Network (VPN) at the device or app level?</span></span>

    -   <span data-ttu-id="a033b-136">O Intune pode provisionar as configurações de VPN para provedores de VPN de terceiros.</span><span class="sxs-lookup"><span data-stu-id="a033b-136">Intune can provision VPN configurations for third-party VPN providers.</span></span>
<br/><br/>
-   <span data-ttu-id="a033b-137">É possível fazer exceções temporárias para certos requisitos a fim de evitar o tempo de inatividade?</span><span class="sxs-lookup"><span data-stu-id="a033b-137">Can temporary exceptions be made for certain requirements to avoid downtime?</span></span> <span data-ttu-id="a033b-138">Ou os dispositivos com acesso sempre devem atender a todos os requisitos de segurança?</span><span class="sxs-lookup"><span data-stu-id="a033b-138">Or must devices with access always comply with all security requirements?</span></span>

## <a name="next-steps"></a><span data-ttu-id="a033b-139">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a033b-139">Next steps</span></span>
<span data-ttu-id="a033b-140">Leia estes [estudos de caso](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) de setores diferentes da indústria para ver como as organizações avaliaram seus requisitos de gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="a033b-140">Read these [case studies](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) from different industry sectors to see how organizations assessed their requirements for mobile device management.</span></span>

<span data-ttu-id="a033b-141">Examine a [configuração básica do Intune](migration-guide-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a033b-141">Review the [basic Intune setup](migration-guide-setup.md).</span></span>
=======
-   Quais são seus comprimentos de código PIN/senha do dispositivo atuais?

-   Você precisa desativar recursos do dispositivo, ou restringir determinados comportamentos do dispositivo? Você pode controlar várias configurações específicas à plataforma com perfis de configuração do dispositivo, por exemplo:
      - Desabilitar a câmera
      - Bloqueio para o modo de aplicativo único<br/>

-   Para quais tipos de autenticação você precisa dar suportar? Se você precisar da autenticação baseada em certificado, quais são os tipos de certificados que devem ser provisionados?
  - O Intune pode provisionar certificados com os perfis de acesso aos recursos dos dispositivos registrados.
    -   Para qual tipo de infraestrutura de PKI (Infraestrutura de chave pública) você precisa oferecer suporte?
<br></br>
-   Você precisa oferecer suporte à VPN (Rede virtual privada) no nível do aplicativo ou dispositivo?

    -   O Intune pode provisionar as configurações de VPN para provedores de VPN de terceiros.
<br/><br/>
-   É possível fazer exceções temporárias para certos requisitos a fim de evitar o tempo de inatividade? Ou os dispositivos com acesso sempre devem atender a todos os requisitos de segurança?

## <a name="next-steps"></a>Próximas etapas
Leia estes [estudos de caso](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) de setores diferentes da indústria para ver como as organizações avaliaram seus requisitos de gerenciamento de dispositivo móvel.

Examine a [configuração básica do Intune](migration-guide-setup.md).
>>>>>>> live
