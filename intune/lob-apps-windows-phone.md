---
title: "Como adicionar aplicativos de linha de negócios do Windows Phone ao Intune"
titleSuffix: Intune on Azure
description: "Saiba como adicionar aplicativos de linha de negócios do Windows Phone ao Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5c27b1a7d0c24bacc206cabe65bd3529a50fc2b4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b6b8f-103">Como adicionar aplicativos de linha de negócios (LOB) do Windows Phone para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b6b8f-103">How to add Windows Phone line-of-business (LOB) apps to Microsoft Intune</span></span>
<a id="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <span data-ttu-id="b6b8f-104">Etapa 1 – Especificar os arquivos de instalação de software</span><span class="sxs-lookup"><span data-stu-id="b6b8f-104">Step 1 - Specify the software setup file</span></span>
<a id="step-1---specify-the-software-setup-file" class="xliff"></a>

1. <span data-ttu-id="b6b8f-105">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b6b8f-106">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b6b8f-107">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="b6b8f-108">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="b6b8f-109">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="b6b8f-110">Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <span data-ttu-id="b6b8f-111">Etapa 2 - configurar o arquivo de pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="b6b8f-111">Step 2 - Configure the app package file</span></span>
<a id="step-2---configure-the-app-package-file" class="xliff"></a>

1. <span data-ttu-id="b6b8f-112">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="b6b8f-113">Na folha do arquivo **Pacote de aplicativos**, escolha o botão Procurar e selecione um arquivo de instalação do Windows Phone com a extensão **.xap**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-113">On the **App package** file blade, choose the browse button, and select a Windows Phone installation file with the extension **.xap**.</span></span>
3. <span data-ttu-id="b6b8f-114">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-114">When you are finished, choose **OK**.</span></span>


## <span data-ttu-id="b6b8f-115">Etapa 3 - configurar informações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="b6b8f-115">Step 3 - Configure app information</span></span>
<a id="step-3---configure-app-information" class="xliff"></a>

1. <span data-ttu-id="b6b8f-116">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="b6b8f-117">Na folha **informações do aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-117">On the **App information** blade, configure the following information.</span></span> <span data-ttu-id="b6b8f-118">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="b6b8f-118">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="b6b8f-119">**Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-119">**Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="b6b8f-120">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-120">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="b6b8f-121">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-121">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="b6b8f-122">**Descrição**: insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-122">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="b6b8f-123">Isso será exibido para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-123">This will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="b6b8f-124">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-124">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="b6b8f-125">**Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-125">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="b6b8f-126">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="b6b8f-126">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="b6b8f-127">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-127">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="b6b8f-128">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-128">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="b6b8f-129">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-129">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="b6b8f-130">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-130">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="b6b8f-131">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-131">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="b6b8f-132">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="b6b8f-133">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="b6b8f-134">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="b6b8f-135">**Logotipo** - carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-135">**Logo** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="b6b8f-136">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-136">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="b6b8f-137">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-137">When you are finished, choose **OK**.</span></span>

## <span data-ttu-id="b6b8f-138">Etapa 4 - conclusão</span><span class="sxs-lookup"><span data-stu-id="b6b8f-138">Step 4 - Finish up</span></span>
<a id="step-4---finish-up" class="xliff"></a>

1. <span data-ttu-id="b6b8f-139">Na folha **Adicionar aplicativo**, verifique se as informações configuradas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-139">On the **Add app** blade, verify the information you configured is correct.</span></span>
2. <span data-ttu-id="b6b8f-140">Escolha **Adicionar** para carregar o aplicativo no Intune.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-140">Choose **Add**, to upload the app to Intune.</span></span>

<span data-ttu-id="b6b8f-141">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="b6b8f-141">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="b6b8f-142">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="b6b8f-142">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
