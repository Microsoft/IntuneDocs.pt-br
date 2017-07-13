---
title: Proteger o SharePoint Online
description: Proteja e controle o acesso aos dados da empresa no SharePoint Online usando o acesso condicional.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b088e5a0-fd4a-4fe7-aa49-cb9c8cfb1585
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e22686964df7415ece75361a645103006af43c51
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="5ff1c-103">Proteger o acesso ao SharePoint Online com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5ff1c-103">Protect access to SharePoint Online with Microsoft Intune</span></span>
<a id="protect-access-to-sharepoint-online-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5ff1c-104">Use o acesso condicional do Microsoft Intune para controlar o acesso a arquivos localizados no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-104">Use Microsoft Intune conditional access to control access to files that are located on SharePoint Online.</span></span>
<span data-ttu-id="5ff1c-105">O acesso condicional tem dois componentes:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-105">Conditional access has two components:</span></span>
- <span data-ttu-id="5ff1c-106">Uma política de conformidade do dispositivo, com a qual o dispositivo deve estar em conformidade para ser considerado compatível.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-106">A device compliance policy that the device must comply with in order to be considered compliant.</span></span>
- <span data-ttu-id="5ff1c-107">Uma política de acesso condicional, na qual você especifica as condições que o dispositivo deve atender para acessar o serviço.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-107">A conditional access policy where you specify the conditions that the device must meet in order to access the service.</span></span>
<span data-ttu-id="5ff1c-108">Para saber mais sobre como funciona o acesso condicional, leia o tópico [Proteger o acesso ao email, O365 e outros serviços](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-108">To learn more about how conditional access works, read the [Protect access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) topic.</span></span>

<span data-ttu-id="5ff1c-109">Você implanta a conformidade e políticas de acesso condicional para os usuários.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-109">You deploy the compliance and conditional access policies to users.</span></span> <span data-ttu-id="5ff1c-110">Qualquer dispositivo que o usuário utiliza para acessar os serviços é verificado quanto à conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-110">Any device that a user uses to access the services is checked for compliance with the policies.</span></span>

<span data-ttu-id="5ff1c-111">Quando um usuário tenta se conectar a um arquivo usando um aplicativo com suporte em seu dispositivo, como o OneDrive, ocorre a seguinte avaliação:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-111">When a user attempts to connect to a file by using a supported app such as OneDrive on their device, the following evaluation occurs:</span></span>

![Diagrama que mostra os pontos de decisão que determinam se um dispositivo tem acesso permitido ou bloqueado ao SharePoint](../media/ConditionalAccess8-6.png)


<span data-ttu-id="5ff1c-113">**Antes** de configurar uma política de acesso condicional para o SharePoint Online, você precisa:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-113">**Before** configuring a conditional access policy for SharePoint Online, you must:</span></span>
- <span data-ttu-id="5ff1c-114">Ter uma **assinatura do SharePoint Online** e os usuários devem ser licenciados para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-114">Have a **SharePoint Online subscription**, and users must be licensed for SharePoint Online.</span></span>
- <span data-ttu-id="5ff1c-115">Ter uma **assinatura do Enterprise Mobility + Security** ou do **Azure Active Directory Premium** e ter os usuários licenciados para o EMS ou o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-115">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="5ff1c-116">Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-116">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>


  <span data-ttu-id="5ff1c-117">Para se conectar aos arquivos necessários, o dispositivo precisa:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-117">To connect to the required files, a device must be:</span></span>
-   <span data-ttu-id="5ff1c-118">**Registrado** no Intune ou em um PC ingressado no domínio.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-118">**Enrolled** with Intune or a domain-joined PC.</span></span>

-   <span data-ttu-id="5ff1c-119">**Registrado** no Azure Active Directory (isso ocorre automaticamente quando o dispositivo for registrado com o Intune).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-119">**Registered** in Azure Active Directory (this happens automatically when the device is enrolled with Intune).</span></span>


-   <span data-ttu-id="5ff1c-120">**Compatível** com qualquer política de conformidade do Intune implantada.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-120">**Compliant** with any deployed Intune compliance policies.</span></span>

<span data-ttu-id="5ff1c-121">O estado do dispositivo é armazenado no Azure Active Directory, que concede ou bloqueia o acesso a arquivos com base nas condições que você especifica.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-121">The device state is stored in Azure Active Directory, which grants or blocks access to the files, based on the conditions that you specify.</span></span>

<span data-ttu-id="5ff1c-122">Se uma condição não for atendida, o usuário receberá uma das seguintes mensagens ao entrar:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-122">If a condition isn't met, the user sees one of the following messages when they sign in:</span></span>

-   <span data-ttu-id="5ff1c-123">Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa e registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-123">If the device isn't enrolled with Intune or isn't registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>

-   <span data-ttu-id="5ff1c-124">Se o dispositivo não for compatível, será exibida uma mensagem que direciona o usuário ao site do Portal da Empresa do Intune, no qual ele pode encontrar informações sobre o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-124">If the device isn't compliant, a message is displayed that directs the user to the Intune Company Portal website, where they can find information about the problem and how to remediate it.</span></span>

<span data-ttu-id="5ff1c-125">**O acesso condicional não se aplica ao compartilhamento externo**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-125">**Conditional access doesn't apply to external sharing**.</span></span> <span data-ttu-id="5ff1c-126">Para saber como evitar o compartilhamento externo em seu locatário ou conjunto de sites, consulte [Gerenciar o compartilhamento externo para o ambiente do SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-126">To learn how to prevent external sharing in your tenant or site collection, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85).</span></span>

>[!NOTE]
><span data-ttu-id="5ff1c-127">Se você habilitar o acesso condicional para o SharePoint Online, recomendamos que desabilite o domínio na lista, conforme descrito no tópico [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-127">If you enable conditional access for SharePoint Online, we recommend that you disable the domain on the list, as described in the [Remove-SPOTenantSyncClientRestriction](https://technet.microsoft.com/library/dn917451.aspx) topic.</span></span>  

## <span data-ttu-id="5ff1c-128">Suporte para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="5ff1c-128">Support for mobile devices</span></span>
<a id="support-for-mobile-devices" class="xliff"></a>
<span data-ttu-id="5ff1c-129">Há suporte para os recursos a seguir:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-129">The following are supported:</span></span>
- <span data-ttu-id="5ff1c-130">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5ff1c-130">iOS 8.0 and later</span></span>
- <span data-ttu-id="5ff1c-131">Android 4.0 e posterior, Samsung Knox Standard 4.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="5ff1c-131">Android 4.0 and later, Samsung Knox Standard 4.0 or later</span></span>
- <span data-ttu-id="5ff1c-132">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="5ff1c-132">Windows Phone 8.1 and later</span></span>

<span data-ttu-id="5ff1c-133">É possível proteger o acesso ao SharePoint Online quando acessado por um navegador em dispositivos **iOS** e **Android**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-133">You can protect access to SharePoint Online when **iOS** and **Android** devices access it from a browser.</span></span> <span data-ttu-id="5ff1c-134">O acesso será permitido somente de navegadores com suporte em dispositivos compatíveis:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-134">Access is only allowed from supported browsers on compliant devices:</span></span>
* <span data-ttu-id="5ff1c-135">Safari (iOS)</span><span class="sxs-lookup"><span data-stu-id="5ff1c-135">Safari (iOS)</span></span>
* <span data-ttu-id="5ff1c-136">Chrome (Android)</span><span class="sxs-lookup"><span data-stu-id="5ff1c-136">Chrome (Android)</span></span>
* <span data-ttu-id="5ff1c-137">Intune Managed Browser (iOS e Android 5.0 e posteriores)</span><span class="sxs-lookup"><span data-stu-id="5ff1c-137">Intune Managed Browser (iOS and Android 5.0 and later)</span></span>

<span data-ttu-id="5ff1c-138">**Navegadores sem suporte serão bloqueados**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-138">**Unsupported browsers are blocked**.</span></span>

## <span data-ttu-id="5ff1c-139">Suporte para computadores</span><span class="sxs-lookup"><span data-stu-id="5ff1c-139">Support for PCs</span></span>
<a id="support-for-pcs" class="xliff"></a>
<span data-ttu-id="5ff1c-140">Há suporte para os recursos a seguir:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-140">The following are supported:</span></span>
- <span data-ttu-id="5ff1c-141">Windows 8.1 e posterior (quando os computadores são registrado com o Intune)</span><span class="sxs-lookup"><span data-stu-id="5ff1c-141">Windows 8.1 and later (when PCs are enrolled with Intune)</span></span>
- <span data-ttu-id="5ff1c-142">Windows 7.0, Windows 8.1 ou Windows 10 (quando os computadores estão ingressados no domínio),</span><span class="sxs-lookup"><span data-stu-id="5ff1c-142">Windows 7.0, Windows 8.1, or Windows 10 (when PCs are domain joined),</span></span>
> [!NOTE]
><span data-ttu-id="5ff1c-143">Para usar o acesso condicional em PCs com Windows 10, você deve atualizar esses PCs com a Atualização de Aniversário do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-143">To use conditional access with Windows 10 PCs, you must update those PCs with the Windows 10 Anniversary Update.</span></span>

  - <span data-ttu-id="5ff1c-144">Computadores ingressados no domínio devem ser configurados para [se registrarem automaticamente](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-144">You must set up domain-joined PCs to [automatically register](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.</span></span> <span data-ttu-id="5ff1c-145">O Registro de Dispositivos do Azure AD será ativado automaticamente para clientes do Intune e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-145">The Azure AD Device Registration service will be activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="5ff1c-146">Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-146">Customers who have already deployed the ADFS Device Registration service will not see registered devices in on-premises Active Directory.</span></span>

  - <span data-ttu-id="5ff1c-147">Se a política estiver definida para exigir o ingresso no domínio e o computador não estiver ingressado no domínio, uma mensagem será exibida para que o usuário entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-147">If the policy is set to require a domain join and the PC isn't domain joined, a message is displayed to contact the IT admin.</span></span>

  - <span data-ttu-id="5ff1c-148">Se a política estiver definida para exigir ingresso no domínio ou conformidade e o computador não atender a nenhum dos dois requisitos, será exibida uma mensagem com instruções sobre como instalar o aplicativo do Portal da Empresa e realizar o registro.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-148">If the policy is set to require a domain join or compliance, and the PC doesn't meet either requirement, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>
  >[!NOTE]
  ><span data-ttu-id="5ff1c-149">Não há suporte ao acesso condicional em computadores que executam o cliente de computador Intune.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-149">Conditional access is not supported on PCs that are running the Intune computer client.</span></span>

<span data-ttu-id="5ff1c-150">[A autenticação moderna do Office 365 deve estar habilitada](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) e ter todas as atualizações mais recentes do Office.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-150">[Office 365 modern authentication must be enabled](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) and have all the latest Office updates.</span></span>

<span data-ttu-id="5ff1c-151">A autenticação moderna leva as credenciais baseadas na ADAL (Biblioteca de Autenticação do Active Directory) aos clientes Windows com Office 2013 e permite mais segurança, como a **autenticação multifator** e a **autenticação baseada em certificado**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-151">Modern authentication brings sign-in based on Active Directory Authentication Library (ADAL) to Office 2013 Windows clients and enables better security, like **multi-factor authentication** and **certificate-based authentication**.</span></span>


## <span data-ttu-id="5ff1c-152">Configurar o acesso condicional para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ff1c-152">Configure conditional access for SharePoint Online</span></span>
<a id="configure-conditional-access-for-sharepoint-online" class="xliff"></a>

### <span data-ttu-id="5ff1c-153">Etapa 1: Configurar grupos de segurança do Active Directory</span><span class="sxs-lookup"><span data-stu-id="5ff1c-153">Step 1: Configure Active Directory security groups</span></span>
<a id="step-1-configure-active-directory-security-groups" class="xliff"></a>
<span data-ttu-id="5ff1c-154">Antes de começar, configure os grupos de segurança do Active Directory do Azure para a política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-154">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="5ff1c-155">É possível configurar esses grupos no **Centro de administração do Office 365** ou no **Portal de conta do Intune**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-155">You can configure these groups in the **Office 365 admin center** or in the **Intune account portal**.</span></span> <span data-ttu-id="5ff1c-156">Use esses grupos para afetar ou isentar os usuários da política.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-156">You use these groups to target or exempt users from the policy.</span></span> <span data-ttu-id="5ff1c-157">Quando um usuário é afetado por uma política, cada dispositivo que ele usa deve ser compatível para que possa acessar os recursos.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-157">When a user is targeted by a policy, each device that they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="5ff1c-158">Você pode especificar dois tipos de grupo em uma política do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-158">You can specify two group types in a SharePoint Online policy:</span></span>

-   <span data-ttu-id="5ff1c-159">**Grupos de destino**: contém grupos de usuários aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-159">**Targeted groups**: Contains groups of users that the policy applies to.</span></span>

-   <span data-ttu-id="5ff1c-160">**Grupos isentos**: contém grupos de usuários isentos da política.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-160">**Exempted groups**: Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="5ff1c-161">Se um usuário estiver nos dois grupos, ele ficará isento da política.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-161">If a user is in both groups, they are exempt from the policy.</span></span>

### <span data-ttu-id="5ff1c-162">Etapa 2: Configurar e implantar uma política de conformidade</span><span class="sxs-lookup"><span data-stu-id="5ff1c-162">Step 2: Configure and deploy a compliance policy</span></span>
<a id="step-2-configure-and-deploy-a-compliance-policy" class="xliff"></a>
<span data-ttu-id="5ff1c-163">Se ainda não tiver feito isso, crie e implante uma política de conformidade para todos os usuários aos quais a política do SharePoint Online se destinará.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-163">If you haven't already done so, create a compliance policy, and deploy it to the users that the SharePoint Online policy targets.</span></span>

> [!NOTE]
> <span data-ttu-id="5ff1c-164">Enquanto as políticas de conformidade são implantadas em grupos do Intune, as políticas de acesso condicional são destinadas a grupos de segurança do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-164">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>

<span data-ttu-id="5ff1c-165">Para obter detalhes sobre como configurar a política de conformidade, consulte [Criar uma política de conformidade](create-a-device-compliance-policy-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-165">For details about how to configure the compliance policy, see [Create a compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ff1c-166">Se você não tiver implantado uma política de conformidade, os dispositivos serão tratados como compatíveis.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-166">If you haven't deployed a compliance policy, the devices are treated as compliant.</span></span>

<span data-ttu-id="5ff1c-167">Quando estiver pronto, continue na **Etapa 3**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-167">When you're ready, continue to **Step 3**.</span></span>

### <span data-ttu-id="5ff1c-168">Etapa 3: Configurar a política do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5ff1c-168">Step 3: Configure the SharePoint Online policy</span></span>
<a id="step-3-configure-the-sharepoint-online-policy" class="xliff"></a>
<span data-ttu-id="5ff1c-169">Em seguida, configure a política para exigir que somente dispositivos gerenciados e compatíveis possam acessar o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-169">Next, configure the policy to require that only managed and compliant devices can access SharePoint Online.</span></span> <span data-ttu-id="5ff1c-170">Essa política será armazenada no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-170">This policy is stored in Azure Active Directory.</span></span>

#### <a name="bkmk_spopolicy"></a>

>[!NOTE]
> <span data-ttu-id="5ff1c-171">Também é possível criar uma política de acesso condicional para dispositivos do Intune no console de gerenciamento do Azure AD (a política é conhecida como o **política de acesso condicional com base no dispositivo** no Azure AD).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-171">You can also create a conditional access policy for Intune devices in the Azure AD management console (the policy is referred to as the **device-based conditional access policy** in Azure AD).</span></span> <span data-ttu-id="5ff1c-172">Além disso, é possível criar outras políticas de acesso condicional, como a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-172">In addition, you can create other conditional access policies like multi-factor authentication.</span></span> <span data-ttu-id="5ff1c-173">Também é possível definir políticas de acesso condicional para aplicativos empresariais de terceiros com suporte do Azure AD, como Salesforce e Box.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-173">You can also set conditional access policies for third-party enterprise apps that Azure AD supports, like Salesforce and Box.</span></span> <span data-ttu-id="5ff1c-174">Para obter mais detalhes, consulte [Como definir a política de acesso condicional com base no dispositivo do Azure Active Directory para controle de acesso dos aplicativos conectados do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-174">For more details, see [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).</span></span>


1.  <span data-ttu-id="5ff1c-175">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Acesso Condicional** > **Política do SharePoint Online**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-175">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **SharePoint Online Policy**.</span></span>
<span data-ttu-id="5ff1c-176">![Captura de tela da página de Política do SharePoint Online](../media/mdm-ca-spo-policy-configuration.png)</span><span class="sxs-lookup"><span data-stu-id="5ff1c-176">![Screenshot of the SharePoint Online Policy page](../media/mdm-ca-spo-policy-configuration.png)</span></span>

2.  <span data-ttu-id="5ff1c-177">Selecione **Habilitar política de acesso condicional para o SharePoint Online**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-177">Select **Enable conditional access policy for SharePoint Online**.</span></span>

3.  <span data-ttu-id="5ff1c-178">Em **Acesso ao aplicativo**, é possível optar por aplicar a política de acesso condicional a:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-178">Under **Application access**, you can choose to apply the conditional access policy to:</span></span>

    -   <span data-ttu-id="5ff1c-179">**Todas as plataformas**</span><span class="sxs-lookup"><span data-stu-id="5ff1c-179">**All platforms**</span></span>

        <span data-ttu-id="5ff1c-180">Isso requer que qualquer dispositivo usado para acessar o **SharePoint Online** seja registrado no Intune e esteja compatível com as políticas.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-180">This requires that any device used to access **SharePoint Online** is enrolled in Intune and is compliant with the policies.</span></span> <span data-ttu-id="5ff1c-181">Qualquer aplicativo cliente que use a **autenticação moderna** está sujeito à política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-181">Any client application that uses **modern authentication** is subject to the conditional access policy.</span></span> <span data-ttu-id="5ff1c-182">Se a plataforma não tiver suporte do Intune, o acesso ao **SharePoint Online** será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-182">If the platform isn't currently supported by Intune, access to **SharePoint Online** is blocked.</span></span>

        <span data-ttu-id="5ff1c-183">Selecionar a opção **Todas as plataformas** significa que o Azure Active Directory aplicará essa política a todas as solicitações de autenticação, independentemente da plataforma relatada pelo aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-183">Selecting the **All platforms** option means that Azure Active Directory applies this policy to all authentication requests, regardless of the platform that is reported by the client application.</span></span> <span data-ttu-id="5ff1c-184">Todas as plataformas precisarão ser registradas e se tornarem compatíveis, exceto:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-184">All platforms are required to be enrolled and become compliant, except for:</span></span>
        *   <span data-ttu-id="5ff1c-185">Dispositivos Windows, que precisarão ser registrados e compatíveis, ingressados no domínio com o Active Directory local ou ambas as opções.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-185">Windows devices, which are required to be enrolled and compliant, domain joined with on-premises Active Directory, or both.</span></span>
        * <span data-ttu-id="5ff1c-186">Plataformas sem suporte, como Mac.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-186">Unsupported platforms like Mac.</span></span> <span data-ttu-id="5ff1c-187">No entanto, os aplicativos que usam autenticação moderna provenientes dessas plataformas ainda estarão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-187">However, apps using modern authentication that come from these platforms are still blocked.</span></span>

    -   <span data-ttu-id="5ff1c-188">**Plataformas específicas**</span><span class="sxs-lookup"><span data-stu-id="5ff1c-188">**Specific platforms**</span></span>

         <span data-ttu-id="5ff1c-189">A política de acesso condicional se aplicará a qualquer aplicativo cliente que usar a autenticação moderna nas plataformas que você especificar.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-189">The conditional access policy applies to any client app that is using modern authentication on the platforms that you specify.</span></span>

     <span data-ttu-id="5ff1c-190">Para computadores Windows, este deve estar ingressado no domínio ou então ser registrado no Intune e ser compatível.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-190">For Windows PCs, a PC must either be domain joined, or enrolled with Intune and compliant.</span></span> <span data-ttu-id="5ff1c-191">Você pode definir os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-191">You can set the following requirements:</span></span>

     -   <span data-ttu-id="5ff1c-192">**Os dispositivos devem estar ingressados no domínio ou ser compatíveis.**</span><span class="sxs-lookup"><span data-stu-id="5ff1c-192">**Devices must be domain joined or compliant.**</span></span> <span data-ttu-id="5ff1c-193">Escolha essa opção se quiser que os computadores estejam ingressados no domínio ou sejam compatíveis com as políticas definidas no Intune.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-193">Choose this option to require that PCs must either be domain joined or compliant with the policies that are set in Intune.</span></span> <span data-ttu-id="5ff1c-194">Se um computador não atender a esses requisitos, será solicitado que o usuário registre o dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-194">If a PC doesn't meet either of these requirements, the user is prompted to enroll the device with Intune.</span></span>

     -   <span data-ttu-id="5ff1c-195">**Os dispositivos devem ser compatíveis.**</span><span class="sxs-lookup"><span data-stu-id="5ff1c-195">**Devices must be compliant.**</span></span> <span data-ttu-id="5ff1c-196">Escolha essa opção para exigir que os computadores sejam compatíveis e estejam registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-196">Choose this option to require that PCs must be enrolled in Intune and compliant.</span></span> <span data-ttu-id="5ff1c-197">Se um computador não estiver registrado, será exibida uma mensagem com instruções sobre como registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-197">If a PC isn't enrolled, a message with instructions on how to enroll is displayed.</span></span>

4.   <span data-ttu-id="5ff1c-198">Em **Acesso do navegador** ao SharePoint Online e OneDrive for Business, é possível optar por permitir o acesso ao Exchange Online somente por meio de navegadores com suporte: Safari (iOS) e Chrome (Android).</span><span class="sxs-lookup"><span data-stu-id="5ff1c-198">Under **Browser access** to SharePoint Online and OneDrive for Business, you can choose to allow access to Exchange Online only through the supported browsers: Safari (iOS) and Chrome (Android).</span></span> <span data-ttu-id="5ff1c-199">O acesso de outros navegadores será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-199">Access from other browsers is blocked.</span></span> <span data-ttu-id="5ff1c-200">As mesmas restrições de plataforma que você selecionou para acesso de aplicativo para o OneDrive também se aplicam aqui.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-200">The same platform restrictions that you selected for Application access for OneDrive also apply here.</span></span>

  <span data-ttu-id="5ff1c-201">Em dispositivos **Android**, os usuários devem habilitar o acesso do navegador.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-201">On **Android** devices, users must enable browser access.</span></span> <span data-ttu-id="5ff1c-202">Para isso, o usuário deve habilitar a opção **Habilitar Acesso do Navegador** no dispositivo registrado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-202">To do this, a user must choose the **Enable Browser Access** option on the enrolled device as follows:</span></span>
  1.    <span data-ttu-id="5ff1c-203">Abra o aplicativo do **Portal da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-203">Open the **Company Portal** app.</span></span>
  2.    <span data-ttu-id="5ff1c-204">Vá para a página **Configurações** por meio das reticências (...) ou do botão de menu do hardware.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-204">Go to the **Settings** page from the ellipsis (…) or hardware menu button.</span></span>
  3.    <span data-ttu-id="5ff1c-205">Pressione o botão **Habilitar Acesso do Navegador**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-205">Press the **Enable Browser Access** button.</span></span>
  4.    <span data-ttu-id="5ff1c-206">No navegador Chrome, saia do Office 365 e reinicie o Chrome.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-206">In the Chrome browser, sign out of Office 365 and restart Chrome.</span></span>

  <span data-ttu-id="5ff1c-207">Em plataformas **iOS** e **Android**, para identificar o dispositivo usado para acessar o serviço, o Azure Active Directory emite um certificado de protocolo TLS para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-207">On **iOS** and **Android** platforms, to identify the device that is used to access the service, Azure Active Directory issues a Transport Layer Security (TLS) certificate to the device.</span></span> <span data-ttu-id="5ff1c-208">O dispositivo exibe o certificado com uma solicitação ao usuário final para selecionar o certificado, conforme mostrado nas capturas de tela a seguir.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-208">The device displays the certificate with a prompt to the user to select the certificate, as shown in the following screenshots.</span></span> <span data-ttu-id="5ff1c-209">O usuário deve selecionar esse certificado antes que seja possível usar o navegador.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-209">The user must select this certificate before they can use the browser.</span></span>

  <span data-ttu-id="5ff1c-210">**iOS**</span><span class="sxs-lookup"><span data-stu-id="5ff1c-210">**iOS**</span></span>

  ![Captura de tela da solicitação de certificado em um iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

  <span data-ttu-id="5ff1c-212">**Android**</span><span class="sxs-lookup"><span data-stu-id="5ff1c-212">**Android**</span></span>

  ![Captura de tela da solicitação de certificado em um dispositivo Android](../media/mdm-browser-ca-android-cert-prompt.png)
5.  <span data-ttu-id="5ff1c-214">Em **Grupos de Destino**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-214">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy applies to.</span></span> <span data-ttu-id="5ff1c-215">Você pode optar por aplicá-la a todos os usuários ou apenas a um grupos seleto de usuários.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-215">You can choose to target this to all users or just a select group of users.</span></span>

6.  <span data-ttu-id="5ff1c-216">Opcionalmente, em **Grupos Isentos**, escolha **Modificar** para selecionar os grupos de segurança do Azure Active Directory que são isentos dessa política.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-216">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>

7.  <span data-ttu-id="5ff1c-217">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-217">When you're done, choose **Save**.</span></span>

<span data-ttu-id="5ff1c-218">Não é necessário implantar a política de acesso condicional, ela entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-218">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>

### <span data-ttu-id="5ff1c-219">Etapa 4: monitorar políticas de acesso condicional e conformidade</span><span class="sxs-lookup"><span data-stu-id="5ff1c-219">Step 4: Monitor the compliance and conditional access policies</span></span>
<a id="step-4-monitor-the-compliance-and-conditional-access-policies" class="xliff"></a>
<span data-ttu-id="5ff1c-220">No espaço de trabalho **Grupos**, você pode exibir o status de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-220">In the **Groups** workspace, you can view the status of your devices.</span></span>

<span data-ttu-id="5ff1c-221">Selecione qualquer grupo de dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-221">Select any mobile device group.</span></span> <span data-ttu-id="5ff1c-222">Em seguida, na guia **Dispositivos**, escolha um dos seguintes **Filtros**:</span><span class="sxs-lookup"><span data-stu-id="5ff1c-222">Then, on the **Devices** tab, choose one of the following **Filters**:</span></span>

-   <span data-ttu-id="5ff1c-223">**Dispositivos não registrados com o AAD**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-223">**Devices that are not registered with AAD**.</span></span> <span data-ttu-id="5ff1c-224">Esses dispositivos estão bloqueados do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-224">These devices are blocked from SharePoint Online.</span></span>

-   <span data-ttu-id="5ff1c-225">**Dispositivos que não são compatíveis**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-225">**Devices that are not compliant**.</span></span> <span data-ttu-id="5ff1c-226">Esses dispositivos estão bloqueados do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-226">These devices are blocked from SharePoint Online.</span></span>

-   <span data-ttu-id="5ff1c-227">**Dispositivos registrados com o AAD e que são compatíveis**.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-227">**Devices that are registered with AAD and compliant**.</span></span> <span data-ttu-id="5ff1c-228">Esses dispositivos podem acessar o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5ff1c-228">These devices can access SharePoint Online.</span></span>

### <span data-ttu-id="5ff1c-229">Consulte também</span><span class="sxs-lookup"><span data-stu-id="5ff1c-229">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="5ff1c-230">Proteger o acesso a email e serviços do O365 com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5ff1c-230">Protect access to email and O365 services with Microsoft Intune</span></span>](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)
