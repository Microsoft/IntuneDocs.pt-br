---
title: <span data-ttu-id="e8469-101">Como adicionar aplicativos da loja do iOS ao Intune</span><span class="sxs-lookup"><span data-stu-id="e8469-101">How to add iOS store apps to Intune</span></span>
titleSuffix: Intune on Azure
description: <span data-ttu-id="e8469-102">Saiba como adicionar aplicativos da loja do iOS ao Intune.</span><span class="sxs-lookup"><span data-stu-id="e8469-102">Learn about adding iOS store apps to Intune."</span></span>
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01f7d391939a5d79c5feb23960aec17e668013d0
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a><span data-ttu-id="e8469-103">Como adicionar aplicativos da iOS Store ao Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e8469-103">How to add iOS store apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="e8469-104">Use as informações neste tópico para ajudá-lo a adicionar aplicativos da iOS store ao Intune.</span><span class="sxs-lookup"><span data-stu-id="e8469-104">Use the information in this topic to help you add iOS store apps to Intune.</span></span>

>[!NOTE]
><span data-ttu-id="e8469-105">Embora os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e8469-105">While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps.</span></span> <span data-ttu-id="e8469-106">Se os usuários finais excluírem esses aplicativos, eles deverão ir para a loja de aplicativos e reinstalá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="e8469-106">If end users delete these apps, they must go to the app store, and manually re install them.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="e8469-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e8469-107">Before you start</span></span>

<span data-ttu-id="e8469-108">Você só poderá atribuir aplicativos usando este método se eles forem gratuitos na App Store.</span><span class="sxs-lookup"><span data-stu-id="e8469-108">You can only assign apps using this method if they are free of charge in the app store.</span></span> <span data-ttu-id="e8469-109">Se você quiser atribuir aplicativos pagos usando o Intune, considere o uso do [programa de compra por volume do iOS](vpp-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="e8469-109">If you want to assign paid apps using Intune, consider using the [iOS volume-purchase program](vpp-apps-ios.md).</span></span>


## <a name="step-1---search-for-the-app-in-the-store"></a><span data-ttu-id="e8469-110">Etapa 1 – Pesquise o aplicativo na loja</span><span class="sxs-lookup"><span data-stu-id="e8469-110">Step 1 - Search for the app in the store</span></span>

1. <span data-ttu-id="e8469-111">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="e8469-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="e8469-112">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="e8469-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="e8469-113">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="e8469-113">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="e8469-114">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > Aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e8469-114">In the **Mobile apps** workload, choose **Manage** > Apps.</span></span>
5. <span data-ttu-id="e8469-115">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e8469-115">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="e8469-116">Na folha **Adicionar Aplicativo**, escolha **Pesquisar na Loja de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="e8469-116">In the **Add App** blade, choose **Search the App Store**.</span></span>
7. <span data-ttu-id="e8469-117">Na folha **Apple App Store**, digite o nome (ou parte do nome) na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e8469-117">In the **Apple App Store** blade, enter the name (or part of the name) in the search box.</span></span> <span data-ttu-id="e8469-118">O Intune pesquisará na loja e retornará uma lista de resultados relevantes.</span><span class="sxs-lookup"><span data-stu-id="e8469-118">Intune will search the store and return a list of relevant results.</span></span>
8. <span data-ttu-id="e8469-119">Na lista, escolha o aplicativo que desejar e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8469-119">From the list, choose the app you want, then click **OK**.</span></span>

## <a name="step-2---configure-app-information"></a><span data-ttu-id="e8469-120">Etapa 2 – Configurar informações de aplicativo</span><span class="sxs-lookup"><span data-stu-id="e8469-120">Step 2 - Configure app information</span></span>

1. <span data-ttu-id="e8469-121">Na folha **Adicionar Aplicativo**, escolha **Informações do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="e8469-121">In the **Add App** blade, choose **App Information**.</span></span>
2. <span data-ttu-id="e8469-122">Na folha **Editar Aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="e8469-122">In the **Edit App** blade, configure the following information.</span></span> <span data-ttu-id="e8469-123">Ao terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e8469-123">Once you are done, click **Add**.</span></span> <span data-ttu-id="e8469-124">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="e8469-124">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
- <span data-ttu-id="e8469-125">**Nome do Aplicativo** – Insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="e8469-125">**App Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="e8469-126">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="e8469-126">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="e8469-127">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="e8469-127">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="e8469-128">**Descrição do Aplicativo** – Insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-128">**App Description** - Enter a description for the app.</span></span> <span data-ttu-id="e8469-129">Isso será exibido para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="e8469-129">This will be displayed to users in the company portal.</span></span>
- <span data-ttu-id="e8469-130">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-130">**Publisher** - Enter the name of the publisher of the app.</span></span>
- <span data-ttu-id="e8469-131">**URL da loja de aplicativos** – Insira a URL da loja de aplicativos do aplicativo que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="e8469-131">**App store URL** - Enter the app store URL of the app you want to create.</span></span>
- <span data-ttu-id="e8469-132">**Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado.</span><span class="sxs-lookup"><span data-stu-id="e8469-132">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="e8469-133">Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.</span><span class="sxs-lookup"><span data-stu-id="e8469-133">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
- <span data-ttu-id="e8469-134">**Categoria** (opcional).</span><span class="sxs-lookup"><span data-stu-id="e8469-134">**Category** (optional).</span></span> <span data-ttu-id="e8469-135">Selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="e8469-135">Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="e8469-136">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="e8469-136">This will make it easier for users to find the app when they browse the company portal.</span></span>
- <span data-ttu-id="e8469-137">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e8469-137">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
- <span data-ttu-id="e8469-138">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-138">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="e8469-139">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="e8469-139">The URL will be displayed to users in the company portal.</span></span>
- <span data-ttu-id="e8469-140">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-140">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="e8469-141">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="e8469-141">The URL will be displayed to users in the company portal.</span></span>
- <span data-ttu-id="e8469-142">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-142">**Developer** - Optionally, enter the name of the app developer.</span></span>
- <span data-ttu-id="e8469-143">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="e8469-143">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
- <span data-ttu-id="e8469-144">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-144">**Notes** - Enter any notes you would like to associate with this app.</span></span>
- <span data-ttu-id="e8469-145">**Carregar Ícone** – Carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e8469-145">**Upload Icon** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="e8469-146">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="e8469-146">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="e8469-147">Após terminar, escolha **Salvar** na folha **Adicionar Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="e8469-147">When you are done, on the **Add App** blade, choose **Save**.</span></span>

<span data-ttu-id="e8469-148">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="e8469-148">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="e8469-149">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="e8469-149">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
