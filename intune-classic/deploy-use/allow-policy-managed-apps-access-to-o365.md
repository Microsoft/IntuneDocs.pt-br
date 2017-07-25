---
title: Acesso condicional ao O365 baseado em aplicativo
description: "Entenda como o AC para MAM pode ajudar a controlar os aplicativos que têm acesso aos serviços do O365."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8fc53e8717277a4075bc7ecde31fd60c3539a5f7
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d7761-103">Permitir que apenas aplicativos móveis que dão suporte às políticas de proteção de aplicativo do Intune acessem os serviços do Office 365</span><span class="sxs-lookup"><span data-stu-id="d7761-103">Allow only mobile apps that support Intune app protection policies to access Office 365 services</span></span>
<a id="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d7761-104">As [Políticas de proteção de aplicativo do Intune](protect-apps-and-data-with-microsoft-intune.md) ajudam a proteger os dados de sua empresa nos dispositivos registrados para gerenciamento no Intune.</span><span class="sxs-lookup"><span data-stu-id="d7761-104">[Intune app protection policies](protect-apps-and-data-with-microsoft-intune.md) help protect your company data on devices that are enrolled for management in Intune.</span></span> <span data-ttu-id="d7761-105">É possível usar as políticas de proteção de aplicativo em **dispositivos do funcionário que não estão registrados para gerenciamento no Intune**.</span><span class="sxs-lookup"><span data-stu-id="d7761-105">You can also use app protection policies on **employee owned devices that are not enrolled for management in Intune**.</span></span>  <span data-ttu-id="d7761-106">Nesse caso, mesmo que você não gerencie o dispositivo, ainda é necessário se certificar de que os dados e recursos da empresa estão protegidos.</span><span class="sxs-lookup"><span data-stu-id="d7761-106">In this case, even though you don't manage the device, you still need to make sure that your company data and resources is protected.</span></span> <span data-ttu-id="d7761-107">Usando o acesso condicional baseado em aplicativo com MAM, você pode criar uma política que permite que apenas aplicativos móveis que dão suporte às políticas de proteção de aplicativo do Intune acessem os serviços do O365, como o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d7761-107">Using App-based conditional access with MAM, you can create a policy that allows only mobile apps that support Intune app protection policies to access O365 services like Exchange Online.</span></span>

<span data-ttu-id="d7761-108">Por exemplo, ao permitir que apenas o **aplicativo do Microsoft Outlook** acesse o Exchange Online você pode **bloquear os aplicativos de email interno no iOS e no Android**, que não têm a proteção de dados das políticas de MAM do Intune, para receber email do **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="d7761-108">For example, by only allowing the **Microsoft Outlook app** to access Exchange Online, you can **block the built-in mail apps on iOS and Android**, which don't have the data protection from Intune MAM policies to get email from **Exchange Online**.</span></span> <span data-ttu-id="d7761-109">Ou você pode bloquear o acesso dos aplicativos móveis que não têm suporte do Intune MAM ao **SharePoint Online**.</span><span class="sxs-lookup"><span data-stu-id="d7761-109">Or you can block mobile apps that don’t have Intune MAM support from accessing **SharePoint Online**.</span></span>

<span data-ttu-id="d7761-110">O diagrama a seguir ilustra o fluxo usado pelas políticas de acesso condicional baseados em aplicativo para determinar quando permitir ou bloquear o acesso: ![Diagrama que mostra os vários critérios incluídos para determinar se o acesso é permitido ou bloqueado](../media/mam-ca-decision-flow_simple.png).</span><span class="sxs-lookup"><span data-stu-id="d7761-110">The diagram below illustrates the flow used by App-based conditional access policies to determine when to allow or block access: ![Diagram that shows the various criteria included to determine whether to allow or block access ](../media/mam-ca-decision-flow_simple.png).</span></span>

<span data-ttu-id="d7761-111">Descrição das abreviações usadas nos diagramas:</span><span class="sxs-lookup"><span data-stu-id="d7761-111">Description of the abbreviations used in the diagrams:</span></span>
* <span data-ttu-id="d7761-112">**CP**: aplicativo de Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="d7761-112">**CP**: Company Portal app</span></span>
* <span data-ttu-id="d7761-113">**AA**: aplicativo Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="d7761-113">**AA**: Azure Authenticator app</span></span>
* <span data-ttu-id="d7761-114">**AAD**: Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d7761-114">**AAD**: Azure Active Directory</span></span>
* <span data-ttu-id="d7761-115">**EAS**: Exchange Active Sync</span><span class="sxs-lookup"><span data-stu-id="d7761-115">**EAS**: Exchange Active Sync</span></span>

## <span data-ttu-id="d7761-116">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d7761-116">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>
<span data-ttu-id="d7761-117">**Antes** de criar uma política de acesso condicional baseado em aplicativo, você deve ter uma **assinatura premium do Enterprise Mobility + Security ou do Azure Active Directory** e os usuários devem ser licenciados para o EMS ou Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d7761-117">**Before** you create an App-based conditional access policy, you must have an **Enterprise Mobility + Security or an Azure Active Directory premium subscription**, and the users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="d7761-118">Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="d7761-118">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>


## <span data-ttu-id="d7761-119">Aplicativos com suporte</span><span class="sxs-lookup"><span data-stu-id="d7761-119">Supported apps</span></span>
<a id="supported-apps" class="xliff"></a>
<span data-ttu-id="d7761-120">**Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="d7761-120">**Exchange Online**:</span></span>
* <span data-ttu-id="d7761-121">**Microsoft Outlook** para Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="d7761-121">**Microsoft Outlook** for Android and iOS.</span></span>

<span data-ttu-id="d7761-122">**SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="d7761-122">**SharePoint Online**</span></span>
* <span data-ttu-id="d7761-123">Microsoft Word para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="d7761-123">Microsoft Word for iOS and Android</span></span>
* <span data-ttu-id="d7761-124">Microsoft Excel para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="d7761-124">Microsoft Excel for iOS and Android</span></span>
* <span data-ttu-id="d7761-125">Microsoft PowerPoint para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="d7761-125">Microsoft PowerPoint for iOS and Android</span></span>
* <span data-ttu-id="d7761-126">Microsoft OneDrive para Empresas para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="d7761-126">Microsoft OneDrive for Business for iOS and Android</span></span>
* <span data-ttu-id="d7761-127">Microsoft OneNote para iOS</span><span class="sxs-lookup"><span data-stu-id="d7761-127">Microsoft OneNote for iOS</span></span>

>[!IMPORTANT]
><span data-ttu-id="d7761-128">Para dispositivos Android, o registro de dispositivo inicial deve ser feito por meio do logon no aplicativo OneDrive ou no aplicativo do Outlook.</span><span class="sxs-lookup"><span data-stu-id="d7761-128">For Android devices, the initial device registration must be done by logging into either the OneDrive app, or the Outlook app.</span></span> <span data-ttu-id="d7761-129">O aplicativo OneNote para Android ainda não tem suporte para MAM sem registro.</span><span class="sxs-lookup"><span data-stu-id="d7761-129">The OneNote app for Android does not yet support MAM without enrollment.</span></span>

<span data-ttu-id="d7761-130">Para saber mais sobre a experiência do usuário com um aplicativo que tem políticas de acesso condicional baseado em aplicativo, consulte [O que esperar ao usar um aplicativo com AC do MAM](use-apps-with-mam-ca.md).</span><span class="sxs-lookup"><span data-stu-id="d7761-130">To learn about the user experience with an app that has App-based conditional access policies, see [What to expect when using an app with MAM CA](use-apps-with-mam-ca.md).</span></span>


## <span data-ttu-id="d7761-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d7761-131">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="d7761-132">Criar uma política do Exchange Online para aplicativos MAM</span><span class="sxs-lookup"><span data-stu-id="d7761-132">Create an Exchange Online Policy for MAM apps</span></span>](mam-ca-for-exchange-online.md)

[<span data-ttu-id="d7761-133">Criar uma política do SharePoint Online para aplicativos MAM</span><span class="sxs-lookup"><span data-stu-id="d7761-133">Create a SharePoint Online Policy for MAM apps</span></span>](mam-ca-for-sharepoint-online.md)

[<span data-ttu-id="d7761-134">Bloquear aplicativos que não têm autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="d7761-134">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

### <span data-ttu-id="d7761-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d7761-135">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="d7761-136">Proteger dados de aplicativo com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d7761-136">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
