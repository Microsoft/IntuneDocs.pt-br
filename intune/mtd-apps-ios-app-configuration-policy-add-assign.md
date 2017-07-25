---
title: Adicionar e atribuir aplicativos MTD ao Intune
titleSuffix: Intune on Azure
description: "Adicionar aplicativos MTD, o aplicativo Microsoft Authenticator e a política de configuração do iOS ao Intune no Azure"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7edd80c7bae429c1f4032cf59aaaf8d91786f92c
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
<<<<<<< HEAD
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a><span data-ttu-id="3ee1c-103">Adicionar e atribuir aplicativos MTD (Defesa contra Ameaças Móveis) com o Intune</span><span class="sxs-lookup"><span data-stu-id="3ee1c-103">Add and assign Mobile Threat Defense (MTD) apps with Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="3ee1c-104">Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="3ee1c-105">Você pode usar o Intune para adicionar e implantar aplicativos MTD para que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-105">You can use Intune to add and deploy MTD apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="3ee1c-106">Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-106">For iOS devices, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD.</span></span> <span data-ttu-id="3ee1c-107">Além disso, você precisará da política de configuração de aplicativo iOS que indica qual aplicativo MTD iOS deve ser usado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-107">Additionally, you need the iOS app configuration policy which signals the MTD iOS app to use with Intune.</span></span>

> [!TIP]
> <span data-ttu-id="3ee1c-108">O Portal da Empresa do Intune funciona como o agente em dispositivos Android para as identidades dos usuários possam ser verificadas pelo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-108">The Intune company portal works as the broker on Android devices so users can have their identities checked by Azure AD.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3ee1c-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3ee1c-109">Before you begin</span></span>

-   <span data-ttu-id="3ee1c-110">As etapas a seguir devem ser concluídas no [Portal do Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-110">The below steps need to be completed in the [Azure portal](https://portal.azure.com/).</span></span>

-   <span data-ttu-id="3ee1c-111">Verifique se que você está familiarizado com o processo de:</span><span class="sxs-lookup"><span data-stu-id="3ee1c-111">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="3ee1c-112">[Adicionar um aplicativo no Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-112">[Adding an app into Intune](apps-add.md).</span></span>

    -   <span data-ttu-id="3ee1c-113">[Adicionar uma política de configuração de aplicativo do iOS no Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-113">[Adding an iOS app configuration policy into Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="3ee1c-114">[Atribuindo um aplicativo com o Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-114">[Assigning an app with Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="3ee1c-115">[ Adicionando uma política de configuração de aplicativo iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-115">[ Adding an iOS app configuration policy](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <a name="to-add-apps"></a><span data-ttu-id="3ee1c-116">Adicionar aplicativos</span><span class="sxs-lookup"><span data-stu-id="3ee1c-116">To add apps</span></span>

### <a name="all-mtd-partners"></a><span data-ttu-id="3ee1c-117">Todos os parceiros de MTD</span><span class="sxs-lookup"><span data-stu-id="3ee1c-117">All MTD partners</span></span>

#### <a name="microsoft-authenticator-app-for-ios"></a><span data-ttu-id="3ee1c-118">Aplicativo Microsoft Authenticator para iOS</span><span class="sxs-lookup"><span data-stu-id="3ee1c-118">Microsoft Authenticator app for iOS</span></span>

- <span data-ttu-id="3ee1c-119">Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-119">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="3ee1c-120">Use esta [URL da loja de aplicativos do Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-120">Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <a name="skycure"></a><span data-ttu-id="3ee1c-121">Skycure</span><span class="sxs-lookup"><span data-stu-id="3ee1c-121">Skycure</span></span>

#### <a name="android"></a><span data-ttu-id="3ee1c-122">Android</span><span class="sxs-lookup"><span data-stu-id="3ee1c-122">Android</span></span>

- <span data-ttu-id="3ee1c-123">Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-123">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="3ee1c-124">Use esta [URL da loja de aplicativos do Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) na **etapa 7**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-124">Use this [Skycure app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="3ee1c-125">iOS</span><span class="sxs-lookup"><span data-stu-id="3ee1c-125">iOS</span></span>

- <span data-ttu-id="3ee1c-126">Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-126">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="3ee1c-127">Use esta [URL da loja de aplicativos do Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-127">Use this [Skycure app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <a name="lookout"></a><span data-ttu-id="3ee1c-128">Lookout</span><span class="sxs-lookup"><span data-stu-id="3ee1c-128">Lookout</span></span>

#### <a name="android"></a><span data-ttu-id="3ee1c-129">Android</span><span class="sxs-lookup"><span data-stu-id="3ee1c-129">Android</span></span>
- <span data-ttu-id="3ee1c-130">Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-130">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="3ee1c-131">Use esta [URL da loja de aplicativos da Google do Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) na **etapa 7**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-131">Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="3ee1c-132">iOS</span><span class="sxs-lookup"><span data-stu-id="3ee1c-132">iOS</span></span>

- <span data-ttu-id="3ee1c-133">Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-133">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="3ee1c-134">Use esta [URL da loja de aplicativos do Lookout for Work iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-134">Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) on **step 5** under the **Configure app information** section.</span></span>

#### <a name="lookout-for-work-app-outside-the-apple-store"></a><span data-ttu-id="3ee1c-135">Aplicativo Lookout for Work fora da Apple store</span><span class="sxs-lookup"><span data-stu-id="3ee1c-135">Lookout for Work app outside the Apple store</span></span>

<span data-ttu-id="3ee1c-136">Será necessário reassinar o aplicativo Lookout for Work iOS.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-136">You need to re-sign the Lookout for Work iOS app.</span></span> <span data-ttu-id="3ee1c-137">O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-137">Lookout distributes its Lookout for Work iOS app outside of the iOS App Store.</span></span> <span data-ttu-id="3ee1c-138">Antes de distribuir o aplicativo, você deverá reassiná-lo com seu iOS Enterprise Developer Certificate.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-138">Before distributing the app, you must re-sign the app with your iOS Enterprise Developer Certificate.</span></span>

<span data-ttu-id="3ee1c-139">Para obter instruções detalhadas sobre como reassinar o aplicativo Lookout for Work iOS, consulte [Processo para reassinar o aplicativo Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-139">For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout website.</span></span>

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a><span data-ttu-id="3ee1c-140">Habilitar a autenticação do Azure AD para o aplicativo Lookout for Work iOS</span><span class="sxs-lookup"><span data-stu-id="3ee1c-140">Enable Azure AD authentication for Lookout for Work iOS app</span></span>

<span data-ttu-id="3ee1c-141">Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3ee1c-141">Enable Azure Active Directory authentication for the iOS users by doing the following:</span></span>

1. <span data-ttu-id="3ee1c-142">Acesse o [Portal do Azure](https://portal.sazure.com), entre com suas credenciais e navegue para a página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-142">Go to the [Azure portal](https://portal.sazure.com), sign in with your credentials, then navigate to the application page.</span></span>
  
2. <span data-ttu-id="3ee1c-143">Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-143">Add the **Lookout for Work iOS app** as a **native client application**.</span></span>

3. <span data-ttu-id="3ee1c-144">Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-144">Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.</span></span>

4.  <span data-ttu-id="3ee1c-145">Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-145">Add additional redirect URI: **&lt;companyportal://code/>** followed by a URL encoded version of your original redirect URI.</span></span>

5.  <span data-ttu-id="3ee1c-146">Adicione **Permissões delegadas** ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-146">Add **Delegated Permissions** to your app.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="3ee1c-147">Consulte [Configurar um aplicativo cliente nativo com o Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) para ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-147">See [configure a native client application with Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) for more details.</span></span>

##### <a name="add-the-lookout-for-work-ipa-file"></a><span data-ttu-id="3ee1c-148">Adicionar o arquivo ipa do Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="3ee1c-148">Add the Lookout for Work ipa file</span></span>

- <span data-ttu-id="3ee1c-149">Carregue o arquivo .ipa reassinado conforme descrito no tópico [Adicionar aplicativos iOS LOB com o Intune](lob-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-149">Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](lob-apps-ios.md) topic.</span></span> <span data-ttu-id="3ee1c-150">Também será necessário definir a versão mínima do sistema operacional para iOS 8.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-150">You also need to set the minimum OS version to iOS 8.0 or later.</span></span>

### <a name="check-point-sandblast-mobile"></a><span data-ttu-id="3ee1c-151">SandBlast Mobile da Check Point</span><span class="sxs-lookup"><span data-stu-id="3ee1c-151">Check Point SandBlast Mobile</span></span>

#### <a name="android"></a><span data-ttu-id="3ee1c-152">Android</span><span class="sxs-lookup"><span data-stu-id="3ee1c-152">Android</span></span>

- <span data-ttu-id="3ee1c-153">Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-153">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="3ee1c-154">Use esta [URL da App Store para o SandBlast Mobile da Check Point](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) na **etapa 7**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-154">Use this [Check Point SandBlast Mobile app store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="3ee1c-155">iOS</span><span class="sxs-lookup"><span data-stu-id="3ee1c-155">iOS</span></span>

- <span data-ttu-id="3ee1c-156">Contate o [SandBlast Mobile da Check Point](https://www.checkpoint.com/products/sandblast-mobile/) a fim de obter o aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-156">Contact [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) to get the iOS app.</span></span> <span data-ttu-id="3ee1c-157">Confira instruções sobre [como adicionar aplicativos da iOS Store ao Microsoft Intune](store-apps-ios.md) e use a URL da Apple Store na **etapa 5**, na seção **Informações de configuração do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-157">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md), then use the Apple store URL on **step 5** under the **Configure app information** section.</span></span>

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a><span data-ttu-id="3ee1c-158">Associar o aplicativo MTD a uma política de configuração de aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="3ee1c-158">To associate the MTD app with an iOS app configuration policy</span></span>

### <a name="for-skycure"></a><span data-ttu-id="3ee1c-159">Para Skycure</span><span class="sxs-lookup"><span data-stu-id="3ee1c-159">For Skycure</span></span>

-   <span data-ttu-id="3ee1c-160">Use a conta do Microsoft Azure AD configurada anteriormente no [Console de Gerenciamento do Skycure](https://aad.skycure.com), que deve ser a mesma conta usada para entrar no console clássico do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-160">Use the same Azure AD account previously configured in the [Skycure Management console](https://aad.skycure.com), which should be the same account used to log in into the Intune classic console.</span></span>

-   <span data-ttu-id="3ee1c-161">É necessário **baixar** o arquivo da política de configuração de aplicativo do iOS:</span><span class="sxs-lookup"><span data-stu-id="3ee1c-161">You need to **download** the iOS app configuration policy file:</span></span> 
    -   <span data-ttu-id="3ee1c-162">Vá para o [Console de Gerenciamento do Skycure](https://aad.skycure.com) e entre com as Credenciais de Administrador.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-162">Go to [Skycure Management console](https://aad.skycure.com) and sign in with your admin credentials.</span></span>
    
    -   <span data-ttu-id="3ee1c-163">Acesse **Configurações** &gt; **Integrações de Gerenciamento de Dispositivo** &gt; **Seleção de Integração EMM**, escolha **Microsoft Intune** e salve sua seleção.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-163">Go to **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choose **Microsoft Intune**, then save your selection.</span></span>
    
    -   <span data-ttu-id="3ee1c-164">Clique no link **Arquivos de configuração da integração** e salve o arquivo \*.zip gerado.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-164">Click on the **Integration setup files** link and save the generated \*.zip file.</span></span> <span data-ttu-id="3ee1c-165">O arquivo .zip contém o arquivo **skycure\_configuration.plist**, que será usado para criar a política de configuração de aplicativo do iOS no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-165">The .zip file contains the **skycure\_configuration.plist** file, which will be used to create the iOS app configuration policy in Intune.</span></span>
    
    -   <span data-ttu-id="3ee1c-166">Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do Skycure.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-166">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Skycure iOS app configuration policy.</span></span>
    
    - <span data-ttu-id="3ee1c-167">Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo do arquivo **skycure_configuration.plist** e cole-o no corpo da política de configuração.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-167">On **step 8**, use the option **Enter XML data**, copy the content from the **skycure_configuration.plist** file and paste its content into the configuration policy body.</span></span>

<span data-ttu-id="3ee1c-168">Você também pode copiar o conteúdo **skycure_configuration.plist** aqui:</span><span class="sxs-lookup"><span data-stu-id="3ee1c-168">You can also copy the **skycure_configuration.plist** content from here:</span></span>
=======
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a>Adicionar e atribuir aplicativos MTD (Defesa contra Ameaças Móveis) com o Intune

> [!NOTE] 
> Este tópico se aplica a todos os parceiros de Defesa contra Ameaças Móveis.

Você pode usar o Intune para adicionar e implantar aplicativos MTD para que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.

Para dispositivos iOS, você precisará do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) para que as identidades dos usuários possam ser verificados pelo Azure AD. Além disso, você precisará da política de configuração de aplicativo iOS que indica qual aplicativo MTD iOS deve ser usado com o Intune.

> [!TIP]
> O Portal da Empresa do Intune funciona como o agente em dispositivos Android para as identidades dos usuários possam ser verificadas pelo Azure AD.

## <a name="before-you-begin"></a>Antes de começar

-   As etapas a seguir devem ser concluídas no [Portal do Azure](https://portal.azure.com/).

-   Verifique se que você está familiarizado com o processo de:

    -   [Adicionar um aplicativo no Intune](apps-add.md).

    -   [Adicionar uma política de configuração de aplicativo do iOS no Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

    -   [Atribuindo um aplicativo com o Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).

    -   [ Adicionando uma política de configuração de aplicativo iOS](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).

## <a name="to-add-apps"></a>Adicionar aplicativos

### <a name="all-mtd-partners"></a>Todos os parceiros de MTD

#### <a name="microsoft-authenticator-app-for-ios"></a>Aplicativo Microsoft Authenticator para iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Microsoft Authenticator](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### <a name="skycure"></a>Skycure

#### <a name="android"></a>Android

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos do Skycure](https://play.google.com/store/apps/details?id=com.skycure.skycure) na **etapa 7**.

#### <a name="ios"></a>iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Skycure](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

### <a name="lookout"></a>Lookout

#### <a name="android"></a>Android
- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da loja de aplicativos da Google do Lookout for Work](https://play.google.com/store/apps/details?id=com.lookout.enterprise) na **etapa 7**.

#### <a name="ios"></a>iOS

- Consulte as instruções para [adicionar aplicativos da loja do iOS ao Microsoft Intune](store-apps-ios.md). Use esta [URL da loja de aplicativos do Lookout for Work iOS](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) na **etapa 5** na seção **Configurar informações de aplicativo**.

#### <a name="lookout-for-work-app-outside-the-apple-store"></a>Aplicativo Lookout for Work fora da Apple store

Será necessário reassinar o aplicativo Lookout for Work iOS. O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store. Antes de distribuir o aplicativo, você deverá reassiná-lo com seu iOS Enterprise Developer Certificate.

Para obter instruções detalhadas sobre como reassinar o aplicativo Lookout for Work iOS, consulte [Processo para reassinar o aplicativo Lookout for Work iOS](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a>Habilitar a autenticação do Azure AD para o aplicativo Lookout for Work iOS

Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:

1. Acesse o [Portal do Azure](https://portal.sazure.com), entre com suas credenciais e navegue para a página do aplicativo.
  
2. Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.

3. Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.

4.  Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.

5.  Adicione **Permissões delegadas** ao aplicativo.

    > [!NOTE] 
    > Consulte [Configurar um aplicativo cliente nativo com o Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) para ver mais detalhes.

##### <a name="add-the-lookout-for-work-ipa-file"></a>Adicionar o arquivo ipa do Lookout for Work

- Carregue o arquivo .ipa reassinado conforme descrito no tópico [Adicionar aplicativos iOS LOB com o Intune](lob-apps-ios.md). Também será necessário definir a versão mínima do sistema operacional para iOS 8.0 ou posterior.

### <a name="check-point-sandblast-mobile"></a>SandBlast Mobile da Check Point

#### <a name="android"></a>Android

- Consulte as instruções para [adicionar aplicativos da loja do Android ao Microsoft Intune](store-apps-android.md). Use esta [URL da App Store para o SandBlast Mobile da Check Point](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) na **etapa 7**.

#### <a name="ios"></a>iOS

- Contate o [SandBlast Mobile da Check Point](https://www.checkpoint.com/products/sandblast-mobile/) a fim de obter o aplicativo iOS. Confira instruções sobre [como adicionar aplicativos da iOS Store ao Microsoft Intune](store-apps-ios.md) e use a URL da Apple Store na **etapa 5**, na seção **Informações de configuração do aplicativo**.

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a>Associar o aplicativo MTD a uma política de configuração de aplicativo iOS

### <a name="for-skycure"></a>Para Skycure

-   Use a conta do Microsoft Azure AD configurada anteriormente no [Console de Gerenciamento do Skycure](https://aad.skycure.com), que deve ser a mesma conta usada para entrar no console clássico do Microsoft Intune.

-   É necessário **baixar** o arquivo da política de configuração de aplicativo do iOS: 
    -   Vá para o [Console de Gerenciamento do Skycure](https://aad.skycure.com) e entre com as Credenciais de Administrador.
    
    -   Acesse **Configurações** &gt; **Integrações de Gerenciamento de Dispositivo** &gt; **Seleção de Integração EMM**, escolha **Microsoft Intune** e salve sua seleção.
    
    -   Clique no link **Arquivos de configuração da integração** e salve o arquivo \*.zip gerado. O arquivo .zip contém o arquivo **skycure\_configuration.plist**, que será usado para criar a política de configuração de aplicativo do iOS no Microsoft Intune.
    
    -   Consulte as instruções para [usar políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) para adicionar a política de configuração de aplicativo iOS do Skycure.
    
    - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo do arquivo **skycure_configuration.plist** e cole-o no corpo da política de configuração.

Você também pode copiar o conteúdo **skycure_configuration.plist** aqui:
>>>>>>> live

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
<<<<<<< HEAD
### <a name="for-lookout"></a><span data-ttu-id="3ee1c-169">Para Lookout</span><span class="sxs-lookup"><span data-stu-id="3ee1c-169">For Lookout</span></span>

- <span data-ttu-id="3ee1c-170">Crie a política de configuração do aplicativo iOS conforme descrito no tópico [usando a política de configuração de aplicativo iOS](app-configuration-policies-use-ios.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-170">Create the iOS app configuration policy as described in the [using iOS app configuration policy](app-configuration-policies-use-ios.md) topic.</span></span>

### <a name="for-check-point-sandblast-mobile"></a><span data-ttu-id="3ee1c-171">Para o SandBlast Mobile da Check Point</span><span class="sxs-lookup"><span data-stu-id="3ee1c-171">For Check Point SandBlast Mobile</span></span>

- <span data-ttu-id="3ee1c-172">Confira instruções sobre [como usar as políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) a fim de adicionar a política de configuração de aplicativo do iOS para o SandBlast Mobile da Check Point.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-172">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Check Point SandBlast Mobile iOS app configuration policy.</span></span>
    - <span data-ttu-id="3ee1c-173">Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo abaixo e cole-o no corpo da política de configuração.</span><span class="sxs-lookup"><span data-stu-id="3ee1c-173">On **step 8**, use the option **Enter XML data**, copy the content below and paste it into the configuration policy body.</span></span>
=======
### <a name="for-lookout"></a>Para Lookout

- Crie a política de configuração do aplicativo iOS conforme descrito no tópico [usando a política de configuração de aplicativo iOS](app-configuration-policies-use-ios.md).

### <a name="for-check-point-sandblast-mobile"></a>Para o SandBlast Mobile da Check Point

- Confira instruções sobre [como usar as políticas de configuração de aplicativo do Microsoft Intune para iOS](app-configuration-policies-use-ios.md) a fim de adicionar a política de configuração de aplicativo do iOS para o SandBlast Mobile da Check Point.
    - Na **etapa 8**, use a opção **Inserir dados XML**, copie o conteúdo abaixo e cole-o no corpo da política de configuração.
>>>>>>> live

```
<dict><key>MDM</key><string>INTUNE</string></dict>

```
<<<<<<< HEAD
## <a name="to-assign-apps-all-mtd-partners"></a><span data-ttu-id="3ee1c-174">Para atribuir aplicativos (todos os parceiros de MTD)</span><span class="sxs-lookup"><span data-stu-id="3ee1c-174">To assign apps (All MTD partners)</span></span>

- <span data-ttu-id="3ee1c-175">Confira instruções sobre [como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="3ee1c-175">See instructions for [assigning apps to groups with Intune](apps-deploy.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3ee1c-176">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3ee1c-176">Next steps</span></span>

- [<span data-ttu-id="3ee1c-177">Configurar a integração do Lookout com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3ee1c-177">Set up the Lookout integration with Intune</span></span>](lookout-mtd-connector-integration.md)
- [<span data-ttu-id="3ee1c-178">Configurar a integração do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="3ee1c-178">Set up the Skycure integration with Intune</span></span>](skycure-mtd-connector-integration.md)
- [<span data-ttu-id="3ee1c-179">Configurar a integração do SandBlast Mobile da Check Point com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3ee1c-179">Set up the Check Point SandBlast integration with Intune</span></span>](checkpoint-sandblast-mobile-mtd-connector-integration.md)
=======
## <a name="to-assign-apps-all-mtd-partners"></a>Para atribuir aplicativos (todos os parceiros de MTD)

- Confira instruções sobre [como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).

## <a name="next-steps"></a>Próximas etapas

- [Configurar a integração do Lookout com o Microsoft Intune](lookout-mtd-connector-integration.md)
- [Configurar a integração do Skycure com o Intune](skycure-mtd-connector-integration.md)
- [Configurar a integração do SandBlast Mobile da Check Point com o Microsoft Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)
>>>>>>> live
