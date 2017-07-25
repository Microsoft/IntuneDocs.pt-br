---
title: "Proteger aplicativos LOB em dispositivos não registrados"
description: "Este tópico descreve como preparar seus aplicativos de linha de negócios personalizados para que você possa aplicar políticas de gerenciamento de aplicativo móvel que podem ajudar a evitar a perda de dados."
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b09daa05db673817bea67cd8b88c2ac63be7f1e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="e3283-103">Proteger aplicativos de linha de negócios e dados em dispositivos não registrados no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e3283-103">Protect line-of-business apps and data on devices that are not enrolled in Microsoft Intune</span></span>
<a id="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e3283-104">Políticas de gerenciamento de aplicativos móveis (MAM) ajudam a proteger dados da empresa, restringindo ações que poderiam vazar dados da empresa e impor requisitos de acesso de dados, como o PIN do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e3283-104">Mobile application management (MAM) policies help protect company data by restricting actions that could leak company data and by enforcing data access requirements, such as an app PIN.</span></span> <span data-ttu-id="e3283-105">Para aplicar políticas de MAM nos aplicativos de linha de negócios iOS e Android, você deve primeiro encapsular o aplicativo com a Ferramenta de Encapsulamento de Aplicativo do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="e3283-105">To apply MAM policies to iOS and Android line-of-business apps, you must first wrap the app with the Microsoft Intune App Wrapping Tool.</span></span> <span data-ttu-id="e3283-106">O encapsulamento de aplicativo é o processo de aplicação de uma camada de gerenciamento a um aplicativo móvel sem a necessidade de nenhum chan/intune/apps-prepare-mobile-application-managementes a ele e distribuí-lo para os usuários.</span><span class="sxs-lookup"><span data-stu-id="e3283-106">App wrapping is the process of applying a management layer to a mobile app without requiring any chan/intune/apps-prepare-mobile-application-managementes to it and distribute it to your users.</span></span>  

<span data-ttu-id="e3283-107">Este tópico explica as etapas necessárias para aplicar políticas de MAM a aplicativos que os usuários acessam em **dispositivos de propriedade dos funcionários que não são gerenciados** e dispositivos gerenciados por uma **solução de MDM (gerenciamento de dispositivo móvel) de terceiros**.</span><span class="sxs-lookup"><span data-stu-id="e3283-107">This topic explains the steps that are required to apply MAM policies for apps that users access on **employee-owned devices that are not managed** and devices that are managed by a **third-party mobile device management (MDM) solution**.</span></span>  <span data-ttu-id="e3283-108">Para preparar os aplicativos de linha de negócios executados em **dispositivos registrados no Intune MDM**, consulte [Decidir como preparar os aplicativos para gerenciamento de aplicativos móveis com o Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span><span class="sxs-lookup"><span data-stu-id="e3283-108">To prepare your line-of-business apps that run on **devices that are enrolled in Intune MDM**, see [Decide how to prepare apps for mobile application management with Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span></span>


##  <span data-ttu-id="e3283-109">Etapa 1: preparar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="e3283-109">Step 1: Prepare the app</span></span>
<a id="step-1-prepare-the-app" class="xliff"></a>

<span data-ttu-id="e3283-110">Antes de aplicar as políticas de MAM a um aplicativo, você deve primeiro encapsular o aplicativo usando a Ferramenta de Disposição de Aplicativo do Microsoft Intune para [iOS](prepare-ios-apps-for-mo/intune/apps-prepare-mobile-application-managementoid](/intune/app-wrapper-prepare-android) ou usar o [SDK do Aplicativo do Intune](/intune/app-sdk) para integrar manualmente os recursos de Proteção de Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="e3283-110">Before you can apply MAM policies to an app, you must first wrap the app by using the Microsoft Intune App Wrapping Tool for [iOS](prepare-ios-apps-for-mo/intune/apps-prepare-mobile-application-managementoid](/intune/app-wrapper-prepare-android), or use the [Intune App SDK](/intune/app-sdk) to manually integrate Intune app protection features.</span></span>

<span data-ttu-id="e3283-111">Para saber mais sobre como usar a Ferramenta de Encapsulamento de Aplicativos em relação ao SDK, consulte [Decidir como preparar aplicativos para o gerenciamento de aplicativos móveis com o Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span><span class="sxs-lookup"><span data-stu-id="e3283-111">For more information on using the App Wrapping Tool vs. the SDK, see [Decide how to prepare apps for mobile application management with Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span></span>

## <span data-ttu-id="e3283-112">Etapa 2: adicionar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="e3283-112">Step 2: Add the app</span></span>
<a id="step-2-add-the-app" class="xliff"></a>

<span data-ttu-id="e3283-113">Para associar seu aplicativo de linha de negócios com as políticas de MAM, é necessário adicionar os detalhes do aplicativo à sua assinatura/locatário do Intune usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="e3283-113">To associate your line-of-business app with MAM policies, you must add the app details to your Intune subscription/tenant by using the following steps:</span></span>

1. <span data-ttu-id="e3283-114">No [portal do Azure](https://portal.azure.com/), vá para **Gerenciamento de aplicativos móveis do Intune** > **Configurações** e escolha **Aplicativos de linha de negócios**.</span><span class="sxs-lookup"><span data-stu-id="e3283-114">In the [Azure portal](https://portal.azure.com/), go to **Intune mobile application management** > **Settings**, and choose **Line-of-business apps**.</span></span>

  ![Captura de tela da folha de configurações com a opção linha de negócios](../media/mam-azure-portal-lob-on-settings.png)

2. <span data-ttu-id="e3283-116">Na folha **Aplicativos da linha de negócios**, escolha **Adicionar um aplicativo personalizado**.</span><span class="sxs-lookup"><span data-stu-id="e3283-116">On the **Line-of-business-apps** blade, choose **Add a custom app**.</span></span>

  ![Captura de tela da folha de aplicativos da linha de negócios com o botão Adicionar aplicativo personalizado na parte superior](../media/mam-azure-portal-add-lob-app-action.png)
3.  <span data-ttu-id="e3283-118">Nomeie o aplicativo, o identificador de pacote em um campo Identificador de aplicativo e a plataforma (iOS ou Android).</span><span class="sxs-lookup"><span data-stu-id="e3283-118">Provide a name for the app, the bundle identifier in the App Identifier field, and the platform (iOS or Android).</span></span>

  ![Captura de tela da folha Adicionar um aplicativo personalizado](../media/mam-azure-portal-add-app-details.png)

  <span data-ttu-id="e3283-120">Esta etapa ajuda a criar uma lista exclusiva de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e3283-120">This step helps create a unique listing of your app.</span></span> <span data-ttu-id="e3283-121">O aplicativo também será exibido na lista de aplicativos de destino de uma política de MAM do seu locatário, conforme descrito na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="e3283-121">The app will also be displayed in the list of Targeted apps for a MAM policy for your tenant, as described in the next step.</span></span>

## <span data-ttu-id="e3283-122">Etapa 3: aplicar políticas MAM</span><span class="sxs-lookup"><span data-stu-id="e3283-122">Step 3: Apply MAM policies</span></span>
<a id="step-3-apply-mam-policies" class="xliff"></a>
<span data-ttu-id="e3283-123">Depois dos metadados do aplicativo serem carregados para o serviço, o aplicativo aparecerá na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e3283-123">After the app metadata is uploaded to the service, the app shows up in the list of apps.</span></span> <span data-ttu-id="e3283-124">Agora, é possível [criar uma nova política ou usar uma política existente](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) e aplicá-la ao aplicativo de linha de negócios adicionado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="e3283-124">You can now [create a new policy or use an existing policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md), and apply it to the line-of-business app that you added in step 2.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e3283-125">Você deve direcionar a política MAM aos usuários que pretendem usar o aplicativo encapsulado.</span><span class="sxs-lookup"><span data-stu-id="e3283-125">You must target the MAM policy to the users who are going to use the wrapped app.</span></span>  <span data-ttu-id="e3283-126">Os usuários que não têm essa política implantada não poderão usar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e3283-126">Users who don’t have this policy deployed to them won't be able to use the app.</span></span>


  ![Captura de tela da folha Lista de destino de aplicativos com o novo aplicativo de linha de negócios exibido](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <span data-ttu-id="e3283-128">Etapa 4: distribuir o aplicativo</span><span class="sxs-lookup"><span data-stu-id="e3283-128">Step 4: Distribute the app</span></span>
<a id="step-4-distribute-the-app" class="xliff"></a>
<span data-ttu-id="e3283-129">É possível implantar aplicativos para seus usuários das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="e3283-129">You can deploy apps to your users in the following ways:</span></span>
* <span data-ttu-id="e3283-130">Para dispositivos registrados em uma solução de MDM de terceiros, você pode distribuir os aplicativos por meio de sua solução de MDM.</span><span class="sxs-lookup"><span data-stu-id="e3283-130">For devices that are enrolled in a third-party MDM solution, you can distribute the apps through your MDM solution.</span></span>
* <span data-ttu-id="e3283-131">Para dispositivos que não são gerenciados por qualquer solução de MDM, uma solução personalizada será necessária.</span><span class="sxs-lookup"><span data-stu-id="e3283-131">For devices that aren't managed by any MDM solution, you need a custom solution.</span></span> <span data-ttu-id="e3283-132">Os usuários devem baixar e instalar o aplicativo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e3283-132">Users must download and install the app on their device.</span></span>

## <span data-ttu-id="e3283-133">Alterar os metadados</span><span class="sxs-lookup"><span data-stu-id="e3283-133">Change the metadata</span></span>
<a id="change-the-metadata" class="xliff"></a>
<span data-ttu-id="e3283-134">Se você precisar alterar os detalhes do aplicativo, como o nome do aplicativo ou o identificador de pacote, será necessário [remover o aplicativo](#remove-apps) e [adicioná-lo](#step-2-add-the-app) com os novos metadados.</span><span class="sxs-lookup"><span data-stu-id="e3283-134">If you need to change the app details, like the name of the app or the bundle identifier, you must [remove the app](#remove-apps) and [add it](#step-2-add-the-app) with the new metadata.</span></span>

##  <span data-ttu-id="e3283-135">Remover aplicativos</span><span class="sxs-lookup"><span data-stu-id="e3283-135">Remove apps</span></span>
<a id="remove-apps" class="xliff"></a>
<span data-ttu-id="e3283-136">É possível remover um aplicativo de linha de negócios da lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e3283-136">You can remove a line-of-business app from the app list.</span></span> <span data-ttu-id="e3283-137">Isso removerá o aplicativo da lista e removerá a associação com políticas de MAM, mas não removerá ou desinstalará o aplicativo do dispositivo do usuário.</span><span class="sxs-lookup"><span data-stu-id="e3283-137">This will remove the app from the list and will remove the association with MAM policies, but will not remove or uninstall the app from the user’s device.</span></span>  

1.  <span data-ttu-id="e3283-138">No [portal do Azure](https://portal.azure.com/), vá para **Gerenciamento de aplicativos móveis do Intune** > **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="e3283-138">In the [Azure portal](https://portal.azure.com/), go to **Intune mobile app management** > **Settings**.</span></span> <span data-ttu-id="e3283-139">Na folha **Configurações**, escolha **Linha de negócios** para abrir a lista de aplicativos existentes.</span><span class="sxs-lookup"><span data-stu-id="e3283-139">On the **Settings** blade, choose **Line-of-business** to open the list of existing apps.</span></span>  
2.  <span data-ttu-id="e3283-140">Escolha o aplicativo que você deseja remover e escolha o menu **(…) contexto**.</span><span class="sxs-lookup"><span data-stu-id="e3283-140">Choose the app that you want to remove, and choose the **(…) context** menu.</span></span>

  ![Captura de tela da folha de aplicativos da linha de negócios com reticências](../media/mam-azure-portal-lob-context-menu.png)
3.  <span data-ttu-id="e3283-142">Escolha **Excluir Aplicativo** para excluir o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e3283-142">Choose **Delete Application** to delete the app.</span></span>

  ![Captura de tela da folha linha de negócios com a opção de exclusão do aplicativo](../media/mam-azure-portal-delete-app.png)

  <span data-ttu-id="e3283-144">Isso removerá os aplicativos da lista de aplicativos da linha de negócios e da lista de destino de aplicativos na política de MAM.</span><span class="sxs-lookup"><span data-stu-id="e3283-144">This will remove apps from the list of line-of-business apps and the Targeted list of apps in the MAM policy.</span></span>
