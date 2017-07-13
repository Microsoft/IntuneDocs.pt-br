---
title: Atualizar aplicativos
description: "Use as informações neste tópico para entender como atualizar aplicativos quando uma nova versão é necessária."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d974a3c8fd69ee970991af96afe2011c6d07db2a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="65693-103">Atualizar aplicativos usando o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="65693-103">Update apps using Microsoft Intune</span></span>
<a id="update-apps-using-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="65693-104">O Microsoft Intune pode ajudar você a gerenciar as atualizações de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65693-104">Microsoft Intune can help you manage app updates.</span></span> <span data-ttu-id="65693-105">Use as informações neste tópico para entender como atualizar aplicativos quando uma nova versão é necessária.</span><span class="sxs-lookup"><span data-stu-id="65693-105">Use the information in this topic to understand how to update apps when a new version is required.</span></span>

## <span data-ttu-id="65693-106">Como atualizar aplicativos</span><span class="sxs-lookup"><span data-stu-id="65693-106">How to update apps</span></span>
<a id="how-to-update-apps" class="xliff"></a>
<span data-ttu-id="65693-107">Quando uma nova versão de um aplicativo que você implantou for lançada, o Intune permitirá que você atualize e implante a versão mais recente do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65693-107">When a new version of an app that you've deployed is released, Intune lets you update and deploy the newer version of the app.</span></span> <span data-ttu-id="65693-108">Só é possível substituir uma implantação por uma versão mais recente do mesmo aplicativo (que tem o mesmo identificador).</span><span class="sxs-lookup"><span data-stu-id="65693-108">You can only replace a deployment with a newer version of the same app (that has the same identifier).</span></span> <span data-ttu-id="65693-109">Não é possível usar atualizações de aplicativo para atualizar uma implantação com um pacote do aplicativo diferente.</span><span class="sxs-lookup"><span data-stu-id="65693-109">You cannot use app updates to update a deployment with a different app package.</span></span>

### <span data-ttu-id="65693-110">Identificadores de aplicativo</span><span class="sxs-lookup"><span data-stu-id="65693-110">App identifiers</span></span>
<a id="app-identifiers" class="xliff"></a>
<span data-ttu-id="65693-111">O identificador de aplicativo é uma propriedade que identifica exclusivamente um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65693-111">The app identifier is a property that uniquely identifies an app.</span></span> <span data-ttu-id="65693-112">Não é possível instalar várias cópias de um aplicativo com o mesmo identificador.</span><span class="sxs-lookup"><span data-stu-id="65693-112">You cannot install multiple copies of an app with the same identifier.</span></span> <span data-ttu-id="65693-113">Veja a seguir alguns exemplos de identificadores de aplicativos:</span><span class="sxs-lookup"><span data-stu-id="65693-113">Following are some examples of app identifiers:</span></span>

- <span data-ttu-id="65693-114">**iOS** – ID do pacote (por exemplo: com.microsoft.excel)</span><span class="sxs-lookup"><span data-stu-id="65693-114">**iOS** - Bundle ID (for example: com.microsoft.excel)</span></span>
- <span data-ttu-id="65693-115">**Android** – ID do pacote (por exemplo: com.microsoft.excel)</span><span class="sxs-lookup"><span data-stu-id="65693-115">**Android** - Package ID (for example: com.microsoft.excel)</span></span>
- <span data-ttu-id="65693-116">**Windows Phone** – (instalador xap), use a ID do produto (GUID)</span><span class="sxs-lookup"><span data-stu-id="65693-116">**Windows Phone** - (xap installer) use Product ID (GUID)</span></span>
- <span data-ttu-id="65693-117">**Windows** – (appx/appxbundle), use o nome completo do pacote</span><span class="sxs-lookup"><span data-stu-id="65693-117">**Windows** - (appx/appxbundle), use the Package Full Name</span></span>



> [!IMPORTANT]
> <span data-ttu-id="65693-118">Quando você implanta um aplicativo com uma ação de implantação de **Instalação requerida** e, posteriormente, altera a ação de implantação para **Instalação disponível**, atualizações do aplicativo não são instaladas automaticamente em dispositivos que instalaram o aplicativo antes da alteração de implantação ter sido feita.</span><span class="sxs-lookup"><span data-stu-id="65693-118">When you deploy an app with a deployment action of **Required install** and later change the deployment action to **Available install**, updates to the app are not automatically installed on devices that installed the app before the deployment change was made.</span></span> <span data-ttu-id="65693-119">Para corrigir esse problema, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="65693-119">To fix this issue, you can do the following:</span></span>
>
> -   <span data-ttu-id="65693-120">O usuário do dispositivo deve ir ao portal da empresa, selecionar o aplicativo instalado e escolher **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="65693-120">Have the user of the device go to the company portal, select the installed app, and then choose **Install**.</span></span>
> -   <span data-ttu-id="65693-121">Altere a ação de implantação para **Desinstalar**e, após o aplicativo ser desinstalado, reimplante o aplicativo com uma ação de implantação de **Instalação disponível**.</span><span class="sxs-lookup"><span data-stu-id="65693-121">Change the deployment action to **Uninstall**, and after the app has been uninstalled, redeploy the app with a deployment action of **Available install**.</span></span>

### <span data-ttu-id="65693-122">Para atualizar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="65693-122">To update an app</span></span>
<a id="to-update-an-app" class="xliff"></a>

1.  <span data-ttu-id="65693-123">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="65693-123">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="65693-124">Na lista **Aplicativos**, selecione o aplicativo que você deseja atualizar e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="65693-124">From the **Apps** list, select the app you want to update, and then choose **Edit**.</span></span>

3.  <span data-ttu-id="65693-125">No assistente **Editar Software** , forneça quaisquer detalhes novos para o pacote do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65693-125">In the **Edit Software** wizard, supply any new details for the app package.</span></span>

4.  <span data-ttu-id="65693-126">Quando você terminar, escolha **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="65693-126">When you are finished, choose **Update**.</span></span>

<span data-ttu-id="65693-127">Da próxima vez que os dispositivos verificarem os aplicativos disponíveis, o aplicativo será atualizado automaticamente para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="65693-127">When devices next check for available apps, the app will be automatically updated to the latest version.</span></span>
<span data-ttu-id="65693-128">Para aplicativos instalados de um pacote do aplicativo (aplicativos de linha de negócios), o aplicativo será atualizado automaticamente para implantações necessárias e disponíveis, desde que o aplicativo tenha o mesmo identificador.</span><span class="sxs-lookup"><span data-stu-id="65693-128">For apps installed from an app package (line of business apps), the app will be upgraded automatically for both required and available deployments, as long as the app has the same identifier.</span></span>

<span data-ttu-id="65693-129">Para aplicativos implantados como um link para um repositório, a atualização é gerenciada pelo repositório do qual se origina o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65693-129">For apps deployed as a link to a store, the update is managed by the store from which the app originates.</span></span>
