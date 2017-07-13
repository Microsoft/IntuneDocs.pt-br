---
title: Conformidade do dispositivo
titleSuffix: Intune on Azure
description: "Use este tópico para saber mais sobre a conformidade do dispositivo no Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a747d577a28433635883ad6c4fe4c858e75902d0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="4b17b-103">O que é a conformidade do dispositivo no Intune?</span><span class="sxs-lookup"><span data-stu-id="4b17b-103">What is device compliance in Intune?</span></span>
<a id="what-is-device-compliance-in-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="4b17b-104">As políticas de conformidade de dispositivo no Intune definem as regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional do EMS e do Intune.</span><span class="sxs-lookup"><span data-stu-id="4b17b-104">Device compliance policies in Intune define the rules and settings that a device must comply with in order to be considered compliant by Intune and EMS conditional access polices.</span></span> <span data-ttu-id="4b17b-105">Você também pode usar as políticas de conformidade de dispositivo para monitorar e corrigir problemas de conformidade com dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4b17b-105">You can also use device compliance policies to monitor and remediate compliance issues with devices.</span></span> 

<span data-ttu-id="4b17b-106">Essas regras incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4b17b-106">These rules include the following:</span></span>

- <span data-ttu-id="4b17b-107">Uso de senha para acessar os dispositivos</span><span class="sxs-lookup"><span data-stu-id="4b17b-107">Use a password to access devices</span></span>
- <span data-ttu-id="4b17b-108">Criptografia</span><span class="sxs-lookup"><span data-stu-id="4b17b-108">Encryption</span></span>
- <span data-ttu-id="4b17b-109">Quer o dispositivo esteja desbloqueado ou com raiz</span><span class="sxs-lookup"><span data-stu-id="4b17b-109">Whether the device is jail-broken or rooted</span></span>
- <span data-ttu-id="4b17b-110">Versão mínima do SO obrigatória</span><span class="sxs-lookup"><span data-stu-id="4b17b-110">Minimum OS version required</span></span>
- <span data-ttu-id="4b17b-111">Versão máxima do SO permitida</span><span class="sxs-lookup"><span data-stu-id="4b17b-111">Maximum OS version allowed</span></span>
- <span data-ttu-id="4b17b-112">Requer que o dispositivo esteja no nível de Defesa Contra Ameaças Móveis</span><span class="sxs-lookup"><span data-stu-id="4b17b-112">Require the device to be at or under the Mobile Threat Defense level</span></span>

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <span data-ttu-id="4b17b-113">Como devo usar uma política de conformidade do dispositivo?</span><span class="sxs-lookup"><span data-stu-id="4b17b-113">How should I use a device compliance policy?</span></span>
<a id="how-should-i-use-a-device-compliance-policy" class="xliff"></a>

### <span data-ttu-id="4b17b-114">Uso do acesso condicional do EMS</span><span class="sxs-lookup"><span data-stu-id="4b17b-114">Using EMS conditional access</span></span>
<a id="using-ems-conditional-access" class="xliff"></a>
<span data-ttu-id="4b17b-115">Você pode usar políticas de conformidade com o acesso condicional do EMS para permitir que somente dispositivos que estão em conformidade com uma ou mais regras de política de conformidade do dispositivo acessem o email e outros recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="4b17b-115">You can use compliance policy with EMS conditional access to allow only devices that comply with one or more device compliance policy rules to access email and other corporate resources.</span></span>

### <span data-ttu-id="4b17b-116">Não usar o acesso condicional do EMS</span><span class="sxs-lookup"><span data-stu-id="4b17b-116">Not using EMS conditional access</span></span>
<a id="not-using-ems-conditional-access" class="xliff"></a>
<span data-ttu-id="4b17b-117">Você também pode usar políticas de conformidade independentemente do acesso condicional do EMS.</span><span class="sxs-lookup"><span data-stu-id="4b17b-117">You can also use device compliance policies independently of EMS conditional access.</span></span>
<span data-ttu-id="4b17b-118">Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade.</span><span class="sxs-lookup"><span data-stu-id="4b17b-118">When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status.</span></span> <span data-ttu-id="4b17b-119">Por exemplo, você pode obter um relatório do número de dispositivos que não estão criptografados ou quais dispositivos estão desbloqueados ou com raiz.</span><span class="sxs-lookup"><span data-stu-id="4b17b-119">For example, you can get a report on how many devices are not encrypted, or which devices are jail-broken or rooted.</span></span> <span data-ttu-id="4b17b-120">No entanto, quando você usa as políticas de conformidade de forma independente, não há restrições de acesso aos recursos da empresa em vigor.</span><span class="sxs-lookup"><span data-stu-id="4b17b-120">But when you use compliance policies independently, no access restrictions to company resources are in place.</span></span>

<span data-ttu-id="4b17b-121">Você pode implantar uma política de conformidade para usuários.</span><span class="sxs-lookup"><span data-stu-id="4b17b-121">You deploy compliance policy to users.</span></span> <span data-ttu-id="4b17b-122">Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade.</span><span class="sxs-lookup"><span data-stu-id="4b17b-122">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span> <span data-ttu-id="4b17b-123">Para saber quanto tempo levará para que dispositivos móveis obtenham uma política após a política ser implantada, consulte Gerenciar configurações e recursos em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4b17b-123">To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.</span></span>

##  <span data-ttu-id="4b17b-124">Console de administração clássica do Intune vs. Intune no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="4b17b-124">Intune classic admin console vs. Intune on the Azure portal</span></span>
<a id="intune-classic-admin-console-vs-intune-on-the-azure-portal" class="xliff"></a>

<span data-ttu-id="4b17b-125">Se você já usou o console de administração clássica do Intune, observe as seguintes diferenças para ajudar na transição para o novo fluxo de trabalho da política de conformidade do dispositivo no portal do Azure:</span><span class="sxs-lookup"><span data-stu-id="4b17b-125">If you have been using the Intune classic admin console, note the following differences to help transition to the new device compliance policy work-flow in the Azure portal:</span></span>

-   <span data-ttu-id="4b17b-126">No Portal do Azure, as políticas de conformidade são criadas separadamente para cada plataforma com suporte.</span><span class="sxs-lookup"><span data-stu-id="4b17b-126">In the Azure portal, the compliance policies are created separately for each supported platform.</span></span> <span data-ttu-id="4b17b-127">No console de administração do Intune, uma política de conformidade era comum a todas as plataformas com suporte.</span><span class="sxs-lookup"><span data-stu-id="4b17b-127">In the Intune Admin console, one compliance policy was common to all supported platforms.</span></span>

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <span data-ttu-id="4b17b-128">Migração do console clássico do Intune para o Intune no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="4b17b-128">Migration from Intune classic console to Intune on the Azure portal</span></span>
<a id="migration-from-intune-classic-console-to-intune-on-the-azure-portal" class="xliff"></a>

<span data-ttu-id="4b17b-129">As políticas de conformidade do dispositivo criadas no [Console clássico do Intune](https://manage.microsoft.com) não aparecerão no novo [Portal do Intune no Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="4b17b-129">Device compliance policies created in the [Intune classic console](https://manage.microsoft.com) will not appear in the new [Intune Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="4b17b-130">No entanto, elas ainda serão destinadas aos usuários e poderão ser gerenciadas por meio do console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="4b17b-130">However, they’ll still be targeted to users and manageable via the Intune classic console.</span></span>

<span data-ttu-id="4b17b-131">Se você quiser aproveitar os novos recursos relacionados à conformidade do dispositivo no Portal do Intune no Azure, será necessário criar novas políticas de conformidade do dispositivo no próprio Portal do Intune no Azure.</span><span class="sxs-lookup"><span data-stu-id="4b17b-131">If you want to take advantage of the new device compliance related features in the Intune Azure portal, you’ll need to create new device compliance policies in the Intune Azure portal itself.</span></span> <span data-ttu-id="4b17b-132">Se você atribuir uma nova política de conformidade do dispositivo no Portal do Intune no Azure a um usuário que também recebeu uma política de conformidade do dispositivo no Portal clássico do Intune, as políticas de conformidade do dispositivo do Portal do Intune no Azure terão precedência sobre as criadas no Console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="4b17b-132">If you assign a new device compliance policy in the Intune Azure portal to a user who also has been assigned with a device compliance policy from the Intune classic portal, then the device compliance policies from the Intune Azure portal takes precedence over the ones created in the Intune classic console.</span></span>

##  <span data-ttu-id="4b17b-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4b17b-133">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="4b17b-134">Introdução às políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="4b17b-134">Get started on device compliance policies</span></span>](device-compliance-get-started.md)


<!---### See also

Conditional access--->
