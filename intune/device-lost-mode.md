---
title: Ativar modo perdido do iOS com o Intune
titleSuffix: Intune on Azure
description: Saiba como usar o Intune para ativar o modo perdido em dispositivos iOS perdidos ou roubados.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a34d008ae76355578c6f24a932c9e1e501d5b46b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="de4f6-103">Ativar modo perdido em dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="de4f6-103">Activate lost mode on iOS devices</span></span>
<a id="activate-lost-mode-on-ios-devices" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="de4f6-104">A ação de dispositivo **Modo perdido** ajuda você a habilitar o modo perdido em dispositivos iOS perdidos ou roubados.</span><span class="sxs-lookup"><span data-stu-id="de4f6-104">The **Lost mode** device action helps you enable lost mode on lost or stolen iOS devices.</span></span> <span data-ttu-id="de4f6-105">Esse modo permite especificar uma mensagem e um número de telefone que serão exibidos na tela de bloqueio do dispositivo</span><span class="sxs-lookup"><span data-stu-id="de4f6-105">This mode lets you specify a message and a phone number that will be displayed on the lock screen of the device</span></span>

1. <span data-ttu-id="de4f6-106">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="de4f6-106">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="de4f6-107">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="de4f6-107">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="de4f6-108">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="de4f6-108">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="de4f6-109">Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="de4f6-109">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="de4f6-110">Na lista de dispositivos gerenciados, escolha um dispositivo iOS e, em seguida, escolha a ação remota **Modo perdido**.</span><span class="sxs-lookup"><span data-stu-id="de4f6-110">From the list of devices you manage, choose an iOS device, and then choose the **Lost mode** remote action.</span></span>
6. <span data-ttu-id="de4f6-111">Na folha **Modo perdido**, ative o modo perdido, digite a mensagem que será exibida e, opcionalmente, um número de telefone de contato.</span><span class="sxs-lookup"><span data-stu-id="de4f6-111">On the **Lost mode** blade, enable lost mode, enter the message that will be displayed, and optionally, a contact phone number.</span></span>
7. <span data-ttu-id="de4f6-112">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="de4f6-112">Click **OK**.</span></span>

<span data-ttu-id="de4f6-113">Quando você ativa o modo perdido, bloqueia todo o uso do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de4f6-113">When you enable lost mode, you block all use of the device.</span></span> <span data-ttu-id="de4f6-114">O usuário final não poderá acessar o dispositivo até que você desative o modo perdido.</span><span class="sxs-lookup"><span data-stu-id="de4f6-114">The end user cannot access the device until you disable lost mode.</span></span> <span data-ttu-id="de4f6-115">Enquanto o modo perdido estiver habilitado, você poderá usar a ação **Localizar dispositivo** para descobrir onde está o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de4f6-115">While lost mode is enabled, you can use the **Locate device** action to find out where the device is.</span></span>
<span data-ttu-id="de4f6-116">Para usar o modo perdido, o dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.</span><span class="sxs-lookup"><span data-stu-id="de4f6-116">To use lost mode, the device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.</span></span>

<span data-ttu-id="de4f6-117">Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="de4f6-117">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>

## <span data-ttu-id="de4f6-118">Informações sobre segurança e privacidade para o modo perdido e ações para localizar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="de4f6-118">Security and privacy information for the lost mode and locate device actions</span></span>
<a id="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions" class="xliff"></a>
- <span data-ttu-id="de4f6-119">Nenhuma informação do local do dispositivo será enviada para o Intune até que você ative esta ação.</span><span class="sxs-lookup"><span data-stu-id="de4f6-119">No device location information is sent to Intune until you turn this action on.</span></span>
- <span data-ttu-id="de4f6-120">Quando você usa a ação para localizar o dispositivo, as coordenadas da latitude e longitude do dispositivo são enviadas para o Intune e exibidas no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="de4f6-120">When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.</span></span>
- <span data-ttu-id="de4f6-121">Os dados são armazenados por 24 horas, então, removidos.</span><span class="sxs-lookup"><span data-stu-id="de4f6-121">The data is stored for 24 hours, then removed.</span></span> <span data-ttu-id="de4f6-122">Você não pode remover manualmente os dados de localização.</span><span class="sxs-lookup"><span data-stu-id="de4f6-122">You cannot manually remove the location data.</span></span>
- <span data-ttu-id="de4f6-123">Os dados de localização são criptografados, enquanto estão armazenados e enquanto estão sendo transmitidos.</span><span class="sxs-lookup"><span data-stu-id="de4f6-123">Location data is encrypted, both while stored, and while being transmitted.</span></span>
- <span data-ttu-id="de4f6-124">Ao configurar o modo perdido, recomendamos que a mensagem inserida para exibição na tela de bloqueio inclua informações que ajudam a pessoa que encontrar o dispositivo a devolvê-lo.</span><span class="sxs-lookup"><span data-stu-id="de4f6-124">When you configure lost mode, we recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.</span></span>

