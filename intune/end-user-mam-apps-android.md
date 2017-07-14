---
title: "Aplicativos Android com políticas de proteção do aplicativo"
description: "Este tópico descreve o que esperar quando seu aplicativo é gerenciado por políticas de proteção de aplicativo."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 030e17a9f28a9476c82e89d4dd26151a2d3cb953
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <span data-ttu-id="0908f-103">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="0908f-103">What to expect when your Android app is managed by app protection policies</span></span>
<a id="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="0908f-104">Este tópico descreve a experiência do usuário para aplicativos com políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0908f-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="0908f-105">As políticas do aplicativo são aplicadas somente quando aplicativos são usados em um contexto de trabalho: por exemplo, para acessar aplicativos com uma conta corporativa ou acessar arquivos armazenados no local de negócios do OneDrive de uma empresa.</span><span class="sxs-lookup"><span data-stu-id="0908f-105">App protection policies are applied only when apps are used in a work context: for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive business location.</span></span>
##  <span data-ttu-id="0908f-106">Acessar aplicativos</span><span class="sxs-lookup"><span data-stu-id="0908f-106">Access apps</span></span>
<a id="access-apps" class="xliff"></a>

<span data-ttu-id="0908f-107">O aplicativo Portal da Empresa é necessário para todos os aplicativos que estão associados a políticas de proteção de aplicativo em dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="0908f-107">The Company Portal app is required for all apps that are associated with app protection policies on Android devices.</span></span>

<span data-ttu-id="0908f-108">É necessário instalar o aplicativo do Portal da Empresa em dispositivos não registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="0908f-108">For devices that are not enrolled in Intune, the Company Portal app must be installed on the device.</span></span> <span data-ttu-id="0908f-109">No entanto, o usuário não precisa iniciar ou entrar no aplicativo do Portal da Empresa antes de ter permissão para usar aplicativos gerenciados por políticas de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0908f-109">However, the user does not have to launch  or sign into the Company Portal app before they can use apps that are managed by app protection policies.</span></span>

<span data-ttu-id="0908f-110">O aplicativo do Portal da Empresa é uma forma do Intune compartilhar dados em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="0908f-110">The Company Portal app is a way for Intune to share data in a secure location.</span></span> <span data-ttu-id="0908f-111">Portanto, o aplicativo do Portal da Empresa é um requisito para todos os aplicativos associados a políticas de proteção do aplicativo, mesmo se o dispositivo não estiver registrado no Intune.</span><span class="sxs-lookup"><span data-stu-id="0908f-111">Therefore, the Company Portal app is a requirement for all apps that are associated with app protection policies, even if the device is not enrolled in Intune.</span></span>


##  <span data-ttu-id="0908f-112">Usar aplicativos com suporte a várias identidades</span><span class="sxs-lookup"><span data-stu-id="0908f-112">Use apps with multi-identity support</span></span>
<a id="use-apps-with-multi-identity-support" class="xliff"></a>

<span data-ttu-id="0908f-113">As políticas de proteção do aplicativo são aplicadas apenas em contextos corporativos.</span><span class="sxs-lookup"><span data-stu-id="0908f-113">App protection polices are only applied in the work context.</span></span> <span data-ttu-id="0908f-114">Desse modo, o aplicativo pode se comportar de forma diferente, de acordo com o contexto – de trabalho ou pessoal.</span><span class="sxs-lookup"><span data-stu-id="0908f-114">Therefore, the app might behave differently depending on whether the context is work or personal.</span></span>

<span data-ttu-id="0908f-115">Por exemplo, o usuário receberá uma solicitação para fornecer o PIN ao acessar dados de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0908f-115">For example, the user gets a PIN prompt when accessing work data.</span></span> <span data-ttu-id="0908f-116">No **aplicativo Outlook**, o usuário será solicitado a fornecer um PIN ao iniciar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0908f-116">For the **Outlook app**, the user is prompted for a PIN when they launch the app.</span></span> <span data-ttu-id="0908f-117">No **aplicativo OneDrive**, o PIN será solicitado ao inserir a conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="0908f-117">For the **OneDrive app**, the user is prompted for the pin when they type in the work account.</span></span> <span data-ttu-id="0908f-118">No Microsoft **Word**, **PowerPoint** e **Excel**, o PIN será solicitado ao acessar os documentos armazenados no local do OneDrive for Business da empresa.</span><span class="sxs-lookup"><span data-stu-id="0908f-118">For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for the pin when they access documents that are stored in the company OneDrive for Business location.</span></span>

##  <span data-ttu-id="0908f-119">Gerenciar contas de usuário no dispositivo</span><span class="sxs-lookup"><span data-stu-id="0908f-119">Manage user accounts on the device</span></span>
<a id="manage-user-accounts-on-the-device" class="xliff"></a>

<span data-ttu-id="0908f-120">O Intune só dá suporte à implantação de políticas de proteção do aplicativo a uma conta de usuário por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0908f-120">Intune  supports the deployment of app protection policies to one user account per device only.</span></span>

* <span data-ttu-id="0908f-121">Dependendo do aplicativo que você estiver usando, o segundo usuário poderá ser bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0908f-121">Depending on the app that you're using, the second user might be blocked on the device.</span></span> <span data-ttu-id="0908f-122">No entanto, em todos os casos, somente o primeiro usuário que obtiver as políticas de proteção de aplicativo será afetado pela política.</span><span class="sxs-lookup"><span data-stu-id="0908f-122">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>

  * <span data-ttu-id="0908f-123">**Microsoft Word**, **Excel** e **PowerPoint** não bloqueiam uma segunda conta de usuário, porém a segunda conta de usuário não é afetada pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0908f-123">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>

  * <span data-ttu-id="0908f-124">Nos **aplicativos OneDrive** e **Outlook**, é possível usar somente uma conta corporativa.</span><span class="sxs-lookup"><span data-stu-id="0908f-124">For **OneDrive** and **Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="0908f-125">Não é possível adicionar várias contas corporativas a esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="0908f-125">You can't add multiple work accounts for these apps.</span></span>  <span data-ttu-id="0908f-126">É possível remover um usuário e adicionar um usuário diferente ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0908f-126">You can however, remove a user and add a different user on the device.</span></span>


* <span data-ttu-id="0908f-127">Se um dispositivo existente tiver várias contas de usuário antes das políticas de proteção de aplicativo serem implantadas, a conta em que as políticas de proteção de aplicativo forem implantadas primeiro será gerenciada pelas políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="0908f-127">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="0908f-128">Leia o cenário de exemplo a seguir para entender melhor como várias contas de usuário são tratadas.</span><span class="sxs-lookup"><span data-stu-id="0908f-128">Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="0908f-129">O usuário A trabalha para duas empresas – **Empresa X** e **Empresa Y**. O usuário A tem uma conta corporativa para cada empresa e ambas usam o Intune para implantar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0908f-129">User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="0908f-130">A **Empresa X** implanta políticas de proteção de aplicativo **antes da** **Empresa Y**. A conta associada à **Empresa X** obterá a política de proteção do aplicativo, mas não a conta associada à Empresa Y. Se você quiser que a conta de usuário associada à Empresa Y seja gerenciada pelas políticas de proteção do aplicativo, será necessário remover a conta de usuário associada à Empresa X.</span><span class="sxs-lookup"><span data-stu-id="0908f-130">**Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.</span></span>
### <span data-ttu-id="0908f-131">Adicionar uma segunda conta</span><span class="sxs-lookup"><span data-stu-id="0908f-131">Add a second account</span></span>
<a id="add-a-second-account" class="xliff"></a>
####  <span data-ttu-id="0908f-132">Android</span><span class="sxs-lookup"><span data-stu-id="0908f-132">Android</span></span>
<a id="android" class="xliff"></a>
<span data-ttu-id="0908f-133">Se estiver usando um dispositivo Android, você poderá ver uma mensagem de bloqueio com instruções para remover a conta existente e adicionar uma nova.</span><span class="sxs-lookup"><span data-stu-id="0908f-133">If you are using an Android device, you might see a blocking message with instructions to remove the existing account and add a new one.</span></span>  <span data-ttu-id="0908f-134">Para remover a conta existente, vá para **Configurações &gt;Geral &gt; Gerenciador de Aplicativos &gt;Portal da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="0908f-134">To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal.**</span></span> <span data-ttu-id="0908f-135">Então, escolha **Limpar Dados**.</span><span class="sxs-lookup"><span data-stu-id="0908f-135">Then choose **Clear Data**.</span></span>

![Captura de tela da mensagem de erro e as instruções para remover a conta](./media/Android_SwitchUser.png)

##  <span data-ttu-id="0908f-137">Exibir arquivos de mídia com o aplicativo de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="0908f-137">View media files with the Azure Information Protection app</span></span>
<a id="view-media-files-with-the-azure-information-protection-app" class="xliff"></a>
<span data-ttu-id="0908f-138">Para exibir os arquivos AV, PDF e de imagem da empresa em dispositivos Android, use o [aplicativo Proteção de Informações do Azure](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (conhecido anteriormente como aplicativo de compartilhamento do Rights Management).</span><span class="sxs-lookup"><span data-stu-id="0908f-138">To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (previously known as the Rights Management sharing app).</span></span>

<span data-ttu-id="0908f-139">Baixe esse aplicativo na loja do Google Play.</span><span class="sxs-lookup"><span data-stu-id="0908f-139">Download this app from the Google Play store.</span></span>  

<span data-ttu-id="0908f-140">Há suporte para os tipos de arquivo a seguir:</span><span class="sxs-lookup"><span data-stu-id="0908f-140">The following file types are supported:</span></span>

* <span data-ttu-id="0908f-141">**Áudio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (AAC+ aprimorado), AAC ELD (AAC com pouco atraso aprimorado), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE</span><span class="sxs-lookup"><span data-stu-id="0908f-141">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE</span></span>
* <span data-ttu-id="0908f-142">**Vídeo:** H.263, H.264 AVC, MPEG-4 SP, VP8</span><span class="sxs-lookup"><span data-stu-id="0908f-142">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8</span></span>
* <span data-ttu-id="0908f-143">**Imagem:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg</span><span class="sxs-lookup"><span data-stu-id="0908f-143">**Image:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg</span></span>
* <span data-ttu-id="0908f-144">**Documentos:** PDF, PPDF</span><span class="sxs-lookup"><span data-stu-id="0908f-144">**Documents:** PDF, PPDF</span></span>


|<span data-ttu-id="0908f-145">**pfile**</span><span class="sxs-lookup"><span data-stu-id="0908f-145">**pfile**</span></span>|<span data-ttu-id="0908f-146">**text**</span><span class="sxs-lookup"><span data-stu-id="0908f-146">**text**</span></span>|
|----|----|
|<span data-ttu-id="0908f-147">Pfile é um formato genérico “wrapper” para arquivos protegidos que encapsula o conteúdo criptografado e as licenças da Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="0908f-147">Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses.</span></span> <span data-ttu-id="0908f-148">Ele pode ser usado para proteger qualquer tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="0908f-148">It can be used to protect any file type.</span></span>|<span data-ttu-id="0908f-149">Arquivos de texto, inclusive XML, CSV etc. podem ser abertos para visualização no aplicativo, mesmo quando são protegidos.</span><span class="sxs-lookup"><span data-stu-id="0908f-149">Text files, including XML, CSV, and so on, can be opened for viewing in the app even when they are protected.</span></span> <span data-ttu-id="0908f-150">Tipos de arquivo: .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.</span><span class="sxs-lookup"><span data-stu-id="0908f-150">File types: .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.</span></span>|

## <span data-ttu-id="0908f-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0908f-151">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="0908f-152">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="0908f-152">What to expect when your iOS app is managed by app protection policies</span></span>](end-user-mam-apps-ios.md)
