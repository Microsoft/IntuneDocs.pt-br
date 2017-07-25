---
title: "Definir configurações de restrição de dispositivo do Intune"
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para definir configurações e recursos nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8652b2b6db340f3b0cddcf538fa418c8774b1d6c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="9316b-103">Como definir as configurações de restrição de dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9316b-103">How to configure device restriction settings in Microsoft Intune</span></span>
<a id="how-to-configure-device-restriction-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="9316b-104">Restrições de dispositivo permitem controlar uma grande variedade de configurações e recursos que você gerencia em uma gama de categorias, incluindo configurações de segurança, navegador, hardware e compartilhamento de dados.</span><span class="sxs-lookup"><span data-stu-id="9316b-104">Device restrictions let you control a wide range of settings and features you manage across a range of categories including security, browser, hardware, and data sharing settings.</span></span> <span data-ttu-id="9316b-105">Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9316b-105">For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.</span></span>

<span data-ttu-id="9316b-106">Use as informações neste tópico para aprender as noções básicas sobre a configuração de perfis de restrição de dispositivo e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9316b-106">Use the information in this topic to learn the basics about configuring device restriction profiles, and then read further topics for each platform to learn about device specifics.</span></span>

## <span data-ttu-id="9316b-107">Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9316b-107">Create a device profile containing device restriction settings</span></span>
<a id="create-a-device-profile-containing-device-restriction-settings" class="xliff"></a>

1. <span data-ttu-id="9316b-108">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="9316b-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="9316b-109">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9316b-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="9316b-110">Na folha **Intune**, escolha **Configurar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9316b-110">On the **Intune** blade, choose **Configure devices**.</span></span>
2. <span data-ttu-id="9316b-111">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="9316b-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="9316b-112">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="9316b-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="9316b-113">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9316b-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="9316b-114">Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9316b-114">From the **Platform** drop-down list, select the device platform to which you want to apply custom settings.</span></span> <span data-ttu-id="9316b-115">No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="9316b-115">Currently, you can choose one of the following platforms for device restriction settings:</span></span>
    - <span data-ttu-id="9316b-116">**Android**</span><span class="sxs-lookup"><span data-stu-id="9316b-116">**Android**</span></span>
    - <span data-ttu-id="9316b-117">**iOS**</span><span class="sxs-lookup"><span data-stu-id="9316b-117">**iOS**</span></span>
    - <span data-ttu-id="9316b-118">**macOS**</span><span class="sxs-lookup"><span data-stu-id="9316b-118">**macOS**</span></span>
    - <span data-ttu-id="9316b-119">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="9316b-119">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="9316b-120">**Windows 8.1 e posterior**</span><span class="sxs-lookup"><span data-stu-id="9316b-120">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="9316b-121">**Windows 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="9316b-121">**Windows 10 and later**</span></span>
6. <span data-ttu-id="9316b-122">Na lista suspensa de **Tipo de perfil**, escolha **Restrições de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9316b-122">From the **Profile type** type drop-down list, choose **Device restrictions**.</span></span> <span data-ttu-id="9316b-123">Se você quiser criar um perfil de restrições de dispositivo para dispositivos Windows 10 Team como um Surface Hub, escolha **Restrições de dispositivos (Windows 10 Team)**.</span><span class="sxs-lookup"><span data-stu-id="9316b-123">If you want to create a device restrictions profile for Windows 10 Team devices like a Surface Hub, choose **Device restrictions (Windows 10 Team)**.</span></span>
7. <span data-ttu-id="9316b-124">Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="9316b-124">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="9316b-125">Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="9316b-125">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="9316b-126">Configurações do Android</span><span class="sxs-lookup"><span data-stu-id="9316b-126">Android settings</span></span>](device-restrictions-android.md)
    - [<span data-ttu-id="9316b-127">Configurações do iOS</span><span class="sxs-lookup"><span data-stu-id="9316b-127">iOS settings</span></span>](device-restrictions-ios.md)
    - [<span data-ttu-id="9316b-128">Configurações do macOS</span><span class="sxs-lookup"><span data-stu-id="9316b-128">macOS settings</span></span>](device-restrictions-macos.md)
    - [<span data-ttu-id="9316b-129">Configurações do Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="9316b-129">Windows Phone 8.1 settings</span></span>](device-restrictions-windows-phone-8-1.md)
    - [<span data-ttu-id="9316b-130">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9316b-130">Windows 8.1</span></span>](device-restrictions-windows-8-1.md)
    - [<span data-ttu-id="9316b-131">Configurações do Windows 10</span><span class="sxs-lookup"><span data-stu-id="9316b-131">Windows 10 settings</span></span>](device-restrictions-windows-10.md)
    - [<span data-ttu-id="9316b-132">Configurações do Windows 10 Team</span><span class="sxs-lookup"><span data-stu-id="9316b-132">Windows 10 Team settings</span></span>](device-restrictions-windows-10-teams.md)
    - [<span data-ttu-id="9316b-133">Configurações do Android for Work</span><span class="sxs-lookup"><span data-stu-id="9316b-133">Android for Work settings</span></span>](device-restrictions-android-for-work.md)
8. <span data-ttu-id="9316b-134">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="9316b-134">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="9316b-135">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="9316b-135">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="9316b-136">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="9316b-136">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

## <span data-ttu-id="9316b-137">Exemplo de configurações de restrição de dispositivo</span><span class="sxs-lookup"><span data-stu-id="9316b-137">Example of device restriction settings</span></span>
<a id="example-of-device-restriction-settings" class="xliff"></a>

<span data-ttu-id="9316b-138">Neste exemplo de alto nível, você criará uma política de restrição de dispositivo que bloqueia o uso do aplicativo de câmera interna em dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="9316b-138">In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.</span></span>

![Como desabilitar a câmera em dispositivos Android](./media/disable-android-camera.png)

