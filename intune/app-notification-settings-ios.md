---
title: "Configurações de notificação de aplicativo do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar para controlar as notificações de aplicativos em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36a9e9a5be9b2dc45ded1a99c7a5871780f7d9b2
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
<<<<<<< HEAD
# <span data-ttu-id="b0ca5-103">Configurações de notificação de aplicativo do Intune para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="b0ca5-103">Intune app notifications settings for iOS devices</span></span>
=======
# Configurações de notificação de aplicativo do Intune para dispositivos iOS
>>>>>>> live
<a id="intune-app-notifications-settings-for-ios-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="b0ca5-104">Permite a configuração de como os aplicativos instalados em um dispositivo enviam notificações.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-104">Lets you configure how apps installed on a device send notifications.</span></span> <span data-ttu-id="b0ca5-105">Essa configuração dá suporte a dispositivos supervisionados que executam o iOS 9.3 e posterior.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-105">These settings support supervised devices running iOS 9.3 and later.</span></span>

## <span data-ttu-id="b0ca5-106">Definir configurações</span><span class="sxs-lookup"><span data-stu-id="b0ca5-106">Configure settings</span></span>
<a id="configure-settings" class="xliff"></a>

1. <span data-ttu-id="b0ca5-107">Na folha Recursos do dispositivo escolha **Notificações de Aplicativo (somente supervisionado)**.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-107">On the Device features blade, choose **App Notifications (supervised only)**.</span></span>
2. <span data-ttu-id="b0ca5-108">Na folha **Notificações do Aplicativo**, escolha **Adicionar** e configure os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b0ca5-108">On the **App Notifications** blade, choose **Add**, and then configure the following values:</span></span>
    - <span data-ttu-id="b0ca5-109">**ID do pacote de aplicativos** - insira a **ID do Pacote de Aplicativos** do aplicativo que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-109">**App bundle ID** - Enter the **App Bundle ID** of the app you want to configure.</span></span> <span data-ttu-id="b0ca5-110">Consulte **Referência da ID de Pacote para aplicativos iOS internos** mais adiante neste tópico para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-110">See **Bundle ID reference for built-in iOS apps** later in this topic for help.</span></span>
    - <span data-ttu-id="b0ca5-111">**Nome do aplicativo** - insira o nome do aplicativo que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-111">**App name** - Enter the name of the app you want to configure.</span></span> <span data-ttu-id="b0ca5-112">Esse nome não é exibido no dispositivo e é usado para ajudar a identificar o aplicativo na lista.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-112">This name is not displayed on the device and is used to help you identify the app in the list.</span></span>
    - <span data-ttu-id="b0ca5-113">**Editor** - insira o editor que você deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-113">**Publisher** - Enter the publisher of the app you want to configure.</span></span> <span data-ttu-id="b0ca5-114">O nome do publicador não é exibido no dispositivo e é usado somente para ajudar a identificar o aplicativo na lista.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-114">The publisher name is not displayed on the device, and is used only to help you identify the app in the list.</span></span>
    - <span data-ttu-id="b0ca5-115">**Notificações** - habilite ou desabilite o envio de notificações para o dispositivo pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-115">**Notifications** - Enable or disable the app from sending notifications to the device.</span></span> <span data-ttu-id="b0ca5-116">Se você desabilitar essa configuração, as configurações a seguir também serão desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-116">If you disable this setting, the following settings are also disabled.</span></span>
        - <span data-ttu-id="b0ca5-117">**Mostrar no Centro de Notificações** – Habilite essa definição para permitir que o aplicativo mostre as notificações no Centro de Notificações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-117">**Show in Notification Center** - Enable this setting to allow the app to show notifications in the device Notification Center.</span></span>
        - <span data-ttu-id="b0ca5-118">**Mostrar na Tela de Bloqueio** – Habilite essa definição para ver as notificações do aplicativo na tela de bloqueio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-118">**Show in Lock Screen** - Enable this setting to see notifications from the app on the device lock screen.</span></span>
        - <span data-ttu-id="b0ca5-119">**Tipo de alerta** - selecione o tipo de notificação desejado quando o dispositivo for desbloqueado entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b0ca5-119">**Alert type** - Select the type of notification you want when the device is unlocked from:</span></span>
            - <span data-ttu-id="b0ca5-120">**Nenhuma** - nenhuma notificação é exibida.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-120">**None** - No notification is displayed.</span></span>
            - <span data-ttu-id="b0ca5-121">**Faixa** - uma faixa é exibida rapidamente mostrando a notificação.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-121">**Banner** - A banner is briefly displayed showing the notification.</span></span>
            - <span data-ttu-id="b0ca5-122">**Modal** - a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-122">**Modal** - The notification is displayed and the user must manually dismiss it before you can continue to use the device.</span></span>
        - <span data-ttu-id="b0ca5-123">**Notificação no ícone do aplicativo** – Habilite esta definição para adicionar uma notificação ao ícone do aplicativo a fim de indicar que o aplicativo enviou uma notificação.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-123">**Badge on app icon** - Enable this setting to add a badge to the app icon to indicate the app sent a notification.</span></span>
        - <span data-ttu-id="b0ca5-124">**Sons** – Habilite esta definição para tocar um som quando uma notificação for entregue.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-124">**Sounds** - Enable this setting to play a sound when a notification is delivered.</span></span>
3. <span data-ttu-id="b0ca5-125">Continue adicionando quantos aplicativos forem necessários.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-125">Continue to add as many apps as you need.</span></span> <span data-ttu-id="b0ca5-126">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-126">When you are finished, choose **OK**.</span></span>
4. <span data-ttu-id="b0ca5-127">Escolha **OK** em até voltar à folha **Criar Perfil**, depois escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-127">Choose **OK** until you return to the **Create Profile** blade, then choose **Create**.</span></span> 


## <span data-ttu-id="b0ca5-128">Referência de ID de Pacote para aplicativos iOS internos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-128">Bundle ID reference for built-in iOS apps</span></span>
=======
Permite a configuração de como os aplicativos instalados em um dispositivo enviam notificações. Essa configuração dá suporte a dispositivos supervisionados que executam o iOS 9.3 e posterior.

## Definir configurações
<a id="configure-settings" class="xliff"></a>

1. Na folha Recursos do dispositivo escolha **Notificações de Aplicativo (somente supervisionado)**.
2. Na folha **Notificações do Aplicativo**, escolha **Adicionar** e configure os seguintes valores:
    - **ID do pacote de aplicativos** - insira a **ID do Pacote de Aplicativos** do aplicativo que você deseja configurar. Consulte **Referência da ID de Pacote para aplicativos iOS internos** mais adiante neste tópico para obter ajuda.
    - **Nome do aplicativo** - insira o nome do aplicativo que você deseja configurar. Esse nome não é exibido no dispositivo e é usado para ajudar a identificar o aplicativo na lista.
    - **Editor** - insira o editor que você deseja configurar. O nome do publicador não é exibido no dispositivo e é usado somente para ajudar a identificar o aplicativo na lista.
    - **Notificações** - habilite ou desabilite o envio de notificações para o dispositivo pelo aplicativo. Se você desabilitar essa configuração, as configurações a seguir também serão desabilitadas.
        - **Mostrar no Centro de Notificações** – Habilite essa definição para permitir que o aplicativo mostre as notificações no Centro de Notificações do dispositivo.
        - **Mostrar na Tela de Bloqueio** – Habilite essa definição para ver as notificações do aplicativo na tela de bloqueio do dispositivo.
        - **Tipo de alerta** - selecione o tipo de notificação desejado quando o dispositivo for desbloqueado entre as seguintes opções:
            - **Nenhuma** - nenhuma notificação é exibida.
            - **Faixa** - uma faixa é exibida rapidamente mostrando a notificação.
            - **Modal** - a notificação é exibida e o usuário deve descartá-la manualmente antes de continuar a usar o dispositivo.
        - **Notificação no ícone do aplicativo** – Habilite esta definição para adicionar uma notificação ao ícone do aplicativo a fim de indicar que o aplicativo enviou uma notificação.
        - **Sons** – Habilite esta definição para tocar um som quando uma notificação for entregue.
3. Continue adicionando quantos aplicativos forem necessários. Quando terminar, escolha **OK**.
4. Escolha **OK** em até voltar à folha **Criar Perfil**, depois escolha **Criar**. 


## Referência de ID de Pacote para aplicativos iOS internos
>>>>>>> live
<a id="bundle-id-reference-for-built-in-ios-apps" class="xliff"></a>

<span data-ttu-id="b0ca5-129">Esta lista mostra a ID de pacote de alguns aplicativos iOS internos comuns.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-129">This list shows the bundle ID of some common built-in iOS apps.</span></span> <span data-ttu-id="b0ca5-130">Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-130">To find the bundle ID of other apps, contact your software vendor.</span></span> 

|||
|-|-|
<<<<<<< HEAD
|<span data-ttu-id="b0ca5-131">Nome do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b0ca5-131">App name</span></span>|<span data-ttu-id="b0ca5-132">ID do pacote</span><span class="sxs-lookup"><span data-stu-id="b0ca5-132">BundleID</span></span>|
|<span data-ttu-id="b0ca5-133">Loja de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-133">App Store</span></span>|<span data-ttu-id="b0ca5-134">com.apple.AppStore</span><span class="sxs-lookup"><span data-stu-id="b0ca5-134">com.apple.AppStore</span></span>|
|<span data-ttu-id="b0ca5-135">Calculadora</span><span class="sxs-lookup"><span data-stu-id="b0ca5-135">Calculator</span></span>|<span data-ttu-id="b0ca5-136">com.apple.calculator</span><span class="sxs-lookup"><span data-stu-id="b0ca5-136">com.apple.calculator</span></span>|
|<span data-ttu-id="b0ca5-137">Calendário</span><span class="sxs-lookup"><span data-stu-id="b0ca5-137">Calendar</span></span>|<span data-ttu-id="b0ca5-138">com.apple.mobilecal</span><span class="sxs-lookup"><span data-stu-id="b0ca5-138">com.apple.mobilecal</span></span>|
|<span data-ttu-id="b0ca5-139">Câmera</span><span class="sxs-lookup"><span data-stu-id="b0ca5-139">Camera</span></span>|<span data-ttu-id="b0ca5-140">com.apple.camera</span><span class="sxs-lookup"><span data-stu-id="b0ca5-140">com.apple.camera</span></span>|
|<span data-ttu-id="b0ca5-141">Relógio</span><span class="sxs-lookup"><span data-stu-id="b0ca5-141">Clock</span></span>|<span data-ttu-id="b0ca5-142">com.apple.mobiletimer</span><span class="sxs-lookup"><span data-stu-id="b0ca5-142">com.apple.mobiletimer</span></span>|
|<span data-ttu-id="b0ca5-143">Bússola</span><span class="sxs-lookup"><span data-stu-id="b0ca5-143">Compass</span></span>|<span data-ttu-id="b0ca5-144">com.apple.compass</span><span class="sxs-lookup"><span data-stu-id="b0ca5-144">com.apple.compass</span></span>|
|<span data-ttu-id="b0ca5-145">Contacts</span><span class="sxs-lookup"><span data-stu-id="b0ca5-145">Contacts</span></span>|<span data-ttu-id="b0ca5-146">com.apple.MobileAddressBook</span><span class="sxs-lookup"><span data-stu-id="b0ca5-146">com.apple.MobileAddressBook</span></span>|
|<span data-ttu-id="b0ca5-147">FaceTime</span><span class="sxs-lookup"><span data-stu-id="b0ca5-147">FaceTime</span></span>|<span data-ttu-id="b0ca5-148">com.apple.facetime</span><span class="sxs-lookup"><span data-stu-id="b0ca5-148">com.apple.facetime</span></span>|
|<span data-ttu-id="b0ca5-149">Buscar Amigos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-149">Find Friends</span></span>|<span data-ttu-id="b0ca5-150">com.apple.mobileme.fmf1</span><span class="sxs-lookup"><span data-stu-id="b0ca5-150">com.apple.mobileme.fmf1</span></span>|
|<span data-ttu-id="b0ca5-151">Buscar iPhone</span><span class="sxs-lookup"><span data-stu-id="b0ca5-151">Find iPhone</span></span>|<span data-ttu-id="b0ca5-152">com.apple.mobileme.fmip1</span><span class="sxs-lookup"><span data-stu-id="b0ca5-152">com.apple.mobileme.fmip1</span></span>|
|<span data-ttu-id="b0ca5-153">Game Center</span><span class="sxs-lookup"><span data-stu-id="b0ca5-153">Game Center</span></span>|<span data-ttu-id="b0ca5-154">com.apple.gamecenter</span><span class="sxs-lookup"><span data-stu-id="b0ca5-154">com.apple.gamecenter</span></span>|
|<span data-ttu-id="b0ca5-155">GarageBand</span><span class="sxs-lookup"><span data-stu-id="b0ca5-155">GarageBand</span></span>|<span data-ttu-id="b0ca5-156">com.apple.mobilegarageband</span><span class="sxs-lookup"><span data-stu-id="b0ca5-156">com.apple.mobilegarageband</span></span>|
|<span data-ttu-id="b0ca5-157">Integridade</span><span class="sxs-lookup"><span data-stu-id="b0ca5-157">Health</span></span>|<span data-ttu-id="b0ca5-158">com.apple.Health</span><span class="sxs-lookup"><span data-stu-id="b0ca5-158">com.apple.Health</span></span>|
|<span data-ttu-id="b0ca5-159">iBooks</span><span class="sxs-lookup"><span data-stu-id="b0ca5-159">iBooks</span></span>|<span data-ttu-id="b0ca5-160">com.apple.iBooks</span><span class="sxs-lookup"><span data-stu-id="b0ca5-160">com.apple.iBooks</span></span>|
|<span data-ttu-id="b0ca5-161">iTunes Store</span><span class="sxs-lookup"><span data-stu-id="b0ca5-161">iTunes Store</span></span>|<span data-ttu-id="b0ca5-162">com.apple.MobileStore</span><span class="sxs-lookup"><span data-stu-id="b0ca5-162">com.apple.MobileStore</span></span>|
|<span data-ttu-id="b0ca5-163">iTunes U</span><span class="sxs-lookup"><span data-stu-id="b0ca5-163">iTunes U</span></span>|<span data-ttu-id="b0ca5-164">com.apple.itunesu</span><span class="sxs-lookup"><span data-stu-id="b0ca5-164">com.apple.itunesu</span></span>|
|<span data-ttu-id="b0ca5-165">Keynote</span><span class="sxs-lookup"><span data-stu-id="b0ca5-165">Keynote</span></span>|<span data-ttu-id="b0ca5-166">com.apple.Keynote</span><span class="sxs-lookup"><span data-stu-id="b0ca5-166">com.apple.Keynote</span></span>|
|<span data-ttu-id="b0ca5-167">Email</span><span class="sxs-lookup"><span data-stu-id="b0ca5-167">Mail</span></span>|<span data-ttu-id="b0ca5-168">com.apple.mobilemail</span><span class="sxs-lookup"><span data-stu-id="b0ca5-168">com.apple.mobilemail</span></span>|
|<span data-ttu-id="b0ca5-169">Mapas</span><span class="sxs-lookup"><span data-stu-id="b0ca5-169">Maps</span></span>|<span data-ttu-id="b0ca5-170">com.apple.Maps</span><span class="sxs-lookup"><span data-stu-id="b0ca5-170">com.apple.Maps</span></span>|
|<span data-ttu-id="b0ca5-171">Mensagens</span><span class="sxs-lookup"><span data-stu-id="b0ca5-171">Messages</span></span>|<span data-ttu-id="b0ca5-172">com.apple.MobileSMS</span><span class="sxs-lookup"><span data-stu-id="b0ca5-172">com.apple.MobileSMS</span></span>|
|<span data-ttu-id="b0ca5-173">Música</span><span class="sxs-lookup"><span data-stu-id="b0ca5-173">Music</span></span>|<span data-ttu-id="b0ca5-174">com.apple.Music</span><span class="sxs-lookup"><span data-stu-id="b0ca5-174">com.apple.Music</span></span>|
|<span data-ttu-id="b0ca5-175">News</span><span class="sxs-lookup"><span data-stu-id="b0ca5-175">News</span></span>|<span data-ttu-id="b0ca5-176">com.apple.news</span><span class="sxs-lookup"><span data-stu-id="b0ca5-176">com.apple.news</span></span>|
|<span data-ttu-id="b0ca5-177">Observações</span><span class="sxs-lookup"><span data-stu-id="b0ca5-177">Notes</span></span>|<span data-ttu-id="b0ca5-178">com.apple.mobilenotes</span><span class="sxs-lookup"><span data-stu-id="b0ca5-178">com.apple.mobilenotes</span></span>|
|<span data-ttu-id="b0ca5-179">Números</span><span class="sxs-lookup"><span data-stu-id="b0ca5-179">Numbers</span></span>|<span data-ttu-id="b0ca5-180">com.apple.Numbers</span><span class="sxs-lookup"><span data-stu-id="b0ca5-180">com.apple.Numbers</span></span>|
|<span data-ttu-id="b0ca5-181">Páginas</span><span class="sxs-lookup"><span data-stu-id="b0ca5-181">Pages</span></span>|<span data-ttu-id="b0ca5-182">com.apple.Pages</span><span class="sxs-lookup"><span data-stu-id="b0ca5-182">com.apple.Pages</span></span>|
|<span data-ttu-id="b0ca5-183">Photo Booth</span><span class="sxs-lookup"><span data-stu-id="b0ca5-183">Photo Booth</span></span>|<span data-ttu-id="b0ca5-184">com.apple.Photo-Booth</span><span class="sxs-lookup"><span data-stu-id="b0ca5-184">com.apple.Photo-Booth</span></span>|
|<span data-ttu-id="b0ca5-185">Fotos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-185">Photos</span></span>|<span data-ttu-id="b0ca5-186">com.apple.mobileslideshow</span><span class="sxs-lookup"><span data-stu-id="b0ca5-186">com.apple.mobileslideshow</span></span>|
|<span data-ttu-id="b0ca5-187">Podcasts</span><span class="sxs-lookup"><span data-stu-id="b0ca5-187">Podcasts</span></span>|<span data-ttu-id="b0ca5-188">com.apple.podcasts</span><span class="sxs-lookup"><span data-stu-id="b0ca5-188">com.apple.podcasts</span></span>|
|<span data-ttu-id="b0ca5-189">Lembretes</span><span class="sxs-lookup"><span data-stu-id="b0ca5-189">Reminders</span></span>|<span data-ttu-id="b0ca5-190">com.apple.reminders</span><span class="sxs-lookup"><span data-stu-id="b0ca5-190">com.apple.reminders</span></span>|
|<span data-ttu-id="b0ca5-191">Safari</span><span class="sxs-lookup"><span data-stu-id="b0ca5-191">Safari</span></span>|<span data-ttu-id="b0ca5-192">com.apple.mobilesafari</span><span class="sxs-lookup"><span data-stu-id="b0ca5-192">com.apple.mobilesafari</span></span>|
|<span data-ttu-id="b0ca5-193">Configurações</span><span class="sxs-lookup"><span data-stu-id="b0ca5-193">Settings</span></span>|<span data-ttu-id="b0ca5-194">com.apple.Preferences</span><span class="sxs-lookup"><span data-stu-id="b0ca5-194">com.apple.Preferences</span></span>|
|<span data-ttu-id="b0ca5-195">Bolsa</span><span class="sxs-lookup"><span data-stu-id="b0ca5-195">Stocks</span></span>|<span data-ttu-id="b0ca5-196">com.apple.stocks</span><span class="sxs-lookup"><span data-stu-id="b0ca5-196">com.apple.stocks</span></span>|
|<span data-ttu-id="b0ca5-197">Dicas</span><span class="sxs-lookup"><span data-stu-id="b0ca5-197">Tips</span></span>|<span data-ttu-id="b0ca5-198">com.apple.tips</span><span class="sxs-lookup"><span data-stu-id="b0ca5-198">com.apple.tips</span></span>|
|<span data-ttu-id="b0ca5-199">Vídeos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-199">Videos</span></span>|<span data-ttu-id="b0ca5-200">com.apple.videos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-200">com.apple.videos</span></span>|
|<span data-ttu-id="b0ca5-201">VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-201">VoiceMemos</span></span>|<span data-ttu-id="b0ca5-202">com.apple.VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="b0ca5-202">com.apple.VoiceMemos</span></span>|
|<span data-ttu-id="b0ca5-203">Carteira</span><span class="sxs-lookup"><span data-stu-id="b0ca5-203">Wallet</span></span>|<span data-ttu-id="b0ca5-204">com.apple.Passbook</span><span class="sxs-lookup"><span data-stu-id="b0ca5-204">com.apple.Passbook</span></span>|
|<span data-ttu-id="b0ca5-205">Assistir</span><span class="sxs-lookup"><span data-stu-id="b0ca5-205">Watch</span></span>|<span data-ttu-id="b0ca5-206">com.apple.Bridge</span><span class="sxs-lookup"><span data-stu-id="b0ca5-206">com.apple.Bridge</span></span>|
|<span data-ttu-id="b0ca5-207">Clima</span><span class="sxs-lookup"><span data-stu-id="b0ca5-207">Weather</span></span>|<span data-ttu-id="b0ca5-208">com.apple.weather</span><span class="sxs-lookup"><span data-stu-id="b0ca5-208">com.apple.weather</span></span>|

## <span data-ttu-id="b0ca5-209">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b0ca5-209">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="b0ca5-210">Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos.</span><span class="sxs-lookup"><span data-stu-id="b0ca5-210">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="b0ca5-211">Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="b0ca5-211">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
=======
|Nome do aplicativo|ID do pacote|
|Loja de aplicativos|com.apple.AppStore|
|Calculadora|com.apple.calculator|
|Calendário|com.apple.mobilecal|
|Câmera|com.apple.camera|
|Relógio|com.apple.mobiletimer|
|Bússola|com.apple.compass|
|Contacts|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Buscar Amigos|com.apple.mobileme.fmf1|
|Buscar iPhone|com.apple.mobileme.fmip1|
|Game Center|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Integridade|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Email|com.apple.mobilemail|
|Mapas|com.apple.Maps|
|Mensagens|com.apple.MobileSMS|
|Música|com.apple.Music|
|News|com.apple.news|
|Observações|com.apple.mobilenotes|
|Números|com.apple.Numbers|
|Páginas|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotos|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Lembretes|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Configurações|com.apple.Preferences|
|Bolsa|com.apple.stocks|
|Dicas|com.apple.tips|
|Vídeos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Carteira|com.apple.Passbook|
|Assistir|com.apple.Bridge|
|Clima|com.apple.weather|

## Próximas etapas
<a id="next-steps" class="xliff"></a>

Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos. Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
>>>>>>> live
