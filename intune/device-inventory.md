---
title: "Exibir o inventário de dispositivo do Intune"
titleSuffix: Intune on Azure
description: Saiba como exibir os dispositivos gerenciados com o Intune e entender seu hardware e seus aplicativos instalados.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dae92c117bcf8a4a8ff133ed613f9f77ea0c07c2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1032b-103">Como exibir o inventário de dispositivo do Intune</span><span class="sxs-lookup"><span data-stu-id="1032b-103">How to view Intune device inventory</span></span>
<a id="how-to-view-intune-device-inventory" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1032b-104">A carga de trabalho **Dispositivos** fornece informações sobre os dispositivos gerenciados, incluindo suas funcionalidades de hardware e os aplicativos instalados neles.</span><span class="sxs-lookup"><span data-stu-id="1032b-104">The **Devices** workload gives you insights into the devices you manage, including their hardware capabilities, and the apps installed on them.</span></span> 

<span data-ttu-id="1032b-105">Para exibir o inventário de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="1032b-105">To view device inventory:</span></span>

1. <span data-ttu-id="1032b-106">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="1032b-106">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="1032b-107">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1032b-107">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="1032b-108">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="1032b-108">On the **Intune** blade, choose **Devices**.</span></span>

<span data-ttu-id="1032b-109">Agora, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1032b-109">Now, choose one of the following options:</span></span>

- <span data-ttu-id="1032b-110">**Visão geral** Obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executado.</span><span class="sxs-lookup"><span data-stu-id="1032b-110">**Overview** Get information about devices you've enrolled, and the operating systems each device runs.</span></span>
- <span data-ttu-id="1032b-111">**Gerenciar** – Escolha **Todos os Dispositivos** para ver uma lista de todos os dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="1032b-111">**Manage** - Choose **All Devices** to see a list of all the devices you manage.</span></span>
    <span data-ttu-id="1032b-112">Selecione um desses dispositivos na lista para abrir a folha <*nome do dispositivo*> **Visão geral** na qual você pode selecionar um destes:</span><span class="sxs-lookup"><span data-stu-id="1032b-112">Select one of those devices in the list to open the <*device name*> **Overview** blade where you can select one of:</span></span>
    - <span data-ttu-id="1032b-113">**Visão geral** – Veja informações gerais sobre o dispositivo, incluindo seu nome, proprietário, se ele é um dispositivo BYOD, quando foi seu último check-in e muito mais.</span><span class="sxs-lookup"><span data-stu-id="1032b-113">**Overview**  - See general information about the device including its name, owner, whether it is a BYOD device, when it checked-in, and more.</span></span>
    <span data-ttu-id="1032b-114">![Visão geral do dispositivo](./media/device-overview.png)</span><span class="sxs-lookup"><span data-stu-id="1032b-114">![Device overview](./media/device-overview.png)</span></span>
    - <span data-ttu-id="1032b-115">**Hardware** – Consulte informações mais detalhadas sobre o dispositivo, inclusive o espaço de armazenamento livre, modelo e fabricante, entre outros.</span><span class="sxs-lookup"><span data-stu-id="1032b-115">**Hardware** - See more detailed information about the device including its free storage space, model and manufacturer, and more.</span></span>
    <span data-ttu-id="1032b-116">![Inventário de hardware de dispositivo gerenciado](./media/hardware-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="1032b-116">![Managed device hardware inventory](./media/hardware-inventory.png)</span></span>
    - <span data-ttu-id="1032b-117">**Aplicativos descobertos** – Exibe uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1032b-117">**Discovered apps** - Displays a list of all apps that Intune found installed on the device.</span></span>
    <span data-ttu-id="1032b-118">![Nó Aplicativos descobertos](./media/detected-applications.png)</span><span class="sxs-lookup"><span data-stu-id="1032b-118">![Discovered apps node](./media/detected-applications.png)</span></span>
    - <span data-ttu-id="1032b-119">**Conformidade do dispositivo** – Exibe o estado de conformidade de todas as políticas de conformidade que foram atribuídas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1032b-119">**Device compliance** - Displays the compliance state of all compliance policies that have been assigned to the device.</span></span>
    - <span data-ttu-id="1032b-120">**Configuração do dispositivo** – Exibe o estado de conformidade de todas as políticas de configuração do dispositivo que foram atribuídas a ele.</span><span class="sxs-lookup"><span data-stu-id="1032b-120">**Device configuration** - Displays the compliance state of all device configuration policies that have been assigned to the device.</span></span>
- <span data-ttu-id="1032b-121">**Monitorar** Escolha **Ações de Dispositivo** para ver uma lista de ações de dispositivo que foram realizadas em dispositivos gerenciados por você, bem como o estado atual dessas ações.</span><span class="sxs-lookup"><span data-stu-id="1032b-121">**Monitor** Choose **Device Actions** to see a list of device actions that have been performed on devices you manage and their current state.</span></span>
- <span data-ttu-id="1032b-122">**Instalação** > **Conector do TeamViewer** – Permite configurar a administração remota em dispositivos que usam o software do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="1032b-122">**Setup** > **TeamViewer Connector** - Let's you configure remote administration on devices using the TeamViewer software.</span></span> <span data-ttu-id="1032b-123">Para ver mais detalhes, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](/intune/device-profile-android-teamviewer).</span><span class="sxs-lookup"><span data-stu-id="1032b-123">For details, see [Provide remote assistance for Intune managed Android devices](/intune/device-profile-android-teamviewer).</span></span>


