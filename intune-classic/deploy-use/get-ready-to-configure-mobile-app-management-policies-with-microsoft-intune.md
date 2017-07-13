---
title: "Pré-requisitos para políticas de MAM"
description: "Este tópico descreve os pré-requisitos para a configuração de usuários antes de criar políticas de gerenciamento de aplicativo móvel."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e6a85e7-e007-41b6-9034-64d77f547b87
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 67c261a3a31229f84d02d4536ab78857369391f1
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="dc921-103">Prepare-se para configurar as políticas de proteção do aplicativo no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="dc921-103">Get ready to configure app protection policies in the Azure portal</span></span>
<a id="get-ready-to-configure-app-protection-policies-in-the-azure-portal" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="dc921-104">Este tópico descreve os pré-requisitos e as etapas que você deve concluir **antes** de criar políticas de proteção de aplicativo no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dc921-104">This topic describes the prerequisites and the steps you must complete **before** you can create app protection policies in the Azure portal.</span></span>

<span data-ttu-id="dc921-105">Para compreender como as políticas de proteção de aplicativo do Intune podem proteger os dados da empresa, consulte [Proteger aplicativos e dados usando políticas de proteção de aplicativo](protect-apps-and-data-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="dc921-105">To understand how Intune app protection policies can protect your company data, see [Protect apps and data using app protection policies](protect-apps-and-data-with-microsoft-intune.md).</span></span>

## <span data-ttu-id="dc921-106">O que é o portal do Azure?</span><span class="sxs-lookup"><span data-stu-id="dc921-106">What is the Azure portal?</span></span>
<a id="what-is-the-azure-portal" class="xliff"></a>

<span data-ttu-id="dc921-107">O portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dc921-107">The Azure portal is the new admin console for creating app protection policies.</span></span> <span data-ttu-id="dc921-108">Ele dá suporte aos seguintes cenários de MAM:</span><span class="sxs-lookup"><span data-stu-id="dc921-108">It supports the following MAM scenarios:</span></span>
- <span data-ttu-id="dc921-109">Dispositivos registrados no Intune</span><span class="sxs-lookup"><span data-stu-id="dc921-109">Devices that are enrolled in Intune</span></span>
- <span data-ttu-id="dc921-110">Dispositivos gerenciados por outra solução de gerenciamento de dispositivo móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="dc921-110">Devices that are managed by another Mobile Device Management (MDM) solution</span></span>
- <span data-ttu-id="dc921-111">Dispositivos que não são gerenciados por uma solução de MDM (BYOD)</span><span class="sxs-lookup"><span data-stu-id="dc921-111">Devices that are not managed by any MDM solution (BYOD)</span></span>

<span data-ttu-id="dc921-112">No momento, o **console do administração do Intune** e o **portal do Azure** permitem configurar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dc921-112">Currently, both the **Intune administrator console** and the **Azure portal** enable you to configure app protection policies.</span></span>  <span data-ttu-id="dc921-113">Considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dc921-113">Consider the following:</span></span>

* <span data-ttu-id="dc921-114">As políticas que você cria no **portal do Azure** têm suporte para **todos os cenários de MAM** listados acima.</span><span class="sxs-lookup"><span data-stu-id="dc921-114">The policies that you create on the **Azure portal** are supported for **all MAM scenarios** that are listed previously.</span></span> <span data-ttu-id="dc921-115">O **console do administrador do Intune** dá suporte apenas à criação de políticas do **dispositivos registrados e gerenciados pelo Intune**.</span><span class="sxs-lookup"><span data-stu-id="dc921-115">The **Intune administrator console** only supports creating policies for **devices that are enrolled and managed by Intune**.</span></span>

* <span data-ttu-id="dc921-116">Talvez você não veja todas as configurações de política de aplicativo no console de administração do Intune, uma vez que **novas configurações** só podem ser adicionadas ao **portal do Azure**.</span><span class="sxs-lookup"><span data-stu-id="dc921-116">You might not see all app policy settings in the Intune administrator console because **new settings** can only be added to the **Azure portal**.</span></span>

* <span data-ttu-id="dc921-117">Se você criar políticas de proteção de aplicativo no console do administrador do Intune **e** no Portal do Azure, a política no **portal do Azure será aplicada aos aplicativos e implantada para usuários**.</span><span class="sxs-lookup"><span data-stu-id="dc921-117">If you create app protection policies in **both** the Intune admin console and the Azure portal, the policy in the **Azure portal is applied to the apps and deployed to users**.</span></span>
    * <span data-ttu-id="dc921-118">As políticas de proteção de aplicativo criadas no console de administração do Intune não podem ser importadas no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dc921-118">App protection policies that are created in the Intune admin console cannot be imported into the Azure portal.</span></span>  <span data-ttu-id="dc921-119">As políticas de proteção de aplicativo devem ser recriadas no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dc921-119">The app protection policies must be re-created in the Azure portal.</span></span>


* <span data-ttu-id="dc921-120">Atualmente, outros **recursos de gerenciamento de aplicativos**, como implantar aplicativos e políticas de configuração de aplicativos, só estão disponíveis no **console de administração do Intune**.</span><span class="sxs-lookup"><span data-stu-id="dc921-120">Other **app management features**, such as deploying apps and app configuration policies, are currently only available in the **Intune administrator console**.</span></span>


<span data-ttu-id="dc921-121">Se você for novo no portal do Azure, leia o tópico [Portal do Azure para políticas de proteção de aplicativo do Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) para obter as noções básicas de como usar o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dc921-121">If you are new to the Azure portal, read [Azure portal for Microsoft Intune app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) to get the basics of using the Azure portal.</span></span>

<span data-ttu-id="dc921-122">Para obter instruções sobre como criar uma política de aplicativo no console de administração do Intune, consulte [Configurar e implantar políticas de proteção de aplicativo no console do Microsoft Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span><span class="sxs-lookup"><span data-stu-id="dc921-122">For instructions about how to create an app policy on the Intune admin console, see [Configure and deploy app protection policies in the Microsoft Intune console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span></span>


##  <span data-ttu-id="dc921-123">Plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="dc921-123">Supported platforms</span></span>
<a id="supported-platforms" class="xliff"></a>
- <span data-ttu-id="dc921-124">iOS 8.1 ou posterior</span><span class="sxs-lookup"><span data-stu-id="dc921-124">iOS 8.1 or later</span></span>
- <span data-ttu-id="dc921-125">Android 4 ou posterior</span><span class="sxs-lookup"><span data-stu-id="dc921-125">Android 4 or later</span></span>
- <span data-ttu-id="dc921-126">Windows 10</span><span class="sxs-lookup"><span data-stu-id="dc921-126">Windows 10</span></span>

>[!NOTE]
><span data-ttu-id="dc921-127">Começando com a versão 1703, políticas de proteção de aplicativos podem ser definidas para dispositivos Windows 10 no MAM sem o cenário de registro.</span><span class="sxs-lookup"><span data-stu-id="dc921-127">Beginning with version 1703, app protection policies can be defined for Windows 10 devices in the MAM without enrollment scenario.</span></span> <span data-ttu-id="dc921-128">Para obter detalhes, consulte [Proteger seus dados empresariais usando a WIP (Proteção de Informações do Windows)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="dc921-128">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>

##  <span data-ttu-id="dc921-129">Aplicativos com suporte</span><span class="sxs-lookup"><span data-stu-id="dc921-129">Supported apps</span></span>
<a id="supported-apps" class="xliff"></a>
* <span data-ttu-id="dc921-130">**Aplicativos Microsoft:** esses aplicativos têm o SDK de Aplicativo do Intune interno e não exigem nenhum processamento adicional antes de aplicar as políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dc921-130">**Microsoft apps:** These apps have the Intune App SDK built in and require no further processing before you apply app protection policies.</span></span>
<span data-ttu-id="dc921-131">Para ver a lista completa de aplicativos da Microsoft com suporte, vá para a [Galeria de aplicativos móveis do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) na página de parceiros de aplicativos do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="dc921-131">To see the full list of supported Microsoft apps, go to the [Microsoft Intune mobile application gallery](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) on the Microsoft Intune application partners page.</span></span> <span data-ttu-id="dc921-132">Clique em um aplicativo para ver os cenários e plataformas com suporte e para ver se o aplicativo dá suporte a várias identidades ou não.</span><span class="sxs-lookup"><span data-stu-id="dc921-132">Click an app to see the supported scenarios and platforms, and to see whether the app supports multiple identities.</span></span>

* <span data-ttu-id="dc921-133">**Aplicativos de linha de negócios da organização:** é necessário preparar esses aplicativos para incluir o SDK de Aplicativo do Intune antes que seja possível aplicar as políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dc921-133">**Your organization's line-of-business apps:** You must prepare these apps to include the Intune App SDK before you can apply app protection policies.</span></span>

  * <span data-ttu-id="dc921-134">Para dispositivos que são gerenciados pelo Intune, consulte [Decide how to prepare apps for MAM](/intune/apps-prepare-mobile-application-management) (Decidir como preparar os aplicativos para MAM).</span><span class="sxs-lookup"><span data-stu-id="dc921-134">For devices that are managed by Intune, see [Decide how to prepare apps for MAM](/intune/apps-prepare-mobile-application-management).</span></span>

  * <span data-ttu-id="dc921-135">Para dispositivos não gerenciados (como dispositivos do funcionário) ou gerenciados por outra solução de gerenciamento de dispositivo móvel, consulte [Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="dc921-135">For devices that are not managed (such as employee-owned devices), or for devices that are managed by another mobile device management solution, see [Protect line-of-business apps and data on devices not enrolled in Intune](protect-line-of-business-apps-and-data-on-devices-not-enrolled-in-microsoft-intune.md).</span></span>

## <span data-ttu-id="dc921-136">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="dc921-136">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

-   <span data-ttu-id="dc921-137">**Uma assinatura do Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="dc921-137">**A Microsoft Intune subscription**.</span></span> <span data-ttu-id="dc921-138">Os usuários precisam de licenças do Intune para obter aplicativos que têm políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dc921-138">Users need Intune licenses to get apps that have app protection policies.</span></span>
<span data-ttu-id="dc921-139">Você já tem uma assinatura do Intune se estiver usando o Intune para gerenciar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dc921-139">You   already have an Intune subscription if you are currently using Intune to manage your devices.</span></span> <span data-ttu-id="dc921-140">Você também terá uma assinatura do Intune se tiver adquirido uma licença do EMS (Enterprise Mobility Suite).</span><span class="sxs-lookup"><span data-stu-id="dc921-140">You also have an Intune subscription if you have purchased an Enterprise Mobility Suite (EMS) license.</span></span> <span data-ttu-id="dc921-141">Se estiver experimentando o Intune para conferir os recursos de MAM, será possível obter uma conta de avaliação na [página do Microsoft Intune](https://www.microsoft.com/server-cloud/products/microsoft-intune/).</span><span class="sxs-lookup"><span data-stu-id="dc921-141">If you are trying Intune to check out the MAM capabilities, you can get a trial account on the [Microsoft Intune page](https://www.microsoft.com/server-cloud/products/microsoft-intune/).</span></span>

    <span data-ttu-id="dc921-142">Para verificar se você tem uma assinatura do Intune no portal do Office, acesse a página **Cobrança**.</span><span class="sxs-lookup"><span data-stu-id="dc921-142">To verify if you have an Intune subscription, in the Office portal, go to the **Billing** page.</span></span>  <span data-ttu-id="dc921-143">Se você tiver uma assinatura, verá o Intune como **Ativo** nas assinaturas.</span><span class="sxs-lookup"><span data-stu-id="dc921-143">If you have a subscription, you should see Intune as **Active** in the subscriptions.</span></span>

-   <span data-ttu-id="dc921-144">**Uma assinatura do Office 365**, que é necessária para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dc921-144">**An Office 365 subscription**, which is required for the following:</span></span>

  - <span data-ttu-id="dc921-145">Para aplicar políticas de proteção de aplicativo a aplicativos com suporte a várias identidades.</span><span class="sxs-lookup"><span data-stu-id="dc921-145">To apply app protection policies to apps with multiple-identity support.</span></span>

  - <span data-ttu-id="dc921-146">Para criar contas corporativas do SharePoint Online e Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc921-146">To create SharePoint Online and Exchange Online work accounts.</span></span> <span data-ttu-id="dc921-147">Não há suporte para o Exchange e o SharePoint locais.</span><span class="sxs-lookup"><span data-stu-id="dc921-147">Exchange on-premises and SharePoint on-premises are not supported.</span></span>

-   <span data-ttu-id="dc921-148">**Instalação do Skype for Business Online para autenticação moderna**.</span><span class="sxs-lookup"><span data-stu-id="dc921-148">**Skype for Business Online setup for modern authentication**.</span></span> <span data-ttu-id="dc921-149">Para obter mais informações, consulte [Habilitar a autenticação moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span><span class="sxs-lookup"><span data-stu-id="dc921-149">For more information, see [Enable modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>


- <span data-ttu-id="dc921-150">Azure AD (Azure Active Directory) para criar usuários.</span><span class="sxs-lookup"><span data-stu-id="dc921-150">Azure Active Directory (Azure AD) to create users.</span></span> <span data-ttu-id="dc921-151">O Azure AD autentica os usuários quando eles abrem o aplicativo e inserem suas credenciais de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dc921-151">Azure AD authenticates users when they open the app and enter their work credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dc921-152">Grupos de usuários devem ser configurados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dc921-152">User groups must be set up in Azure AD.</span></span> <span data-ttu-id="dc921-153">Grupos de usuários do Intune não podem ser usados para implantar políticas de proteção de aplicativo no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dc921-153">Intune user groups cannot be used to deploy app protection policies in the Azure portal.</span></span>

### <span data-ttu-id="dc921-154">Criar usuários e atribuir licenças do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc921-154">Create users and assign Microsoft Intune licenses</span></span>
<a id="create-users-and-assign-microsoft-intune-licenses" class="xliff"></a>

1.  <span data-ttu-id="dc921-155">Entre no [portal do Office](https://portal.office.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="dc921-155">Sign in to the [Office portal](https://portal.office.com) with your admin credentials.</span></span>

2.  <span data-ttu-id="dc921-156">Adicione usuários, conforme descrito na seção **Etapas para realizar uma avaliação de 30 dias do Intune** do [Guia de avaliação do Intune](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune) e, em seguida, atribua as licenças do Intune.</span><span class="sxs-lookup"><span data-stu-id="dc921-156">Add users as described in the **Steps to complete a 30-day evaluation of Intune** section of the [Intune evaluation guide](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune), and then assign Intune licenses.</span></span> <span data-ttu-id="dc921-157">Para conceder a um usuário a capacidade de acessar o portal do Office, o portal do Azure AD e o Portal do Azure, atribua a função de **Administrador Global** ao usuário.</span><span class="sxs-lookup"><span data-stu-id="dc921-157">To give a user the ability to access the Office portal, the Azure AD portal, and the Azure  portal, assign the **Global administrator** role to the user.</span></span>

5.  <span data-ttu-id="dc921-158">Políticas de proteção de aplicativo são implantadas ema grupos de usuários no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dc921-158">App protection policies are deployed to user groups in Azure Active Directory.</span></span> <span data-ttu-id="dc921-159">Para criar grupos de usuários para as políticas de proteção de aplicativo, crie um grupo de usuários, conforme descrito na seção **Criar um grupo de usuários** de [Criar grupos para organizar usuários e dispositivos de assinatura de avaliação](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).</span><span class="sxs-lookup"><span data-stu-id="dc921-159">To create user groups for your app protection policies, create a user group as described in the **Create a user group** section of [Create groups to organize evaluation subscription users and devices](/intune-classic/understand-explore/get-started-with-a-30-day-trial-of-microsoft-intune-step-3).</span></span>

### <span data-ttu-id="dc921-160">Atribua funções a usuários administradores não globais</span><span class="sxs-lookup"><span data-stu-id="dc921-160">Assign roles to non-global admin users</span></span>
<a id="assign-roles-to-non-global-admin-users" class="xliff"></a>

<span data-ttu-id="dc921-161">Os administradores globais têm acesso ao [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="dc921-161">Global administrators have access to the [Azure portal](https://portal.azure.com).</span></span>  <span data-ttu-id="dc921-162">Se você desejar que usuários que não são administradores globais possam configurar políticas e realizar outras tarefas de gerenciamento de aplicativo móvel, consulte o artigo [Usar atribuições de função para gerenciar acesso para seus recursos de assinatura do Azure](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/).</span><span class="sxs-lookup"><span data-stu-id="dc921-162">If you want users who are not global administrators to be able to configure policies and do other mobile app management tasks, check the [Use role assignments to manage access to your Azure subscription resources](https://azure.microsoft.com/documentation/articles/role-based-access-control-configure/) article.</span></span>

## <span data-ttu-id="dc921-163">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dc921-163">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="dc921-164">Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc921-164">Create and deploy app protection policies with Microsoft Intune</span></span>](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
