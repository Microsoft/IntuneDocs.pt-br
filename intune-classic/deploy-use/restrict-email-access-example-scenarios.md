---
title: "Proteger cenários de email"
description: "Alguns cenários de exemplo e como eles podem ser implementados com acesso condicional."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a60c41d5a35ee60677db3835818ca8b90420c715
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1bb47-103">Proteger o acesso a email com o Microsoft Intune: cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="1bb47-103">Protect access to email with Microsoft Intune: Example scenarios</span></span>
<a id="protect-access-to-email-with-microsoft-intune-example-scenarios" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="1bb47-104">Cenário 1: impedir que usuários usem dispositivos não compatíveis para acessar o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="1bb47-104">Scenario 1: Block users from using noncompliant devices to access Exchange Online</span></span>
<a id="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online" class="xliff"></a>
### <span data-ttu-id="1bb47-105">Requisitos do cenário</span><span class="sxs-lookup"><span data-stu-id="1bb47-105">Scenario requirements</span></span>
<a id="scenario-requirements" class="xliff"></a>
- <span data-ttu-id="1bb47-106">Todos os usuários do grupo de segurança **Contabilidade** do Azure Active Directory deverão ser impedidos de acessar o Exchange Online se o dispositivo não for compatível com uma política de conformidade implantada por você.</span><span class="sxs-lookup"><span data-stu-id="1bb47-106">All users in the **Accounting** Azure Active Directory security group must be blocked from accessing Exchange Online if their device is not compliant with a compliance policy that you deployed.</span></span>
- <span data-ttu-id="1bb47-107">Se existirem quaisquer usuários nesse grupo que não têm suporte do Intune, seu acesso ao Exchange Online deverá ser bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1bb47-107">If any users exist in this group whose devices are not supported by Intune, they must be blocked from accessing Exchange Online on that device.</span></span>
- <span data-ttu-id="1bb47-108">Os usuários do grupo de segurança **Finanças** do Azure Active Directory devem ser isentos da política, mesmo que também estejam no grupo de segurança **Contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="1bb47-108">Users in the **Finance** Azure Active Directory security group must be exempt from the policy, even if they're also in the **Accounting** security group.</span></span>

<span data-ttu-id="1bb47-109">Para fazer isso, configure uma política de acesso condicional para o Exchange Online com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1bb47-109">To accomplish this, configure a conditional access policy for Exchange Online with the following settings:</span></span>

- <span data-ttu-id="1bb47-110">Selecione **Habilitar política de acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="1bb47-110">Choose **Enable conditional access policy**.</span></span>

- <span data-ttu-id="1bb47-111">Selecione as plataformas a que você deseja permitir o acesso de aplicativos com autenticação moderna.</span><span class="sxs-lookup"><span data-stu-id="1bb47-111">Choose the platforms that you want to allow access from apps with modern authentication.</span></span>
- <span data-ttu-id="1bb47-112">Para aplicativos do Exchange ActiveSync, selecione **Bloquear dispositivos incompatíveis em plataformas com suporte do Microsoft Intune** e **Bloquear todos os outros dispositivos em plataformas sem suporte do Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="1bb47-112">For Exchange ActiveSync apps, choose **Block noncompliant devices on platforms supported by Microsoft Intune** and **Block all other devices on platforms not supported by Microsoft Intune.**</span></span>
-   <span data-ttu-id="1bb47-113">Na seção **Grupo de destino**, em **Grupos de segurança selecionados**, escolha o grupo de usuários **Contabilidade**.</span><span class="sxs-lookup"><span data-stu-id="1bb47-113">In the **Targeted group** section, under **Selected security groups**, choose the **Accounting** user group.</span></span>

-   <span data-ttu-id="1bb47-114">Na seção **Grupo isento**, em **Grupos de segurança selecionados**, escolha o grupo de usuários **Finanças**.</span><span class="sxs-lookup"><span data-stu-id="1bb47-114">In the **Exempted group** section, under **Selected security groups**, choose the **Finance** user group.</span></span>


<span data-ttu-id="1bb47-115">O fluxo a seguir é usado no cenário para decidir quais dispositivos podem acessar o Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="1bb47-115">The following flow is used in the scenario to decide which devices can access Exchange Online:</span></span>

![Fluxo de acesso ao dispositivo](./media/ConditionalAccess8-5.png)

## <span data-ttu-id="1bb47-117">Cenário 2: todos os dispositivos iOS que acessam o Exchange local devem ser gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="1bb47-117">Scenario 2: All iOS devices that access Exchange on-premises must be managed by Intune</span></span>
<a id="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune" class="xliff"></a>
### <span data-ttu-id="1bb47-118">Requisitos do cenário</span><span class="sxs-lookup"><span data-stu-id="1bb47-118">Scenario requirements</span></span>
<a id="scenario-requirements" class="xliff"></a>
- <span data-ttu-id="1bb47-119">Somente dispositivos que executam o iOS devem ter acesso permitido ao Exchange local.</span><span class="sxs-lookup"><span data-stu-id="1bb47-119">Only devices that run iOS should be allowed access to Exchange on-premises.</span></span>
- <span data-ttu-id="1bb47-120">Os dispositivos também devem estar registrados no Intune e atender às regras da política de conformidade antes que possam ser usados para acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-120">The devices must also be enrolled in Intune and meet the compliance policy rules before they can be used to access Exchange.</span></span>

<span data-ttu-id="1bb47-121">Para fazer isso, configure a seguinte política de acesso condicional para o Exchange local com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1bb47-121">To accomplish this, configure the following conditional access policy for Exchange on-premises with the following settings:</span></span>

-   <span data-ttu-id="1bb47-122">Escolha a opção **Bloquear o acesso de aplicativos de email ao Exchange local se o dispositivo não for compatível ou não estiver registrado no Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="1bb47-122">Choose the option **Block email apps from accessing Exchange on-premises if the device is noncompliant or not enrolled in Microsoft Intune**.</span></span> <span data-ttu-id="1bb47-123">Ao escolher essa opção, a política de acesso condicional é habilitada, o que requer que todos os dispositivos sejam registrados no Microsoft Intune e obedeçam às regras da política de conformidade antes que possam acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-123">By choosing this option, you enable the conditional access policy, which requires that all devices must be enrolled in Microsoft Intune and meet the compliancy policy rules before they can access Exchange.</span></span>

-   <span data-ttu-id="1bb47-124">Para configurações avançadas do Exchange Active Sync, crie:</span><span class="sxs-lookup"><span data-stu-id="1bb47-124">For advanced Exchange Active Sync settings, create:</span></span>

  -   <span data-ttu-id="1bb47-125">Uma exceção de plataforma que permite que dispositivos que executam iOS acessem o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-125">A platform exception that allows devices that run iOS to access Exchange.</span></span>   

  -   <span data-ttu-id="1bb47-126">Uma regra padrão que especifica que quando um dispositivo não está coberto pela regra de exceção de plataforma, ele deve ser impedido de acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-126">A default rule that specifies that when a device isn't covered by the platform exception rule, it should be blocked from accessing Exchange.</span></span> <span data-ttu-id="1bb47-127">Essa regra garante que dispositivos que não executam o iOS sejam impedidos de acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-127">This rule makes sure that devices that aren't running iOS are blocked from accessing Exchange.</span></span>

<span data-ttu-id="1bb47-128">O fluxo a seguir é usado para decidir quais dispositivos podem acessar o Exchange:</span><span class="sxs-lookup"><span data-stu-id="1bb47-128">You use the following flow to decide which devices can access Exchange:</span></span>

![Fluxo de acesso ao dispositivo](./media/ConditionalAccess8-3.png)

## <span data-ttu-id="1bb47-130">Cenário 3: nenhum dispositivo Android pode acessar o Exchange local</span><span class="sxs-lookup"><span data-stu-id="1bb47-130">Scenario 3: No Android devices can access Exchange on-premises</span></span>
<a id="scenario-3-no-android-devices-can-access-exchange-on-premises" class="xliff"></a>
### <span data-ttu-id="1bb47-131">Requisitos do cenário</span><span class="sxs-lookup"><span data-stu-id="1bb47-131">Scenario requirements</span></span>
<a id="scenario-requirements" class="xliff"></a>
- <span data-ttu-id="1bb47-132">Todos os dispositivos Android devem ser impedidos de acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-132">All Android devices should be blocked from accessing Exchange.</span></span>
- <span data-ttu-id="1bb47-133">Todos os outros dispositivos com suporte podem acessar o Exchange se forem gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="1bb47-133">All other supported devices can access Exchange, as long as they're managed by Intune.</span></span>

<span data-ttu-id="1bb47-134">Para fazer isso, configure uma política de acesso condicional para o Exchange local com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="1bb47-134">To accomplish this, configure a conditional access policy for Exchange on-premises with the following settings:</span></span>

-   <span data-ttu-id="1bb47-135">Escolha a opção **Bloquear o acesso de aplicativos de email ao Exchange local se o dispositivo não for compatível ou não estiver registrado no Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="1bb47-135">Choose the option **Block email apps from accessing Exchange on-premises if the device is noncompliant or not enrolled in Microsoft Intune**.</span></span> <span data-ttu-id="1bb47-136">Ao selecionar essa opção, exige-se que todos os dispositivos sejam registrados no Intune e atendam às regras da política de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1bb47-136">By choosing this option, you require that any device must be enrolled in Intune and meet the compliance policy rules.</span></span>

- <span data-ttu-id="1bb47-137">Para configurações avançadas do Exchange Active Sync, crie:</span><span class="sxs-lookup"><span data-stu-id="1bb47-137">For advanced Exchange Active Sync settings, create:</span></span>
  -   <span data-ttu-id="1bb47-138">Uma exceção de plataforma que bloqueia o acesso de dispositivos que executam Android ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-138">A platform exception that blocks devices that run Android from accessing Exchange.</span></span> <span data-ttu-id="1bb47-139">Essa regra garante que os dispositivos Android não sejam usados para acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-139">This rule makes sure that Android devices can't be used to access Exchange.</span></span>

  -   <span data-ttu-id="1bb47-140">Uma regra padrão que especifica que quando um dispositivo não é coberto por outras regras, ele deve ter permissão para acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-140">A default rule that specifies that when a device isn't covered by other rules, it should be allowed to access Exchange.</span></span> <span data-ttu-id="1bb47-141">Essa regra padrão garante que os dispositivos que executam plataformas diferentes do Android, mas com suporte do Microsoft Intune, possam ser usados para acessar o Exchange.</span><span class="sxs-lookup"><span data-stu-id="1bb47-141">This default rule makes sure that devices that run platforms other than Android, but are supported by Microsoft Intune, can be used to access Exchange.</span></span> <span data-ttu-id="1bb47-142">No entanto, eles deverão estar registrados no Intune e atender às regras de política de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1bb47-142">They must, however, be enrolled in Intune and meet the compliance policy rules.</span></span>

<span data-ttu-id="1bb47-143">O fluxo a seguir é usado para decidir quais dispositivos podem acessar o Exchange:</span><span class="sxs-lookup"><span data-stu-id="1bb47-143">You use the following flow to decide which devices can access Exchange:</span></span>

![Fluxo de acesso ao dispositivo](./media/ConditionalAccess8-4.png)
