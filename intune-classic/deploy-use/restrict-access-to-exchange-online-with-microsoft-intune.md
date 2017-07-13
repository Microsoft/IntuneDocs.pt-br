---
title: <span data-ttu-id="2154c-101">Proteger o email no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2154c-101">Protect email to Exchange Online</span></span>
description: <span data-ttu-id="2154c-102">Proteja e controle o acesso ao email da empresa no Exchange Online com acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-102">Protect and control access to company email on Exchange Online with conditional access.</span></span>
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09c82f5d-531c-474d-add6-784c83f96d93
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c428d7f01872c9f0968bb69dc4dc1886a7c1828b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2154c-103">Proteger o acesso ao email no Exchange Online e ao novo Exchange Online Dedicado com o Intune</span><span class="sxs-lookup"><span data-stu-id="2154c-103">Protect email access to Exchange Online and new Exchange Online Dedicated with Intune</span></span>
<a id="protect-email-access-to-exchange-online-and-new-exchange-online-dedicated-with-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2154c-104">Você pode configurar o acesso condicional para o Exchange Online ou Exchange Online Dedicado usando o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-104">You can configure conditional access for Exchange Online or Exchange Online Dedicated by using Microsoft Intune.</span></span> <span data-ttu-id="2154c-105">Para saber mais sobre como funciona o acesso condicional, leia o artigo [Proteger o acesso ao email, O365 e outros serviços](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="2154c-105">To learn more about how conditional access works, read the [Protect access to email, O365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

> [!NOTE]
><span data-ttu-id="2154c-106">Se você tiver um ambiente do Exchange Online Dedicado e precisar descobrir se ele está com a configuração nova ou herdada, contate seu gerente de conta.</span><span class="sxs-lookup"><span data-stu-id="2154c-106">If you have an Exchange Online Dedicated environment and need to find out whether it's in the new or the legacy configuration, contact your account manager.</span></span>

## <span data-ttu-id="2154c-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="2154c-107">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="2154c-108">Para configurar o acesso condicional, você deve:</span><span class="sxs-lookup"><span data-stu-id="2154c-108">To configure conditional access, you must:</span></span>

-   <span data-ttu-id="2154c-109">Ter uma **assinatura do Office 365 que inclui o Exchange Online (como E3)**; além disso, os usuários devem ser licenciados para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2154c-109">Have an **Office 365 subscription that includes Exchange Online (such as E3)**, and users must be licensed for Exchange Online.</span></span>

- <span data-ttu-id="2154c-110">Ter uma **assinatura do Enterprise Mobility + Security** ou do **Azure Active Directory Premium** e ter os usuários licenciados para o EMS ou o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2154c-110">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="2154c-111">Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="2154c-111">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

-  <span data-ttu-id="2154c-112">Considere a configuração do **conector serviço a serviço opcional do Intune**, que conecta o Intune ao Exchange Online e ajuda você a gerenciar as informações do dispositivo por meio do console do Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-112">Consider configuring the optional **Intune service-to-service connector**, which connects Intune to Exchange Online and helps you manage device information through the Intune console.</span></span> <span data-ttu-id="2154c-113">Você não precisa usar o conector para usar políticas de conformidade ou políticas de acesso condicional, mas ele é necessário para executar relatórios que ajudam a avaliar o impacto do acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-113">You don't need to use the connector to use compliance policies or conditional access policies—but it's required to run reports that help evaluate the impact of conditional access.</span></span>
    -  <span data-ttu-id="2154c-114">Saiba mais sobre o [Intune Service to Service Connector](intune-service-to-service-exchange-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2154c-114">Learn more about the [Intune service-to-service connector](intune-service-to-service-exchange-connector.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="2154c-115">Não configure o Intune Service to Service Connector se você pretende usar o acesso condicional para o Exchange Online e o Exchange local.</span><span class="sxs-lookup"><span data-stu-id="2154c-115">Do not configure the Intune service-to-service connector if you intend to use conditional access for both Exchange Online and Exchange on-premises.</span></span>

### <span data-ttu-id="2154c-116">Requisitos de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2154c-116">Device compliance requirements</span></span>
<a id="device-compliance-requirements" class="xliff"></a>

<span data-ttu-id="2154c-117">Ao configurar políticas de acesso condicional e direcioná-las a um usuário, antes que um usuário possa se conectar a seu email, o **dispositivo** usado deve ser/estar:</span><span class="sxs-lookup"><span data-stu-id="2154c-117">When you configure conditional access policies and target them to a user, before a user can connect to their email, the **device** they use must be:</span></span>

-   <span data-ttu-id="2154c-118">Um computador ingressado no domínio ou **registrado** no Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-118">A domain-joined PC or **enrolled** with Intune.</span></span>

-  <span data-ttu-id="2154c-119">**Registrado no Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="2154c-119">**Registered in Azure Active Directory**.</span></span> <span data-ttu-id="2154c-120">Isso ocorre automaticamente quando o dispositivo é registrado com Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-120">This happens automatically when the device is enrolled with Intune.</span></span> <span data-ttu-id="2154c-121">Além disso, a ID do Exchange ActiveSync do cliente deve estar registrada com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2154c-121">Additionally, the client Exchange ActiveSync ID must be registered with Azure Active Directory.</span></span>

  <span data-ttu-id="2154c-122">O serviço Registro do Dispositivo do Azure Active Directory é ativado automaticamente para clientes do Intune e Office 365.</span><span class="sxs-lookup"><span data-stu-id="2154c-122">The Azure Active Directory Device Registration service is activated automatically for Intune and Office 365 customers.</span></span> <span data-ttu-id="2154c-123">Clientes que já tiverem implantado o Serviço de Registro de Dispositivos do ADFS não verão dispositivos registrados no seu Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="2154c-123">Customers who have already deployed the ADFS Device Registration service will not see registered devices in on-premises Active Directory.</span></span>

-   <span data-ttu-id="2154c-124">**Em conformidade** com todas as políticas de conformidade do Intune implantadas nesse dispositivo ou ingressadas no domínio em um domínio local.</span><span class="sxs-lookup"><span data-stu-id="2154c-124">**Compliant** with any Intune compliance policies that are deployed to that device or domain joined to an on-premises domain.</span></span>

### <span data-ttu-id="2154c-125">Quando o dispositivo não for compatível</span><span class="sxs-lookup"><span data-stu-id="2154c-125">When the device is not compliant</span></span>
<a id="when-the-device-is-not-compliant" class="xliff"></a>

<span data-ttu-id="2154c-126">Se uma política de acesso condicional não for atendida, o dispositivo será colocado imediatamente em quarentena e o usuário receberá um email com uma das seguintes notificações de quarentena ao entrar:</span><span class="sxs-lookup"><span data-stu-id="2154c-126">If a conditional access policy isn't met, the device gets immediately quarantined, and the user receives an e-mail and sees one of the following quarantine notifications when they sign in:</span></span>

- <span data-ttu-id="2154c-127">Se o dispositivo não estiver registrado no Intune ou não estiver registrado no Azure Active Directory, será exibida uma mensagem com instruções sobre como instalar o aplicativo Portal da Empresa, registrar o dispositivo e ativar o email.</span><span class="sxs-lookup"><span data-stu-id="2154c-127">If the device isn't enrolled with Intune or isn't registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app, enroll the device, and activate email.</span></span> <span data-ttu-id="2154c-128">Esse processo também associa a ID do Exchange ActiveSync do dispositivo com o registro no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2154c-128">This process also associates the device’s Exchange ActiveSync ID with the record in Azure Active Directory.</span></span>

-   <span data-ttu-id="2154c-129">Se o dispositivo for avaliado como não estando em conformidade com as regras da política de conformidade, o usuário será direcionado para o site do Portal da Empresa do Intune ou para o aplicativo Portal da Empresa, em que poderá encontrar informações sobre o problema e como corrigi-lo.</span><span class="sxs-lookup"><span data-stu-id="2154c-129">If the device is evaluated as not compliant with the compliance policy rules, the user is directed to the Intune Company Portal website or the Company Portal app, where they can find information about the problem and how to remediate it.</span></span>

### <span data-ttu-id="2154c-130">Como o acesso condicional funciona com o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2154c-130">How conditional access works with Exchange Online</span></span>
<a id="how-conditional-access-works-with-exchange-online" class="xliff"></a>

<span data-ttu-id="2154c-131">O diagrama a seguir ilustra o fluxo usado pelas políticas de acesso condicional para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2154c-131">The following diagram illustrates the flow that is used by conditional access policies for Exchange Online.</span></span>

![Diagrama que ilustra os pontos de decisões que determinam se um dispositivo tem permissão de acesso ou está bloqueado](../media/ConditionalAccess8-1.png)

## <span data-ttu-id="2154c-133">Suporte para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="2154c-133">Support for mobile devices</span></span>
<a id="support-for-mobile-devices" class="xliff"></a>
<span data-ttu-id="2154c-134">É possível proteger o acesso ao email do Exchange Online no **Outlook** e em outros **aplicativos que usam a autenticação moderna**.</span><span class="sxs-lookup"><span data-stu-id="2154c-134">You can protect access to Exchange Online email from **Outlook** and other **apps that use modern authentication**.</span></span> <span data-ttu-id="2154c-135">Há suporte para os recursos a seguir:</span><span class="sxs-lookup"><span data-stu-id="2154c-135">The following are supported:</span></span>

- <span data-ttu-id="2154c-136">Android 4.0 e posterior, Samsung Knox Standard 4.0 e posterior e Android for Work</span><span class="sxs-lookup"><span data-stu-id="2154c-136">Android 4.0 and later, Samsung Knox Standard 4.0 and later, and Android for Work</span></span>
- <span data-ttu-id="2154c-137">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2154c-137">iOS 8.0 and later</span></span>

<span data-ttu-id="2154c-138">A **autenticação moderna** leva a conexão baseada no ADAL (Biblioteca de Autenticação do Active Directory) para os clientes do Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="2154c-138">**Modern authentication** brings sign-in based on Active Directory Authentication Library (ADAL) to Microsoft Office clients.</span></span>

-   <span data-ttu-id="2154c-139">A autenticação baseada em ADAL permite que os clientes do Office participem da autenticação baseada em navegador (também conhecida como autenticação passiva).</span><span class="sxs-lookup"><span data-stu-id="2154c-139">The ADAL-based authentication enables Office clients to engage in browser-based authentication (also known as passive authentication).</span></span> <span data-ttu-id="2154c-140">Para se autenticar, um usuário é direcionado para uma página da Web de conexão.</span><span class="sxs-lookup"><span data-stu-id="2154c-140">To authenticate, a user is directed to a sign-in web page.</span></span>
-   <span data-ttu-id="2154c-141">Esse novo método de conexão permite uma melhor segurança, como a **autenticação multifator** e a **autenticação baseada em certificado**.</span><span class="sxs-lookup"><span data-stu-id="2154c-141">This new sign-in method enables better security like **multi-factor authentication** and **certificate-based authentication**.</span></span> <span data-ttu-id="2154c-142">Para obter informações mais detalhadas, consulte [Como funciona a autenticação moderna](https://support.office.com/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517).</span><span class="sxs-lookup"><span data-stu-id="2154c-142">For more detailed information, see [How modern authentication works](https://support.office.com/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517).</span></span> <span data-ttu-id="2154c-143">É possível configurar regras de declaração do ADFS para bloquear protocolos de autenticação não moderna.</span><span class="sxs-lookup"><span data-stu-id="2154c-143">You can set up ADFS claim rules to block non-modern authentication protocols.</span></span> <span data-ttu-id="2154c-144">Instruções detalhadas são fornecidas em [Cenário 3: bloquear todo o acesso ao O365, exceto para aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).</span><span class="sxs-lookup"><span data-stu-id="2154c-144">Detailed instructions are provided in [Scenario 3: Block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>

<span data-ttu-id="2154c-145">É possível proteger o acesso ao **OWA (Outlook Web Access)** no Exchange Online quando um usuário o acessa em um navegador em dispositivos **iOS** e **Android**.</span><span class="sxs-lookup"><span data-stu-id="2154c-145">You can protect access to **Outlook Web Access (OWA)** on Exchange Online when a user accesses it from a browser on **iOS** and **Android** devices.</span></span> <span data-ttu-id="2154c-146">O acesso será permitido somente de navegadores com suporte em dispositivos compatíveis:</span><span class="sxs-lookup"><span data-stu-id="2154c-146">Access is only allowed from supported browsers on compliant devices:</span></span>

* <span data-ttu-id="2154c-147">Safari (iOS)</span><span class="sxs-lookup"><span data-stu-id="2154c-147">Safari (iOS)</span></span>
* <span data-ttu-id="2154c-148">Chrome (Android)</span><span class="sxs-lookup"><span data-stu-id="2154c-148">Chrome (Android)</span></span>
* <span data-ttu-id="2154c-149">Intune Managed Browser (iOS, Android 5.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="2154c-149">Intune Managed Browser (iOS, Android 5.0 and later)</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2154c-150">**Navegadores sem suporte serão bloqueados**.</span><span class="sxs-lookup"><span data-stu-id="2154c-150">**Unsupported browsers are blocked**.</span></span>

<span data-ttu-id="2154c-151">**O aplicativo OWA para iOS e Android pode ser modificado para não usar a autenticação moderna e não há suporte para isso. O acesso do aplicativo OWA deve ser bloqueado por meio de regras de declaração do ADFS.**</span><span class="sxs-lookup"><span data-stu-id="2154c-151">**The OWA app for iOS and Android can be modified not to use modern authentication, and it isn't supported. Access from the OWA app must be blocked through ADFS claim rules.**</span></span>


<span data-ttu-id="2154c-152">Você pode proteger o acesso ao email no Exchange por meio do **cliente de email do Exchange ActiveSync** interno nas seguintes plataformas:</span><span class="sxs-lookup"><span data-stu-id="2154c-152">You can protect access to Exchange email from the built-in **Exchange ActiveSync email client** on the following platforms:</span></span>

- <span data-ttu-id="2154c-153">Android 4.0 e posterior, Samsung Knox Standard 4.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2154c-153">Android 4.0 and later, Samsung Knox Standard 4.0 and later</span></span>

- <span data-ttu-id="2154c-154">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2154c-154">iOS 8.0 and later</span></span>

- <span data-ttu-id="2154c-155">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="2154c-155">Windows Phone 8.1 and later</span></span>

## <span data-ttu-id="2154c-156">Suporte para computadores</span><span class="sxs-lookup"><span data-stu-id="2154c-156">Support for PCs</span></span>
<a id="support-for-pcs" class="xliff"></a>

<span data-ttu-id="2154c-157">É possível configurar o acesso condicional para computadores que executam aplicativos da área de trabalho do Office para acessar o **Exchange Online** e o **SharePoint Online** em computadores que atendem aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="2154c-157">You can set up conditional access for PCs that run Office desktop applications to access **Exchange Online** and **SharePoint Online** for PCs that meet the following requirements:</span></span>

-   <span data-ttu-id="2154c-158">O computador deve executar o Windows 7.0, Windows 8.1 ou Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2154c-158">The PC must be running Windows 7.0, Windows 8.1, or Windows 10.</span></span>

  >[!NOTE]
  > <span data-ttu-id="2154c-159">Para usar o acesso condicional em PCs com Windows 10, você deve atualizar esses PCs com a Atualização de Aniversário do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="2154c-159">To use conditional access with Windows 10 PCs, you must update those PCs with the Windows 10 Anniversary Update.</span></span>

  <span data-ttu-id="2154c-160">O computador deve estar ingressado no domínio ou deve ser compatível com as regras de políticas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="2154c-160">The PC must either be domain joined or compliant with the compliance policy rules.</span></span>

  <span data-ttu-id="2154c-161">Para ser considerado em compatível, o computador deve ser registrado no Intune e estar em conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="2154c-161">In order to be considered compliant, the PC must be enrolled in Intune and comply with the policies.</span></span>

  <span data-ttu-id="2154c-162">Para computadores ingressados no domínio, é necessário configurar o acesso condicional para [registrar o dispositivo automaticamente](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2154c-162">For domain-joined PCs, you must set up conditional access to [automatically register the device](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-automatic-device-registration/) with Azure Active Directory.</span></span>

  >[!NOTE]
    ><span data-ttu-id="2154c-163">Não há suporte para o acesso condicional em computadores que executam o cliente de computador do Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-163">Conditional access isn't supported on PCs that are running the Intune computer client.</span></span>

-   <span data-ttu-id="2154c-164">[A autenticação moderna do Office 365 deve estar habilitada](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) e ter todas as atualizações mais recentes do Office.</span><span class="sxs-lookup"><span data-stu-id="2154c-164">[Office 365 modern authentication must be enabled](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) and have all the latest Office updates.</span></span>

    <span data-ttu-id="2154c-165">A autenticação moderna leva a conexão baseada no ADAL (Biblioteca de Autenticação do Active Directory) para os clientes do Office 2013/Windows.</span><span class="sxs-lookup"><span data-stu-id="2154c-165">Modern authentication brings sign-in based on Active Directory Authentication Library (ADAL) to Office 2013/Windows clients.</span></span> <span data-ttu-id="2154c-166">Ela permite uma melhor segurança, como a **autenticação multifator** e a **autenticação baseada em certificado**.</span><span class="sxs-lookup"><span data-stu-id="2154c-166">It enables better security like **multi-factor authentication** and **certificate-based authentication**.</span></span>

-   <span data-ttu-id="2154c-167">As regras de declaração do ADFS são configuradas para bloquear protocolos de autenticação não modernos.</span><span class="sxs-lookup"><span data-stu-id="2154c-167">ADFS claim rules are set up to block non-modern authentication protocols.</span></span> <span data-ttu-id="2154c-168">Instruções detalhadas são fornecidas em [Cenário 3: bloquear todo o acesso ao O365, exceto para aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).</span><span class="sxs-lookup"><span data-stu-id="2154c-168">Detailed instructions are provided in [Scenario 3: Block all access to O365 except browser based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>

## <span data-ttu-id="2154c-169">Configurar acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2154c-169">Configure conditional access</span></span>
<a id="configure-conditional-access" class="xliff"></a>
### <span data-ttu-id="2154c-170">Etapa 1: configurar e implantar uma política de conformidade</span><span class="sxs-lookup"><span data-stu-id="2154c-170">Step 1: Configure and deploy a compliance policy</span></span>
<a id="step-1-configure-and-deploy-a-compliance-policy" class="xliff"></a>
<span data-ttu-id="2154c-171">Lembre-se de [criar](create-a-device-compliance-policy-in-microsoft-intune.md) e [implantar](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) uma política de conformidade para os grupos de usuários que também receberão a política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-171">Make sure you [create](create-a-device-compliance-policy-in-microsoft-intune.md) and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy to the user groups that will also get the conditional access policy.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="2154c-172">Se você ainda não tiver implantado nenhuma política de conformidade, os dispositivos serão considerados em conformidade e terão acesso ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="2154c-172">If you haven't deployed a compliance policy, the devices are considered compliant and are allowed access to Exchange.</span></span>

### <span data-ttu-id="2154c-173">Etapa 2: avaliar o efeito da política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2154c-173">Step 2: Evaluate the effect of the conditional access policy</span></span>
<a id="step-2-evaluate-the-effect-of-the-conditional-access-policy" class="xliff"></a>
<span data-ttu-id="2154c-174">Você pode usar os **Relatórios de Inventário de Dispositivos Móveis** para identificar quais dispositivos em sua organização serão impedidos de acessar o Exchange quando você configura uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-174">You can use the **Mobile Device Inventory Reports** to identify the devices that might be blocked from accessing Exchange after you configure the conditional access policy.</span></span>

<span data-ttu-id="2154c-175">Para fazer isso, configure uma conexão entre o Intune e o Exchange usando o [Conector entre serviços do Microsoft Intune](intune-service-to-service-exchange-connector.md).</span><span class="sxs-lookup"><span data-stu-id="2154c-175">To do this, configure a connection between Intune and Exchange by using the [Microsoft Intune service-to-service connector](intune-service-to-service-exchange-connector.md).</span></span>
1.  <span data-ttu-id="2154c-176">Navegue até **Relatórios** > **Relatórios de Inventário de Dispositivo Móvel**.</span><span class="sxs-lookup"><span data-stu-id="2154c-176">Navigate to **Reports** > **Mobile Device Inventory Reports**.</span></span>
<span data-ttu-id="2154c-177">![Captura de tela da página Relatórios de Inventário de Dispositivo Móvel](../media/IntuneSA2bMobileDeviceInventoryReport.png)</span><span class="sxs-lookup"><span data-stu-id="2154c-177">![Screenshot of the Mobile Device Inventory Reports page](../media/IntuneSA2bMobileDeviceInventoryReport.png)</span></span>

2.  <span data-ttu-id="2154c-178">Nos parâmetros do relatório, selecione o grupo do Intune que você deseja avaliar e, se necessário, as plataformas de dispositivo às quais a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="2154c-178">In the report parameters, select the Intune group that you want to evaluate and, if required, the device platforms that the policy will apply to.</span></span>
3.  <span data-ttu-id="2154c-179">Depois de selecionar os critérios que atendem às necessidades de sua organização, escolha **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="2154c-179">After you’ve selected the criteria that meets your organization’s needs, choose **View Report**.</span></span>
<span data-ttu-id="2154c-180">Um Visualizador de Relatórios é aberto em uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="2154c-180">The Report Viewer opens in a new window.</span></span>
<span data-ttu-id="2154c-181">![Captura de tela de um exemplo do relatório de inventário do dispositivo móvel](../media/IntuneSA2cViewReport.PNG)</span><span class="sxs-lookup"><span data-stu-id="2154c-181">![Screenshot of an sample mobile device inventory report](../media/IntuneSA2cViewReport.PNG)</span></span>

<span data-ttu-id="2154c-182">Depois de executar o relatório, examine essas quatro colunas para determinar se um usuário será bloqueado:</span><span class="sxs-lookup"><span data-stu-id="2154c-182">After you run the report, examine these four columns to determine whether a user will be blocked:</span></span>

-   <span data-ttu-id="2154c-183">**Canal de Gerenciamento**: indica se o dispositivo é gerenciado pelo Intune, pelo Exchange ActiveSync ou por ambos.</span><span class="sxs-lookup"><span data-stu-id="2154c-183">**Management Channel**: Indicates whether the device is managed by Intune, Exchange ActiveSync, or both.</span></span>

-   <span data-ttu-id="2154c-184">**Registrado no AAD**: indica se o dispositivo está registrado no Azure Active Directory (conhecido como Workplace Join).</span><span class="sxs-lookup"><span data-stu-id="2154c-184">**AAD Registered**: Indicates whether the device is registered with Azure Active Directory (known as Workplace Join).</span></span>

-   <span data-ttu-id="2154c-185">**Em Conformidade**: indica se o dispositivo está em conformidade com as políticas de conformidade implantadas.</span><span class="sxs-lookup"><span data-stu-id="2154c-185">**Compliant**: Indicates whether the device is compliant with any compliance policies that you deployed.</span></span>

-   <span data-ttu-id="2154c-186">**ID do Exchange ActiveSync**: dispositivos iOS e Android precisam ter sua ID do Exchange ActiveSync associada ao registro do dispositivo no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2154c-186">**Exchange ActiveSync ID**: iOS and Android devices are required to have their Exchange ActiveSync ID associated with the device registration record in Azure Active Directory.</span></span> <span data-ttu-id="2154c-187">Isso acontece quando um usuário escolhe o link **Ativar Email** no email de quarentena.</span><span class="sxs-lookup"><span data-stu-id="2154c-187">This happens when a user chooses the **Activate Email** link in the quarantine email.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2154c-188">Dispositivos Windows Phone sempre exibem um valor nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="2154c-188">Windows Phone devices always display a value in this column.</span></span>

<span data-ttu-id="2154c-189">Dispositivos que fazem parte de um grupo de destino são impedidos de acessar o Exchange, a menos que os valores da coluna correspondam aos valores listados na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="2154c-189">Devices that are part of a targeted group are blocked from accessing Exchange unless the column values match those listed in the following table:</span></span>

--------------------------
|<span data-ttu-id="2154c-190">Canal de Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="2154c-190">Management Channel</span></span>|<span data-ttu-id="2154c-191">Registrado no AAD</span><span class="sxs-lookup"><span data-stu-id="2154c-191">AAD Registered</span></span>|<span data-ttu-id="2154c-192">Compatível</span><span class="sxs-lookup"><span data-stu-id="2154c-192">Compliant</span></span>|<span data-ttu-id="2154c-193">ID do Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="2154c-193">Exchange ActiveSync ID</span></span>|<span data-ttu-id="2154c-194">Ação resultante</span><span class="sxs-lookup"><span data-stu-id="2154c-194">Resulting action</span></span>|
|----------------------|------------------|-------------|--------------------------|--------------------|
|<span data-ttu-id="2154c-195">**Gerenciado pelo Microsoft Intune e pelo Exchange ActiveSync**</span><span class="sxs-lookup"><span data-stu-id="2154c-195">**Managed by Microsoft Intune and Exchange ActiveSync**</span></span>|<span data-ttu-id="2154c-196">Sim</span><span class="sxs-lookup"><span data-stu-id="2154c-196">Yes</span></span>|<span data-ttu-id="2154c-197">Sim</span><span class="sxs-lookup"><span data-stu-id="2154c-197">Yes</span></span>|<span data-ttu-id="2154c-198">Um valor é exibido</span><span class="sxs-lookup"><span data-stu-id="2154c-198">A value is displayed</span></span>|<span data-ttu-id="2154c-199">O acesso ao email é permitido</span><span class="sxs-lookup"><span data-stu-id="2154c-199">Email access is allowed</span></span>|
|<span data-ttu-id="2154c-200">Qualquer outro valor</span><span class="sxs-lookup"><span data-stu-id="2154c-200">Any other value</span></span>|<span data-ttu-id="2154c-201">Não</span><span class="sxs-lookup"><span data-stu-id="2154c-201">No</span></span>|<span data-ttu-id="2154c-202">Não</span><span class="sxs-lookup"><span data-stu-id="2154c-202">No</span></span>|<span data-ttu-id="2154c-203">Nenhum valor é exibido</span><span class="sxs-lookup"><span data-stu-id="2154c-203">No value is displayed</span></span>|<span data-ttu-id="2154c-204">O acesso ao email é bloqueado</span><span class="sxs-lookup"><span data-stu-id="2154c-204">Email access is blocked</span></span>|
----------------------
<span data-ttu-id="2154c-205">Você pode exportar o conteúdo do relatório e usar a coluna **Endereço de email** para informar os usuários de que eles serão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2154c-205">You can export the contents of the report and use the **Email Address** column to tell your users that they will be blocked.</span></span>

### <span data-ttu-id="2154c-206">Etapa 3: configurar grupos de usuários para a política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2154c-206">Step 3: Configure user groups for the conditional access policy</span></span>
<a id="step-3-configure-user-groups-for-the-conditional-access-policy" class="xliff"></a>
<span data-ttu-id="2154c-207">Políticas de acesso condicional são destinadas a diferentes grupos de segurança do Azure Active Directory de usuários.</span><span class="sxs-lookup"><span data-stu-id="2154c-207">Conditional access policies are targeted to different Azure Active Directory security groups of users.</span></span> <span data-ttu-id="2154c-208">Você também pode isentar alguns grupos de usuários de uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-208">You can also exempt certain user groups from a conditional access policy.</span></span> <span data-ttu-id="2154c-209">Quando um usuário é afetado por uma política, todos os dispositivos usados por ele devem estar em conformidade para que ele possa acessar o email.</span><span class="sxs-lookup"><span data-stu-id="2154c-209">When a user is targeted by a policy, each device that they use must be compliant in order to access email.</span></span>

<span data-ttu-id="2154c-210">É possível configurar esses grupos no **Centro de administração do Office 365** ou no **Portal de conta do Intune**.</span><span class="sxs-lookup"><span data-stu-id="2154c-210">You can configure these groups in the **Office 365 admin center** or in the **Intune account portal**.</span></span>

<span data-ttu-id="2154c-211">Você pode especificar dois tipos de grupo em cada política:</span><span class="sxs-lookup"><span data-stu-id="2154c-211">You can specify two group types in each policy:</span></span>

-   <span data-ttu-id="2154c-212">**Grupos de destino**: grupos de usuários aos quais a política é aplicada.</span><span class="sxs-lookup"><span data-stu-id="2154c-212">**Targeted groups**: User groups that the policy is applied to.</span></span>

-   <span data-ttu-id="2154c-213">**Grupos isentos**: grupos de usuários isentos da política (opcional).</span><span class="sxs-lookup"><span data-stu-id="2154c-213">**Exempted groups**: User groups that are exempt from the policy (optional).</span></span>

<span data-ttu-id="2154c-214">Se um usuário estiver nos dois grupos, ele ficará isento da política.</span><span class="sxs-lookup"><span data-stu-id="2154c-214">If a user is in both groups, they are exempt from the policy.</span></span>

<span data-ttu-id="2154c-215">Somente os grupos que são afetados pela política de acesso condicional são avaliados.</span><span class="sxs-lookup"><span data-stu-id="2154c-215">Only the groups that are targeted by the conditional access policy are evaluated.</span></span>

### <span data-ttu-id="2154c-216">Etapa 4: Configurar a política de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2154c-216">Step 4: Configure the conditional access policy</span></span>
<a id="step-4-configure-the-conditional-access-policy" class="xliff"></a>

>[!NOTE]
> <span data-ttu-id="2154c-217">Também é possível criar uma política de acesso condicional no console de gerenciamento do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2154c-217">You can also create a conditional access policy in the Azure AD management console.</span></span> <span data-ttu-id="2154c-218">O console de gerenciamento do Azure AD permite que você crie uma política de acesso condicional de dispositivo do Intune (conhecida como a **política de acesso condicional baseada em dispositivo** no Azure AD), além de outras políticas de acesso condicional, como a autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="2154c-218">The Azure AD management console lets you create an Intune device conditional access policy (referred to as the **device-based conditional access policy** in Azure AD), in addition to other conditional access policies like multi-factor authentication.</span></span>

><span data-ttu-id="2154c-219">Também é possível definir políticas de acesso condicional para aplicativos empresariais de terceiros com suporte do Azure AD, como Salesforce e Box.</span><span class="sxs-lookup"><span data-stu-id="2154c-219">You can also set conditional access policies for third-party enterprise apps that Azure AD supports, like Salesforce and Box.</span></span> <span data-ttu-id="2154c-220">Para obter mais detalhes, consulte [Como definir a política de acesso condicional com base no dispositivo do Azure Active Directory para controle de acesso dos aplicativos conectados no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).</span><span class="sxs-lookup"><span data-stu-id="2154c-220">For more details, see [How to set Azure Active Directory device-based conditional access policy for access control to Azure Active Directory-connected applications](https://azure.microsoft.com/documentation/articles/active-directory-conditional-access-policy-connected-applications/).</span></span>


1.  <span data-ttu-id="2154c-221">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Acesso Condicional** > **Política do Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="2154c-221">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **Exchange Online Policy**.</span></span>

2.  <span data-ttu-id="2154c-222">Na página **Política do Exchange Online**, escolha **Habilitar política de acesso condicional para o Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="2154c-222">On the **Exchange Online Policy** page, choose **Enable conditional access policy for Exchange Online**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2154c-223">Se você ainda não tiver implantado nenhuma política de conformidade, os dispositivos serão tratados como em conformidade.</span><span class="sxs-lookup"><span data-stu-id="2154c-223">If you haven't deployed a compliance policy, devices are treated as compliant.</span></span>
    >
    > <span data-ttu-id="2154c-224">Independentemente do estado de conformidade, todos os usuários que são afetados pela política precisam registrar seus dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-224">Regardless of the compliance state, all users who are targeted by the policy are required to enroll their devices with Intune.</span></span>

3.  <span data-ttu-id="2154c-225">Em **Acesso ao aplicativo**, para aplicativos que usam a autenticação moderna, há duas maneiras de escolher as plataformas às quais a política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="2154c-225">Under **Application access**, for apps that use modern authentication, you have two ways of choosing which platforms the policy should apply to.</span></span> <span data-ttu-id="2154c-226">Plataformas com suporte incluem iOS, Android, Windows e Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="2154c-226">Supported platforms include Android, iOS, Windows, and Windows Phone.</span></span>

    -   <span data-ttu-id="2154c-227">**Todas as plataformas**</span><span class="sxs-lookup"><span data-stu-id="2154c-227">**All platforms**</span></span>

        <span data-ttu-id="2154c-228">Isso exige que os dispositivos usados para acessar o **Exchange Online** sejam registrados no Intune e estejam em conformidade com as políticas.</span><span class="sxs-lookup"><span data-stu-id="2154c-228">This requires that any device that is used to access **Exchange Online** is enrolled in Intune and compliant with the policies.</span></span> <span data-ttu-id="2154c-229">Qualquer aplicativo cliente que use a **autenticação moderna** está sujeito à política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-229">Any client application that uses **modern authentication** is subject to the conditional access policy.</span></span> <span data-ttu-id="2154c-230">Se, no momento, não houver suporte para a plataforma no Intune, o acesso ao **Exchange Online** será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="2154c-230">If the platform is currently not supported by Intune, access to **Exchange Online** is blocked.</span></span>

        <span data-ttu-id="2154c-231">Selecionar a opção **Todas as plataformas** significa que o Azure Active Directory aplicará essa política a todas as solicitações de autenticação, independentemente da plataforma relatada pelo aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="2154c-231">Selecting the **All platforms** option means that Azure Active Directory applies this policy to all authentication requests, regardless of the platform that is reported by the client application.</span></span> <span data-ttu-id="2154c-232">Todas as plataformas devem ser registradas e estar em conformidade, exceto:</span><span class="sxs-lookup"><span data-stu-id="2154c-232">All platforms are required to enroll and become compliant, except for:</span></span>
        *   <span data-ttu-id="2154c-233">Dispositivos Windows, que precisarão ser registrados e compatíveis, ingressados no domínio com o Active Directory local ou ambas as opções.</span><span class="sxs-lookup"><span data-stu-id="2154c-233">Windows devices, which are required to be enrolled and compliant, domain joined with on-premises Active Directory, or both.</span></span>
        * <span data-ttu-id="2154c-234">Plataformas sem suporte, como Mac OS.</span><span class="sxs-lookup"><span data-stu-id="2154c-234">Unsupported platforms like Mac OS.</span></span> <span data-ttu-id="2154c-235">No entanto, os aplicativos que usam a autenticação moderna provenientes dessas plataformas ainda estarão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="2154c-235">However, apps that use modern authentication coming from these platforms is still blocked.</span></span>

    -   <span data-ttu-id="2154c-236">**Plataformas específicas**</span><span class="sxs-lookup"><span data-stu-id="2154c-236">**Specific platforms**</span></span>

         <span data-ttu-id="2154c-237">A política de acesso condicional se aplica ao aplicativos cliente que usam a **autenticação moderna** nas plataformas de dispositivo especificadas.</span><span class="sxs-lookup"><span data-stu-id="2154c-237">The conditional access policy applies to any client app that is using **modern authentication** on the device platforms that you specify.</span></span>

4. <span data-ttu-id="2154c-238">Em **OWA (Outlook Web Access)**, você pode optar por permitir o acesso ao Exchange Online apenas por meio de navegadores com suporte: Safari (iOS) e Chrome (Android).</span><span class="sxs-lookup"><span data-stu-id="2154c-238">Under **Outlook Web Access (OWA)**, you can choose to allow access to Exchange Online only through the supported browsers: Safari (iOS) and Chrome (Android).</span></span> <span data-ttu-id="2154c-239">O acesso de outros navegadores será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="2154c-239">Access from other browsers is blocked.</span></span> <span data-ttu-id="2154c-240">As mesmas restrições de plataforma selecionadas para Acesso ao aplicativo para Outlook também se aplicam aqui.</span><span class="sxs-lookup"><span data-stu-id="2154c-240">The same platform restrictions that you selected for Application access for Outlook also apply here.</span></span>

  <span data-ttu-id="2154c-241">Em dispositivos **Android**, os usuários devem habilitar o acesso do navegador.</span><span class="sxs-lookup"><span data-stu-id="2154c-241">On **Android** devices, users must enable browser access.</span></span> <span data-ttu-id="2154c-242">Para fazer isso, o usuário deve habilitar a opção **Habilitar Acesso do Navegador** no dispositivo registrado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="2154c-242">To do this, the user must enable the **Enable Browser Access** option on the enrolled device as follows:</span></span>
  1.    <span data-ttu-id="2154c-243">Abra o **aplicativo Portal da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="2154c-243">Open the **Company Portal app**.</span></span>
  2.    <span data-ttu-id="2154c-244">Acesse a página **Configurações** por meio das reticências (...) ou do botão de menu do hardware.</span><span class="sxs-lookup"><span data-stu-id="2154c-244">Go to the **Settings** page from the ellipsis (…) or the hardware menu button.</span></span>
  3.    <span data-ttu-id="2154c-245">Pressione o botão **Habilitar Acesso do Navegador**.</span><span class="sxs-lookup"><span data-stu-id="2154c-245">Press the **Enable Browser Access** button.</span></span>
  4.    <span data-ttu-id="2154c-246">No navegador Chrome, saia do Office 365 e reinicie o Chrome.</span><span class="sxs-lookup"><span data-stu-id="2154c-246">In the Chrome browser, sign out of Office 365 and restart Chrome.</span></span>

  <span data-ttu-id="2154c-247">Em plataformas **iOS** e **Android**, para identificar o dispositivo usado para acessar o serviço, o Azure Active Directory emite um certificado de protocolo TLS para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2154c-247">On **iOS** and **Android** platforms, to identify the device that is used to access the service, Azure Active Directory issues a Transport Layer Security (TLS) certificate to the device.</span></span> <span data-ttu-id="2154c-248">O dispositivo exibe o certificado com uma solicitação ao usuário final para selecionar o certificado, conforme mostrado nas capturas de tela a seguir.</span><span class="sxs-lookup"><span data-stu-id="2154c-248">The device displays the certificate with a prompt to the user to select the certificate, as shown in the following screenshots.</span></span> <span data-ttu-id="2154c-249">O usuário deve selecionar esse certificado antes que possa continuar usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="2154c-249">The user must select this certificate before they can continue to use the browser.</span></span>

  <span data-ttu-id="2154c-250">**iOS**</span><span class="sxs-lookup"><span data-stu-id="2154c-250">**iOS**</span></span>

  ![Captura de tela da solicitação de certificado em um iPad](../media/mdm-browser-ca-ios-cert-prompt.png)

  <span data-ttu-id="2154c-252">**Android**</span><span class="sxs-lookup"><span data-stu-id="2154c-252">**Android**</span></span>

  ![captura de tela da solicitação de certificado em um dispositivo Android](../media/mdm-browser-ca-android-cert-prompt.png)

5.  <span data-ttu-id="2154c-254">Em **aplicativos do Exchange ActiveSync**, você pode optar por bloquear dispositivos incompatíveis de acessar o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2154c-254">Under **Exchange ActiveSync apps**, you can choose to block noncompliant devices from accessing Exchange Online.</span></span> <span data-ttu-id="2154c-255">Também é possível escolher se deseja permitir ou bloquear o acesso ao email quando o dispositivo não está executando uma plataforma com suporte.</span><span class="sxs-lookup"><span data-stu-id="2154c-255">You can also select whether to allow or block access to email when the device isn't running a supported platform.</span></span> <span data-ttu-id="2154c-256">Plataformas com suporte incluem iOS, Android, Windows e Windows Phone.</span><span class="sxs-lookup"><span data-stu-id="2154c-256">Supported platforms include Android, iOS, Windows, and Windows Phone.</span></span>

 <span data-ttu-id="2154c-257">Aplicativos do Exchange Active Sync em dispositivos **Android para Trabalho**:</span><span class="sxs-lookup"><span data-stu-id="2154c-257">Exchange Active Sync apps on **Android for Work** devices:</span></span>
 -  <span data-ttu-id="2154c-258">Em dispositivos Android for Work, há suporte somente para os aplicativos **Gmail** e **Nine Work** no **perfil de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2154c-258">Only **Gmail** and **Nine Work** apps in the **work profile** are supported on Android for Work devices.</span></span> <span data-ttu-id="2154c-259">Para que o acesso condicional funcione em dispositivos Android para Trabalho, é necessário implantar um perfil de email para os aplicativos Gmail ou Nine Work e também implantá-los como uma instalação **obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="2154c-259">For conditional access to work on Android for Work devices, you must deploy an email profile for the Gmail or Nine Work app, and also deploy it as a **required** installation.</span></span>

6.  <span data-ttu-id="2154c-260">Em **Grupos de Destino**, selecione os grupos de usuários de segurança do Active Directory aos quais a política se aplica.</span><span class="sxs-lookup"><span data-stu-id="2154c-260">Under **Targeted Groups**, select the Active Directory security groups of users that the policy applies to.</span></span> <span data-ttu-id="2154c-261">Você pode optar por direcionar todos os usuários ou uma lista selecionada de grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="2154c-261">You can either choose to target all users or a selected list of user groups.</span></span>
<span data-ttu-id="2154c-262">![Captura de tela da página da política de acesso condicional do Exchange Online que mostra as opções de grupo de Destino e Isento](../media/IntuneSA5eTargetedExemptedGroups.PNG)</span><span class="sxs-lookup"><span data-stu-id="2154c-262">![Screenshot of the Exchange Online conditional access policy page that shows the Targeted and Exempted group options](../media/IntuneSA5eTargetedExemptedGroups.PNG)</span></span>
    > [!NOTE]
    > <span data-ttu-id="2154c-263">Para usuários que estão nos **Grupos de destino**, as políticas do Intune substituem as regras e políticas do Exchange.</span><span class="sxs-lookup"><span data-stu-id="2154c-263">For users that are in the **Targeted groups**, the Intune polices replace Exchange rules and policies.</span></span>
    >
    > <span data-ttu-id="2154c-264">O Exchange apenas imporá as regras de permissão, bloqueio e quarentena, bem como as políticas do Exchange se:</span><span class="sxs-lookup"><span data-stu-id="2154c-264">Exchange only enforces the Exchange allow, block, and quarantine rules, and Exchange policies if:</span></span>
    >
    > -   <span data-ttu-id="2154c-265">Um usuário não está licenciado para o Intune.</span><span class="sxs-lookup"><span data-stu-id="2154c-265">A user isn't licensed for Intune.</span></span>
    > -   <span data-ttu-id="2154c-266">Um usuário está licenciado para o Intune, mas não pertence a nenhum grupo de segurança é afetado na política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="2154c-266">A user is licensed for Intune, but the user doesn't belong to any security groups that are targeted in the conditional access policy.</span></span>

6.  <span data-ttu-id="2154c-267">Em **Grupos isentos**, selecione os grupos de segurança de usuários do Active Directory que serão isentos desta política.</span><span class="sxs-lookup"><span data-stu-id="2154c-267">Under **Exempted Groups**, select the Active Directory security groups of users that are exempt from this policy.</span></span> <span data-ttu-id="2154c-268">Se um usuário estiver nos grupos de destino e isentos, ele será isento da política.</span><span class="sxs-lookup"><span data-stu-id="2154c-268">If a user is in both the targeted and exempted groups, they are exempt from the policy.</span></span>

7.  <span data-ttu-id="2154c-269">Quando terminar, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2154c-269">When you're done, choose **Save**.</span></span>

-   <span data-ttu-id="2154c-270">Não é necessário implantar a política de acesso condicional, ela entra em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2154c-270">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>

-   <span data-ttu-id="2154c-271">Depois que um usuário cria uma conta de email, o dispositivo é bloqueado imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2154c-271">After a user creates an email account, the device is blocked immediately.</span></span>

-   <span data-ttu-id="2154c-272">Se um usuário bloqueado registrar o dispositivo no Intune e corrigir os problemas de não conformidade, o acesso ao email será desbloqueado em até dois minutos.</span><span class="sxs-lookup"><span data-stu-id="2154c-272">If a blocked user enrolls the device with Intune and fixes any noncompliance issues, email access is unblocked within two minutes.</span></span>

-   <span data-ttu-id="2154c-273">Se o usuário cancelar o registro de seu dispositivo, o email será bloqueado após seis horas, aproximadamente.</span><span class="sxs-lookup"><span data-stu-id="2154c-273">If the user unenrolls their device, email is blocked after around six hours.</span></span>

<span data-ttu-id="2154c-274">Para ver alguns **cenários de exemplo de como você poderá configurar uma política de acesso condicional para proteger o acesso ao dispositivo**, consulte [Proteger o acesso a email – cenários de exemplo](restrict-email-access-example-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="2154c-274">To see some **example scenarios of how you would configure a conditional access policy to protect device access**, see [Protect email access example scenarios](restrict-email-access-example-scenarios.md).</span></span>

## <span data-ttu-id="2154c-275">Monitorar a conformidade e políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="2154c-275">Monitor the compliance and conditional access policies</span></span>
<a id="monitor-the-compliance-and-conditional-access-policies" class="xliff"></a>

#### <span data-ttu-id="2154c-276">Para exibir dispositivos que foram bloqueados do Exchange</span><span class="sxs-lookup"><span data-stu-id="2154c-276">To view devices that are blocked from Exchange</span></span>
<a id="to-view-devices-that-are-blocked-from-exchange" class="xliff"></a>

<span data-ttu-id="2154c-277">No painel do Intune, escolha o bloco **Dispositivos Bloqueados do Exchange** para mostrar o número de dispositivos bloqueados e links para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2154c-277">On the Intune dashboard, choose the **Blocked Devices from Exchange** tile to show the number of blocked devices and links to more information.</span></span>
<span data-ttu-id="2154c-278">![Captura de tela do painel do Intune mostrando o número de dispositivos que são impedidos de acessar o Exchange](../media/IntuneSA6BlockedDevices.PNG)</span><span class="sxs-lookup"><span data-stu-id="2154c-278">![Screenshot of the Intune dashboard showing the number of devices that are blocked from accessing Exchange](../media/IntuneSA6BlockedDevices.PNG)</span></span>

## <span data-ttu-id="2154c-279">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="2154c-279">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
- [<span data-ttu-id="2154c-280">Proteger o acesso ao SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2154c-280">Protect access to SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

- [<span data-ttu-id="2154c-281">Proteger o acesso ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2154c-281">Protect access to Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
