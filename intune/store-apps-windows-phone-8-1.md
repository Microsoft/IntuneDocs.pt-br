---
title: Como adicionar aplicativos da Windows Phone 8.1 Store ao Intune
titleSuffix: Intune on Azure
description: Saiba como adicionar aplicativos da loja do Windows Phone 8.1 ao Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a95e575-2c63-4bfc-b9c4-f0a132eef618
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd2d590514ba370b34745c5426c0f047364a1062
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="380e1-103">Como adicionar aplicativos da Store do Windows Phone 8.1 ao Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="380e1-103">How to add Windows Phone 8.1 store apps to Microsoft Intune</span></span>
<a id="how-to-add-windows-phone-81-store-apps-to-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. <span data-ttu-id="380e1-104">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="380e1-104">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="380e1-105">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="380e1-105">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="380e1-106">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="380e1-106">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="380e1-107">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="380e1-107">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="380e1-108">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="380e1-108">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="380e1-109">Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="380e1-109">In the **Add App** blade, choose **App Information**.</span></span>
7. <span data-ttu-id="380e1-110">Na folha **Editar Aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="380e1-110">In the **Edit App** blade, configure the following information.</span></span> <span data-ttu-id="380e1-111">Ao terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="380e1-111">Once you are done, click **Add**.</span></span> <span data-ttu-id="380e1-112">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="380e1-112">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="380e1-113">**Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="380e1-113">**App Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="380e1-114">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="380e1-114">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="380e1-115">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="380e1-115">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="380e1-116">**Descrição do Aplicativo** – Insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-116">**App Description** - Enter a description for the app.</span></span> <span data-ttu-id="380e1-117">Isso será exibido para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="380e1-117">This will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="380e1-118">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-118">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="380e1-119">**URL da loja de aplicativos** – Insira a URL da loja de aplicativos do aplicativo que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="380e1-119">**App store URL** - Enter the app store URL of the app you want to create.</span></span>
    - <span data-ttu-id="380e1-120">**Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado.</span><span class="sxs-lookup"><span data-stu-id="380e1-120">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="380e1-121">Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.</span><span class="sxs-lookup"><span data-stu-id="380e1-121">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
    - <span data-ttu-id="380e1-122">**Categoria (opcional)** – Selecione uma das categorias de aplicativo internas ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="380e1-122">**Category (optional)** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="380e1-123">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="380e1-123">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="380e1-124">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="380e1-124">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="380e1-125">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-125">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="380e1-126">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="380e1-126">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="380e1-127">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-127">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="380e1-128">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="380e1-128">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="380e1-129">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-129">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="380e1-130">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="380e1-130">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="380e1-131">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-131">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="380e1-132">**Carregar Ícone** – Carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="380e1-132">**Upload Icon** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="380e1-133">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="380e1-133">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
8. <span data-ttu-id="380e1-134">Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="380e1-134">When you are done, on the **Add App** blade, choose **Save**.</span></span>

<span data-ttu-id="380e1-135">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="380e1-135">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="380e1-136">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="380e1-136">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>