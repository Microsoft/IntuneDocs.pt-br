---
title: "<span data-ttu-id=\"65afb-101\">Como adicionar aplicativos de linha de negócios do Windows ao Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"65afb-101\">How to add Windows line-of-business apps to Intune</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"65afb-102\">Saiba como adicionar aplicativos de linha de negócios do Windows ao Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"65afb-102\">Learn about adding Windows line-of-business apps to Intune.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c01099888ed4cfd04264ad902c73cf475385f1e3
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="65afb-103">Como adicionar aplicativos de linha de negócios (LOB) do Windows para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="65afb-103">How to add Windows line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="65afb-104">Etapa 1 – Especificar os arquivos de instalação de software</span><span class="sxs-lookup"><span data-stu-id="65afb-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="65afb-105">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="65afb-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="65afb-106">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="65afb-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="65afb-107">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="65afb-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="65afb-108">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="65afb-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="65afb-109">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="65afb-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="65afb-110">Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.</span><span class="sxs-lookup"><span data-stu-id="65afb-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="65afb-111">Etapa 2 - configurar o arquivo de pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="65afb-111">Step 2 - Configure the app package file</span></span>

<<<<<<< HEAD
1. <span data-ttu-id="65afb-112">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="65afb-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="65afb-113">Na folha do arquivo **Pacote do aplicativo**, escolha o botão Procurar e selecione um arquivo de instalação do Windows com a extensão **.msi**, **.appx** ou **.appxbundle**.</span><span class="sxs-lookup"><span data-stu-id="65afb-113">On the **App package** file blade, choose the browse button, and select a Windows installation file with the extension **.msi**, **.appx**, or **.appxbundle**.</span></span>
3. <span data-ttu-id="65afb-114">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="65afb-114">When you are finished, choose **OK**.</span></span>
=======
1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha do arquivo **Pacote do aplicativo**, escolha o botão Procurar e selecione um arquivo de instalação do Windows com a extensão **.msi**, **.appx** ou **.appxbundle**.
3. Quando terminar, escolha **OK**.
>>>>>>> live


## <a name="step-3---configure-app-information"></a><span data-ttu-id="65afb-115">Etapa 3 - configurar informações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="65afb-115">Step 3 - Configure app information</span></span>

<<<<<<< HEAD
1. <span data-ttu-id="65afb-116">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="65afb-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="65afb-117">Na folha **Informações do aplicativo**, configure as informações a seguir (alguns dos valores nessa folha podem ser preenchidos automaticamente):</span><span class="sxs-lookup"><span data-stu-id="65afb-117">On the **App information** blade, configure the following information (some of the values in this blade might be automatically filled-in):</span></span>
    - <span data-ttu-id="65afb-118">**Nome** – insira o nome do aplicativo como ele é exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-118">**Name** - Enter the name of the app as it is displayed in the company portal.</span></span> <span data-ttu-id="65afb-119">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="65afb-119">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="65afb-120">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-120">If the same app name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="65afb-121">**Descrição**: insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-121">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="65afb-122">A descrição é exibida para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-122">The description is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="65afb-123">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-123">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="65afb-124">**Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="65afb-124">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="65afb-125">Categorizar os aplicativos facilita a localização do aplicativo pelos usuários quando eles navegam pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-125">Categorizing apps makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="65afb-126">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="65afb-126">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="65afb-127">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-127">**Information URL** - Optionally, enter the URL of a website that contains information about the app.</span></span> <span data-ttu-id="65afb-128">A URL é exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-128">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="65afb-129">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-129">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for the app.</span></span> <span data-ttu-id="65afb-130">A URL é exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-130">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="65afb-131">**Argumentos de linha de comando** – opcionalmente, insira os argumentos de linha de comando que você deseja aplicar ao arquivo .msi quando ele for executado, tais como **/q**.</span><span class="sxs-lookup"><span data-stu-id="65afb-131">**Command-line arguments** - Optionally, enter any command-line arguments that you want to apply to the .msi file when it runs, like **/q**.</span></span>
    - <span data-ttu-id="65afb-132">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="65afb-133">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="65afb-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="65afb-134">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="65afb-135">**Logotipo** – carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="65afb-135">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="65afb-136">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="65afb-136">The icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="65afb-137">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="65afb-137">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="65afb-138">Etapa 4 - conclusão</span><span class="sxs-lookup"><span data-stu-id="65afb-138">Step 4 - Finish up</span></span>
=======
1. Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.
2. Na folha **Informações do aplicativo**, configure as informações a seguir (alguns dos valores nessa folha podem ser preenchidos automaticamente):
    - **Nome** – insira o nome do aplicativo como ele é exibido no portal da empresa. Certifique-se de que todos os nomes de aplicativo usados são exclusivos. Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.
    - **Descrição**: insira uma descrição para o aplicativo. A descrição é exibida para usuários no portal da empresa.
    - **Editor**: insira o nome do editor do aplicativo.
    - **Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você. Categorizar os aplicativos facilita a localização do aplicativo pelos usuários quando eles navegam pelo portal da empresa.
    - **Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.
    - **URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre o aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade do aplicativo. A URL é exibida para os usuários no portal da empresa.
    - **Argumentos de linha de comando** – opcionalmente, insira os argumentos de linha de comando que você deseja aplicar ao arquivo .msi quando ele for executado, tais como **/q**.
    - **Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.
    - **Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.
    - **Observações** – Digite as observações que você deseja associar a este aplicativo.
    - **Logotipo** – carregue um ícone que será associado ao aplicativo. Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.
3. Quando terminar, escolha **OK**.
>>>>>>> live

1. <span data-ttu-id="65afb-139">Na folha **Adicionar aplicativo**, verifique se você configurou as informações do aplicativo corretamente.</span><span class="sxs-lookup"><span data-stu-id="65afb-139">On the **Add app** blade, verify you configured the app information correctly.</span></span>
2. <span data-ttu-id="65afb-140">Escolha **Adicionar** para carregar o aplicativo no Intune.</span><span class="sxs-lookup"><span data-stu-id="65afb-140">Choose **Add**, to upload the app to Intune.</span></span>

<<<<<<< HEAD
## <a name="next-steps"></a><span data-ttu-id="65afb-141">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="65afb-141">Next steps</span></span>

<span data-ttu-id="65afb-142">O aplicativo que você criou é exibido na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="65afb-142">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="65afb-143">Agora você pode atribuí-lo aos grupos que você escolher.</span><span class="sxs-lookup"><span data-stu-id="65afb-143">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="65afb-144">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="65afb-144">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
=======
1. Na folha **Adicionar aplicativo**, verifique se você configurou as informações do aplicativo corretamente.
2. Escolha **Adicionar** para carregar o aplicativo no Intune.

## <a name="next-steps"></a>Próximas etapas

O aplicativo que você criou é exibido na lista de aplicativos. Agora você pode atribuí-lo aos grupos que você escolher. Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).
>>>>>>> live
