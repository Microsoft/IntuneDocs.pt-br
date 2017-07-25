---
title: "Como definir configurações personalizadas do dispositivo do Intune"
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para definir configurações personalizadas nos dispositivos gerenciados."
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
ms.openlocfilehash: 769c566c7ebb91743fc0f18ebf8f3e76377ca847
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="49152-103">Como definir configurações personalizadas do dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="49152-103">How to configure custom device settings in Microsoft Intune</span></span>
<a id="how-to-configure-custom-device-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <span data-ttu-id="49152-104">Quando usar configurações personalizadas</span><span class="sxs-lookup"><span data-stu-id="49152-104">When to use custom settings</span></span>
<a id="when-to-use-custom-settings" class="xliff"></a>

<span data-ttu-id="49152-105">Configurações personalizadas do dispositivo podem ser úteis quando o Intune não tem as configurações que você deseja para configurar internamente e disponíveis de outros perfis de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49152-105">Custom device settings can be useful when Intune doesn't have the settings you want to configure built-in, and available from other device profiles.</span></span>
<span data-ttu-id="49152-106">As configurações personalizadas são definidas forma diferente para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="49152-106">Custom settings are configured differently for each platform.</span></span> <span data-ttu-id="49152-107">Por exemplo, com dispositivos com Android e Windows, você pode especificar que valores OMA-URI (Open Mobile Alliance Uniform Resource Identifier) controlam os recursos dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="49152-107">For example, with Android and Windows devices, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to control features on devices.</span></span> <span data-ttu-id="49152-108">Para dispositivos da Apple, você pode importar um arquivo criado com o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).</span><span class="sxs-lookup"><span data-stu-id="49152-108">For Apple devices, you can import a file you created with the [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).</span></span>

<span data-ttu-id="49152-109">Use as informações neste tópico para aprender as noções básicas sobre a definição de perfis com configuração personalizada e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="49152-109">Use the information in this topic to learn the basics about configuring profiles with custom settings, and then read further topics for each platform to learn about device specifics.</span></span>

## <span data-ttu-id="49152-110">Criar um perfil de dispositivo que contém configurações personalizadas</span><span class="sxs-lookup"><span data-stu-id="49152-110">Create a device profile containing custom settings</span></span>
<a id="create-a-device-profile-containing-custom-settings" class="xliff"></a>

1. <span data-ttu-id="49152-111">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="49152-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="49152-112">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="49152-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="49152-113">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="49152-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="49152-114">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="49152-114">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="49152-115">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="49152-115">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="49152-116">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil personalizado.</span><span class="sxs-lookup"><span data-stu-id="49152-116">On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.</span></span>
5. <span data-ttu-id="49152-117">Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="49152-117">From the **Platform** drop-down list, select the device platform to which you want to apply custom settings.</span></span> <span data-ttu-id="49152-118">No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo personalizado:</span><span class="sxs-lookup"><span data-stu-id="49152-118">Currently, you can choose one of the following platforms for custom device settings:</span></span>
    - <span data-ttu-id="49152-119">**Android**</span><span class="sxs-lookup"><span data-stu-id="49152-119">**Android**</span></span>
    - <span data-ttu-id="49152-120">**iOS**</span><span class="sxs-lookup"><span data-stu-id="49152-120">**iOS**</span></span>
    - <span data-ttu-id="49152-121">**macOS**</span><span class="sxs-lookup"><span data-stu-id="49152-121">**macOS**</span></span>
    - <span data-ttu-id="49152-122">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="49152-122">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="49152-123">**Windows 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="49152-123">**Windows 10 and later**</span></span>
6. <span data-ttu-id="49152-124">Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="49152-124">From the **Profile** type drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="49152-125">Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="49152-125">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="49152-126">Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="49152-126">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="49152-127">Configurações do Android</span><span class="sxs-lookup"><span data-stu-id="49152-127">Android settings</span></span>](custom-settings-android.md)
    - [<span data-ttu-id="49152-128">Configurações do iOS</span><span class="sxs-lookup"><span data-stu-id="49152-128">iOS settings</span></span>](custom-settings-ios.md)
    - [<span data-ttu-id="49152-129">Configurações do macOS</span><span class="sxs-lookup"><span data-stu-id="49152-129">macOS settings</span></span>](custom-settings-macos.md)
    - [<span data-ttu-id="49152-130">Configurações do Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="49152-130">Windows Phone 8.1 settings</span></span>](custom-settings-windows-phone-8-1.md)
    - [<span data-ttu-id="49152-131">Configurações do Windows 10</span><span class="sxs-lookup"><span data-stu-id="49152-131">Windows 10 settings</span></span>](custom-settings-windows-10.md)
    - [<span data-ttu-id="49152-132">Configurações do Android for Work</span><span class="sxs-lookup"><span data-stu-id="49152-132">Android for Work settings</span></span>](custom-settings-android-for-work.md)
8. <span data-ttu-id="49152-133">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="49152-133">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="49152-134">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="49152-134">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="49152-135">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="49152-135">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
