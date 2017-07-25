---
title: "Definir as configurações de recurso de dispositivo do Intune"
titleSuffix: Intune on Azure
description: Saiba como usar o Intune para configurar recursos nos dispositivos gerenciados.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f286119019bb26d8851c766a9d88ad818d7e600b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b7365-103">Como definir as configurações de recurso de dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b7365-103">How to configure device feature settings in Microsoft Intune</span></span>
<a id="how-to-configure-device-feature-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b7365-104">As restrições de dispositivo permitem que você controle os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7365-104">Device restrictions let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.</span></span>

<span data-ttu-id="b7365-105">Use as informações neste tópico para aprender as noções básicas sobre a configuração de perfis de recurso de dispositivo e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7365-105">Use the information in this topic to learn the basics about configuring device feature profiles, and then read further topics for each platform to learn about device specifics.</span></span>

## <span data-ttu-id="b7365-106">Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b7365-106">Create a device profile containing device restriction settings</span></span>
<a id="create-a-device-profile-containing-device-restriction-settings" class="xliff"></a>

1. <span data-ttu-id="b7365-107">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7365-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b7365-108">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b7365-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b7365-109">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b7365-109">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="b7365-110">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="b7365-110">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="b7365-111">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="b7365-111">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="b7365-112">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de recursos do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b7365-112">On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.</span></span>
5. <span data-ttu-id="b7365-113">Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações.</span><span class="sxs-lookup"><span data-stu-id="b7365-113">From the **Platform** drop-down list, select the device platform to which you want to apply the settings.</span></span> <span data-ttu-id="b7365-114">No momento, é possível escolher uma das seguintes plataformas para os recursos do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b7365-114">Currently, you can choose one of the following platforms for device features:</span></span>
    - <span data-ttu-id="b7365-115">**iOS**</span><span class="sxs-lookup"><span data-stu-id="b7365-115">**iOS**</span></span>
    - <span data-ttu-id="b7365-116">**macOS**</span><span class="sxs-lookup"><span data-stu-id="b7365-116">**macOS**</span></span>
6. <span data-ttu-id="b7365-117">Na lista suspensa do **Tipo de perfil**, escolha **Recursos do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b7365-117">From the **Profile type** type drop-down list, choose **Device features**.</span></span> 
7. <span data-ttu-id="b7365-118">Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="b7365-118">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="b7365-119">Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="b7365-119">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="b7365-120">Configurações do AirPrint para iOS e MacOS</span><span class="sxs-lookup"><span data-stu-id="b7365-120">AirPrint settings for iOS and MacOS</span></span>](air-print-settings-ios-macos.md)
    - [<span data-ttu-id="b7365-121">Configurações do AirPlay para iOS</span><span class="sxs-lookup"><span data-stu-id="b7365-121">AirPlay settings for iOS</span></span>](airplay-settings-ios.md)
    - [<span data-ttu-id="b7365-122">Configurações do layout da Tela inicial para iOS</span><span class="sxs-lookup"><span data-stu-id="b7365-122">Home screen layout settings for iOS</span></span>](home-screen-settings-ios.md)
    - [<span data-ttu-id="b7365-123">Configurações de notificação de aplicativos para iOS</span><span class="sxs-lookup"><span data-stu-id="b7365-123">App notification settings for iOS</span></span>](app-notification-settings-ios.md)
    - [<span data-ttu-id="b7365-124">Definições de configuração de dispositivo compartilhado para iOS</span><span class="sxs-lookup"><span data-stu-id="b7365-124">Shared device configuration settings for iOS</span></span>](shared-device-settings-ios.md)
    - [<span data-ttu-id="b7365-125">Configurações de filtro de conteúdo da Web para iOS</span><span class="sxs-lookup"><span data-stu-id="b7365-125">Web content filter settings for iOS</span></span>](web-content-filter-settings-ios.md)

8. <span data-ttu-id="b7365-126">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b7365-126">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="b7365-127">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="b7365-127">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="b7365-128">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="b7365-128">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>



