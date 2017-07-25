---
title: Bloquear dispositivos gerenciados remotamente com o Intune
titleSuffix: Intune on Azure
description: Saiba como usar o Intune para bloquear os dispositivos gerenciados remotamente.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e6a372d6512c68ef7eb7df5796f91d8259d024b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="68a3f-103">Bloquear dispositivos gerenciados remotamente com o Intune</span><span class="sxs-lookup"><span data-stu-id="68a3f-103">Remotely lock managed devices with Intune</span></span>
<a id="remotely-lock-managed-devices-with-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="68a3f-104">O dispositivo **Bloqueio remoto** bloqueia o dispositivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="68a3f-104">The **Remote lock** device locks the selected device.</span></span> <span data-ttu-id="68a3f-105">O proprietário do dispositivo deve usar a senha para desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="68a3f-105">The device owner must use their passcode to unlock it.</span></span> <span data-ttu-id="68a3f-106">Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.</span><span class="sxs-lookup"><span data-stu-id="68a3f-106">You can only remotely lock a device that has a PIN or password set.</span></span>

1. <span data-ttu-id="68a3f-107">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="68a3f-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="68a3f-108">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="68a3f-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="68a3f-109">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="68a3f-109">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="68a3f-110">Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="68a3f-110">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="68a3f-111">Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Bloqueio remoto**.</span><span class="sxs-lookup"><span data-stu-id="68a3f-111">From the list of devices you manage, choose a device, and then choose the **Remote lock** device remote action.</span></span>

<span data-ttu-id="68a3f-112">Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="68a3f-112">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
