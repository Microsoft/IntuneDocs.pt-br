---
title: "Adicionar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS"
description: "Adicione os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 425b86e92281bb6e3657a6c806be269ccae94311
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="650a7-103">Adicionar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS</span><span class="sxs-lookup"><span data-stu-id="650a7-103">Add Skycure apps, Microsoft Authenticator app and iOS configuration policy</span></span>
<a id="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="650a7-104">Você precisa usar o Intune para adicionar e implantar os aplicativos Skycure de modo que os usuários finais possam receber notificações quando uma ameaça for identificada em seus dispositivos móveis e para receber orientação para corrigir essas ameaças.</span><span class="sxs-lookup"><span data-stu-id="650a7-104">You need to use Intune to add and deploy the Skycure apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="650a7-105">Além disso, você precisa do [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), para que os usuários possam ter suas identidades verificadas pelo Azure AD, e da política de configuração de aplicativo do iOS, que sinaliza ao aplicativo para iOS do Skycure o uso do Intune e do SSO (Logon único) do Azure AD para que os usuários não precisem digitar o nome de usuário e a senha sempre que fizerem logon no aplicativo Skycure.</span><span class="sxs-lookup"><span data-stu-id="650a7-105">Additionally, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD, and the iOS app configuration policy which signals the Skycure iOS app to use Intune and Azure AD Single Sign On (SSO) so users don’t need to type username and password every time they log in the Skycure app.</span></span>

## <span data-ttu-id="650a7-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="650a7-106">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

-   <span data-ttu-id="650a7-107">As etapas a seguir devem ser concluídas no [console clássico do Intune](https://manage.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="650a7-107">The below steps need to be completed in the [Intune classic console](https://manage.microsoft.com/).</span></span>

-   <span data-ttu-id="650a7-108">Use a mesma conta do Azure AD previamente configurada no console de Gerenciamento do Skycure, que deve ser a mesma conta usada para fazer logon no console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="650a7-108">Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic console.</span></span>

-   <span data-ttu-id="650a7-109">O arquivo de integração do Skycure precisa estar pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="650a7-109">You need to have the Skycure integration file ready to use.</span></span> <span data-ttu-id="650a7-110">Este é o arquivo .zip baixado anteriormente do console de Gerenciamento do Skycure, que contém o arquivo **skycure\_configuration.plist** com os parâmetros da política de configuração de aplicativo do iOS.</span><span class="sxs-lookup"><span data-stu-id="650a7-110">This is the .zip file previously downloaded from the Skycure Management console, which contains the file **skycure\_configuration.plist** with the iOS app configuration policy parameters.</span></span>

-   <span data-ttu-id="650a7-111">Verifique se que você está familiarizado com o processo de:</span><span class="sxs-lookup"><span data-stu-id="650a7-111">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="650a7-112">[Adicionar um aplicativo no Intune](/intune-classic/deploy-use/add-apps).</span><span class="sxs-lookup"><span data-stu-id="650a7-112">[Adding an app into Intune](/intune-classic/deploy-use/add-apps).</span></span>

    -   <span data-ttu-id="650a7-113">[Adicionar uma política de configuração de aplicativo do iOS no Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="650a7-113">[Adding an iOS app configuration policy into Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <span data-ttu-id="650a7-114">Para adicionar o aplicativo Skycure para Android</span><span class="sxs-lookup"><span data-stu-id="650a7-114">To add the Skycure app for Android</span></span>
<a id="to-add-the-skycure-app-for-android" class="xliff"></a>

1.  <span data-ttu-id="650a7-115">No console clássico do Intune, escolha **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-115">In the Intune classic console, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="650a7-116">Na página **Instalação do software** escolha **Link externo** e cole a [URL do aplicativo Skycure para Android](https://play.google.com/store/apps/details?id=com.skycure.skycure) em **Especificar a URL**.</span><span class="sxs-lookup"><span data-stu-id="650a7-116">On the **Software setup** page, choose **External link**, then paste the [Skycure app for Android url](https://play.google.com/store/apps/details?id=com.skycure.skycure) under **Specify the URL**.</span></span>

    ![Especificar a URL do Intune Software Publisher](../media/mtp/skycure-add-apps-1.png)

3.  <span data-ttu-id="650a7-118">Na página **Descrição do software**, insira o **Publicador**, o **Nome** e a **Descrição**, selecione a opção **Exibir como um aplicativo em destaque e realçá-lo no portal da empresa**, depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-118">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Descrição do Software do Intune Software Publisher](../media/mtp/skycure-add-apps-2.png)

4.  <span data-ttu-id="650a7-120">Clique em **Carregar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-120">Click **Upload**, then **Close**.</span></span>

## <span data-ttu-id="650a7-121">Para adicionar o aplicativo Skycure para iOS</span><span class="sxs-lookup"><span data-stu-id="650a7-121">To add the Skycure app for iOS</span></span>
<a id="to-add-the-skycure-app-for-ios" class="xliff"></a>

1.  <span data-ttu-id="650a7-122">No console clássico do Intune, escolha **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-122">In the Intune classic console, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="650a7-123">Na página **Configuração do Software** escolha **Aplicativo iOS gerenciado da App Store** e cole a [URL do aplicativo Skycure para iOS](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) em **Especificar a URL**.</span><span class="sxs-lookup"><span data-stu-id="650a7-123">On the **Software setup** page, choose **Managed iOS App from the App Store**, then paste the [Skycure app for iOS url](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) under **Specify the URL**.</span></span>

    ![Aplicativo iOS gerenciado do Intune Software Publisher](../media/mtp/skycure-add-apps-3.png)

3.  <span data-ttu-id="650a7-125">Na página **Descrição do software**, insira o **Publicador**, o **Nome** e a **Descrição**, selecione a opção **Exibir como um aplicativo em destaque e realçá-lo no portal da empresa**, depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-125">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Opções do Intune Software Publisher](../media/mtp/skycure-add-apps-4.png)

4.  <span data-ttu-id="650a7-127">Na página **Requisitos**, selecione a opção **Qualquer** em **Tipo de dispositivo móvel** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-127">On the **Requirements** page, select the option **Any** under **Mobile device type**, then click **Next**.</span></span>

5.  <span data-ttu-id="650a7-128">Clique em **Carregar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-128">Click **Upload**, then **Close**.</span></span>

## <span data-ttu-id="650a7-129">Para adicionar o aplicativo Microsoft Authenticator para iOS</span><span class="sxs-lookup"><span data-stu-id="650a7-129">To add the Microsoft Authenticator app for iOS</span></span>
<a id="to-add-the-microsoft-authenticator-app-for-ios" class="xliff"></a>

1.  <span data-ttu-id="650a7-130">No console clássico do Intune, escolha **Aplicativos** &gt; **Adicionar Aplicativos** para iniciar o Intune Software Publisher e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-130">In the Intune classic console, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="650a7-131">Na página **Configuração do Software** escolha **Aplicativo iOS gerenciado da App Store** e cole a [URL do aplicativo Microsoft Authenticator para iOS](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) em **Especificar a URL**.</span><span class="sxs-lookup"><span data-stu-id="650a7-131">On the **Software setup** page, choose **Managed iOS App from the App Store**, then paste the [Microsoft Authenticator app for iOS url](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) under **Specify the URL**.</span></span>

    ![Aplicativo iOS gerenciado do Intune Software Publisher 2](../media/mtp/skycure-add-apps-5.png)

3.  <span data-ttu-id="650a7-133">Na página **Descrição do software**, insira o **Publicador**, o **Nome** e a **Descrição**, selecione a opção **Exibir como um aplicativo em destaque e realçá-lo no portal da empresa**, depois clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-133">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Aplicativo iOS gerenciado do Intune Software Publisher 3](../media/mtp/skycure-add-apps-6.png)

4.  <span data-ttu-id="650a7-135">Na página **Requisitos**, selecione a opção **Qualquer** em **Tipo de dispositivo móvel** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-135">On the **Requirements** page, select the option **Any** under **Mobile device type**, then click **Next**.</span></span>

5.  <span data-ttu-id="650a7-136">Clique em **Carregar** e em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="650a7-136">Click **Upload**, then **Close**.</span></span>

## <span data-ttu-id="650a7-137">Para adicionar a política de configuração de aplicativo para iOS do Skycure</span><span class="sxs-lookup"><span data-stu-id="650a7-137">To add the Skycure iOS app configuration policy</span></span>
<a id="to-add-the-skycure-ios-app-configuration-policy" class="xliff"></a>

1.  <span data-ttu-id="650a7-138">No console clássico do Intune, escolha **Política** &gt; **Visão geral &gt; Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="650a7-138">In the Intune classic console, choose **Policy** &gt; **Overview &gt; Add Policy**.</span></span>

2.  <span data-ttu-id="650a7-139">Na lista de políticas, expanda **iOS**, escolha **Política de Configuração do Aplicativo Móvel (iOS 8.0 e posterior)**, depois escolha **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="650a7-139">In the list of policies, expand **iOS**, choose **Mobile App Configuration Policy (iOS 8.0 and later)**, then choose **Create Policy**.</span></span>

    ![Política de configuração de aplicativo iOS](../media/mtp/skycure-add-apps-7.png)

3.  <span data-ttu-id="650a7-141">Na seção **Geral** da página **Criar Política**, forneça um nome e uma descrição opcional para a política de configuração de aplicativo para iOS.</span><span class="sxs-lookup"><span data-stu-id="650a7-141">In the **General** section of the **Create Policy** page, supply a name and an optional description for the iOS app configuration policy.</span></span>

    <span data-ttu-id="650a7-142">a.</span><span class="sxs-lookup"><span data-stu-id="650a7-142">a.</span></span>  <span data-ttu-id="650a7-143">Abra o arquivo **skycure\_configuration.plist** usando um editor de texto como o bloco de notas, copie o conteúdo e cole-o no corpo da **Política de Configuração de Aplicativo Móvel**, escolha **Validar** e **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="650a7-143">Open the **skycure\_configuration.plist** file using a text editor like notepad, copy the content and paste it into the **Mobile App Configuration Policy** body, choose **Validate**, then choose **Save Policy**.</span></span>

       ![Política de configuração de aplicativo iOS 2](../media/mtp/skycure-add-apps-8.png)

## <span data-ttu-id="650a7-145">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="650a7-145">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="650a7-146">Implantar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração de aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="650a7-146">Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy</span></span>](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
