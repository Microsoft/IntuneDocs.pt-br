---
title: "<span data-ttu-id=\"59308-101\">Como adicionar aplicativos de linha de negócios do Windows Phone ao Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"59308-101\">How to add Windows Phone line-of-business apps to Intune</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"59308-102\">Saiba como adicionar aplicativos de linha de negócios do Windows Phone ao Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"59308-102\">Learn about adding Windows Phone line-of-business apps to Intune.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f27ad720556a866b5f2a9326df0a574cc37f2a5d
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="59308-103">Como adicionar aplicativos de linha de negócios (LOB) do Windows Phone para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="59308-103">How to add Windows Phone line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="59308-104">Etapa 1 – Especificar os arquivos de instalação de software</span><span class="sxs-lookup"><span data-stu-id="59308-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="59308-105">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="59308-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="59308-106">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="59308-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="59308-107">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="59308-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="59308-108">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="59308-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="59308-109">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="59308-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="59308-110">Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.</span><span class="sxs-lookup"><span data-stu-id="59308-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="59308-111">Etapa 2 - configurar o arquivo de pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="59308-111">Step 2 - Configure the app package file</span></span>

<<<<<<< HEAD
1. <span data-ttu-id="59308-112">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="59308-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="59308-113">Na folha do arquivo **Pacote do aplicativo**, escolha o botão Procurar e selecione um arquivo de instalação do Windows Phone com a extensão **.xap**.</span><span class="sxs-lookup"><span data-stu-id="59308-113">On the **App package** file blade, choose the browse button, and select a Windows Phone installation file with the extension, **.xap**.</span></span>
3. <span data-ttu-id="59308-114">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="59308-114">When you are finished, choose **OK**.</span></span>
=======
1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha do arquivo **Pacote do aplicativo**, escolha o botão Procurar e selecione um arquivo de instalação do Windows Phone com a extensão **.xap**.
3. Quando terminar, escolha **OK**.
>>>>>>> live


## <a name="step-3---configure-app-information"></a><span data-ttu-id="59308-115">Etapa 3 - configurar informações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="59308-115">Step 3 - Configure app information</span></span>

<<<<<<< HEAD
1. <span data-ttu-id="59308-116">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="59308-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="59308-117">Na folha **informações do aplicativo**, configure as informações do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-117">On the **App information** blade, configure the app information.</span></span> <span data-ttu-id="59308-118">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="59308-118">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="59308-119">**Nome** – insira o nome do aplicativo como ele é exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-119">**Name** - Enter the name of the app as it is displayed in the company portal.</span></span> <span data-ttu-id="59308-120">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="59308-120">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="59308-121">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-121">If the same app name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="59308-122">**Descrição**: insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-122">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="59308-123">A descrição é exibida para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-123">The description is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="59308-124">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-124">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="59308-125">**Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="59308-125">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="59308-126">O uso de categorias facilita a localização do aplicativo pelos usuários quando eles navegam pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-126">Using categories makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="59308-127">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="59308-127">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="59308-128">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-128">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="59308-129">A URL é exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-129">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="59308-130">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-130">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="59308-131">A URL é exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-131">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="59308-132">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="59308-133">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="59308-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="59308-134">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="59308-135">**Logotipo** – carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59308-135">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="59308-136">Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="59308-136">This icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="59308-137">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="59308-137">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="59308-138">Etapa 4 - conclusão</span><span class="sxs-lookup"><span data-stu-id="59308-138">Step 4 - Finish up</span></span>
=======
1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha **informações do aplicativo**, configure as informações do aplicativo. Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:
    - **Nome** – insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. O uso de categorias facilita a localização do aplicativo pelos usuários quando eles navegam pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Logotipo** – carregue um ícone que será associado ao aplicativo. Esse ícone é exibido com o aplicativo quando os usuários navegam pelo portal da empresa.
3. Quando terminar, escolha **OK**.
>>>>>>> live

1. <span data-ttu-id="59308-139">Na folha **Adicionar aplicativo**, verifique se você configurou as informações corretamente.</span><span class="sxs-lookup"><span data-stu-id="59308-139">On the **Add app** blade, verify that you configured the information correctly.</span></span>
2. <span data-ttu-id="59308-140">Escolha **Adicionar** para carregar o aplicativo no Intune.</span><span class="sxs-lookup"><span data-stu-id="59308-140">Choose **Add**, to upload the app to Intune.</span></span>

<<<<<<< HEAD
## <a name="next-steps"></a><span data-ttu-id="59308-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="59308-141">Next steps</span></span>

<span data-ttu-id="59308-142">O aplicativo que você criou será exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="59308-142">The app you have created are displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="59308-143">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="59308-143">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
=======
1. Na folha **Adicionar aplicativo**, verifique se você configurou as informações corretamente.
2. Escolha **Adicionar** para carregar o aplicativo no Intune.

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou será exibido na lista de aplicativos, na qual você poderá atribuí-lo aos grupos que escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).
>>>>>>> live
