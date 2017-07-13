---
title: Proteger o Skype for Business Online
description: Proteja e controle o acesso ao Skype for Business Online usando o acesso condicional.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c2d6a00f99047e4b18821e81da0c36b988e36c2a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2f081-103">Proteger o acesso ao Skype for Business Online com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2f081-103">Protect access to Skype for Business Online with Microsoft Intune</span></span>
<a id="protect-access-to-skype-for-business-online-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2f081-104">Use a política de acesso condicional para controlar o acesso ao **Skype for Business Online**.</span><span class="sxs-lookup"><span data-stu-id="2f081-104">You can use a conditional access policy for **Skype for Business Online** to control access to Skype for Business Online.</span></span>
<span data-ttu-id="2f081-105">O acesso condicional tem dois componentes:</span><span class="sxs-lookup"><span data-stu-id="2f081-105">Conditional access has two components:</span></span>
- <span data-ttu-id="2f081-106">Uma política de conformidade do dispositivo, com a qual o dispositivo deve estar em conformidade para ser considerado compatível.</span><span class="sxs-lookup"><span data-stu-id="2f081-106">A device compliance policy that the device must comply with in order to be considered compliant.</span></span>
- <span data-ttu-id="2f081-107">Uma política de acesso condicional, na qual você especifica as condições que o dispositivo deve atender para acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="2f081-107">A conditional access policy where you specify the conditions that the device must meet in order for you to access the service.</span></span>
<span data-ttu-id="2f081-108">Para saber mais sobre como o acesso condicional funciona, leia o artigo [Proteger acesso a email e a serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="2f081-108">To learn more about how conditional access works, read the [Protect access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

<span data-ttu-id="2f081-109">Quando um determinado usuário tenta usar o Skype for Business Online em seu dispositivo, ocorre a seguinte avaliação:</span><span class="sxs-lookup"><span data-stu-id="2f081-109">When a targeted user attempts to use Skype for Business Online on their device, the following evaluation occurs:</span></span>

![Diagrama que mostra os pontos de decisão usados para determinar se um dispositivo tem acesso permitido ou bloqueado ao Skype for Business Online](../media/ConditionalAccess_SkypeforBusiness.png)

<span data-ttu-id="2f081-111">**Antes** de configurar uma política de acesso condicional para o Skype for Business Online, você precisa:</span><span class="sxs-lookup"><span data-stu-id="2f081-111">**Before** configuring a conditional access policy for Skype for Business Online, you must:</span></span>
- <span data-ttu-id="2f081-112">Ter uma **assinatura do Skype for Business Online** e atribuir a licença do Skype for Business Online aos usuários.</span><span class="sxs-lookup"><span data-stu-id="2f081-112">Have a **Skype for Business Online subscription** and assign the Skype for Business Online license to users.</span></span>
- <span data-ttu-id="2f081-113">Ter uma **assinatura do Enterprise Mobility + Security** ou do **Azure Active Directory Premium** e ter os usuários licenciados para o EMS ou o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f081-113">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and have users be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="2f081-114">Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="2f081-114">For more details, see [Enterprise Mobility pricing](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

-   <span data-ttu-id="2f081-115">[Habilitar a autenticação moderna](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) para o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f081-115">[Enable modern authentication](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) for Skype for Business Online.</span></span>
-  <span data-ttu-id="2f081-116">Todos os seus usuários devem estar usando o **Skype for Business Online**.</span><span class="sxs-lookup"><span data-stu-id="2f081-116">Have all your users using **Skype for Business Online**.</span></span> <span data-ttu-id="2f081-117">Se você tiver uma implantação com o Skype for Business Online e o Skype for Business local, a política de acesso condicional não será aplicada aos usuários.</span><span class="sxs-lookup"><span data-stu-id="2f081-117">If you have a deployment with both Skype for Business Online and Skype for Business on-premises, the conditional access policy will not be applied to users.</span></span>

<span data-ttu-id="2f081-118">O dispositivo que precisa acessar o Skype for Business Online deve:</span><span class="sxs-lookup"><span data-stu-id="2f081-118">The device that needs access to Skype for Business Online must:</span></span>

-   <span data-ttu-id="2f081-119">Ser um dispositivo **Android** ou **iOS**.</span><span class="sxs-lookup"><span data-stu-id="2f081-119">Be an **Android** or **iOS** device.</span></span>

-   <span data-ttu-id="2f081-120">Estar **registrado** no Intune.</span><span class="sxs-lookup"><span data-stu-id="2f081-120">Be **enrolled** with Intune.</span></span>

-   <span data-ttu-id="2f081-121">Ser **compatível** com qualquer política de conformidade do Intune implantada.</span><span class="sxs-lookup"><span data-stu-id="2f081-121">Be **compliant** with any deployed Intune compliance policies.</span></span>


<span data-ttu-id="2f081-122">O estado do dispositivo é armazenado no Azure Active Directory, que concede ou bloqueia o acesso com base nas condições que você especificar.</span><span class="sxs-lookup"><span data-stu-id="2f081-122">The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.</span></span>

<span data-ttu-id="2f081-123">Se uma condição não for atendida, o usuário receberá uma das seguintes mensagens de erro ao se conectar:</span><span class="sxs-lookup"><span data-stu-id="2f081-123">If a condition is not met, the user is presented with one of the following messages when they sign in:</span></span>

-   <span data-ttu-id="2f081-124">Se o dispositivo não estiver registrado no Intune ou no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa e registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="2f081-124">If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>

-   <span data-ttu-id="2f081-125">Se o dispositivo não for compatível, será exibida uma mensagem que direciona o usuário para o site do Portal da Empresa do Intune ou para o aplicativo do Portal da Empresa, no qual ele pode encontrar informações sobre o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="2f081-125">If the device is not compliant, a message is displayed that directs the user to the Intune Company Portal website or Company Portal app, where they can find information about the problem and how to fix it.</span></span>

## <span data-ttu-id="2f081-126">Configurar o acesso condicional ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2f081-126">Configure conditional access for Skype for Business Online</span></span>
<a id="configure-conditional-access-for-skype-for-business-online" class="xliff"></a>

### <span data-ttu-id="2f081-127">Etapa 1: Configurar grupos de segurança do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2f081-127">Step 1: Configure Azure Active Directory security groups</span></span>
<a id="step-1-configure-azure-active-directory-security-groups" class="xliff"></a>
<span data-ttu-id="2f081-128">Antes de começar, configure os grupos de segurança do Active Directory do Azure para a política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2f081-128">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="2f081-129">Você pode configurar esses grupos no **Centro de administração do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2f081-129">You can configure these groups in the **Office 365 admin center**.</span></span> <span data-ttu-id="2f081-130">Esses grupos serão usados para afetar ou isentar os usuários da política.</span><span class="sxs-lookup"><span data-stu-id="2f081-130">These groups will be used to target or exempt users from the policy.</span></span> <span data-ttu-id="2f081-131">Quando um usuário é afetado pela política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.</span><span class="sxs-lookup"><span data-stu-id="2f081-131">When a user is targeted by the policy, each device they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="2f081-132">Você pode especificar dois tipos de grupos para usar com a política do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="2f081-132">You can specify two group types to use for the Skype for Business policy:</span></span>

-   <span data-ttu-id="2f081-133">**Grupos de destino**: contém grupos de usuários aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="2f081-133">**Targeted groups**: Contains groups of users that the policy applies to.</span></span>

-   <span data-ttu-id="2f081-134">**Grupos isentos**: contém grupos de usuários isentos da política.</span><span class="sxs-lookup"><span data-stu-id="2f081-134">**Exempted groups**: Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="2f081-135">Se um usuário estiver nos dois grupos, ele ficará isento da política.</span><span class="sxs-lookup"><span data-stu-id="2f081-135">If a user is in both groups, they will be exempt from the policy.</span></span>

### <span data-ttu-id="2f081-136">Etapa 2: Configurar e implantar uma política de conformidade</span><span class="sxs-lookup"><span data-stu-id="2f081-136">Step 2: Configure and deploy a compliance policy</span></span>
<a id="step-2-configure-and-deploy-a-compliance-policy" class="xliff"></a>
<span data-ttu-id="2f081-137">[Crie](create-a-device-compliance-policy-in-microsoft-intune.md) e [implante](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) uma política de conformidade para todos os dispositivos que serão afetados pela política.</span><span class="sxs-lookup"><span data-stu-id="2f081-137">[Create](create-a-device-compliance-policy-in-microsoft-intune.md) and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy to all devices that will be affected by the policy.</span></span> <span data-ttu-id="2f081-138">Esses seriam todos os dispositivos usados pelos usuários nos **Grupos de destino**.</span><span class="sxs-lookup"><span data-stu-id="2f081-138">These will be all the devices that are used by the users in the **Targeted groups**.</span></span>

> [!NOTE]
> <span data-ttu-id="2f081-139">Enquanto as políticas de conformidade são implantadas em grupos do Intune, as políticas de acesso condicional são destinadas a grupos de segurança do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f081-139">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2f081-140">Se você não tiver implantado uma política de conformidade, os dispositivos serão tratados como compatíveis.</span><span class="sxs-lookup"><span data-stu-id="2f081-140">If you haven't deployed a compliance policy, the devices will be treated as compliant.</span></span>

<span data-ttu-id="2f081-141">Quando estiver pronto, continue na **Etapa 3**.</span><span class="sxs-lookup"><span data-stu-id="2f081-141">When you're ready, continue to **Step 3**.</span></span>

### <span data-ttu-id="2f081-142">Etapa 3: Configurar a política do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2f081-142">Step 3: Configure the Skype for Business Online policy</span></span>
<a id="step-3-configure-the-skype-for-business-online-policy" class="xliff"></a>
<span data-ttu-id="2f081-143">Em seguida, configure a política para exigir que somente dispositivos gerenciados e compatíveis possam acessar o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f081-143">Next, configure the policy to require that only managed and compliant devices can access Skype for Business Online.</span></span> <span data-ttu-id="2f081-144">Essa política será armazenada no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2f081-144">This policy will be stored in Azure Active Directory.</span></span>

1.  <span data-ttu-id="2f081-145">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Acesso Condicional** > **Política do Skype for Business Online**.</span><span class="sxs-lookup"><span data-stu-id="2f081-145">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **Skype for Business Online Policy**.</span></span>

  ![Captura de tela da página de política de acesso condicional do Skype for Business Online](./media/conditional_access_SFBPolicy.png)

2.  <span data-ttu-id="2f081-147">Selecione **Habilitar política de acesso condicional**.</span><span class="sxs-lookup"><span data-stu-id="2f081-147">Choose **Enable conditional access policy**.</span></span>

3.  <span data-ttu-id="2f081-148">Em **Acesso ao aplicativo**, você pode optar por aplicar a política de acesso condicional a:</span><span class="sxs-lookup"><span data-stu-id="2f081-148">Under **Application access**, you can choose to apply conditional access policy to:</span></span>

    -   <span data-ttu-id="2f081-149">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2f081-149">**iOS**</span></span>

    -   <span data-ttu-id="2f081-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="2f081-150">**Android**</span></span>

4.  <span data-ttu-id="2f081-151">Em **Grupos de Destino**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory aos quais a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="2f081-151">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to.</span></span> <span data-ttu-id="2f081-152">Você pode optar por aplicá-la a todos os usuários ou apenas a um grupos seleto de usuários.</span><span class="sxs-lookup"><span data-stu-id="2f081-152">You can choose to target this to all users or just a select group of users.</span></span>

5.  <span data-ttu-id="2f081-153">Opcionalmente, em **Grupos Isentos**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory que são isentos dessa política.</span><span class="sxs-lookup"><span data-stu-id="2f081-153">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>

6.  <span data-ttu-id="2f081-154">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2f081-154">When you're done, choose **Save**.</span></span>

<span data-ttu-id="2f081-155">Você configurou o acesso condicional ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f081-155">You have now configured conditional access for Skype for Business Online.</span></span> <span data-ttu-id="2f081-156">Não é necessário implantar a política de acesso condicional, ela entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2f081-156">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>


## <span data-ttu-id="2f081-157">Monitorar a conformidade e políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2f081-157">Monitor the compliance and conditional access policies</span></span>
<a id="monitor-the-compliance-and-conditional-access-policies" class="xliff"></a>
<span data-ttu-id="2f081-158">No espaço de trabalho **Grupos** , você pode exibir o status de acesso condicional de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f081-158">In the **Groups** workspace, you can view the conditional access status of your devices.</span></span>

<span data-ttu-id="2f081-159">Selecione qualquer grupo de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="2f081-159">Select any mobile device group.</span></span> <span data-ttu-id="2f081-160">Em seguida, na guia **Dispositivos**, escolha um dos seguintes **Filtros**:</span><span class="sxs-lookup"><span data-stu-id="2f081-160">Then, on the **Devices** tab, choose one of the following **Filters**:</span></span>

* <span data-ttu-id="2f081-161">**Dispositivos que não estão registrados com o AAD**: esses dispositivos estão bloqueados do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f081-161">**Devices that are not registered with AAD**: These devices are blocked from Skype for Business Online.</span></span>

* <span data-ttu-id="2f081-162">**Dispositivos que não são compatíveis**: esses dispositivos estão bloqueados do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f081-162">**Devices that are not compliant**: These devices are blocked from Skype for Business Online.</span></span>

* <span data-ttu-id="2f081-163">**Dispositivos registrados com o AAD e que são compatíveis**: esses dispositivos podem acessar o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f081-163">**Devices that are registered with AAD and compliant**: These devices can access Skype for Business Online.</span></span>
