---
title: Atribuir aplicativos a dispositivos Android for Work
titleSuffix: Intune on Azure
description: "Use este tópico para sincronizar e, depois, atribuir aplicativos a dispositivos Android for Work da Google Play for Work Store."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 94394a889d97b4d1bdf09303b11cdc3688e4f55a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b94c8-103">Como atribuir aplicativos em dispositivos Android for Work com o Intune</span><span class="sxs-lookup"><span data-stu-id="b94c8-103">How to assign apps to Android for Work devices with Intune</span></span>
<a id="how-to-assign-apps-to-android-for-work-devices-with-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b94c8-104">A maneira pela qual aplicativos são atribuídos em dispositivos Android for Work e dispositivos Android padrão é diferente.</span><span class="sxs-lookup"><span data-stu-id="b94c8-104">You assign apps to Android for Work devices in a different way than you assign them to standard Android devices.</span></span> <span data-ttu-id="b94c8-105">Todos os aplicativos instalados no Android for Work são obtidos na loja do Google Play for Work.</span><span class="sxs-lookup"><span data-stu-id="b94c8-105">All apps you install for Android for Work come from the Google Play for Work store.</span></span> <span data-ttu-id="b94c8-106">Faça logon na loja, procure os aplicativos desejados e aprove-os.</span><span class="sxs-lookup"><span data-stu-id="b94c8-106">You log on to the store, browse for the apps you want, and approve them.</span></span>
<span data-ttu-id="b94c8-107">Então, o aplicativo aparecerá no nó **Aplicativos licenciados** do portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="b94c8-107">The app then appears in the **Licensed apps** node of the Intune portal.</span></span> <span data-ttu-id="b94c8-108">A partir desse momento, é possível gerenciar a atribuição do aplicativo do mesmo modo que você atribui qualquer outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b94c8-108">From here, you can manage assignment of the app in the same way you would assign any other app.</span></span>

<span data-ttu-id="b94c8-109">Além disso, se você criou seus próprios aplicativos LOB (linha de negócios), poderá atribuí-los da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b94c8-109">Additionally, if you have created your own line of business (LOB) apps, you can assign them as follows:</span></span>
- <span data-ttu-id="b94c8-110">Inscreva-se em uma conta de Desenvolvedor do Google que permite publicar aplicativos em uma área particular da Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="b94c8-110">Sign up for a Google Developer account that lets you publish apps to a private area in the Google Play store.</span></span>
- <span data-ttu-id="b94c8-111">Sincronize os aplicativos com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b94c8-111">Synchronize the apps with Intune.</span></span>

## <span data-ttu-id="b94c8-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b94c8-112">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="b94c8-113">Verifique se você configurou o Intune e o Android for Work para trabalharem juntos na carga de trabalho **Registro de dispositivo** do portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="b94c8-113">Make sure you have configured Intune and Android for Work to work together in the **Device enrollment** workload of the Intune portal.</span></span>

## <span data-ttu-id="b94c8-114">Sincronize um aplicativo da loja do Google Play for Work</span><span class="sxs-lookup"><span data-stu-id="b94c8-114">Synchronize an app from the Google Play for Work store</span></span>
<a id="synchronize-an-app-from-the-google-play-for-work-store" class="xliff"></a>

1. <span data-ttu-id="b94c8-115">Vá para a [loja do Google Play for Work](https://play.google.com/work).</span><span class="sxs-lookup"><span data-stu-id="b94c8-115">Go to the [Google Play for Work store](https://play.google.com/work).</span></span> <span data-ttu-id="b94c8-116">Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.</span><span class="sxs-lookup"><span data-stu-id="b94c8-116">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span>
2. <span data-ttu-id="b94c8-117">Pesquise o aplicativo que deseja atribuir usando o Intune.</span><span class="sxs-lookup"><span data-stu-id="b94c8-117">Search the store for the app you want to assign using Intune.</span></span>
3. <span data-ttu-id="b94c8-118">Na página do aplicativo que você escolheu, escolha **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="b94c8-118">On the page for the app you chose, choose **Approve**.</span></span> <span data-ttu-id="b94c8-119">Neste exemplo, você escolheu o aplicativo Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="b94c8-119">In this example, you have chosen the Microsoft Excel app.</span></span><br><span data-ttu-id="b94c8-120">
  ![Aprovar o exemplo de aplicativo](media/approve.png)</span><span class="sxs-lookup"><span data-stu-id="b94c8-120">
![Approve app example](media/approve.png)</span></span>
4. <span data-ttu-id="b94c8-121">Uma janela do aplicativo se abrirá solicitando que você conceda permissões para o aplicativo executar várias operações.</span><span class="sxs-lookup"><span data-stu-id="b94c8-121">A window for the app opens asking you to give permissions for the app to perform various operations.</span></span> <span data-ttu-id="b94c8-122">Escolha **Aprovar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="b94c8-122">Choose **Approve** to continue.</span></span><br><span data-ttu-id="b94c8-123">
  ![Aprovar o exemplo de permissões de aplicativo](media/approve-app-permissions.png)</span><span class="sxs-lookup"><span data-stu-id="b94c8-123">
![Approve app permissions example](media/approve-app-permissions.png)</span></span>
5. <span data-ttu-id="b94c8-124">O aplicativo foi aprovado e é exibido no console do administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="b94c8-124">The app is approved and displays in your IT admin console.</span></span>

## <span data-ttu-id="b94c8-125">Publicar e, em seguida, sincronizar um aplicativo de linha de negócios da Google Play for Work Store</span><span class="sxs-lookup"><span data-stu-id="b94c8-125">Publish, then synchronize, a line-of-business app from the Google Play for Work store</span></span>
<a id="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store" class="xliff"></a>

1. <span data-ttu-id="b94c8-126">Acesse o Console do Desenvolvedor do Google Play, em [play.google.com/apps/publish](https://play.google.com/apps/publish).</span><span class="sxs-lookup"><span data-stu-id="b94c8-126">Go to the Google Play Developer Console, [play.google.com/apps/publish](https://play.google.com/apps/publish).</span></span>
2. <span data-ttu-id="b94c8-127">Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.</span><span class="sxs-lookup"><span data-stu-id="b94c8-127">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span> <span data-ttu-id="b94c8-128">Se você estiver entrando pela primeira vez, será necessário se registrar e pagar uma taxa para se tornar membro do programa de Desenvolvedor do Google.</span><span class="sxs-lookup"><span data-stu-id="b94c8-128">If you are signing in for the first time, you must register, and pay a fee to become a member of the Google Developer program.</span></span>
3. <span data-ttu-id="b94c8-129">No console, escolha **Adicionar novo aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="b94c8-129">In the console, choose **Add new application**.</span></span>
4. <span data-ttu-id="b94c8-130">Carregue e forneça informações sobre o aplicativo da mesma maneira que você publica aplicativos na loja do Google Play.</span><span class="sxs-lookup"><span data-stu-id="b94c8-130">You upload and provide information about your app in the same way as you publish any app to the Google Play store.</span></span> <span data-ttu-id="b94c8-131">No entanto, você deve selecionar a configuração **Disponibilizar este aplicativo somente para minha organização (<*nome da organização*>)**:</span><span class="sxs-lookup"><span data-stu-id="b94c8-131">However, you must select the setting **Only make this application available to my organization (<*organization name*>)**:</span></span><br><span data-ttu-id="b94c8-132">
  ![Opção para disponibilizar o aplicativo apenas para sua organização](media/restrict.png)</span><span class="sxs-lookup"><span data-stu-id="b94c8-132">
![Option to only make app available to your organization](media/restrict.png)</span></span><br>
<span data-ttu-id="b94c8-133">Essa operação garante que o aplicativo estará disponível apenas para sua organização e não na Google Play Store pública.</span><span class="sxs-lookup"><span data-stu-id="b94c8-133">This operation ensures that the app is only available to your organization, and is not available in the public Google Play store.</span></span>
<span data-ttu-id="b94c8-134">Para obter mais informações sobre como carregar e publicar aplicativos Android, consulte [Ajuda do Console do Desenvolvedor do Google](https://support.google.com/googleplay/android-developer/answer/113469).</span><span class="sxs-lookup"><span data-stu-id="b94c8-134">For more information about how to upload and publish Android apps, see the [Google Developer Console Help](https://support.google.com/googleplay/android-developer/answer/113469).</span></span>
5. <span data-ttu-id="b94c8-135">Depois publicar o aplicativo, vá para a [loja do Google Play for Work](https://play.google.com/work).</span><span class="sxs-lookup"><span data-stu-id="b94c8-135">Once you have published your app, go to the [Google Play for Work store](https://play.google.com/work).</span></span> <span data-ttu-id="b94c8-136">Entre com a mesma conta usada para configurar a conexão entre o Intune e o Android for Work.</span><span class="sxs-lookup"><span data-stu-id="b94c8-136">Sign in with the same account you used to configure the connection between Intune and Android for Work.</span></span>
6. <span data-ttu-id="b94c8-137">No nó **Aplicativos** da loja, verifique se o aplicativo que você publicou pode ser visto.</span><span class="sxs-lookup"><span data-stu-id="b94c8-137">In the **Apps** node of the store, verify you can see the app you have published.</span></span> <span data-ttu-id="b94c8-138">A sincronização do aplicativo com o Intune é aprovada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b94c8-138">The app is automatically approved to be synchronized with Intune.</span></span>

## <span data-ttu-id="b94c8-139">Atribuir um aplicativo Android for Work</span><span class="sxs-lookup"><span data-stu-id="b94c8-139">Assign an Android for Work app</span></span>
<a id="assign-an-android-for-work-app" class="xliff"></a>

<span data-ttu-id="b94c8-140">Se você aprovou um aplicativo da loja e ainda não o encontrou no nó **Aplicativos licenciados** da carga de trabalho **Aplicativos móveis**, force uma sincronização imediata da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="b94c8-140">If you have approved an app from the store and don't see it in the **Licensed apps** node of the **Mobile apps** workload, force an immediate sync as follows:</span></span>

1. <span data-ttu-id="b94c8-141">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b94c8-141">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b94c8-142">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="b94c8-142">On the **Intune** blade, choose **Mobile apps**.</span></span>
3. <span data-ttu-id="b94c8-143">Na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Android for Work**.</span><span class="sxs-lookup"><span data-stu-id="b94c8-143">In the **Mobile apps** workload, choose **Setup** > **Android for Work**.</span></span>
4. <span data-ttu-id="b94c8-144">Na folha Android for Work, escolha **Sincronizar Agora**.</span><span class="sxs-lookup"><span data-stu-id="b94c8-144">On the Android for Work blade, choose **Sync Now**.</span></span>
5. <span data-ttu-id="b94c8-145">A página também exibe o tempo e o status da última sincronização.</span><span class="sxs-lookup"><span data-stu-id="b94c8-145">The page also displays the time and status of the last sync.</span></span>

<span data-ttu-id="b94c8-146">Quando o aplicativo é exibido no nó **Aplicativos licenciados** da carga de trabalho **Aplicativos móveis**, você pode [atribuí-lo, assim como atribuiria qualquer outro aplicativo](/intune-azure/manage-apps/deploy-apps).</span><span class="sxs-lookup"><span data-stu-id="b94c8-146">When the app is displayed in the **Licensed apps** node of the **Mobile apps** workload, you can [assign it just like you would assign any other app](/intune-azure/manage-apps/deploy-apps).</span></span> <span data-ttu-id="b94c8-147">O aplicativo pode ser atribuído somente em grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="b94c8-147">You can assign the app to groups of users only.</span></span>

<span data-ttu-id="b94c8-148">Depois de atribuir o aplicativo, ele será instalado nos dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="b94c8-148">After you assign the app, it will be installed on the devices you targeted.</span></span> <span data-ttu-id="b94c8-149">A aprovação da instalação do dispositivo não é solicitada ao usuário.</span><span class="sxs-lookup"><span data-stu-id="b94c8-149">The user of the device is not asked to approve the installation.</span></span>

## <span data-ttu-id="b94c8-150">Gerenciar permissões de aplicativo do Android for Work</span><span class="sxs-lookup"><span data-stu-id="b94c8-150">Manage Android for Work app permissions</span></span>
<a id="manage-android-for-work-app-permissions" class="xliff"></a>
<span data-ttu-id="b94c8-151">O Android for Work exige que você aprove aplicativos no console da Web do Play gerenciado do Google antes de sincronizá-los para o Intune e atribuí-los para os usuários.</span><span class="sxs-lookup"><span data-stu-id="b94c8-151">Android for Work requires you approve apps in Google's managed Play web console before syncing them to Intune and assigning them to your users.</span></span>  <span data-ttu-id="b94c8-152">Como Android for Work permite que você envie de maneira silenciosa e automática esses aplicativos para os dispositivos dos usuários, você deve aceitar as permissões do aplicativo em nome de todos os seus usuários.</span><span class="sxs-lookup"><span data-stu-id="b94c8-152">Because Android for Work allows you to silently and automatically push these apps to users' devices, you must accept the app's permissions on behalf of all your users.</span></span>  <span data-ttu-id="b94c8-153">Os usuários finais não veem as permissões do aplicativo durante a instalação; portanto, é importante que você leia e entenda essas permissões.</span><span class="sxs-lookup"><span data-stu-id="b94c8-153">End users do not see any app permissions when they install, so it's important that you read and understand these permissions.</span></span>

<span data-ttu-id="b94c8-154">Quando um desenvolvedor de aplicativo publica uma nova versão do aplicativo com permissões atualizadas, essas permissões não são automaticamente aceitas, mesmo se você tiver aprovado as permissões anteriores.</span><span class="sxs-lookup"><span data-stu-id="b94c8-154">When an app developer publishes a new version of the app with updated permissions, those permissions are not automatically accepted, even if you've approved the previous permissions.</span></span> <span data-ttu-id="b94c8-155">Os dispositivos que executam a versão antiga do aplicativo ainda podem usá-lo.</span><span class="sxs-lookup"><span data-stu-id="b94c8-155">Devices that run the old version of the app can still use it.</span></span> <span data-ttu-id="b94c8-156">No entanto, só é feito o upgrade do aplicativo quando as novas permissões são aprovadas.</span><span class="sxs-lookup"><span data-stu-id="b94c8-156">However, the app is not upgraded until the new permissions are approved.</span></span> <span data-ttu-id="b94c8-157">Os dispositivos sem o aplicativo instalado só instalam o aplicativo quando você aprova as novas permissões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b94c8-157">Devices without the app installed do not install the app until you approve the app's new permissions.</span></span>

### <span data-ttu-id="b94c8-158">Como atualizar as permissões do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b94c8-158">How to update app permissions</span></span>
<a id="how-to-update-app-permissions" class="xliff"></a>

<span data-ttu-id="b94c8-159">Periodicamente, acesse o console gerenciado do Google Play para verificar se há novas permissões.</span><span class="sxs-lookup"><span data-stu-id="b94c8-159">Periodically visit the managed Google Play console to check for new permissions.</span></span> <span data-ttu-id="b94c8-160">Você pode configurar o Google Play para enviar um email a você ou a outras pessoas quando novas permissões forem necessárias para um aplicativo aprovado.</span><span class="sxs-lookup"><span data-stu-id="b94c8-160">You can configure Google Play to send you or others an e-mail when new permissions are required for an approved app.</span></span> <span data-ttu-id="b94c8-161">Se você atribuir um aplicativo e observar que ele não está instalado nos dispositivos, verifique se há novas permissões com as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="b94c8-161">If you assign an app and observe it isn't installed on devices, check for new permissions with the following steps:</span></span>

1. <span data-ttu-id="b94c8-162">Visite http://play.google.com/work</span><span class="sxs-lookup"><span data-stu-id="b94c8-162">Visit http://play.google.com/work</span></span>
2. <span data-ttu-id="b94c8-163">Entre com a conta do Google usada para publicar e aprovar os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b94c8-163">Sign in with the Google account you used to publish and approve the apps.</span></span>
3. <span data-ttu-id="b94c8-164">Visite a guia **Atualizações** para ver se algum aplicativo precisa de atualização.</span><span class="sxs-lookup"><span data-stu-id="b94c8-164">Visit the **Updates** tab to see if any apps require an update.</span></span>  <span data-ttu-id="b94c8-165">Os aplicativos listados exigem novas permissões e só são atribuídos quando elas são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="b94c8-165">Any listed apps require new permissions and are not assigned until they are applied.</span></span>  

<span data-ttu-id="b94c8-166">Como alternativa, você pode configurar o Google Play para aprovar permissões de aplicativo novamente de forma automática por aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b94c8-166">Alternatively, you can configure Google Play to automatically reapprove app permissions on a per app basis.</span></span> 



