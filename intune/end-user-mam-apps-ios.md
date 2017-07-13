---
title: "Aplicativos iOS com políticas de proteção de aplicativo"
description: "Este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a4b7ad6cfd8e07137bac9d430088274d9161c7ac
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="452be-103">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="452be-103">What to expect when your iOS app is managed by app protection policies</span></span>
<a id="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

 <span data-ttu-id="452be-104">Este tópico descreve a experiência do usuário ao usar aplicativos com políticas de proteção de aplicativo aplicadas.</span><span class="sxs-lookup"><span data-stu-id="452be-104">This topic describes the user experience when using apps with app protection policies applied to.</span></span> <span data-ttu-id="452be-105">As políticas do aplicativo são aplicadas somente quando aplicativos são usados no contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no OneDrive para Empresas.</span><span class="sxs-lookup"><span data-stu-id="452be-105">App protection policies are applied only when apps are used in the work context; for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive for business location.</span></span>

##  <span data-ttu-id="452be-106">Acessar aplicativos</span><span class="sxs-lookup"><span data-stu-id="452be-106">Access apps</span></span>
<a id="access-apps" class="xliff"></a>

<span data-ttu-id="452be-107">Se o dispositivo **não estiver registrado no Intune**, o usuário será solicitado a reiniciar o aplicativo ao usá-lo pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="452be-107">If the device is **not enrolled in Intune**, the user is asked to restart the app when they first use it.</span></span> <span data-ttu-id="452be-108">Uma reinicialização é necessária para que essas políticas de proteção de aplicativo possam ser aplicadas ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="452be-108">A restart is required so that app protection polices can be applied to the app.</span></span> 

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

<span data-ttu-id="452be-109">Em dispositivos **registrados para gerenciamento no Intune**, o usuário verá uma mensagem informando que seu aplicativo agora é gerenciado.</span><span class="sxs-lookup"><span data-stu-id="452be-109">For devices that are **enrolled for management in Intune**, the user sees a message that their app is now managed.</span></span>

##  <span data-ttu-id="452be-110">Usar aplicativos com suporte a várias identidades</span><span class="sxs-lookup"><span data-stu-id="452be-110">Use apps with multi-identity support</span></span>
<a id="use-apps-with-multi-identity-support" class="xliff"></a>

<span data-ttu-id="452be-111">Aplicativos que dão suporte a várias identidades permitem usar contas diferentes (pessoal e corporativa) para acessar os mesmos aplicativos quando políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="452be-111">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>  

<span data-ttu-id="452be-112">Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho.</span><span class="sxs-lookup"><span data-stu-id="452be-112">For example, the user gets a PIN prompt when accessing work data.</span></span> <span data-ttu-id="452be-113">No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="452be-113">For the **Outlook app**, the user is prompted for a PIN when they launch the app.</span></span> <span data-ttu-id="452be-114">No **aplicativo OneDrive**, o usuário será solicitado a fornecer um PIN ao digitar a conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="452be-114">For the **OneDrive app**, the user is prompted for a pin when they type in the work account.</span></span>  <span data-ttu-id="452be-115">No Microsoft **Word**, **PowerPoint** e **Excel**, o usuário será solicitado a fornecer um PIN ao acessar os documentos armazenados no local do OneDrive for Business da empresa.</span><span class="sxs-lookup"><span data-stu-id="452be-115">For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for a pin when they access documents that are stored in the company OneDrive for Business location.</span></span>

- <span data-ttu-id="452be-116">Saiba mais sobre os aplicativos que oferecem suporte a [MAM e várias identidades](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="452be-116">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

<span data-ttu-id="452be-117">As políticas de proteção do aplicativo são aplicadas apenas em contextos corporativos.</span><span class="sxs-lookup"><span data-stu-id="452be-117">App protection polices are only applied in the work context.</span></span> <span data-ttu-id="452be-118">Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.</span><span class="sxs-lookup"><span data-stu-id="452be-118">Therefore, the app might behave differently depending on whether the context is work or personal.</span></span>

##  <span data-ttu-id="452be-119">Gerenciar contas de usuário no dispositivo</span><span class="sxs-lookup"><span data-stu-id="452be-119">Manage user accounts on the device</span></span>
<a id="manage-user-accounts-on-the-device" class="xliff"></a>

<span data-ttu-id="452be-120">O Intune só dá suporte à implantação de políticas de proteção do aplicativo a uma conta de usuário por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="452be-120">Intune supports the deployment of app protection policies to  one user account per device only.</span></span>

* <span data-ttu-id="452be-121">Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ser bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="452be-121">Depending on the app that you are using, the second user might be blocked on the device.</span></span> <span data-ttu-id="452be-122">No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.</span><span class="sxs-lookup"><span data-stu-id="452be-122">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>
  * <span data-ttu-id="452be-123">**Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="452be-123">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>  

  * <span data-ttu-id="452be-124">Nos **aplicativos OneDrive** e **Outlook**, é possível usar somente uma conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="452be-124">For **OneDrive** and **Outlook apps**, you can only use one work account.</span></span> <span data-ttu-id="452be-125">Não é possível adicionar várias contas corporativas a esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="452be-125">You can't add multiple work accounts for these apps.</span></span> <span data-ttu-id="452be-126">É possível remover um usuário e adicionar um usuário diferente ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="452be-126">You can however, remove a user and add a different user on the device.</span></span>

* <span data-ttu-id="452be-127">Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="452be-127">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="452be-128">Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.</span><span class="sxs-lookup"><span data-stu-id="452be-128">Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="452be-129">O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="452be-129">User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="452be-130">A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo, mas não a conta associada à Empresa Y. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X.</span><span class="sxs-lookup"><span data-stu-id="452be-130">**Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.</span></span>

### <span data-ttu-id="452be-131">Adicionar uma segunda conta</span><span class="sxs-lookup"><span data-stu-id="452be-131">Add a second account</span></span>
<a id="add-a-second-account" class="xliff"></a>

<span data-ttu-id="452be-132">Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="452be-132">If you are using an iOS device, when you try to add a second work account on that device, you might see a blocking message.</span></span> <span data-ttu-id="452be-133">As contas serão exibidas e você poderá escolher a conta que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="452be-133">The accounts will be displayed, and then you can choose the account you want to remove.</span></span>

## <span data-ttu-id="452be-134">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="452be-134">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="452be-135">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="452be-135">What to expect when your Android app is managed by app protection policies</span></span>](end-user-mam-apps-android.md)
