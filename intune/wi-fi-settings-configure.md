---
title: "Como definir configurações de Wi-Fi do Intune"
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para configurar as conexões Wi-Fi nos dispositivos gerenciados."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0e191fe443757a5ea43ccc2b4ef2e9cb331b2142
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="a8488-103">Como definir configurações de Wi-Fi no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a8488-103">How to configure Wi-Fi settings in Microsoft Intune</span></span>
<a id="how-to-configure-wi-fi-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a8488-104">Use os perfis de Wi-Fi do Microsoft Intune para atribuir configurações de rede sem fio para usuários e dispositivos na organização.</span><span class="sxs-lookup"><span data-stu-id="a8488-104">Use Microsoft Intune Wi-Fi profiles to assign wireless network settings to users and devices in your organization.</span></span> <span data-ttu-id="a8488-105">Quando você atribui um perfil de Wi-Fi, os usuários terão acesso à rede Wi-Fi corporativa sem precisar configurá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="a8488-105">When you assign a Wi-Fi profile, your users will have access to your corporate Wi-Fi network without having to configure it themselves.</span></span>

<span data-ttu-id="a8488-106">Por exemplo, você pode instalar uma nova rede Wi-Fi chamada Contoso Wi-Fi e configurar todos os dispositivos iOS para se conectarem a essa rede.</span><span class="sxs-lookup"><span data-stu-id="a8488-106">For example, you install a new Wi-Fi network named Contoso Wi-Fi and want to set up all iOS devices to connect to this network.</span></span> <span data-ttu-id="a8488-107">Este é o processo:</span><span class="sxs-lookup"><span data-stu-id="a8488-107">Here's the process:</span></span>

1. <span data-ttu-id="a8488-108">Crie um perfil de Wi-Fi contendo as configurações necessárias para conectar à rede sem fio Contoso Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8488-108">Create a Wi-Fi profile containing the settings necessary to connect to the Contoso Wi-Fi wireless network.</span></span>
2. <span data-ttu-id="a8488-109">Atribua o perfil a um grupo que contém todos os usuários de dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="a8488-109">Assign the profile to a group containing all users of iOS devices.</span></span>
3. <span data-ttu-id="a8488-110">Os usuários encontram a nova rede Contoso Wi-Fi na lista de redes sem fio em seus dispositivos e podem facilmente se conectar a ela.</span><span class="sxs-lookup"><span data-stu-id="a8488-110">Users find the new Contoso Wi-Fi network in the list of wireless networks on their device and can easily connect to it.</span></span>

<span data-ttu-id="a8488-111">Perfis de Wi-Fi dão suporte às seguintes plataformas de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="a8488-111">Wi-Fi profiles support the following device platforms:</span></span>

- <span data-ttu-id="a8488-112">Android 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="a8488-112">Android 4 and later</span></span>
- <span data-ttu-id="a8488-113">Android for Work</span><span class="sxs-lookup"><span data-stu-id="a8488-113">Android for Work</span></span>
- <span data-ttu-id="a8488-114">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="a8488-114">iOS 8.0 and later</span></span>
- <span data-ttu-id="a8488-115">macOS (Mac OS X 10.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="a8488-115">macOS (Mac OS X 10.9 and later)</span></span>

<span data-ttu-id="a8488-116">Para dispositivos que executam o Windows 8.1, Windows 10 e Windows Mobile 10, você pode importar uma configuração de Wi-Fi previamente exportada de outro dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a8488-116">For devices running Windows 8.1, Windows 10, and Windows 10 Mobile, you can import a Wi-Fi configuration that was previously exported from another device.</span></span>

<span data-ttu-id="a8488-117">Use as informações neste tópico para aprender as noções básicas sobre a configuração de um perfil de Wi-Fi e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a8488-117">Use the information in this topic to learn the basics about configuring a Wi-Fi profile, and then read further topics for each platform to learn about device specifics.</span></span>

## <span data-ttu-id="a8488-118">Criar um perfil de dispositivo que contém configurações de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="a8488-118">Create a device profile containing Wi-Fi settings</span></span>
<a id="create-a-device-profile-containing-wi-fi-settings" class="xliff"></a>

1. <span data-ttu-id="a8488-119">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="a8488-119">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a8488-120">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a8488-120">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="a8488-121">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="a8488-121">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="a8488-122">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="a8488-122">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="a8488-123">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="a8488-123">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="a8488-124">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8488-124">On the **Create Profile** blade, enter a **Name** and **Description** for the Wi-Fi profile.</span></span>
5. <span data-ttu-id="a8488-125">Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="a8488-125">From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings.</span></span> <span data-ttu-id="a8488-126">No momento, é possível escolher uma das seguintes plataformas para as configurações de Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="a8488-126">Currently, you can choose one of the following platforms for Wi-Fi settings:</span></span>
    - <span data-ttu-id="a8488-127">**Android**</span><span class="sxs-lookup"><span data-stu-id="a8488-127">**Android**</span></span>
    - <span data-ttu-id="a8488-128">**Android for Work**</span><span class="sxs-lookup"><span data-stu-id="a8488-128">**Android for Work**</span></span>
    - <span data-ttu-id="a8488-129">**iOS**</span><span class="sxs-lookup"><span data-stu-id="a8488-129">**iOS**</span></span>
    - <span data-ttu-id="a8488-130">**macOS**</span><span class="sxs-lookup"><span data-stu-id="a8488-130">**macOS**</span></span>
    - <span data-ttu-id="a8488-131">**Windows 8.1 e posterior (importar um perfil)**</span><span class="sxs-lookup"><span data-stu-id="a8488-131">**Windows 8.1 and later (import a profile)**</span></span>
6. <span data-ttu-id="a8488-132">Na lista suspensa de tipos de **Perfil**, escolha **Wi-Fi básico** ou **Wi-Fi empresarial**.</span><span class="sxs-lookup"><span data-stu-id="a8488-132">From the **Profile** type drop-down list, choose **Wi-Fi basic** or **Wi-Fi enterprise**.</span></span>
    >[!TIP]
    ><span data-ttu-id="a8488-133">Use **Wi-Fi básico** para fornecer recursos básicos como nome de rede e SSID.</span><span class="sxs-lookup"><span data-stu-id="a8488-133">Use **Wi-fi basic** to supply basic features like the network name, and the SSID.</span></span> <span data-ttu-id="a8488-134">**Wi-Fi corporativa** permite que você forneça informações mais avançadas, como o protocolo EAP (Extensible Authentication Protocol) se sua rede Wi-Fi o utilizar.</span><span class="sxs-lookup"><span data-stu-id="a8488-134">**Wi-Fi enterprise** lets you supply more advanced information like the  Extensible Authentication Protocol (EAP) if your Wi-Fi network uses this.</span></span> <span data-ttu-id="a8488-135">**Importação de Wi-Fi** (para Windows 8.1 e Windows 10) permite que você importe as configurações de Wi-Fi como um arquivo XML previamente exportado de um dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="a8488-135">**Wi-Fi import** (for Windows 8.1 and Windows 10) lets you import Wi-Fi settings as an XML file that you previusly exported from a different device.</span></span>
7. <span data-ttu-id="a8488-136">Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="a8488-136">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="a8488-137">Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="a8488-137">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="a8488-138">Configurações do Android e do Android for Work</span><span class="sxs-lookup"><span data-stu-id="a8488-138">Android and Android for Work settings</span></span>](wi-fi-settings-android.md)
    - [<span data-ttu-id="a8488-139">Configurações do iOS</span><span class="sxs-lookup"><span data-stu-id="a8488-139">iOS settings</span></span>](wi-fi-settings-ios.md)
    - [<span data-ttu-id="a8488-140">Configurações do macOS</span><span class="sxs-lookup"><span data-stu-id="a8488-140">macOS settings</span></span>](wi-fi-settings-macos.md)
    - [<span data-ttu-id="a8488-141">Configurações do Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="a8488-141">Windows Phone 8.1 settings</span></span>](wi-fi-settings-import-windows-8-1.md)
8. <span data-ttu-id="a8488-142">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a8488-142">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="a8488-143">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="a8488-143">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="a8488-144">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="a8488-144">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
