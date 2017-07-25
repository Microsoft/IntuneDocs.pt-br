---
title: "Aplicativos iOS com políticas de proteção de aplicativo"
titleSuffix: Intune on Azure
description: "Este tópico descreve o que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 912bc5230904f5798b2e0026dcf0dd1cecdb811c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ad1bb-103">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ad1bb-103">What to expect when your iOS app is managed by app protection policies</span></span>
<a id="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies" class="xliff"></a>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]<span data-ttu-id="ad1bb-104"> Este tópico descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-104"> This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="ad1bb-105">Políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho, como acessar aplicativos usando sua conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-105">App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.</span></span>
##  <span data-ttu-id="ad1bb-106">Acessando aplicativos</span><span class="sxs-lookup"><span data-stu-id="ad1bb-106">Accessing apps</span></span>
<a id="accessing-apps" class="xliff"></a>

<span data-ttu-id="ad1bb-107">Se o dispositivo **não estiver registrado no Intune**, o usuário final será solicitado a reiniciar o aplicativo quando usar o aplicativo pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-107">If the device is **not enrolled in Intune**, the end-user will be asked to restart the app when they first use the app.</span></span>  <span data-ttu-id="ad1bb-108">Uma reinicialização é necessária para que as políticas de proteção de aplicativo possam ser aplicadas ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-108">A restart is required so app protection polices can be applied to the app.</span></span> <span data-ttu-id="ad1bb-109">A captura de tela a seguir ilustra isso usando o aplicativo Skype:</span><span class="sxs-lookup"><span data-stu-id="ad1bb-109">The following screenshot illustrates this using the Skype app:</span></span>


![captura de tela do dispositivo iOS mostrando a solicitação do PIN](./media/ios-pin-prompt.png)

<span data-ttu-id="ad1bb-111">Para dispositivos que estão **registrados para gerenciamento no Intune**, o usuário final verá uma mensagem informando que seu aplicativo agora é gerenciado:</span><span class="sxs-lookup"><span data-stu-id="ad1bb-111">For devices that are **enrolled for management in Intune**, the end-user will see a message that their app is now managed:</span></span>

![captura de tela do dispositivo iOS mostrando a mensagem de que ele é gerenciado pela empresa com a solicitação do PIN](./media/ios-managed-devices-pin-prompt.png)

##  <span data-ttu-id="ad1bb-113">Usando aplicativos com suporte a várias identidades</span><span class="sxs-lookup"><span data-stu-id="ad1bb-113">Using apps with multi-identity support</span></span>
<a id="using-apps-with-multi-identity-support" class="xliff"></a>

<span data-ttu-id="ad1bb-114">As políticas de proteção de aplicativo são aplicadas apenas no contexto de trabalho ao usar o aplicativo, de modo que você pode ver diferentes comportamentos de aplicativo dependendo do contexto: trabalho ou pessoal.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-114">App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.</span></span>  

<span data-ttu-id="ad1bb-115">Para aplicativos que dão suporte a várias identidades, o Intune aplica as políticas de proteção de aplicativo somente quando o usuário final estiver usando o aplicativo no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-115">For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.</span></span>  <span data-ttu-id="ad1bb-116">Por exemplo, o usuário final receberá um prompt para fornecer o PIN ao acessar dados de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-116">For example, the end-user will get a PIN prompt when accessing work data.</span></span>  <span data-ttu-id="ad1bb-117">Para o **aplicativo Outlook**, o usuário final será solicitado a fornecer um PIN ao iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-117">For the **Outlook app**, the end-user is prompted for a PIN on launching the app.</span></span> <span data-ttu-id="ad1bb-118">Para o **aplicativo OneDrive**, isso acontece quando o usuário final insere a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-118">For the **OneDrive app**, this happens when the end-user types in the work account.</span></span>  <span data-ttu-id="ad1bb-119">Para o Microsoft **Word**, **PowerPoint* e **Excel**, isso acontece quando o usuário final acessa os documentos armazenados no local do OneDrive for Business da empresa.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-119">For Microsoft **Word**, **PowerPoint*, and **Excel**, this happens when the end-user accesses documents stored in the company OneDrive for Business location.</span></span>
##  <span data-ttu-id="ad1bb-120">Gerenciando contas de usuário no dispositivo</span><span class="sxs-lookup"><span data-stu-id="ad1bb-120">Managing user accounts on the device</span></span>
<a id="managing-user-accounts-on-the-device" class="xliff"></a>

<span data-ttu-id="ad1bb-121">O Intune dá suporte somente a políticas de proteção de aplicativo para apenas uma conta de usuário por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-121">Intune only supports deploying app protection policies to only one user account per device.</span></span>

* <span data-ttu-id="ad1bb-122">Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-122">Depending on the app that you are using, the second user may or may not be blocked on the device.</span></span> <span data-ttu-id="ad1bb-123">No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-123">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>
  * <span data-ttu-id="ad1bb-124">**Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-124">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>  

  * <span data-ttu-id="ad1bb-125">Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-125">For **OneDrive and Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="ad1bb-126">A adição de várias contas corporativas é bloqueada nesses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-126">Adding multiple work accounts are blocked on these apps.</span></span>  <span data-ttu-id="ad1bb-127">É possível remover um usuário e adicionar um usuário diferente ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-127">You can however, remove a user and add a different user on the device.</span></span>

* <span data-ttu-id="ad1bb-128">Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-128">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="ad1bb-129">Leia o cenário de exemplo abaixo para obter uma compreensão mais profunda de como várias contas de usuário são tratadas.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-129">Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="ad1bb-130">O usuário A trabalha para duas empresas - **empresa X**, e **empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-130">User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="ad1bb-131">A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção de aplicativo, mas a conta associada à Empresa Y não a obterá. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção de aplicativo, será necessário remover a conta de usuário associada à Empresa X.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-131">**Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.</span></span>
### <span data-ttu-id="ad1bb-132">Adicionando uma segunda conta</span><span class="sxs-lookup"><span data-stu-id="ad1bb-132">Adding a second account</span></span>
<a id="adding-a-second-account" class="xliff"></a>

<span data-ttu-id="ad1bb-133">Se estiver usando um dispositivo iOS, ao tentar adicionar uma segunda conta corporativa ao mesmo dispositivo, você poderá ver uma mensagem de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-133">If you are using an iOS device, when you try to add a second work account on the same device, you may see a blocking message.</span></span>  <span data-ttu-id="ad1bb-134">As contas serão exibidas e você pode escolher a conta que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="ad1bb-134">The accounts will be displayed and you can choose the account you want to remove.</span></span>

![Captura de tela da caixa de diálogo com a mensagem de bloqueio e as opções Sim e Não](./media/ios-switch-user.PNG)

## <span data-ttu-id="ad1bb-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ad1bb-136">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="ad1bb-137">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="ad1bb-137">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
### <span data-ttu-id="ad1bb-138">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ad1bb-138">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="ad1bb-139">Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ad1bb-139">Create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
