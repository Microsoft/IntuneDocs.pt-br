---
title: "Solicitar e fornecer assistência remota para computadores Windows"
description: "Descreve as etapas administrativas do usuário final e do administrador de TI para fornecer assistência remota para áreas de trabalho do Windows gerenciadas como computadores e iniciar um computador remotamente."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3d173cf9a9ec8617cb7feec858b696aa0e80c12d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3ee89-103">Solicitar e fornecer assistência remota para computadores Windows</span><span class="sxs-lookup"><span data-stu-id="3ee89-103">Request and provide remote assistance for Windows PCs</span></span>
<a id="request-and-provide-remote-assistance-for-windows-pcs" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


<span data-ttu-id="3ee89-104">As informações descritas neste tópico se aplicam somente a áreas de trabalho do Windows que estão sendo gerenciadas como computadores por meio do cliente de software do Intune.</span><span class="sxs-lookup"><span data-stu-id="3ee89-104">The information in this topic applies only to Windows desktops that you are managing as PCs by using the Intune software client.</span></span>

<span data-ttu-id="3ee89-105">O Intune pode usar o software [TeamViewer](https://www.teamviewer.com), adquirido separadamente, para permitir que você dê assistência remota para os usuários que executam o cliente de software do Intune.</span><span class="sxs-lookup"><span data-stu-id="3ee89-105">Intune can use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running the Intune software client.</span></span> <span data-ttu-id="3ee89-106">Quando um usuário solicita ajuda do Microsoft Intune Center, você será informado por um alerta, pode aceitar a solicitação e, em seguida, fornecer assistência.</span><span class="sxs-lookup"><span data-stu-id="3ee89-106">When a user requests help from the Microsoft Intune Center, you are informed by an alert, can accept the request, and then provide assistance.</span></span> <span data-ttu-id="3ee89-107">Esta funcionalidade substitui a funcionalidade de Assistência Remota do Windows existente no Intune.</span><span class="sxs-lookup"><span data-stu-id="3ee89-107">This functionality replaces the existing Windows Remote Assistance functionality in Intune.</span></span>


## <span data-ttu-id="3ee89-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3ee89-108">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="3ee89-109">Antes de começar a estabelecer e responder às solicitações de assistência remota, verifique se os seguintes pré-requisitos estão em vigor:</span><span class="sxs-lookup"><span data-stu-id="3ee89-109">Before you begin to establish and to respond to remote assistance requests, ensure that the following prerequisites are in place:</span></span>

- <span data-ttu-id="3ee89-110">Você deve ter se [inscrito para uma conta do TeamViewer](https://login.teamviewer.com/LogOn#register) fazer logon no site do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="3ee89-110">You must have [signed up for a TeamViewer account](https://login.teamviewer.com/LogOn#register) to log in to the TeamViewer website.</span></span>
- <span data-ttu-id="3ee89-111">Os computadores Windows que você deseja administrar devem ser [gerenciados pelo cliente de software do Windows](manage-windows-pcs-with-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="3ee89-111">Windows PCs that you want to administer must be [managed by the Windows software client](manage-windows-pcs-with-microsoft-intune.md)</span></span>
- <span data-ttu-id="3ee89-112">Todos os sistemas operacionais de computador Windows com suporte pelo Intune podem ser administrados.</span><span class="sxs-lookup"><span data-stu-id="3ee89-112">All Windows PC operating systems supported by Intune can be administered.</span></span>

## <span data-ttu-id="3ee89-113">Configure o TeamViewer Connector</span><span class="sxs-lookup"><span data-stu-id="3ee89-113">Configure the TeamViewer Connector</span></span>
<a id="configure-the-teamviewer-connector" class="xliff"></a>

1. <span data-ttu-id="3ee89-114">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-114">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
2. <span data-ttu-id="3ee89-115">No espaço de trabalho **Administrador**, escolha **TeamViewer**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-115">In the **Admin** workspace, choose **TeamViewer**.</span></span>
3. <span data-ttu-id="3ee89-116">Na página **TeamViewer** em **TeamViewer Connector**, escolha **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-116">On the **TeamViewer** page, under **TeamViewer Connector**, choose **Enable**.</span></span>
4. <span data-ttu-id="3ee89-117">Na caixa de diálogo **Habilitar TeamViewer**, exiba e, em seguida, **Aceite** os termos de licença.</span><span class="sxs-lookup"><span data-stu-id="3ee89-117">In the **Enable TeamViewer** dialog box, view, then **Accept** the license terms.</span></span> <span data-ttu-id="3ee89-118">Se você ainda não tem uma licença do TeamViewer, escolha **Comprar uma licença do TeamViewer**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-118">If you don't already own a TeamViewer license, choose **Purchase a TeamViewer license**.</span></span>
5. <span data-ttu-id="3ee89-119">Depois que a janela do navegador do TeamViewer for aberta, entre no site com suas credenciais do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="3ee89-119">After the TeamViewer browser window opens, sign into the site with your TeamViewer credentials.</span></span>
6. <span data-ttu-id="3ee89-120">No site do TeamViewer, leia e aceite as opções para permitir que o Intune se conecte com o TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="3ee89-120">On the TeamViewer site, read, then accept the options to allow Intune to connect with TeamViewer.</span></span>
7. <span data-ttu-id="3ee89-121">No console do Intune, verifique se o item **TeamViewer Connector** é mostrado como **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-121">In the Intune console, verify that the **TeamViewer Connector** item shows as **Enabled**.</span></span>


## <span data-ttu-id="3ee89-122">Abrir uma solicitação de assistência remota (usuário final)</span><span class="sxs-lookup"><span data-stu-id="3ee89-122">Open a remote assistance request (end user)</span></span>
<a id="open-a-remote-assistance-request-end-user" class="xliff"></a>

1. <span data-ttu-id="3ee89-123">Em um cliente de computador Windows, abra o **Microsoft Intune Center**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-123">On a client Windows PC, open the **Microsoft Intune Center**.</span></span>
2. <span data-ttu-id="3ee89-124">Em **Assistência Remota**, escolha **Solicitar Assistência Remota**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-124">Under **Remote Assistance**, choose **Request Remote Assistance**.</span></span>
3. <span data-ttu-id="3ee89-125">Depois de aprovar a solicitação (veja abaixo), o TeamViewer abrirá no cliente.</span><span class="sxs-lookup"><span data-stu-id="3ee89-125">After you approve the request (see below), TeamViewer opens on the client.</span></span> <span data-ttu-id="3ee89-126">O usuário deve aceitar quaisquer mensagens indicando que o navegador da Web está tentando abrir o aplicativo TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="3ee89-126">The user must accept any messages indicating that the web browser is trying to open the TeamViewer application.</span></span>
4. <span data-ttu-id="3ee89-127">O usuário vê uma mensagem perguntando se você pode controlar o seu computador.</span><span class="sxs-lookup"><span data-stu-id="3ee89-127">The user sees a message asking if you can control their PC.</span></span> <span data-ttu-id="3ee89-128">Eles devem aceitar esta mensagem para continuar.</span><span class="sxs-lookup"><span data-stu-id="3ee89-128">They must accept this message to continue.</span></span>
5. <span data-ttu-id="3ee89-129">Durante a sessão de assistência remota, o usuário vê uma janela que mostra a eles que estão conectados.</span><span class="sxs-lookup"><span data-stu-id="3ee89-129">During the remote assistance session, the user sees a window that shows them you are connected.</span></span> <span data-ttu-id="3ee89-130">Se eles fecharem esta janela, a sessão remota será encerrada.</span><span class="sxs-lookup"><span data-stu-id="3ee89-130">If they close this window, the remote session ends.</span></span>

## <span data-ttu-id="3ee89-131">Responder a uma solicitação de assistência remota</span><span class="sxs-lookup"><span data-stu-id="3ee89-131">Respond to a remote assistance request</span></span>
<a id="respond-to-a-remote-assistance-request" class="xliff"></a>

1. <span data-ttu-id="3ee89-132">Quando um usuário envia uma solicitação de assistência remota, você poderá exibi-la no espaço de trabalho **Alertas**, em **Monitoramento** > **Assistência Remota**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-132">When a user submits a remote assistance request, you can view it in the **Alerts** workspace, under **Monitoring** > **Remote Assistance**.</span></span> <span data-ttu-id="3ee89-133">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3ee89-133">For example:</span></span>
> ![Captura de tela de uma solicitação de assistência remota](./media/team-viewer.png)

<br><span data-ttu-id="3ee89-135">Se uma solicitação não for atendida por mais de 4 horas, ela será removida.</span><span class="sxs-lookup"><span data-stu-id="3ee89-135">If a request goes unanswered for more than 4 hours, it is removed.</span></span>
2. <span data-ttu-id="3ee89-136">Para aceitar a solicitação, escolha **Aprovar solicitação e iniciar Assistência Remota**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-136">To accept the request, choose **Approve request and launch Remote Assistance**.</span></span>
3. <span data-ttu-id="3ee89-137">Na caixa de diálogo **Uma nova solicitação de assistência remota está pendente**, escolha **Aceitar a solicitação de assistência remota**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-137">In the **A New Remote Assistance Request is Pending** dialog box, choose **Accept the remote assistance request**.</span></span> <span data-ttu-id="3ee89-138">Se ele ainda não estiver instalado, o TeamViewer instalará todos os aplicativos necessários no computador.</span><span class="sxs-lookup"><span data-stu-id="3ee89-138">If it's not already installed, TeamViewer will install any necessary apps on your PC.</span></span>
4. <span data-ttu-id="3ee89-139">O TeamViewer notifica o usuário final que você deseja assumir o controle do seu computador.</span><span class="sxs-lookup"><span data-stu-id="3ee89-139">TeamViewer then notifies the end user that you want to take control of their PC.</span></span> <span data-ttu-id="3ee89-140">Depois que o usuário aceitar a solicitação, uma janela do TeamViewer será aberta e você poderá controlar o computador.</span><span class="sxs-lookup"><span data-stu-id="3ee89-140">After the user has accepted the request, the TeamViewer windows opens, and you can control the PC.</span></span>

<span data-ttu-id="3ee89-141">Durante uma sessão de assistência remota, você poderá usar todos os comandos disponíveis do TeamViewer para controlar o computador remoto.</span><span class="sxs-lookup"><span data-stu-id="3ee89-141">While in a remote assistance session, you can use all available TeamViewer commands to control the remote PC.</span></span> <span data-ttu-id="3ee89-142">Para obter ajuda com esses comandos, baixe o [Manual for remote control](http://www.teamviewer.com/en/support/documents/) (Manual para controle remoto) do site do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="3ee89-142">For help with these commands, download the [Manual for remote control](http://www.teamviewer.com/en/support/documents/) from the TeamViewer website.</span></span>

## <span data-ttu-id="3ee89-143">Feche a sessão de assistência remota</span><span class="sxs-lookup"><span data-stu-id="3ee89-143">Close the remote assistance session</span></span>
<a id="close-the-remote-assistance-session" class="xliff"></a>

<span data-ttu-id="3ee89-144">Do menu **Ações** da janela **TeamViewer**, escolha **Encerrar a Sessão**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-144">From the **Actions** menu of the **TeamViewer** window, choose **End Session**.</span></span>

## <span data-ttu-id="3ee89-145">Reiniciar remotamente um computador Windows</span><span class="sxs-lookup"><span data-stu-id="3ee89-145">Remotely restart a Windows PC</span></span>
<a id="remotely-restart-a-windows-pc" class="xliff"></a>
<span data-ttu-id="3ee89-146">Ao ajudar os usuários com problemas, talvez seja necessário reiniciar remotamente os computadores de tempos em tempos.</span><span class="sxs-lookup"><span data-stu-id="3ee89-146">When helping your users with issues, you might need to remotely restart their PC from time to time.</span></span> <span data-ttu-id="3ee89-147">Use as etapas a seguir para reiniciar remotamente um computador Windows.</span><span class="sxs-lookup"><span data-stu-id="3ee89-147">Use the following steps to remotely restart a Windows PC.</span></span>

1.  <span data-ttu-id="3ee89-148">No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contém o computador que você deseja reiniciar).</span><span class="sxs-lookup"><span data-stu-id="3ee89-148">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to restart).</span></span>

2.  <span data-ttu-id="3ee89-149">Selecione um ou mais computadores e escolha **Tarefas Remotas** &gt; **Reiniciar o Computador**.</span><span class="sxs-lookup"><span data-stu-id="3ee89-149">Select one or more PCs, and then choose **Remote Tasks** &gt; **Restart Computer**.</span></span>

3.  <span data-ttu-id="3ee89-150">Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.</span><span class="sxs-lookup"><span data-stu-id="3ee89-150">To view the task status, choose **Remote Tasks** in the bottom right corner of the page.</span></span>

4.  <span data-ttu-id="3ee89-151">Na caixa de diálogo **Status da tarefa** , examine as tarefas remotas atuais, seus status, nome do dispositivo e todos os erros reportados.</span><span class="sxs-lookup"><span data-stu-id="3ee89-151">In the **Task Status** dialog box, review the current remote tasks, task status, device name, and any reported errors.</span></span>

### <span data-ttu-id="3ee89-152">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3ee89-152">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="3ee89-153">Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="3ee89-153">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)