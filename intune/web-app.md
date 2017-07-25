---
title: Como adicionar aplicativos Web ao Intune
titleSuffix: Intune on Azure
description: Saiba como adicionar aplicativos Web ao Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 476e547f2ee21119443b08db0984f66844f701d3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1cc4e-103">Como adicionar aplicativos Web ao Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1cc4e-103">How to add web apps to Microsoft Intune</span></span>
<a id="how-to-add-web-apps-to-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

1. <span data-ttu-id="1cc4e-104">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-104">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="1cc4e-105">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-105">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="1cc4e-106">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-106">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="1cc4e-107">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-107">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="1cc4e-108">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-108">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="1cc4e-109">Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-109">In the **Add App** blade, choose **App Information**.</span></span>
7. <span data-ttu-id="1cc4e-110">Na folha **Editar Aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-110">In the **Edit App** blade, configure the following information.</span></span> <span data-ttu-id="1cc4e-111">Ao terminar, clique em **Adicionar**:</span><span class="sxs-lookup"><span data-stu-id="1cc4e-111">Once you are done, click **Add**:</span></span>
    - <span data-ttu-id="1cc4e-112">**URL do aplicativo** – insira a URL do site da web que hospeda o aplicativo que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-112">**App URL** - Enter the URL of the web site that hosts the app you want to assign.</span></span>
    - <span data-ttu-id="1cc4e-113">**Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-113">**App Name** - Enter the name of the app as it will be displayed in the company portal.</span></span>
    - <span data-ttu-id="1cc4e-114">**Descrição do Aplicativo** – Insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-114">**App Description** - Enter a description for the app.</span></span> <span data-ttu-id="1cc4e-115">Isso será exibido para os usuários finais no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-115">This will be displayed to end users in the company portal.</span></span>
    - <span data-ttu-id="1cc4e-116">**Editor** – insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-116">**Publisher** - Enter the name of the publisher of this app.</span></span>
    - <span data-ttu-id="1cc4e-117">**Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-117">**Category (optional)** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="1cc4e-118">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="1cc4e-118">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="1cc4e-119">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-119">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="1cc4e-120">**Requer um navegador gerenciado para abrir esse link** – quando você atribui um link para um site ou aplicativo Web aos usuários, eles só poderão abri-lo no navegador gerenciado do Intune.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-120">**Require a managed browser to open this link** - When you assign a link to a website or web app to users, they will be able to open it only in the Intune managed browser.</span></span> <span data-ttu-id="1cc4e-121">Este navegador deve estar instalado em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-121">This browser must be installed on their device.</span></span>
    - <span data-ttu-id="1cc4e-122">**Carregar Ícone** – Carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-122">**Upload Icon** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="1cc4e-123">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-123">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
8. <span data-ttu-id="1cc4e-124">Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-124">When you are done, on the **Add App** blade, choose **Save**.</span></span>

<span data-ttu-id="1cc4e-125">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="1cc4e-125">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="1cc4e-126">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="1cc4e-126">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>