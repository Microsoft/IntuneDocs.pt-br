---
title: "<span data-ttu-id=\"dfb29-101\">Aplicativos Android com políticas de proteção do aplicativo</span><span class=\"sxs-lookup\"><span data-stu-id=\"dfb29-101\">Android apps with app protection policies</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"dfb29-102\">Este tópico descreve o que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo.</span><span class=\"sxs-lookup\"><span data-stu-id=\"dfb29-102\">This topic describes what to expect when your Android app is managed by app protection policies.\"</span></span>"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 63badd001958f22339415e0cd03da9ade275c6f3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="dfb29-103">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="dfb29-103">What to expect when your Android app is managed by app protection policies</span></span>
<a id="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies" class="xliff"></a> 
[!INCLUDE[azure_portal](./includes/azure_portal.md)]<span data-ttu-id="dfb29-104">Este tópico descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-104"> This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="dfb29-105">Políticas de proteção de aplicativo são aplicadas somente quando os aplicativos são usados no contexto de trabalho, como acessar aplicativos usando sua conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="dfb29-105">App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.</span></span>
##  <span data-ttu-id="dfb29-106">Acessando aplicativos</span><span class="sxs-lookup"><span data-stu-id="dfb29-106">Accessing apps</span></span>
<a id="accessing-apps" class="xliff"></a>

<span data-ttu-id="dfb29-107">O aplicativo Portal da Empresa é necessário para todos os aplicativos associados a políticas de proteção de aplicativo em dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="dfb29-107">The Company Portal app is required for all apps associated with app protection policies on Android devices.</span></span>

<span data-ttu-id="dfb29-108">Para dispositivos não registrados no Intune, o aplicativo de Portal da Empresa deve ser instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-108">For devices not enrolled in Intune, the Company Portal app must be installed on the device.</span></span> <span data-ttu-id="dfb29-109">No entanto, o usuário não precisa iniciar nem entrar no aplicativo de Portal da Empresa antes que possam usar aplicativos gerenciados por políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-109">However, user does not have to launch  or sign into the Company Portal app before they can use apps managed by app protection policies.</span></span>
<span data-ttu-id="dfb29-110">O aplicativo de Portal da Empresa é uma forma do Intune compartilhar dados em um local seguro. Portanto, isto é um requisito mesmo que o dispositivo não esteja registrado no Intune.</span><span class="sxs-lookup"><span data-stu-id="dfb29-110">The Company Portal app is a way for Intune to share data in a secure location, hence this is a requirement even if the device is not enrolled in Intune.</span></span>


##  <span data-ttu-id="dfb29-111">Usando aplicativos com suporte a várias identidades</span><span class="sxs-lookup"><span data-stu-id="dfb29-111">Using apps with multi-identity support</span></span>
<a id="using-apps-with-multi-identity-support" class="xliff"></a>

<span data-ttu-id="dfb29-112">As políticas de proteção de aplicativo são aplicadas apenas no contexto de trabalho ao usar o aplicativo, de modo que você pode ver diferentes comportamentos de aplicativo dependendo do contexto: trabalho ou pessoal.</span><span class="sxs-lookup"><span data-stu-id="dfb29-112">App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.</span></span>

<span data-ttu-id="dfb29-113">Para aplicativos que dão suporte a várias identidades, o Intune aplica as políticas de proteção de aplicativo somente quando o usuário final estiver usando o aplicativo no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dfb29-113">For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.</span></span>  <span data-ttu-id="dfb29-114">Por exemplo, o usuário final receberá um prompt para fornecer o PIN ao acessar dados de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dfb29-114">For example, the end-user will get a PIN prompt when accessing work data.</span></span>  <span data-ttu-id="dfb29-115">Para o **aplicativo Outlook**, o usuário final será solicitado a fornecer um PIN ao iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-115">For the **Outlook app**, the end-user is prompted for a PIN on launching the app.</span></span> <span data-ttu-id="dfb29-116">Para o **aplicativo OneDrive**, isso acontece quando o usuário final insere a conta de trabalho.</span><span class="sxs-lookup"><span data-stu-id="dfb29-116">For the **OneDrive app**, this happens when the end-user types in the work account.</span></span>  <span data-ttu-id="dfb29-117">Para o Microsoft **Word**, **PowerPoint* e **Excel**, isso acontece quando o usuário final acessa os documentos armazenados no local do OneDrive for Business da empresa.</span><span class="sxs-lookup"><span data-stu-id="dfb29-117">For Microsoft **Word**, **PowerPoint*, and **Excel**, this happens when the end-user accesses documents stored in the company OneDrive for Business location.</span></span>
##  <span data-ttu-id="dfb29-118">Gerenciando contas de usuário no dispositivo</span><span class="sxs-lookup"><span data-stu-id="dfb29-118">Managing user accounts on the device</span></span>
<a id="managing-user-accounts-on-the-device" class="xliff"></a>

<span data-ttu-id="dfb29-119">O Intune dá suporte somente a políticas de proteção de aplicativo para apenas uma conta de usuário por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-119">Intune only supports deploying app protection policies to only one user account per device.</span></span>

* <span data-ttu-id="dfb29-120">Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ou não ser bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-120">Depending on the app that you are using, the second user may or may not be blocked on the device.</span></span> <span data-ttu-id="dfb29-121">No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.</span><span class="sxs-lookup"><span data-stu-id="dfb29-121">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>

  * <span data-ttu-id="dfb29-122">**Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-122">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>

  * <span data-ttu-id="dfb29-123">Para os **aplicativos OneDrive e Outlook**, só pode ser usada uma conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="dfb29-123">For **OneDrive and Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="dfb29-124">A adição de várias contas corporativas é bloqueada nesses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="dfb29-124">Adding multiple work accounts are blocked on these apps.</span></span>  <span data-ttu-id="dfb29-125">É possível remover um usuário e adicionar um usuário diferente ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-125">You can however, remove a user and add a different user on the device.</span></span>


* <span data-ttu-id="dfb29-126">Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="dfb29-126">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="dfb29-127">Leia o cenário de exemplo abaixo para obter uma compreensão mais profunda de como várias contas de usuário são tratadas.</span><span class="sxs-lookup"><span data-stu-id="dfb29-127">Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="dfb29-128">O usuário A trabalha para duas empresas - **empresa X**, e **empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-128">User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="dfb29-129">A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção de aplicativo, mas a conta associada à Empresa Y não a obterá. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção de aplicativo, será necessário remover a conta de usuário associada à Empresa X.</span><span class="sxs-lookup"><span data-stu-id="dfb29-129">**Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.</span></span>
### <span data-ttu-id="dfb29-130">Adicionando uma segunda conta</span><span class="sxs-lookup"><span data-stu-id="dfb29-130">Adding a second account</span></span>
<a id="adding-a-second-account" class="xliff"></a>
####  <span data-ttu-id="dfb29-131">Android</span><span class="sxs-lookup"><span data-stu-id="dfb29-131">Android</span></span>
<a id="android" class="xliff"></a>
<span data-ttu-id="dfb29-132">Se estiver usando um dispositivo Android, você poderá ver uma mensagem de bloqueio com instruções para remover a conta existente e adicionar uma nova.</span><span class="sxs-lookup"><span data-stu-id="dfb29-132">If you are using an Android device, you may see a blocking message with instructions to remove the existing account and add a new one.</span></span>  <span data-ttu-id="dfb29-133">Para remover a conta existente, vá para **Configurações &gt;Geral &gt; Gerenciador de Aplicativos &gt;Portal da Empresa e selecione "Limpar Dados"**.</span><span class="sxs-lookup"><span data-stu-id="dfb29-133">To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal and select "Clear Data"**.</span></span>

![Captura de tela da mensagem de erro e as instruções para remover a conta](./media/android-switch-user.png)

##  <span data-ttu-id="dfb29-135">Exibindo arquivos de mídia com o aplicativo Proteção de Informações do Azure (anteriormente conhecido como aplicativo de compartilhamento Rights Management)</span><span class="sxs-lookup"><span data-stu-id="dfb29-135">Viewing media files with the Azure Information Protection app (previously known as Rights Management sharing app)</span></span>
<a id="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app" class="xliff"></a>
<span data-ttu-id="dfb29-136">Para exibir os arquivos AV, PDF e de imagem em dispositivos Android, use o [aplicativo Proteção de Informações do Azure](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).</span><span class="sxs-lookup"><span data-stu-id="dfb29-136">To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).</span></span>

<span data-ttu-id="dfb29-137">Baixe este aplicativo da Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="dfb29-137">Download this app from the  Google Play store.</span></span>  

<span data-ttu-id="dfb29-138">Os tipos de arquivo a seguir têm suporte:</span><span class="sxs-lookup"><span data-stu-id="dfb29-138">The following filetypes are supported:</span></span>

* <span data-ttu-id="dfb29-139">**Áudio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ aprimorado), AAC ELD (AAC com pouco atraso aprimorado), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.</span><span class="sxs-lookup"><span data-stu-id="dfb29-139">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.</span></span>
* <span data-ttu-id="dfb29-140">**Vídeo:** H.263, H.264 AVC, MPEG-4 SP, VP8.</span><span class="sxs-lookup"><span data-stu-id="dfb29-140">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.</span></span>
* <span data-ttu-id="dfb29-141">**Imagem:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.</span><span class="sxs-lookup"><span data-stu-id="dfb29-141">**Image:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.</span></span>
* <span data-ttu-id="dfb29-142">**Documentos:** PDF, PPDF</span><span class="sxs-lookup"><span data-stu-id="dfb29-142">**Documents:** PDF, PPDF</span></span>

------------
|<span data-ttu-id="dfb29-143">**pfile**</span><span class="sxs-lookup"><span data-stu-id="dfb29-143">**pfile**</span></span>|<span data-ttu-id="dfb29-144">**text**</span><span class="sxs-lookup"><span data-stu-id="dfb29-144">**text**</span></span>|
|----|----|
|<span data-ttu-id="dfb29-145">Pfile é um formato genérico “wrapper” para arquivos protegidos que encapsula o conteúdo criptografado e as licenças da Proteção de Informações do Azure e podem ser usadas para proteger qualquer tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="dfb29-145">Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses and can be used to protect any file type.</span></span>|<span data-ttu-id="dfb29-146">Arquivos de texto, inclusive XML, CSV etc. podem ser abertos para visualização no aplicativo, mesmo quando eles são protegidos.</span><span class="sxs-lookup"><span data-stu-id="dfb29-146">Text files, including XML, CSV, etc. can be opened for viewing in the app even when they are protected.</span></span> <span data-ttu-id="dfb29-147">Tipos de arquivo: txt, ptxt, csv, pcsv, log, plog, xml, pxml.</span><span class="sxs-lookup"><span data-stu-id="dfb29-147">File types: txt, ptxt, csv, pcsv, log, plog, xml, pxml.</span></span>|
---------------
## <span data-ttu-id="dfb29-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dfb29-148">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="dfb29-149">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="dfb29-149">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)

### <span data-ttu-id="dfb29-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dfb29-150">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="dfb29-151">Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dfb29-151">Create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
