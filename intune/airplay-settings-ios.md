---
title: "Configurações do Intune AirPlay para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Saiba como você pode usar o Intune para ajudar com a conexão automática dos dispositivos iOS para dispositivos compatíveis com AirPlay."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7e44c1d438fc5782d696cba0b39c3c4d65492096
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <span data-ttu-id="b1b9a-103">Configurações do Intune AirPlay para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="b1b9a-103">Intune AirPlay settings for iOS devices</span></span>
<a id="intune-airplay-settings-for-ios-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b1b9a-104">Use essas configurações para ajudar a conectar os dispositivos iOS gerenciados a dispositivos compatíveis com AirPlay (como Apple TVs) em sua rede.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-104">Use these settings to help connect iOS devices you manage to AirPlay compatible devices (like Apple TVs) on your network.</span></span>
<span data-ttu-id="b1b9a-105">Com esse recurso, você pode:</span><span class="sxs-lookup"><span data-stu-id="b1b9a-105">With this capability you can:</span></span>

- <span data-ttu-id="b1b9a-106">**Configurar uma lista de dispositivos e senhas** – permita que os usuários se conectem automaticamente aos dispositivos AirPlay que estão no alcance.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-106">**Configure a device and password list** - Let users automatically connect to AirPlay devices that are in range.</span></span> <span data-ttu-id="b1b9a-107">Provisione-os com o nome e a senha dos dispositivos AirPlay, de forma que eles não precisem fornecê-los quando se conectarem.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-107">Provision them with the name and password of AirPlay devices so that they don't need to supply it when they connect.</span></span>
- <span data-ttu-id="b1b9a-108">**Configurar destinos permitidos** - configure uma lista de dispositivos AirPlay (por ID de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="b1b9a-108">**Configure allowed destinations** - Configure a list of AirPlay devices (by device ID).</span></span> <span data-ttu-id="b1b9a-109">Os usuários finais somente podem ver e se conectar aos dispositivos listados (apenas para dispositivos supervisionados).</span><span class="sxs-lookup"><span data-stu-id="b1b9a-109">End users can only see and connect to the devices you list (for supervised devices only).</span></span>

## <span data-ttu-id="b1b9a-110">Introdução</span><span class="sxs-lookup"><span data-stu-id="b1b9a-110">Get started</span></span>
<a id="get-started" class="xliff"></a>

1. <span data-ttu-id="b1b9a-111">Na folha **Recursos do dispositivo**, escolha **AirPlay**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-111">On the **Device features** blade, choose **AirPlay**.</span></span>
2. <span data-ttu-id="b1b9a-112">Na folha **AirPlay**, escolha uma ou ambas as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="b1b9a-112">On the **AirPlay** blade, choose one or both of the following actions:</span></span>

## <span data-ttu-id="b1b9a-113">Configurar uma lista de dispositivos e senha</span><span class="sxs-lookup"><span data-stu-id="b1b9a-113">Configure a device and password list</span></span>
<a id="configure-a-device-and-password-list" class="xliff"></a>

1. <span data-ttu-id="b1b9a-114">Na folha **Senhas**, insira o **Nome do Dispositivo** e a **Senha** de um dispositivo AirPlay, por exemplo, **Contoso Apple TV**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-114">On the **Passwords** blade, enter the **Device Name** and **Password** of an AirPlay device, for example **Contoso Apple TV**.</span></span>
2. <span data-ttu-id="b1b9a-115">Depois de inserir os detalhes do dispositivo, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-115">After entering the device details, click **Add**.</span></span> <span data-ttu-id="b1b9a-116">O dispositivo é exibido na lista **Nome do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-116">The device appears in the **Device Name** list.</span></span>
3. <span data-ttu-id="b1b9a-117">Continue adicionando itens.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-117">Continue to add devices.</span></span> <span data-ttu-id="b1b9a-118">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-118">When you are finished, choose **OK**.</span></span>


## <span data-ttu-id="b1b9a-119">Configurar destinos permitidos</span><span class="sxs-lookup"><span data-stu-id="b1b9a-119">Configure allowed destinations</span></span>
<a id="configure-allowed-destinations" class="xliff"></a>

1. <span data-ttu-id="b1b9a-120">Na folha **Destinos permitidos (somente supervisionados)**, insira a **ID do Dispositivo** de um dispositivo AirPlay, por exemplo, 52:46:CD:51:83:4C.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-120">On the **Allowed destinations (supervised only)** blade, enter the **Device ID** of an AirPlay device, for example 52:46:CD:51:83:4C.</span></span>
2. <span data-ttu-id="b1b9a-121">Depois de inserir a ID do dispositivo, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-121">After entering the device ID, click **Add**.</span></span> <span data-ttu-id="b1b9a-122">A ID é exibida na lista **ID do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-122">The ID appears in the **Device ID** list.</span></span>
3. <span data-ttu-id="b1b9a-123">Continue adicionando itens.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-123">Continue to add devices.</span></span> <span data-ttu-id="b1b9a-124">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-124">When you are finished, choose **OK**.</span></span>

<span data-ttu-id="b1b9a-125">Você também pode importar o dispositivo e as senhas, bem como os destinos permitidos, de um arquivo csv (valores separados por vírgula).</span><span class="sxs-lookup"><span data-stu-id="b1b9a-125">You can also import device and passwords, and allowed destinations from a comma-separated values (csv) file.</span></span>


## <span data-ttu-id="b1b9a-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b1b9a-126">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="b1b9a-127">Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos.</span><span class="sxs-lookup"><span data-stu-id="b1b9a-127">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="b1b9a-128">Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="b1b9a-128">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>

