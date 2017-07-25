---
<<<<<<< HEAD
title: "<span data-ttu-id=\"53929-101\">Exibir o inventário de dispositivo do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"53929-101\">View Intune device inventory</span></span>"
titleSuffix: Intune on Azure
description: <span data-ttu-id="53929-102">Saiba como exibir os dispositivos gerenciados com o Intune e entender seu hardware e seus aplicativos instalados.</span><span class="sxs-lookup"><span data-stu-id="53929-102">Learn how to view the devices you manage with Intune, and understand their hardware and installed apps."</span></span>
=======
title: "Exibir o inventário de dispositivo do Intune"
titleSuffix: Intune on Azure
description: Saiba como exibir os dispositivos gerenciados com o Intune e entender seu hardware e seus aplicativos instalados.
>>>>>>> live
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3618c5ee0b4a7ff0e7b6a4d6ed58f77a2af0ba66
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
<<<<<<< HEAD
# <a name="how-to-view-intune-device-inventory"></a><span data-ttu-id="53929-103">Como exibir o inventário de dispositivo do Intune</span><span class="sxs-lookup"><span data-stu-id="53929-103">How to view Intune device inventory</span></span>
=======
# <a name="how-to-view-intune-device-inventory"></a>Como exibir o inventário de dispositivo do Intune
>>>>>>> live


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="53929-104">A carga de trabalho **Dispositivos** fornece informações sobre os dispositivos gerenciados, incluindo suas funcionalidades de hardware e os aplicativos instalados neles.</span><span class="sxs-lookup"><span data-stu-id="53929-104">The **Devices** workload gives you insights into the devices you manage, including their hardware capabilities, and the apps installed on them.</span></span> 

<span data-ttu-id="53929-105">Para exibir o inventário de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="53929-105">To view device inventory:</span></span>

1. <span data-ttu-id="53929-106">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="53929-106">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="53929-107">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="53929-107">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="53929-108">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="53929-108">On the **Intune** blade, choose **Devices**.</span></span>

<span data-ttu-id="53929-109">Agora, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="53929-109">Now, choose one of the following options:</span></span>

- <span data-ttu-id="53929-110">**Visão geral** Obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executado.</span><span class="sxs-lookup"><span data-stu-id="53929-110">**Overview** Get information about devices you've enrolled, and the operating systems each device runs.</span></span>
- <span data-ttu-id="53929-111">**Gerenciar** – Escolha **Todos os Dispositivos** para ver uma lista de todos os dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="53929-111">**Manage** - Choose **All Devices** to see a list of all the devices you manage.</span></span>
    <span data-ttu-id="53929-112">Selecione um desses dispositivos na lista para abrir a folha <*nome do dispositivo*> **Visão geral** na qual você pode selecionar um destes:</span><span class="sxs-lookup"><span data-stu-id="53929-112">Select one of those devices in the list to open the <*device name*> **Overview** blade where you can select one of:</span></span>
    - <span data-ttu-id="53929-113">**Visão geral** – Veja informações gerais sobre o dispositivo, incluindo seu nome, proprietário, se ele é um dispositivo BYOD, quando foi seu último check-in e muito mais.</span><span class="sxs-lookup"><span data-stu-id="53929-113">**Overview**  - See general information about the device including its name, owner, whether it is a BYOD device, when it checked-in, and more.</span></span>
    <span data-ttu-id="53929-114">![Visão geral do dispositivo](./media/device-overview.png)</span><span class="sxs-lookup"><span data-stu-id="53929-114">![Device overview](./media/device-overview.png)</span></span>
    - <span data-ttu-id="53929-115">**Hardware** – Consulte informações mais detalhadas sobre o dispositivo, inclusive o espaço de armazenamento livre, modelo e fabricante, entre outros.</span><span class="sxs-lookup"><span data-stu-id="53929-115">**Hardware** - See more detailed information about the device including its free storage space, model and manufacturer, and more.</span></span>
    <span data-ttu-id="53929-116">![Inventário de hardware de dispositivo gerenciado](./media/hardware-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="53929-116">![Managed device hardware inventory](./media/hardware-inventory.png)</span></span>
    - <span data-ttu-id="53929-117">**Aplicativos descobertos** – Exibe uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53929-117">**Discovered apps** - Displays a list of all apps that Intune found installed on the device.</span></span>
    <span data-ttu-id="53929-118">![Nó Aplicativos descobertos](./media/detected-applications.png)</span><span class="sxs-lookup"><span data-stu-id="53929-118">![Discovered apps node](./media/detected-applications.png)</span></span>
    


    - <span data-ttu-id="53929-119">**Conformidade do dispositivo** – Exibe o estado de conformidade de todas as políticas de conformidade que foram atribuídas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53929-119">**Device compliance** - Displays the compliance state of all compliance policies that have been assigned to the device.</span></span>
    - <span data-ttu-id="53929-120">**Configuração do dispositivo** – Exibe o estado de conformidade de todas as políticas de configuração do dispositivo que foram atribuídas a ele.</span><span class="sxs-lookup"><span data-stu-id="53929-120">**Device configuration** - Displays the compliance state of all device configuration policies that have been assigned to the device.</span></span>
- <span data-ttu-id="53929-121">**Monitorar** Escolha **Ações de Dispositivo** para ver uma lista de ações de dispositivo que foram realizadas em dispositivos gerenciados por você, bem como o estado atual dessas ações.</span><span class="sxs-lookup"><span data-stu-id="53929-121">**Monitor** Choose **Device Actions** to see a list of device actions that have been performed on devices you manage and their current state.</span></span>
- <span data-ttu-id="53929-122">**Instalação** > **Conector do TeamViewer** – Permite configurar a administração remota em dispositivos que usam o software do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="53929-122">**Setup** > **TeamViewer Connector** - Let's you configure remote administration on devices using the TeamViewer software.</span></span> <span data-ttu-id="53929-123">Para ver mais detalhes, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](/intune/device-profile-android-teamviewer).</span><span class="sxs-lookup"><span data-stu-id="53929-123">For details, see [Provide remote assistance for Intune managed Android devices](/intune/device-profile-android-teamviewer).</span></span>

>[!NOTE]
> <span data-ttu-id="53929-124">O Intune coleta o inventário de aplicativos apenas em dispositivos de propriedade da empresa.</span><span class="sxs-lookup"><span data-stu-id="53929-124">Intune collects app inventory only on corporate-owned devices.</span></span> <span data-ttu-id="53929-125">Os aplicativos não são inventariados nos dispositivos pessoais.</span><span class="sxs-lookup"><span data-stu-id="53929-125">Apps are not inventoried on personal devices.</span></span> <span data-ttu-id="53929-126">No caso de PCs com Windows 10, o Intune coleta apenas um inventário de aplicativos modernos em dispositivos de propriedade da empresa.</span><span class="sxs-lookup"><span data-stu-id="53929-126">For Windows 10 PCs, only modern app inventory is collected on corporate-owned devices.</span></span> <span data-ttu-id="53929-127">O Intune não coleta informações sobre aplicativos Win32 no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53929-127">Intune does not collect information about Win32 apps on the device.</span></span>
=======
A carga de trabalho **Dispositivos** fornece informações sobre os dispositivos gerenciados, incluindo suas funcionalidades de hardware e os aplicativos instalados neles. 

Para exibir o inventário de dispositivo:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.

Agora, selecione uma das seguintes opções:

- **Visão geral** Obtenha informações sobre os dispositivos registrados e os sistemas operacionais que cada dispositivo executado.
- **Gerenciar** – Escolha **Todos os Dispositivos** para ver uma lista de todos os dispositivos gerenciados.
    Selecione um desses dispositivos na lista para abrir a folha <*nome do dispositivo*> **Visão geral** na qual você pode selecionar um destes:
    - **Visão geral** – Veja informações gerais sobre o dispositivo, incluindo seu nome, proprietário, se ele é um dispositivo BYOD, quando foi seu último check-in e muito mais.
    ![Visão geral do dispositivo](./media/device-overview.png)
    - **Hardware** – Consulte informações mais detalhadas sobre o dispositivo, inclusive o espaço de armazenamento livre, modelo e fabricante, entre outros.
    ![Inventário de hardware de dispositivo gerenciado](./media/hardware-inventory.png)
    - **Aplicativos descobertos** – Exibe uma lista de todos os aplicativos que o Intune encontrou instalados no dispositivo.
    ![Nó Aplicativos descobertos](./media/detected-applications.png)
    


    - **Conformidade do dispositivo** – Exibe o estado de conformidade de todas as políticas de conformidade que foram atribuídas ao dispositivo.
    - **Configuração do dispositivo** – Exibe o estado de conformidade de todas as políticas de configuração do dispositivo que foram atribuídas a ele.
- **Monitorar** Escolha **Ações de Dispositivo** para ver uma lista de ações de dispositivo que foram realizadas em dispositivos gerenciados por você, bem como o estado atual dessas ações.
- **Instalação** > **Conector do TeamViewer** – Permite configurar a administração remota em dispositivos que usam o software do TeamViewer. Para ver mais detalhes, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](/intune/device-profile-android-teamviewer).

>[!NOTE]
> O Intune coleta o inventário de aplicativos apenas em dispositivos de propriedade da empresa. Os aplicativos não são inventariados nos dispositivos pessoais. No caso de PCs com Windows 10, o Intune coleta apenas um inventário de aplicativos modernos em dispositivos de propriedade da empresa. O Intune não coleta informações sobre aplicativos Win32 no dispositivo.
>>>>>>> live
