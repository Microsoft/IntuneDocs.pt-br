---
title: Implantar o aplicativo Lookout for Work
description: Configurar e implantar aplicativos Lookout for Work para Android.
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 524c4209-ad57-4d35-955e-a00d796bf858
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5d4f496709a8607b0d6d473355c96e8fc502838b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c72ac-103">Configurar e implantar o aplicativo Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="c72ac-103">Configure and deploy Lookout for Work app</span></span>
<a id="configure-and-deploy-lookout-for-work-app" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c72ac-104">Este artigo explica como configurar e implantar o aplicativo Lookout for Work em dispositivos Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="c72ac-104">This article explains how to configure and deploy the Lookout for Work app for Android and iOS devices.</span></span>

## <span data-ttu-id="c72ac-105">Android (aplicativo da Google Play Store)</span><span class="sxs-lookup"><span data-stu-id="c72ac-105">Android (Google Play Store app)</span></span>
<a id="android-google-play-store-app" class="xliff"></a>

1.  <span data-ttu-id="c72ac-106">No [console do administrador do Microsoft Intune](https://manage.microsoft.com), acesse **Aplicativos** e escolha **Adicionar Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c72ac-106">In the [Microsoft Intune administrator console](https://manage.microsoft.com), go to **Apps** and choose **Add Apps**.</span></span>
2.  <span data-ttu-id="c72ac-107">Na página **Configuração de Software** do editor, escolha **Link externo** e especifique a seguinte URL: https://play.google.com/store/apps/details?id=com.lookout.enterprise</span><span class="sxs-lookup"><span data-stu-id="c72ac-107">On the **Software Setup** page of the publisher, choose **External link**, and specify the following URL:  https://play.google.com/store/apps/details?id=com.lookout.enterprise</span></span>
  >[!NOTE]
  ><span data-ttu-id="c72ac-108">Não clique na caixa para exigir um navegador gerenciado.</span><span class="sxs-lookup"><span data-stu-id="c72ac-108">Do not click the box for requiring a managed browser.</span></span>

3.  <span data-ttu-id="c72ac-109">Na página **Descrição do software**, preencha as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="c72ac-109">On the **Software description** page fill in the following information:</span></span>
  * <span data-ttu-id="c72ac-110">**Editor:** Lookout Mobile Security</span><span class="sxs-lookup"><span data-stu-id="c72ac-110">**Publisher:** Lookout Mobile Security</span></span>
  * <span data-ttu-id="c72ac-111">**Nome:** Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="c72ac-111">**Name:**   Lookout for Work</span></span>
  * <span data-ttu-id="c72ac-112">**Descrição:** o Lookout oferece a melhor proteção contra ameaças móveis para manter seu dispositivo em segurança.</span><span class="sxs-lookup"><span data-stu-id="c72ac-112">**Description:**  Lookout offers the best protection against mobile threats to keep your device safe.</span></span> <span data-ttu-id="c72ac-113">Quando o aplicativo Lookout é instalado no dispositivo, ele o protege contra ameaças e alerta você e o administrador da empresa se alguma ameaça for encontrada.</span><span class="sxs-lookup"><span data-stu-id="c72ac-113">When the Lookout app is installed on the device, the app protects your device from threats and will alert you, and your company administrator, if any are found.</span></span>
  * <span data-ttu-id="c72ac-114">**Categoria:** Gerenciamento de Computador</span><span class="sxs-lookup"><span data-stu-id="c72ac-114">**Category:** Computer Management</span></span>

4. <span data-ttu-id="c72ac-115">Após a conclusão bem-sucedida, você verá a mensagem **Upload de dados para o Microsoft Intune concluído com êxito**.</span><span class="sxs-lookup"><span data-stu-id="c72ac-115">Upon successful completion you see a message **Upload of data to Microsoft Intune successfully completed**.</span></span>

  <span data-ttu-id="c72ac-116">No Console do Intune, ao clicar em **Aplicativos**, agora você verá o aplicativo **Lookout for Work** na lista ![captura de tela da página de aplicativos do console do administrador do Intune mostrando os aplicativos Lookout for Work na lista](../media/mtp/lookout-app-listed-intune-console.png)</span><span class="sxs-lookup"><span data-stu-id="c72ac-116">In the Intune Console when you click on the **Apps** you will now see the **Lookout for Work** app in the list ![screenshot of Intune admin console apps page showing the Lookout for work apps in the list](../media/mtp/lookout-app-listed-intune-console.png)</span></span>

5. <span data-ttu-id="c72ac-117">Implante o aplicativo nos usuários selecionando o aplicativo Lookout for Work e escolhendo **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="c72ac-117">Deploy the app to users by selecting the Lookout for Work app and choosing  **Manage Deployment**.</span></span>

  <span data-ttu-id="c72ac-118">Você precisa selecionar os mesmos usuários adicionados à opção de Gerenciamento de Registro no console da Consulta MTP.</span><span class="sxs-lookup"><span data-stu-id="c72ac-118">You must select the same users added in to the Enrollment Management option in the Lookout MTP console.</span></span>  <span data-ttu-id="c72ac-119">Consulte a Etapa 3 na seção [Configurar sua assinatura da Consulta MTP](configure-deploy-lookout-for-work-app.md) para obter informações sobre como adicionar grupos de usuários à Consulta MTP.</span><span class="sxs-lookup"><span data-stu-id="c72ac-119">See Step 3 in the [configure your subscription with Lookout MTP section](configure-deploy-lookout-for-work-app.md) for information about adding user groups to Lookout MTP.</span></span>

  >[!IMPORTANT]
  > <span data-ttu-id="c72ac-120">O assistente de implantação de aplicativo do Intune não está ciente dos grupos de usuários do Azure AD e usa os grupos de usuários do Intune em vez disso.</span><span class="sxs-lookup"><span data-stu-id="c72ac-120">The Intune app deployment Wizard is not aware of the Azure AD user groups and uses the Intune user groups instead.</span></span> <span data-ttu-id="c72ac-121">Sendo assim, você precisa criar um grupo de usuários do Intune com base no grupo de usuários do Azure AD que está registrado no console da Consulta MTP, conforme descrito [neste](plan-your-user-and-device-groups.md) tópico.</span><span class="sxs-lookup"><span data-stu-id="c72ac-121">So you must create an Intune user group based on the Azure AD user group that is enrolled in the Lookout MTP console as described in [this](plan-your-user-and-device-groups.md)topic.</span></span>

6. <span data-ttu-id="c72ac-122">Escolha a opção **Instalação Obrigatória** para exigir que o aplicativo Lookout seja instalado no dispositivo do usuário.</span><span class="sxs-lookup"><span data-stu-id="c72ac-122">Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.</span></span>

## <span data-ttu-id="c72ac-123">iOS (versão Enterprise assinada do aplicativo Lookout)</span><span class="sxs-lookup"><span data-stu-id="c72ac-123">iOS (Enterprise-signed version of Lookout app)</span></span>
<a id="ios-enterprise-signed-version-of-lookout-app" class="xliff"></a>

1. <span data-ttu-id="c72ac-124">Verifique se o **Gerenciamento do iOS** está configurado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c72ac-124">Make sure **iOS management** is set up on your device.</span></span> <span data-ttu-id="c72ac-125">Para obter instruções sobre como configurar seu dispositivo para gerenciamento de iOS, confira [Configurar o gerenciamento de dispositivos iOS e Mac](set-up-ios-and-mac-management-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c72ac-125">For instructions on how to set up your device for iOS management, see [Set up iOS and Mac device management](set-up-ios-and-mac-management-with-microsoft-intune.md).</span></span>

2. <span data-ttu-id="c72ac-126">**Reassine** o aplicativo Lookout for Work do iOS.</span><span class="sxs-lookup"><span data-stu-id="c72ac-126">**Re-sign** the Lookout for Work iOS app.</span></span> <span data-ttu-id="c72ac-127">O Lookout distribui o aplicativo iOS Lookout for Work fora da iOS App Store.</span><span class="sxs-lookup"><span data-stu-id="c72ac-127">Lookout distributes its Lookout for Work iOS app outside of the iOS App Store.</span></span> <span data-ttu-id="c72ac-128">**Antes de distribuir o aplicativo**, você deve reassinar o aplicativo com seu certificado de desenvolvedor iOS corporativo.</span><span class="sxs-lookup"><span data-stu-id="c72ac-128">**Before distributing the app**, you must re-sign the app with your iOS Enterprise Developer Certificate.</span></span> <span data-ttu-id="c72ac-129">Para obter instruções detalhadas sobre como reassinar o aplicativo iOS Lookout for Work, consulte [Processo para reassinar o aplicativo iOS Lookout for Work](https://personal.support.lookout.com/hc/articles/114094038714) no site do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c72ac-129">For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout site.</span></span>

3. <span data-ttu-id="c72ac-130">Habilite a autenticação do Azure Active Directory para os usuários do iOS fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c72ac-130">Enable Azure Active Directory authentication for the iOS users by doing the following:</span></span>
  1.  <span data-ttu-id="c72ac-131">Faça logon no [portal de gerenciamento do Azure Active Directory](https://manage.windowsazure.com) e navegue até a página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c72ac-131">Login to the [Azure Active Directory management portal](https://manage.windowsazure.com), and navigate to the application page.</span></span>
  2.  <span data-ttu-id="c72ac-132">Adicione o **aplicativo Lookout for Work iOS** como um **aplicativo cliente nativo**.</span><span class="sxs-lookup"><span data-stu-id="c72ac-132">Add the **Lookout for Work iOS app** as a **native client application**.</span></span>
  <span data-ttu-id="c72ac-133">![captura de tela da caixa de diálogo para adicionar aplicativos mostrando a opção de aplicativo cliente nativo](../media/mtp/aad-add-app.png)</span><span class="sxs-lookup"><span data-stu-id="c72ac-133">![screenshot of the add apps dialog showing the native client app option](../media/mtp/aad-add-app.png)</span></span>
  3. <span data-ttu-id="c72ac-134">Substitua o **com.lookout.enterprise.yourcompanyname** pela ID do grupo do cliente que você selecionou quando assinou o IPA.</span><span class="sxs-lookup"><span data-stu-id="c72ac-134">Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.</span></span>
  4.  <span data-ttu-id="c72ac-135">Adicione o URI de redirecionamento adicional: **&lt;companyportal://code/>** seguido por uma versão codificada da URL do URI de redirecionamento original.</span><span class="sxs-lookup"><span data-stu-id="c72ac-135">Add additional redirect URI: **&lt;companyportal://code/>** followed by a URLencoded version of your original redirect URI.</span></span>
  5.  <span data-ttu-id="c72ac-136">Adicione **Permissões delegadas** ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c72ac-136">Add **Delegated Permissions** to your app.</span></span>

  <span data-ttu-id="c72ac-137">Para obter mais detalhes, consulte [Configurar um aplicativo de cliente nativo](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).</span><span class="sxs-lookup"><span data-stu-id="c72ac-137">For more details, see [Configure a native client application](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).</span></span>

4. <span data-ttu-id="c72ac-138">Carregue o arquivo .ipa reassinado, conforme descrito no tópico [Adicionar aplicativo para dispositivos móveis no Microsoft Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="c72ac-138">Upload the re-signed .ipa file as described in the [Add app for mobile devices in Microsoft Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune) topic.</span></span> <span data-ttu-id="c72ac-139">Defina a versão mínima do sistema operacional para iOS 8.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="c72ac-139">Set the minimum OS version to iOS 8.0 or later.</span></span>

  ![captura de tela da página de aplicativos do console do administrador do Intune com o aplicativo Lookout for Work exibido na lista de aplicativos](../media/mtp/ios-app-uploaded-intune.png)

5. <span data-ttu-id="c72ac-141">Crie a política de configuração de aplicativo gerenciado, conforme descrito no tópico [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) (Configurar aplicativos iOS com políticas de configuração de aplicativo móvel no Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="c72ac-141">Create the managed app configuration policy as described in the [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune) topic.</span></span>

  ![captura de tela do assistente de criação de nova política com o iOS 8.0 ou posterior com a política de configuração do aplicativo destacada](../media/mtp/ios-app-config.png)

6. <span data-ttu-id="c72ac-143">**Para implantar o aplicativo nos usuários**, selecione o aplicativo Lookout for Work e escolha **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="c72ac-143">**To deploy the app to users**, select the Lookout for Work app, and choose **Manage Deployment**.</span></span>

  <span data-ttu-id="c72ac-144">Você precisa selecionar os mesmos usuários que foram adicionados à opção de Gerenciamento de Registro no console do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c72ac-144">You must select the same users that were added to the Enrollment Management option in the Lookout  console.</span></span>  <span data-ttu-id="c72ac-145">Confira a Etapa 3 na seção [Configurar sua assinatura do Lookout](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps) para obter informações sobre como adicionar grupos de usuários ao Lookout MTP.</span><span class="sxs-lookup"><span data-stu-id="c72ac-145">See Step 3 in the [configure your Lookout subscription section](https://docs.microsoft.com/sccm/protect/deploy-use/configure-and-deploy-lookout-for-work-apps) for information about adding user groups to Lookout MTP.</span></span>

  >[!IMPORTANT]
  > <span data-ttu-id="c72ac-146">O assistente de implantação de aplicativo do Intune não está ciente dos grupos de usuários do Azure AD e, em vez disso, usa os grupos de usuários do Intune, portanto você deve criar um grupo de usuários do Azure AD que está registrado no console do Lookout, conforme descrito [neste](plan-your-user-and-device-groups.md) tópico.</span><span class="sxs-lookup"><span data-stu-id="c72ac-146">The Intune app deployment wizard is not aware of the Azure AD user groups and uses the Intune user groups instead, so you must create an Intune user group based on the Azure AD user group that is enrolled in the Lookout console as described in [this](plan-your-user-and-device-groups.md) topic.</span></span>

  <span data-ttu-id="c72ac-147">Escolha a opção **Instalação Obrigatória** para exigir que o aplicativo Lookout seja instalado no dispositivo do usuário.</span><span class="sxs-lookup"><span data-stu-id="c72ac-147">Choose the **Required Install** option to require that the Lookout app be installed on the user’s device.</span></span>

## <span data-ttu-id="c72ac-148">O que acontece quando o aplicativo implantado é aberto no dispositivo</span><span class="sxs-lookup"><span data-stu-id="c72ac-148">What happens when the deployed app is opened on the device</span></span>
<a id="what-happens-when-the-deployed-app-is-opened-on-the-device" class="xliff"></a>
<span data-ttu-id="c72ac-149">https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md Quando o usuário abre o Lookout for Work no dispositivo, é solicitado que ele ative o aplicativo e escolha a opção Entrar com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c72ac-149">https://github.com/Microsoft/Docs/blob/master/ContributorGuide/index.md When the user opens the Lookout for Work on the device they are prompted to activate the app, and choose the Sign in with Azure Active Directory option.</span></span> <span data-ttu-id="c72ac-150">Um passo a passo detalhado com o fluxo do usuário final pode ser encontrado nos tópicos a seguir:</span><span class="sxs-lookup"><span data-stu-id="c72ac-150">A detailed walkthrough with the end-user flow can be found in the following topics:</span></span>

* [<span data-ttu-id="c72ac-151">Será solicitada a instalação do Lookout for Work em seu dispositivo Android</span><span class="sxs-lookup"><span data-stu-id="c72ac-151">You are prompted to install Lookout for Work on your Android device</span></span>](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)

* [<span data-ttu-id="c72ac-152">Você precisa resolver uma ameaça encontrada pelo Lookout for Work no dispositivo Android</span><span class="sxs-lookup"><span data-stu-id="c72ac-152">You need to resolve a threat that Lookout for Work found on your Android device</span></span>](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)

## <span data-ttu-id="c72ac-153">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c72ac-153">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
* [<span data-ttu-id="c72ac-154">Criar política de conformidade de dispositivo do Lookout no Intune</span><span class="sxs-lookup"><span data-stu-id="c72ac-154">Create Lookout device compliance policy in Intune</span></span>](https://docs.microsoft.com/sccm/protect/deploy-use/enable-device-threat-protection-rule-compliance-policy)
