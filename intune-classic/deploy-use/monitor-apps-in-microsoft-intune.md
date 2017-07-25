---
title: "Monitorar implantações de aplicativo"
description: Saiba como monitorar aplicativos implantados com o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9255a9cb966ef02aba11e0a6aaf7caf7e808a41c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b88d3-103">Monitorar implantações de aplicativo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b88d3-103">Monitor app deployments in Microsoft Intune</span></span>
<a id="monitor-app-deployments-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="b88d3-104">Monitorar uma implantação de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b88d3-104">Monitor an app deployment</span></span>
<a id="monitor-an-app-deployment" class="xliff"></a>
<span data-ttu-id="b88d3-105">Você pode ver os aplicativos gerenciados e o status de todas as implantações no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="b88d3-105">You can see the apps that you manage and the status of any deployments in the Intune administration console.</span></span> <!---App status is displayed in real-time. You don't have to wait for the device to check-in before you can see this.--->

### <span data-ttu-id="b88d3-106">Para exibir os aplicativos gerenciados e seu status</span><span class="sxs-lookup"><span data-stu-id="b88d3-106">To view apps that you manage and their status</span></span>
<a id="to-view-apps-that-you-manage-and-their-status" class="xliff"></a>
<span data-ttu-id="b88d3-107">No espaço de trabalho **Aplicativos**, escolha o nó **Aplicativos** e escolha **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b88d3-107">In the **Apps** workspace, choose the **Apps** node, and then choose **Apps**.</span></span>

<span data-ttu-id="b88d3-108">É exibida a lista de aplicativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="b88d3-108">The list of apps that you manage appears.</span></span> <span data-ttu-id="b88d3-109">Você pode escolher qualquer aplicativo para ver um status de instalação no painel inferior das janelas do console.</span><span class="sxs-lookup"><span data-stu-id="b88d3-109">You can choose any app to see an installation status in the lower pane of the console windows.</span></span> <span data-ttu-id="b88d3-110">Clique nesse status para ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="b88d3-110">Choose this status to see further details.</span></span> <span data-ttu-id="b88d3-111">Por exemplo, se o status mostra **1 usuário tem este software disponível**, você pode escolher a mensagem para ver o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="b88d3-111">For example, if the status shows **1 user has this software available**, you can choose the message to see the name of the user.</span></span>

> [!TIP]
> <span data-ttu-id="b88d3-112">É possível usar a lista suspensa **Filtros** para mostrar apenas os aplicativos que atendem aos critérios especificados por você, como aplicativos cuja instalação falhou ou aplicativos que foram implantados com êxito.</span><span class="sxs-lookup"><span data-stu-id="b88d3-112">You can use the **Filters** drop-down list to show only apps that meet the criteria that you specify, like apps that failed to install or apps that were successfully deployed.</span></span>
>
> ![Exemplo de filtros de aplicativo](./media/app-filters.png)

<span data-ttu-id="b88d3-114">Além disso, o espaço de trabalho **Painel** mostra uma visão geral do status de seus aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b88d3-114">Additionally, the **Dashboard** workspace shows an overview of the status of your apps.</span></span> <span data-ttu-id="b88d3-115">Se você clicar em qualquer lugar na visão geral, você será levado à lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b88d3-115">If you click anywhere in the overview, you'll be taken to the list of apps.</span></span>

## <span data-ttu-id="b88d3-116">Para exibir informações mais detalhadas sobre um aplicativo</span><span class="sxs-lookup"><span data-stu-id="b88d3-116">To view more detailed information about an app</span></span>
<a id="to-view-more-detailed-information-about-an-app" class="xliff"></a>
<span data-ttu-id="b88d3-117">Na lista de aplicativos, selecione qualquer aplicativo e escolha **Exibir Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b88d3-117">In the list of apps, select any app, and then choose **View Properties**.</span></span>

<span data-ttu-id="b88d3-118">Na página **Propriedades de Software** do aplicativo, clique em uma dessas guias: **Geral** – mostra informações gerais sobre o aplicativo e seu status de instalação, **Dispositivos** – mostra os dispositivos que instalaram com êxito uma implantação direcionada do aplicativo e **Usuários** – mostra os usuários cujos dispositivos instalaram com êxito uma implantação direcionada do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b88d3-118">On the **Software Properties** page for the app, choose one of these tabs: **General** - Shows general information about the app and its installation status, **Devices** - Shows the devices that successfully installed a targeted deployment of the app, and **Users** - Shows the users whose devices successfully installed a targeted deployment of the app.</span></span>

<span data-ttu-id="b88d3-119">Assim como antes, você pode usar a lista suspensa **Filtros** para configurar os valores mostrados em cada uma das guias.</span><span class="sxs-lookup"><span data-stu-id="b88d3-119">As before, you can use the **Filters** drop-down list to configure the values shown on each of the tabs.</span></span>
