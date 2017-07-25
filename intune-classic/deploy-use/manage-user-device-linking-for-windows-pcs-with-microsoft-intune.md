---
title: "Gerenciar a vinculação de usuário e dispositivo para computadores Windows"
description: "Como vincular um usuário a um computador Windows gerenciado pelo Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9641c40229be52066a97389584e55f2f95bc286d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d21f5-103">Gerenciar a vinculação de usuário e dispositivo para computadores Windows</span><span class="sxs-lookup"><span data-stu-id="d21f5-103">Manage user-device linking for Windows PCs</span></span>
<a id="manage-user-device-linking-for-windows-pcs" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d21f5-104">As informações descritas neste tópico se aplicam somente a áreas de trabalho do Windows que estão sendo gerenciadas como computadores por meio do cliente de software do Intune.</span><span class="sxs-lookup"><span data-stu-id="d21f5-104">The information in this topic applies only to Windows desktops that you are managing as PCs by using the Intune software client.</span></span> 

<span data-ttu-id="d21f5-105">Antes de poder implantar o software em um usuário, é necessário vincular o usuário a um computador.</span><span class="sxs-lookup"><span data-stu-id="d21f5-105">Before you can deploy software to a user, you must link the user to a PC.</span></span> <span data-ttu-id="d21f5-106">É possível vincular um usuário a vários computadores, mas cada computador pode ser vinculado a apenas um usuário.</span><span class="sxs-lookup"><span data-stu-id="d21f5-106">You can link a user to multiple PCs, but each PC can be linked to only one user.</span></span> <span data-ttu-id="d21f5-107">Os usuários são vinculados automaticamente aos computadores registrados por eles no Intune por meio do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="d21f5-107">Users are automatically linked to any PCs that they enroll in Intune by using the company portal.</span></span>

<span data-ttu-id="d21f5-108">Para vincular um usuário a um computador:</span><span class="sxs-lookup"><span data-stu-id="d21f5-108">To link a user to a PC:</span></span>

1.  <span data-ttu-id="d21f5-109">No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contém o computador que você deseja vincular a um usuário).</span><span class="sxs-lookup"><span data-stu-id="d21f5-109">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to link to a user).</span></span>

2.  <span data-ttu-id="d21f5-110">Selecione o computador que você deseja vincular a um usuário e escolha **Vincular Usuário**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-110">Select the PC that you want to link a user, and then choose **Link User**.</span></span>

    <span data-ttu-id="d21f5-111">A caixa de diálogo **Vincular Usuário** exibe uma lista de usuários disponíveis com o nome de exibição, ID de usuário e o número de computadores aos quais cada usuário está vinculado.</span><span class="sxs-lookup"><span data-stu-id="d21f5-111">The **Link User** dialog box displays a list of available users with their display name, user ID, and the number of PCs to which each user is currently linked.</span></span> <span data-ttu-id="d21f5-112">Se um usuário já estiver vinculado ao computador selecionado, o nome e a ID desse usuário serão exibidos em **Usuário atual**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-112">If a user is already linked to the selected PC, that user’s name and user ID are displayed under **Current user**.</span></span> <span data-ttu-id="d21f5-113">Se o computador não estiver vinculado a nenhum usuário, a opção **Nenhum Usuário** será exibida em **Usuário Atual**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-113">If the PC is not linked to any user, **No User** appears under **Current User**.</span></span>

3.  <span data-ttu-id="d21f5-114">Realize um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="d21f5-114">Do one of the following:</span></span>

    -   <span data-ttu-id="d21f5-115">Para deixar o computador vinculado ao usuário atual, se houver um, escolha **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-115">To leave the PC linked to its current user, if there is one, choose **Cancel**.</span></span>

    -   <span data-ttu-id="d21f5-116">Para remover o vínculo com o usuário atual, se houver, escolha **Remover link **&gt; **OK**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-116">To remove the link to the current user, if there is one, choose **Remove link **&gt; **OK**.</span></span>

    -   <span data-ttu-id="d21f5-117">Para vincular o computador a um novo usuário, na lista **Todos os usuários**, selecione um usuário.</span><span class="sxs-lookup"><span data-stu-id="d21f5-117">To link the PC to a new user, in the **All users** list, select a user.</span></span> <span data-ttu-id="d21f5-118">Confirme se os dados do usuário estão corretos e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-118">Confirm that the user data is correct, and then choose **OK**.</span></span>

> [!TIP]
> <span data-ttu-id="d21f5-119">Se você desejar restringir a capacidade dos usuários finais de se vincularem a computadores, habilite a opção **Restringir a capacidade dos usuários de se vincularem a computadores** na política **Configurações do Agente do Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="d21f5-119">If you want to restrict end users ability to link themselves to PCs, enable the option **Restrict users' ability to link themselves to PCs** in the **Microsoft Intune Agent Settings** policy.</span></span>

### <span data-ttu-id="d21f5-120">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d21f5-120">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="d21f5-121">Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="d21f5-121">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)