---
title: Localizar dispositivos iOS perdidos com o Intune
titleSuffix: Intune on Azure
description: Saiba como localizar dispositivos iOS perdidos ou roubados com o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 80aa0e5afd1f8862b181d455ff6b545e462f90c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="9eae7-103">Localizar dispositivos iOS perdidos ou roubados com o Intune</span><span class="sxs-lookup"><span data-stu-id="9eae7-103">Locate lost or stolen iOS devices with Intune</span></span>
<a id="locate-lost-or-stolen-ios-devices-with-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="9eae7-104">A ação de dispositivo **Localizar Dispositivo** exibe a localização de um dispositivo iOS perdido ou roubado em um mapa.</span><span class="sxs-lookup"><span data-stu-id="9eae7-104">The **Locate Device** device action displays the location of a lost or stolen iOS device on a map.</span></span> <span data-ttu-id="9eae7-105">O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.</span><span class="sxs-lookup"><span data-stu-id="9eae7-105">The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.</span></span> <span data-ttu-id="9eae7-106">Antes de usar essa ação, o dispositivo deve ter sido colocado no [modo perdido](/intune-azure/manage-devices/lost-mode.md).</span><span class="sxs-lookup"><span data-stu-id="9eae7-106">Before you use this action, the device must have been placed into [lost mode](/intune-azure/manage-devices/lost-mode.md).</span></span>

1. <span data-ttu-id="9eae7-107">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="9eae7-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="9eae7-108">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9eae7-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="9eae7-109">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9eae7-109">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="9eae7-110">Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="9eae7-110">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="9eae7-111">Na lista de dispositivos gerenciados, escolha um dispositivo iOS e, em seguida, escolha a ação remota **Localizar Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9eae7-111">From the list of devices you manage, choose an iOS device, and then choose the **Locate Device** remote action.</span></span>
6. <span data-ttu-id="9eae7-112">Depois do dispositivo ser localizado, o local será exibido na folha **Localizar dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9eae7-112">After the device has been located, it's location is displayed on the **Locate device** blade.</span></span>
    <span data-ttu-id="9eae7-113">![Folha Localizar dispositivo](./media/locate-device.png)</span><span class="sxs-lookup"><span data-stu-id="9eae7-113">![Locate device blade](./media/locate-device.png)</span></span>

>[!NOTE]
><span data-ttu-id="9eae7-114">Para fins de privacidade, a distância de ampliação do zoom do mapa é limitada.</span><span class="sxs-lookup"><span data-stu-id="9eae7-114">For privacy purposes, the distance you can zoom into the map is limited.</span></span>

## <span data-ttu-id="9eae7-115">Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9eae7-115">Security and privacy information for the lost mode and locate device actions</span></span>
<a id="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions" class="xliff"></a>
- <span data-ttu-id="9eae7-116">Nenhuma informação do local do dispositivo será enviada para o Intune até que você ative esta ação.</span><span class="sxs-lookup"><span data-stu-id="9eae7-116">No device location information is sent to Intune until you turn this action on.</span></span>
- <span data-ttu-id="9eae7-117">Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="9eae7-117">When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.</span></span>
- <span data-ttu-id="9eae7-118">Os dados são armazenados por 24 horas, então, removidos.</span><span class="sxs-lookup"><span data-stu-id="9eae7-118">The data is stored for 24 hours, then removed.</span></span> <span data-ttu-id="9eae7-119">Você não pode remover manualmente os dados de localização.</span><span class="sxs-lookup"><span data-stu-id="9eae7-119">You cannot manually remove the location data.</span></span>
- <span data-ttu-id="9eae7-120">Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.</span><span class="sxs-lookup"><span data-stu-id="9eae7-120">Location data is encrypted, both while stored, and while being transmitted.</span></span>
- <span data-ttu-id="9eae7-121">Ao configurar o modo perdido, recomendamos que a mensagem inserida para exibição na tela de bloqueio inclua informações que ajudam a pessoa que encontrar o dispositivo a devolvê-lo.</span><span class="sxs-lookup"><span data-stu-id="9eae7-121">When you configure lost mode, we recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.</span></span>
