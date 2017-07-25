---
title: "Configurações da política de atualização de edição do Windows"
description: "Saiba como atualizar automaticamente os dispositivos com Windows 10 para uma versão diferente com o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1505adb219c38d9a67f4fa276ca345f05a0df42a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="a5038-103">Configurações da política de atualização de edição do Windows no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a5038-103">Windows edition upgrade policy settings in Microsoft Intune</span></span>
<a id="windows-edition-upgrade-policy-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a5038-104">A **Política de Atualização de Edição** do Microsoft Intune permite atualizar automaticamente os dispositivos que executam uma das seguintes versões do Windows 10 para uma edição diferente:</span><span class="sxs-lookup"><span data-stu-id="a5038-104">The Microsoft Intune **Edition Upgrade Policy** lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:</span></span>
* <span data-ttu-id="a5038-105">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="a5038-105">Windows 10 Desktop</span></span>
* <span data-ttu-id="a5038-106">Windows 10 Holographic</span><span class="sxs-lookup"><span data-stu-id="a5038-106">Windows 10 Holographic</span></span>
* <span data-ttu-id="a5038-107">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="a5038-107">Windows 10 Mobile</span></span>

<span data-ttu-id="a5038-108">Há suporte para os seguintes caminhos de atualização:</span><span class="sxs-lookup"><span data-stu-id="a5038-108">The following upgrade paths are supported:</span></span>
- <span data-ttu-id="a5038-109">Do Windows 10 Pro para Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="a5038-109">From Windows 10 Pro to Windows 10 Enterprise</span></span>
- <span data-ttu-id="a5038-110">Do Windows 10 Home para Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="a5038-110">From Windows 10 Home to Windows 10 Education</span></span>
- <span data-ttu-id="a5038-111">Do Windows 10 Mobile para Windows 10 Mobile Enterprise</span><span class="sxs-lookup"><span data-stu-id="a5038-111">From Windows 10 Mobile to Windows 10 Mobile Enterprise</span></span>
- <span data-ttu-id="a5038-112">Do Windows 10 Holographic Pro para o Windows 10 Holographic Enterprise</span><span class="sxs-lookup"><span data-stu-id="a5038-112">From Windows 10 Holographic Pro to Windows 10 Holographic Enterprise</span></span>

## <span data-ttu-id="a5038-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a5038-113">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="a5038-114">Antes de começar a atualizar os dispositivos para a versão mais recente, será necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a5038-114">Before you begin to upgrade devices to the latest version, you will need one of the following:</span></span>
* <span data-ttu-id="a5038-115">Uma chave do produto (Product Key) que é válida para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para edições do Windows 10 Desktop).</span><span class="sxs-lookup"><span data-stu-id="a5038-115">A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions).</span></span> <span data-ttu-id="a5038-116">Você pode usar chaves MAK (Chaves de Ativação Múltipla) ou KMS (Servidor de Gerenciamento de Chaves).</span><span class="sxs-lookup"><span data-stu-id="a5038-116">You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys.</span></span>
<span data-ttu-id="a5038-117">**ou** Um arquivo de licença da Microsoft que contém as informações de licenciamento para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para as edições Windows 10 Mobile e Windows 10 Holographic).</span><span class="sxs-lookup"><span data-stu-id="a5038-117">**or** A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).</span></span>
* <span data-ttu-id="a5038-118">Os dispositivos Windows 10 de destino devem ser registrados no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="a5038-118">The Windows 10 devices that you target must be enrolled in Microsoft Intune.</span></span> <span data-ttu-id="a5038-119">Você não pode usar a política de atualização de edição com computadores que executam o software cliente do Intune PC.</span><span class="sxs-lookup"><span data-stu-id="a5038-119">You cannot use the edition upgrade policy with PCs that run the Intune PC client software.</span></span>

## <span data-ttu-id="a5038-120">Configurações da política de atualização de edição</span><span class="sxs-lookup"><span data-stu-id="a5038-120">Edition upgrade policy settings</span></span>
<a id="edition-upgrade-policy-settings" class="xliff"></a>

|<span data-ttu-id="a5038-121">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="a5038-121">Setting name</span></span>|<span data-ttu-id="a5038-122">Detalhes</span><span class="sxs-lookup"><span data-stu-id="a5038-122">Details</span></span>|
|-|-|
|<span data-ttu-id="a5038-123">**Nome**</span><span class="sxs-lookup"><span data-stu-id="a5038-123">**Name**</span></span>|<span data-ttu-id="a5038-124">Insira um nome para a política de atualização da edição.</span><span class="sxs-lookup"><span data-stu-id="a5038-124">Enter a name for the edition upgrade policy.</span></span>|
|<span data-ttu-id="a5038-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a5038-125">**Description**</span></span>|<span data-ttu-id="a5038-126">Opcionalmente, digite uma descrição para a política que ajude a identificá-la no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="a5038-126">Optionally, enter a description for the policy that helps you identify it in the Intune console.</span></span>
|<span data-ttu-id="a5038-127">**Edição a ser atualizada para**</span><span class="sxs-lookup"><span data-stu-id="a5038-127">**Edition to upgrade to**</span></span>|<span data-ttu-id="a5038-128">Na lista suspensa, selecione a versão do Windows 10 Desktop, Windows 10 Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="a5038-128">From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.</span></span>
|<span data-ttu-id="a5038-129">**Chave do produto (Product Key)**</span><span class="sxs-lookup"><span data-stu-id="a5038-129">**Product Key**</span></span>|<span data-ttu-id="a5038-130">Especifique a chave do produto (Product Key) que você obteve da Microsoft que pode ser usada para atualizar todos os dispositivos de destino do Windows 10 Desktop.</span><span class="sxs-lookup"><span data-stu-id="a5038-130">Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.</span></span><br><span data-ttu-id="a5038-131">Depois de criar uma política que contém uma chave do produto (Product Key), não é possível editar essa chave mais tarde.</span><span class="sxs-lookup"><span data-stu-id="a5038-131">After you create a policy that contains a product key, you cannot edit the product key later.</span></span> <span data-ttu-id="a5038-132">Isso ocorre porque a chave é obscurecida por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="a5038-132">This is because the key is obscured for security reasons.</span></span> <span data-ttu-id="a5038-133">Para alterar a chave do produto (Product Key), você deve inserir a chave inteira novamente.</span><span class="sxs-lookup"><span data-stu-id="a5038-133">To change the product key, you must enter the entire key again.</span></span>
|<span data-ttu-id="a5038-134">**Arquivo de licença**</span><span class="sxs-lookup"><span data-stu-id="a5038-134">**License File**</span></span>|<span data-ttu-id="a5038-135">Escolha **Procurar** para selecionar o arquivo de licença que você obteve da Microsoft com as informações de licença para a edição Windows Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="a5038-135">Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.</span></span>

### <span data-ttu-id="a5038-136">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a5038-136">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="a5038-137">Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a5038-137">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
