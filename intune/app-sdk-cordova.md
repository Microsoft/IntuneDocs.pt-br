---
title: Plug-in Cordova do SDK de Aplicativo do Microsoft Intune
description: 
keywords: sdk, Cordova, intune
author: oydang
manager: angrobe
ms.author: oydang
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0329720b6f02c718ef27a59e6efc5f3a76eed1c5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="85510-103">Plug-in Cordova do SDK de Aplicativo do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="85510-103">Microsoft Intune App SDK Cordova Plugin</span></span>
<a id="microsoft-intune-app-sdk-cordova-plugin" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="85510-104">Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.</span><span class="sxs-lookup"><span data-stu-id="85510-104">You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>

## <span data-ttu-id="85510-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="85510-105">Overview</span></span>
<a id="overview" class="xliff"></a>

<span data-ttu-id="85510-106">O [Plug-in Cordova do SDK de Aplicativo do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) nos aplicativos iOS e Android criados com Cordova.</span><span class="sxs-lookup"><span data-stu-id="85510-106">The [Intune App SDK Cordova Plugin](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Cordova.</span></span> <span data-ttu-id="85510-107">O plug-in permite que os desenvolvedores integrem os recursos de proteção de dados e aplicativos do Intune em seu aplicativo baseado no Cordova.</span><span class="sxs-lookup"><span data-stu-id="85510-107">The plugin allows developers to integrate Intune app and data protection features into their Cordova-based app.</span></span>

<span data-ttu-id="85510-108">Você descobrirá que é possível habilitar os recursos do SDK sem alterar o comportamento do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="85510-108">You will find that you can enable SDK features without changing your app's behavior.</span></span> <span data-ttu-id="85510-109">Depois de compilar o plug-in em seu aplicativo iOS ou Android, o administrador do Microsoft Intune será capaz de implantar a política de proteção de aplicativo do Intune, que é composta por uma vários recursos de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="85510-109">Once you have built the plugin into your iOS or Android app, the Microsoft Intune administrator will be able to deploy Intune app protection policy, which consists of a variety of data protection features.</span></span> <span data-ttu-id="85510-110">O plug-in é compilado para que a maioria das etapas sejam realizadas automaticamente no processo de build do Cordova.</span><span class="sxs-lookup"><span data-stu-id="85510-110">The plugin is built so that most of the steps are automatically performed in the Cordova build process.</span></span> <span data-ttu-id="85510-111">Como resultado, você deve ser capaz de habilitar rapidamente seu aplicativo para proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="85510-111">As a result, you should be able to get your app enabled for Intune app protection quickly.</span></span> <span data-ttu-id="85510-112">Para começar, siga as etapas abaixo com base em sua plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="85510-112">To get started, follow the steps below based on your target platform.</span></span>

## <span data-ttu-id="85510-113">Plataformas suportadas</span><span class="sxs-lookup"><span data-stu-id="85510-113">Supported Platforms</span></span>
<a id="supported-platforms" class="xliff"></a>

* <span data-ttu-id="85510-114">O plug-in funciona nos sistemas operacionais Windows, Mac e Linux</span><span class="sxs-lookup"><span data-stu-id="85510-114">The plugin works on Windows, Mac and Linux OS</span></span>
* <span data-ttu-id="85510-115">O plug-in funciona para aplicativos Android com `minSdkVersion` >= 14 e `targetSdkVersion` <= 24</span><span class="sxs-lookup"><span data-stu-id="85510-115">The plugin works for Android apps with `minSdkVersion` >= 14 and `targetSdkVersion` <= 24</span></span>
* <span data-ttu-id="85510-116">O plug-in funciona para aplicativos iOS direcionados para iOS 9.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="85510-116">The plugin works for iOS apps targeted for iOS 9.0 and above.</span></span>

## <span data-ttu-id="85510-117">Cenários de gerenciamento de aplicativo móvel do Intune</span><span class="sxs-lookup"><span data-stu-id="85510-117">Intune Mobile Application Management scenarios</span></span>
<a id="intune-mobile-application-management-scenarios" class="xliff"></a>

* <span data-ttu-id="85510-118">Dispositivos registrados no MDM do Intune</span><span class="sxs-lookup"><span data-stu-id="85510-118">Intune MDM-enrolled devices</span></span>
* <span data-ttu-id="85510-119">Dispositivos registrados em EMM de terceiros</span><span class="sxs-lookup"><span data-stu-id="85510-119">Third-party EMM-enrolled devices</span></span>
* <span data-ttu-id="85510-120">Dispositivos não gerenciados (não registrados com em nenhum MDM)</span><span class="sxs-lookup"><span data-stu-id="85510-120">Unmanaged devices (not enrolled with any MDM)</span></span>

<span data-ttu-id="85510-121">Os aplicativos Cordova criados com o Plug-in Cordova do SDK de Aplicativo do Intune agora podem receber políticas de proteção de aplicativo em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.</span><span class="sxs-lookup"><span data-stu-id="85510-121">Cordova apps built with the Intune App SDK Cordova Plugin can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.</span></span>

## <span data-ttu-id="85510-122">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="85510-122">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

### <span data-ttu-id="85510-123">Android</span><span class="sxs-lookup"><span data-stu-id="85510-123">Android</span></span>
<a id="android" class="xliff"></a>

* <span data-ttu-id="85510-124">O aplicativo de Portal da Empresa do Microsoft Intune mais recente sempre deve estar instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85510-124">The latest Microsoft Intune Company Portal app must always be installed on the device.</span></span>
* <span data-ttu-id="85510-125">É necessário ter, no mínimo, Java 7 no caminho onde você executará a compilação do Cordova ao usar o plug-in.</span><span class="sxs-lookup"><span data-stu-id="85510-125">Java 7 at minimum must be on the path where you will execute Cordova build when using the plugin.</span></span>

### <span data-ttu-id="85510-126">iOS</span><span class="sxs-lookup"><span data-stu-id="85510-126">iOS</span></span>
<a id="ios" class="xliff"></a>

* <span data-ttu-id="85510-127">O aplicativo de Portal da Empresa do Microsoft Intune mais recente deve estar instalado no dispositivo para poder contar com os recursos de MDM.</span><span class="sxs-lookup"><span data-stu-id="85510-127">The latest Microsoft Intune Company Portal app must be installed on the device for MDM features.</span></span> <span data-ttu-id="85510-128">Ele *não* é necessário para a política de proteção de aplicativo do Intune sem recursos de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85510-128">It is *not* needed for Intune app protection policy without device enrollment features.</span></span>

### <span data-ttu-id="85510-129">As duas plataformas</span><span class="sxs-lookup"><span data-stu-id="85510-129">Both platforms</span></span>
<a id="both-platforms" class="xliff"></a>

* <span data-ttu-id="85510-130">A versão 0.8.0+ do [plug-in da ADAL (Biblioteca de Autenticação do Azure Active Directory) para Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) é necessária.</span><span class="sxs-lookup"><span data-stu-id="85510-130">Version 0.8.0+ of the [Azure Active Directory Authentication Libraries (ADAL) plugin for Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) is required.</span></span>

> [!NOTE]
> <span data-ttu-id="85510-131">Devido a um bug do Apache Cordova registrado [aqui](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), os aplicativos que já têm a dependência do plug-in não atualizarão automaticamente o plug-in para a versão solicitada.</span><span class="sxs-lookup"><span data-stu-id="85510-131">Due to an Apache Cordova bug the filed [here](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), apps that already have the plugin dependency will not automatically upgrade the plugin to the requested version.</span></span>



## <span data-ttu-id="85510-132">Início rápido</span><span class="sxs-lookup"><span data-stu-id="85510-132">Quick start</span></span>
<a id="quick-start" class="xliff"></a>

1. <span data-ttu-id="85510-133">Atualize sua versão da ADAL:</span><span class="sxs-lookup"><span data-stu-id="85510-133">Update your version of ADAL:</span></span>

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. <span data-ttu-id="85510-134">Adicione o Plug-in Cordova do SDK de Aplicativo do Intune:</span><span class="sxs-lookup"><span data-stu-id="85510-134">Add the Intune App SDK for Cordova plugin:</span></span>

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <span data-ttu-id="85510-135">Compilar o plug-in em seu aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="85510-135">Build the plugin into your iOS app</span></span>
<a id="build-the-plugin-into-your-ios-app" class="xliff"></a>

<span data-ttu-id="85510-136">Você precisará concluir algumas etapas para que seu aplicativo seja habilitado para a política de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="85510-136">You'll need to complete some steps for your app to be enabled for Intune app protection policy.</span></span> <span data-ttu-id="85510-137">Por conveniência, essas etapas são executadas automaticamente no processo de compilação do Cordova como um gancho pré-compilação.</span><span class="sxs-lookup"><span data-stu-id="85510-137">For convenience, these steps are performed automatically in the Cordova build process as a pre-build hook.</span></span> <span data-ttu-id="85510-138">Como resultado, as etapas automatizadas modificarão seus arquivos `*.pbxproj`, `*-Info.plist` e `*.entitlements` que estão associados a uma configuração do projeto.</span><span class="sxs-lookup"><span data-stu-id="85510-138">As a result, the automated steps will modify your `*.pbxproj` , `*-Info.plist`, and `*.entitlements` files that are associated with a project configuration.</span></span> <span data-ttu-id="85510-139">Se seu projeto não contiver um arquivo de direitos, o plug-in criará um automaticamente.</span><span class="sxs-lookup"><span data-stu-id="85510-139">If your project doesn't contain an entitlements file, the plugin will create one automatically.</span></span>

<span data-ttu-id="85510-140">Essa configuração dá suporte a um único destino e executará a configuração no primeiro destino encontrado se houver vários destinos.</span><span class="sxs-lookup"><span data-stu-id="85510-140">This setup only supports a single target and will perform the configuration on the first target found if there are multiple targets.</span></span> <span data-ttu-id="85510-141">Se o processo falhar, verifique se:</span><span class="sxs-lookup"><span data-stu-id="85510-141">If the process fails, check that:</span></span>

1. <span data-ttu-id="85510-142">O projeto Xcode do seu aplicativo é `[name].xcodeproj`, em que `[name]` é o valor definido em `config.xml`</span><span class="sxs-lookup"><span data-stu-id="85510-142">Your app's Xcode project is `[name].xcodeproj` where `[name]` is the value defined in `config.xml`</span></span>
2. <span data-ttu-id="85510-143">O projeto usa a [estrutura de diretório de aplicativos padrão do Cordova](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).</span><span class="sxs-lookup"><span data-stu-id="85510-143">Your project uses the [standard Cordova app directory structure](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).</span></span>

## <span data-ttu-id="85510-144">Compilar o plug-in em seu aplicativo Android</span><span class="sxs-lookup"><span data-stu-id="85510-144">Build the plugin into your Android app</span></span>
<a id="build-the-plugin-into-your-android-app" class="xliff"></a>

1. <span data-ttu-id="85510-145">Importe esse plug-in com as ferramentas mais recentes do Cordova.</span><span class="sxs-lookup"><span data-stu-id="85510-145">Import this plugin with the latest Cordova tools.</span></span> <span data-ttu-id="85510-146">Automaticamente, o plug-in será invocado como uma etapa `after_compile`.</span><span class="sxs-lookup"><span data-stu-id="85510-146">The plugin will be automatically invoked as an `after_compile` step.</span></span>

2. <span data-ttu-id="85510-147">O plug-in criará uma versão habilitada para Intune de um APK interno (Android API 14+) no final do processo de build.</span><span class="sxs-lookup"><span data-stu-id="85510-147">The plugin will create a Intune-enabled version of a built apk (Android API 14+) at the end of the build process.</span></span> <span data-ttu-id="85510-148">A saída do build conterá um `[Project]-intunewrapped-[Build_Configuration].apk` (por exemplo, `helloWorld-intunewrapped-debug.apk`).</span><span class="sxs-lookup"><span data-stu-id="85510-148">The build output will contain a `[Project]-intunewrapped-[Build_Configuration].apk` (e.g. `helloWorld-intunewrapped-debug.apk`).</span></span>

> [!NOTE]
> <span data-ttu-id="85510-149">O plug-in somente dá suporte a compilações Gradle.</span><span class="sxs-lookup"><span data-stu-id="85510-149">The plugin only supports gradle builds.</span></span>

<span data-ttu-id="85510-150">Devido a um bug do Cordova registrado [aqui](https://issues.apache.org/jira/browse/CB-9434) que faz com que determinados ganchos do Cordova sejam ignorado no `cordova run`, para executar o aplicativo encapsulado na linha de comando, você deve fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="85510-150">Due to a Cordova bug filed [here](https://issues.apache.org/jira/browse/CB-9434) that causes certain Cordova hooks to be ignored on `cordova run`, to run the wrapped app from the command line, you must do the following:</span></span>

```shell
$ cordova build
$ cordova run --nobuild
```

## <span data-ttu-id="85510-151">Assinatura de seu aplicativo Android</span><span class="sxs-lookup"><span data-stu-id="85510-151">Sign your Android app</span></span>
<a id="sign-your-android-app" class="xliff"></a>

<span data-ttu-id="85510-152">O plug-in reconhece automaticamente as informações de assinatura fornecidas para o Cordova nos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="85510-152">The plugin automatically recognizes signing information you have provided to Cordova at the following locations:</span></span>

* <span data-ttu-id="85510-153">platforms/android/debug-signing.properties</span><span class="sxs-lookup"><span data-stu-id="85510-153">platforms/android/debug-signing.properties</span></span>
* <span data-ttu-id="85510-154">platforms/android/release-signing.properties</span><span class="sxs-lookup"><span data-stu-id="85510-154">platforms/android/release-signing.properties</span></span>
* <span data-ttu-id="85510-155">res/native/android/ant.properties</span><span class="sxs-lookup"><span data-stu-id="85510-155">res/native/android/ant.properties</span></span>

<span data-ttu-id="85510-156">Veja as [informações de assinatura gradle do Cordova](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) para saber mais sobre o formato esperado.</span><span class="sxs-lookup"><span data-stu-id="85510-156">See [the Cordova gradle signing information](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) for more information about the expected format.</span></span>

<span data-ttu-id="85510-157">No momento, não há suporte para a capacidade de fornecer informações de assinatura em `build.json` ou em locais aleatórios fornecidos via parâmetros à compilação do Cordova.</span><span class="sxs-lookup"><span data-stu-id="85510-157">We currently don't support the ability to provide signing information in `build.json` or arbitrary locations provided via parameters to Cordova build.</span></span>

## <span data-ttu-id="85510-158">Depuração do Visual Studio</span><span class="sxs-lookup"><span data-stu-id="85510-158">Debugging from Visual Studio</span></span>
<a id="debugging-from-visual-studio" class="xliff"></a>

<span data-ttu-id="85510-159">Após iniciar o aplicativo pela primeira vez, você verá uma caixa de diálogo informando que o aplicativo é gerenciado pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="85510-159">After launching the app for the first time you should see a dialog notifying you that the app is managed by Intune.</span></span> <span data-ttu-id="85510-160">Clique em "Não mostrar novamente" e clique no botão depurar/executar novamente do VS para que os pontos de interrupção sejam atingidos.</span><span class="sxs-lookup"><span data-stu-id="85510-160">Hit "Don't show again" and click the debug/run button again from VS for breakpoints to be hit.</span></span>

## <span data-ttu-id="85510-161">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="85510-161">Known Limitations</span></span>
<a id="known-limitations" class="xliff"></a>

### <span data-ttu-id="85510-162">Android</span><span class="sxs-lookup"><span data-stu-id="85510-162">Android</span></span>
<a id="android" class="xliff"></a>

* <span data-ttu-id="85510-163">Suporte incompleto para MultiDex.</span><span class="sxs-lookup"><span data-stu-id="85510-163">MultiDex support is incomplete.</span></span>
* <span data-ttu-id="85510-164">O aplicativo deve ter um `minSdkVersion` de 14 e um `targetSdkVersion` de 24 ou abaixo.</span><span class="sxs-lookup"><span data-stu-id="85510-164">App must have `minSdkVersion` of 14 and `targetSdkVersion` of 24 or below.</span></span> <span data-ttu-id="85510-165">No momento, não há suporte para aplicativos destinados à API 25</span><span class="sxs-lookup"><span data-stu-id="85510-165">We currently don't support apps targeting API 25</span></span>
* <span data-ttu-id="85510-166">Não podemos assinar novamente aplicativos assinados com o Esquema de assinatura V2.</span><span class="sxs-lookup"><span data-stu-id="85510-166">We cannot re-sign apps that were signed with the V2 Signature Scheme.</span></span> <span data-ttu-id="85510-167">Quando aplicativos assinados por V2 são agrupados com o plug-in, a saída .apk agrupada não é assinada.</span><span class="sxs-lookup"><span data-stu-id="85510-167">When V2-signed apps are wrapped by the plugin, the wrapped output .apk will be unsigned.</span></span>
*
  * <span data-ttu-id="85510-168">Desabilite a Assinatura V2 padrão do Cordova adicionando o seguinte ao seu arquivo `build-extras.gradle`:</span><span class="sxs-lookup"><span data-stu-id="85510-168">You can disable Cordova's default V2 Signing by adding the following to your `build-extras.gradle` file:</span></span>

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <span data-ttu-id="85510-169">iOS</span><span class="sxs-lookup"><span data-stu-id="85510-169">iOS</span></span>
<a id="ios" class="xliff"></a>

* <span data-ttu-id="85510-170">Sempre que modificar a lista de UTI no nó **CFBundleDocumentTypes** do arquivo **Info.plist**, você deve limpar o UTI do Intune na seção de UTIs Importados do mesmo arquivo plist (nó **UTImportedTypeDeclarations**) antes de compilar novamente.</span><span class="sxs-lookup"><span data-stu-id="85510-170">Whenever you modify the list of UTI's under the **CFBundleDocumentTypes** node of the **Info.plist** file, you must clear the Intune UTI's in the Imported UTI's section of the same plist file (**UTImportedTypeDeclarations** node) before building again.</span></span> <span data-ttu-id="85510-171">Todos os UTIs do Intune começarão com o prefixo `com.microsoft.intune.mam`.</span><span class="sxs-lookup"><span data-stu-id="85510-171">All of the Intune UTI's will start with the prefix `com.microsoft.intune.mam`.</span></span>

* <span data-ttu-id="85510-172">Se quiser remover o plug-in SDK de Aplicativo do Intune para Cordova de seu projeto Cordova, você também deverá remover a plataforma iOS e adicioná-la novamente para desfazer parte da configuração do Intune nos arquivos .xcodeproj e .plist.</span><span class="sxs-lookup"><span data-stu-id="85510-172">If you want to remove the Intune App SDK for Cordova plugin from your Cordova project, you must also remove the iOS platform and re-add it, in order to undo some of the Intune configuration in the .xcodeproj and .plist files.</span></span>
