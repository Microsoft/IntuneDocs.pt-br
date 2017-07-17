---
title: "Configurações do Intune AirPrint para dispositivos iOS e macOS"
titleSuffix: Intune on Azure
description: "Saiba como você pode usar o Intune para ajudar a conectar automaticamente dispositivos iOS e macOS com impressoras compatíveis com AirPrint."
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
ms.openlocfilehash: 743eb9a71efe1a5ea18b15312fdd4fe684f0ff07
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <span data-ttu-id="7fd8a-103">Configurações do AirPrint para dispositivos iOS e macOS</span><span class="sxs-lookup"><span data-stu-id="7fd8a-103">AirPrint settings for iOS and macOS devices</span></span>
<a id="airprint-settings-for-ios-and-macos-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7fd8a-104">Use essas configurações para configurar os dispositivos iOS ou macOS para se conectarem automaticamente a impressoras compatíveis com AirPrint em sua rede.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-104">Use these settings to configure iOS or macOS devices to automatically connect to AirPrint compatible printers on your network.</span></span> <span data-ttu-id="7fd8a-105">Você precisará do endereço IP e do caminho de recursos de suas impressoras para continuar.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-105">You need the IP address and resource path of your printers to proceed.</span></span>

## <span data-ttu-id="7fd8a-106">Encontrar informações da impressora AirPrint</span><span class="sxs-lookup"><span data-stu-id="7fd8a-106">Find AirPrint printer information</span></span>
<a id="find-airprint-printer-information" class="xliff"></a>

<span data-ttu-id="7fd8a-107">Use este procedimento para adicionar informações do AirPrint à carga do AirPrint, para que os usuários de dispositivos iOS possam imprimir em impressoras do AirPrint conhecidas.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-107">Use this procedure to add AirPrint information to the AirPrint payload so that iOS device users can print to known AirPrint printers.</span></span>

1. <span data-ttu-id="7fd8a-108">Em um Mac conectado à mesma rede local (sub-rede) que as impressoras AirPrint, abra o Terminal (em **/Applications/Utilities**)</span><span class="sxs-lookup"><span data-stu-id="7fd8a-108">On a Mac that’s connected to the same local network (subnet) as the AirPrint printers, open Terminal (from **/Applications/Utilities**)</span></span>
2. <span data-ttu-id="7fd8a-109">No Terminal, digite **ippfind** e pressione enter.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-109">In the Terminal, type **ippfind**, then press enter.</span></span>
3. <span data-ttu-id="7fd8a-110">Anote qualquer informação sobre a impressora retornada pelo comando, por exemplo: **ipp://myprinter.local.:631/ipp/port1**.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-110">Make a note of any printer information the command returns, for example: **ipp://myprinter.local.:631/ipp/port1**.</span></span> <span data-ttu-id="7fd8a-111">A primeira parte das informações é o nome da impressora, e a última parte é o caminho do recurso.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-111">The first part of the information is the name of your printer and the last part is the resource path.</span></span>
4. <span data-ttu-id="7fd8a-112">No Terminal, digite **ping myprinter.local** e pressione enter.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-112">In the Terminal, type **ping myprinter.local**, then press enter.</span></span>
5. <span data-ttu-id="7fd8a-113">Anote as informações de endereço IP retornadas pelo comando, por exemplo, **myprinter.local de PING (10.50.25.21)**.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-113">Make a note of the IP address information returned by the command, for example, **PING myprinter.local (10.50.25.21)**.</span></span>
6. <span data-ttu-id="7fd8a-114">Por fim, use o caminho de recursos e o endereço IP nas configurações de carga do AirPrint.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-114">Finally, use the IP address and resource path in the AirPrint payload settings.</span></span> <span data-ttu-id="7fd8a-115">Um exemplo de endereço IP pode ser **10.50.25.21**, e um exemplo de caminho de recurso pode ser **/ipp port1**.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-115">An example IP address might be **10.50.25.21**, and an example resource path might be **/ipp/port1**.</span></span>

## <span data-ttu-id="7fd8a-116">Configurar um perfil de AirPrint</span><span class="sxs-lookup"><span data-stu-id="7fd8a-116">Configure an AirPrint profile</span></span>
<a id="configure-an-airprint-profile" class="xliff"></a>

1. <span data-ttu-id="7fd8a-117">Na folha **Recursos do dispositivo**, escolha **AirPrint**.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-117">On the **Device features** blade, choose **AirPrint**.</span></span>
2. <span data-ttu-id="7fd8a-118">Na folha **AirPrint**, para adicionar um destino de AirPrint, insira seu **Endereço IP** e **caminho do recurso**e depois clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-118">On the **AirPrint** blade, to add an AirPrint destination, enter its **IP address** and **resource path**, and then click **Add**.</span></span>
3. <span data-ttu-id="7fd8a-119">Adicionar quantos destinos forem necessários.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-119">Continue to add as many destinations as you need.</span></span> <span data-ttu-id="7fd8a-120">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-120">When you are finished, choose **OK**.</span></span>

<span data-ttu-id="7fd8a-121">Você também pode importar uma lista de impressoras de um arquivo de valores separados por vírgulas (.csv) ou exportar a lista.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-121">You can also import a list of printers from a comma-separated values (.csv) file or export the list.</span></span>


## <span data-ttu-id="7fd8a-122">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7fd8a-122">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="7fd8a-123">Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos.</span><span class="sxs-lookup"><span data-stu-id="7fd8a-123">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="7fd8a-124">Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="7fd8a-124">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>