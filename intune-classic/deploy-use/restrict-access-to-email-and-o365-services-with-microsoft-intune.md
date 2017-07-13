---
title: Proteger o email e o Office 365
description: "Este tópico descreve como usar o acesso condicional para permitir que apenas dispositivos compatíveis acessem dados e o email da empresa no SharePoint Online e outros serviços."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3405671130a58aa944d6c689264379a254face1d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="bf4f9-103">Proteger o acesso a email, Office 365 e outros serviços com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bf4f9-103">Protect access to email, Office 365, and other services with Microsoft Intune</span></span>
<a id="protect-access-to-email-office-365-and-other-services-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bf4f9-104">É possível proteger o acesso ao email de sua empresa, a serviços do Office 365 como **Exchange no Local**, **Exchange Online**, **Exchange Online Dedicado**, **SharePoint Online**, **Skype for Business Online** e a outros serviços usando o Acesso Condicional do EMS (Enterprise Mobility + Security).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-104">You can protect access to your company email, Office 365 services like **Exchange On-premises**, **Exchange Online**, **Exchange Online Dedicated**,  **SharePoint Online**, **Skype for Business Online**, and other services by using Enterprise Mobility + Security (EMS) Conditional Access.</span></span> <span data-ttu-id="bf4f9-105">Essa funcionalidade permite que você garanta que o acesso ao email de sua empresa e a serviços do Office 365 é restrito aos dispositivos que estão em conformidade com as regras de acesso condicional definidas no console de administração do Intune ou no Portal Clássico do Azure.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-105">This capability allows you to make sure that access to your company email and Office 365 services is restricted to devices that are compliant with the conditional access rules that you set either in the Intune admin console, or Azure classic portal.</span></span>
## <span data-ttu-id="bf4f9-106">Como funciona o acesso condicional?</span><span class="sxs-lookup"><span data-stu-id="bf4f9-106">How does conditional access work?</span></span>
<a id="how-does-conditional-access-work" class="xliff"></a>
<span data-ttu-id="bf4f9-107">É possível usar as configurações de política de conformidade para avaliar a conformidade de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-107">You can use compliance policy settings to evaluate the compliance of a device.</span></span> <span data-ttu-id="bf4f9-108">Uma política de acesso condicional usa a avaliação para restringir ou permitir o acesso a um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-108">A conditional access policy uses the evaluation to restrict or allow access to a specific service.</span></span> <span data-ttu-id="bf4f9-109">Quando você usa uma política de acesso condicional em combinação com uma política de conformidade do dispositivo, apenas os dispositivos que estão em conformidade poderão acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-109">When you use a conditional access policy in combination with a device compliance policy, only compliant devices are allowed to access the service.</span></span> <span data-ttu-id="bf4f9-110">A política de conformidade e a política de acesso condicional são implantadas para o usuário.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-110">The compliance policy and the conditional access policy are deployed to the user.</span></span> <span data-ttu-id="bf4f9-111">Qualquer dispositivo que o usuário utiliza para acessar os serviços é verificado quanto à conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-111">Any device that the user uses to access the services is checked for compliance with the policies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bf4f9-112">Tenha em mente que o usuário que está usando o dispositivo deve ter uma política de conformidade implantada para que o dispositivo seja avaliado quanto à conformidade.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-112">Keep in mind that the user who is using the device must have a compliance policy that is deployed to them in order for the device to be evaluated for compliance.</span></span>
> <span data-ttu-id="bf4f9-113">Se nenhuma política de conformidade for implantada para o usuário, o dispositivo será tratado como compatível e nenhuma restrição de acesso será aplicada.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-113">If no compliance policy is deployed to the user, the device is treated as compliant, and no access restrictions are applied.</span></span>

<span data-ttu-id="bf4f9-114">Quando dispositivos não atendem às condições definidas na política, o usuário final é guiado pelo processo de registro do dispositivo e correção do problema que está impedindo o dispositivo de ser compatível.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-114">When devices don't meet the conditions that are set in the policies, the end user is guided though the process of enrolling the device and fixing the issue that prevents the device from being compliant.</span></span>

<span data-ttu-id="bf4f9-115">Um fluxo típico do acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="bf4f9-115">A typical flow of conditional access:</span></span>

![Diagrama que mostra os pontos de decisão usados para determinar se um dispositivo tem acesso permitido ou bloqueado a um serviço](../media/ConditionalAccess4.png)

## <span data-ttu-id="bf4f9-117">Considerações sobre instalação</span><span class="sxs-lookup"><span data-stu-id="bf4f9-117">Setup considerations</span></span>
<a id="setup-considerations" class="xliff"></a>

### <span data-ttu-id="bf4f9-118">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="bf4f9-118">Licensing</span></span>
<a id="licensing" class="xliff"></a>

<span data-ttu-id="bf4f9-119">O Microsoft Intune e o Azure AD (Azure Active Directory) Premium trabalham diretamente juntos para fornecer várias camadas de controle por meio do acesso condicional do EMS. Se você desejar implantar políticas de acesso condicional usando o Intune, será necessário ter a licença dos dois produtos.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-119">Microsoft Intune and Azure Active Directory (Azure AD) Premium work seamlessly together to provide multiple layers of control through EMS conditional access, if you want to deploy conditional access policies using Intune, you're required to have license for both products.</span></span>

<span data-ttu-id="bf4f9-120">**Licenças do Azure AD Premium** podem ser adquiridas como um serviço independente ou ser adquiridas (juntamente com o Intune) como parte do Enterprise Agreement.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-120">**Azure AD Premium licenses** can be purchased as a standalone service or can be purchased (along with Intune) as part of the Enterprise agreement.</span></span> <span data-ttu-id="bf4f9-121">Se você tiver implantado políticas de acesso condicional com o Intune, garanta que você obteve as **licenças adequadas do EMS** ou do Azure AD Premium.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-121">If you have deployed conditional access policies with Intune, please ensure that you have obtained the proper Azure AD Premium or **EMS licenses**.</span></span>

- <span data-ttu-id="bf4f9-122">Saiba mais sobre a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-122">Learn more about [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

<span data-ttu-id="bf4f9-123">Além disso, garanta que os usuários aos quais você pretende aplicar as políticas de acesso condicional [recebem as licenças do Azure AD Premium ou do EMS](/intune/licenses-assign).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-123">Additionally, make sure the users you plan to apply conditional access policies are [assigned with the Azure AD Premium or EMS licenses](/intune/licenses-assign).</span></span>

### <span data-ttu-id="bf4f9-124">Configurações de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf4f9-124">Device compliance settings</span></span>
<a id="device-compliance-settings" class="xliff"></a>

<span data-ttu-id="bf4f9-125">Para configurar o acesso condicional, configure uma política de conformidade do dispositivo e uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-125">To set up conditional access, configure a device compliance policy and a conditional access policy.</span></span> <span data-ttu-id="bf4f9-126">A política de conformidade inclui configurações como senha, criptografia e se um dispositivo tem ou não jailbreak.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-126">The compliance policy includes settings like passcode, encryption, and whether or not a device is jailbroken.</span></span> <span data-ttu-id="bf4f9-127">O dispositivo deve atender a essas regras para ser considerado compatível.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-127">The device must meet these rules in order to be considered compliant.</span></span>

- <span data-ttu-id="bf4f9-128">Saiba mais sobre a [política de conformidade do dispositivo e como ela funciona](introduction-to-device-compliance-policies-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-128">Learn more about [device compliance policy and how it works](introduction-to-device-compliance-policies-in-microsoft-intune.md).</span></span>

### <span data-ttu-id="bf4f9-129">Política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="bf4f9-129">Conditional access policy</span></span>
<a id="conditional-access-policy" class="xliff"></a>

<span data-ttu-id="bf4f9-130">Você pode definir uma política de acesso condicional para proteger o acesso com base em:</span><span class="sxs-lookup"><span data-stu-id="bf4f9-130">You can set a conditional access policy to protect access based on:</span></span>
- <span data-ttu-id="bf4f9-131">Status de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-131">The device compliance status.</span></span>
- <span data-ttu-id="bf4f9-132">Plataforma em execução no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-132">The platform that is running on the device.</span></span>
- <span data-ttu-id="bf4f9-133">Tipos de aplicativos usados para acessar os serviços.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-133">The type of apps that are used to access the services.</span></span>

<span data-ttu-id="bf4f9-134">Ao contrário de outras políticas do Intune, você não implanta políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-134">Unlike other Intune policies, you don't deploy conditional access policies.</span></span> <span data-ttu-id="bf4f9-135">Em vez disso, depois de configurar a política e selecionar os usuários que devem ter a política, a política é aplicada a todos os usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-135">Instead, after you configure the policy and select the users that should have the policy, the policy is applied to all targeted users.</span></span> <span data-ttu-id="bf4f9-136">Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.</span><span class="sxs-lookup"><span data-stu-id="bf4f9-136">When a user is targeted by a policy, each device they use must be compliant in order for them to access resources.</span></span>


## <span data-ttu-id="bf4f9-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bf4f9-137">Next steps</span></span>
<a id="next-steps" class="xliff"></a>


2. <span data-ttu-id="bf4f9-138">[Criar uma política de conformidade do dispositivo](create-a-device-compliance-policy-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="bf4f9-138">[Create a device compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).</span></span>

2.  <span data-ttu-id="bf4f9-139">Criar uma política de acesso condicional para um dos seguintes produtos/serviços em nuvem da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="bf4f9-139">Create a conditional access policy for one of the following Microsoft cloud services/product:</span></span>

  - [<span data-ttu-id="bf4f9-140">Criar uma política de acesso condicional para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bf4f9-140">Create a conditional access policy for Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [<span data-ttu-id="bf4f9-141">Criar uma política de acesso condicional para o Exchange Local</span><span class="sxs-lookup"><span data-stu-id="bf4f9-141">Create a conditional access policy for Exchange On-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [<span data-ttu-id="bf4f9-142">Criar uma política de acesso condicional para o novo Exchange Online Dedicado</span><span class="sxs-lookup"><span data-stu-id="bf4f9-142">Create a conditional access policy for new Exchange Online Dedicated</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
  - [<span data-ttu-id="bf4f9-143">Criar uma política de acesso condicional para o Exchange Online Dedicado herdado</span><span class="sxs-lookup"><span data-stu-id="bf4f9-143">Create a conditional access policy for legacy Exchange Online Dedicated</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  - [<span data-ttu-id="bf4f9-144">Criar uma política de acesso condicional para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bf4f9-144">Create a conditional access policy for SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  - [<span data-ttu-id="bf4f9-145">Criar uma política de acesso condicional para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bf4f9-145">Create a conditional access policy for Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  - [<span data-ttu-id="bf4f9-146">Criar uma política de acesso condicional para o Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="bf4f9-146">Create a conditional access policy for Dynamics CRM Online</span></span>](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
