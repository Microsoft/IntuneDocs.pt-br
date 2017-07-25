---
title: Remover dados da empresa de dispositivos com o Intune
titleSuffix: Intune on Azure
description: Saiba como remover apenas os dados da empresa de dispositivos gerenciados com o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="8b690-103">Remover dados da empresa de dispositivos gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="8b690-103">Remove company data from Intune-managed devices</span></span>
<a id="remove-company-data-from-intune-managed-devices" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="8b690-104">A opção **Remover dados da empresa** remove somente os dados da empresa de dispositivos gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="8b690-104">The **Remove company data** removes only company data from devices managed by Intune.</span></span> <span data-ttu-id="8b690-105">Não remove dados pessoais do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8b690-105">Does not remove personal data from the device.</span></span> <span data-ttu-id="8b690-106">O dispositivo não será mais gerenciado pelo Intune e não será capaz de acessar recursos corporativos (sem suporte para dispositivos Windows que fazem parte do Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="8b690-106">The device will no longer be managed by Intune, and will no longer be able to access corporate resources (not supported for Windows devices that are joined to Azure Active Directory).</span></span>

1. <span data-ttu-id="8b690-107">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="8b690-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="8b690-108">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="8b690-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="8b690-109">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8b690-109">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="8b690-110">Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8b690-110">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="8b690-111">Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Remover dados da empresa**.</span><span class="sxs-lookup"><span data-stu-id="8b690-111">From the list of devices you manage, choose a device, and then choose the **Remove company data** device remote action.</span></span>

<span data-ttu-id="8b690-112">Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8b690-112">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
