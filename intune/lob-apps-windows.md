---
title: "Como adicionar aplicativos de linha de negócios do Windows ao Intune"
titleSuffix: Intune on Azure
description: "Saiba como adicionar aplicativos de linha de negócios do Windows ao Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f8be4f6bf47ceb966e9042465dc8839d9aa9119
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="67d8b-103">Como adicionar aplicativos de linha de negócios (LOB) do Windows para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="67d8b-103">How to add Windows line-of-business (LOB) apps to Microsoft Intune</span></span>
<a id="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <span data-ttu-id="67d8b-104">Etapa 1 – Especificar os arquivos de instalação de software</span><span class="sxs-lookup"><span data-stu-id="67d8b-104">Step 1 - Specify the software setup file</span></span>
<a id="step-1---specify-the-software-setup-file" class="xliff"></a>

1. <span data-ttu-id="67d8b-105">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="67d8b-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="67d8b-106">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="67d8b-107">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="67d8b-108">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="67d8b-109">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="67d8b-110">Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <span data-ttu-id="67d8b-111">Etapa 2 - configurar o arquivo de pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="67d8b-111">Step 2 - Configure the app package file</span></span>
<a id="step-2---configure-the-app-package-file" class="xliff"></a>

1. <span data-ttu-id="67d8b-112">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="67d8b-113">Na folha do arquivo **Pacote de aplicativos**, escolha o botão Procurar e selecione um arquivo de instalação do Windows com a extensão **.msi** (não há suporte para outros tipos de arquivo de instalação).</span><span class="sxs-lookup"><span data-stu-id="67d8b-113">On the **App package** file blade, choose the browse button, and select a Windows installation file with the extension **.msi** (other installation file types are not supported).</span></span>
3. <span data-ttu-id="67d8b-114">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-114">When you are finished, choose **OK**.</span></span>


## <span data-ttu-id="67d8b-115">Etapa 3 - configurar informações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="67d8b-115">Step 3 - Configure app information</span></span>
<a id="step-3---configure-app-information" class="xliff"></a>

1. <span data-ttu-id="67d8b-116">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="67d8b-117">Na folha **informações do aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="67d8b-117">On the **App information** blade, configure the following information.</span></span> <span data-ttu-id="67d8b-118">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="67d8b-118">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="67d8b-119">**Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="67d8b-119">**Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="67d8b-120">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="67d8b-120">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="67d8b-121">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="67d8b-121">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="67d8b-122">**Descrição**: insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-122">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="67d8b-123">Isso será exibido para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="67d8b-123">This will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="67d8b-124">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-124">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="67d8b-125">**Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="67d8b-125">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="67d8b-126">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="67d8b-126">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="67d8b-127">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="67d8b-127">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="67d8b-128">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-128">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="67d8b-129">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="67d8b-129">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="67d8b-130">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-130">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="67d8b-131">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="67d8b-131">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="67d8b-132">**Argumentos de linha de comando** – opcionalmente, insira os argumentos de linha de comando que você deseja aplicar ao arquivo .msi quando ele for executado, como **/q**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-132">**Command-line arguments** - Optionally, enter any command line arguments that you want to apply to the .msi file when it runs, like **/q**.</span></span>
    - <span data-ttu-id="67d8b-133">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-133">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="67d8b-134">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-134">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="67d8b-135">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-135">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="67d8b-136">**Logotipo** - carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="67d8b-136">**Logo** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="67d8b-137">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="67d8b-137">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="67d8b-138">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="67d8b-138">When you are finished, choose **OK**.</span></span>

## <span data-ttu-id="67d8b-139">Etapa 4 - conclusão</span><span class="sxs-lookup"><span data-stu-id="67d8b-139">Step 4 - Finish up</span></span>
<a id="step-4---finish-up" class="xliff"></a>

1. <span data-ttu-id="67d8b-140">Na folha **Adicionar aplicativo**, verifique se as informações configuradas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="67d8b-140">On the **Add app** blade, verify the information you configured is correct.</span></span>
2. <span data-ttu-id="67d8b-141">Escolha **Adicionar** para carregar o aplicativo no Intune.</span><span class="sxs-lookup"><span data-stu-id="67d8b-141">Choose **Add**, to upload the app to Intune.</span></span>

<span data-ttu-id="67d8b-142">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="67d8b-142">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="67d8b-143">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="67d8b-143">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
