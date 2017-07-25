---
title: Proteger o Dynamics CRM Online
description: Proteja e controle o acesso ao Dynamics CRM Online com acesso condicional.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: da92d75cfafa2a605ed8606ba7c8f3ec18dc6063
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="99dc2-103">Proteger o acesso ao Dynamics CRM Online com o Intune</span><span class="sxs-lookup"><span data-stu-id="99dc2-103">Protect access to Dynamics CRM Online with Intune</span></span>
<a id="protect-access-to-dynamics-crm-online-with-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="99dc2-104">É possível controlar o acesso ao Microsoft Dynamics CRM Online de dispositivos iOS e Android usando acesso condicional do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="99dc2-104">You can control access to Microsoft Dynamics CRM Online from iOS and Android devices by using Microsoft Intune conditional access.</span></span>  <span data-ttu-id="99dc2-105">Acesso condicional do Intune tem dois componentes:</span><span class="sxs-lookup"><span data-stu-id="99dc2-105">Intune conditional access has two components:</span></span>
* <span data-ttu-id="99dc2-106">Uma [política de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md), com a qual o dispositivo deve estar em conformidade para ser considerado compatível.</span><span class="sxs-lookup"><span data-stu-id="99dc2-106">A [device compliance policy](introduction-to-device-compliance-policies-in-microsoft-intune.md) that the device must comply with in order to be considered compliant.</span></span>
* <span data-ttu-id="99dc2-107">Uma [política de acesso condicional](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), na qual você especifica as condições que o dispositivo deve atender para acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="99dc2-107">A [conditional access policy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) where you specify the conditions that the device must meet in order to access the service.</span></span>

<span data-ttu-id="99dc2-108">Para saber mais sobre como o acesso condicional funciona, leia o artigo [Protect access to email, 0365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (Proteger o acesso ao email, O365 e outros serviços).</span><span class="sxs-lookup"><span data-stu-id="99dc2-108">To learn more about how conditional access works, read the [protect access to email, 0365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99dc2-109">Para implantar o acesso condicional, é necessário ter assinaturas do Intune e do Azure Active Directory Premium e os usuários devem estar licenciados para ambos os produtos.</span><span class="sxs-lookup"><span data-stu-id="99dc2-109">To deploy conditional access, you must have subscriptions for Intune and Azure Active Directory Premium, and users must be licensed for both products.</span></span> <span data-ttu-id="99dc2-110">A **assinatura do EMS (Enterprise Mobility + Security)** inclui tanto assinaturas do Intune quanto do Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="99dc2-110">The **Enterprise Mobility + Security (EMS) subscription** includes both Intune and Azure Active Directory Premium subscriptions.</span></span> <span data-ttu-id="99dc2-111">Para obter mais detalhes, consulte a página de preços do [Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing).</span><span class="sxs-lookup"><span data-stu-id="99dc2-111">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing).</span></span> <span data-ttu-id="99dc2-112">Se você não tiver a assinatura do EMS, poderá obter uma assinatura para o Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="99dc2-112">If you don't have the EMS subscription, you can get a subscription for Azure Active Directory Premium.</span></span> <span data-ttu-id="99dc2-113">Veja a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="99dc2-113">See the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

<span data-ttu-id="99dc2-114">Quando um determinado usuário tenta usar o aplicativo Dynamics CRM em seu dispositivo, ocorre a seguinte avaliação:</span><span class="sxs-lookup"><span data-stu-id="99dc2-114">When a targeted user attempts to use the Dynamics CRM app on their device, the following evaluation occurs:</span></span>

![Diagrama que mostra os pontos de decisão usados para determinar se um dispositivo tem acesso permitido ou bloqueado a um serviço](../media/mdm-ca-dynamics-crm-flow-diagram.png)

<span data-ttu-id="99dc2-116">O dispositivo que precisa acessar o Dynamics CRM Online deve ser:</span><span class="sxs-lookup"><span data-stu-id="99dc2-116">The device that needs access to Dynamics CRM Online must be:</span></span>
* <span data-ttu-id="99dc2-117">**Android** ou **iOS**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-117">An **Android** or **iOS** device.</span></span>
* <span data-ttu-id="99dc2-118">**Registrado** no Intune.</span><span class="sxs-lookup"><span data-stu-id="99dc2-118">**Enrolled** with Intune.</span></span>
* <span data-ttu-id="99dc2-119">**Compatível** com qualquer política de conformidade do Intune implantada.</span><span class="sxs-lookup"><span data-stu-id="99dc2-119">**Compliant** with any deployed Intune compliance policies.</span></span>

<span data-ttu-id="99dc2-120">O estado do dispositivo é armazenado no Azure Active Directory, que concede ou bloqueia o acesso com base nas condições que você especificar.</span><span class="sxs-lookup"><span data-stu-id="99dc2-120">The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.</span></span>

<span data-ttu-id="99dc2-121">Se uma condição não for atendida, o usuário receberá uma das seguintes mensagens de erro ao se conectar:</span><span class="sxs-lookup"><span data-stu-id="99dc2-121">If a condition is not met, the user is presented with one of the following messages when they sign in:</span></span>
* <span data-ttu-id="99dc2-122">Se o dispositivo não estiver registrado no Intune ou no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa e registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="99dc2-122">If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>
* <span data-ttu-id="99dc2-123">Se o dispositivo não for compatível, será exibida uma mensagem que direciona o usuário ao site do Portal da Empresa do Microsoft Intune ou ao aplicativo do Portal da Empresa, em que ele pode encontrar informações sobre o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="99dc2-123">If the device is not compliant, a message is displayed that directs the user to the Microsoft Intune Company Portal website or Company Portal app, where they can find information about the problem and how to remediate it.</span></span>

## <span data-ttu-id="99dc2-124">Configurar acesso condicional para o Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="99dc2-124">Configure conditional access for Dynamics CRM Online</span></span>
<a id="configure-conditional-access-for-dynamics-crm-online" class="xliff"></a>  
### <span data-ttu-id="99dc2-125">Etapa 1: Configurar grupos de segurança do Active Directory</span><span class="sxs-lookup"><span data-stu-id="99dc2-125">Step 1: Configure Active Directory security groups</span></span>
<a id="step-1-configure-active-directory-security-groups" class="xliff"></a>

<span data-ttu-id="99dc2-126">Antes de começar, configure os grupos de segurança do Active Directory do Azure para a política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="99dc2-126">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="99dc2-127">Você pode configurar esses grupos no **Centro de administração do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-127">You can configure these groups in the **Office 365 admin center**.</span></span> <span data-ttu-id="99dc2-128">Use esses grupos para afetar ou isentar os usuários da política.</span><span class="sxs-lookup"><span data-stu-id="99dc2-128">You use these groups to target or exempt users from the policy.</span></span> <span data-ttu-id="99dc2-129">Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.</span><span class="sxs-lookup"><span data-stu-id="99dc2-129">When a user is targeted by a policy, each device they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="99dc2-130">Você pode especificar dois tipos de grupos para usar com a política do Dynamics CRM:</span><span class="sxs-lookup"><span data-stu-id="99dc2-130">You can specify two group types to use for the Dynamics CRM policy:</span></span>
* <span data-ttu-id="99dc2-131">**Grupos de destino**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-131">**Targeted groups**.</span></span> <span data-ttu-id="99dc2-132">Contém grupos de usuários aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="99dc2-132">Contains groups of users that the policy applies to.</span></span>
* <span data-ttu-id="99dc2-133">**Grupos isentos**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-133">**Exempted groups**.</span></span> <span data-ttu-id="99dc2-134">Contém grupos de usuários isentos da política.</span><span class="sxs-lookup"><span data-stu-id="99dc2-134">Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="99dc2-135">Se um usuário estiver nos dois grupos, ele ficará isento da política.</span><span class="sxs-lookup"><span data-stu-id="99dc2-135">If a user is in both groups, they are exempt from the policy.</span></span>

### <span data-ttu-id="99dc2-136">Etapa 2: Configurar e implantar uma política de conformidade</span><span class="sxs-lookup"><span data-stu-id="99dc2-136">Step 2: Configure and deploy a compliance policy</span></span>
<a id="step-2-configure-and-deploy-a-compliance-policy" class="xliff"></a>
<span data-ttu-id="99dc2-137">[Crie](create-a-device-compliance-policy-in-microsoft-intune.md) e [implante](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) uma política de conformidade para todos os dispositivos que serão afetados pela política.</span><span class="sxs-lookup"><span data-stu-id="99dc2-137">[Create](create-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) it to all devices that will be affected by the policy.</span></span> <span data-ttu-id="99dc2-138">Esses são todos os dispositivos usados pelos usuários nos Grupos de destino.</span><span class="sxs-lookup"><span data-stu-id="99dc2-138">These are all the devices that are used by the users in the Targeted groups.</span></span>

> [!NOTE]
> <span data-ttu-id="99dc2-139">Enquanto as políticas de conformidade são implantadas em grupos do Intune, as políticas de acesso condicional são destinadas a grupos de segurança do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99dc2-139">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99dc2-140">Se você não tiver implantado uma política de conformidade, os dispositivos serão tratados como compatíveis.</span><span class="sxs-lookup"><span data-stu-id="99dc2-140">If you have not deployed a compliance policy, the devices will be treated as compliant.</span></span>

<span data-ttu-id="99dc2-141">Quando estiver pronto, continue na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="99dc2-141">When you are ready, continue to Step 3.</span></span>
### <span data-ttu-id="99dc2-142">Etapa 3: Configurar a política do Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="99dc2-142">Step 3: Configure the Dynamics CRM policy</span></span>
<a id="step-3-configure-the-dynamics-crm-policy" class="xliff"></a>
<span data-ttu-id="99dc2-143">Em seguida, configure a política para exigir que somente dispositivos gerenciados e compatíveis possam acessar o Dynamics CRM.</span><span class="sxs-lookup"><span data-stu-id="99dc2-143">Next, configure the policy to require that only managed and compliant devices can access Dynamics CRM.</span></span> <span data-ttu-id="99dc2-144">Essa política será armazenada no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99dc2-144">This policy will be stored in Azure Active Directory.</span></span>

1.  <span data-ttu-id="99dc2-145">No console de administração do Intune, escolha **Política > Acesso Condicional > Política do Dynamics CRM Online**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-145">In the Intune administration console, choose **Policy > Conditional Access > Dynamics CRM Online Policy**.</span></span>

  ![Captura de tela da página de política de acesso condicional do Dynamics CRM Online](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2.  <span data-ttu-id="99dc2-147">Escolha **Habilitar política de acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-147">Choose the **Enable conditional access** policy.</span></span>
3.  <span data-ttu-id="99dc2-148">Em **Acesso ao aplicativo**, você pode optar por aplicar a política de acesso condicional a:</span><span class="sxs-lookup"><span data-stu-id="99dc2-148">Under **Application access**, you can choose to apply conditional access policy to:</span></span>
  * <span data-ttu-id="99dc2-149">**iOS**</span><span class="sxs-lookup"><span data-stu-id="99dc2-149">**iOS**</span></span>
  * <span data-ttu-id="99dc2-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="99dc2-150">**Android**</span></span>
4.  <span data-ttu-id="99dc2-151">Em **Grupos de Destino**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory aos quais a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="99dc2-151">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to.</span></span> <span data-ttu-id="99dc2-152">Você pode optar por aplicá-la a todos os usuários ou apenas a um grupos seleto de usuários.</span><span class="sxs-lookup"><span data-stu-id="99dc2-152">You can choose to target this to all users or just a select group of users.</span></span>
5.  <span data-ttu-id="99dc2-153">Opcionalmente, em **Grupos Isentos**, escolha em **Modificar** para selecionar os grupos de segurança do Azure Active Directory que são isentos dessa política.</span><span class="sxs-lookup"><span data-stu-id="99dc2-153">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>
6.  <span data-ttu-id="99dc2-154">Quando terminar, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-154">When you are done, choose **Save**.</span></span>

<span data-ttu-id="99dc2-155">Você configurou o acesso condicional ao Dynamics CRM.</span><span class="sxs-lookup"><span data-stu-id="99dc2-155">You have now configured conditional access for Dynamics CRM.</span></span> <span data-ttu-id="99dc2-156">Não é necessário implantar a política de acesso condicional, ela entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="99dc2-156">You do not have to deploy the conditional access policy—it takes effect immediately.</span></span>
##  <span data-ttu-id="99dc2-157">Monitorar a conformidade e políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="99dc2-157">Monitor the compliance and conditional access policies</span></span>
<a id="monitor-the-compliance-and-conditional-access-policies" class="xliff"></a>

<span data-ttu-id="99dc2-158">No espaço de trabalho **Grupos** , você pode exibir o status de acesso condicional de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="99dc2-158">In the **Groups** workspace, you can view the conditional access status of your devices.</span></span>

<span data-ttu-id="99dc2-159">Escolha qualquer grupo de dispositivos móveis e, então, na guia **Dispositivos**, escolha um dos seguintes **Filtros**:</span><span class="sxs-lookup"><span data-stu-id="99dc2-159">Choose any mobile device group and then, on the **Devices** tab, choose one of the following **Filters**:</span></span>
* <span data-ttu-id="99dc2-160">**Dispositivos não registrados com o AAD**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-160">**Devices that are not registered with AAD**.</span></span> <span data-ttu-id="99dc2-161">Esses dispositivos estão bloqueados do Dynamics CRM.</span><span class="sxs-lookup"><span data-stu-id="99dc2-161">These devices are blocked from Dynamics CRM.</span></span>
* <span data-ttu-id="99dc2-162">**Dispositivos que não são compatíveis**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-162">**Devices that are not compliant**.</span></span> <span data-ttu-id="99dc2-163">Esses dispositivos estão bloqueados do Dynamics CRM.</span><span class="sxs-lookup"><span data-stu-id="99dc2-163">These devices are blocked from Dynamics CRM.</span></span>
* <span data-ttu-id="99dc2-164">**Dispositivos registrados com o AAD e que são compatíveis**.</span><span class="sxs-lookup"><span data-stu-id="99dc2-164">**Devices that are registered with AAD and compliant**.</span></span> <span data-ttu-id="99dc2-165">Esses dispositivos podem acessar o Dynamics CRM.</span><span class="sxs-lookup"><span data-stu-id="99dc2-165">These devices can access Dynamics CRM.</span></span>

##  <span data-ttu-id="99dc2-166">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="99dc2-166">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
* [<span data-ttu-id="99dc2-167">Proteger o acesso ao Exchange Online</span><span class="sxs-lookup"><span data-stu-id="99dc2-167">Protect access to Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [<span data-ttu-id="99dc2-168">Proteger o acesso ao Exchange local</span><span class="sxs-lookup"><span data-stu-id="99dc2-168">Protect access to Exchange on-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [<span data-ttu-id="99dc2-169">Proteger o acesso ao SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="99dc2-169">Protect access to SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [<span data-ttu-id="99dc2-170">Proteger o acesso ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="99dc2-170">Protect access to Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
