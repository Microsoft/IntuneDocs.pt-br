---
title: Adicionar e atribuir aplicativos MTD ao Intune
titleSuffix: Intune on Azure
description: "Adicionar aplicativos MTD, o aplicativo Microsoft Authenticator e a política de configuração do iOS ao Intune no Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7b3fb86648a86b161eadfc071bdacbfd4ea0222f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="fbeee-103">Adicionar e atribuir aplicativos MTD (Defesa contra Ameaças Móveis) com o Intune</span><span class="sxs-lookup"><span data-stu-id="fbeee-103">Add and assign Mobile Threat Defense (MTD) apps with Intune</span></span>
<a id="add-and-assign-mobile-threat-defense-mtd-apps-with-intune" class="xliff"></a>

<span data-ttu-id="fbeee-104">Você pode usar o Intune para adicionar e implantar aplicativos MTD para que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.</span><span class="sxs-lookup"><span data-stu-id="fbeee-104">You can use Intune to add and deploy MTD apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="fbeee-105">Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fbeee-105">For iOS devices, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD.</span></span> <span data-ttu-id="fbeee-106">Além disso, você precisará da política de configuração de aplicativo iOS que indica qual aplicativo MTD iOS deve ser usado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="fbeee-106">Additionally, you need the iOS app configuration policy which signals the MTD iOS app to use with Intune.</span></span>

> [!TIP]
> <span data-ttu-id="fbeee-107">O Portal da Empresa do Intune funciona como o agente em dispositivos Android para as identidades dos usuários possam ser verificadas pelo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fbeee-107">The Intune company portal works as the broker on Android devices so users can have their identities checked by Azure AD.</span></span>

## <span data-ttu-id="fbeee-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fbeee-108">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

-   <span data-ttu-id="fbeee-109">As etapas a seguir devem ser concluídas no [Portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="fbeee-109">The below steps need to be completed in the [Azure portal](https://portal.azure.com/).</span></span>

-   <span data-ttu-id="fbeee-110">Verifique se que você está familiarizado com o processo de:</span><span class="sxs-lookup"><span data-stu-id="fbeee-110">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="fbeee-111">[Adicionar um aplicativo no Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-111">[Adding an app into Intune](apps-add.md).</span></span>

    -   <span data-ttu-id="fbeee-112">[Adicionar uma política de configuração de aplicativo do iOS no Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="fbeee-112">[Adding an iOS app configuration policy into Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="fbeee-113">[Atribuindo um aplicativo com o Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="fbeee-113">[Assigning an app with Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="fbeee-114">[ Adicionando uma política de configuração de aplicativo iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="fbeee-114">[ Adding an iOS app configuration policy](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <span data-ttu-id="fbeee-115">Adicionar aplicativos</span><span class="sxs-lookup"><span data-stu-id="fbeee-115">To add apps</span></span>
<a id="to-add-apps" class="xliff"></a>

### <span data-ttu-id="fbeee-116">Aplicativo Skycure para Android</span><span class="sxs-lookup"><span data-stu-id="fbeee-116">Skycure app for Android</span></span>
<a id="skycure-app-for-android" class="xliff"></a>

- <span data-ttu-id="fbeee-117">Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-117">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="fbeee-118">Use esta [URL da loja de aplicativos do Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) na **etapa 7**.</span><span class="sxs-lookup"><span data-stu-id="fbeee-118">Use this [Skycure app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) on **step 7**.</span></span>

### <span data-ttu-id="fbeee-119">Aplicativo Skycure para iOS</span><span class="sxs-lookup"><span data-stu-id="fbeee-119">Skycure app for iOS</span></span>
<a id="skycure-app-for-ios" class="xliff"></a>

- <span data-ttu-id="fbeee-120">Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-120">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="fbeee-121">Use esta [URL da loja de aplicativos do Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="fbeee-121">Use this [Skycure app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <span data-ttu-id="fbeee-122">Aplicativo Microsoft Authenticator para iOS</span><span class="sxs-lookup"><span data-stu-id="fbeee-122">Microsoft Authenticator app for iOS</span></span>
<a id="microsoft-authenticator-app-for-ios" class="xliff"></a>

- <span data-ttu-id="fbeee-123">Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-123">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="fbeee-124">Use esta [URL da loja de aplicativos do Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="fbeee-124">Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <span data-ttu-id="fbeee-125">Aplicativo Lookout for Work Android</span><span class="sxs-lookup"><span data-stu-id="fbeee-125">Lookout for work Android app</span></span>
<a id="lookout-for-work-android-app" class="xliff"></a>

- <span data-ttu-id="fbeee-126">Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-126">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="fbeee-127">Use esta [URL da loja de aplicativos da Google do Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) na **etapa 7**.</span><span class="sxs-lookup"><span data-stu-id="fbeee-127">Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) on **step 7**.</span></span>

### <span data-ttu-id="fbeee-128">Aplicativo Lookout for Work iOS</span><span class="sxs-lookup"><span data-stu-id="fbeee-128">Lookout for Work iOS app</span></span>
<a id="lookout-for-work-ios-app" class="xliff"></a>

- <span data-ttu-id="fbeee-129">Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-129">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="fbeee-130">Use esta [URL da loja de aplicativos do Lookout for Work iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="fbeee-130">Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <span data-ttu-id="fbeee-131">Aplicativo Lookout for Work fora da Apple store</span><span class="sxs-lookup"><span data-stu-id="fbeee-131">Lookout for Work app outside the Apple store</span></span>
<a id="lookout-for-work-app-outside-the-apple-store" class="xliff"></a>

<span data-ttu-id="fbeee-132">Será necessário reassinar o aplicativo Lookout for Work iOS.</span><span class="sxs-lookup"><span data-stu-id="fbeee-132">You need to re-sign the Lookout for Work iOS app.</span></span> <span data-ttu-id="fbeee-133">O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store.</span><span class="sxs-lookup"><span data-stu-id="fbeee-133">Lookout distributes its Lookout for Work iOS app outside of the iOS App Store.</span></span> <span data-ttu-id="fbeee-134">Antes de distribuir o aplicativo, você deverá reassiná-lo com seu iOS Enterprise Developer Certificate.</span><span class="sxs-lookup"><span data-stu-id="fbeee-134">Before distributing the app, you must re-sign the app with your iOS Enterprise Developer Certificate.</span></span>

<span data-ttu-id="fbeee-135">Para obter instruções detalhadas sobre como reassinar o aplicativo Lookout for Work iOS, consulte [Processo para reassinar o aplicativo Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.</span><span class="sxs-lookup"><span data-stu-id="fbeee-135">For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout website.</span></span>

#### <span data-ttu-id="fbeee-136">Habilitar a autenticação do Azure AD para o aplicativo Lookout for Work iOS</span><span class="sxs-lookup"><span data-stu-id="fbeee-136">Enable Azure AD authentication for Lookout for Work iOS app</span></span>
<a id="enable-azure-ad-authentication-for-lookout-for-work-ios-app" class="xliff"></a>

<span data-ttu-id="fbeee-137">Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="fbeee-137">Enable Azure Active Directory authentication for the iOS users by doing the following:</span></span>

1. <span data-ttu-id="fbeee-138">Acesse o [Portal do Azure](https://portal.sazure.com), entre com suas credenciais e navegue para a página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fbeee-138">Go to the [Azure portal](https://portal.sazure.com), sign in with your credentials, then navigate to the application page.</span></span>
  
2. <span data-ttu-id="fbeee-139">Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.</span><span class="sxs-lookup"><span data-stu-id="fbeee-139">Add the **Lookout for Work iOS app** as a **native client application**.</span></span>

3. <span data-ttu-id="fbeee-140">Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.</span><span class="sxs-lookup"><span data-stu-id="fbeee-140">Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.</span></span>

4.  <span data-ttu-id="fbeee-141">Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.</span><span class="sxs-lookup"><span data-stu-id="fbeee-141">Add additional redirect URI: **&lt;companyportal://code/>** followed by a URL encoded version of your original redirect URI.</span></span>

5.  <span data-ttu-id="fbeee-142">Adicione **Permissões delegadas** ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fbeee-142">Add **Delegated Permissions** to your app.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="fbeee-143">Consulte [Configurar um aplicativo cliente nativo com o Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) para ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="fbeee-143">See [configure a native client application with Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) for more details.</span></span>

#### <span data-ttu-id="fbeee-144">Adicionar o arquivo ipa do Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="fbeee-144">Add the Lookout for Work ipa file</span></span>
<a id="add-the-lookout-for-work-ipa-file" class="xliff"></a>

- <span data-ttu-id="fbeee-145">Carregue o arquivo .ipa reassinado conforme descrito no tópico [Adicionar aplicativos iOS LOB com o Intune](lob-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-145">Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](lob-apps-ios.md) topic.</span></span> <span data-ttu-id="fbeee-146">Também será necessário definir a versão mínima do sistema operacional para iOS 8.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="fbeee-146">You also need to set the minimum OS version to iOS 8.0 or later.</span></span>

## <span data-ttu-id="fbeee-147">Associar o aplicativo MTD a uma política de configuração de aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="fbeee-147">To associate the MTD app with an iOS app configuration policy</span></span>
<a id="to-associate-the-mtd-app-with-an-ios-app-configuration-policy" class="xliff"></a>

### <span data-ttu-id="fbeee-148">Para Skycure</span><span class="sxs-lookup"><span data-stu-id="fbeee-148">For Skycure</span></span>
<a id="for-skycure" class="xliff"></a>

-   <span data-ttu-id="fbeee-149">Use a mesma conta do Azure AD previamente configurada no Console de gerenciamento do Skycure, que deve ser a mesma conta usada para fazer logon no console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="fbeee-149">Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic console.</span></span>

-   <span data-ttu-id="fbeee-150">O arquivo de integração do Skycure precisa estar pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="fbeee-150">You need to have the Skycure integration file ready to use.</span></span> <span data-ttu-id="fbeee-151">Este é o arquivo .zip baixado anteriormente do console de Gerenciamento do Skycure, que contém o arquivo **skycure\_configuration.plist** com os parâmetros da política de configuração de aplicativo do iOS.</span><span class="sxs-lookup"><span data-stu-id="fbeee-151">This is the .zip file previously downloaded from the Skycure Management console, which contains the file **skycure\_configuration.plist** with the iOS app configuration policy parameters.</span></span>

- <span data-ttu-id="fbeee-152">Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do Skycure.</span><span class="sxs-lookup"><span data-stu-id="fbeee-152">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Skycure iOS app configuration policy.</span></span>
    - <span data-ttu-id="fbeee-153">Na etapa 8, use a opção **Inserir dados XML**, copie o conteúdo do arquivo **skycure_configuration.plist** e cole seu conteúdo no corpo da política de configuração.</span><span class="sxs-lookup"><span data-stu-id="fbeee-153">On step 8, use the option **Enter XML data**, copy the content from the **skycure_configuration.plist** file and paste its content into the configuration policy body.</span></span>

<span data-ttu-id="fbeee-154">Você também pode copiar o conteúdo **skycure_configuration.plist** aqui:</span><span class="sxs-lookup"><span data-stu-id="fbeee-154">You can also copy the **skycure_configuration.plist** content from here:</span></span>

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <span data-ttu-id="fbeee-155">Para Lookout</span><span class="sxs-lookup"><span data-stu-id="fbeee-155">For Lookout</span></span>
<a id="for-lookout" class="xliff"></a>

- <span data-ttu-id="fbeee-156">Crie a política de configuração do aplicativo iOS conforme descrito no tópico [usando a política de configuração de aplicativo iOS](app-configuration-policies-use-ios.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-156">Create the iOS app configuration policy as described in the [using iOS app configuration policy](app-configuration-policies-use-ios.md) topic.</span></span>

## <span data-ttu-id="fbeee-157">Atribuir aplicativos MTD</span><span class="sxs-lookup"><span data-stu-id="fbeee-157">To assign MTD apps</span></span>
<a id="to-assign-mtd-apps" class="xliff"></a>

- <span data-ttu-id="fbeee-158">Consulte as instruções para [atribuir aplicativos a grupos com o Intune](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="fbeee-158">See the instructions for [assigning apps to groups with Intune](apps-deploy.md).</span></span>

## <span data-ttu-id="fbeee-159">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="fbeee-159">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="fbeee-160">[Configurar a integração de Skycure com o Intune](skycure-mtd-connector-integration.md)
[Configurar a integração do Lookout com o Intune](lookout-mtd-connector-integration.md)</span><span class="sxs-lookup"><span data-stu-id="fbeee-160">[Set up the Skycure integration with Intune](skycure-mtd-connector-integration.md)
[Set up the Lookout integration with Intune](lookout-mtd-connector-integration.md)</span></span>
