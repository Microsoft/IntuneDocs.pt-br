---
title: "<span data-ttu-id=\"cc8d9-101\">Como adicionar aplicativos de linha de negócios do iOS ao Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"cc8d9-101\">How to add iOS line-of-business apps to Intune</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"cc8d9-102\">Saiba como adicionar aplicativos de linha de negócios do iOS ao Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"cc8d9-102\">Learn about adding iOS line-of-business apps to Intune.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fb0e151c8b9a948dfd6bb330e1375ddeff2d8e16
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="cc8d9-103">Como adicionar aplicativos de linha de negócios (LOB) do iOS para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cc8d9-103">How to add iOS line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="cc8d9-104">Use as informações neste tópico para ajudá-lo a adicionar aplicativos da linha de negócios do iOS ao Intune.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-104">Use the information in this topic to help you add iOS line-of-business apps to Intune.</span></span>

>[!NOTE]
><span data-ttu-id="cc8d9-105">Embora os usuários de dispositivos iOS possam remover alguns dos aplicativos iOS internos, por exemplo, Ações e Mapas, você não pode usar o Intune para reimplantar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-105">While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps.</span></span> <span data-ttu-id="cc8d9-106">Se os usuários finais excluírem esses aplicativos, eles deverão ir para a loja de aplicativos e reinstalá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-106">If end users delete these apps, they must go to the app store, and manually re install them.</span></span>

## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="cc8d9-107">Etapa 1 – Especificar os arquivos de instalação de software</span><span class="sxs-lookup"><span data-stu-id="cc8d9-107">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="cc8d9-108">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="cc8d9-109">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="cc8d9-110">Na folha **Intune**, escolha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-110">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="cc8d9-111">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-111">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="cc8d9-112">Acima da lista de aplicativos, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-112">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="cc8d9-113">Na folha **Adicionar Aplicativo**, escolha **Aplicativo de linha de negócios**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-113">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="cc8d9-114">Etapa 2 - configurar o arquivo de pacote de aplicativos</span><span class="sxs-lookup"><span data-stu-id="cc8d9-114">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="cc8d9-115">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-115">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="cc8d9-116">Na folha do arquivo **Pacote de aplicativos**, escolha o botão Procurar e selecione um arquivo de instalação do iOS com a extensão **.ipa**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-116">On the **App package** file blade, choose the browse button, and select an iOS installation file with the extension **.ipa**.</span></span>
3. <span data-ttu-id="cc8d9-117">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-117">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="cc8d9-118">Etapa 3 - configurar informações do aplicativo</span><span class="sxs-lookup"><span data-stu-id="cc8d9-118">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="cc8d9-119">Na folha **Adicionar Aplicativo**, escolha o arquivo **Adicionar pacote**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-119">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="cc8d9-120">Na folha **informações do aplicativo**, configure as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-120">On the **App information** blade, configure the following information.</span></span> <span data-ttu-id="cc8d9-121">Dependendo do aplicativo escolhido, alguns dos valores nessa folha podem ter sido preenchidos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="cc8d9-121">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="cc8d9-122">**Nome**: insira o nome do aplicativo como ele será exibido no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-122">**Name** - Enter the name of the app as it will be displayed in the company portal.</span></span> <span data-ttu-id="cc8d9-123">Certifique-se de que todos os nomes de aplicativo usados são exclusivos.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-123">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="cc8d9-124">Se o mesmo nome de aplicativo for usado duas vezes, apenas um dos aplicativos será exibido para usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-124">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="cc8d9-125">**Descrição**: insira uma descrição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-125">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="cc8d9-126">Isso será exibido para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-126">This will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="cc8d9-127">**Editor**: insira o nome do editor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-127">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="cc8d9-128">**Sistema Operacional Mínimo** – Na lista, escolha a versão mínima do sistema operacional no qual o aplicativo pode ser instalado.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-128">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="cc8d9-129">Se você atribuir o aplicativo a um dispositivo com um sistema operacional mais antigo, ele não será instalado.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-129">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
    - <span data-ttu-id="cc8d9-130">**Categoria** - selecione uma ou mais das categorias de aplicativo interno, ou uma categoria criada por você.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-130">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="cc8d9-131">Isso facilitará a localização do aplicativo quando os usuários navegarem pelo portal da empresa.
</span><span class="sxs-lookup"><span data-stu-id="cc8d9-131">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="cc8d9-132">**Exibir isso como um aplicativo em destaque no portal da empresa** – Exiba o aplicativo de forma proeminente na página principal do portal da empresa quando os usuários procurarem aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-132">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="cc8d9-133">**URL de Informações** – Opcionalmente, insira a URL de um site que contém informações sobre esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-133">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="cc8d9-134">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-134">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="cc8d9-135">**URL de Privacidade** – Opcionalmente, insira a URL para um site que contém informações de privacidade desse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-135">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="cc8d9-136">A URL será exibida para os usuários no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-136">The URL will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="cc8d9-137">**Desenvolvedor** – Opcionalmente, insira o nome do desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-137">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="cc8d9-138">**Proprietário** – Opcionalmente, insira um nome para o proprietário desse aplicativo, por exemplo, **Departamento de RH**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-138">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="cc8d9-139">**Observações** – Digite as observações que você deseja associar a este aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-139">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="cc8d9-140">**Logotipo** - carregue um ícone que será associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-140">**Logo** - Upload an icon that will be associated with the app.</span></span> <span data-ttu-id="cc8d9-141">Esse é o ícone que será exibido com o aplicativo quando os usuários navegarem pelo portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-141">This is the icon that will be displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="cc8d9-142">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-142">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="cc8d9-143">Etapa 4 - conclusão</span><span class="sxs-lookup"><span data-stu-id="cc8d9-143">Step 4 - Finish up</span></span>

1. <span data-ttu-id="cc8d9-144">Na folha **Adicionar aplicativo**, verifique se as informações configuradas estão corretas.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-144">On the **Add app** blade, verify the information you configured is correct.</span></span>
2. <span data-ttu-id="cc8d9-145">Escolha **Adicionar** para carregar o aplicativo no Intune.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-145">Choose **Add**, to upload the app to Intune.</span></span>

<span data-ttu-id="cc8d9-146">O aplicativo que criado será exibido na lista de aplicativos, na qual você poderá atribuí-lo para os grupos que escolher.</span><span class="sxs-lookup"><span data-stu-id="cc8d9-146">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="cc8d9-147">Para obter ajuda, consulte [Como atribuir aplicativos aos grupos](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="cc8d9-147">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>
