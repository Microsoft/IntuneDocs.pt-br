---
title: "Introdução ao SDK de Aplicativos do Microsoft Intune"
description: "Habilite rapidamente seu aplicativo móvel para MAM (gerenciamento de aplicativo móvel) com o Microsoft Intune."
keywords: 
author: mtillman
manager: angrobe
ms.author: oydang
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38ebd3f5-cfcc-4204-8a75-6e2f162cd7c1
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d61432eafef67ca997d4e03d305e1c068ac5fd6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="fe3af-103">Introdução ao SDK de Aplicativos do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fe3af-103">Get started with the Microsoft Intune App SDK</span></span>
<a id="get-started-with-the-microsoft-intune-app-sdk" class="xliff"></a>

<span data-ttu-id="fe3af-104">Este guia ajudará você a habilitar rapidamente seu aplicativo móvel para políticas de proteção do aplicativo com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-104">This guide will help you quickly enable your mobile app for app protection policies with Microsoft Intune.</span></span> <span data-ttu-id="fe3af-105">Pode ser útil compreender primeiro os benefícios do SDK de Aplicativo do Intune enumerados na [Visão geral do SDK de Aplicativos do Intune](app-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="fe3af-105">You may find it useful to first understand the benefits of the Intune App SDK, as explained in the [Intune App SDK overview](app-sdk.md).</span></span>

<span data-ttu-id="fe3af-106">O SDK do Aplicativo do Intune dá suporte a cenários semelhantes no iOS e Android e destina-se a criar uma experiência consistente em todas as plataformas para os administradores de TI.</span><span class="sxs-lookup"><span data-stu-id="fe3af-106">The Intune App SDK supports similar scenarios across iOS and Android, and is intended to create a consistent experience across the platforms for IT admins.</span></span> <span data-ttu-id="fe3af-107">Porém, há pequenas diferenças no suporte a determinados recursos devido a limitações da plataforma.</span><span class="sxs-lookup"><span data-stu-id="fe3af-107">But there are small differences in the support of certain features, because of platform limitations.</span></span>

## <span data-ttu-id="fe3af-108">Registrar seu aplicativo de uma loja de aplicativos no Microsoft</span><span class="sxs-lookup"><span data-stu-id="fe3af-108">Register your store app with Microsoft</span></span>
<a id="register-your-store-app-with-microsoft" class="xliff"></a>

### <span data-ttu-id="fe3af-109">Caso o aplicativo seja interno à sua organização e não esteja disponível publicamente:</span><span class="sxs-lookup"><span data-stu-id="fe3af-109">If your app is internal to your organization and will not be publicly available:</span></span>
<a id="if-your-app-is-internal-to-your-organization-and-will-not-be-publicly-available" class="xliff"></a>

<span data-ttu-id="fe3af-110">Você *não precisa* registrar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fe3af-110">You *do not need* to register your app.</span></span> <span data-ttu-id="fe3af-111">Para aplicativos de linha de negócios internos, o administrador de TI implantará o aplicativo internamente.</span><span class="sxs-lookup"><span data-stu-id="fe3af-111">For internal line-of-business apps, the IT administrator will deploy the app internally.</span></span> <span data-ttu-id="fe3af-112">O Intune detectará que o aplicativo foi criado com o SDK e permitirá que o administrador de TI aplique a política de proteção do aplicativo a ele.</span><span class="sxs-lookup"><span data-stu-id="fe3af-112">Intune will detect that the app has been built with the SDK, and will let the IT administrator apply app protection policy to it.</span></span> <span data-ttu-id="fe3af-113">É possível ignorar a seção [Habilitar o aplicativo iOS ou Android para a política de proteção do aplicativo](#enable-your-iOS-or-Android-app-for-app-protection-policy).</span><span class="sxs-lookup"><span data-stu-id="fe3af-113">You can skip to the section [Enable your iOS or Android app for app protection policy](#enable-your-iOS-or-Android-app-for-app-protection-policy).</span></span>

### <span data-ttu-id="fe3af-114">Se o aplicativo for liberado para uma loja pública de aplicativos, como a Apple App Store ou o Google Play:</span><span class="sxs-lookup"><span data-stu-id="fe3af-114">If your app will be released to a public app store, like the Apple App Store or Google Play:</span></span>
<a id="if-your-app-will-be-released-to-a-public-app-store-like-the-apple-app-store-or-google-play" class="xliff"></a>

<span data-ttu-id="fe3af-115">Primeiro, você _**deve**_ registrar o aplicativo no Microsoft Intune e concordar com os termos de registro.</span><span class="sxs-lookup"><span data-stu-id="fe3af-115">You _**must**_ first register your app with Microsoft Intune and agree to the registration terms.</span></span> <span data-ttu-id="fe3af-116">Em seguida, os administradores de TI poderão aplicar a política de proteção do aplicativo ao aplicativo habilitado, que será listado como um parceiro de aplicativos do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-116">IT administrators can then apply app protection policy to the enlightened app, which will be listed as an Intune app partner.</span></span>

<span data-ttu-id="fe3af-117">Somente depois que o registro for concluído e confirmado pela equipe do Microsoft Intune os administradores do Intune terão a opção de aplicar a política de proteção do aplicativo ao link profundo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fe3af-117">Until registration has been finished and confirmed by the Microsoft Intune team, Intune administrators will not have the option to apply app protection policy to your app's deep link.</span></span> <span data-ttu-id="fe3af-118">A Microsoft também adicionará seu aplicativo à [página Parceiros do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span><span class="sxs-lookup"><span data-stu-id="fe3af-118">Microsoft will also add your app to its [Microsoft Intune Partners page](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span></span> <span data-ttu-id="fe3af-119">Nessa página, o ícone do aplicativo será exibido para mostrar que ele dá suporte às políticas de proteção do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-119">There, the app's icon will be displayed to show that it supports Intune app protection policies.</span></span>

<span data-ttu-id="fe3af-120">Para iniciar o processo de registro, preencha o [Questionário de Parceiro de Aplicativo do Microsoft Intune](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).</span><span class="sxs-lookup"><span data-stu-id="fe3af-120">To begin the registration process, fill out the [Microsoft Intune App Partner Questionnaire](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR6oOVGFZ3pxJmwSN1N_eXwJUQUc5Mkw2UVU0VzI5WkhQOEYyMENWNDBWRS4u).</span></span>

<span data-ttu-id="fe3af-121">Usaremos os endereços de email listados em suas respostas ao questionário para contatá-lo e continuar o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="fe3af-121">We will use the email addresses listed in your questionnaire response to reach out and continue the registration process.</span></span> <span data-ttu-id="fe3af-122">Além disso, usamos o seu endereço de email de registro para entrar em contato com você caso tenhamos quaisquer dúvidas.</span><span class="sxs-lookup"><span data-stu-id="fe3af-122">Additionally, we use your registration email address to contact you if we have any concerns.</span></span>

> [!NOTE]
> <span data-ttu-id="fe3af-123">Todas as informações coletadas no questionários e por email com a equipe do Microsoft Intune serão tratadas de acordo com a [Política de Privacidade da Microsoft](https://www.microsoft.com/privacystatement/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="fe3af-123">All information collected in the questionnaire and through email correspondence with the Microsoft Intune team will honor the [Microsoft Privacy Statement](https://www.microsoft.com/privacystatement/default.aspx).</span></span>

<span data-ttu-id="fe3af-124">**O que esperar no processo de registro**:</span><span class="sxs-lookup"><span data-stu-id="fe3af-124">**What to expect in the registration process**:</span></span>

1. <span data-ttu-id="fe3af-125">Após enviar o questionário, nós contataremos você pelo endereço de email registrado para confirmar o recebimento ou para solicitar informações adicionais para concluir o registro.</span><span class="sxs-lookup"><span data-stu-id="fe3af-125">After you have submitted the questionnaire, we will contact you via your registration email address, to either confirm successful receipt or request additional information to finish the registration.</span></span>

2. <span data-ttu-id="fe3af-126">Após recebermos de você todas as informações necessárias, enviaremos o Contrato de Parceiro do Aplicativo do Microsoft Intune para você assinar.</span><span class="sxs-lookup"><span data-stu-id="fe3af-126">After we receive all necessary information from you, we will send you the Microsoft Intune App Partner Agreement to sign.</span></span> <span data-ttu-id="fe3af-127">Este contrato descreve os termos que sua empresa deve aceitar antes de se tornar um parceiro de aplicativo do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-127">This agreement describes the terms that your company must accept before it becomes a Microsoft Intune app partner.</span></span>

3. <span data-ttu-id="fe3af-128">Você também será notificado quando seu aplicativo for registrado com êxito no serviço do Microsoft Intune e quando ele estiver em destaque no site de [parceiros do Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span><span class="sxs-lookup"><span data-stu-id="fe3af-128">You will be notified when your app is successfully registered with the Microsoft Intune service and when your app is featured on the [Microsoft Intune partners](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) site.</span></span>

4. <span data-ttu-id="fe3af-129">Por fim, o link profundo de seu aplicativo será adicionado à próxima atualização mensal do Serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-129">Finally, your app's deep link will be added to the next monthly Intune Service update.</span></span> <span data-ttu-id="fe3af-130">Por exemplo, se as informações o registro forem concluídas em julho, o link profundo terá suporte em meados de agosto.</span><span class="sxs-lookup"><span data-stu-id="fe3af-130">For example, if the registration information is finished in July, the deep link will be supported in mid-August.</span></span>

<span data-ttu-id="fe3af-131">Se o link profundo do aplicativo for alterado no futuro, você precisará registrar novamente o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fe3af-131">If your app's deep link changes in the future, you will need to re-register your app.</span></span>

> [!NOTE]
> <span data-ttu-id="fe3af-132">Além disso, informe se você atualizou o aplicativo com uma nova versão do SDK do Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-132">Please inform us if you update your app with a new version of the Intune App SDK.</span></span>



## <span data-ttu-id="fe3af-133">Baixar os arquivos do SDK</span><span class="sxs-lookup"><span data-stu-id="fe3af-133">Download the SDK files</span></span>
<a id="download-the-sdk-files" class="xliff"></a>

<span data-ttu-id="fe3af-134">Os SDKs do Aplicativo do Intune para iOS e Android nativo são hospedados em uma conta do GitHub da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe3af-134">The Intune App SDKs for native iOS and Android are hosted on a Microsoft GitHub account.</span></span> <span data-ttu-id="fe3af-135">Esses repositórios públicos têm os arquivos do SDK para o iOS e Android nativo, respectivamente:</span><span class="sxs-lookup"><span data-stu-id="fe3af-135">These public repositories have the SDK files for native iOS and Android, respectively:</span></span>

* [<span data-ttu-id="fe3af-136">SDK de Aplicativo do Intune para iOS</span><span class="sxs-lookup"><span data-stu-id="fe3af-136">Intune App SDK for iOS</span></span>](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios)
* [<span data-ttu-id="fe3af-137">SDK de Aplicativo do Intune para Android</span><span class="sxs-lookup"><span data-stu-id="fe3af-137">Intune App SDK for Android</span></span>](https://github.com/msintuneappsdk/ms-intune-app-sdk-android)

<span data-ttu-id="fe3af-138">Caso o aplicativo seja um aplicativo Xamarin ou Cordova, use essas variantes do SDK:</span><span class="sxs-lookup"><span data-stu-id="fe3af-138">If your app is a Xamarin or Cordova app, please use these SDK variants:</span></span>

* [<span data-ttu-id="fe3af-139">Componente Xamarin do SDK de Aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="fe3af-139">Intune App SDK Xamarin Component</span></span>](https://github.com/msintuneappsdk/intune-app-sdk-xamarin)
* [<span data-ttu-id="fe3af-140">Plug-in Cordova do SDK de Aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="fe3af-140">Intune App SDK Cordova Plugin</span></span>](https://github.com/msintuneappsdk/cordova-plugin-ms-intune-mam)

<span data-ttu-id="fe3af-141">Convém criar uma conta do GitHub que você possa usar para bifurcar e efetuar pull de nosso repositórios.</span><span class="sxs-lookup"><span data-stu-id="fe3af-141">It's a good idea to sign up for a GitHub account that you can use to fork and pull from our repositories.</span></span> <span data-ttu-id="fe3af-142">O GitHub permite que os desenvolvedores se comuniquem com nossa equipe de produto, abram questões e recebam respostas rápidas, exibam notas de versão e forneçam comentários à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe3af-142">GitHub lets developers communicate with our product team, open issues and receive quick responses, view release notes, and provide feedback to Microsoft.</span></span> <span data-ttu-id="fe3af-143">Em caso de dúvidas sobre o GitHub do SDK do Aplicativo do Intune, contate msintuneappsdk@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="fe3af-143">For questions on the Intune App SDK GitHub, contact msintuneappsdk@microsoft.com.</span></span>





## <span data-ttu-id="fe3af-144">Habilitar o aplicativo iOS ou Android para a política de proteção do aplicativo</span><span class="sxs-lookup"><span data-stu-id="fe3af-144">Enable your iOS or Android app for app protection policy</span></span>
<a id="enable-your-ios-or-android-app-for-app-protection-policy" class="xliff"></a>

<span data-ttu-id="fe3af-145">Você precisará de um dos seguintes guias do desenvolvedor para ajudá-lo a integrar o SDK do Aplicativo do Intune em seu aplicativo:</span><span class="sxs-lookup"><span data-stu-id="fe3af-145">You will need one of the following developer guides to help you integrate the Intune App SDK into your app:</span></span>

* <span data-ttu-id="fe3af-146">**[Guia do Desenvolvedor do SDK do Aplicativo do Intune para iOS](app-sdk-ios.md)**: esse documento fornece um passo a passo para a habilitação do aplicativo iOS nativo com o SDK do Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-146">**[Intune App SDK for iOS Developer Guide](app-sdk-ios.md)**: This document will walk you step-by-step through enabling your native iOS app with the Intune App SDK.</span></span>

* <span data-ttu-id="fe3af-147">**[Guia do Desenvolvedor do SDK do Aplicativo do Intune para Android](app-sdk-android.md)**: esse documento fornece um passo a passo para a habilitação do aplicativo Android nativo com o SDK do Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-147">**[Intune App SDK for Android Developer Guide](app-sdk-android.md)**: This document will walk you step-by-step through enabling your native Android app with the Intune App SDK.</span></span>

* <span data-ttu-id="fe3af-148">**[Guia do plug-in Cordova do SDK de Aplicativo do Intune](app-sdk-cordova.md)**: esse documento ajudará você a criar aplicativos iOS e Android usando o Cordova para as políticas de proteção do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-148">**[Intune App SDK Cordova Plugin guide](app-sdk-cordova.md)**: This document will help you build iOS and Android apps using Cordova for Intune app protection policies.</span></span>

* <span data-ttu-id="fe3af-149">**[Guia do Componente Xamarin do SDK do Aplicativo do Intune](app-sdk-xamarin.md)**: esse documento ajudará você a criar aplicativos iOS e Android usando o Cordova para as políticas de proteção do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-149">**[Intune App SDK Xamarin Component guide](app-sdk-xamarin.md)**: This document will help you build iOS and Android apps using Cordova for Intune app protection policies.</span></span>




## <span data-ttu-id="fe3af-150">Configurando a Telemetria para seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="fe3af-150">Configure Telemetry for your app</span></span>
<a id="configure-telemetry-for-your-app" class="xliff"></a>

<span data-ttu-id="fe3af-151">O Microsoft Intune coleta dados sobre estatísticas de uso para seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fe3af-151">Microsoft Intune collects data on usage statistics for your app.</span></span>

* <span data-ttu-id="fe3af-152">**SDK de Aplicativo Intune para iOS**: o SDK registra dados de telemetria do SDK sobre eventos de uso por padrão.</span><span class="sxs-lookup"><span data-stu-id="fe3af-152">**Intune App SDK for iOS**: The SDK logs SDK telemetry data on usage events by default.</span></span> <span data-ttu-id="fe3af-153">Esses dados são enviados para o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-153">This data is sent to Microsoft Intune.</span></span>

    * <span data-ttu-id="fe3af-154">Se optar por não enviar dados de telemetria do SDK para o Microsoft Intune do seu aplicativo, você deverá desabilitar a transmissão de telemetria definindo a propriedade `MAMTelemetryDisabled` como ”YES” no dicionário IntuneMAMSettings.</span><span class="sxs-lookup"><span data-stu-id="fe3af-154">If you choose not to send SDK telemetry data to Microsoft Intune from your app, you must disable telemetry transmission by setting the property `MAMTelemetryDisabled` to "YES" in the IntuneMAMSettings dictionary.</span></span>


* <span data-ttu-id="fe3af-155">**SDK do Aplicativo do Intune para Android**: os dados de telemetria não são registrados por meio do SDK.</span><span class="sxs-lookup"><span data-stu-id="fe3af-155">**Intune App SDK for Android**: Telemetry data is not logged through the SDK.</span></span>

## <span data-ttu-id="fe3af-156">Próximas etapas após integração</span><span class="sxs-lookup"><span data-stu-id="fe3af-156">Next steps after integration</span></span>
<a id="next-steps-after-integration" class="xliff"></a>

### <span data-ttu-id="fe3af-157">Teste seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="fe3af-157">Test your app</span></span>
<a id="test-your-app" class="xliff"></a>
<span data-ttu-id="fe3af-158">Depois de concluir as etapas necessárias para integrar seu aplicativo iOS ou Android com o SDK do Aplicativo do Intune, você precisará garantir que todas as políticas de proteção do aplicativo estão habilitadas e funcionando para o usuário e o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="fe3af-158">After you finish the necessary steps to integrate your iOS or Android app with the Intune App SDK, you will need to ensure that all the app protection policies are enabled and functioning for the user and the IT admin.</span></span> <span data-ttu-id="fe3af-159">Para testar seu aplicativo integrado, você precisará do seguinte:</span><span class="sxs-lookup"><span data-stu-id="fe3af-159">To test your integrated app, you will need the following:</span></span>

* <span data-ttu-id="fe3af-160">**Conta de teste do Microsoft Intune**: para testar seu aplicativo habilitado pelo Intune nos recursos de proteção do aplicativo do Intune, você precisará de uma conta do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-160">**Microsoft Intune test account**: To test your Intune-enlightened app against Intune app protection features, you will need a Microsoft Intune account.</span></span>

    * <span data-ttu-id="fe3af-161">Se você for um ISV que habilita aplicativos da loja do iOS ou do Android para a política de proteção do aplicativo do Intune, receberá um código promocional após a conclusão do registro no Microsoft Intune, conforme descrito na etapa de registro.</span><span class="sxs-lookup"><span data-stu-id="fe3af-161">If you are an ISV enabling your iOS or Android store apps for Intune app protection policy, you will receive a promo code after you finish the registration with Microsoft Intune, as outlined in the registration step.</span></span> <span data-ttu-id="fe3af-162">O código de promoção permitirá que você se inscreva para uma avaliação de um ano de uso estendido do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-162">The promo code will let you sign up for a Microsoft Intune trial for one year of extended use.</span></span>

    * <span data-ttu-id="fe3af-163">Se estiver desenvolvendo um aplicativo de linha de negócios que não será enviado para a loja, você deverá ter acesso ao Microsoft Intune por meio de sua organização.</span><span class="sxs-lookup"><span data-stu-id="fe3af-163">If you are developing a line-of-business app that will not be shipped to the store, you are expected to have access to Microsoft Intune through your organization.</span></span> <span data-ttu-id="fe3af-164">Você também pode se inscrever para uma avaliação gratuita de uma mês no [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).</span><span class="sxs-lookup"><span data-stu-id="fe3af-164">You can also sign up for a one-month free trial in [Microsoft Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0).</span></span>

* <span data-ttu-id="fe3af-165">**Políticas de proteção do aplicativo do Intune**: para testar seu aplicativo em todas as políticas de proteção do aplicativo do Intune, é necessário saber qual é o comportamento esperado para cada configuração da política.</span><span class="sxs-lookup"><span data-stu-id="fe3af-165">**Intune app protection policies**: To test your app against all the Intune app protection policies, you should know what the expected behavior is for each policy setting.</span></span> <span data-ttu-id="fe3af-166">Consulte as descrições de [políticas de proteção do aplicativo do iOS](/intune-classic/deploy-use/ios-mam-policy-settings) e [políticas de proteção do aplicativo do Android](/intune-classic/deploy-use/android-mam-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="fe3af-166">See the descriptions for [iOS app protection policies](/intune-classic/deploy-use/ios-mam-policy-settings) and [Android app protection policies](/intune-classic/deploy-use/android-mam-policy-settings).</span></span>

* <span data-ttu-id="fe3af-167">**Solução de problemas**: em caso de problemas durante o teste manual da experiência do usuário de seu aplicativo, confira [Solucionar problemas do gerenciamento de aplicativo móvel](/intune-classic/troubleshoot/troubleshoot-mam).</span><span class="sxs-lookup"><span data-stu-id="fe3af-167">**Troubleshoot**: If you run into any issues while manually testing your app's user experience, check out the [Troubleshooting MAM](/intune-classic/troubleshoot/troubleshoot-mam).</span></span> <span data-ttu-id="fe3af-168">Este artigo oferece ajuda para problemas comuns, caixas de diálogo e mensagens de erro que podem ocorrer em aplicativos habilitados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-168">This article offers help for common issues, dialogs, and error messages that may be experienced in Intune-enlightened apps.</span></span> 

### <span data-ttu-id="fe3af-169">Marcar com uma notificação no aplicativo (opcional)</span><span class="sxs-lookup"><span data-stu-id="fe3af-169">Badge your app (optional)</span></span>
<a id="badge-your-app-optional" class="xliff"></a>

<span data-ttu-id="fe3af-170">Depois de validar que as políticas de proteção do aplicativo do Intune funcionam no aplicativo, é possível marcar o ícone do aplicativo com uma notificação do logotipo de proteção do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-170">After validating that Intune app protection policies work in your app, you can badge your app icon with the Intune app protection logo.</span></span>

<span data-ttu-id="fe3af-171">Essa notificação indica aos administradores de TI, usuários finais e clientes potenciais do Intune que seu aplicativo funciona com as políticas de proteção do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-171">This badge indicates to IT administrators, end-users, and potential Intune customers that your app works with Intune app protection policies.</span></span> <span data-ttu-id="fe3af-172">Ela incentiva o uso e a adoção de seu aplicativo pelos clientes do Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-172">It encourages the usage and adoption of your app by Intune customers.</span></span>

<span data-ttu-id="fe3af-173">A notificação é um ícone de porta-arquivos e pode ser vista nos exemplos abaixo:</span><span class="sxs-lookup"><span data-stu-id="fe3af-173">The badge is a briefcase icon and can be seen in the samples below:</span></span>

![Exemplo de notificação 1](./media/badge-example-1.png) ![Exemplo de notificação 2](./media/badge-example-2.png)

<span data-ttu-id="fe3af-176">**O que será necessário para marcar o aplicativo com uma notificação**:</span><span class="sxs-lookup"><span data-stu-id="fe3af-176">**What you'll need to badge your app**:</span></span>

* <span data-ttu-id="fe3af-177">Um aplicativo de manipulação de imagem que pode ler arquivos **.eps** ou um aplicativo Adobe que pode ler arquivos **.ai**.</span><span class="sxs-lookup"><span data-stu-id="fe3af-177">An image manipulation application that can read **.eps** files, or an Adobe application that can read **.ai** files.</span></span>

* <span data-ttu-id="fe3af-178">Encontre os [ativos de notificação de aplicativo do Intune e as diretrizes](https://github.com/msintuneappsdk/intune-app-partner-badge) no GitHub do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="fe3af-178">You can find the [Intune app badge assets and guidelines](https://github.com/msintuneappsdk/intune-app-partner-badge) on the Microsoft Intune GitHub.</span></span>
