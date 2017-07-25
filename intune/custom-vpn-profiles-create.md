---
title: Como criar perfis VPN personalizados com o Microsoft Intune
titleSuffix: Intune on Azure
description: "Use configurações personalizadas para criar perfis de VPN no Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 11da0d31a9a00364a6105006c3e75b6bb6f2cb77
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f8bcd-103">Como criar perfis de VPN personalizados no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f8bcd-103">How to create custom VPN profiles in Microsoft Intune</span></span>
<a id="how-to-create-custom-vpn-profiles-in-microsoft-intune" class="xliff"></a>

## <span data-ttu-id="f8bcd-104">Criar uma configuração personalizada</span><span class="sxs-lookup"><span data-stu-id="f8bcd-104">Create a custom configuration</span></span>
<a id="create-a-custom-configuration" class="xliff"></a>
<span data-ttu-id="f8bcd-105">É possível usar políticas de configuração personalizada do Intune para criar perfis VPN para:</span><span class="sxs-lookup"><span data-stu-id="f8bcd-105">You can use Intune custom configuration polices to create VPN profiles for:</span></span>

* <span data-ttu-id="f8bcd-106">Dispositivos que executam o Android 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="f8bcd-106">Devices that run Android 4 and later</span></span>
* <span data-ttu-id="f8bcd-107">Dispositivos registrados que executam o Windows 8.1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="f8bcd-107">Enrolled devices that run Windows 8.1 and later</span></span>
* <span data-ttu-id="f8bcd-108">Dispositivos que executam o Windows Phone 8.1 e versões posteriores</span><span class="sxs-lookup"><span data-stu-id="f8bcd-108">Devices that run Windows Phone 8.1 and later</span></span>
* <span data-ttu-id="f8bcd-109">Dispositivos registrados que executam o Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="f8bcd-109">Enrolled devices that run Windows 10 desktop</span></span> 
* <span data-ttu-id="f8bcd-110">Dispositivos que executam o Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="f8bcd-110">Devices that run Windows 10 Mobile</span></span>

<span data-ttu-id="f8bcd-111">Esse tipo de política pode ser útil quando as políticas de VPN padrão do Intune não contêm as configurações que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-111">This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.</span></span>

## <span data-ttu-id="f8bcd-112">Para criar uma política de configuração personalizada:</span><span class="sxs-lookup"><span data-stu-id="f8bcd-112">To create a custom configuration policy:</span></span>
<a id="to-create-a-custom-configuration-policy" class="xliff"></a>

1. <span data-ttu-id="f8bcd-113">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-113">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="f8bcd-114">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-114">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="f8bcd-115">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-115">On the **Intune** blade, choose **Device configuration**.</span></span>
4. <span data-ttu-id="f8bcd-116">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-116">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
5. <span data-ttu-id="f8bcd-117">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-117">On the profiles blade, choose **Create Profile**.</span></span>
6. <span data-ttu-id="f8bcd-118">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-118">On the **Create Profile** blade, enter a **Name** and **Description** for the VPN profile.</span></span>
7. <span data-ttu-id="f8bcd-119">Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-119">From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings.</span></span> <span data-ttu-id="f8bcd-120">No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo personalizado:</span><span class="sxs-lookup"><span data-stu-id="f8bcd-120">Currently, you can choose one of the following platforms for custom device settings:</span></span>
    - <span data-ttu-id="f8bcd-121">**Android**</span><span class="sxs-lookup"><span data-stu-id="f8bcd-121">**Android**</span></span>
    - <span data-ttu-id="f8bcd-122">**iOS** (configurado usando um arquivo exportado do Apple Configurator).</span><span class="sxs-lookup"><span data-stu-id="f8bcd-122">**iOS** (configured using a file you exported from Apple Configurator).</span></span>
    - <span data-ttu-id="f8bcd-123">**macOS** (configurado usando um arquivo exportado do Apple Configurator).</span><span class="sxs-lookup"><span data-stu-id="f8bcd-123">**macOS** (configured using a file you exported from Apple Configurator).</span></span>
    - <span data-ttu-id="f8bcd-124">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="f8bcd-124">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="f8bcd-125">**Windows 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="f8bcd-125">**Windows 10 and later**</span></span>
6. <span data-ttu-id="f8bcd-126">Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-126">From the **Profile** type drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="f8bcd-127">Na folha **Configurações personalizadas de OMA-URI**, para cada configuração de URI que você deseja especificar, escolha **Adicionar**, forneça as informações solicitadas e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-127">On the **Custom OMA-URI Settings** blade, for each URI setting you want to specify, choose **Add**, provide the requested information, then choose **OK**.</span></span> <span data-ttu-id="f8bcd-128">Aqui está um exemplo:</span><span class="sxs-lookup"><span data-stu-id="f8bcd-128">Here's an example:</span></span>

   ![Caixa de diálogo de configuração personalizada de perfil de VPN](./media/Intune_Add_VPN_URI.png)

4.  <span data-ttu-id="f8bcd-130">Depois de inserir todas as configurações de URI necessárias, escolha **OK** e, em seguida, na folha **Criar Perfil**, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-130">After you've entered all of URI settings you need, choose **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="f8bcd-131">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="f8bcd-131">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="f8bcd-132">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="f8bcd-132">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>




