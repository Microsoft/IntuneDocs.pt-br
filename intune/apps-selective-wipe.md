---
title: Como apagar apenas dados corporativos de aplicativos
titleSuffix: Intune on Azure
description: Saiba como apagar aplicativos seletivamente com o Microsoft Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bfebc391997ac4e63466eb3a09044318cf807dbc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="59ebd-103">Como apagar somente dados corporativos de aplicativos gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="59ebd-103">How to wipe only corporate data from Intune-managed apps</span></span>
<a id="how-to-wipe-only-corporate-data-from-intune-managed-apps" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="59ebd-104">Quando um dispositivo é perdido ou roubado ou quando um funcionário sai da empresa, você quer ter certeza de que os dados dos aplicativos da empresa sejam removidos do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59ebd-104">When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device.</span></span> <span data-ttu-id="59ebd-105">No entanto, talvez você não queira remover dados pessoais do dispositivo, principalmente quando se trata de um dispositivo que pertence a um funcionário.</span><span class="sxs-lookup"><span data-stu-id="59ebd-105">But you might not want to remove personal data on the device, especially if this is an employee-owned device.</span></span>

<span data-ttu-id="59ebd-106">Para remover seletivamente os dados de aplicativo da empresa, crie uma solicitação de apagamento usando as etapas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="59ebd-106">To selectively remove company app data, create a wipe request by using the steps in this topic.</span></span> <span data-ttu-id="59ebd-107">Após a solicitação ser concluída, na próxima vez que o aplicativo for executado no dispositivo, os dados da empresa serão removidos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59ebd-107">After the request is finished, the next time the app runs on the device, company data is removed from the app.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="59ebd-108">Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.</span><span class="sxs-lookup"><span data-stu-id="59ebd-108">Contacts synced directly from the app to the native address book are removed.</span></span> <span data-ttu-id="59ebd-109">Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados.</span><span class="sxs-lookup"><span data-stu-id="59ebd-109">Any contacts synced from the native address book to another external source cannot be wiped.</span></span> <span data-ttu-id="59ebd-110">Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="59ebd-110">Currently, this only applies to the Microsoft Outlook app.</span></span>

## <span data-ttu-id="59ebd-111">Criar uma solicitação de apagamento</span><span class="sxs-lookup"><span data-stu-id="59ebd-111">Create a wipe request</span></span>
<a id="create-a-wipe-request" class="xliff"></a>

1.  <span data-ttu-id="59ebd-112">Entre no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="59ebd-112">Sign in to the [Azure portal](https://portal.azure.com).</span></span>

2.  <span data-ttu-id="59ebd-113">Escolha **Mais Serviços**, digite **Intune** na caixa de texto de filtro e selecione **Intune**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-113">Choose **More Services**, type **Intune** in the filter textbox, and select **Intune**.</span></span> <span data-ttu-id="59ebd-114">A folha do Intune é aberta. Escolha a folha **Gerenciar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-114">The Intune blade opens, choose the **Manage apps** blade.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](./media/intune-azure-preview-blade.png)

3.  <span data-ttu-id="59ebd-116">Na **folha Aplicativos Móveis**, escolha **Nova solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-116">On the **Mobile Apps blade**, choose **New wipe request**.</span></span> <span data-ttu-id="59ebd-117">A folha **Nova solicitação de apagamento** é aberta.</span><span class="sxs-lookup"><span data-stu-id="59ebd-117">The **New wipe request** blade opens.</span></span>

4.  <span data-ttu-id="59ebd-118">Escolha **Nova solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-118">Choose  **New wipe request**.</span></span> <span data-ttu-id="59ebd-119">A folha **Nova solicitação de apagamento** é aberta.</span><span class="sxs-lookup"><span data-stu-id="59ebd-119">The **New wipe request** blade opens.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  <span data-ttu-id="59ebd-121">Escolha **Usuário** para abrir a folha **Usuário** e selecione o usuário cujos dados de aplicativo você deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="59ebd-121">Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.</span></span>

6.  <span data-ttu-id="59ebd-122">Escolha **Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-122">Choose **Device**.</span></span> <span data-ttu-id="59ebd-123">Isso abre a folha **Dispositivo** que lista todos os dispositivos associados ao usuário selecionado e também fornece duas colunas, o nome do dispositivo, que é um nome amigável definido pelo usuário, e o tipo e a plataforma do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="59ebd-123">This opens the **Device** blade that lists all the devices associated with the selected user, and also provides two columns, the device name, which is a friendly name defined by the user, and the device type, its device platform.</span></span> <span data-ttu-id="59ebd-124">Selecione o dispositivo que deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="59ebd-124">Select the device you want to wipe.</span></span>

7.  <span data-ttu-id="59ebd-125">Você está de volta na folha **Nova solicitação para apagar**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-125">You are now back on the **New wipe request** blade.</span></span> <span data-ttu-id="59ebd-126">Escolha **OK** para fazer uma solicitação de apagamento.</span><span class="sxs-lookup"><span data-stu-id="59ebd-126">Choose **Ok** to make a wipe request.</span></span> 

<span data-ttu-id="59ebd-127">O serviço cria e controla uma solicitação de apagamento separada para cada aplicativo protegido no dispositivo e o usuário associado à solicitação de apagamento.</span><span class="sxs-lookup"><span data-stu-id="59ebd-127">The service creates and tracks a separate wipe request for each protected app on the device, and the user associated with the wipe request.</span></span>

## <span data-ttu-id="59ebd-128">Monitorar suas solicitações de apagamento</span><span class="sxs-lookup"><span data-stu-id="59ebd-128">Monitor your wipe requests</span></span>
<a id="monitor-your-wipe-requests" class="xliff"></a>

<span data-ttu-id="59ebd-129">É possível obter um relatório resumido que mostra o status geral da solicitação de apagamento e inclui o número de falhas e solicitações pendentes.</span><span class="sxs-lookup"><span data-stu-id="59ebd-129">You can have a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures.</span></span> <span data-ttu-id="59ebd-130">Para obter mais detalhes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="59ebd-130">To get more details, follow these steps:</span></span>

1.  <span data-ttu-id="59ebd-131">Na folha **Aplicativos Móveis – Apagamento Seletivo de Aplicativo**, você pode ver a lista de suas solicitações agrupadas por usuários.</span><span class="sxs-lookup"><span data-stu-id="59ebd-131">On the **Mobile Apps - App Selective Wipe blade** blade, you can see the list of your requests grouped by users.</span></span> <span data-ttu-id="59ebd-132">Como o sistema cria uma solicitação de apagamento para cada aplicativo protegido em execução no dispositivo, você poderá ver várias solicitações de um usuário.</span><span class="sxs-lookup"><span data-stu-id="59ebd-132">Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user.</span></span> <span data-ttu-id="59ebd-133">O status indica se uma solicitação de apagamento está **pendente**, com **falha**ou **bem-sucedida**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-133">The status indicates whether a wipe request is **pending**, **failed**, or **successful**.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](./media/wipe-request-status-1.png)

<span data-ttu-id="59ebd-135">Além disso, você poderá ver o nome e o tipo de dispositivo, o que pode ser útil ao ler os relatórios.</span><span class="sxs-lookup"><span data-stu-id="59ebd-135">Additionally, you'll be able to see the device name, and its device type, which can be helpful when reading the reports.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="59ebd-136">O usuário deve abrir o aplicativo para que o apagamento ocorra, e ele pode durar até 30 minutos após a criação da solicitação.</span><span class="sxs-lookup"><span data-stu-id="59ebd-136">The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.</span></span>

## <span data-ttu-id="59ebd-137">Excluir uma solicitação de apagamento</span><span class="sxs-lookup"><span data-stu-id="59ebd-137">Delete a wipe request</span></span>
<a id="delete-a-wipe-request" class="xliff"></a>

<span data-ttu-id="59ebd-138">Apagamentos com status pendente são exibidos até serem excluídos manualmente.</span><span class="sxs-lookup"><span data-stu-id="59ebd-138">Wipes with pending status are displayed until you manually delete them.</span></span>  <span data-ttu-id="59ebd-139">Para excluir uma solicitação de apagamento manualmente:</span><span class="sxs-lookup"><span data-stu-id="59ebd-139">To manually delete a wipe request:</span></span>

1.  <span data-ttu-id="59ebd-140">Na folha **Solicitação de apagamento**, escolha o bloco **Solicitação de apagamento** para abrir a folha **Solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-140">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

2.  <span data-ttu-id="59ebd-141">Clique com o botão direito do mouse na solicitação de apagamento que você deseja excluir e escolha **Excluir solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-141">Right-click on the wipe request you want to delete, then choose **Delete wipe request**.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](./media/delete-wipe-request.png)

3.  <span data-ttu-id="59ebd-143">Será solicitado que você confirme a exclusão, escolha **Sim** ou **Não** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="59ebd-143">You're prompted to confirm the deletion, choose **Yes** or **No**, then click **OK**.</span></span>

### <span data-ttu-id="59ebd-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="59ebd-144">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="59ebd-145">O que é política de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="59ebd-145">What's app protection policy</span></span>](app-protection-policy.md)

[<span data-ttu-id="59ebd-146">O que é gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="59ebd-146">What's app management</span></span>](app-management.md)