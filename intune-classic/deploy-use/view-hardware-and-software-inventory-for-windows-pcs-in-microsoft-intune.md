---
title: "Exibir o inventário de software e hardware para computadores Windows"
description: "Como exibir informações de hardware e software sobre áreas de trabalho do Windows gerenciadas como computadores com o cliente de software do Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0fdb49e8742fa49f1c0c1b24d5f09bcaf08a0f0a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1b45e-103">Exibir o inventário de software e hardware para computadores Windows</span><span class="sxs-lookup"><span data-stu-id="1b45e-103">View hardware and software inventory for Windows PCs</span></span>
<a id="view-hardware-and-software-inventory-for-windows-pcs" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1b45e-104">O Intune coleta informações detalhadas sobre o hardware e software de áreas de trabalho gerenciadas como computadores, usando o cliente de software do Intune.</span><span class="sxs-lookup"><span data-stu-id="1b45e-104">Intune collects detailed information about the hardware and software of desktops that you manage as PCs by using the Intune software client.</span></span> <span data-ttu-id="1b45e-105">Use as informações nos procedimentos a seguir para aprender a criar:</span><span class="sxs-lookup"><span data-stu-id="1b45e-105">Use the information in the following procedures to learn how to create:</span></span>

-   <span data-ttu-id="1b45e-106">Um relatório que lista as informações sobre as funcionalidades de hardware dos computadores gerenciados.</span><span class="sxs-lookup"><span data-stu-id="1b45e-106">A report that lists information about the hardware capabilities of PCs you manage.</span></span>

-   <span data-ttu-id="1b45e-107">Um relatório que lista o software instalado em cada computador.</span><span class="sxs-lookup"><span data-stu-id="1b45e-107">A report that lists the software installed on each PC.</span></span>

-   <span data-ttu-id="1b45e-108">Como atualizar um inventário de computadores para garantir que os dados no relatório são atuais.</span><span class="sxs-lookup"><span data-stu-id="1b45e-108">How to refresh a PCs inventory to ensure that the data in the report is current.</span></span>

## <span data-ttu-id="1b45e-109">Para exibir informações sobre os computadores gerenciados</span><span class="sxs-lookup"><span data-stu-id="1b45e-109">To display information about PCs you manage</span></span>
<a id="to-display-information-about-pcs-you-manage" class="xliff"></a>

1.  <span data-ttu-id="1b45e-110">No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Inventário de Computador**.</span><span class="sxs-lookup"><span data-stu-id="1b45e-110">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Computer Inventory Reports**.</span></span>

2.  <span data-ttu-id="1b45e-111">Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório.</span><span class="sxs-lookup"><span data-stu-id="1b45e-111">On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report.</span></span> <span data-ttu-id="1b45e-112">Por exemplo, você pode escolher que apenas os computadores que executam o Windows 8.1 serão exibidos no relatório.</span><span class="sxs-lookup"><span data-stu-id="1b45e-112">For example, you could select that only PCs that run Windows 8.1 will be displayed in the report.</span></span>

3.  <span data-ttu-id="1b45e-113">Escolha **Exibir Relatório** para abrir o **Relatório de Inventário do Computador** em uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="1b45e-113">Choose **View Report** to open the **Computer Inventory Report** in a new window.</span></span>

    <span data-ttu-id="1b45e-114">Você pode classificar o relatório com base em qualquer uma das colunas, como **Nome**, **Tipo de Chassi** ou **Fabricante** selecionando cada título de coluna.</span><span class="sxs-lookup"><span data-stu-id="1b45e-114">You can sort the report by any of the columns, like **Name**, **Chassis Type** or **Manufacturer** by selecting each column heading.</span></span>

## <span data-ttu-id="1b45e-115">Para exibir o software instalado nos computadores gerenciados</span><span class="sxs-lookup"><span data-stu-id="1b45e-115">To display software installed on PCs you manage</span></span>
<a id="to-display-software-installed-on-pcs-you-manage" class="xliff"></a>

1.  <span data-ttu-id="1b45e-116">No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Software Detectados**.</span><span class="sxs-lookup"><span data-stu-id="1b45e-116">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Detected Software Reports**.</span></span>

2.  <span data-ttu-id="1b45e-117">Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório.</span><span class="sxs-lookup"><span data-stu-id="1b45e-117">On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report.</span></span> <span data-ttu-id="1b45e-118">Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório.</span><span class="sxs-lookup"><span data-stu-id="1b45e-118">For example, you could select that only software published by Microsoft will be displayed in the report.</span></span>

3.  <span data-ttu-id="1b45e-119">Escolha **Exibir Relatório** para abrir o **Relatório de Software Detectado** em uma nova janela.</span><span class="sxs-lookup"><span data-stu-id="1b45e-119">Choose **View Report** to open the **Detected Software Report** in a new window.</span></span>

    <span data-ttu-id="1b45e-120">O relatório pode ser classificado com base em qualquer uma das colunas, como **Nome**, **Editor** ou **Categoria** selecionando cada título de coluna.</span><span class="sxs-lookup"><span data-stu-id="1b45e-120">You can sort the report by any of the columns, like **Name**, **Publisher** or **Category** by selecting each column heading.</span></span> <span data-ttu-id="1b45e-121">É possível expandir as atualizações na lista para mostrar mais detalhes (como os computadores nos quais elas estão instaladas) escolhendo a seta de direção ao lado do item de lista.</span><span class="sxs-lookup"><span data-stu-id="1b45e-121">You can expand the updates in the list to show more detail (such as the PCs on which it is installed) by choosing the directional arrow next to the list item.</span></span>

## <span data-ttu-id="1b45e-122">Para atualizar o inventário do computador e garantir que esteja atualizado</span><span class="sxs-lookup"><span data-stu-id="1b45e-122">To refresh computer inventory to ensure it is current</span></span>
<a id="to-refresh-computer-inventory-to-ensure-it-is-current" class="xliff"></a>

1.  <span data-ttu-id="1b45e-123">No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contêm o computador para o qual você deseja atualizar o inventário).</span><span class="sxs-lookup"><span data-stu-id="1b45e-123">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC for which you want to refresh inventory).</span></span>

2.  <span data-ttu-id="1b45e-124">Selecione um computador ou pressione e mantenha a tecla **Ctrl** pressionada para selecionar vários computadores.</span><span class="sxs-lookup"><span data-stu-id="1b45e-124">Select a PC, or press and hold **Ctrl** to select multiple PCs.</span></span>

3.  <span data-ttu-id="1b45e-125">Na barra de tarefas, clique em **Tarefas Remotas** &gt; **Atualizar Inventário**.</span><span class="sxs-lookup"><span data-stu-id="1b45e-125">On the taskbar, choose **Remote Tasks** &gt; **Refresh Inventory**.</span></span>

4.  <span data-ttu-id="1b45e-126">Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.</span><span class="sxs-lookup"><span data-stu-id="1b45e-126">To view the task status, choose **Remote Tasks** in the bottom right corner of the page.</span></span>

    <span data-ttu-id="1b45e-127">A caixa de diálogo **Status da tarefa** é exibida e mostra as tarefas remotas atuais, seus status, nome do dispositivo, todos os erros reportados e fornece um link para as informações sobre a solução problemas.</span><span class="sxs-lookup"><span data-stu-id="1b45e-127">The **Task Status** dialog box displays showing current remote tasks, task status, device name, and any reported errors, and provides a link to troubleshooting information.</span></span>

### <span data-ttu-id="1b45e-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1b45e-128">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="1b45e-129">Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="1b45e-129">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)