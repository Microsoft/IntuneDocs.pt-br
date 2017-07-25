---
title: "Implantar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS"
description: "Implante aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 45826fbc-6df5-41b2-8e80-d1353f904b43
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 60f4ab5a656a2e253d82971d7bea6b3a6c9eb25a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6d2ce-103">Implantar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração de aplicativo iOS</span><span class="sxs-lookup"><span data-stu-id="6d2ce-103">Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy</span></span>
<a id="deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="6d2ce-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6d2ce-104">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

-   <span data-ttu-id="6d2ce-105">As etapas a seguir devem ser concluídas no [console clássico do Intune](https://manage.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6d2ce-105">The below steps need to be completed in the [Intune classic console](https://manage.microsoft.com/).</span></span>

-   <span data-ttu-id="6d2ce-106">Use a mesma conta do Azure AD previamente configurada no Console de gerenciamento do Skycure, que deve ser a mesma conta usada para fazer logon no console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-106">Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic console.</span></span>

-   <span data-ttu-id="6d2ce-107">Verifique se que você está familiarizado com o processo de:</span><span class="sxs-lookup"><span data-stu-id="6d2ce-107">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="6d2ce-108">[Implantar um aplicativo com o Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="6d2ce-108">[Deploying an app with Intune](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="6d2ce-109">[Implantar a política de configuração de aplicativo do iOS](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="6d2ce-109">[Deploying an iOS app configuration policy](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <span data-ttu-id="6d2ce-110">Para implantar aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração de aplicativo do iOS</span><span class="sxs-lookup"><span data-stu-id="6d2ce-110">To deploy Skycure apps, Microsoft Authenticator app and the iOS app configuration policy</span></span>
<a id="to-deploy-skycure-apps-microsoft-authenticator-app-and-the-ios-app-configuration-policy" class="xliff"></a>

1.  <span data-ttu-id="6d2ce-111">No console clássico do Intune, escolha **Aplicativos** &gt; **Aplicativos** para exibir a lista de aplicativos que você pode gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-111">In the Intune classic console, choose **Apps** &gt; **Apps** to view the list of apps that you can manage.</span></span>

2.  <span data-ttu-id="6d2ce-112">Selecione os seguintes aplicativos:</span><span class="sxs-lookup"><span data-stu-id="6d2ce-112">Select the following apps:</span></span>

    <span data-ttu-id="6d2ce-113">a.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-113">a.</span></span>  <span data-ttu-id="6d2ce-114">Microsoft Authenticator</span><span class="sxs-lookup"><span data-stu-id="6d2ce-114">Microsoft Authenticator</span></span>

    <span data-ttu-id="6d2ce-115">b.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-115">b.</span></span>  <span data-ttu-id="6d2ce-116">Aplicativo Skycure para Android</span><span class="sxs-lookup"><span data-stu-id="6d2ce-116">Skycure app for Android</span></span>

    <span data-ttu-id="6d2ce-117">c.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-117">c.</span></span>  <span data-ttu-id="6d2ce-118">Aplicativo Skycure para iOS</span><span class="sxs-lookup"><span data-stu-id="6d2ce-118">Skycure app for iOS</span></span>

       ![Todos os aplicativos do console clássico do Intune para implantar](../media/mtp/skycure-deploy-app-1.png)

3.  <span data-ttu-id="6d2ce-120">Escolha **Gerenciar Implantações**, selecione o grupo de segurança do Azure AD que tenha os usuários do Skycure, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-120">Choose **Manage Deployments,** select the Azure AD security group that has the Skycure users, then click **Next**.</span></span>

4.  <span data-ttu-id="6d2ce-121">Na página **Ação de Implantação**, selecione a opção **Instalação Necessária** do menu suspenso **Aprovação**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-121">On the **Deployment Action** page, select the option **Required Install** from the **Approval** drop-down list, then click **Next**.</span></span>

    ![Ação de implantação do console clássico do Intune](../media/mtp/skycure-deploy-app-2.png)

5.  <span data-ttu-id="6d2ce-123">Na página **Perfil de VPN**, selecione a opção **Nenhum** na lista suspensa **Política de VPN** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-123">On the **VPN profile** page, select the option **None** from the **VPN Policy** drop-down list, then click **Next**.</span></span>

6.  <span data-ttu-id="6d2ce-124">Na página **Configuração de Aplicativo Móvel**, selecione a Política de Configuração de Aplicativo do iOS criada anteriormente na lista suspensa **Política de Configuração do Aplicativo** e, em seguida, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="6d2ce-124">On the **Mobile App Configuration** page, select the iOS App Configuration Policy previously created from the **App Configuration Policy** drop-down list, then click **Finish**.</span></span>

    ![Configuração de aplicativo móvel do console clássico do Intune](../media/mtp/skycure-deploy-app-3.png)

## <span data-ttu-id="6d2ce-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6d2ce-126">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="6d2ce-127">Configurar a integração do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="6d2ce-127">Set up the Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)
