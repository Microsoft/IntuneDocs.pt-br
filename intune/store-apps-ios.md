---
title: Como adicionar aplicativos da loja do iOS ao Intune
titleSuffix: Intune on Azure
description: Saiba como adicionar aplicativos da loja do iOS ao Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 84c5b7c2d849fb39a9466d5b92eb4f2a4a411808
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="59b3f-103">Como adicionar aplicativos da iOS Store ao Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="59b3f-103">How to add iOS store apps to Microsoft Intune</span></span>
<a id="how-to-add-ios-store-apps-to-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <span data-ttu-id="59b3f-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="59b3f-104">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="59b3f-105">Você só poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store.</span><span class="sxs-lookup"><span data-stu-id="59b3f-105">You can only assign apps using this method if they are free of charge in the app store.</span></span> <span data-ttu-id="59b3f-106">Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="59b3f-106">If you want to assign paid apps using Intune, consider using the [iOS volume-purchase program](vpp-apps-ios.md).</span></span>


## <span data-ttu-id="59b3f-107">Etapa 1 – Pesquise o aplicativo na loja</span><span class="sxs-lookup"><span data-stu-id="59b3f-107">Step 1 - Search for the app in the store</span></span>
<a id="step-1---search-for-the-app-in-the-store" class="xliff"></a>

1. <span data-ttu-id="59b3f-108">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="59b3f-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="59b3f-109">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="59b3f-110">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-110">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="59b3f-111">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="59b3f-111">In the **Mobile apps** workload, choose **Manage** > Apps.</span></span>
5. <span data-ttu-id="59b3f-112">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-112">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="59b3f-113">Na folha **Adicionar Aplicativo**, escolha **Pesquisar na Loja de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-113">In the **Add App** blade, choose **Search the App Store**.</span></span>
7. <span data-ttu-id="59b3f-114">Na folha **Apple App Store**, digite o nome (ou parte do nome) na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-114">In the **Apple App Store** blade, enter the name (or part of the name) in the search box.</span></span> <span data-ttu-id="59b3f-115">O Intune pesquisará na loja e retornará uma lista de resultados relevantes.</span><span class="sxs-lookup"><span data-stu-id="59b3f-115">Intune will search the store and return a list of relevant results.</span></span>
8. <span data-ttu-id="59b3f-116">Na lista, escolha o aplicativo que desejar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-116">From the list, choose the app you want, then click **OK**.</span></span>

## <span data-ttu-id="59b3f-117">Etapa 2 – Configurar informações de aplicativo</span><span class="sxs-lookup"><span data-stu-id="59b3f-117">Step 2 - Configure app information</span></span>
<a id="step-2---configure-app-information" class="xliff"></a>

1. <span data-ttu-id="59b3f-118">Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-118">In the **Add App** blade, choose **App Information**.</span></span>
2. <span data-ttu-id="59b3f-119">Na folha **Editar Aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="59b3f-119">In the **Edit App** blade, configure the following information.</span></span> <span data-ttu-id="59b3f-120">Ao terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-120">Once you are done, click **Add**.</span></span> <span data-ttu-id="59b3f-121">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="59b3f-121">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
- <span data-ttu-id="59b3f-122">**Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-122">**App Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="59b3f-123">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="59b3f-123">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="59b3f-124">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-124">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="59b3f-125">**Descrição do Aplicativo** – Insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-125">**App Description** - Enter a description for the app.</span></span> <span data-ttu-id="59b3f-126">Isso será exibido para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-126">This will be displayed to users in the company portal.</span></span>
- <span data-ttu-id="59b3f-127">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-127">**Publisher** - Enter the name of the publisher of the app.</span></span>
- <span data-ttu-id="59b3f-128">**URL da loja de aplicativos** – Insira a URL da loja de aplicativos do aplicativo que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="59b3f-128">**App store URL** - Enter the app store URL of the app you want to create.</span></span>
- <span data-ttu-id="59b3f-129">**Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado.</span><span class="sxs-lookup"><span data-stu-id="59b3f-129">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="59b3f-130">Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.</span><span class="sxs-lookup"><span data-stu-id="59b3f-130">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
- <span data-ttu-id="59b3f-131">**Categoria** (opcional).</span><span class="sxs-lookup"><span data-stu-id="59b3f-131">**Category** (optional).</span></span> <span data-ttu-id="59b3f-132">Selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="59b3f-132">Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="59b3f-133">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="59b3f-133">This will make it easier for users to find the app when they browse the company portal.</span></span>
- <span data-ttu-id="59b3f-134">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="59b3f-134">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
- <span data-ttu-id="59b3f-135">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-135">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="59b3f-136">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-136">The URL will be displayed to users in the company portal.</span></span>
- <span data-ttu-id="59b3f-137">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-137">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="59b3f-138">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-138">The URL will be displayed to users in the company portal.</span></span>
- <span data-ttu-id="59b3f-139">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-139">**Developer** - Optionally, enter the name of the app developer.</span></span>
- <span data-ttu-id="59b3f-140">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-140">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
- <span data-ttu-id="59b3f-141">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-141">**Notes** - Enter any notes you would like to associate with this app.</span></span>
- <span data-ttu-id="59b3f-142">**Carregar Ícone** – Carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59b3f-142">**Upload Icon** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="59b3f-143">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59b3f-143">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="59b3f-144">Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="59b3f-144">When you are done, on the **Add App** blade, choose **Save**.</span></span>

<span data-ttu-id="59b3f-145">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="59b3f-145">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="59b3f-146">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="59b3f-146">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
