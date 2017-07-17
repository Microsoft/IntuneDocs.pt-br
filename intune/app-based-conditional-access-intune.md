---
title: Acesso condicional baseado no aplicativo com o Intune
description: Entenda os conceitos de como o acesso condicional baseado no aplicativo funciona com o Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0893d511c73e4154c61063d96e26937ea2825467
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7b6e0-103">Acesso condicional baseado no aplicativo com o Intune</span><span class="sxs-lookup"><span data-stu-id="7b6e0-103">App-based conditional access with Intune</span></span>
<a id="app-based-conditional-access-with-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7b6e0-104">As [políticas de Proteção de Aplicativo do Intune](app-protection-policy.md) ajudam a proteger os dados da empresa nos dispositivos registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-104">[Intune app protection policies](app-protection-policy.md) help protect your company data on devices that are enrolled into Intune.</span></span> <span data-ttu-id="7b6e0-105">Use também as políticas de proteção de aplicativo em dispositivos dos funcionários que não estão registrados no gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-105">You can also use app protection policies on employee owned devices that are not enrolled for management in Intune.</span></span> <span data-ttu-id="7b6e0-106">Nesse caso, mesmo que sua empresa não gerencie o dispositivo, ainda é necessário verificar se os dados e recursos da empresa estão protegidos.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-106">In this case, even though your company doesn't manage the device, you still need to make sure that company data and resources are protected.</span></span>

<span data-ttu-id="7b6e0-107">O acesso condicional baseado no aplicativo e o gerenciamento de aplicativo móvel adicionam uma camada de segurança garantindo que apenas os aplicativos móveis que dão suporte às políticas de Proteção de Aplicativo do Intune podem acessar o Exchange Online e outros serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-107">App-based conditional access and mobile application management adds a security layer by making sure only mobile apps that support Intune app protection policies can access Exchange online, and other Office 365 services.</span></span>

> [!NOTE]
> <span data-ttu-id="7b6e0-108">Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativo aplicadas e que pode ser gerenciado pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-108">A managed app is an app that has app protection policies applied to it, and can be managed by Intune.</span></span>

<span data-ttu-id="7b6e0-109">Você poderá bloquear os aplicativos de email internos no iOS e no Android quando permitir que apenas o aplicativo Microsoft Outlook acesse o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-109">You can block the built-in mail apps on iOS and Android when you only allow the Microsoft Outlook app to access Exchange Online.</span></span> <span data-ttu-id="7b6e0-110">Além disso, bloqueie o acesso ao SharePoint Online por aplicativos que não têm as políticas de Proteção de Aplicativo do Intune aplicadas.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-110">Additionally, you can block apps that don’t have Intune app protection policies applied from accessing SharePoint Online.</span></span>

## <span data-ttu-id="7b6e0-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7b6e0-111">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>
<span data-ttu-id="7b6e0-112">Antes de criar uma política de acesso condicional baseado no aplicativo, você deve ter:</span><span class="sxs-lookup"><span data-stu-id="7b6e0-112">Before you create an App-based conditional access policy, you must have:</span></span>

- <span data-ttu-id="7b6e0-113">Uma **assinatura do Enterprise Mobility + Security ou do Azure Active Directory Premium** e os usuários devem ser licenciados para o EMS ou o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-113">**Enterprise Mobility + Security or an Azure Active Directory premium subscription**, and the users must be licensed for EMS or Azure AD.</span></span>
    - <span data-ttu-id="7b6e0-114">Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="7b6e0-114">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

## <span data-ttu-id="7b6e0-115">Aplicativos com suporte</span><span class="sxs-lookup"><span data-stu-id="7b6e0-115">Supported apps</span></span>
<a id="supported-apps" class="xliff"></a>

- <span data-ttu-id="7b6e0-116">**Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="7b6e0-116">**Exchange Online**:</span></span>
    - <span data-ttu-id="7b6e0-117">Microsoft Outlook para Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-117">Microsoft Outlook for Android and iOS.</span></span>
<br></br>
- <span data-ttu-id="7b6e0-118">**SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="7b6e0-118">**SharePoint Online**</span></span>
    - <span data-ttu-id="7b6e0-119">Microsoft Word para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b6e0-119">Microsoft Word for iOS and Android</span></span>
    - <span data-ttu-id="7b6e0-120">Microsoft Excel para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b6e0-120">Microsoft Excel for iOS and Android</span></span>
    - <span data-ttu-id="7b6e0-121">Microsoft PowerPoint para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b6e0-121">Microsoft PowerPoint for iOS and Android</span></span>
    - <span data-ttu-id="7b6e0-122">Microsoft OneDrive para Empresas para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b6e0-122">Microsoft OneDrive for Business for iOS and Android</span></span>
    - <span data-ttu-id="7b6e0-123">Microsoft OneNote para iOS</span><span class="sxs-lookup"><span data-stu-id="7b6e0-123">Microsoft OneNote for iOS</span></span>
<br></br>
- <span data-ttu-id="7b6e0-124">**Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="7b6e0-124">**Microsoft Teams**</span></span>

    > [!NOTE] 
    > <span data-ttu-id="7b6e0-125">O acesso condicional baseado no aplicativo [também dá suporte a aplicativos LOB](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), mas esses aplicativos precisam usar a [autenticação moderna do Office 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).</span><span class="sxs-lookup"><span data-stu-id="7b6e0-125">App-based conditional access [also supports LOB apps](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), but these apps need to use [Office 365 modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).</span></span>

## <span data-ttu-id="7b6e0-126">Como funciona o acesso condicional baseado no aplicativo</span><span class="sxs-lookup"><span data-stu-id="7b6e0-126">How app-based conditional access works</span></span>
<a id="how-app-based-conditional-access-works" class="xliff"></a>

<span data-ttu-id="7b6e0-127">Neste exemplo, o administrador tem políticas de proteção de aplicativo aplicadas ao aplicativo Outlook seguidas por uma regra de acesso condicional que adiciona o aplicativo Outlook a uma lista aprovada de aplicativos que podem ser usados ao acessar o email corporativo.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-127">In this example, the admin has app protection policies applied to the Outlook app followed by a conditional access rule that adds the Outlook app to an approved list of apps that can be used when accessing corporate e-mail.</span></span>

> [!NOTE] 
> <span data-ttu-id="7b6e0-128">A estrutura de fluxograma abaixo pode ser usada para outros aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-128">The flowchart structure below can be used for other managed apps.</span></span>

![Fluxograma da AC baseada no aplicativo com o Intune](./media/ca-intune-common-ways-3.png)

1.  <span data-ttu-id="7b6e0-130">O usuário tenta se autenticar no Azure AD por meio do aplicativo Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-130">The user tries to authenticate to Azure AD from the Outlook app.</span></span>

2.  <span data-ttu-id="7b6e0-131">O usuário é redirecionado para a loja de aplicativos para instalar um aplicativo agente ao tentar se autenticar pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-131">The user gets redirected to the app store to install a broker app when trying to authenticate for the first time.</span></span> <span data-ttu-id="7b6e0-132">O aplicativo agente pode ser o Microsoft Authenticator para iOS ou o portal da Empresa da Microsoft para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-132">The broker app can be either the Microsoft Authenticator for iOS, or the Microsoft Company portal for Android devices.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7b6e0-133">Nesse cenário, se os usuários tentarem usar um aplicativo de email nativo, eles serão redirecionados para a loja de aplicativos para, em seguida, instalarem o aplicativo Outlook.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-133">In this scenario, if users try to use a native e-mail app, they’ll be redirected to the app store to then install the Outlook app.</span></span>

3.  <span data-ttu-id="7b6e0-134">O aplicativo agente é instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-134">The broker app gets installed on the device.</span></span>

4.  <span data-ttu-id="7b6e0-135">O aplicativo agente inicia o processo de registro do Azure AD que cria um registro de dispositivo no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-135">The broker app starts the Azure AD registration process which creates a device record in Azure AD.</span></span> <span data-ttu-id="7b6e0-136">Isso não é o mesmo que o processo de registro do MDM (gerenciamento de dispositivo móvel), mas esse registro é necessário para que as políticas de acesso condicional possam ser impostas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-136">This is not the same as the mobile device management (MDM) enrollment process, but this record is necessary so the conditional access policies can be enforced on the device.</span></span>

5.  <span data-ttu-id="7b6e0-137">O aplicativo agente verifica a identidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-137">The broker app verifies the identity of the app.</span></span> <span data-ttu-id="7b6e0-138">Há uma camada de segurança para que o aplicativo agente possa validar se o aplicativo está autorizado a ser usado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-138">There’s a security layer so the broker app can validate if the app is authorized to be used by the user.</span></span>

6.  <span data-ttu-id="7b6e0-139">O aplicativo agente envia a ID do Cliente do Aplicativo para o Azure AD como parte do processo de autenticação do usuário para verificar se ele está na lista aprovada de políticas.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-139">The broker app sends the App Client ID to Azure AD as part of the user authentication process to check if it’s in the policy approved list.</span></span>

7.  <span data-ttu-id="7b6e0-140">O Azure AD permite ao usuário se autenticar e usar o aplicativo com base na lista aprovada de políticas.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-140">Azure AD allows the user to authenticate and use the app based on the policy approved list.</span></span> <span data-ttu-id="7b6e0-141">Se o aplicativo não estiver na lista aprovada de políticas, o Azure AD negará o acesso ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-141">If the app is not in the policy approved list, Azure AD denies access to the app.</span></span>

8.  <span data-ttu-id="7b6e0-142">O aplicativo Outlook se comunica com o Serviço de Nuvem do Outlook para iniciar a comunicação com o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-142">Outlook app communicates with Outlook Cloud Service to initiate communication with Exchange Online.</span></span>

9.  <span data-ttu-id="7b6e0-143">O Serviço de Nuvem do Outlook se comunica com o Azure AD para recuperar o token de acesso do serviço Exchange Online para o usuário.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-143">Outlook Cloud Service communicates with Azure AD to retrieve Exchange Online service access token for the user.</span></span>

10.  <span data-ttu-id="7b6e0-144">O aplicativo Outlook se comunica com o Exchange Online para recuperar o email corporativo do usuário.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-144">Outlook app communicates with Exchange Online to retrieve user's corporate e-mail.</span></span>

11.  <span data-ttu-id="7b6e0-145">O email corporativo é entregue à caixa de correio do usuário.</span><span class="sxs-lookup"><span data-stu-id="7b6e0-145">Corporate e-mail is delivered to the user's mailbox.</span></span>

## <span data-ttu-id="7b6e0-146">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7b6e0-146">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="7b6e0-147">Criar uma política de acesso condicional baseado no aplicativo</span><span class="sxs-lookup"><span data-stu-id="7b6e0-147">Create an app-based conditional access policy</span></span>](app-based-conditional-access-intune-create.md)

[<span data-ttu-id="7b6e0-148">Bloquear aplicativos que não têm autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="7b6e0-148">Block apps that do not have modern authentication</span></span>](app-modern-authentication-block.md)
