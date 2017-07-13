---
title: <span data-ttu-id="c95a7-101">Como implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="c95a7-101">How to deploy apps</span></span>
description: "<span data-ttu-id=\"c95a7-102\">Use as informações neste tópico para ajudá-lo a implantar aplicativos com o Microsoft Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"c95a7-102\">Use the information in this topic to help you deploy apps with Microsoft Intune.</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f684a1b8d74f7625d3262d4f02eb9841a203e883
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c95a7-103">Implantar aplicativos no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c95a7-103">Deploy apps in Microsoft Intune</span></span>
<a id="deploy-apps-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c95a7-104">Use as informações neste tópico para ajudá-lo a implantar aplicativos com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="c95a7-104">Use the information in this topic to help you deploy apps with Microsoft Intune.</span></span>


## <span data-ttu-id="c95a7-105">Implantar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="c95a7-105">Deploy an app</span></span>
<a id="deploy-an-app" class="xliff"></a>
<span data-ttu-id="c95a7-106">Neste procedimento, você implantará o aplicativo para os grupos de dispositivos ou usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="c95a7-106">In this procedure, you'll deploy an app to selected groups of devices or users.</span></span>

### <span data-ttu-id="c95a7-107">Para implantar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="c95a7-107">To deploy an app</span></span>
<a id="to-deploy-an-app" class="xliff"></a>

1. <span data-ttu-id="c95a7-108">No [Console do administração do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Aplicativos** para exibir a lista dos aplicativos gerenciados por você.</span><span class="sxs-lookup"><span data-stu-id="c95a7-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Apps** &gt; **Apps** to view the list of apps that you manage.</span></span>

2.  <span data-ttu-id="c95a7-109">Selecione o aplicativo que deseja implantar e clique em **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="c95a7-109">Select the app that you want to deploy, and then click **Manage Deployment**.</span></span>

3.  <span data-ttu-id="c95a7-110">Na caixa de diálogo *&lt;nome do aplicativo&gt;*, na página **Selecionar Grupos**, selecione os grupos de usuários ou de dispositivos nos quais deseja implantar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c95a7-110">In the *&lt;app name&gt;* dialog box, on the **Select Groups** page, choose the user or device groups to which you want to deploy the app.</span></span>

4.  <span data-ttu-id="c95a7-111">Na página **Ação de Implantação**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c95a7-111">On the **Deployment Action** page, configure the following:</span></span>

    - <span data-ttu-id="c95a7-112">**Aprovação** - Escolha se a implantação será:</span><span class="sxs-lookup"><span data-stu-id="c95a7-112">**Approval** - Choose whether the deployment is:</span></span>
        - <span data-ttu-id="c95a7-113">**Necessário** (instalação obrigatória)</span><span class="sxs-lookup"><span data-stu-id="c95a7-113">**Required** (mandatory install)</span></span>
        - <span data-ttu-id="c95a7-114">**Disponível** (usuários instalam por meio do portal da empresa, sob demanda)</span><span class="sxs-lookup"><span data-stu-id="c95a7-114">**Available** (users install from the company portal on demand)</span></span>
        - <span data-ttu-id="c95a7-115">**Não Aplicável** (o aplicativo não está instalado nem é mostrado no portal da empresa)</span><span class="sxs-lookup"><span data-stu-id="c95a7-115">**Not Applicable** (the app is not installed or shown in the company portal)</span></span>
        - <span data-ttu-id="c95a7-116">**Desinstalar** (o aplicativo é desinstalado dos dispositivos de destino)</span><span class="sxs-lookup"><span data-stu-id="c95a7-116">**Uninstall** (the app is uninstalled from targeted devices)</span></span>
    - <span data-ttu-id="c95a7-117">**Data Limite** - Para as instalações necessárias, escolha quando implantar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c95a7-117">**Deadline** - For required installations, choose how soon to deploy the app.</span></span> <span data-ttu-id="c95a7-118">Você pode escolher entre os valores predefinidos ou selecionar **Personalizado** para configurar seu próprio prazo.</span><span class="sxs-lookup"><span data-stu-id="c95a7-118">You can choose from the predefined values, or you can select **Custom** to configure your own deadline.</span></span>

5. <span data-ttu-id="c95a7-119">Se o aplicativo que você está implantando puder ser configurado por uma política de gerenciamento de aplicativo móvel, a página **Gerenciamento de Aplicativo Móvel** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c95a7-119">If the app you are deploying can be configured by a mobile application management policy, the **Mobile App Management** page is displayed.</span></span> <span data-ttu-id="c95a7-120">Nessa página, escolha a política de gerenciamento de aplicativo móvel que você deseja associar a esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c95a7-120">On this page, choose the mobile application management policy that you want to associate with this app.</span></span>

    [<span data-ttu-id="c95a7-121">Veja quais aplicativos da Microsoft são compatíveis com políticas de gerenciamento de aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="c95a7-121">See which Microsoft apps are compatible with mobile application management policies.</span></span>](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. <span data-ttu-id="c95a7-122">Se o aplicativo que você está implantando for compatível com perfis de VPN do Intune, a página **Perfil de VPN** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c95a7-122">If the app you are deploying is compatible with Intune VPN profiles, the **VPN Profile** page is displayed.</span></span> <span data-ttu-id="c95a7-123">Nessa página, você pode optar por associar aplicativos iOS a um perfil de VPN implantado por você anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c95a7-123">On this page, you can choose to associate iOS apps with a VPN profile that you have deployed.</span></span> <span data-ttu-id="c95a7-124">A conexão VPN é aberta automaticamente quando o aplicativo é iniciado.</span><span class="sxs-lookup"><span data-stu-id="c95a7-124">The VPN connection automatically opens when the app is launched.</span></span> <span data-ttu-id="c95a7-125">Para disponibilizar um perfil VPN, ele deve ter a configuração de perfil **VPN por aplicativo** habilitada.</span><span class="sxs-lookup"><span data-stu-id="c95a7-125">To make a VPN profile available, it must have the **Per-app VPN** profile setting enabled.</span></span>
 <span data-ttu-id="c95a7-126">Para obter informações sobre como configurar perfis VPN, incluindo informações sobre como associar perfis a aplicativos, consulte [Conexões VPN no Microsoft Intune](vpn-connections-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c95a7-126">For information about how to configure VPN profiles, including information about how to associate profiles with apps, see [VPN connections in Microsoft Intune](vpn-connections-in-microsoft-intune.md).</span></span>

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <span data-ttu-id="c95a7-127">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c95a7-127">Example</span></span>
<a id="example" class="xliff"></a>

<span data-ttu-id="c95a7-128">Neste exemplo, você implantou o aplicativo como **Disponível** em um dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="c95a7-128">In this example, you deployed the app as **Available** to an iOS device.</span></span>
<span data-ttu-id="c95a7-129">O aplicativo é exibido em dispositivos dos usuários no portal da empresa e os usuários podem instalá-lo de lá.</span><span class="sxs-lookup"><span data-stu-id="c95a7-129">The app displays on users' devices in the company portal, and users can install it from there.</span></span>

<span data-ttu-id="c95a7-130">Por exemplo, nesta captura de tela, o Bing para aplicativo iOS foi implantado usando o tipo de instalação **link externo** com um ícone personalizado.</span><span class="sxs-lookup"><span data-stu-id="c95a7-130">For example, in this screenshot, the Bing for iOS app was deployed by using the **External Link** installation type with a custom icon.</span></span> <span data-ttu-id="c95a7-131">A opção **Exibir como um aplicativo em destaque e realçá-lo no portal de empresa** foi selecionada.</span><span class="sxs-lookup"><span data-stu-id="c95a7-131">The option **Display this as a featured app and highlight it in the company portal** was selected.</span></span>  
<span data-ttu-id="c95a7-132">![Aplicativo disponível para iOS](./media/available-install-on-iOS.png)</span><span class="sxs-lookup"><span data-stu-id="c95a7-132">![iOS available app](./media/available-install-on-iOS.png)</span></span>

<span data-ttu-id="c95a7-133">Se você implantou o aplicativo como **Necessário** em um dispositivo iOS, o usuário receberá uma notificação de que um aplicativo está pronto para ser instalado.</span><span class="sxs-lookup"><span data-stu-id="c95a7-133">If you deployed the app as **Required** to an iOS device, the user will get a notification that an app is ready to install.</span></span> <span data-ttu-id="c95a7-134">Por exemplo, nesta captura de tela, o aplicativo Pastas de Trabalho para iOS foi implantado usando o tipo de instalação **Aplicativo iOS gerenciado da loja de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c95a7-134">For example, in this screenshot, the Work Folders for iOS app was deployed by using the **Managed iOS app from the app store** installation type.</span></span>  
<span data-ttu-id="c95a7-135">![Aplicativo necessário para iOS](./media/iOS-Required-install.PNG)</span><span class="sxs-lookup"><span data-stu-id="c95a7-135">![iOS required app](./media/iOS-Required-install.PNG)</span></span>

## <span data-ttu-id="c95a7-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c95a7-136">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="c95a7-137">Depois de implantar um aplicativo, você vai querer monitorar seu andamento.</span><span class="sxs-lookup"><span data-stu-id="c95a7-137">After you deploy an app, you'll want to monitor its progress.</span></span> <span data-ttu-id="c95a7-138">Para obter mais informações, consulte [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md) (Monitorar aplicativos no Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="c95a7-138">For more information, see [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md).</span></span>
