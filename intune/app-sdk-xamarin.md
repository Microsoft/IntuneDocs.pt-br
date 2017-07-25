---
title: Componente Xamarin do SDK de Aplicativo do Microsoft Intune
description: 
keywords: sdk, Xamarin, intune
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b900cb2c2c02ca96a771dbebd208872941079e38
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="11199-103">Componente Xamarin do SDK de Aplicativo do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="11199-103">Microsoft Intune App SDK Xamarin Component</span></span>
<a id="microsoft-intune-app-sdk-xamarin-component" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="11199-104">Primeiro, leia o artigo [Introdução ao SDK de Aplicativo do Intune](app-sdk-get-started.md), que explica como se preparar para a integração em cada plataforma com suporte.</span><span class="sxs-lookup"><span data-stu-id="11199-104">You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>



## <span data-ttu-id="11199-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="11199-105">Overview</span></span>
<a id="overview" class="xliff"></a>
<span data-ttu-id="11199-106">O [componente do Microsoft Intune App SDK Xamarin](https://components.xamarin.com/view/microsoft.intune.mam) habilita a [política de proteção de aplicativo do Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) em aplicativos Android e iOS criados com o Xamarin.</span><span class="sxs-lookup"><span data-stu-id="11199-106">The [Intune App SDK Xamarin component](https://components.xamarin.com/view/microsoft.intune.mam) enables [Intune app protection policy](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Xamarin.</span></span> <span data-ttu-id="11199-107">O componente permite que os desenvolvedores incorporem facilmente recursos de proteção de aplicativo do Intune em seus aplicativos baseados em Xamarin.</span><span class="sxs-lookup"><span data-stu-id="11199-107">The component allows developers to easily build in Intune app protection features into their Xamarin-based app.</span></span>

<span data-ttu-id="11199-108">Você descobrirá que é possível habilitar os recursos do SDK sem alterar o comportamento do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="11199-108">You will find that you can enable SDK features without changing your app’s behavior.</span></span> <span data-ttu-id="11199-109">Após você ter incorporado o componente em seu aplicativo móvel iOS ou Android, o administrador de TI poderá implantar a política por meio do Microsoft Intune MAM (gerenciamento de aplicativo móvel) para dar suporte a vários recursos de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="11199-109">Once you've built the component into your iOS or Android mobile app, the IT admin will be able to deploy policy via Microsoft Intune Mobile Application Management (MAM) supporting a variety of data protection features.</span></span>

## <span data-ttu-id="11199-110">Para que há suporte?</span><span class="sxs-lookup"><span data-stu-id="11199-110">What's supported?</span></span>
<a id="whats-supported" class="xliff"></a>

### <span data-ttu-id="11199-111">Computadores de desenvolvedores</span><span class="sxs-lookup"><span data-stu-id="11199-111">Developer machines</span></span>
<a id="developer-machines" class="xliff"></a>
* <span data-ttu-id="11199-112">Windows</span><span class="sxs-lookup"><span data-stu-id="11199-112">Windows</span></span>


### <span data-ttu-id="11199-113">Plataformas de aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="11199-113">Mobile app platforms</span></span>
<a id="mobile-app-platforms" class="xliff"></a>
* <span data-ttu-id="11199-114">Android</span><span class="sxs-lookup"><span data-stu-id="11199-114">Android</span></span>
* <span data-ttu-id="11199-115">iOS</span><span class="sxs-lookup"><span data-stu-id="11199-115">iOS</span></span>


### <span data-ttu-id="11199-116">Cenários de gerenciamento de aplicativo móvel do Intune</span><span class="sxs-lookup"><span data-stu-id="11199-116">Intune Mobile Application Management scenarios</span></span>
<a id="intune-mobile-application-management-scenarios" class="xliff"></a>

* <span data-ttu-id="11199-117">Dispositivos registrados no MDM do Intune</span><span class="sxs-lookup"><span data-stu-id="11199-117">Intune MDM-enrolled devices</span></span>
* <span data-ttu-id="11199-118">Dispositivos registrados em EMM de terceiros</span><span class="sxs-lookup"><span data-stu-id="11199-118">Third-party EMM-enrolled devices</span></span>
* <span data-ttu-id="11199-119">Dispositivos não gerenciados (não registrados com em nenhum MDM)</span><span class="sxs-lookup"><span data-stu-id="11199-119">Unmanaged devices (not enrolled with any MDM)</span></span>

<span data-ttu-id="11199-120">Aplicativos Xamarin criados com o Componente Xamarin do SDK de Aplicativo do Intune agora podem receber políticas de MAM (gerenciamento de aplicativo móvel) em dispositivos registrados no MDM (gerenciamento de dispositivo móvel) do Intune e em dispositivos não registrados.</span><span class="sxs-lookup"><span data-stu-id="11199-120">Xamarin apps built with the Intune App SDK Xamarin Component can now receive Intune mobile application management (MAM) policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.</span></span>

## <span data-ttu-id="11199-121">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="11199-121">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

* <span data-ttu-id="11199-122">**[Somente Android]** O aplicativo de Portal da Empresa do Microsoft Intune mais recente sempre deve estar instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="11199-122">**[Android only]** The latest Microsoft Intune Company Portal app must always be installed on the device.</span></span>

## <span data-ttu-id="11199-123">Introdução</span><span class="sxs-lookup"><span data-stu-id="11199-123">Get started</span></span>
<a id="get-started" class="xliff"></a>

1.  <span data-ttu-id="11199-124">Baixe o arquivo **Xamarin-component.exe** [aqui](https://components.xamarin.com/submit/xpkg) e extraia o arquivo.</span><span class="sxs-lookup"><span data-stu-id="11199-124">Download **Xamarin-component.exe** from [here](https://components.xamarin.com/submit/xpkg) and extract it.</span></span>

2. <span data-ttu-id="11199-125">Leia os [termos de licença](https://components.xamarin.com/license/microsoft.intune.mam) do Componente Xamarin para MAM no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="11199-125">Read the [license terms](https://components.xamarin.com/license/microsoft.intune.mam) for the Microsoft Intune MAM Xamarin Component.</span></span>

3.  <span data-ttu-id="11199-126">Baixar a pasta do Componente Xamarin do SDK de Aplicativo do Intune do [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) ou do [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) e extraia.</span><span class="sxs-lookup"><span data-stu-id="11199-126">Download the Intune App SDK Xamarin Component folder from [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) or [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) and extract it.</span></span> <span data-ttu-id="11199-127">Os arquivos baixados na etapa 1 e na etapa 3 deve estar no mesmo nível de diretório.</span><span class="sxs-lookup"><span data-stu-id="11199-127">Both files downloaded from step 1 and step 3 should be in the same directory level.</span></span>

4.  <span data-ttu-id="11199-128">Na linha de comando como administrador, execute `Xamarin.Component.exe install <.xam> file`.</span><span class="sxs-lookup"><span data-stu-id="11199-128">In the command line as an administrator, run `Xamarin.Component.exe install <.xam> file`.</span></span>

5.  <span data-ttu-id="11199-129">No Visual Studio, clique com o botão direito do mouse em **componentes** no seu projeto Xamarin criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="11199-129">In Visual Studio, right click **components** in your previously created Xamarin project.</span></span>

6.  <span data-ttu-id="11199-130">Selecione **Editar Componentes** e adicione o componente do SDK de Aplicativo do Intune que você baixou localmente em seu computador.</span><span class="sxs-lookup"><span data-stu-id="11199-130">Select **Edit Components** and add the Intune App SDK component you’ve downloaded locally to your computer.</span></span>



## <span data-ttu-id="11199-131">Habilitar o MAM do Intune em seu aplicativo móvel iOS</span><span class="sxs-lookup"><span data-stu-id="11199-131">Enabling Intune MAM in your iOS mobile app</span></span>
<a id="enabling-intune-mam-in-your-ios-mobile-app" class="xliff"></a>
1.  <span data-ttu-id="11199-132">Para inicializar o SDK de Aplicativo do Intune, você precisará fazer uma chamada de API na classe `AppDelegate.cs`.</span><span class="sxs-lookup"><span data-stu-id="11199-132">In order to initialize the Intune App SDK, you will need to make a call for any API in the `AppDelegate.cs` class.</span></span> <span data-ttu-id="11199-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="11199-133">For example:</span></span>

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  <span data-ttu-id="11199-134">Agora que o componente foi adicionado e inicializado, você pode seguir as etapas gerais necessárias para a criação do SDK de Aplicativo em um aplicativo móvel iOS.</span><span class="sxs-lookup"><span data-stu-id="11199-134">Now that the component is added and initialized, you can follow the general steps required for building the App SDK into an iOS mobile app.</span></span> <span data-ttu-id="11199-135">Você pode encontrar a documentação completa para habilitar aplicativos iOS nativos no [Guia do SDK de Aplicativos do Intune para desenvolvedores de iOS](app-sdk-ios.md).</span><span class="sxs-lookup"><span data-stu-id="11199-135">You can find the full documentation for enabling native iOS apps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md).</span></span>
3. <span data-ttu-id="11199-136">**Importante**: há várias modificações específicas para aplicativos iOS baseados em Xamarin.</span><span class="sxs-lookup"><span data-stu-id="11199-136">**Important**: There are several modifications specific to Xamarin-based iOS apps.</span></span> <span data-ttu-id="11199-137">Por exemplo, ao habilitar grupos de conjunto de chaves, você precisará adicionar o seguinte para incluir o aplicativo de exemplo do Xamarin que incluímos no componente.</span><span class="sxs-lookup"><span data-stu-id="11199-137">For instance, when enabling keychain groups, you'll need to add the following to include the Xamarin sample app we included in the component.</span></span> <span data-ttu-id="11199-138">Veja abaixo um exemplo dos grupos que você precisaria ter em seus grupos de Acesso de Conjunto de Chaves:</span><span class="sxs-lookup"><span data-stu-id="11199-138">Below is an example of the groups you would need to have in your Keychain Access groups:</span></span>

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

<span data-ttu-id="11199-139">Você concluiu as etapas necessárias para incorporar o componente em seu aplicativo iOS baseado em Xamarin.</span><span class="sxs-lookup"><span data-stu-id="11199-139">You have completed the steps necessary to build the component into your Xamarin-based iOS app.</span></span> <span data-ttu-id="11199-140">Se estiver utilizando o Xcode para criar seu projeto, você poderá usar o `Intune App SDK Settings.bundle`.</span><span class="sxs-lookup"><span data-stu-id="11199-140">If you are utilizing Xcode for building your project, you can use the `Intune App SDK Settings.bundle`.</span></span> <span data-ttu-id="11199-141">Isso permitirá ativar e desativar as configurações de política do Intune conforme você criar seu projeto para testar e depurar.</span><span class="sxs-lookup"><span data-stu-id="11199-141">This will allow you to toggle Intune policy settings on and off as you build your project to test and debug.</span></span> <span data-ttu-id="11199-142">Para tirar proveito desse pacote, siga as etapas em [Guia do SDK de Aplicativos do Intune para desenvolvedores de iOS](app-sdk-ios.md) e leia a seção sobre [depuração no Xcode](app-sdk-ios.md#status-result-and-debug-notifications).</span><span class="sxs-lookup"><span data-stu-id="11199-142">To take advantage of this bundle, follow the steps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md) and read the section on [debugging in Xcode](app-sdk-ios.md#status-result-and-debug-notifications).</span></span>

## <span data-ttu-id="11199-143">Habilitando MAM em seu aplicativo móvel Android</span><span class="sxs-lookup"><span data-stu-id="11199-143">Enabling MAM in your Android mobile app</span></span>
<a id="enabling-mam-in-your-android-mobile-app" class="xliff"></a>
<span data-ttu-id="11199-144">Para aplicativos Android baseados em Xamarin que não usam uma estrutura de interface do usuário, você precisará ler e seguir o [Guia de desenvolvedores do SDK de Aplicativos do Intune para Android].</span><span class="sxs-lookup"><span data-stu-id="11199-144">For Xamarin-based Android apps not using a UI framework, you will need to read and follow the [Intune App SDK for Android Developer Guide].</span></span> <span data-ttu-id="11199-145">Para seu aplicativo Android baseado em Xamarin, você precisará substituir classe, métodos e atividades pelos equivalentes do MAM com base na [tabela](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) incluída no guia.</span><span class="sxs-lookup"><span data-stu-id="11199-145">For your Xamarin-based Android app, you will need to replace class, methods, and activities with their MAM equivalent based on the [table](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) included in the guide.</span></span> <span data-ttu-id="11199-146">Se o seu aplicativo não definir uma classe `android.app.Application`, você precisará criar uma e certificar-se de herdar de `MAMApplication`.</span><span class="sxs-lookup"><span data-stu-id="11199-146">If your app doesn’t define an `android.app.Application` class, you will need to create one and ensure that you inherit from `MAMApplication`.</span></span>

<span data-ttu-id="11199-147">Para Formulários do Xamarin e outras estruturas de interface do usuário, fornecemos uma ferramenta chamada `MAM.Remapper`.</span><span class="sxs-lookup"><span data-stu-id="11199-147">For Xamarin Forms and other UI frameworks, we have provided a tool called `MAM.Remapper`.</span></span> <span data-ttu-id="11199-148">A ferramenta realizará a substituição da classe para você.</span><span class="sxs-lookup"><span data-stu-id="11199-148">The tool will accomplish the class replacement for you.</span></span> <span data-ttu-id="11199-149">No entanto, você precisará realizar as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="11199-149">However, you will need to do the following steps:</span></span>

1.  <span data-ttu-id="11199-150">Adicione uma referência ao` Microsoft.Intune.MAM.Remapper.Tasks` pacote NuGet 0.1.0.0 ou superior.</span><span class="sxs-lookup"><span data-stu-id="11199-150">Add a reference to the` Microsoft.Intune.MAM.Remapper.Tasks` nuget package version 0.1.0.0 or greater.</span></span>

2.  <span data-ttu-id="11199-151">Adicione a seguinte linha ao seu csproj Android:</span><span class="sxs-lookup"><span data-stu-id="11199-151">Add the following line to your Android csproj:</span></span>
  ```xml
  <Import
  Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
  ```

3.  <span data-ttu-id="11199-152">Defina a ação de build do arquivo `remapping-config.json` adicionado como **RemappingConfigFile**.</span><span class="sxs-lookup"><span data-stu-id="11199-152">Set the build action of the added `remapping-config.json` file to **RemappingConfigFile**.</span></span> <span data-ttu-id="11199-153">O `remapping-config.json` incluído só funciona com Xamarin.Forms.</span><span class="sxs-lookup"><span data-stu-id="11199-153">The included `remapping-config.json` only works with Xamarin.Forms.</span></span> <span data-ttu-id="11199-154">Para outras estruturas de interface do usuário, consulte o arquivo Leiame incluído no pacote NuGet Remapper.</span><span class="sxs-lookup"><span data-stu-id="11199-154">For other UI frameworks, refer to the Readme included with the Remapper nuget package.</span></span>

## <span data-ttu-id="11199-155">Teste seu aplicativo</span><span class="sxs-lookup"><span data-stu-id="11199-155">Test your app</span></span>
<a id="test-your-app" class="xliff"></a>

<span data-ttu-id="11199-156">Você concluiu as etapas básicas da incorporação do componente ao seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="11199-156">You have completed the basic steps of building the component into your app.</span></span> <span data-ttu-id="11199-157">Agora, você pode seguir as etapas incluídas no aplicativo de exemplo de Xamarin para Android.</span><span class="sxs-lookup"><span data-stu-id="11199-157">Now you can follow the steps included in the Xamarin Android sample app.</span></span> <span data-ttu-id="11199-158">Nós fornecemos dois exemplos, um para Xamarin.Forms e outro para o Android.</span><span class="sxs-lookup"><span data-stu-id="11199-158">We have provided two samples, one for Xamarin.Forms and another for Android.</span></span>
