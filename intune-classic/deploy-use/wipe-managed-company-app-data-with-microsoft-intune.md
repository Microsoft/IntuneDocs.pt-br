---
title: Apagar dados de aplicativos de empresa gerenciados
description: "Saiba como você pode remover seletivamente os dados da empresa de dispositivos remotamente."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7025bdd5d89e52f1c99f9cd834232daf324f3285
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="61dad-103">Apagar dados de aplicativo da empresa com o Intune MAM</span><span class="sxs-lookup"><span data-stu-id="61dad-103">Wipe company app data with Intune MAM</span></span>
<a id="wipe-company-app-data-with-intune-mam" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="61dad-104">Quando um dispositivo é perdido ou roubado ou quando um funcionário sai da empresa, você quer ter certeza de que os dados dos aplicativos da empresa sejam removidos do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="61dad-104">When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device.</span></span> <span data-ttu-id="61dad-105">No entanto, talvez você não queira remover dados pessoais do dispositivo, principalmente quando se trata de um dispositivo que pertence a um funcionário.</span><span class="sxs-lookup"><span data-stu-id="61dad-105">But you might not want to remove personal data on the device, especially if this is an employee-owned device.</span></span>

<span data-ttu-id="61dad-106">Para remover seletivamente os dados de aplicativo da empresa, crie uma solicitação de apagamento usando as etapas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="61dad-106">To selectively remove company app data, create a wipe request by using the steps in this topic.</span></span> <span data-ttu-id="61dad-107">Após a solicitação ser concluída, na próxima vez que o aplicativo for executado no dispositivo, os dados da empresa serão removidos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="61dad-107">After the request is finished, the next time the app runs on the device, company data is removed from the app.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="61dad-108">Contatos sincronizados diretamente do aplicativo para o catálogo de endereços nativos são removidos.</span><span class="sxs-lookup"><span data-stu-id="61dad-108">Contacts synced directly from the app to the native address book are removed.</span></span> <span data-ttu-id="61dad-109">Todos os contatos sincronizados do catálogo de endereços nativos com outra fonte externa não podem ser apagados.</span><span class="sxs-lookup"><span data-stu-id="61dad-109">Any contacts synced from the native address book to another external source cannot be wiped.</span></span> <span data-ttu-id="61dad-110">Atualmente, isso se aplica somente ao aplicativo Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="61dad-110">Currently, this only applies to the Microsoft Outlook app.</span></span>

## <span data-ttu-id="61dad-111">Criar uma solicitação de apagamento</span><span class="sxs-lookup"><span data-stu-id="61dad-111">Create a wipe request</span></span>
<a id="create-a-wipe-request" class="xliff"></a>

1.  <span data-ttu-id="61dad-112">Entre no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="61dad-112">Sign in to the [Azure portal](https://portal.azure.com).</span></span>

2.  <span data-ttu-id="61dad-113">Escolha **Mais Serviços**, digite **Intune** na caixa de texto de filtro e selecione **Proteção de Aplicativo do Intune**.</span><span class="sxs-lookup"><span data-stu-id="61dad-113">Choose **More Services**, type **Intune** in the filter textbox, and select **Intune App Protection**.</span></span> <span data-ttu-id="61dad-114">A folha de Gerenciamento de aplicativos móveis do Intune é aberta.</span><span class="sxs-lookup"><span data-stu-id="61dad-114">The Intune mobile application management blade opens.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  <span data-ttu-id="61dad-116">Na folha **Configurações**, escolha **Solicitações de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-116">On the **Settings** blade, choose **Wipe requests**.</span></span>

3.  <span data-ttu-id="61dad-117">Escolha **Nova solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-117">Choose  **New wipe request**.</span></span> <span data-ttu-id="61dad-118">A folha **Nova solicitação de apagamento** é aberta.</span><span class="sxs-lookup"><span data-stu-id="61dad-118">The **New wipe request** blade opens.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  <span data-ttu-id="61dad-120">Escolha **Usuário** para abrir a folha **Usuário** e selecione o usuário cujos dados de aplicativo você deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="61dad-120">Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.</span></span>

5.  <span data-ttu-id="61dad-121">Escolha **Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="61dad-121">Choose **Device**.</span></span> <span data-ttu-id="61dad-122">Isso abre a folha **Dispositivo** que lista todos os dispositivos associados ao usuário selecionado e também fornece duas colunas, o nome do dispositivo, que é um nome amigável definido pelo usuário, e o tipo e a plataforma do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="61dad-122">This opens the **Device** blade that lists all the devices associated with the selected user, and also provides two columns, the device name, which is a friendly name defined by the user, and the device type, its device platform.</span></span> <span data-ttu-id="61dad-123">Selecione o dispositivo que deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="61dad-123">Select the device you want to wipe.</span></span>

6.  <span data-ttu-id="61dad-124">Você está de volta na folha **Nova solicitação para apagar**.</span><span class="sxs-lookup"><span data-stu-id="61dad-124">You are now back on the **New wipe request** blade.</span></span> <span data-ttu-id="61dad-125">Escolha **OK** para fazer uma solicitação de apagamento.</span><span class="sxs-lookup"><span data-stu-id="61dad-125">Choose **Ok** to make a wipe request.</span></span> 

<span data-ttu-id="61dad-126">O serviço cria e controla uma solicitação de apagamento separada para cada aplicativo protegido no dispositivo e o usuário associado à solicitação de apagamento.</span><span class="sxs-lookup"><span data-stu-id="61dad-126">The service creates and tracks a separate wipe request for each protected app on the device, and the user associated with the wipe request.</span></span>

>[!NOTE]
> <span data-ttu-id="61dad-127">Você também pode criar **Solicitações de apagamento** clicando no **bloco de Solicitação de apagamento** da folha de gerenciamento de aplicativos móveis do Intune.</span><span class="sxs-lookup"><span data-stu-id="61dad-127">You can also create **Wipe requests** by clicking on the **Wipe request tile** from the Intune mobile application management blade.</span></span>

## <span data-ttu-id="61dad-128">Monitorar suas solicitações de apagamento</span><span class="sxs-lookup"><span data-stu-id="61dad-128">Monitor your wipe requests</span></span>
<a id="monitor-your-wipe-requests" class="xliff"></a>

<span data-ttu-id="61dad-129">É possível obter um relatório resumido que mostra o status geral da solicitação de apagamento e inclui o número de falhas e solicitações pendentes.</span><span class="sxs-lookup"><span data-stu-id="61dad-129">You can have a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures.</span></span> <span data-ttu-id="61dad-130">Para obter mais detalhes, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="61dad-130">To get more details, follow these steps:</span></span>

1.  <span data-ttu-id="61dad-131">Na folha Gerenciamento de aplicativos móveis do Intune, clique no bloco **Solicitações de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-131">On the Intune mobile application management blade, click on the **Wipe requests** tile.</span></span>

2.  <span data-ttu-id="61dad-132">Na folha **Solicitação de apagamento**, escolha o bloco **Solicitação de apagamento** para abrir a folha **Solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-132">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

3.  <span data-ttu-id="61dad-133">Na folha **Solicitação de apagamento**, você pode ver a lista de suas solicitações agrupadas por usuário.</span><span class="sxs-lookup"><span data-stu-id="61dad-133">On the **Wipe request** blade, you can see the list of your requests grouped by users.</span></span> <span data-ttu-id="61dad-134">Como o sistema cria uma solicitação de apagamento para cada aplicativo protegido em execução no dispositivo, você poderá ver várias solicitações de um usuário.</span><span class="sxs-lookup"><span data-stu-id="61dad-134">Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user.</span></span> <span data-ttu-id="61dad-135">O status indica se uma solicitação de apagamento está **pendente**, com **falha**ou **bem-sucedida**.</span><span class="sxs-lookup"><span data-stu-id="61dad-135">The status indicates whether a wipe request is **pending**, **failed**, or **successful**.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/wipe-request-status-1.png)

<span data-ttu-id="61dad-137">Além disso, você poderá ver o nome e o tipo de dispositivo, o que pode ser útil ao ler os relatórios.</span><span class="sxs-lookup"><span data-stu-id="61dad-137">Additionally, you'll be able to see the device name, and its device type, which can be helpful when reading the reports.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="61dad-138">O usuário deve abrir o aplicativo para que o apagamento ocorra, e ele pode durar até 30 minutos após a criação da solicitação.</span><span class="sxs-lookup"><span data-stu-id="61dad-138">The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.</span></span>

## <span data-ttu-id="61dad-139">Excluir uma solicitação de apagamento</span><span class="sxs-lookup"><span data-stu-id="61dad-139">Delete a wipe request</span></span>
<a id="delete-a-wipe-request" class="xliff"></a>

<span data-ttu-id="61dad-140">Apagamentos com status pendente são exibidos até serem excluídos manualmente.</span><span class="sxs-lookup"><span data-stu-id="61dad-140">Wipes with pending status are displayed until you manually delete them.</span></span>  <span data-ttu-id="61dad-141">Para excluir uma solicitação de apagamento manualmente</span><span class="sxs-lookup"><span data-stu-id="61dad-141">To manually delete a wipe request</span></span>

1.  <span data-ttu-id="61dad-142">Na folha Gerenciamento de aplicativos móveis do Intune, clique no bloco **Solicitações de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-142">On the Intune mobile application management blade, click on the **Wipe requests** tile.</span></span>

2.  <span data-ttu-id="61dad-143">Na folha **Solicitação de apagamento**, escolha o bloco **Solicitação de apagamento** para abrir a folha **Solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-143">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

3.  <span data-ttu-id="61dad-144">Clique com o botão direito do mouse na solicitação de apagamento que você deseja excluir e escolha **Excluir solicitação de apagamento**.</span><span class="sxs-lookup"><span data-stu-id="61dad-144">Right-click on the wipe request you want to delete, then choose **Delete wipe request**.</span></span>

    ![Captura de tela da folha Nova solicitação para apagar](../media/AppManagement/delete-wipe-request.png)

4.  <span data-ttu-id="61dad-146">Será solicitado que você confirme a exclusão, escolha **Sim** ou **Não** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="61dad-146">You're prompted to confirm the deletion, choose **Yes** or **No**, then click **OK**.</span></span>


### <span data-ttu-id="61dad-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="61dad-147">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="61dad-148">Proteger dados de aplicativo usando políticas de gerenciamento de aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="61dad-148">Protect app data using mobile app management policies </span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="61dad-149">Usando o Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="61dad-149">Using the Azure portal</span></span>](azure-portal-for-microsoft-intune-mam-policies.md)
