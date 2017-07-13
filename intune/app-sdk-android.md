---
title: Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android
description: "O SDK de Aplicativo do Microsoft Intune para Android permite incorporar o MAM (gerenciamento de aplicativo móvel) do Intune em seu aplicativo Android."
keywords: SDK
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 403917adb1fb1156f0ed0027a316677d1e4f2f84
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="749d4-104">Guia do SDK de Aplicativo do Microsoft Intune para desenvolvedores do Android</span><span class="sxs-lookup"><span data-stu-id="749d4-104">Microsoft Intune App SDK for Android developer guide</span></span>
<a id="microsoft-intune-app-sdk-for-android-developer-guide" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="749d4-105">Leia primeiro a [Visão geral do SDK de Aplicativo do Intune](app-sdk.md), que explica os recursos atuais do SDK e descreve como preparar a integração em cada plataforma com suporte.</span><span class="sxs-lookup"><span data-stu-id="749d4-105">You might want to first read the [Intune App SDK overview](app-sdk.md), which covers the current features of the SDK and describes how to prepare for integration on each supported platform.</span></span>

<span data-ttu-id="749d4-106">O SDK do Aplicativo do Microsoft Intune para Android permite incorporar políticas de proteção do aplicativo do Intune (também conhecidas como políticas **APP** ou MAM) em seu aplicativo Android nativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-106">The Microsoft Intune App SDK for Android lets you incorporate Intune app protection policies (also known as **APP** or MAM policies) into your native Android app.</span></span> <span data-ttu-id="749d4-107">Um aplicativo orientado para Intune é aquele que está integrado ao SDK de Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-107">An Intune-enlightened application is one that is integrated with the Intune App SDK.</span></span> <span data-ttu-id="749d4-108">Os administradores do Intune podem facilmente implantar políticas de proteção do aplicativo em seu aplicativo orientado para Intune quando o Intune gerencia o aplicativo de forma ativa.</span><span class="sxs-lookup"><span data-stu-id="749d4-108">Intune administrators can easily deploy app protection policies to your Intune-enlightened app when Intune actively manages the app.</span></span>


## <span data-ttu-id="749d4-109">O que está contido no SDK</span><span class="sxs-lookup"><span data-stu-id="749d4-109">What's in the SDK</span></span>
<a id="whats-in-the-sdk" class="xliff"></a>

<span data-ttu-id="749d4-110">O SDK do aplicativo do Intune é composto pelos seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="749d4-110">The Intune App SDK consists of the following files:</span></span>  

* <span data-ttu-id="749d4-111">**Microsoft.Intune.MAM.SDK.aar**: os componentes do SDK, com exceção dos arquivos JAR Support.V4 e Support.V7.</span><span class="sxs-lookup"><span data-stu-id="749d4-111">**Microsoft.Intune.MAM.SDK.aar**: The SDK components, with the exception of the Support.V4 and Support.V7 JAR files.</span></span> <span data-ttu-id="749d4-112">Esse arquivo pode ser usado no lugar de componentes individuais se sua compilação do sistema der suporte a arquivos AAR.</span><span class="sxs-lookup"><span data-stu-id="749d4-112">This file can be used in place of the individual components if your build system supports AAR files.</span></span>
* <span data-ttu-id="749d4-113">**Microsoft.Intune.MAM.SDK.Support.v4.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v4.</span><span class="sxs-lookup"><span data-stu-id="749d4-113">**Microsoft.Intune.MAM.SDK.Support.v4.jar**: The interfaces necessary to enable MAM in apps that use the Android v4 support library.</span></span> <span data-ttu-id="749d4-114">Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo JAR.</span><span class="sxs-lookup"><span data-stu-id="749d4-114">Apps that need this support must reference the JAR file directly.</span></span>
* <span data-ttu-id="749d4-115">**Microsoft.Intune.MAM.SDK.Support.v7.jar**: as interfaces necessárias para habilitar o MAM em aplicativos que utilizam a biblioteca de suporte do Android v7.</span><span class="sxs-lookup"><span data-stu-id="749d4-115">**Microsoft.Intune.MAM.SDK.Support.v7.jar**: The interfaces necessary to enable MAM in apps that use the Android v7 support library.</span></span> <span data-ttu-id="749d4-116">Os aplicativos que precisam desse suporte devem referenciar diretamente o arquivo JAR.</span><span class="sxs-lookup"><span data-stu-id="749d4-116">Apps that need this support must reference the JAR file directly.</span></span>
* <span data-ttu-id="749d4-117">**proguard.txt**: contém regras do ProGuard que devem ser aplicadas se estiver desenvolvendo com o ProGuard.</span><span class="sxs-lookup"><span data-stu-id="749d4-117">**proguard.txt**: Contains ProGuard rules which must be applied if building with ProGuard.</span></span>
* <span data-ttu-id="749d4-118">**CHANGELOG.txt**: fornece um registro das alterações feitas em cada versão do SDK.</span><span class="sxs-lookup"><span data-stu-id="749d4-118">**CHANGELOG.txt**: Provides a record of changes made in each SDK version.</span></span>
* <span data-ttu-id="749d4-119">**THIRDPARTYNOTICES.TXT**: um aviso de atribuição que reconhece códigos de terceiros e/ou de OSS que serão compilados em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-119">**THIRDPARTYNOTICES.TXT**:  An attribution notice that acknowledges third-party and/or OSS code that will be compiled into your app.</span></span>

<span data-ttu-id="749d4-120">Se o sistema de compilação não der suporte a arquivos AAR, você poderá usar os seguintes arquivos em vez de Microsoft.Intune.MAM.SDK.aar.</span><span class="sxs-lookup"><span data-stu-id="749d4-120">If your build system does not support AAR files, you may use the following files in place of Microsoft.Intune.MAM.SDK.aar.</span></span>
* <span data-ttu-id="749d4-121">**Microsoft.Intune.MAM.SDK.jar**: as interfaces necessárias para habilitar o MAM e a interoperabilidade com o aplicativo de Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-121">**Microsoft.Intune.MAM.SDK.jar**: The interfaces necessary to enable MAM and interoperability with the Intune Company Portal app.</span></span> <span data-ttu-id="749d4-122">Os aplicativos devem especificá-lo como uma referência de biblioteca Android.</span><span class="sxs-lookup"><span data-stu-id="749d4-122">Apps must specify it as an Android library reference.</span></span>
* <span data-ttu-id="749d4-123">**O diretório de recursos**: os recursos (como cadeias de caracteres) dos quais o SDK depende.</span><span class="sxs-lookup"><span data-stu-id="749d4-123">**The res directory**: The resources (like strings) on which the SDK relies.</span></span>
* <span data-ttu-id="749d4-124">**AndroidManifest.xml**: os pontos de entrada e os requisitos da biblioteca.</span><span class="sxs-lookup"><span data-stu-id="749d4-124">**AndroidManifest.xml**: Entry points and the library requirements.</span></span>


## <span data-ttu-id="749d4-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="749d4-125">Requirements</span></span>
<a id="requirements" class="xliff"></a>

<span data-ttu-id="749d4-126">O SDK de Aplicativos do Intune é um projeto Android compilado.</span><span class="sxs-lookup"><span data-stu-id="749d4-126">The Intune App SDK is a compiled Android project.</span></span> <span data-ttu-id="749d4-127">Como resultado, ele não é afetado pela versão do Android que o aplicativo usa para suas versões de API mínima ou de destino.</span><span class="sxs-lookup"><span data-stu-id="749d4-127">As a result, it is largely unaffected by the version of Android that the app uses for its minimum or target API versions.</span></span> <span data-ttu-id="749d4-128">O SDK dá suporte à API 14 do Android (Android 4.0 +) por meio da API 25 do Android (Android 7.1).</span><span class="sxs-lookup"><span data-stu-id="749d4-128">The SDK supports Android API 14 (Android 4.0+) through Android API 25 (Android 7.1).</span></span>



### <span data-ttu-id="749d4-129">Aplicativo do Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="749d4-129">Company Portal app</span></span>
<a id="company-portal-app" class="xliff"></a>
<span data-ttu-id="749d4-130">O SDK de Aplicativo do Intune para Android depende da presença do aplicativo do [Portal da Empresa](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) no dispositivo para habilitar as políticas de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-130">The Intune App SDK for Android relies on the presence of the [Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) app on the device to enable app protection policies.</span></span> <span data-ttu-id="749d4-131">O Portal da Empresa recupera as políticas de proteção de aplicativo do serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-131">The Company Portal retrieves app protection policies from the Intune service.</span></span> <span data-ttu-id="749d4-132">Quando o aplicativo é inicializado, ele carrega a política e o código para impor essa política do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="749d4-132">When the app initializes, it loads policy and code to enforce that policy from the Company Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="749d4-133">Quando o aplicativo do Portal da Empresa não está no dispositivo, um aplicativo orientado para Intune comporta-se como um aplicativo normal que não oferece suporte a políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-133">When the Company Portal app is not on the device, an Intune-enlightened app behaves the same as a normal app that does not support Intune app protection policies.</span></span>

<span data-ttu-id="749d4-134">Para a proteção do aplicativo sem registro de dispositivo, o usuário _**não**_ precisa registrar o dispositivo usando o aplicativo do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="749d4-134">For app protection without device enrollment, the user is _**not**_ required to enroll the device by using the Company Portal app.</span></span>

## <span data-ttu-id="749d4-135">Integração do SDK</span><span class="sxs-lookup"><span data-stu-id="749d4-135">SDK Integration</span></span>
<a id="sdk-integration" class="xliff"></a>

### <span data-ttu-id="749d4-136">Integração de compilação</span><span class="sxs-lookup"><span data-stu-id="749d4-136">Build integration</span></span>
<a id="build-integration" class="xliff"></a>

<span data-ttu-id="749d4-137">O SDK de Aplicativos do Intune é uma biblioteca Android padrão sem dependências externas.</span><span class="sxs-lookup"><span data-stu-id="749d4-137">The Intune App SDK is a standard Android library with no external dependencies.</span></span> <span data-ttu-id="749d4-138">O **Microsoft.Intune.MAM.SDK.jar** contém ambas as interfaces necessárias para a habilitação da política de proteção de aplicativo e o código necessário para interoperar com o aplicativo do Portal da Empresa do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-138">**Microsoft.Intune.MAM.SDK.jar** contains both the interfaces necessary for an app protection policy enablement and the code necessary to interoperate with the Microsoft Intune Company Portal app.</span></span>

<span data-ttu-id="749d4-139">O **Microsoft.Intune.MAM.SDK.jar** deve ser especificado como uma referência da biblioteca do Android.</span><span class="sxs-lookup"><span data-stu-id="749d4-139">**Microsoft.Intune.MAM.SDK.jar** must be specified as an Android library reference.</span></span> <span data-ttu-id="749d4-140">Para fazer isso, abra o projeto de aplicativo no Android Studio e vá para **Arquivo > Novo > Novo módulo** e selecione **Importar .JAR/Pacote .AAR**.</span><span class="sxs-lookup"><span data-stu-id="749d4-140">To do this, open your app project in Android Studio and go to **File > New > New module** and select **Import .JAR/.AAR Package**.</span></span> <span data-ttu-id="749d4-141">Selecione nosso pacote de arquivamento do Android Microsoft.Intune.MAM.SDK.aar.</span><span class="sxs-lookup"><span data-stu-id="749d4-141">Select our Android archive package Microsoft.Intune.MAM.SDK.aar.</span></span>

<span data-ttu-id="749d4-142">Além disso, o **Microsoft.Intune.MAM.SDK.Support.v4** e o **Microsoft.Intune.MAM.SDK.Support.v7** contêm variantes do Intune de `android.support.v4` e `android.support.v7` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="749d4-142">Additionally, **Microsoft.Intune.MAM.SDK.Support.v4** and **Microsoft.Intune.MAM.SDK.Support.v7** contain Intune variants of `android.support.v4` and `android.support.v7` respectively.</span></span> <span data-ttu-id="749d4-143">Eles não são criados no Microsoft.Intune.MAM.SDK.aar no caso de um aplicativo não querer incluir as bibliotecas de suporte.</span><span class="sxs-lookup"><span data-stu-id="749d4-143">They are not built into Microsoft.Intune.MAM.SDK.aar in case an app does not want to include the support libraries.</span></span> <span data-ttu-id="749d4-144">Eles são arquivos JAR padrão em vez de projetos de biblioteca do Android.</span><span class="sxs-lookup"><span data-stu-id="749d4-144">They are standard JAR files instead of Android library projects.</span></span>

#### <span data-ttu-id="749d4-145">ProGuard</span><span class="sxs-lookup"><span data-stu-id="749d4-145">ProGuard</span></span>
<a id="proguard" class="xliff"></a>

<span data-ttu-id="749d4-146">Se o [ProGuard](http://proguard.sourceforge.net/) (ou qualquer outro mecanismo de redução/ofuscação) for usado como uma etapa de compilação, as classes de SDK do Intune deverão ser excluídas.</span><span class="sxs-lookup"><span data-stu-id="749d4-146">If [ProGuard](http://proguard.sourceforge.net/) (or any other shrinking/obfuscation mechanism) is used as a build step, Intune SDK classes must be excluded.</span></span> <span data-ttu-id="749d4-147">Para o ProGuard, isso pode ser feito incluindo as regras do arquivo proguard.txt distribuído com o SDK.</span><span class="sxs-lookup"><span data-stu-id="749d4-147">For ProGuard, this can be accomplished by including the rules from the proguard.txt file distributed with the SDK.</span></span>

<span data-ttu-id="749d4-148">As Bibliotecas de autenticação do Azure Active Directory (ADAL) podem ter suas próprias restrições de ProGuard.</span><span class="sxs-lookup"><span data-stu-id="749d4-148">The Azure Active Directory Authentication Libraries (ADAL) may have its own ProGuard restrictions.</span></span> <span data-ttu-id="749d4-149">Se seu aplicativo se integrar com a ADAL, você deverá seguir a documentação do ADAL sobre estas restrições.</span><span class="sxs-lookup"><span data-stu-id="749d4-149">If your app integrates ADAL, you must follow the ADAL documentation on these restrictions.</span></span>

### <span data-ttu-id="749d4-150">Pontos de entrada</span><span class="sxs-lookup"><span data-stu-id="749d4-150">Entry points</span></span>
<a id="entry-points" class="xliff"></a>

<span data-ttu-id="749d4-151">A Biblioteca de Autenticação do Azure Active Directory ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) exige essas permissões para realizar a autenticação agenciada.</span><span class="sxs-lookup"><span data-stu-id="749d4-151">The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication.</span></span> <span data-ttu-id="749d4-152">Se essas permissões não forem concedidas ao aplicativo ou revogadas pelo usuário, os fluxos de autenticação que exigem o agente (o aplicativo de Portal da Empresa) serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="749d4-152">If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.</span></span>

<span data-ttu-id="749d4-153">O SDK de Aplicativo do Intune requer alterações no código-fonte do aplicativo para habilitar as políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-153">The Intune App SDK requires changes to an app's source code to enable Intune app protection policies.</span></span> <span data-ttu-id="749d4-154">Isso é feito por meio da substituição das classes base do Android por classes base do Intune equivalentes, cujos nomes têm o prefixo **MAM**.</span><span class="sxs-lookup"><span data-stu-id="749d4-154">This is done through the replacement of the Android base classes with equivalent Intune base classes, whose names have the prefix **MAM**.</span></span> <span data-ttu-id="749d4-155">As classes do SDK estão entre a classe base do Android e a versão do próprio aplicativo derivada dessa classe.</span><span class="sxs-lookup"><span data-stu-id="749d4-155">The SDK classes live between the Android base class and the app's own derived version of that class.</span></span> <span data-ttu-id="749d4-156">Usando uma atividade como exemplo, você acabará com uma hierarquia de herança que se parece com: `Activity` > `MAMActivity` > `AppSpecificActivity`.</span><span class="sxs-lookup"><span data-stu-id="749d4-156">Using an activity as an example, you end up with an inheritance hierarchy that looks like: `Activity` > `MAMActivity` > `AppSpecificActivity`.</span></span>

<span data-ttu-id="749d4-157">Por exemplo, quando `AppSpecificActivity` interage com seu pai (por exemplo, chamando `super.onCreate()`), `MAMActivity` é a superclasse.</span><span class="sxs-lookup"><span data-stu-id="749d4-157">For example, when `AppSpecificActivity` interacts with its parent (for example, calling `super.onCreate()`), `MAMActivity` is the super class.</span></span>

<span data-ttu-id="749d4-158">Aplicativos Android típicos têm um modo único e têm acesso ao sistema por meio de seu objeto de [**Contexto**](https://developer.android.com/reference/android/content/Context.html).</span><span class="sxs-lookup"><span data-stu-id="749d4-158">Typical Android apps have a single mode and can access the system through their [**Context**](https://developer.android.com/reference/android/content/Context.html) object.</span></span> <span data-ttu-id="749d4-159">Aplicativos que integraram o SDK de Aplicativo do Intune, por outro lado, têm modo dual.</span><span class="sxs-lookup"><span data-stu-id="749d4-159">Apps that have integrated the Intune App SDK, on the other hand, have dual modes.</span></span> <span data-ttu-id="749d4-160">Esses aplicativos continuam a acessar o sistema por meio do objeto `Context`.</span><span class="sxs-lookup"><span data-stu-id="749d4-160">These apps continue to access the system through the `Context` object.</span></span> <span data-ttu-id="749d4-161">Dependendo da base de `Activity` utilizada, o objeto `Context` será fornecido pelo Android ou será inteligentemente multiplexado entre uma exibição restrita do sistema e a fornecida pelo Android `Context`.</span><span class="sxs-lookup"><span data-stu-id="749d4-161">Depending on the base `Activity` used, the `Context` object will be provided by Android or will intelligently multiplex between a restricted view of the system and the Android-provided `Context`.</span></span>


## <span data-ttu-id="749d4-162">Substitua classes, métodos e atividades por seus equivalentes com MAM</span><span class="sxs-lookup"><span data-stu-id="749d4-162">Replace classes, methods, and activities with their MAM equivalent</span></span>
<a id="replace-classes-methods-and-activities-with-their-mam-equivalent" class="xliff"></a>

<span data-ttu-id="749d4-163">As classes base do Android devem ser substituídas por seus equivalentes com MAM.</span><span class="sxs-lookup"><span data-stu-id="749d4-163">Android base classes must be replaced with their respective MAM equivalents.</span></span> <span data-ttu-id="749d4-164">Para fazer isso, localize todas as instâncias das classes listadas na tabela a seguir e as substitua pelo SDK de Aplicativo do Intune equivalente.</span><span class="sxs-lookup"><span data-stu-id="749d4-164">To do so, find all instances of the classes listed in the following table and replace them with the Intune App SDK equivalent.</span></span>

| <span data-ttu-id="749d4-165">Classe base do Android</span><span class="sxs-lookup"><span data-stu-id="749d4-165">Android base class</span></span> | <span data-ttu-id="749d4-166">Substituição do SDK de Aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="749d4-166">Intune App SDK replacement</span></span> |
|--|--|
| <span data-ttu-id="749d4-167">android.app.Activity</span><span class="sxs-lookup"><span data-stu-id="749d4-167">android.app.Activity</span></span> | <span data-ttu-id="749d4-168">MAMActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-168">MAMActivity</span></span> |
| <span data-ttu-id="749d4-169">android.app.ActivityGroup</span><span class="sxs-lookup"><span data-stu-id="749d4-169">android.app.ActivityGroup</span></span> | <span data-ttu-id="749d4-170">MAMActivityGroup</span><span class="sxs-lookup"><span data-stu-id="749d4-170">MAMActivityGroup</span></span> |
| <span data-ttu-id="749d4-171">android.app.AliasActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-171">android.app.AliasActivity</span></span> | <span data-ttu-id="749d4-172">MAMAliasActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-172">MAMAliasActivity</span></span> |
| <span data-ttu-id="749d4-173">android.app.Application</span><span class="sxs-lookup"><span data-stu-id="749d4-173">android.app.Application</span></span> | <span data-ttu-id="749d4-174">MAMApplication</span><span class="sxs-lookup"><span data-stu-id="749d4-174">MAMApplication</span></span> |
| <span data-ttu-id="749d4-175">android.app.DialogFragment</span><span class="sxs-lookup"><span data-stu-id="749d4-175">android.app.DialogFragment</span></span> | <span data-ttu-id="749d4-176">MAMDialogFragment</span><span class="sxs-lookup"><span data-stu-id="749d4-176">MAMDialogFragment</span></span> |
| <span data-ttu-id="749d4-177">android.app.ExpandableListActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-177">android.app.ExpandableListActivity</span></span> | <span data-ttu-id="749d4-178">MAMExpandableListActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-178">MAMExpandableListActivity</span></span> |
| <span data-ttu-id="749d4-179">android.app.Fragment</span><span class="sxs-lookup"><span data-stu-id="749d4-179">android.app.Fragment</span></span> | <span data-ttu-id="749d4-180">MAMFragment</span><span class="sxs-lookup"><span data-stu-id="749d4-180">MAMFragment</span></span> |
| <span data-ttu-id="749d4-181">android.app.IntentService</span><span class="sxs-lookup"><span data-stu-id="749d4-181">android.app.IntentService</span></span> | <span data-ttu-id="749d4-182">MAMIntentService</span><span class="sxs-lookup"><span data-stu-id="749d4-182">MAMIntentService</span></span> |
| <span data-ttu-id="749d4-183">android.app.LauncherActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-183">android.app.LauncherActivity</span></span> | <span data-ttu-id="749d4-184">MAMLauncherActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-184">MAMLauncherActivity</span></span> |
| <span data-ttu-id="749d4-185">android.app.ListActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-185">android.app.ListActivity</span></span> | <span data-ttu-id="749d4-186">MAMListActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-186">MAMListActivity</span></span> |
| <span data-ttu-id="749d4-187">android.app.NativeActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-187">android.app.NativeActivity</span></span> | <span data-ttu-id="749d4-188">MAMNativeActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-188">MAMNativeActivity</span></span> |
| <span data-ttu-id="749d4-189">android.app.PendingIntent</span><span class="sxs-lookup"><span data-stu-id="749d4-189">android.app.PendingIntent</span></span> | <span data-ttu-id="749d4-190">MAMPendingIntent (veja as observações abaixo)</span><span class="sxs-lookup"><span data-stu-id="749d4-190">MAMPendingIntent (see notes below)</span></span> |
| <span data-ttu-id="749d4-191">android.app.Service</span><span class="sxs-lookup"><span data-stu-id="749d4-191">android.app.Service</span></span> | <span data-ttu-id="749d4-192">MAMService</span><span class="sxs-lookup"><span data-stu-id="749d4-192">MAMService</span></span> |
| <span data-ttu-id="749d4-193">android.app.TabActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-193">android.app.TabActivity</span></span> | <span data-ttu-id="749d4-194">MAMTabActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-194">MAMTabActivity</span></span> |
| <span data-ttu-id="749d4-195">android.app.TaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="749d4-195">android.app.TaskStackBuilder</span></span> | <span data-ttu-id="749d4-196">MAMTaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="749d4-196">MAMTaskStackBuilder</span></span> |
| <span data-ttu-id="749d4-197">android.app.backup.BackupAgent</span><span class="sxs-lookup"><span data-stu-id="749d4-197">android.app.backup.BackupAgent</span></span> | <span data-ttu-id="749d4-198">MAMBackupAgent</span><span class="sxs-lookup"><span data-stu-id="749d4-198">MAMBackupAgent</span></span> |
| <span data-ttu-id="749d4-199">android.app.backup.BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-199">android.app.backup.BackupAgentHelper</span></span> | <span data-ttu-id="749d4-200">MAMBackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-200">MAMBackupAgentHelper</span></span> |
| <span data-ttu-id="749d4-201">android.app.backup.FileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-201">android.app.backup.FileBackupHelper</span></span> | <span data-ttu-id="749d4-202">MAMFileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-202">MAMFileBackupHelper</span></span> |
| <span data-ttu-id="749d4-203">android.app.backup.SharePreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-203">android.app.backup.SharePreferencesBackupHelper</span></span> | <span data-ttu-id="749d4-204">MAMSharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-204">MAMSharedPreferencesBackupHelper</span></span> |
| <span data-ttu-id="749d4-205">android.content.BroadcastReceiver</span><span class="sxs-lookup"><span data-stu-id="749d4-205">android.content.BroadcastReceiver</span></span> | <span data-ttu-id="749d4-206">MAMBroadcastReceiver</span><span class="sxs-lookup"><span data-stu-id="749d4-206">MAMBroadcastReceiver</span></span> |
| <span data-ttu-id="749d4-207">android.content.ContentProvider</span><span class="sxs-lookup"><span data-stu-id="749d4-207">android.content.ContentProvider</span></span> | <span data-ttu-id="749d4-208">MAMContentProvider</span><span class="sxs-lookup"><span data-stu-id="749d4-208">MAMContentProvider</span></span> |
| <span data-ttu-id="749d4-209">android.os.Binder</span><span class="sxs-lookup"><span data-stu-id="749d4-209">android.os.Binder</span></span> | <span data-ttu-id="749d4-210">MAMBinder (necessário apenas se o Associador não for gerado de uma interface da AIDL (linguagem IDL do Android))</span><span class="sxs-lookup"><span data-stu-id="749d4-210">MAMBinder (Only necessary if the Binder is not generated from an Android Interface Definition Language (AIDL) interface)</span></span> |
| <span data-ttu-id="749d4-211">android.provider.DocumentsProvider</span><span class="sxs-lookup"><span data-stu-id="749d4-211">android.provider.DocumentsProvider</span></span> | <span data-ttu-id="749d4-212">MAMDocumentsProvider</span><span class="sxs-lookup"><span data-stu-id="749d4-212">MAMDocumentsProvider</span></span> |
| <span data-ttu-id="749d4-213">android.preference.PreferenceActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-213">android.preference.PreferenceActivity</span></span> | <span data-ttu-id="749d4-214">MAMPreferenceActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-214">MAMPreferenceActivity</span></span> |


### <span data-ttu-id="749d4-215">Microsoft.Intune.MAM.SDK.Suppout.v4.jar:</span><span class="sxs-lookup"><span data-stu-id="749d4-215">Microsoft.Intune.MAM.SDK.Support.v4.jar:</span></span>
<a id="microsoftintunemamsdksupportv4jar" class="xliff"></a>

| <span data-ttu-id="749d4-216">MAM do Intune da classe Android</span><span class="sxs-lookup"><span data-stu-id="749d4-216">Android Class Intune MAM</span></span> | <span data-ttu-id="749d4-217">Substituição do SDK de Aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="749d4-217">Intune App SDK replacement</span></span> |
|--|--|
| <span data-ttu-id="749d4-218">android.support.v4.app.DialogFragment</span><span class="sxs-lookup"><span data-stu-id="749d4-218">android.support.v4.app.DialogFragment</span></span> | <span data-ttu-id="749d4-219">MAMDialogFragment</span><span class="sxs-lookup"><span data-stu-id="749d4-219">MAMDialogFragment</span></span>
| <span data-ttu-id="749d4-220">Android.support.v4.App.FragmentActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-220">android.support.v4.app.FragmentActivity</span></span> | <span data-ttu-id="749d4-221">MAMFragmentActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-221">MAMFragmentActivity</span></span>
| <span data-ttu-id="749d4-222">android.support.v4.app.Fragment</span><span class="sxs-lookup"><span data-stu-id="749d4-222">android.support.v4.app.Fragment</span></span> | <span data-ttu-id="749d4-223">MAMFragment</span><span class="sxs-lookup"><span data-stu-id="749d4-223">MAMFragment</span></span>
| <span data-ttu-id="749d4-224">android.support.v4.app.TaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="749d4-224">android.support.v4.app.TaskStackBuilder</span></span> | <span data-ttu-id="749d4-225">MAMTaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="749d4-225">MAMTaskStackBuilder</span></span>
| <span data-ttu-id="749d4-226">android.support.v4.content.FileProvider</span><span class="sxs-lookup"><span data-stu-id="749d4-226">android.support.v4.content.FileProvider</span></span> | <span data-ttu-id="749d4-227">MAMFileProvider</span><span class="sxs-lookup"><span data-stu-id="749d4-227">MAMFileProvider</span></span>

### <span data-ttu-id="749d4-228">Microsoft.Intune.MAM.SDK.Suppout.v7.jar:</span><span class="sxs-lookup"><span data-stu-id="749d4-228">Microsoft.Intune.MAM.SDK.Support.v7.jar:</span></span>
<a id="microsoftintunemamsdksupportv7jar" class="xliff"></a>

|<span data-ttu-id="749d4-229">Classe do Android</span><span class="sxs-lookup"><span data-stu-id="749d4-229">Android Class</span></span> | <span data-ttu-id="749d4-230">Substituição do SDK de Aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="749d4-230">Intune App SDK replacement</span></span> |
|--|--|
|<span data-ttu-id="749d4-231">Android.support.v7.App.ActionBarActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-231">android.support.v7.app.ActionBarActivity</span></span> | <span data-ttu-id="749d4-232">MAMActionBarActivity</span><span class="sxs-lookup"><span data-stu-id="749d4-232">MAMActionBarActivity</span></span> |


### <span data-ttu-id="749d4-233">Métodos renomeados</span><span class="sxs-lookup"><span data-stu-id="749d4-233">Renamed Methods</span></span>
<a id="renamed-methods" class="xliff"></a>
<span data-ttu-id="749d4-234">Após derivar de um dos pontos de entrada com MAM, é seguro usar `Context` normalmente – por exemplo, iniciando as classes `Activity` e usando `PackageManager`.</span><span class="sxs-lookup"><span data-stu-id="749d4-234">After you derive from one of the MAM entry points, it's safe to use `Context` as you would normally -- for example, starting `Activity` classes and using `PackageManager`.</span></span>

<span data-ttu-id="749d4-235">Em muitos casos, um método disponível na classe Android foi marcado como final na classe de MAM de substituição.</span><span class="sxs-lookup"><span data-stu-id="749d4-235">In many cases, a method available in the Android class has been marked as final in the MAM replacement class.</span></span> <span data-ttu-id="749d4-236">Nesse caso, a classe de MAM de substituição fornece um método nomeado da mesma forma (em geral, com o sufixo `MAM`), que deve ser substituído em vez disso.</span><span class="sxs-lookup"><span data-stu-id="749d4-236">In this case, the MAM replacement class provides a similarly named method (generally suffixed with `MAM`) that you should override instead.</span></span> <span data-ttu-id="749d4-237">Por exemplo, ao derivar de `MAMActivity`, em vez de substituir `onCreate()` e chamar `super.onCreate()`, `Activity` deve substituir `onMAMCreate()` e chamar `super.onMAMCreate()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-237">For example, when deriving from `MAMActivity`, instead of overriding `onCreate()` and calling `super.onCreate()`, `Activity` must override `onMAMCreate()` and call `super.onMAMCreate()`.</span></span> <span data-ttu-id="749d4-238">O compilador Java deve impor as restrições finais para evitar a substituição acidental do método original em vez do MAM equivalente.</span><span class="sxs-lookup"><span data-stu-id="749d4-238">The Java compiler should enforce the final restrictions to prevent accidental override of the original method instead of the MAM equivalent.</span></span>

### <span data-ttu-id="749d4-239">PendingIntent</span><span class="sxs-lookup"><span data-stu-id="749d4-239">PendingIntent</span></span>
<a id="pendingintent" class="xliff"></a>
<span data-ttu-id="749d4-240">Em vez de `PendingIntent.get*`, você deve usar o método `MAMPendingIntent.get*`.</span><span class="sxs-lookup"><span data-stu-id="749d4-240">Instead of `PendingIntent.get*`, you must use the `MAMPendingIntent.get*` method.</span></span> <span data-ttu-id="749d4-241">Depois disso, você pode usar o `PendingIntent` resultante, como de costume.</span><span class="sxs-lookup"><span data-stu-id="749d4-241">After this, you can use the resultant `PendingIntent` as usual.</span></span>

### <span data-ttu-id="749d4-242">Substituições de manifesto</span><span class="sxs-lookup"><span data-stu-id="749d4-242">Manifest Replacements</span></span>
<a id="manifest-replacements" class="xliff"></a>
<span data-ttu-id="749d4-243">Observe que talvez seja necessário executar algumas das substituições de classe acima no manifesto, bem como no código Java.</span><span class="sxs-lookup"><span data-stu-id="749d4-243">Please note that it may be necessary to perform some of the above class replacements in the manifest as well as in Java code.</span></span> <span data-ttu-id="749d4-244">Nota especial:</span><span class="sxs-lookup"><span data-stu-id="749d4-244">Of special note:</span></span>
* <span data-ttu-id="749d4-245">As referências do manifesto a `android.support.v4.content.FileProvider` devem ser substituídas por `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.</span><span class="sxs-lookup"><span data-stu-id="749d4-245">Manifest references to `android.support.v4.content.FileProvider` must be replaced with `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.</span></span>


## <span data-ttu-id="749d4-246">Permissões do SDK</span><span class="sxs-lookup"><span data-stu-id="749d4-246">SDK permissions</span></span>
<a id="sdk-permissions" class="xliff"></a>

<span data-ttu-id="749d4-247">O SDK de Aplicativo do Intune exige três [permissões de sistema do Android](https://developer.android.com/guide/topics/security/permissions.html) em aplicativos que o integram:</span><span class="sxs-lookup"><span data-stu-id="749d4-247">The Intune App SDK requires three [Android system permissions](https://developer.android.com/guide/topics/security/permissions.html) on apps that integrate it:</span></span>

* <span data-ttu-id="749d4-248">`android.permission.GET_ACCOUNTS`  (solicitada em tempo de execução se necessário)</span><span class="sxs-lookup"><span data-stu-id="749d4-248">`android.permission.GET_ACCOUNTS`  (requested at runtime if required)</span></span>

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

<span data-ttu-id="749d4-249">A Biblioteca de Autenticação do Azure Active Directory ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) exige essas permissões para realizar a autenticação agenciada.</span><span class="sxs-lookup"><span data-stu-id="749d4-249">The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication.</span></span> <span data-ttu-id="749d4-250">Se essas permissões não forem concedidas ao aplicativo ou revogadas pelo usuário, os fluxos de autenticação que exigem o agente (o aplicativo de Portal da Empresa) serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="749d4-250">If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.</span></span>

## <span data-ttu-id="749d4-251">Logging</span><span class="sxs-lookup"><span data-stu-id="749d4-251">Logging</span></span>
<a id="logging" class="xliff"></a>

<span data-ttu-id="749d4-252">O registro em log deve ser inicializado no início para obter o máximo dos dados registrados.</span><span class="sxs-lookup"><span data-stu-id="749d4-252">Logging should be initialized early to get the most value out of logged data.</span></span> <span data-ttu-id="749d4-253">O `Application.onMAMCreate()` normalmente é o melhor lugar para inicializar o registro em log.</span><span class="sxs-lookup"><span data-stu-id="749d4-253">`Application.onMAMCreate()` is typically the best place to initialize logging.</span></span>

<span data-ttu-id="749d4-254">Para receber logs do MAM em seu aplicativo, crie um [manipulador Java](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) e adicione-o ao `MAMLogHandlerWrapper`.</span><span class="sxs-lookup"><span data-stu-id="749d4-254">To receive MAM logs in your app, create a [Java Handler](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) and add it to the `MAMLogHandlerWrapper`.</span></span> <span data-ttu-id="749d4-255">Isso irá chamar o `publish()` no manipulador de aplicativo para cada mensagem de log.</span><span class="sxs-lookup"><span data-stu-id="749d4-255">This will invoke `publish()` on the application handler for every log message.</span></span>

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <span data-ttu-id="749d4-256">Habilitar recursos que exigem a participação do aplicativo</span><span class="sxs-lookup"><span data-stu-id="749d4-256">Enable features that require app participation</span></span>
<a id="enable-features-that-require-app-participation" class="xliff"></a>

<span data-ttu-id="749d4-257">Há várias políticas de proteção de aplicativo que o SDK não pode implementar por conta própria.</span><span class="sxs-lookup"><span data-stu-id="749d4-257">There are several app protection policies the SDK cannot implement on its own.</span></span> <span data-ttu-id="749d4-258">O aplicativo pode controlar seu comportamento para conquistar esses recursos usando várias APIs que podem ser encontradas na interface `AppPolicy` a seguir.</span><span class="sxs-lookup"><span data-stu-id="749d4-258">The app can control its behavior to achieve these features by using several APIs that you can find in the following `AppPolicy` interface.</span></span>

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}

```

> [!NOTE]
> <span data-ttu-id="749d4-259">`MAMComponents.get(AppPolicy.class)` sempre retornará uma política de aplicativo não nula, mesmo que o dispositivo ou aplicativo não esteja sob uma política de gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-259">`MAMComponents.get(AppPolicy.class)` will always return a non-null App Policy, even if the device or app is not under an Intune management policy.</span></span>

### <span data-ttu-id="749d4-260">Exemplo: determinar se o PIN é necessário para o aplicativo</span><span class="sxs-lookup"><span data-stu-id="749d4-260">Example: Determine if PIN is required for the app</span></span>
<a id="example-determine-if-pin-is-required-for-the-app" class="xliff"></a>

<span data-ttu-id="749d4-261">Se o aplicativo tem sua própria experiência de usuário de PIN, convém desabilitá-lo se o administrador de TI tiver configurado o SDK para solicitar um PIN do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-261">If the app has its own PIN user experience, you might want to disable it if the IT administrator has configured the SDK to prompt for an app PIN.</span></span> <span data-ttu-id="749d4-262">Para determinar se o administrador de TI implantou a política PIN de aplicativo para esse aplicativo, para o usuário final atual, chame o método a seguir:</span><span class="sxs-lookup"><span data-stu-id="749d4-262">To determine if the IT administrator has deployed the app PIN policy to this app, for the current end user, call the following method:</span></span>

```java
MAMComponents.get(AppPolicy.class).getIsPinRequired();
```

### <span data-ttu-id="749d4-263">Exemplo: determinar o usuário principal do Intune</span><span class="sxs-lookup"><span data-stu-id="749d4-263">Example: Determine the primary Intune user</span></span>
<a id="example-determine-the-primary-intune-user" class="xliff"></a>

<span data-ttu-id="749d4-264">Além das APIs expostas na AppPolicy, o nome principal do usuário (**UPN**) também é exposto pela API `getPrimaryUser()` definida dentro da interface do `MAMUserInfo`.</span><span class="sxs-lookup"><span data-stu-id="749d4-264">In addition to the APIs exposed in AppPolicy, the user principal name (**UPN**) is also exposed by the `getPrimaryUser()` API defined inside the `MAMUserInfo` interface.</span></span> <span data-ttu-id="749d4-265">Para obter o UPN, chame o seguinte:</span><span class="sxs-lookup"><span data-stu-id="749d4-265">To get the UPN, call the following:</span></span>

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

<span data-ttu-id="749d4-266">A definição completa da interface MAMUserInfo está disponível abaixo:</span><span class="sxs-lookup"><span data-stu-id="749d4-266">The full definition of the MAMUserInfo interface is below:</span></span>

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <span data-ttu-id="749d4-267">Exemplo: determinar se é permitido salvar em dispositivo ou armazenamento em nuvem</span><span class="sxs-lookup"><span data-stu-id="749d4-267">Example: Determine if saving to device or cloud storage is permitted</span></span>
<a id="example-determine-if-saving-to-device-or-cloud-storage-is-permitted" class="xliff"></a>

<span data-ttu-id="749d4-268">Muitos aplicativos implementam recursos que permitem que o usuário final salve arquivos localmente ou em um serviço de armazenamento em nuvem.</span><span class="sxs-lookup"><span data-stu-id="749d4-268">Many apps implement features that allow the end user to save files locally or to a cloud storage service.</span></span> <span data-ttu-id="749d4-269">O SDK de Aplicativo do Azure permite que os administradores de TI protejam contra vazamento de dados aplicando as restrições de política da forma que considerarem adequada para sua organização.</span><span class="sxs-lookup"><span data-stu-id="749d4-269">The Intune App SDK allows IT administrators to protect against data leakage by applying policy restrictions as they see fit in their organization.</span></span>  <span data-ttu-id="749d4-270">Uma das políticas que o setor de TI pode controlar é se o usuário final pode salvar em um armazenamento de dados "pessoal" não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="749d4-270">One of the policies that IT can control is whether the end user can save to a "personal," unmanaged data store.</span></span> <span data-ttu-id="749d4-271">Isso inclui salvar localmente, em cartões SD ou em serviços de backup de terceiros.</span><span class="sxs-lookup"><span data-stu-id="749d4-271">This includes saving to a local location, SD card, or third-party backup services.</span></span>

<span data-ttu-id="749d4-272">**A participação do aplicativo é necessária para habilitar o recurso.**</span><span class="sxs-lookup"><span data-stu-id="749d4-272">**App participation is needed to enable the feature.**</span></span> <span data-ttu-id="749d4-273">Se o seu aplicativo permitir o salvamento em locais na nuvem ou pessoais diretamente do aplicativo, você deve implementar esse recurso para garantir que o administrador de TI possa controlar se é permitido salvar em um local.</span><span class="sxs-lookup"><span data-stu-id="749d4-273">If your app allows saving to personal or cloud locations directly from the app, you must implement this feature to ensure that the IT administrator can control whether saving to a location is allowed.</span></span> <span data-ttu-id="749d4-274">A API abaixo permite que o aplicativo saiba se é permitido salvar em um armazenamento pessoal de acordo com a atual política do administrador.</span><span class="sxs-lookup"><span data-stu-id="749d4-274">The API below lets the app know whether saving to a personal store is allowed by the current Intune administrator's policy.</span></span> <span data-ttu-id="749d4-275">O aplicativo pode, então, aplicar a política, pois ele está ciente de que o armazenamento pessoal de dados está disponível para o usuário final por meio do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-275">The app can then enforce the policy, since it is aware of personal data store available to the end user through the app.</span></span>  

<span data-ttu-id="749d4-276">Para determinar se a política é aplicada, faça a chamada a seguir:</span><span class="sxs-lookup"><span data-stu-id="749d4-276">To determine if the policy is enforced, make the following call:</span></span>

```java
MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(
SaveLocation service, String username);
```

<span data-ttu-id="749d4-277">... onde `service` é um dos seguintes SaveLocations:</span><span class="sxs-lookup"><span data-stu-id="749d4-277">... where `service` is one of the following SaveLocations:</span></span>


    * <span data-ttu-id="749d4-278">SaveLocation.ONEDRIVE_FOR_BUSINESS</span><span class="sxs-lookup"><span data-stu-id="749d4-278">SaveLocation.ONEDRIVE_FOR_BUSINESS</span></span>
    * <span data-ttu-id="749d4-279">SaveLocation.LOCAL</span><span class="sxs-lookup"><span data-stu-id="749d4-279">SaveLocation.LOCAL</span></span>
    * <span data-ttu-id="749d4-280">SaveLocation.OTHER</span><span class="sxs-lookup"><span data-stu-id="749d4-280">SaveLocation.OTHER</span></span>

<span data-ttu-id="749d4-281">O método anterior para determinar se a política de um usuário permitia que eles salvassem dados em vários locais era `getIsSaveToPersonalAllowed()` dentro da mesma classe **AppPolicy**.</span><span class="sxs-lookup"><span data-stu-id="749d4-281">The previous method of determining whether a user’s policy allowed them to save data to various locations was `getIsSaveToPersonalAllowed()` within the same **AppPolicy** class.</span></span> <span data-ttu-id="749d4-282">Essa função está agora **preterida** e não deve ser usada, a chamada a seguir é equivalente a `getIsSaveToPersonalAllowed()`:</span><span class="sxs-lookup"><span data-stu-id="749d4-282">This function is now **deprecated** and should not be used, the following invocation is equivalent to `getIsSaveToPersonalAllowed()`:</span></span>

```java

MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> <span data-ttu-id="749d4-283">Use `SaveLocation.OTHER` se o local em questão não estiver listado na enum **SaveLocations**.</span><span class="sxs-lookup"><span data-stu-id="749d4-283">Use `SaveLocation.OTHER` if the location in question is not listed in the **SaveLocations** enum.</span></span>


## <span data-ttu-id="749d4-284">Registrar-se para notificações do SDK</span><span class="sxs-lookup"><span data-stu-id="749d4-284">Register for notifications from the SDK</span></span>
<a id="register-for-notifications-from-the-sdk" class="xliff"></a>

### <span data-ttu-id="749d4-285">Visão geral</span><span class="sxs-lookup"><span data-stu-id="749d4-285">Overview</span></span>
<a id="overview" class="xliff"></a>
<span data-ttu-id="749d4-286">O SDK de Aplicativo do Intune permite que seu aplicativo controle o comportamento de algumas políticas, como um apagamento remoto, quando elas são implantadas pelo administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="749d4-286">The Intune App SDK allows your app to control the behavior of certain policies, such as selective wipe, when they are deployed by the IT administrator.</span></span> <span data-ttu-id="749d4-287">Quando um administrador de TI implanta tal política, o serviço do Intune envia uma notificação para o SDK.</span><span class="sxs-lookup"><span data-stu-id="749d4-287">When an IT administrator deploys such a policy, the Intune service sends down a notification to the SDK.</span></span>

<span data-ttu-id="749d4-288">O aplicativo deve ser registrado para receber notificações do SDK, criando uma `MAMNotificationReceiver` e registrando-a com `MAMNotificationReceiverRegistry`.</span><span class="sxs-lookup"><span data-stu-id="749d4-288">Your app must register for notifications from the SDK by creating a `MAMNotificationReceiver` and  registering it with `MAMNotificationReceiverRegistry`.</span></span> <span data-ttu-id="749d4-289">Isso é feito fornecendo o receptor e o tipo de notificação desejada em `App.onCreate`, como mostra o exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="749d4-289">This is done by providing the receiver and the type of notification desired in  `App.onCreate`, as the example below illustrates:</span></span>

```java
@Override
public void onCreate() {
    super.onCreate();
    MAMComponents.get(MAMNotificationReceiverRegistry.class)
        .registerReceiver(
            new ToastNotificationReceiver(),
            MAMNotificationType.WIPE_USER_DATA);
    }
```

### <span data-ttu-id="749d4-290">MAMNotificationReceiver</span><span class="sxs-lookup"><span data-stu-id="749d4-290">MAMNotificationReceiver</span></span>
<a id="mamnotificationreceiver" class="xliff"></a>

<span data-ttu-id="749d4-291">A interface `MAMNotificationReceiver` apenas recebe notificações do serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-291">The `MAMNotificationReceiver` interface simply receives notifications from the Intune service.</span></span> <span data-ttu-id="749d4-292">Algumas notificações são manipuladas pelo SDK diretamente, enquanto outras exigem a participação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-292">Some notifications are handled by the SDK directly, while others require the app's participation.</span></span> <span data-ttu-id="749d4-293">Um aplicativo **deve** retornar true ou false de uma notificação.</span><span class="sxs-lookup"><span data-stu-id="749d4-293">An app **must** return either true or false from a notification.</span></span> <span data-ttu-id="749d4-294">Ele deve sempre retornar true, a menos que alguma ação que ele tentou executar como resultado da notificação falhe.</span><span class="sxs-lookup"><span data-stu-id="749d4-294">It must always return true unless some action it tried to take as a result of the notification failed.</span></span>

* <span data-ttu-id="749d4-295">Essa falha pode ser relatada ao serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-295">This failure may be reported to the Intune service.</span></span> <span data-ttu-id="749d4-296">Um exemplo de cenário a ser relatado é se o aplicativo falhar ao apagar dados do usuário após o administrador de TI iniciar um apagamento.</span><span class="sxs-lookup"><span data-stu-id="749d4-296">An example of a scenario to report is if the app fails to wipe user data after the IT administrator initiates a wipe.</span></span>

>[!NOTE]
> <span data-ttu-id="749d4-297">É seguro bloquear em `MAMNotificationReceiver.onReceive` porque seu retorno de chamada não está em execução no thread da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="749d4-297">It is safe to block in `MAMNotificationReceiver.onReceive` because its callback is not running on the UI thread.</span></span>

<span data-ttu-id="749d4-298">A interface do `MAMNotificationReceiver` conforme definida no SDK está incluída abaixo:</span><span class="sxs-lookup"><span data-stu-id="749d4-298">The `MAMNotificationReceiver` interface as defined in the SDK is included below :</span></span>

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

### <span data-ttu-id="749d4-299">Tipos de notificações</span><span class="sxs-lookup"><span data-stu-id="749d4-299">Types of notifications</span></span>
<a id="types-of-notifications" class="xliff"></a>

<span data-ttu-id="749d4-300">As seguintes notificações são enviadas para o aplicativo e algumas delas podem exigir a participação do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="749d4-300">The following notifications are sent to the app and some of them may require app participation:</span></span>

* <span data-ttu-id="749d4-301">**WIPE_USER_DATA**: essa notificação é enviada em uma classe `MAMUserNotification`.</span><span class="sxs-lookup"><span data-stu-id="749d4-301">**WIPE_USER_DATA**: This notification is sent in a `MAMUserNotification` class.</span></span> <span data-ttu-id="749d4-302">Quando a notificação é recebida, o aplicativo deve excluir todos os dados associados à identidade "corporativa" passada com o `MAMUserNotification`.</span><span class="sxs-lookup"><span data-stu-id="749d4-302">When this notification is received, the app is expected to delete all data associated with the "corporate" identity passed with the `MAMUserNotification`.</span></span> <span data-ttu-id="749d4-303">Atualmente, essa notificação é enviada durante o cancelamento do registro do serviço do APP-WE.</span><span class="sxs-lookup"><span data-stu-id="749d4-303">This notification is currently sent during APP-WE service unenrollment.</span></span> <span data-ttu-id="749d4-304">O nome principal do usuário geralmente é especificado durante o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="749d4-304">The user's primary name is typically specified during the enrollment process.</span></span> <span data-ttu-id="749d4-305">Se você se registrar para essa notificação, seu aplicativo deve garantir que todos os dados do usuário tenham sido excluídos.</span><span class="sxs-lookup"><span data-stu-id="749d4-305">If you register for this notification, your app must ensure that all the user's data has been deleted.</span></span> <span data-ttu-id="749d4-306">Se você não se registrar para ela, o comportamento de apagamento seletivo padrão será executado.</span><span class="sxs-lookup"><span data-stu-id="749d4-306">If you don't register for it, the default selective wipe behavior will be performed.</span></span>

* <span data-ttu-id="749d4-307">**WIPE_USER_AUXILIARY_DATA**: os aplicativos podem se registrar para essa notificação se quiserem que o SDK de Aplicativo do Intune execute o comportamento de apagamento seletivo padrão, mas ainda desejarem remover alguns dados auxiliares quando o apagamento ocorrer.</span><span class="sxs-lookup"><span data-stu-id="749d4-307">**WIPE_USER_AUXILIARY_DATA**: Apps can register for this notification if they'd like the Intune App SDK to perform the default selective wipe behavior, but would still like to remove some auxiliary data when the wipe occurs.</span></span>

* <span data-ttu-id="749d4-308">**REFRESH_POLICY**: essa notificação é enviada em uma `MAMUserNotification`.</span><span class="sxs-lookup"><span data-stu-id="749d4-308">**REFRESH_POLICY**: This notification is sent in a `MAMUserNotification`.</span></span> <span data-ttu-id="749d4-309">Quando a notificação é recebida, qualquer política do Intune armazenada em cache deve ser invalidada e atualizada.</span><span class="sxs-lookup"><span data-stu-id="749d4-309">When this notification is received, any cached Intune policy must be invalidated and updated.</span></span> <span data-ttu-id="749d4-310">Normalmente, isso é tratado pelo SDK, porém deve ser tratado pelo aplicativo se a política for usada de qualquer maneira persistente.</span><span class="sxs-lookup"><span data-stu-id="749d4-310">This is generally handled by the SDK; however, it should be handled by the app if the policy is used in any persistent way.</span></span>

* <span data-ttu-id="749d4-311">**MANAGEMENT_REMOVED**: essa notificação é enviada um `MAMUserNotification` e informa ao aplicativo que ele está prestes a não ser mais gerenciado.</span><span class="sxs-lookup"><span data-stu-id="749d4-311">**MANAGEMENT_REMOVED**: This notification is sent in a `MAMUserNotification` and informs the app that it is about to become unmanaged.</span></span> <span data-ttu-id="749d4-312">Depois de não ser gerenciado, ele não será mais capaz de ler arquivos criptografados, ler os dados criptografados com MAMDataProtectionManager, interagir com a área de transferência criptografada ou de outra forma participar do ecossistema de aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="749d4-312">Once unmanaged, it will no longer be able to read encrypted files, read data encrypted with MAMDataProtectionManager, interact with the encrypted clipboard, or otherwise participate in the managed-app ecosystem.</span></span>


> [!NOTE]
> <span data-ttu-id="749d4-313">Um aplicativo nunca deve se registrar para as notificações `WIPE_USER_DATA` e `WIPE_USER_AUXILIARY_DATA` simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="749d4-313">An app should never register for both the `WIPE_USER_DATA` and `WIPE_USER_AUXILIARY_DATA` notifications.</span></span>


## <span data-ttu-id="749d4-314">Configurar a ADAL (Biblioteca de Autenticação do Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="749d4-314">Configure Azure Active Directory Authentication Library (ADAL)</span></span>
<a id="configure-azure-active-directory-authentication-library-adal" class="xliff"></a>

<span data-ttu-id="749d4-315">Primeiro, leia as diretrizes de integração ADAL encontradas no [repositório ADAL no GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).</span><span class="sxs-lookup"><span data-stu-id="749d4-315">First, please read the ADAL integration guidelines found in the [ADAL repository on GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).</span></span>

<span data-ttu-id="749d4-316">O SDK depende da [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) para [autenticação](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) e cenários de inicialização condicional, o que exige que os aplicativos sejam configurados com o [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/).</span><span class="sxs-lookup"><span data-stu-id="749d4-316">The SDK relies on [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) for its [authentication](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) and conditional launch scenarios, which require apps to be configured with [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/).</span></span> <span data-ttu-id="749d4-317">Os valores de configuração são comunicados para o SDK por meio dos metadados AndroidManifest.</span><span class="sxs-lookup"><span data-stu-id="749d4-317">The configuration values are communicated to the SDK via AndroidManifest metadata.</span></span>

<span data-ttu-id="749d4-318">Para configurar seu aplicativo e habilitar a autenticação adequada, adicione o seguinte ao nó de aplicativo no AndroidManifest.xml.</span><span class="sxs-lookup"><span data-stu-id="749d4-318">To configure your app and enable proper authentication, add the following to the app node in AndroidManifest.xml.</span></span> <span data-ttu-id="749d4-319">Algumas dessas configurações somente são necessárias se seu aplicativo usar o ADAL para autenticação em geral. Nesse caso, você precisará dos valores específicos que seu aplicativo usa para se registrar com o AAD.</span><span class="sxs-lookup"><span data-stu-id="749d4-319">Some of these configurations are only required if your app uses ADAL for authentication in general; in that case, you will need the specific values your app uses to register itself with AAD.</span></span> <span data-ttu-id="749d4-320">Isso é feito para garantir que não seja solicitada a autenticação do usuário final duas vezes devido ao AAD reconhecer dois valores de registro separados: um do aplicativo e um do SDK.</span><span class="sxs-lookup"><span data-stu-id="749d4-320">This is done to ensure that the end user does not get prompted for authentication twice, due to AAD recognizing two separate registration values: one from the app and one from the SDK.</span></span>

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <span data-ttu-id="749d4-321">Metadados de ADAL</span><span class="sxs-lookup"><span data-stu-id="749d4-321">ADAL metadata</span></span>
<a id="adal-metadata" class="xliff"></a>

* <span data-ttu-id="749d4-322">**Autoridade** é a autoridade AAD atual em uso.</span><span class="sxs-lookup"><span data-stu-id="749d4-322">**Authority** is the current AAD authority in use.</span></span> <span data-ttu-id="749d4-323">Se houver, será necessário usar seu próprio ambiente no qual as contas do AAD foram configuradas.</span><span class="sxs-lookup"><span data-stu-id="749d4-323">If present, you should use your own environment where AAD accounts have been configured.</span></span> <span data-ttu-id="749d4-324">Se esse valor estiver ausente, um padrão do Intune será usado.</span><span class="sxs-lookup"><span data-stu-id="749d4-324">If this value is absent, an Intune default is used.</span></span>

* <span data-ttu-id="749d4-325">**ClientID** é a ClientID do AAD a ser usada.</span><span class="sxs-lookup"><span data-stu-id="749d4-325">**ClientID** is the AAD ClientID to be used.</span></span> <span data-ttu-id="749d4-326">Você deve usar o ClientID do seu próprio aplicativo se ele estiver registrado com o AD do Azure.</span><span class="sxs-lookup"><span data-stu-id="749d4-326">You should use your own app's ClientID if it is registered with Azure AD.</span></span> <span data-ttu-id="749d4-327">Se esse valor estiver ausente, um padrão do Intune será usado.</span><span class="sxs-lookup"><span data-stu-id="749d4-327">If this value is absent, an Intune default is used.</span></span>

* <span data-ttu-id="749d4-328">**NonBrokerRedirectURI** é URI de redirecionamento do AAD para usar em casos sem agente.</span><span class="sxs-lookup"><span data-stu-id="749d4-328">**NonBrokerRedirectURI** is the AAD redirect URI to use in broker-less cases.</span></span> <span data-ttu-id="749d4-329">Se nenhum for especificado, um valor padrão `urn:ietf:wg:oauth:2.0:oob` será usado.</span><span class="sxs-lookup"><span data-stu-id="749d4-329">If none is specified, a default value of `urn:ietf:wg:oauth:2.0:oob` is used.</span></span> <span data-ttu-id="749d4-330">Esse padrão é adequado para a maioria dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="749d4-330">This default is suitable for most apps.</span></span>

* <span data-ttu-id="749d4-331">**SkipBroker** é usado no caso do ClientID não ter sido configurado para usar o URI de redirecionamento do agente.</span><span class="sxs-lookup"><span data-stu-id="749d4-331">**SkipBroker** is used in case the ClientID has not been configured to use the broker redirect URI.</span></span> <span data-ttu-id="749d4-332">O valor padrão é "false".</span><span class="sxs-lookup"><span data-stu-id="749d4-332">The default value is "false."</span></span>
    * <span data-ttu-id="749d4-333">Para aplicativos que **não integram o ADAL** e **não desejam participar de autenticação/SSO orientada para todo o dispositivo**, ele deve ser definido como "true".</span><span class="sxs-lookup"><span data-stu-id="749d4-333">For apps that **do not integrate ADAL** and **do not want to participate in device-wide brokered authentication/SSO**, this should be set to "true."</span></span> <span data-ttu-id="749d4-334">Quando esse valor for "true", o único URI de redirecionamento que será usado é NonBrokerRedirectURI.</span><span class="sxs-lookup"><span data-stu-id="749d4-334">When this value is "true," the only redirect URI that will be used is NonBrokerRedirectURI.</span></span>

    * <span data-ttu-id="749d4-335">Para aplicativos que dão suporte a agenciamento de SSO em todo o dispositivo, ele deve ser "false".</span><span class="sxs-lookup"><span data-stu-id="749d4-335">For apps that do support device-wide SSO brokering, this should be "false."</span></span> <span data-ttu-id="749d4-336">Quando o valor for "false", o SDK selecionará um agente entre o resultado de [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) e NonBrokerRedirectURI, com base na disponibilidade do agente no sistema.</span><span class="sxs-lookup"><span data-stu-id="749d4-336">When the value is "false," the SDK will select a broker between the result of [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) and NonBrokerRedirectURI, based on the availability of the broker on the system.</span></span> <span data-ttu-id="749d4-337">Em geral, o agente estará disponível no aplicativo do Portal da Empresa ou aplicativo do Autenticador do Azure.</span><span class="sxs-lookup"><span data-stu-id="749d4-337">In general, the broker will be available from the Company Portal app or Azure Authenticator app.</span></span>

### <span data-ttu-id="749d4-338">Configurações comuns do ADAL</span><span class="sxs-lookup"><span data-stu-id="749d4-338">Common ADAL configurations</span></span>
<a id="common-adal-configurations" class="xliff"></a>

<span data-ttu-id="749d4-339">Veja seguir as maneiras comuns de um aplicativo ser configurado com a ADAL.</span><span class="sxs-lookup"><span data-stu-id="749d4-339">The following are common ways an app can be configured with ADAL.</span></span> <span data-ttu-id="749d4-340">Localize a configuração do aplicativo e defina os parâmetros de metadados do ADAL (explicados acima) para os valores necessários.</span><span class="sxs-lookup"><span data-stu-id="749d4-340">Find your app's configuration and make sure to set the ADAL metadata parameters (explained above) to the necessary values.</span></span>

1. <span data-ttu-id="749d4-341">**O aplicativo não se integra ao ADAL:**</span><span class="sxs-lookup"><span data-stu-id="749d4-341">**App does not integrate ADAL:**</span></span>

    | <span data-ttu-id="749d4-342">Parâmetro do ADAL necessário</span><span class="sxs-lookup"><span data-stu-id="749d4-342">Required ADAL parameter</span></span> | <span data-ttu-id="749d4-343">Valor</span><span class="sxs-lookup"><span data-stu-id="749d4-343">Value</span></span> |
    |--|--|
    | <span data-ttu-id="749d4-344">Autoridade</span><span class="sxs-lookup"><span data-stu-id="749d4-344">Authority</span></span> | <span data-ttu-id="749d4-345">Ambiente desejado no qual as contas do AAD foram configuradas</span><span class="sxs-lookup"><span data-stu-id="749d4-345">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="749d4-346">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="749d4-346">SkipBroker</span></span> | <span data-ttu-id="749d4-347">verdadeiro</span><span class="sxs-lookup"><span data-stu-id="749d4-347">True</span></span> |

2. <span data-ttu-id="749d4-348">**O aplicativo integra o ADAL:**</span><span class="sxs-lookup"><span data-stu-id="749d4-348">**App integrates ADAL:**</span></span>

    |<span data-ttu-id="749d4-349">Parâmetro do ADAL necessário</span><span class="sxs-lookup"><span data-stu-id="749d4-349">Required ADAL parameter</span></span>| <span data-ttu-id="749d4-350">Valor</span><span class="sxs-lookup"><span data-stu-id="749d4-350">Value</span></span> |
    |--|--|
    | <span data-ttu-id="749d4-351">Autoridade</span><span class="sxs-lookup"><span data-stu-id="749d4-351">Authority</span></span> | <span data-ttu-id="749d4-352">Ambiente desejado no qual as contas do AAD foram configuradas</span><span class="sxs-lookup"><span data-stu-id="749d4-352">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="749d4-353">ClientID</span><span class="sxs-lookup"><span data-stu-id="749d4-353">ClientID</span></span> | <span data-ttu-id="749d4-354">O ClientID do aplicativo (gerado pelo AD do Azure, quando o aplicativo é registrado)</span><span class="sxs-lookup"><span data-stu-id="749d4-354">The app's ClientID (generated by Azure AD when the app is registered)</span></span> |
    | <span data-ttu-id="749d4-355">NonBrokerRedirectURI</span><span class="sxs-lookup"><span data-stu-id="749d4-355">NonBrokerRedirectURI</span></span> | <span data-ttu-id="749d4-356">Um URI de redirecionamento válido para o aplicativo ou `urn:ietf:wg:oauth:2.0:oob` por padrão.</span><span class="sxs-lookup"><span data-stu-id="749d4-356">A valid redirect URI for the app, or `urn:ietf:wg:oauth:2.0:oob` by default.</span></span> <br><br> <span data-ttu-id="749d4-357">Configure o valor como um URI de redirecionamento aceitável para o ClientID do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-357">Make sure to configure the value as an acceptable redirect URI for your app's ClientID.</span></span>
    | <span data-ttu-id="749d4-358">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="749d4-358">SkipBroker</span></span> | <span data-ttu-id="749d4-359">Falso</span><span class="sxs-lookup"><span data-stu-id="749d4-359">False</span></span> |


3. <span data-ttu-id="749d4-360">**O aplicativo integra-se ao ADAL, mas não oferece suporte a autenticação/SSO orientada para todo o dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="749d4-360">**App integrates ADAL but does not support brokered authentication/device-wide SSO:**</span></span>

    |<span data-ttu-id="749d4-361">Parâmetro do ADAL necessário</span><span class="sxs-lookup"><span data-stu-id="749d4-361">Required ADAL parameter</span></span>| <span data-ttu-id="749d4-362">Valor</span><span class="sxs-lookup"><span data-stu-id="749d4-362">Value</span></span> |
    |--|--|
    | <span data-ttu-id="749d4-363">Autoridade</span><span class="sxs-lookup"><span data-stu-id="749d4-363">Authority</span></span> | <span data-ttu-id="749d4-364">Ambiente desejado no qual as contas do AAD foram configuradas</span><span class="sxs-lookup"><span data-stu-id="749d4-364">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="749d4-365">ClientID</span><span class="sxs-lookup"><span data-stu-id="749d4-365">ClientID</span></span> | <span data-ttu-id="749d4-366">O ClientID do aplicativo (gerado pelo AD do Azure, quando o aplicativo é registrado)</span><span class="sxs-lookup"><span data-stu-id="749d4-366">The app's ClientID (generated by Azure AD when the app is registered)</span></span> |
    | <span data-ttu-id="749d4-367">NonBrokerRedirectURI</span><span class="sxs-lookup"><span data-stu-id="749d4-367">NonBrokerRedirectURI</span></span> | <span data-ttu-id="749d4-368">Um URI de redirecionamento válido para o aplicativo ou `urn:ietf:wg:oauth:2.0:oob` por padrão.</span><span class="sxs-lookup"><span data-stu-id="749d4-368">A valid redirect URI for the app, or `urn:ietf:wg:oauth:2.0:oob` by default.</span></span> <br><br> <span data-ttu-id="749d4-369">Configure o valor como um URI de redirecionamento aceitável para o ClientID do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-369">Make sure to configure the value as an acceptable redirect URI for your app's ClientID.</span></span>
    | <span data-ttu-id="749d4-370">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="749d4-370">SkipBroker</span></span> | <span data-ttu-id="749d4-371">**True**</span><span class="sxs-lookup"><span data-stu-id="749d4-371">**True**</span></span> |

## <span data-ttu-id="749d4-372">Política de proteção do aplicativo sem registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="749d4-372">App protection policy without device enrollment</span></span>
<a id="app-protection-policy-without-device-enrollment" class="xliff"></a>

### <span data-ttu-id="749d4-373">Visão geral</span><span class="sxs-lookup"><span data-stu-id="749d4-373">Overview</span></span>
<a id="overview" class="xliff"></a>
<span data-ttu-id="749d4-374">Política de proteção de aplicativo do Intune sem registro do dispositivo, também conhecido como APP-WE ou MAM-WE, permite que os aplicativos sejam gerenciados pelo Intune sem a necessidade de o dispositivo ser registrado no MDM do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-374">Intune app protection policy without device enrollment, also known as APP-WE or MAM-WE, allows apps to be managed by Intune without the need for the device to be enrolled Intune MDM.</span></span> <span data-ttu-id="749d4-375">O aplicativo-funciona com ou sem registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-375">APP-WE works with or without device enrollment.</span></span> <span data-ttu-id="749d4-376">O Portal da Empresa ainda é necessário para ser instalado no dispositivo, mas o usuário não precisa entrar no Portal da Empresa e registrar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-376">The Company Portal is still required to be installed on the device, but the user does not need to sign into the Company Portal and enroll the device.</span></span>

> [!NOTE]
> <span data-ttu-id="749d4-377">Todos os aplicativos são necessários para dar suporte à política de proteção do aplicativo sem registro de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-377">All apps are required to support app protection policy without device enrollment.</span></span>

### <span data-ttu-id="749d4-378">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="749d4-378">Workflow</span></span>
<a id="workflow" class="xliff"></a>

<span data-ttu-id="749d4-379">Quando um aplicativo cria uma nova conta de usuário, ele deve registrar a conta para gerenciamento com o SDK de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-379">When an app creates a new user account, it should register the account for management with the Intune App SDK.</span></span> <span data-ttu-id="749d4-380">O SDK tratará os detalhes do registro do aplicativo no serviço APP-WE; se necessário, ele tentará novamente outros registros em intervalos de tempo apropriados, se houver falhas.</span><span class="sxs-lookup"><span data-stu-id="749d4-380">The SDK will handle the details of enrolling the app in the APP-WE service; if necessary, it will retry any enrollments at appropriate time intervals if failures occur.</span></span>

<span data-ttu-id="749d4-381">O aplicativo também pode consultar o SDK de aplicativo do Intune para o status de um usuário registrado para determinar se o usuário deve ser impedido de acessar o conteúdo corporativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-381">The app can also query the Intune App SDK for the status of a registered user to determine if the user should be blocked from accessing corporate content.</span></span> <span data-ttu-id="749d4-382">Várias contas podem ser registradas para gerenciamento, mas, no momento, apenas uma conta pode ser registrada ativamente com o serviço APP-WE de cada vez.</span><span class="sxs-lookup"><span data-stu-id="749d4-382">Multiple accounts may be registered for management, but currently only one account can be actively enrolled with the APP-WE service at a time.</span></span> <span data-ttu-id="749d4-383">Isso significa que apenas uma conta no aplicativo pode receber a política de proteção do aplicativo de cada vez.</span><span class="sxs-lookup"><span data-stu-id="749d4-383">This means only one account on the app can receive app protection policy at a time.</span></span>

<span data-ttu-id="749d4-384">O aplicativo deve fornecer um retorno de chamada para adquirir o token de acesso apropriado do Azure Active Directory Authentication Library (ADAL) em nome do SDK.</span><span class="sxs-lookup"><span data-stu-id="749d4-384">The app is required to provide a callback to acquire the appropriate access token from the Azure Active Directory Authentication Library (ADAL) on behalf of the SDK.</span></span> <span data-ttu-id="749d4-385">Supõe-se que o aplicativo já use ADAL para autenticação do usuário e para adquirir os seus próprios tokens de acesso.</span><span class="sxs-lookup"><span data-stu-id="749d4-385">It is assumed that the app already uses ADAL for user authentication and to acquire its own access tokens.</span></span>

<span data-ttu-id="749d4-386">Quando o aplicativo remove completamente uma conta, ele deverá cancelar o registro dessa conta para indicar que o aplicativo não deve mais aplicar a política para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="749d4-386">When the app removes an account completely, it should unregister that account to indicate that the app should no longer apply policy for that user.</span></span> <span data-ttu-id="749d4-387">Se o usuário tiver sido inscrito no serviço de MAM, o usuário terá o registro cancelado e o aplicativo será apagado.</span><span class="sxs-lookup"><span data-stu-id="749d4-387">If the user was enrolled in the MAM service, the user will be unenrolled and the app will be wiped.</span></span>


### <span data-ttu-id="749d4-388">Visão geral dos requisitos de aplicativo</span><span class="sxs-lookup"><span data-stu-id="749d4-388">Overview of app requirements</span></span>
<a id="overview-of-app-requirements" class="xliff"></a>

<span data-ttu-id="749d4-389">Para implementar a integração APP-WE, seu aplicativo deverá registrar a conta de usuário com o SDK do MAM:</span><span class="sxs-lookup"><span data-stu-id="749d4-389">To implement APP-WE integration, your app must register the user account with the MAM SDK:</span></span>

1. <span data-ttu-id="749d4-390">O aplicativo _deve_ implementar e registrar uma instância da interface do `MAMServiceAuthenticationCallback`.</span><span class="sxs-lookup"><span data-stu-id="749d4-390">The app _must_ implement and register an instance of the `MAMServiceAuthenticationCallback` interface.</span></span> <span data-ttu-id="749d4-391">A instância de retorno de chamada deve ser registrada o mais cedo possível no ciclo de vida do aplicativo (normalmente no método `onMAMCreate()` da classe de aplicativo).</span><span class="sxs-lookup"><span data-stu-id="749d4-391">The callback instance should be registered as early as possible in the app's lifecycle (typically in the `onMAMCreate()` method of the application class).</span></span>

2. <span data-ttu-id="749d4-392">Quando uma conta de usuário é criada e o usuário entra com êxito com o ADAL, o aplicativo _deve_ chamar o `registerAccountForMAM()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-392">When a user account is created and the user successfully signs in with ADAL, the app _must_ call the `registerAccountForMAM()`.</span></span>

3. <span data-ttu-id="749d4-393">Quando uma conta de usuário tiver sido completamente removida, o aplicativo deverá chamar o `unregisterAccountForMAM()` para remover a conta do gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-393">When a user account is completely removed, the app should call `unregisterAccountForMAM()` to remove the account from Intune management.</span></span>

    > [!NOTE]
    > <span data-ttu-id="749d4-394">Se um usuário sair do aplicativo temporariamente, o aplicativo não precisará chamar o `unregisterAccountForMAM()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-394">If a user signs out of the app temporarily, the app does not need to call `unregisterAccountForMAM()`.</span></span> <span data-ttu-id="749d4-395">A chamada pode iniciar um apagamento para remover completamente os dados corporativos para o usuário.</span><span class="sxs-lookup"><span data-stu-id="749d4-395">The call may initiate a wipe to completely remove corporate data for the user.</span></span>


### <span data-ttu-id="749d4-396">MAMEnrollmentManager</span><span class="sxs-lookup"><span data-stu-id="749d4-396">MAMEnrollmentManager</span></span>
<a id="mamenrollmentmanager" class="xliff"></a>

<span data-ttu-id="749d4-397">Todas as APIs de registro e autenticação necessárias podem ser encontradas na interface do `MAMEnrollmentManager`.</span><span class="sxs-lookup"><span data-stu-id="749d4-397">All the necessary authentication and registration APIs can be found in the `MAMEnrollmentManager` interface.</span></span> <span data-ttu-id="749d4-398">Uma referência ao `MAMEnrollmentManager` pode ser obtida da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="749d4-398">A reference to the `MAMEnrollmentManager` can be obtained as follows:</span></span>

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

<span data-ttu-id="749d4-399">A instância do `MAMEnrollmentManager` retornada tem a garantia de não ser nula.</span><span class="sxs-lookup"><span data-stu-id="749d4-399">The `MAMEnrollmentManager` instance returned is guaranteed not to be null.</span></span> <span data-ttu-id="749d4-400">Os métodos de API enquadram-se em duas categorias: **autenticação** e **registro de conta**.</span><span class="sxs-lookup"><span data-stu-id="749d4-400">The API methods fall into two categories: **authentication** and **account registration**.</span></span>

> [!NOTE]
> <span data-ttu-id="749d4-401">O `MAMEnrollmentManager` contém alguns métodos de API que serão preteridos em breve.</span><span class="sxs-lookup"><span data-stu-id="749d4-401">`MAMEnrollmentManager` contains some API methods that will be deprecated soon.</span></span> <span data-ttu-id="749d4-402">Para maior clareza, somente os métodos relevantes e os códigos de resultado são mostrados no bloco de código abaixo.</span><span class="sxs-lookup"><span data-stu-id="749d4-402">For clarity, only the relevant methods and result codes are shown in the code block below.</span></span>

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <span data-ttu-id="749d4-403">Autenticação de conta</span><span class="sxs-lookup"><span data-stu-id="749d4-403">Account authentication</span></span>
<a id="account-authentication" class="xliff"></a>

<span data-ttu-id="749d4-404">Esta seção descreve os métodos de API de autenticação no `MAMEnrollmentManager` e como usá-los.</span><span class="sxs-lookup"><span data-stu-id="749d4-404">This section describes the authentication API methods in `MAMEnrollmentManager` and how to use them.</span></span>

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. <span data-ttu-id="749d4-405">O aplicativo deve implementar a interface do `MAMServiceAuthenticationCallback` para permitir que o SDK solicite um token do ADAL para o usuário e a ID de recurso determinados.</span><span class="sxs-lookup"><span data-stu-id="749d4-405">The app must implement the `MAMServiceAuthenticationCallback` interface to allow the SDK to request an ADAL token for the given user and resource ID.</span></span> <span data-ttu-id="749d4-406">A instância de retorno de chamada deve ser fornecida para o `MAMEnrollmentManager` chamando seu método `registerAuthenticationCallback()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-406">The callback instance must be provided to the `MAMEnrollmentManager` by calling its `registerAuthenticationCallback()` method.</span></span> <span data-ttu-id="749d4-407">Um token pode ser necessário muito cedo no ciclo de vida do aplicativo para as tentativas de registro ou check-ins de atualização periódica da política de proteção de aplicativo; portanto, é o lugar ideal para registrar o retorno de chamada no método `onMAMCreate()` da subclasse `MAMApplication` do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-407">A token may be needed very early in the app lifecycle for enrollment retries or app protection policy refresh check-ins, so the ideal place to register the callback is in the `onMAMCreate()` method of the app's `MAMApplication` subclass.</span></span>

2. <span data-ttu-id="749d4-408">O método `acquireToken()` deve adquirir o token de acesso para a ID de recurso solicitada para o usuário especificado.</span><span class="sxs-lookup"><span data-stu-id="749d4-408">The `acquireToken()` method should acquire the access token for the requested resource ID for the given user.</span></span> <span data-ttu-id="749d4-409">Se ele não puder adquirir o token solicitado, deverá retornar nulo.</span><span class="sxs-lookup"><span data-stu-id="749d4-409">If it can't acquire the requested token, it should return null.</span></span>

3. <span data-ttu-id="749d4-410">Caso o aplicativo seja capaz de fornecer um token quando o SDK chamar o `acquireToken()` – por exemplo, se houver falha de autenticação silenciosa e for um momento inconveniente para mostrar uma interface do usuário – o aplicativo poderá fornecer um token em um momento posterior chamando o método `updateToken()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-410">In case the app is unable to provide a token when the SDK calls `acquireToken()`  -- for example, if silent authentication fails and it is an inconvenient time to show a UI -- the app can provide a token at a later time by calling the `updateToken()` method.</span></span> <span data-ttu-id="749d4-411">O mesmo UPN, ID do AAD e ID de recursos que foram solicitados pela chamada anterior a `acquireToken()` devem ser passadas para o `updateToken()`, juntamente com o token que finalmente foi adquirido.</span><span class="sxs-lookup"><span data-stu-id="749d4-411">The same UPN, AAD ID, and resource ID that were requested by the prior call to `acquireToken()` must be passed to `updateToken()`, along with the token that was finally acquired.</span></span> <span data-ttu-id="749d4-412">O aplicativo deverá chamar esse método o mais rápido possível após retornar nulo do retorno de chamada fornecido.</span><span class="sxs-lookup"><span data-stu-id="749d4-412">The app should call this method as soon as possible after returning null from the provided callback.</span></span>

> [!NOTE]
> <span data-ttu-id="749d4-413">O SDK chamará `acquireToken()` periodicamente para obter o token, de modo que chamar `updateToken()` não seja estritamente necessário.</span><span class="sxs-lookup"><span data-stu-id="749d4-413">The SDK will call `acquireToken()` periodically to get the token, so calling `updateToken()` is not strictly required.</span></span> <span data-ttu-id="749d4-414">No entanto, isso é recomendável porque pode ajudar as inscrições e os check-ins de política de proteção de aplicativo serem concluídos de maneira oportuna.</span><span class="sxs-lookup"><span data-stu-id="749d4-414">However, it is recommended as it can help enrollments and app protection policy check-ins complete in a timely manner.</span></span>


### <span data-ttu-id="749d4-415">Registro de conta</span><span class="sxs-lookup"><span data-stu-id="749d4-415">Account registration</span></span>
<a id="account-registration" class="xliff"></a>

<span data-ttu-id="749d4-416">Esta seção descreve os métodos de API de registro de conta no `MAMEnrollmentManager` e como usá-los.</span><span class="sxs-lookup"><span data-stu-id="749d4-416">This section describes the account registration API methods in `MAMEnrollmentManager` and how to use them.</span></span>

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. <span data-ttu-id="749d4-417">Para registrar uma conta para gerenciamento, o aplicativo deverá chamar `registerAccountForMAM()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-417">To register an account for management, the app should call `registerAccountForMAM()`.</span></span> <span data-ttu-id="749d4-418">Uma conta de usuário é identificada por seu UPN e sua ID de usuário do AAD.</span><span class="sxs-lookup"><span data-stu-id="749d4-418">A user account is identified by both its UPN and its AAD user ID.</span></span> <span data-ttu-id="749d4-419">A ID do locatário também é necessária para associar os dados de registro ao locatário do AAD do usuário.</span><span class="sxs-lookup"><span data-stu-id="749d4-419">The tenant ID is also required to associate enrollment data with the user's AAD tenant.</span></span> <span data-ttu-id="749d4-420">O SDK pode tentar registrar o aplicativo para o usuário especificado no serviço do MAM; se o registro falhar, ele tentará registrar de novo periodicamente até que a conta tenha o registro cancelado.</span><span class="sxs-lookup"><span data-stu-id="749d4-420">The SDK may attempt to enroll the app for the given user in the MAM service; if enrollment fails, it will periodically retry enrollment until the account is unregistered.</span></span> <span data-ttu-id="749d4-421">Normalmente, o período de repetição será de 12-24 horas.</span><span class="sxs-lookup"><span data-stu-id="749d4-421">The retry period will typically be 12-24 hours.</span></span> <span data-ttu-id="749d4-422">O SDK fornece o status de tentativas de registro de forma assíncrona por meio de notificações.</span><span class="sxs-lookup"><span data-stu-id="749d4-422">The SDK provides the status of enrollment attempts asynchronously via notifications.</span></span>

2. <span data-ttu-id="749d4-423">Como a autenticação do AAD é necessária, o melhor momento para registrar a conta do usuário é depois que o usuário tiver entrado no aplicativo e tiver sido autenticado com êxito usando o ADAL.</span><span class="sxs-lookup"><span data-stu-id="749d4-423">Because AAD authentication is required, the best time to register the user account is after the user has signed into the app and is successfully authenticated using ADAL.</span></span>
    * <span data-ttu-id="749d4-424">A ID do AAD do usuário e a ID do locatário são retornadas da chamada de autenticação do ADAL como parte do objeto [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android).</span><span class="sxs-lookup"><span data-stu-id="749d4-424">The user's AAD ID and tenant ID are returned from the ADAL authentication call as part of the [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) object.</span></span> <span data-ttu-id="749d4-425">A ID do locatário é proveniente do método `AuthenticationResult.getTenantID()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-425">The tenant ID comes from the `AuthenticationResult.getTenantID()` method.</span></span>
    * <span data-ttu-id="749d4-426">As informações sobre o usuário encontram-se em um subobjeto do tipo `UserInfo` que vem do `AuthenticationResult.getUserInfo()` e a ID do usuário do AAD é recuperada do objeto chamando `UserInfo.getUserId()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-426">Information about the user is found in a sub-object of type `UserInfo` that comes from `AuthenticationResult.getUserInfo()`, and the AAD user ID is retrieved from that object by calling `UserInfo.getUserId()`.</span></span>

3. <span data-ttu-id="749d4-427">Para cancelar o registro de uma conta do gerenciamento do Intune, o aplicativo deverá chamar `unregisterAccountForMAM()`.</span><span class="sxs-lookup"><span data-stu-id="749d4-427">To unregister an account from Intune management, the app should call `unregisterAccountForMAM()`.</span></span> <span data-ttu-id="749d4-428">Se a conta tiver sido registrada com êxito e for gerenciada, o SDK cancelará o registro da conta e apagará seus dados.</span><span class="sxs-lookup"><span data-stu-id="749d4-428">If the account has been successfully enrolled and is managed, the SDK will unenroll the account and wipe its data.</span></span> <span data-ttu-id="749d4-429">As tentativas periódicas de registro para a conta serão interrompidas.</span><span class="sxs-lookup"><span data-stu-id="749d4-429">Periodic enrollment retries for the account will be stopped.</span></span> <span data-ttu-id="749d4-430">O SDK fornece o status da solicitação de cancelamento de registro de forma assíncrona por meio de notificações.</span><span class="sxs-lookup"><span data-stu-id="749d4-430">The SDK provides the status of unenrollment request asynchronously via notifications.</span></span>

### <span data-ttu-id="749d4-431">Notas importantes da implementação</span><span class="sxs-lookup"><span data-stu-id="749d4-431">Important implementation notes</span></span>
<a id="important-implementation-notes" class="xliff"></a>

#### <span data-ttu-id="749d4-432">Autenticação</span><span class="sxs-lookup"><span data-stu-id="749d4-432">Authentication</span></span>
<a id="authentication" class="xliff"></a>

* <span data-ttu-id="749d4-433">Quando o aplicativo chamar `registerAccountForMAM()`, ele poderá receber um retorno de chamada em sua interface do `MAMServiceAuthenticationCallback` logo em seguida em um thread diferente.</span><span class="sxs-lookup"><span data-stu-id="749d4-433">When the app calls `registerAccountForMAM()`, it may receive a callback on its `MAMServiceAuthenticationCallback` interface shortly thereafter, on a different thread.</span></span> <span data-ttu-id="749d4-434">Idealmente, o aplicativo adquiriu seu próprio token do ADAL antes de registrar a conta para agilizar a aquisição do **token MAMService**.</span><span class="sxs-lookup"><span data-stu-id="749d4-434">Ideally, the app acquired its own token from ADAL prior to registering the account to expedite the acquisition of the **MAMService token**.</span></span> <span data-ttu-id="749d4-435">Se o aplicativo retornar um token válido do retorno de chamada, o registro continuará e o aplicativo obterá o resultado final por meio de uma notificação.</span><span class="sxs-lookup"><span data-stu-id="749d4-435">IF the app returns a valid token from the callback, enrollment will proceed and the app will get the final result via a notification.</span></span>

* <span data-ttu-id="749d4-436">Se o aplicativo não retornar um token válido do AAD, o resultado final da tentativa de registro será `AUTHENTICATION_NEEDED`.</span><span class="sxs-lookup"><span data-stu-id="749d4-436">If the app doesn't return a valid AAD token, the final result from the enrollment attempt will be `AUTHENTICATION_NEEDED`.</span></span> <span data-ttu-id="749d4-437">Se o aplicativo recebe esse resultado por meio de notificação, ele poderá agilizar o processo de registro adquirindo o **token MAMService** e chamar o método `updateToken()` para iniciar o processo de registro novamente.</span><span class="sxs-lookup"><span data-stu-id="749d4-437">If the app receives this Result via notification, it can expedite the enrollment process by acquiring the **MAMService token** and calling the `updateToken()` method to initiate the enrollment process again.</span></span> <span data-ttu-id="749d4-438">Isso _não_ é um requisito sólido; no entanto, como o SDK tenta realizar o registro periodicamente, ele invoca o retorno de chamada para adquirir o token.</span><span class="sxs-lookup"><span data-stu-id="749d4-438">This is _not_ a firm requirement, however, since the SDK retries enrollment periodically and invokes the callback to acquire the token.</span></span>

* <span data-ttu-id="749d4-439">O `MAMServiceAuthenticationCallback` registrado do aplicativo também será chamado para adquirir um token para check-ins de atualização periódica da política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-439">The app's registered `MAMServiceAuthenticationCallback` will also be called to acquire a token for periodic app protection policy refresh check-ins.</span></span> <span data-ttu-id="749d4-440">Se o aplicativo não for capaz de fornecer um token quando solicitado, ele não receberá uma notificação, mas deverá tentar adquirir um token e chamar o `updateToken()` no próximo horário conveniente para agilizar o processo de check-in.</span><span class="sxs-lookup"><span data-stu-id="749d4-440">If the app is unable to provide a token when requested, it will not get a notification, but it should attempt to acquire a token and call `updateToken()` at the next convenient time to expedite the check-in process.</span></span> <span data-ttu-id="749d4-441">Se não for fornecido um token, o retorno de chamada ainda será chamado na próxima tentativa de check-in.</span><span class="sxs-lookup"><span data-stu-id="749d4-441">If a token is not provided, the callback will still be called at the next check-in attempt.</span></span>

#### <span data-ttu-id="749d4-442">Registro</span><span class="sxs-lookup"><span data-stu-id="749d4-442">Registration</span></span>
<a id="registration" class="xliff"></a>

* <span data-ttu-id="749d4-443">Para sua conveniência, os métodos de registro são imutáveis; por exemplo, `registerAccountForMAM()` registrará somente uma conta e tentará registrar o aplicativo se a conta não estiver registrada, e `unregisterAccountForMAM()` apenas cancelará uma conta se ela estiver registrada.</span><span class="sxs-lookup"><span data-stu-id="749d4-443">For your convenience, the registration methods are idempotent; for example, `registerAccountForMAM()`will only register an account and attempt to enroll the app if the account is not already registered, and `unregisterAccountForMAM()` will only unregister an account if it is currently registered.</span></span> <span data-ttu-id="749d4-444">As chamadas subsequentes são não operacionais; portanto, não há prejuízo em chamar esses métodos mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="749d4-444">Subsequent calls are no-ops, so there is no harm in calling these methods more than once.</span></span> <span data-ttu-id="749d4-445">Além disso, a correspondência entre chamadas para esses métodos e as notificações de resultados não são garantidas: por exemplo, se `registerAccountForMAM` for chamado para uma identidade que já esteja registrada, a notificação poderá não ser enviada novamente para essa identidade.</span><span class="sxs-lookup"><span data-stu-id="749d4-445">Additionally, correspondence between calls to these methods and notifications of results are not guaranteed: i.e. if `registerAccountForMAM` is called for an identity that is already registered, the notification may not be sent again for that identity.</span></span> <span data-ttu-id="749d4-446">É possível que as notificações sejam enviadas sem corresponderem a todas as chamadas para esses métodos, porque o SDK pode periodicamente tentar inscrições em segundo plano e os cancelamentos de registro podem ser disparados por solicitações de apagamento recebidas do serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-446">It is possible that notifications are sent that don't correspond to any calls to these methods, since the SDK may periodically try enrollments in the background, and unenrollments may be triggered by wipe requests received from the Intune service.</span></span>

* <span data-ttu-id="749d4-447">Os métodos de registro podem ser chamados para qualquer número de identidades diferentes, mas atualmente apenas uma conta de usuário pode ser registrada com êxito.</span><span class="sxs-lookup"><span data-stu-id="749d4-447">The registration methods can be called for any number of different identities, but currently only one user account can become successfully enrolled.</span></span> <span data-ttu-id="749d4-448">Se várias contas de usuário que são licenciadas para o Intune e afetadas pela política de proteção do aplicativo forem registradas ao mesmo tempo ou quase simultaneamente, não há nenhuma garantia de qual ganhará a corrida.</span><span class="sxs-lookup"><span data-stu-id="749d4-448">If multiple user accounts that are licensed for Intune and targeted by app protection policy are registered at or near the same time, there is no guarantee on which one will win the race.</span></span>

* <span data-ttu-id="749d4-449">Por fim, você pode consultar o `MAMEnrollmentManager` para ver se uma conta específica está registrada e para obter seu status atual usando o método `getRegisteredAccountStatus`.</span><span class="sxs-lookup"><span data-stu-id="749d4-449">Finally, you can query the `MAMEnrollmentManager` to see if a particular account is registered and to get its current status using the `getRegisteredAccountStatus` method.</span></span> <span data-ttu-id="749d4-450">Se a conta fornecida não estiver registrada, esse método retornará **nulo**.</span><span class="sxs-lookup"><span data-stu-id="749d4-450">If the provided account is not registered, this method will return **null**.</span></span> <span data-ttu-id="749d4-451">Se a conta estiver registrada, esse método retornará o status da conta como um dos membros da enumeração `MAMEnrollmentManager.Result`.</span><span class="sxs-lookup"><span data-stu-id="749d4-451">If the account is registered, this method will return the account's status as one of the members of the `MAMEnrollmentManager.Result` enumeration.</span></span>

### <span data-ttu-id="749d4-452">Resultado e códigos de status</span><span class="sxs-lookup"><span data-stu-id="749d4-452">Result and status codes</span></span>
<a id="result-and-status-codes" class="xliff"></a>

<span data-ttu-id="749d4-453">Quando uma conta é registrada pela primeira vez, ela começa no estado `PENDING`, indicando que a tentativa inicial de registro de serviço do MAM está incompleta.</span><span class="sxs-lookup"><span data-stu-id="749d4-453">When an account is first registered, it begins in the `PENDING` state, indicating that the initial MAM service enrollment attempt is incomplete.</span></span> <span data-ttu-id="749d4-454">Após a tentativa de registro terminar, uma notificação será enviada com um dos códigos de resultado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="749d4-454">After the enrollment attempt finishes, a notification will be sent with one of the Result codes in the table below.</span></span> <span data-ttu-id="749d4-455">Além disso, o método `getRegisteredAccountStatus()` retornará o status da conta para que o aplicativo sempre possa determinar se o acesso ao conteúdo corporativo é bloqueado para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="749d4-455">In addition, the `getRegisteredAccountStatus()` method will return the account's status so the app can always determine if access to corporate content is blocked for that user.</span></span> <span data-ttu-id="749d4-456">Se a tentativa de registro falhar, o status da conta poderá mudar ao longo do tempo como o registro de novas tentativas do SDK no plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="749d4-456">If the enrollment attempt fails, the account's status may change over time as the SDK retries enrollment in the background.</span></span>

|<span data-ttu-id="749d4-457">Código de Resultado</span><span class="sxs-lookup"><span data-stu-id="749d4-457">Result code</span></span> | <span data-ttu-id="749d4-458">Explicação</span><span class="sxs-lookup"><span data-stu-id="749d4-458">Explanation</span></span> |
| -- | -- |
|<span data-ttu-id="749d4-459">AUTHORIZATION_NEEDED</span><span class="sxs-lookup"><span data-stu-id="749d4-459">AUTHORIZATION_NEEDED</span></span> | <span data-ttu-id="749d4-460">Esse resultado indica que um token não foi fornecido pela instância `MAMServiceAuthenticationCallback` registrada do aplicativo ou o token fornecido era inválido.</span><span class="sxs-lookup"><span data-stu-id="749d4-460">This result indicates that a token was not provided by the app’s registered `MAMServiceAuthenticationCallback` instance, or the provided token was invalid.</span></span>  <span data-ttu-id="749d4-461">O aplicativo deve adquirir um token válido e chamar `updateToken()` se for possível.</span><span class="sxs-lookup"><span data-stu-id="749d4-461">The app should acquire a valid token and call `updateToken()` if possible.</span></span> |
| <span data-ttu-id="749d4-462">NOT_LICENSED</span><span class="sxs-lookup"><span data-stu-id="749d4-462">NOT_LICENSED</span></span> | <span data-ttu-id="749d4-463">O usuário não está licenciado para o Intune ou a tentativa de contatar o serviço MAM do Intune falhou.</span><span class="sxs-lookup"><span data-stu-id="749d4-463">The user is not licensed for Intune, or the attempt to contact the Intune MAM service failed.</span></span>  <span data-ttu-id="749d4-464">O aplicativo deve continuar em um estado não gerenciado (normal) e o usuário não deve estar bloqueado.</span><span class="sxs-lookup"><span data-stu-id="749d4-464">The app should continue in an unmanaged (normal) state and the user should not be blocked.</span></span>  <span data-ttu-id="749d4-465">Os registros serão repetidos periodicamente caso o usuário se torne licenciado no futuro.</span><span class="sxs-lookup"><span data-stu-id="749d4-465">Enrollments will be retried periodically in case the user becomes licensed in the future.</span></span> |
| <span data-ttu-id="749d4-466">ENROLLMENT_SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="749d4-466">ENROLLMENT_SUCCEEDED</span></span> | <span data-ttu-id="749d4-467">A tentativa de registro teve êxito ou o usuário já está registrado.</span><span class="sxs-lookup"><span data-stu-id="749d4-467">The enrollment attempt succeeded, or the user is already enrolled.</span></span>  <span data-ttu-id="749d4-468">No caso de um registro bem-sucedido, uma notificação de atualização de política será enviada antes dessa notificação.</span><span class="sxs-lookup"><span data-stu-id="749d4-468">In the case of a successful enrollment, a policy refresh notification will be sent before this notification.</span></span>  <span data-ttu-id="749d4-469">O acesso a dados corporativos deve ser permitido.</span><span class="sxs-lookup"><span data-stu-id="749d4-469">Access to corporate data should be allowed.</span></span> |
| <span data-ttu-id="749d4-470">ENROLLMENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="749d4-470">ENROLLMENT_FAILED</span></span> | <span data-ttu-id="749d4-471">Falha na tentativa de registro.</span><span class="sxs-lookup"><span data-stu-id="749d4-471">The enrollment attempt failed.</span></span>  <span data-ttu-id="749d4-472">Detalhes adicionais podem ser encontrados nos logs do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-472">Further details can be found in the device logs.</span></span>  <span data-ttu-id="749d4-473">O aplicativo não deve permitir o acesso corporativo nesse estado, porque anteriormente foi determinado que o usuário estava licenciado para o Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-473">The app should not allow access to corporate in this state, since it was previously determined that the user is licensed for Intune.</span></span>|
| <span data-ttu-id="749d4-474">WRONG_USER</span><span class="sxs-lookup"><span data-stu-id="749d4-474">WRONG_USER</span></span> | <span data-ttu-id="749d4-475">Somente um usuário por dispositivo pode registrar um aplicativo com o serviço do MAM.</span><span class="sxs-lookup"><span data-stu-id="749d4-475">Only one user per device can enroll an app with the MAM service.</span></span>  <span data-ttu-id="749d4-476">Para registrar com êxito como um usuário diferente, todos os aplicativos registrados deverão ter o registro cancelado primeiro.</span><span class="sxs-lookup"><span data-stu-id="749d4-476">In order to enroll successfully as a different user, all enrolled apps must be unenrolled first.</span></span>  <span data-ttu-id="749d4-477">Caso contrário, esse aplicativo deverá ser registrado como o usuário principal.</span><span class="sxs-lookup"><span data-stu-id="749d4-477">Otherwise, this app must enroll as the primary user.</span></span>  <span data-ttu-id="749d4-478">Essa verificação ocorre após a verificação da licença, então o usuário deve ser impedido de acessar dados corporativos até que o aplicativo seja registrado com êxito.</span><span class="sxs-lookup"><span data-stu-id="749d4-478">This check happens after the license check, so the user should be blocked from accessing corporate data until the app is successfully enrolled.</span></span>|
| <span data-ttu-id="749d4-479">UNENROLLMENT_SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="749d4-479">UNENROLLMENT_SUCCEEDED</span></span> | <span data-ttu-id="749d4-480">O cancelamento do registro foi realizado com sucesso.</span><span class="sxs-lookup"><span data-stu-id="749d4-480">Unenrollment was successful.</span></span>|
| <span data-ttu-id="749d4-481">UNENROLLMENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="749d4-481">UNENROLLMENT_FAILED</span></span> | <span data-ttu-id="749d4-482">Houve falha na solicitação de cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="749d4-482">The unenrollment request failed.</span></span>  <span data-ttu-id="749d4-483">Detalhes adicionais podem ser encontrados nos logs do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-483">Further details can be found in the device logs.</span></span> |
| <span data-ttu-id="749d4-484">PENDING</span><span class="sxs-lookup"><span data-stu-id="749d4-484">PENDING</span></span> | <span data-ttu-id="749d4-485">A tentativa de registro inicial para o usuário está em andamento.</span><span class="sxs-lookup"><span data-stu-id="749d4-485">The initial enrollment attempt for the user is in progress.</span></span>  <span data-ttu-id="749d4-486">O aplicativo pode bloquear o acesso a dados corporativos até que o resultado do registro seja conhecido, mas não é obrigado a fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="749d4-486">The app can block access to corporate data until the enrollment result is known, but is not required to do so.</span></span> |
| <span data-ttu-id="749d4-487">COMPANY_PORTAL_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="749d4-487">COMPANY_PORTAL_REQUIRED</span></span> | <span data-ttu-id="749d4-488">O usuário é licenciado para o Intune, mas o aplicativo não pode ser registrado até que o aplicativo do Portal da Empresa esteja instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-488">The user is licensed for Intune, but the app cannot be enrolled until the Company Portal app is installed on the device.</span></span> <span data-ttu-id="749d4-489">O SDK do aplicativo do Intune tenta bloquear o acesso ao aplicativo para determinado usuário e o direciona para instalar o aplicativo do Portal da Empresa (veja abaixo para obter detalhes).</span><span class="sxs-lookup"><span data-stu-id="749d4-489">The Intune App SDK will attempt to block access to the app for the given user and direct them to install the Company Portal app (see below for details).</span></span> |


### <span data-ttu-id="749d4-490">Substituição do prompt de requisito do Portal da Empresa (opcional)</span><span class="sxs-lookup"><span data-stu-id="749d4-490">Company Portal requirement prompt override (optional)</span></span>
<a id="company-portal-requirement-prompt-override-optional" class="xliff"></a>

<span data-ttu-id="749d4-491">Se o resultado de `COMPANY_PORTAL_REQUIRED` for recebido, o SDK bloqueará o uso de atividades que usam a identidade para a qual o registro foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="749d4-491">If the `COMPANY_PORTAL_REQUIRED` Result is received, the SDK will block use of activities that use the identity for which enrollment was requested.</span></span> <span data-ttu-id="749d4-492">Em vez disso, o SDK fará essas atividades exibirem um prompt para baixar o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="749d4-492">Instead, the SDK will cause those activities to display a prompt to download the Company Portal.</span></span> <span data-ttu-id="749d4-493">Se você quiser impedir esse comportamento em seu aplicativo, as atividades poderão implementar o `MAMActivity.onMAMCompanyPortalRequired`.</span><span class="sxs-lookup"><span data-stu-id="749d4-493">If you want to prevent this behavior in your app, activities may implement `MAMActivity.onMAMCompanyPortalRequired`.</span></span>

<span data-ttu-id="749d4-494">Esse método é chamado antes que o SDK exiba sua interface de usuário de bloqueio padrão.</span><span class="sxs-lookup"><span data-stu-id="749d4-494">This method is called before the SDK displays its default blocking UI.</span></span> <span data-ttu-id="749d4-495">Se o aplicativo alterar a identidade da atividade ou cancelar o registro do usuário que tentou registrar, o SDK não bloqueará a atividade.</span><span class="sxs-lookup"><span data-stu-id="749d4-495">If the app changes the activity identity or unregisters the user who attempted to enroll, the SDK will not block the activity.</span></span> <span data-ttu-id="749d4-496">Nessa situação, depende do aplicativo evitar o vazamento de dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="749d4-496">In this situation, it is up to the app to avoid leaking corporate data.</span></span>

### <span data-ttu-id="749d4-497">Notificações</span><span class="sxs-lookup"><span data-stu-id="749d4-497">Notifications</span></span>
<a id="notifications" class="xliff"></a>

<span data-ttu-id="749d4-498">Um novo tipo de `MAMNotification` foi adicionado para informar ao aplicativo que a solicitação de registro foi concluída.</span><span class="sxs-lookup"><span data-stu-id="749d4-498">A new type of `MAMNotification` has been added in order to inform the app that the enrollment request has completed.</span></span>  <span data-ttu-id="749d4-499">O `MAMEnrollmentNotification` será recebido por meio da interface do `MAMNotificationReceiver` conforme descrito na seção [Registrar-se para notificações do SDK](#register-for-notifications-from-the-sdk).</span><span class="sxs-lookup"><span data-stu-id="749d4-499">The `MAMEnrollmentNotification` will be received through the `MAMNotificationReceiver` interface as described in the [Register for notifications from the SDK](#register-for-notifications-from-the-sdk) section.</span></span>

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

<span data-ttu-id="749d4-500">O método `getEnrollmentResult()` retorna o resultado da solicitação de registro.</span><span class="sxs-lookup"><span data-stu-id="749d4-500">The `getEnrollmentResult()` method returns the result of the enrollment request.</span></span>  <span data-ttu-id="749d4-501">Como o `MAMEnrollmentNotification` estende o `MAMUserNotification`, a identidade do usuário para o qual o registro foi tentado também está disponível.</span><span class="sxs-lookup"><span data-stu-id="749d4-501">Since `MAMEnrollmentNotification` extends `MAMUserNotification`, the identity of the user for whom the enrollment was attempted is also available.</span></span> <span data-ttu-id="749d4-502">O aplicativo deve implementar a interface do `MAMNotificationReceiver` para receber essas notificações que estão detalhadas na seção [Registrar-se para notificações do SDK](#Register-for-notifications-from-the-SDK).</span><span class="sxs-lookup"><span data-stu-id="749d4-502">The app must implement the `MAMNotificationReceiver` interface to receive these notifications, detailed in the [Register for notifications from the SDK](#Register-for-notifications-from-the-SDK) section.</span></span>

<span data-ttu-id="749d4-503">O status da conta de usuário registrado poderá ser alterado quando um registro de notificação for recebido, mas não será alterada em alguns casos (por exemplo, se a notificação do `AUTHORIZATION_NEEDED` for recebida após um resultado mais informativo como `WRONG_USER`, o resultado mais informativo será mantido como o status da conta)</span><span class="sxs-lookup"><span data-stu-id="749d4-503">The registered user account's status may change when an enrollment notification is received, but it will not change in some cases (e.g. if `AUTHORIZATION_NEEDED` notification is received after a more informative result such as `WRONG_USER`, the more informative result will be maintained as the account's status)</span></span>


## <span data-ttu-id="749d4-504">Proteção de dados de backup</span><span class="sxs-lookup"><span data-stu-id="749d4-504">Protecting Backup data</span></span>
<a id="protecting-backup-data" class="xliff"></a>

<span data-ttu-id="749d4-505">A partir do Android Marshmallow (API 23), o Android tem duas formas para um aplicativo fazer backup de seus dados.</span><span class="sxs-lookup"><span data-stu-id="749d4-505">As of Android Marshmallow (API 23), Android has two ways for an app to back up its data.</span></span> <span data-ttu-id="749d4-506">Cada opção está disponível para seu aplicativo e requer etapas diferentes para garantir que a proteção de dados do Intune seja implementada corretamente.</span><span class="sxs-lookup"><span data-stu-id="749d4-506">Each option is available to your app and requires different steps to ensure that Intune data protection is correctly implemented.</span></span> <span data-ttu-id="749d4-507">Examine a tabela abaixo para ver as ações correspondentes necessárias para o comportamento correto de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="749d4-507">You can review the table below on corresponding actions required for correct data protection behavior.</span></span>  <span data-ttu-id="749d4-508">Leia mais sobre os métodos de backup no [Guia da API do Android](http://developer.android.com/guide/topics/data/backup.html).</span><span class="sxs-lookup"><span data-stu-id="749d4-508">You can read more about the backup methods in the [Android API guide](http://developer.android.com/guide/topics/data/backup.html).</span></span>

### <span data-ttu-id="749d4-509">Backup automático de aplicativos</span><span class="sxs-lookup"><span data-stu-id="749d4-509">Auto Backup for Apps</span></span>
<a id="auto-backup-for-apps" class="xliff"></a>

<span data-ttu-id="749d4-510">O Android começou a oferecer [backups completos automáticos](https://developer.android.com/guide/topics/data/autobackup.html) para o Google Drive para aplicativos em dispositivos Android Marshmallow, independentemente da API de destino do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-510">Android began offering [automatic full backups](https://developer.android.com/guide/topics/data/autobackup.html) to Google Drive for apps on Android Marshmallow devices, regardless of the app's target API.</span></span> <span data-ttu-id="749d4-511">Em seu AndroidManifest.xml, se você definir explicitamente `android:allowBackup` como **false**, seu aplicativo nunca será enfileirado para backups pelo Android e os dados "corporativos" permanecerão no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-511">In your AndroidManifest.xml, if you explicitly set `android:allowBackup` to **false**, then your app will never be queued for backups by Android and "corporate" data will stay within the app.</span></span> <span data-ttu-id="749d4-512">Nesse caso, nenhuma ação adicional é necessária.</span><span class="sxs-lookup"><span data-stu-id="749d4-512">In this case, no further action is necessary.</span></span>

<span data-ttu-id="749d4-513">No entanto, por padrão, o atributo `android:allowBackup` é definido como true, mesmo que `android:allowBackup` não esteja especificado no arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="749d4-513">However, by default the `android:allowBackup` attribute is set to true, even if `android:allowBackup` isn't specified in the manifest file.</span></span> <span data-ttu-id="749d4-514">Isso significa que todos os dados do aplicativo são copiados automaticamente para a conta do Google Drive do usuário, um comportamento padrão que representa um **risco de vazamento de dados**.</span><span class="sxs-lookup"><span data-stu-id="749d4-514">This means all app data is automatically backed up to the user's Google Drive account, a default behavior that poses a **data leak risk**.</span></span> <span data-ttu-id="749d4-515">Portanto, o SDK requer as alterações descritas na tabela a seguir para garantir que a proteção de dados seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="749d4-515">Therefore, the SDK requires the changes outlined below to ensure that data protection is applied.</span></span>  <span data-ttu-id="749d4-516">É importante seguir as diretrizes abaixo para proteger os dados do cliente corretamente se você quiser que seu aplicativo seja executado em dispositivos Android Marshmallow.</span><span class="sxs-lookup"><span data-stu-id="749d4-516">It is important to follow the guidelines  below to protect customer data properly if you want your app to run on Android Marshmallow devices.</span></span>  

<span data-ttu-id="749d4-517">O Intune permite que você utilize todos os [recursos de Backup Automático](https://developer.android.com/guide/topics/data/autobackup.html) disponíveis no Android, incluindo a capacidade de definir regras personalizadas no XML, mas você precisa seguir as etapas abaixo para proteger seus dados:</span><span class="sxs-lookup"><span data-stu-id="749d4-517">Intune allows you to utilize all the [Auto Backup features](https://developer.android.com/guide/topics/data/autobackup.html) available from Android, including the ability to define custom rules in XML, but you must follow the steps below to secure your data:</span></span>

1. <span data-ttu-id="749d4-518">Se seu aplicativo **não** usar seu próprio BackupAgent, use o MAMBackupAgent padrão para permitir backups completos automáticos que estejam em conformidade com a política do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-518">If your app does **not** use its own custom BackupAgent, use the default MAMBackupAgent to allow for automatic full backups that are Intune policy compliant.</span></span> <span data-ttu-id="749d4-519">Se você fizer isso, poderá ignorar o atributo do manifesto `android:fullBackupOnly`, pois ele não será aplicável para nosso agente de backup.</span><span class="sxs-lookup"><span data-stu-id="749d4-519">If you do this, you can ignore the `android:fullBackupOnly` manifest attribute, as it’s not applicable for our backup agent.</span></span> <span data-ttu-id="749d4-520">Coloque o seguinte no manifesto do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="749d4-520">Place the following in the app manifest:</span></span>

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```

2. <span data-ttu-id="749d4-521">**[Opcional]**  Se você tiver implementado um BackupAgent personalizado opcional, precisará usar MAMBackupAgent ou MAMBackupAgentHelper.</span><span class="sxs-lookup"><span data-stu-id="749d4-521">**[Optional]** If you implemented an optional custom BackupAgent, you need to make sure to use MAMBackupAgent or MAMBackupAgentHelper.</span></span> <span data-ttu-id="749d4-522">Confira as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="749d4-522">See the following sections.</span></span> <span data-ttu-id="749d4-523">Use o **MAMDefaultFullBackupAgent** do Intune (descrito na etapa 1), que fornece backup fácil no Android M e superior.</span><span class="sxs-lookup"><span data-stu-id="749d4-523">Consider switching to using Intune's **MAMDefaultFullBackupAgent** (described in step 1) which provides easy back up on Android M and above.</span></span>

3. <span data-ttu-id="749d4-524">Quando decidir qual tipo de backup completo seu aplicativo deve receber (filtrado, não filtrado ou nenhum), você precisará definir o atributo `android:fullBackupContent` como true, false ou um recurso XML em seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-524">When you decide which type of full backup your app should receive (unfiltered, filtered, or none) you'll need to set the attribute `android:fullBackupContent`  to true, false, or an XML resource in your app.</span></span>

4. <span data-ttu-id="749d4-525">Em seguida, você _**deve**_ copiar tudo o que colocar no `android:fullBackupContent` em uma marca de metadados chamada `com.microsoft.intune.mam.FullBackupContent` no manifesto.</span><span class="sxs-lookup"><span data-stu-id="749d4-525">Then, you _**must**_ copy whatever you put into `android:fullBackupContent` into a metadata tag named `com.microsoft.intune.mam.FullBackupContent` in the manifest.</span></span>

    <span data-ttu-id="749d4-526">**Exemplo 1**: se você quiser que seu aplicativo tenha backups completos sem exclusões, defina o atributo `android:fullBackupContent` e a marca de metadados `com.microsoft.intune.mam.FullBackupContent` como **true**:</span><span class="sxs-lookup"><span data-stu-id="749d4-526">**Example 1**: If you want your app to have full backups without exclusions, set both the `android:fullBackupContent` attribute and `com.microsoft.intune.mam.FullBackupContent` metadata tag to **true**:</span></span>

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    <span data-ttu-id="749d4-527">**Exemplo 2**: se você quiser que seu aplicativo use seu BackupAgent personalizado e recuse backups automáticos completos compatíveis com a política do Intune, defina o atributo e a marca de metadados como **false**:</span><span class="sxs-lookup"><span data-stu-id="749d4-527">**Example 2**: If you want your app to use its custom BackupAgent and opt out of full, Intune policy compliant, automatic backups, you must set the attribute and metadata tag to **false**:</span></span>

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    <span data-ttu-id="749d4-528">**Exemplos 3**: se você quiser que seu aplicativo tenha backups completos de acordo com suas regras personalizadas definidas em um arquivo XML, defina o atributo e a marca de metadados como o mesmo recurso de XML:</span><span class="sxs-lookup"><span data-stu-id="749d4-528">**Example 3**: If you want your app to have full backups according to your custom rules defined in an XML file, please set the attribute and metadata tag to the same XML resource:</span></span>

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <span data-ttu-id="749d4-529">Backups de chave/valor</span><span class="sxs-lookup"><span data-stu-id="749d4-529">Key/Value Backup</span></span>
<a id="keyvalue-backup" class="xliff"></a>

<span data-ttu-id="749d4-530">A opção [Backup de chave/valor](https://developer.android.com/guide/topics/data/keyvaluebackup.html) está disponível para todas as APIs acima de 8 e carrega dados do aplicativo para o [Serviço de Backup do Android](https://developer.android.com/google/backup/index.html).</span><span class="sxs-lookup"><span data-stu-id="749d4-530">The [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) option is available to all APIs 8+ and uploads app data to the [Android Backup Service](https://developer.android.com/google/backup/index.html).</span></span> <span data-ttu-id="749d4-531">A quantidade de dados por usuário de seu aplicativo é limitada a 5MB.</span><span class="sxs-lookup"><span data-stu-id="749d4-531">The amount of data per user of your app is limited to 5MB.</span></span> <span data-ttu-id="749d4-532">Se você usar o Backup de chave/valor, deverá usar um **BackupAgentHelper** ou **BackupAgent**.</span><span class="sxs-lookup"><span data-stu-id="749d4-532">If you use Key/Value Backup, you must use a **BackupAgentHelper** or a **BackupAgent**.</span></span>

### <span data-ttu-id="749d4-533">BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-533">BackupAgentHelper</span></span>
<a id="backupagenthelper" class="xliff"></a>

<span data-ttu-id="749d4-534">O BackupAgentHelper é mais simples de implementar do que o BackupAgent em termos de funcionalidade nativa do Android e integração de MAM do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-534">BackupAgentHelper is easier to implement than BackupAgent both in terms of native Android functionality and Intune MAM integration.</span></span> <span data-ttu-id="749d4-535">O BackupAgentHelper permite que o desenvolvedor registre arquivos inteiros e preferências compartilhadas com um **FileBackupHelper** e **SharedPreferencesBackupHelper** (respectivamente), que são adicionados ao BackupAgentHelper no momento da criação.</span><span class="sxs-lookup"><span data-stu-id="749d4-535">BackupAgentHelper allows the developer to register entire files and shared preferences to a **FileBackupHelper** and **SharedPreferencesBackupHelper** (respectively) which are then added to the BackupAgentHelper upon creation.</span></span> <span data-ttu-id="749d4-536">Siga as etapas abaixo para usar um BackupAgentHelper com o MAM do Intune:</span><span class="sxs-lookup"><span data-stu-id="749d4-536">Follow the steps below to use a BackupAgentHelper with Intune MAM:</span></span>

1. <span data-ttu-id="749d4-537">Para utilizar o backup de várias identidades com um BackupAgentHelper, siga o guia do Android para [Estendendo o BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).</span><span class="sxs-lookup"><span data-stu-id="749d4-537">To utilize multi-identity backup with a BackupAgentHelper, follow the Android guide to [Extending BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).</span></span>

2. <span data-ttu-id="749d4-538">Faça a sua classe estender o equivalente do MAM a BackupAgentHelper, FileBackupHelper e SharedPreferencesBackupHelper.</span><span class="sxs-lookup"><span data-stu-id="749d4-538">Have your class extend the MAM equivalent of BackupAgentHelper, FileBackupHelper, and SharedPreferencesBackupHelper.</span></span>

|<span data-ttu-id="749d4-539">Classe do Android</span><span class="sxs-lookup"><span data-stu-id="749d4-539">Android class</span></span> | <span data-ttu-id="749d4-540">Equivalente do MAM</span><span class="sxs-lookup"><span data-stu-id="749d4-540">MAM equivalent</span></span> |
|--|--|
|<span data-ttu-id="749d4-541">BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-541">BackupAgentHelper</span></span> |<span data-ttu-id="749d4-542">MAMBackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-542">MAMBackupAgentHelper</span></span> |
|<span data-ttu-id="749d4-543">FileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-543">FileBackupHelper</span></span> | <span data-ttu-id="749d4-544">MAMFileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-544">MAMFileBackupHelper</span></span>
|<span data-ttu-id="749d4-545">SharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-545">SharedPreferencesBackupHelper</span></span>| <span data-ttu-id="749d4-546">MAMSharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="749d4-546">MAMSharedPreferencesBackupHelper</span></span>|

<span data-ttu-id="749d4-547">As diretrizes a seguir levam a um backup e uma restauração bem-sucedidos de várias identidades.</span><span class="sxs-lookup"><span data-stu-id="749d4-547">Following these guidelines will lead to a successful multi-identity backup and restore.</span></span>

### <span data-ttu-id="749d4-548">BackupAgent</span><span class="sxs-lookup"><span data-stu-id="749d4-548">BackupAgent</span></span>
<a id="backupagent" class="xliff"></a>

<span data-ttu-id="749d4-549">O BackupAgent permite que você seja muito mais explícito sobre de quais dados é feito backup.</span><span class="sxs-lookup"><span data-stu-id="749d4-549">A BackupAgent allows you to be much more explicit about what data is backed up.</span></span> <span data-ttu-id="749d4-550">Como o desenvolvedor é bastante responsável pela implementação, há mais etapas necessárias para garantir a proteção de dados apropriada do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-550">Because the developer is fairly responsible for the implementation, there are more steps required to ensure appropriate data protection from Intune.</span></span> <span data-ttu-id="749d4-551">Uma vez que a maioria do trabalho é passado para você, o desenvolvedor, integração do Intune é um pouco mais envolvida.</span><span class="sxs-lookup"><span data-stu-id="749d4-551">Since most of the work is pushed onto you, the developer, Intune integration is slightly more involved.</span></span>

<span data-ttu-id="749d4-552">**Integrar o MAM:**</span><span class="sxs-lookup"><span data-stu-id="749d4-552">**Integrate MAM:**</span></span>

1. <span data-ttu-id="749d4-553">Leia atentamente o guia do Android para [Backup de chave/valor](https://developer.android.com/guide/topics/data/keyvaluebackup.html) e especificamente [Estendendo o BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) para garantir que a sua implementação do BackupAgent siga as diretrizes do Android.</span><span class="sxs-lookup"><span data-stu-id="749d4-553">Please carefully read the Android guide for [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) and specifically [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) to ensure your BackupAgent implementation follows Android guidelines.</span></span>

2. <span data-ttu-id="749d4-554">Faça sua classe estender o `MAMBackupAgent`.</span><span class="sxs-lookup"><span data-stu-id="749d4-554">Have your class extend `MAMBackupAgent`.</span></span>

<span data-ttu-id="749d4-555">**Backup de várias identidades:**</span><span class="sxs-lookup"><span data-stu-id="749d4-555">**Multi-identity Backup:**</span></span>

1. <span data-ttu-id="749d4-556">Antes de iniciar o backup, verifique se os arquivos ou buffers de dados dos quais você planeja fazer backup estão realmente **permitidos pelo administrador de TI para terem o backup feito** em cenários de várias identidades.</span><span class="sxs-lookup"><span data-stu-id="749d4-556">Before beginning your backup, check that the files or data buffers you plan to back up are indeed **permitted by the IT administrator to be backed up** in multi-identity scenarios.</span></span> <span data-ttu-id="749d4-557">Nós fornecemos a função `isBackupAllowed` em `MAMFileProtectionManager` e `MAMDataProtectionManager` para determinar isso.</span><span class="sxs-lookup"><span data-stu-id="749d4-557">We provide you with the `isBackupAllowed` function in `MAMFileProtectionManager` and `MAMDataProtectionManager` to determine this.</span></span> <span data-ttu-id="749d4-558">Se o buffer de dados ou arquivo não tiver permissão para backup, você não deverá continuar incluindo-o em seu backup.</span><span class="sxs-lookup"><span data-stu-id="749d4-558">If the file or data buffer is not allowed to be backed up, then you should not continue including it in your backup.</span></span>

2. <span data-ttu-id="749d4-559">Em algum momento durante o backup, se desejar que as identidades dos arquivos verificados na etapa 1 façam backup, você deverá chamar `backupMAMFileIdentity(BackupDataOutput data, File … files)` com os arquivos dos quais planeja extrair dados.</span><span class="sxs-lookup"><span data-stu-id="749d4-559">At some point during your backup, if you want to back up the identities for the files you checked in step 1, you must call `backupMAMFileIdentity(BackupDataOutput data, File … files)` with the files from which you plan to extract data.</span></span> <span data-ttu-id="749d4-560">Isso criará automaticamente novas entidades de backup e as gravará em `BackupDataOutput` para você.</span><span class="sxs-lookup"><span data-stu-id="749d4-560">This will automatically create new backup entities and write them to the `BackupDataOutput` for you.</span></span> <span data-ttu-id="749d4-561">Essas entidades serão consumidas automaticamente após a restauração.</span><span class="sxs-lookup"><span data-stu-id="749d4-561">These entities will be automatically consumed upon restore.</span></span>

<span data-ttu-id="749d4-562">**Restauração de várias identidades:**</span><span class="sxs-lookup"><span data-stu-id="749d4-562">**Multi-identity Restore:**</span></span>

<span data-ttu-id="749d4-563">O guia de Backup de dados especifica um algoritmo geral para restaurar os dados do aplicativo e fornece um exemplo de código na seção [Estendendo o BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent).</span><span class="sxs-lookup"><span data-stu-id="749d4-563">The Data Backup guide specifies a general algorithm for restoring your application’s data and provides a code sample in the [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) section.</span></span> <span data-ttu-id="749d4-564">Para ter uma restauração bem-sucedida de várias identidades, você deverá seguir a estrutura geral fornecida neste exemplo de código com atenção especial para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="749d4-564">In order to have a successful multi-identity restore, you must follow the general structure provided in this code sample with special attention to the following:</span></span>

1.  <span data-ttu-id="749d4-565">Você deve utilizar um loop `while(data.readNextHeader())`* para percorrer as entidades de backup.</span><span class="sxs-lookup"><span data-stu-id="749d4-565">You must utilize a `while(data.readNextHeader())`* loop to go through the backup entities.</span></span>

2.  <span data-ttu-id="749d4-566">Você deve chamar `data.skipEntityData()`* se `data.getKey()`* não coincidir com a chave que você escreveu em `onBackup`.</span><span class="sxs-lookup"><span data-stu-id="749d4-566">You must call `data.skipEntityData()`* if `data.getKey()`* does not match the key you wrote in `onBackup`.</span></span> <span data-ttu-id="749d4-567">Sem realizar esta etapa, suas restaurações poderão não obter êxito.</span><span class="sxs-lookup"><span data-stu-id="749d4-567">Without performing this step, your restores may not succeed.</span></span>

3.  <span data-ttu-id="749d4-568">Evite retornar enquanto estiver consumindo entidades de backup na construção `while(data.readNextHeader())`*, porque as entidades que escrevemos automaticamente serão perdidas.</span><span class="sxs-lookup"><span data-stu-id="749d4-568">Avoid returning while consuming backup entities in the `while(data.readNextHeader())`* construct, as the entities we automatically write will be lost.</span></span>

* <span data-ttu-id="749d4-569">Onde `data` é o nome da variável local para o **BackupDataInput** que é passado para o seu aplicativo após a restauração.</span><span class="sxs-lookup"><span data-stu-id="749d4-569">Where `data` is the local variable name for the **BackupDataInput** that is passed to your app upon restore.</span></span>

## <span data-ttu-id="749d4-570">Várias identidades (opcional)</span><span class="sxs-lookup"><span data-stu-id="749d4-570">Multi-identity (optional)</span></span>
<a id="multi-identity-optional" class="xliff"></a>

### <span data-ttu-id="749d4-571">Visão geral</span><span class="sxs-lookup"><span data-stu-id="749d4-571">Overview</span></span>
<a id="overview" class="xliff"></a>
<span data-ttu-id="749d4-572">Por padrão, o SDK de Aplicativo do Intune aplicará a política ao aplicativo como um todo.</span><span class="sxs-lookup"><span data-stu-id="749d4-572">By default, the Intune App SDK will apply policy  to the app as a whole.</span></span> <span data-ttu-id="749d4-573">Várias identidades é um recurso de proteção opcional do aplicativo do Intune que pode ser habilitado para permitir que a política seja aplicada por identidade.</span><span class="sxs-lookup"><span data-stu-id="749d4-573">Multi-identity is an optional Intune app protection feature which can be enabled to allow policy to be applied on a per-identity level.</span></span> <span data-ttu-id="749d4-574">Ele requer uma participação significativamente maior do aplicativo do que outros recursos de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-574">This requires significantly more app participation than other app protection features.</span></span>

<span data-ttu-id="749d4-575">O aplicativo _precisa_ informar o SDK quando pretender alterar a identidade ativa. O SDK também notificará o aplicativo quando uma alteração de identidade for necessária.</span><span class="sxs-lookup"><span data-stu-id="749d4-575">The app _must_ inform the SDK when it intends to change the active identity, the SDK will also notify the app when an identity change is required.</span></span> <span data-ttu-id="749d4-576">Depois que o usuário registrar o dispositivo ou o aplicativo, o SDK registrará essa identidade e a considerará a identidade gerenciada primária do Intune.</span><span class="sxs-lookup"><span data-stu-id="749d4-576">Once the user enrolls the device or the app, the SDK registers this identity and considers it the primary Intune managed identity.</span></span> <span data-ttu-id="749d4-577">Outros usuários no aplicativo serão tratados como não gerenciados, com configurações de política irrestritas.</span><span class="sxs-lookup"><span data-stu-id="749d4-577">Other users in the app will be treated as unmanaged, with unrestricted policy settings.</span></span>

> [!NOTE]
> <span data-ttu-id="749d4-578">Atualmente, há suporte para apenas uma identidade gerenciada do Intune por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-578">Currently, only one Intune managed identity is supported per device.</span></span>

<span data-ttu-id="749d4-579">Observe que uma identidade é definida simplesmente como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="749d4-579">Note that an identity is simply defined as a string.</span></span> <span data-ttu-id="749d4-580">As identidades **não diferenciam maiúsculas de minúsculas** e as solicitações de identidade ao SDK podem não retornar o mesmo esquema de maiúsculas e minúsculas usado originalmente ao definir a identidade.</span><span class="sxs-lookup"><span data-stu-id="749d4-580">Identities are **case-insensitive**, and requests to the SDK for an identity may not return the same casing that was originally used when setting the identity.</span></span>


### <span data-ttu-id="749d4-581">Habilitando várias identidades</span><span class="sxs-lookup"><span data-stu-id="749d4-581">Enabling Multi-identity</span></span>
<a id="enabling-multi-identity" class="xliff"></a>

<span data-ttu-id="749d4-582">Por padrão, considera-se que todos os aplicativos são aplicativos de identidade única.</span><span class="sxs-lookup"><span data-stu-id="749d4-582">By default, all apps are considered to be single-identity apps.</span></span> <span data-ttu-id="749d4-583">Você pode declarar um aplicativo para reconhecer várias identidades colocando os seguintes metadados no arquivo AndroidManifest.xml.</span><span class="sxs-lookup"><span data-stu-id="749d4-583">You can declare an app to be multi-identity aware by placing the following metadata in AndroidManifest.xml.</span></span>

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <span data-ttu-id="749d4-584">Definindo a identidade</span><span class="sxs-lookup"><span data-stu-id="749d4-584">Setting the Identity</span></span>
<a id="setting-the-identity" class="xliff"></a>

<span data-ttu-id="749d4-585">Os desenvolvedores podem definir a identidade do usuário aplicativo nos níveis a seguir em ordem de prioridade descendente:</span><span class="sxs-lookup"><span data-stu-id="749d4-585">Developers can set the identity of the app user on the following levels in descending priority:</span></span>

  1. <span data-ttu-id="749d4-586">Nível de thread</span><span class="sxs-lookup"><span data-stu-id="749d4-586">Thread level</span></span>
  2. <span data-ttu-id="749d4-587">Nível de contexto (geralmente, a Atividade)</span><span class="sxs-lookup"><span data-stu-id="749d4-587">Context  (generally Activity) level</span></span>
  3. <span data-ttu-id="749d4-588">Nível de processo</span><span class="sxs-lookup"><span data-stu-id="749d4-588">Process level</span></span>

<span data-ttu-id="749d4-589">Uma identidade definida no nível do thread substitui uma identidade definida no nível do Contexto, que substitui uma identidade definida no nível do processo.</span><span class="sxs-lookup"><span data-stu-id="749d4-589">An identity set at the thread level supersedes an identity set at the Context level, which supersedes an identity set at the process level.</span></span> <span data-ttu-id="749d4-590">Uma identidade definida em um contexto é usada apenas em operações de E/S de arquivo de cenários associados apropriados, por exemplo, não tem um contexto associado.</span><span class="sxs-lookup"><span data-stu-id="749d4-590">An identity set on a Context is only used in appropriate associated scenarios File IO operations, for example, do not have an associated Context.</span></span> <span data-ttu-id="749d4-591">Os seguintes métodos no `MAMPolicyManager` podem ser usados para definir a identidade e recuperar os valores de identidade definidos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="749d4-591">The following methods in `MAMPolicyManager` may be used to set the identity and retrieve the identity values previously set.</span></span>

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

  /**
   * Get the currently applicable app policy. Same as
   * MAMComponents.get(AppPolicy.class). This method does
   * not take the context identity into account.
   */
  public static AppPolicy getPolicy();

  /**
   * Get the currently applicable app policy, taking the context
   * identity into account.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);

  ```

>[!NOTE]
> <span data-ttu-id="749d4-592">Você pode limpar a identidade do aplicativo definido-a como nula.</span><span class="sxs-lookup"><span data-stu-id="749d4-592">You can clear the identity of the app by setting it to null.</span></span>
>
> <span data-ttu-id="749d4-593">A cadeia de caracteres vazia pode ser usada como uma identidade que nunca terá política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-593">The empty string may be used as an identity that will never have app protection policy.</span></span>

#### <span data-ttu-id="749d4-594">Resultados</span><span class="sxs-lookup"><span data-stu-id="749d4-594">Results</span></span>
<a id="results" class="xliff"></a>
<span data-ttu-id="749d4-595">Todos os métodos usados para definir a identidade relatam os valores de resultado via `MAMIdentitySwitchResult`.</span><span class="sxs-lookup"><span data-stu-id="749d4-595">All the methods used to set the identity report back result values via `MAMIdentitySwitchResult`.</span></span> <span data-ttu-id="749d4-596">Há quatro valores que podem ser retornados:</span><span class="sxs-lookup"><span data-stu-id="749d4-596">There are four values that can be returned:</span></span>

| <span data-ttu-id="749d4-597">Retornar valor</span><span class="sxs-lookup"><span data-stu-id="749d4-597">Return value</span></span> | <span data-ttu-id="749d4-598">Cenário</span><span class="sxs-lookup"><span data-stu-id="749d4-598">Scenario</span></span> |
|--|--|
| <span data-ttu-id="749d4-599">SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="749d4-599">SUCCEEDED</span></span> | <span data-ttu-id="749d4-600">A alteração de identidade foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="749d4-600">The identity change was successful.</span></span> |
| <span data-ttu-id="749d4-601">NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="749d4-601">NOT_ALLOWED</span></span> | <span data-ttu-id="749d4-602">Não é permitido alterar a identidade.</span><span class="sxs-lookup"><span data-stu-id="749d4-602">The identity change is not allowed.</span></span> <br><br><span data-ttu-id="749d4-603">Isso ocorrerá se for feita uma tentativa de mudar para outro usuário gerenciado que pertence à mesma organização que o usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="749d4-603">This occurs if an attempt is made to switch to a different managed user belonging to the same organization as the enrolled user.</span></span> <span data-ttu-id="749d4-604">Ocorrerá também se for feita uma tentativa de definir a identidade da interface do usuário (Contexto) quando uma identidade diferente estiver definida no thread atual.</span><span class="sxs-lookup"><span data-stu-id="749d4-604">It also occurs if an attempt is made to set the UI (Context) identity when a different identity is set on the current thread.</span></span> |
| <span data-ttu-id="749d4-605">CANCELLED</span><span class="sxs-lookup"><span data-stu-id="749d4-605">CANCELLED</span></span> | <span data-ttu-id="749d4-606">O usuário cancelou a alteração de identidade, normalmente pressionando o botão Voltar em um PIN ou prompt de autenticação.</span><span class="sxs-lookup"><span data-stu-id="749d4-606">The user cancelled the identity change, generally by pressing the back button on a PIN or authentication prompt.</span></span> |
| <span data-ttu-id="749d4-607">FAILED</span><span class="sxs-lookup"><span data-stu-id="749d4-607">FAILED</span></span> | <span data-ttu-id="749d4-608">Ocorreu uma falha na alteração da identidade por um motivo não especificado.</span><span class="sxs-lookup"><span data-stu-id="749d4-608">The identity change failed for an unspecified reason.</span></span>|


<span data-ttu-id="749d4-609">No caso da definição de uma identidade de Contexto, o resultado é relatado de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="749d4-609">In the case of setting a Context identity, the result is reported asynchronously.</span></span> <span data-ttu-id="749d4-610">Se o Contexto for uma Atividade, o SDK não saberá se a alteração de identidade foi bem-sucedida até que a inicialização condicional seja realizada, o que pode exigir que o usuário insira um PIN ou suas credenciais corporativas.</span><span class="sxs-lookup"><span data-stu-id="749d4-610">If the Context is an Activity, the SDK doesn't know if the identity change succeeded until after conditional launch is performed -- which may require the user to enter a PIN or corporate credentials.</span></span> <span data-ttu-id="749d4-611">Espera-se que o aplicativo implemente um `MAMSetUIIdentityCallback` para receber esse resultado, você pode passar null para esse parâmetro.</span><span class="sxs-lookup"><span data-stu-id="749d4-611">The app is expected to implement a `MAMSetUIIdentityCallback` to receive this result, you can pass null for this parameter.</span></span>

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

<span data-ttu-id="749d4-612">Também é possível definir a identidade de uma atividade diretamente por meio de um método em `MAMActivity`, em vez de chamar `MAMPolicyManager.setUIPolicyIdentity`.</span><span class="sxs-lookup"><span data-stu-id="749d4-612">You can also set the identity of an activity directly through a method in `MAMActivity` instead of calling `MAMPolicyManager.setUIPolicyIdentity`.</span></span> <span data-ttu-id="749d4-613">Use o seguinte método para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="749d4-613">Use following method to do so:</span></span>

```java
     public final void switchMAMIdentity(final String newIdentity);
```

<span data-ttu-id="749d4-614">Você também pode substituir um método no `MAMActivity` se quiser que o aplicativo seja notificado do resultado das tentativas de alterar a identidade da atividade.</span><span class="sxs-lookup"><span data-stu-id="749d4-614">You can also override a method in `MAMActivity` if you want the app to be notified of the result of attempts to change the identity of that activity.</span></span>

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> <span data-ttu-id="749d4-615">Alterar a identidade pode exigir a recriação da atividade.</span><span class="sxs-lookup"><span data-stu-id="749d4-615">Switching the identity may require recreating the activity.</span></span> <span data-ttu-id="749d4-616">Nesse caso, o retorno de chamada `onSwitchMAMIdentityComplete` será entregue para a nova instância da atividade.</span><span class="sxs-lookup"><span data-stu-id="749d4-616">In this case, the `onSwitchMAMIdentityComplete` callback will be delivered to the new instance of the activity.</span></span>


### <span data-ttu-id="749d4-617">Alterações de identidade implícitas</span><span class="sxs-lookup"><span data-stu-id="749d4-617">Implicit Identity Changes</span></span>
<a id="implicit-identity-changes" class="xliff"></a>

<span data-ttu-id="749d4-618">Além da capacidade do aplicativo de definir a identidade, um thread ou a identidade de um contexto pode mudar com base na entrada de dados de outro aplicativo orientado para Intune que tenha política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-618">In addition to the app's ability to set the identity, a thread or a context's identity may change based on data ingress from another Intune-enlightened app that has app protection policy.</span></span>

#### <span data-ttu-id="749d4-619">Exemplos</span><span class="sxs-lookup"><span data-stu-id="749d4-619">Examples</span></span>
<a id="examples" class="xliff"></a>

  1. <span data-ttu-id="749d4-620">Se uma atividade for iniciada de uma `Intent` enviada por outro aplicativo com MAM, a identidade da atividade será definida com base na identidade em vigor no outro aplicativo no momento em que a `Intent` foi enviada.</span><span class="sxs-lookup"><span data-stu-id="749d4-620">If an activity is launched from an `Intent` sent by another MAM app, the activity’s identity will be set based on the effective identity in the other app at the point the `Intent` was sent.</span></span>

  2.  <span data-ttu-id="749d4-621">Para serviços, a identidade do thread será definida da mesma forma pela duração de uma chamada `onStart` ou `onBind`.</span><span class="sxs-lookup"><span data-stu-id="749d4-621">For services, the thread identity will be set similarly for the duration of an `onStart` or `onBind` call.</span></span> <span data-ttu-id="749d4-622">Chamadas para `Binder` retornadas de `onBind` também definirão temporariamente a identidade do thread.</span><span class="sxs-lookup"><span data-stu-id="749d4-622">Calls into the `Binder` returned from `onBind` will also temporarily set the thread identity.</span></span>

  3. <span data-ttu-id="749d4-623">De forma semelhante, chamadas para um `ContentProvider` definirão a identidade do thread no período de sua duração.</span><span class="sxs-lookup"><span data-stu-id="749d4-623">Calls into a `ContentProvider` will similarly set the thread identity for their duration.</span></span>


  <span data-ttu-id="749d4-624">Além disso, a interação do usuário com uma atividade pode causar uma mudança de identidade implícita.</span><span class="sxs-lookup"><span data-stu-id="749d4-624">In addition, user interaction with an activity may cause an implicit identity switch.</span></span>

  <span data-ttu-id="749d4-625">**Exemplo:** se um usuário cancelar após um prompt de autorização durante o `Resume`, ocorrerá uma mudança implícita para uma identidade vazia.</span><span class="sxs-lookup"><span data-stu-id="749d4-625">**Example:** A user canceling out of an authorization prompt during `Resume` will result in an implicit switch to an empty identity.</span></span>

  <span data-ttu-id="749d4-626">O aplicativo tem uma oportunidade de ser informado dessas alterações e, se precisar, pode proibi-las.</span><span class="sxs-lookup"><span data-stu-id="749d4-626">The app is given an opportunity to be made aware of these changes, and, if it must, the app can forbid them.</span></span> <span data-ttu-id="749d4-627">`MAMService` e `MAMContentProvider` expõem o seguinte método que as subclasses podem substituir:</span><span class="sxs-lookup"><span data-stu-id="749d4-627">`MAMService` and `MAMContentProvider` expose the following method that subclasses may override:</span></span>

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  <span data-ttu-id="749d4-628">Na classe `MAMActivity`, um parâmetro adicional está presente no método:</span><span class="sxs-lookup"><span data-stu-id="749d4-628">In the `MAMActivity` class , an additional parameter is present in the method:</span></span>

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * <span data-ttu-id="749d4-629">O `AppIdentitySwitchReason` captura a fonte da mudança implícita e pode aceitar os valores `CREATE`, `RESUME_CANCELLED` e `NEW_INTENT`.</span><span class="sxs-lookup"><span data-stu-id="749d4-629">The `AppIdentitySwitchReason` captures the source of the implicit switch, and can accept the values `CREATE`, `RESUME_CANCELLED`, and `NEW_INTENT`.</span></span>  <span data-ttu-id="749d4-630">O motivo `RESUME_CANCELLED` é usado quando a atividade é retomada e faz com que o PIN, a autenticação ou outra interface do usuário de conformidade seja exibida; o usuário tenta cancelar para sair dessa interface do usuário, normalmente usando o uso do botão Voltar.</span><span class="sxs-lookup"><span data-stu-id="749d4-630">The `RESUME_CANCELLED` reason is used when activity resume causes PIN, authentication, or other compliance UI to be displayed and the user attempts to cancel out of that UI, generally though use of the back button.</span></span>


  * <span data-ttu-id="749d4-631">`AppIdentitySwitchResultCallback` é o seguinte:</span><span class="sxs-lookup"><span data-stu-id="749d4-631">The `AppIdentitySwitchResultCallback` is as follows:</span></span>

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    <span data-ttu-id="749d4-632">Onde ```AppIdentitySwitchResult``` é ÊXITO ou FALHA.</span><span class="sxs-lookup"><span data-stu-id="749d4-632">Where ```AppIdentitySwitchResult``` is either SUCCESS or FAILURE.</span></span>

<span data-ttu-id="749d4-633">O método `onMAMIdentitySwitchRequired` é chamado para todas as mudanças de identidade implícitas, exceto por aquelas feitas por meio de um Associador retornado de `MAMService.onMAMBind`.</span><span class="sxs-lookup"><span data-stu-id="749d4-633">The method `onMAMIdentitySwitchRequired` is called for all implicit identity changes except for those made through a Binder returned from `MAMService.onMAMBind`.</span></span> <span data-ttu-id="749d4-634">As implementações padrão do `onMAMIdentitySwitchRequired` imediatamente chamam:</span><span class="sxs-lookup"><span data-stu-id="749d4-634">The default implementations of `onMAMIdentitySwitchRequired` immediately call:</span></span>

*  <span data-ttu-id="749d4-635">`reportIdentitySwitchResult(FAILURE)` quando o motivo é RESUME_CANCELLED.</span><span class="sxs-lookup"><span data-stu-id="749d4-635">`reportIdentitySwitchResult(FAILURE)` when the reason is RESUME_CANCELLED.</span></span>

*  <span data-ttu-id="749d4-636">`reportIdentitySwitchResult(SUCCESS)` em todos os outros casos.</span><span class="sxs-lookup"><span data-stu-id="749d4-636">`reportIdentitySwitchResult(SUCCESS)` in all other cases.</span></span>

  <span data-ttu-id="749d4-637">Não é esperado que a maioria dos aplicativos precisem bloquear ou adiar uma mudança de identidade de maneira diferente, mas se um aplicativo precisar fazer isso, os seguintes pontos devem ser considerados:</span><span class="sxs-lookup"><span data-stu-id="749d4-637">It is not expected that most apps will need to block or delay an identity switch in a different manner, but if an app needs to do so, the following points must be considered:</span></span>

  * <span data-ttu-id="749d4-638">Se uma mudança de identidade estiver bloqueada, o resultado será o mesmo, como se as configurações de compartilhamento de `Receive` tivessem proibido a entrada de dados.</span><span class="sxs-lookup"><span data-stu-id="749d4-638">If an identity switch is blocked, the result is the same as if `Receive` sharing settings had prohibited the data ingress.</span></span>

  * <span data-ttu-id="749d4-639">Se um serviço estiver em execução no thread principal, `reportIdentitySwitchResult` **deve** ser chamado de forma síncrona ou o thread da interface do usuário falhará.</span><span class="sxs-lookup"><span data-stu-id="749d4-639">If a Service is running on the main thread, `reportIdentitySwitchResult` **must** be called synchronously or the UI thread will hang.</span></span>

  * <span data-ttu-id="749d4-640">Para criação de **Atividade**, `onMAMIdentitySwitchRequired` será chamado antes de `onMAMCreate`.</span><span class="sxs-lookup"><span data-stu-id="749d4-640">For **Activity** creation, `onMAMIdentitySwitchRequired` will be called before `onMAMCreate`.</span></span> <span data-ttu-id="749d4-641">Se o aplicativo precisar mostrar a interface do usuário para determinar se deve permitir a mudança de identidade, a interface do usuário deverá ser exibida usando uma atividade *diferente*.</span><span class="sxs-lookup"><span data-stu-id="749d4-641">If the app must show UI to determine whether to allow the identity switch, that UI must be shown using a *different* activity.</span></span>

  * <span data-ttu-id="749d4-642">Em uma **Atividade**, quando for solicitada uma mudança para a identidade vazia com o motivo igual a RESUME_CANCELLED, o aplicativo deverá modificar a atividade retomada para exibir dados consistentes com essa mudança de identidade.</span><span class="sxs-lookup"><span data-stu-id="749d4-642">In an **Activity**, when a switch to the empty identity is requested with the reason as RESUME_CANCELLED, the app must modify the resumed activity to display data consistent with that identity switch.</span></span>  <span data-ttu-id="749d4-643">Se isso não for possível, o aplicativo deverá recusar a mudança e o usuário será solicitado novamente a obedecer a política para retomar a identidade (por exemplo, recebendo a tela de entrada de PIN do aplicativo).</span><span class="sxs-lookup"><span data-stu-id="749d4-643">If this is not possible, the app should refuse the switch, and the user will be asked again to comply with policy for the resuming identity (e.g. by being presented with the app PIN entry screen).</span></span>

    > [!NOTE]
    > <span data-ttu-id="749d4-644">Um aplicativo com várias identidades sempre receberá dados de entrada de aplicativos gerenciados e não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="749d4-644">A multi-identity app will always receive incoming data from both managed and unmanaged apps.</span></span> <span data-ttu-id="749d4-645">É responsabilidade do aplicativo tratar dados de identidades gerenciadas de maneira gerenciada.</span><span class="sxs-lookup"><span data-stu-id="749d4-645">It is the responsibility of the app to treat data from managed identities in a managed manner.</span></span>

  <span data-ttu-id="749d4-646">Se uma identidade solicitada for gerenciada (use `MAMPolicyManager.getIsIdentityManaged` para verificar), mas o aplicativo não puder usar a conta (por exemplo, porque contas, como contas de email, devem ser configuradas no aplicativo primeiro), a chave de identidade deverá ser recusada.</span><span class="sxs-lookup"><span data-stu-id="749d4-646">If a requested identity is managed (use `MAMPolicyManager.getIsIdentityManaged` to check), but the app is not able to use that account (e.g. because accounts, such as email accounts, must be set up in the app first) then the identity switch should be refused.</span></span>



  ### <span data-ttu-id="749d4-647">Proteção de arquivo</span><span class="sxs-lookup"><span data-stu-id="749d4-647">File Protection</span></span>
<a id="file-protection" class="xliff"></a>

  <span data-ttu-id="749d4-648">Cada arquivo tem uma identidade associada no momento da criação, com base na identidade do thread e do processo.</span><span class="sxs-lookup"><span data-stu-id="749d4-648">Every file has an identity associated with it at the time of creation, based on thread and process identity.</span></span> <span data-ttu-id="749d4-649">Essa identidade será usada para a criptografia de arquivos e o apagamento seletivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-649">This identity will be used for both file encryption and selective wipe.</span></span> <span data-ttu-id="749d4-650">Somente arquivos cuja identidade é gerenciada e tem uma política que exige criptografia serão criptografados.</span><span class="sxs-lookup"><span data-stu-id="749d4-650">Only files whose identity is managed and has policy requiring encryption will be encrypted.</span></span> <span data-ttu-id="749d4-651">A funcionalidade de apagamento seletivo padrão do SDK apagará apenas arquivos associados à identidade gerenciada para a qual um apagamento foi solicitado.</span><span class="sxs-lookup"><span data-stu-id="749d4-651">The SDK's default selective functionality wipe will only wipe files associated with the managed identity for which a wipe has been requested.</span></span> <span data-ttu-id="749d4-652">O aplicativo pode consultar ou alterar a identidade de um arquivo usando a classe `MAMFileProtectionManager`.</span><span class="sxs-lookup"><span data-stu-id="749d4-652">The app may query or change a file’s identity using the `MAMFileProtectionManager` class.</span></span>

  ```java
    public final class MAMFileProtectionManager {

        /**
         * Protect a file. This will synchronously trigger whatever protection is required for the file, and will tag the file for
         * future protection changes.
         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final File file) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```

<span data-ttu-id="749d4-653">A marcação de identidade do arquivo é sensível ao modo offline.</span><span class="sxs-lookup"><span data-stu-id="749d4-653">File identity tagging is sensitive to offline mode.</span></span> <span data-ttu-id="749d4-654">Os aspectos a seguir devem ser levados em conta:</span><span class="sxs-lookup"><span data-stu-id="749d4-654">The following points should be taken into account:</span></span>

  * <span data-ttu-id="749d4-655">Se o Portal da Empresa não estiver instalado, os arquivos não poderão ser marcados segundo a identidade.</span><span class="sxs-lookup"><span data-stu-id="749d4-655">If the Company Portal is not installed, files cannot be identity-tagged.</span></span>

  * <span data-ttu-id="749d4-656">Se o Portal da Empresa estiver instalado, mas o aplicativo não tiver a política do MAM do Intune, os arquivos não poderão ser marcados segundo a identidade de forma confiável.</span><span class="sxs-lookup"><span data-stu-id="749d4-656">If the Company Portal is installed, but the app does not have Intune MAM policy, files cannot be reliably tagged with identity.</span></span>

  * <span data-ttu-id="749d4-657">Quando a marcação de identidade do arquivo se torna disponível, todos os arquivos criados anteriormente são tratados como pessoais/não gerenciados (pertencentes à identidade de cadeia de caracteres vazia), a menos que o aplicativo tenha sido instalado anteriormente como um aplicativo gerenciado de identidade única. Nesse caso, eles serão tratados como pertencentes ao usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="749d4-657">When file identity tagging becomes available, all previously created files are treated as personal/unmanaged (belonging to the empty-string identity) unless the app was previously installed as a single-identity managed app in which case they are treated as belonging to the enrolled user.</span></span>

### <span data-ttu-id="749d4-658">Proteção de diretório</span><span class="sxs-lookup"><span data-stu-id="749d4-658">Directory Protection</span></span>
<a id="directory-protection" class="xliff"></a>

<span data-ttu-id="749d4-659">Os diretórios podem ser protegidos com o mesmo método `protect` usado para proteger os arquivos.</span><span class="sxs-lookup"><span data-stu-id="749d4-659">Directories may be protected using the same `protect` method used to protect files.</span></span> <span data-ttu-id="749d4-660">Observe que a proteção de diretório é aplicada recursivamente para todos os arquivos e subdiretórios contidos no diretório e para novos arquivos criados dentro do diretório.</span><span class="sxs-lookup"><span data-stu-id="749d4-660">Please note that directory protection applies recursively to all files and subdirectories contained in the directory, and to new files created within the directory.</span></span> <span data-ttu-id="749d4-661">Como a proteção de diretório é aplicada recursivamente, a chamada do `protect` pode levar algum tempo para ser concluída em diretórios muito grandes.</span><span class="sxs-lookup"><span data-stu-id="749d4-661">Because directory protection is applied recursively, the `protect` call can take some time to complete for very large directories.</span></span> <span data-ttu-id="749d4-662">Por esse motivo, os aplicativos que aplicam proteção a um diretório que contém um grande número de arquivos podem desejar executar o `protect` de maneira assíncrona em um thread em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="749d4-662">For that reason, apps applying protection to a directory that contains a large number of files might wish to run `protect` asynchronously on a background thread.</span></span>

### <span data-ttu-id="749d4-663">Proteção de dados</span><span class="sxs-lookup"><span data-stu-id="749d4-663">Data Protection</span></span>
<a id="data-protection" class="xliff"></a>

<span data-ttu-id="749d4-664">Não é possível marcar um arquivo como pertencente a várias identidades.</span><span class="sxs-lookup"><span data-stu-id="749d4-664">It is not possible to tag a file as belonging to multiple identities.</span></span> <span data-ttu-id="749d4-665">Aplicativos que precisam armazenar dados pertencentes a diferentes usuários no mesmo arquivo podem fazer isso manualmente usando os recursos fornecidos pelo `MAMDataProtectionManager`.</span><span class="sxs-lookup"><span data-stu-id="749d4-665">Apps that must store data belonging to different users in the same file can do so manually, using the features provided by `MAMDataProtectionManager`.</span></span> <span data-ttu-id="749d4-666">Isso permite que o aplicativo criptografe dados e os vincule a um usuário específico.</span><span class="sxs-lookup"><span data-stu-id="749d4-666">This allows the app to encrypt data and tie it to a particular user.</span></span> <span data-ttu-id="749d4-667">Os dados criptografados são adequados para armazenamento em disco em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-667">The encrypted data is suitable for storing to disk in a file.</span></span> <span data-ttu-id="749d4-668">Você pode consultar os dados associados à identidade e os dados podem ser descriptografados mais tarde.</span><span class="sxs-lookup"><span data-stu-id="749d4-668">You can query the data associated with the identity and the data can be unecrypted later.</span></span>

<span data-ttu-id="749d4-669">Os aplicativos que usam o `MAMDataProtectionManager` devem implementar um receptor para a notificação `MANAGEMENT_REMOVED`.</span><span class="sxs-lookup"><span data-stu-id="749d4-669">Apps which make use of `MAMDataProtectionManager` should implement a receiver for the `MANAGEMENT_REMOVED` notification.</span></span> <span data-ttu-id="749d4-670">Após essa notificação ser concluída, os buffers que foram protegidos por meio dessa classe não serão mais legíveis se a criptografia de arquivo tiver sido habilitada quando os buffers estavam protegidos.</span><span class="sxs-lookup"><span data-stu-id="749d4-670">After this notification completes, buffers which were protected via this class will no longer be readable if file encryption was enabled when the buffers were protected.</span></span> <span data-ttu-id="749d4-671">Um aplicativo pode corrigir essa situação chamando MAMDataProtectionManager.unprotect em todos os buffers durante essa notificação.</span><span class="sxs-lookup"><span data-stu-id="749d4-671">An app can remediate this situation by calling MAMDataProtectionManager.unprotect on all buffers during this notification.</span></span> <span data-ttu-id="749d4-672">Observe que também é seguro chamar a proteção durante essa notificação se for necessário preservar as informações de identidade: a criptografia tem garantia de ser desativada durante a notificação.</span><span class="sxs-lookup"><span data-stu-id="749d4-672">Note that it is also safe to call protect during this notification if it is desired to preserve identity information -- encryption is guaranteed to be disabled during the notification.</span></span>

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}

```

### <span data-ttu-id="749d4-673">Provedores de conteúdo</span><span class="sxs-lookup"><span data-stu-id="749d4-673">Content Providers</span></span>
<a id="content-providers" class="xliff"></a>

<span data-ttu-id="749d4-674">Se o aplicativo fornece dados corporativos além de um **ParcelFileDescriptor** por meio de um **ContentProvider**, o aplicativo deve chamar o método `isProvideContentAllowed(String)` no `MAMContentProvider`, passando um UPN da identidade do proprietário (nome principal do usuário) para o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="749d4-674">If the app provides corporate data other than a **ParcelFileDescriptor** through a **ContentProvider**, the app must call the method `isProvideContentAllowed(String)` in `MAMContentProvider`, passing the owner identity's UPN (user principal name) for the content.</span></span> <span data-ttu-id="749d4-675">Se essa função retornar false, o conteúdo *não pode* ser retornado ao chamador.</span><span class="sxs-lookup"><span data-stu-id="749d4-675">If this function returns false, the content *may not* be returned to the caller.</span></span> <span data-ttu-id="749d4-676">Descritores de arquivo retornados por meio de um provedor de conteúdo são manipulados automaticamente com base na identidade do arquivo.</span><span class="sxs-lookup"><span data-stu-id="749d4-676">File descriptors returned through a content provider are handled automatically based on the file identity.</span></span>

### <span data-ttu-id="749d4-677">Apagamento seletivo</span><span class="sxs-lookup"><span data-stu-id="749d4-677">Selective Wipe</span></span>
<a id="selective-wipe" class="xliff"></a>

<span data-ttu-id="749d4-678">Se um aplicativo se registrar para notificação do `WIPE_USER_DATA`, ele não receberá o benefício do comportamento de apagamento seletivo do SDK padrão.</span><span class="sxs-lookup"><span data-stu-id="749d4-678">If an app registers for the `WIPE_USER_DATA` notification, it will not receive the benefit of the SDK's default selective wipe behavior.</span></span> <span data-ttu-id="749d4-679">Para aplicativos com reconhecimento de várias identidades, essa perda pode ser mais significativo, uma vez que o apagamento seletivo padrão do MAM apagará apenas os arquivos cujas identidades são direcionadas por um apagamento.</span><span class="sxs-lookup"><span data-stu-id="749d4-679">For multi-identity aware apps, this loss may be more significant since MAM default selective wipe will wipe only files whose identity is targeted by a wipe.</span></span>

<span data-ttu-id="749d4-680">Se um aplicativo com reconhecimento de várias identidade deseja que o apagamento seletivo padrão do MAM seja feito _**e**_ deseja realizar suas próprias ações de apagamento, ele deve se registrar para as notificações do `WIPE_USER_AUXILIARY_DATA`.</span><span class="sxs-lookup"><span data-stu-id="749d4-680">If a multi-identity aware application wishes MAM default selective wipe to be done _**and**_ wishes to perform its own actions on wipe, it should register for `WIPE_USER_AUXILIARY_DATA` notifications.</span></span> <span data-ttu-id="749d4-681">Essa notificação será enviada imediatamente pelo SDK antes de executar o apagamento seletivo padrão do MAM.</span><span class="sxs-lookup"><span data-stu-id="749d4-681">This notification will be sent immediately by the SDK before it performs the MAM default selective wipe.</span></span> <span data-ttu-id="749d4-682">Um aplicativo nunca deve se registrar para WIPE_USER_DATA e WIPE_USER_AUXILIARY_DATA.</span><span class="sxs-lookup"><span data-stu-id="749d4-682">An app should never register for both WIPE_USER_DATA and WIPE_USER_AUXILIARY_DATA.</span></span>


## <span data-ttu-id="749d4-683">Personalização de estilo (opcional)</span><span class="sxs-lookup"><span data-stu-id="749d4-683">Style Customization (optional)</span></span>
<a id="style-customization-optional" class="xliff"></a>

<span data-ttu-id="749d4-684">Os modos de exibição gerados pelo SDK do MAM visualmente podem ser personalizados para atender melhor ao aplicativo no qual ele está integrado.</span><span class="sxs-lookup"><span data-stu-id="749d4-684">Views generated by the MAM SDK can be visually customized to more closely match the app in which it is integrated.</span></span> <span data-ttu-id="749d4-685">Você pode personalizar as cores primárias, secundárias e de plano de fundo, além do tamanho do logotipo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-685">You can customize primary, secondary, and background colors, as well as the size of the app logo.</span></span> <span data-ttu-id="749d4-686">Essa personalização de estilo é opcional e o padrão será usado se nenhum estilo personalizado estiver configurado.</span><span class="sxs-lookup"><span data-stu-id="749d4-686">This style customization is optional and defaults will be used if no custom style is configured.</span></span>


### <span data-ttu-id="749d4-687">Como personalizar</span><span class="sxs-lookup"><span data-stu-id="749d4-687">How to customize</span></span>
<a id="how-to-customize" class="xliff"></a>
<span data-ttu-id="749d4-688">Para que as alterações de estilo se apliquem às exibições do MAM do Intune, crie primeiro um arquivo XML de substituição de estilo.</span><span class="sxs-lookup"><span data-stu-id="749d4-688">In order to have style changes apply to the Intune MAM views, you must first create a style override XML file.</span></span> <span data-ttu-id="749d4-689">Esse arquivo deve ser colocado no diretório "/res/xml" do seu aplicativo e você pode renomeá-lo como quiser.</span><span class="sxs-lookup"><span data-stu-id="749d4-689">This file should be placed in the “/res/xml” directory of your app and you may name it whatever you like.</span></span> <span data-ttu-id="749d4-690">Veja abaixo um exemplo do formato que esse arquivo deve seguir.</span><span class="sxs-lookup"><span data-stu-id="749d4-690">Below is an example of the format this file needs to follow.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

<span data-ttu-id="749d4-691">Você deve reutilizar os recursos que já existem dentro de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-691">You must reuse resources that already exist within your app.</span></span> <span data-ttu-id="749d4-692">Por exemplo, você deve definir a cor verde no arquivo colors.xml e referenciá-la aqui.</span><span class="sxs-lookup"><span data-stu-id="749d4-692">For example, you must define the color green in the colors.xml file and reference it here.</span></span> <span data-ttu-id="749d4-693">Você não pode usar o código de cor hexadecimal “#0000ff".</span><span class="sxs-lookup"><span data-stu-id="749d4-693">You cannot use the Hex color code “#0000ff."</span></span> <span data-ttu-id="749d4-694">O tamanho máximo para o logotipo do aplicativo é 110 dip (dp).</span><span class="sxs-lookup"><span data-stu-id="749d4-694">The maximum size for the app logo is 110 dip (dp).</span></span> <span data-ttu-id="749d4-695">Você pode usar uma imagem de logotipo menor, mas seguir o tamanho máximo produzirá resultados melhores visualmente.</span><span class="sxs-lookup"><span data-stu-id="749d4-695">You may use a smaller logo image, but adhering to the maximum size will yield the best looking results.</span></span> <span data-ttu-id="749d4-696">Se você exceder o limite de 110 dip, a imagem será reduzida e possivelmente ficará desfocada.</span><span class="sxs-lookup"><span data-stu-id="749d4-696">If you exceed the 110 dip limit, the image will scale down and possibly cause blurring.</span></span>

<span data-ttu-id="749d4-697">Veja abaixo uma lista completa de atributos de estilo permitidos, os elementos de interface do usuário que eles controlam, seus nomes de item de atributo de XML e o tipo de recurso esperado para cada.</span><span class="sxs-lookup"><span data-stu-id="749d4-697">Below is the complete list of allowed style attributes, the UI elements they control, their XML attribute item names, and the type of resource expected for each.</span></span>

|<span data-ttu-id="749d4-698">Atributo de estilo</span><span class="sxs-lookup"><span data-stu-id="749d4-698">Style attribute</span></span> | <span data-ttu-id="749d4-699">Elementos de interface do usuário afetados</span><span class="sxs-lookup"><span data-stu-id="749d4-699">UI elements affected</span></span> | <span data-ttu-id="749d4-700">Nome do item de atributo</span><span class="sxs-lookup"><span data-stu-id="749d4-700">Attribute item name</span></span> | <span data-ttu-id="749d4-701">Tipo de recurso esperado</span><span class="sxs-lookup"><span data-stu-id="749d4-701">Expected resource type</span></span> |
| -- | -- | -- | -- |
| <span data-ttu-id="749d4-702">Cor da tela de fundo</span><span class="sxs-lookup"><span data-stu-id="749d4-702">Background color</span></span> | <span data-ttu-id="749d4-703">Cor de fundo da tela de PIN</span><span class="sxs-lookup"><span data-stu-id="749d4-703">PIN screen background color</span></span> <Br><span data-ttu-id="749d4-704">Cor de preenchimento da caixa de PIN</span><span class="sxs-lookup"><span data-stu-id="749d4-704">PIN box fill color</span></span> | <span data-ttu-id="749d4-705">background_color</span><span class="sxs-lookup"><span data-stu-id="749d4-705">background_color</span></span> | <span data-ttu-id="749d4-706">Cor</span><span class="sxs-lookup"><span data-stu-id="749d4-706">Color</span></span> |
| <span data-ttu-id="749d4-707">Cor da tela de primeiro plano</span><span class="sxs-lookup"><span data-stu-id="749d4-707">Foreground color</span></span> | <span data-ttu-id="749d4-708">Cor de texto da tela de primeiro plano</span><span class="sxs-lookup"><span data-stu-id="749d4-708">Foreground text color</span></span> <br> <span data-ttu-id="749d4-709">Borda da caixa se PIN no estado padrão</span><span class="sxs-lookup"><span data-stu-id="749d4-709">PIN box border in default state</span></span> <br> <span data-ttu-id="749d4-710">Caracteres (incluindo caracteres ofuscados) na caixa PIN quando o usuário digita um PIN</span><span class="sxs-lookup"><span data-stu-id="749d4-710">Characters (including obfuscated characters) in PIN box when user enters a PIN</span></span>| <span data-ttu-id="749d4-711">foreground_color</span><span class="sxs-lookup"><span data-stu-id="749d4-711">foreground_color</span></span> | <span data-ttu-id="749d4-712">Cor</span><span class="sxs-lookup"><span data-stu-id="749d4-712">Color</span></span>|
| <span data-ttu-id="749d4-713">Cor de ênfase</span><span class="sxs-lookup"><span data-stu-id="749d4-713">Accent color</span></span> | <span data-ttu-id="749d4-714">Borda da caixa de PIN quando realçada</span><span class="sxs-lookup"><span data-stu-id="749d4-714">PIN box border when highlighted</span></span> <br> <span data-ttu-id="749d4-715">Hiperlinks</span><span class="sxs-lookup"><span data-stu-id="749d4-715">Hyperlinks</span></span> |<span data-ttu-id="749d4-716">accent_color</span><span class="sxs-lookup"><span data-stu-id="749d4-716">accent_color</span></span> | <span data-ttu-id="749d4-717">Cor</span><span class="sxs-lookup"><span data-stu-id="749d4-717">Color</span></span> |
| <span data-ttu-id="749d4-718">Logotipo do aplicativo</span><span class="sxs-lookup"><span data-stu-id="749d4-718">App logo</span></span> | <span data-ttu-id="749d4-719">Ícone grande que aparece na tela de PIN do aplicativo do Intune</span><span class="sxs-lookup"><span data-stu-id="749d4-719">Large icon that appears in the Intune app PIN screen</span></span> | <span data-ttu-id="749d4-720">logo_image</span><span class="sxs-lookup"><span data-stu-id="749d4-720">logo_image</span></span> | <span data-ttu-id="749d4-721">Desenhável</span><span class="sxs-lookup"><span data-stu-id="749d4-721">Drawable</span></span> |

## <span data-ttu-id="749d4-722">Limitações</span><span class="sxs-lookup"><span data-stu-id="749d4-722">Limitations</span></span>
<a id="limitations" class="xliff"></a>

### <span data-ttu-id="749d4-723">Limitações de tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="749d4-723">File Size limitations</span></span>
<a id="file-size-limitations" class="xliff"></a>

<span data-ttu-id="749d4-724">Para grandes bases de código que são executadas sem o [ProGuard](http://proguard.sourceforge.net/), as limitações do formato de arquivo executável Dalvik podem se tornar um problema.</span><span class="sxs-lookup"><span data-stu-id="749d4-724">For large code bases that run without [ProGuard](http://proguard.sourceforge.net/), the limitations of the Dalvik executable file format become an issue.</span></span> <span data-ttu-id="749d4-725">Especificamente, as limitações a seguir podem ocorrer:</span><span class="sxs-lookup"><span data-stu-id="749d4-725">Specifically, the following limitations may occur:</span></span>

1.  <span data-ttu-id="749d4-726">O limite de 65 mil para campos.</span><span class="sxs-lookup"><span data-stu-id="749d4-726">The 65K limit on fields.</span></span>
2.  <span data-ttu-id="749d4-727">O limite de 65 mil para métodos.</span><span class="sxs-lookup"><span data-stu-id="749d4-727">The 65K limit on methods.</span></span>



### <span data-ttu-id="749d4-728">Limitações de imposição de política</span><span class="sxs-lookup"><span data-stu-id="749d4-728">Policy enforcement limitations</span></span>
<a id="policy-enforcement-limitations" class="xliff"></a>

* <span data-ttu-id="749d4-729">**Captura de tela**: o SDK não impõe um novo valor de configuração de captura de tela Atividades que já passaram por Activity.onCreate.</span><span class="sxs-lookup"><span data-stu-id="749d4-729">**Screen Capture**: The SDK is unable to enforce a new screen capture setting value in Activities that have already gone through Activity.onCreate.</span></span> <span data-ttu-id="749d4-730">Isso pode resultar em um período de tempo em que o aplicativo foi configurado para desabilitar as capturas de tela, mas capturas de tela ainda podem ser feitas.</span><span class="sxs-lookup"><span data-stu-id="749d4-730">This can result in a period of time where the app has been configured to disable screenshots but screenshots can still be taken.</span></span>

* <span data-ttu-id="749d4-731">**Usando resolvedores de conteúdo**: a política de transferência ou de recebimento do Intune pode bloquear ou bloquear parcialmente o uso de um resolvedor de conteúdo para acessar o provedor de conteúdo em outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="749d4-731">**Using Content Resolvers**: The "transfer or receive" Intune policy may block or partially block the use of a content resolver to access the content provider in another app.</span></span> <span data-ttu-id="749d4-732">Isso fará com que os métodos de ContentResolver retornem null ou gerem um valor de falha (por exemplo, `openOutputStream` lançará `FileNotFoundException` se bloqueado).</span><span class="sxs-lookup"><span data-stu-id="749d4-732">This will cause ContentResolver methods to return null or throw a failure value (e.g. `openOutputStream` will throw `FileNotFoundException` if blocked).</span></span> <span data-ttu-id="749d4-733">O aplicativo pode determinar se uma falha de gravação de dados por meio de um resolvedor de conteúdo foi causada pela política (ou seria causada pela política), fazendo a chamada:</span><span class="sxs-lookup"><span data-stu-id="749d4-733">The app can determine whether a failure to write data through a content resolver was caused by policy (or would be caused by policy) by making the call:</span></span>

    ```java
    MAMComponents.get(AppPolicy.class).getIsSaveToLocationAllowed(contentURI);
    ```

### <span data-ttu-id="749d4-734">Serviços exportados</span><span class="sxs-lookup"><span data-stu-id="749d4-734">Exported services</span></span>
<a id="exported-services" class="xliff"></a>

 <span data-ttu-id="749d4-735">O arquivo AndroidManifest.xml incluído no SDK de Aplicativos do Intune contém **MAMNotificationReceiverService**, que deve ser um serviço exportado para permitir que o Portal da Empresa envie notificações para um aplicativo esclarecido.</span><span class="sxs-lookup"><span data-stu-id="749d4-735">The AndroidManifest.xml file included in the Intune App SDK contains **MAMNotificationReceiverService**, which must be an exported service to allow the Company Portal to send notifications to an enlightened app.</span></span> <span data-ttu-id="749d4-736">O serviço verifica o chamador para garantir que apenas o Portal da Empresa tenha permissão para enviar notificações.</span><span class="sxs-lookup"><span data-stu-id="749d4-736">The service checks the caller to ensure that only the Company Portal is allowed to send notifications.</span></span>



## <span data-ttu-id="749d4-737">Expectativas do cliente do SDK</span><span class="sxs-lookup"><span data-stu-id="749d4-737">Expectations of the SDK consumer</span></span>
<a id="expectations-of-the-sdk-consumer" class="xliff"></a>

<span data-ttu-id="749d4-738">O SDK do Intune mantém o contrato fornecido pela API do Android, embora condições de falha possam ser disparadas com mais frequência como resultado da aplicação de políticas.</span><span class="sxs-lookup"><span data-stu-id="749d4-738">The Intune SDK maintains the contract provided by the Android API, though failure conditions may be triggered more frequently as a result of policy enforcement.</span></span> <span data-ttu-id="749d4-739">Essas práticas recomendadas do Android reduzirão a probabilidade de falha:</span><span class="sxs-lookup"><span data-stu-id="749d4-739">These Android best practices will reduce the likelihood of failure:</span></span>

* <span data-ttu-id="749d4-740">Funções do SDK do Android que podem retornar valores nulos agora têm maior alta probabilidade de ser nulas.</span><span class="sxs-lookup"><span data-stu-id="749d4-740">Android SDK functions that may return null have a higher likelihood of being null now.</span></span>  <span data-ttu-id="749d4-741">Para minimizar problemas, certifique-se de que verificações nulas estejam nos lugares certos.</span><span class="sxs-lookup"><span data-stu-id="749d4-741">To minimize issues, ensure that null checks are in the right places.</span></span>

* <span data-ttu-id="749d4-742">Recursos que podem ser verificados devem ser verificados por meio de suas APIs de substituição do MAM.</span><span class="sxs-lookup"><span data-stu-id="749d4-742">Features that can be checked for must be checked for through their MAM replacement APIs.</span></span>

* <span data-ttu-id="749d4-743">Quaisquer funções derivadas devem chamar por meio de suas versões de superclasse.</span><span class="sxs-lookup"><span data-stu-id="749d4-743">Any derived functions must call through to their super class versions.</span></span>

* <span data-ttu-id="749d4-744">Evite o uso de qualquer API de forma ambígua.</span><span class="sxs-lookup"><span data-stu-id="749d4-744">Avoid use of any API in an ambiguous way.</span></span> <span data-ttu-id="749d4-745">Por exemplo, usar `Activity.startActivityForResult` sem verificar o requestCode causará um comportamento estranho.</span><span class="sxs-lookup"><span data-stu-id="749d4-745">For example, using `Activity.startActivityForResult` without checking the requestCode will cause strange behavior.</span></span>

## <span data-ttu-id="749d4-746">Práticas recomendadas de Android</span><span class="sxs-lookup"><span data-stu-id="749d4-746">Recommended Android best practices</span></span>
<a id="recommended-android-best-practices" class="xliff"></a>

* <span data-ttu-id="749d4-747">Todos os projetos de biblioteca devem compartilhar o mesmo android:package sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="749d4-747">All library projects should share the same android:package where possible.</span></span> <span data-ttu-id="749d4-748">Isso não falhará esporadicamente em tempo de execução; este é essencialmente um problema de tempo de compilação.</span><span class="sxs-lookup"><span data-stu-id="749d4-748">This will not sporadically fail in run-time; this is purely a build-time problem.</span></span> <span data-ttu-id="749d4-749">As versões mais recentes do SDK do aplicativo do Intune removerão parte da redundância.</span><span class="sxs-lookup"><span data-stu-id="749d4-749">Newer versions of the Intune App SDK will remove some of the redundancy.</span></span>

* <span data-ttu-id="749d4-750">Use das ferramentas de compilação do SDK do Android mais recentes.</span><span class="sxs-lookup"><span data-stu-id="749d4-750">Use the newest Android SDK build tools.</span></span>

* <span data-ttu-id="749d4-751">Remova todas as bibliotecas desnecessárias e não utilizadas (por exemplo, android.support.v4)</span><span class="sxs-lookup"><span data-stu-id="749d4-751">Remove all unnecessary and unused libraries (e.g. android.support.v4)</span></span>
