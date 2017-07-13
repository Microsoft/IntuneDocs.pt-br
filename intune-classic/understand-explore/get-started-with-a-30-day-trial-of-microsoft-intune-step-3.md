---
title: "Criar grupos para organizar usuários e dispositivos na avaliação gratuita"
description: "Como criar grupos de dispositivos e grupos de usuários ao se inscrever para uma avaliação gratuita de 30 dias do Microsoft Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 084cc155a64a58582e3008df10e86c1e5266054d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="11053-103">Criar grupos para organizar usuários e dispositivos de assinatura de avaliação</span><span class="sxs-lookup"><span data-stu-id="11053-103">Create groups to organize evaluation subscription users and devices</span></span>
<a id="create-groups-to-organize-evaluation-subscription-users-and-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="11053-104">Os grupos no Intune oferecem grande flexibilidade para o gerenciamento de dispositivos e usuários.</span><span class="sxs-lookup"><span data-stu-id="11053-104">Groups in Intune give you great flexibility for managing your devices and users.</span></span> <span data-ttu-id="11053-105">Você pode configurar grupos para atender as suas necessidades organizacionais (por exemplo, por localização geográfica, departamento ou características de hardware) e usá-los para executar diversas tarefas administrativas em escala, da definição de políticas para um conjunto de usuários à implantação de aplicativos para um conjunto de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="11053-105">You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a variety of administrative tasks at scale, from setting policies for a set of users to deploying applications to a set of devices.</span></span>

## <span data-ttu-id="11053-106">Criar um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="11053-106">Create a device group</span></span>
<a id="create-a-device-group" class="xliff"></a>
<span data-ttu-id="11053-107">Use grupos de dispositivos para implantar software e atualizações e configurar políticas de Configurações do Agente do Microsoft Intune e Configurações do Firewall do Windows.</span><span class="sxs-lookup"><span data-stu-id="11053-107">Use device groups to deploy software and updates, and configure Microsoft Intune Agent Settings and Windows Firewall Settings policies.</span></span> <span data-ttu-id="11053-108">Por exemplo, configure um grupo "Meus Dispositivos de Avaliação" usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="11053-108">For example, set up a "My Trial Devices" group using the following steps:</span></span>

1.  <span data-ttu-id="11053-109">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="11053-109">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **Overview** &gt; **Create Group**.</span></span>

2.  <span data-ttu-id="11053-110">Em **Nome do grupo**, digite “Meus Dispositivos de Avaliação”, na lista de grupos pai, selecione **Todos os Dispositivos** e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="11053-110">For the **Group name**, type “My Trial Devices” and, from the parent group list, select **All Devices**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="11053-111">Na página **Definir critérios de associação** , selecione **Todos os dispositivos** , para indicar que o grupo inclui tanto dispositivos móveis quanto computadores.</span><span class="sxs-lookup"><span data-stu-id="11053-111">On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.</span></span>

4.  <span data-ttu-id="11053-112">Na página **Definir Associação Direta**, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="11053-112">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="11053-113">Caso você tenha criado anteriormente um grupo que não incluiu todos os dispositivos e deseje adicionar dispositivos específicos ao seu novo grupo, você pode fazer isso aqui.</span><span class="sxs-lookup"><span data-stu-id="11053-113">If you previously created a group that does not include all devices, and you wanted to add specific devices to your new group, you can do that here.</span></span>

5.  <span data-ttu-id="11053-114">Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="11053-114">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="11053-115">O grupo recém-criado pode ser encontrado na lista **Grupos** , no espaço de trabalho **Grupos** em **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="11053-115">You can find the newly created group in the **Groups** list, in the **Groups** workspace under **All Devices**.</span></span> <span data-ttu-id="11053-116">Nesse local, também é possível editar ou excluir o grupo.</span><span class="sxs-lookup"><span data-stu-id="11053-116">From here, you can also edit or delete the group.</span></span>

## <span data-ttu-id="11053-117">Criar um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="11053-117">Create a user group</span></span>
<a id="create-a-user-group" class="xliff"></a>
<span data-ttu-id="11053-118">Use grupos de usuários para implantar políticas de dispositivo e software.</span><span class="sxs-lookup"><span data-stu-id="11053-118">Use user groups to deploy software and device policies.</span></span> <span data-ttu-id="11053-119">Por exemplo, configure um grupo "Meus Usuários de Avaliação" usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="11053-119">For example, set up a "My Trial Users" group using the following steps:</span></span>

1.  <span data-ttu-id="11053-120">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="11053-120">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **Overview** &gt; **Create Group**.</span></span>

2.  <span data-ttu-id="11053-121">Em **Nome do grupo**, digite “Meus Usuários de Avaliação” e, na lista de grupos pai, selecione **Todos os usuários** e, em seguida, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="11053-121">For the **Group name**, type “My Trial Users” and, from the parent group list, select **All Users**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="11053-122">Na página **Definir Critérios de Associação** , defina **Iniciar associação de grupo com** como **Todos os usuários no grupo Pai**.</span><span class="sxs-lookup"><span data-stu-id="11053-122">On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.</span></span>

4.  <span data-ttu-id="11053-123">Ao lado de **Excluir membros destes grupos de segurança**, escolha **Procurar** e, em seguida, selecione **Administrador da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="11053-123">Beside **Exclude members from these security groups**, choose **Browse** and then select **Company Administrator**.</span></span> <span data-ttu-id="11053-124">Essa exclusão permitirá gerenciar o grupo Meus Usuários de Avaliação sem afetar a conta de Administrador da Empresa (também conhecida como administrador de locatários).</span><span class="sxs-lookup"><span data-stu-id="11053-124">This exclusion lets you manage the My Trial Users group without affecting the Company Administrator account (also known as the tenant administrator).</span></span>

5.  <span data-ttu-id="11053-125">Na página **Definir Associação Direta**, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="11053-125">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="11053-126">Você não precisa fazer nada aqui porque deseja que o grupo Meus usuários de avaliação inclua todos os usuários, exceto o Administrador da empresa.</span><span class="sxs-lookup"><span data-stu-id="11053-126">You don’t need to do anything here because you want the My Trial Users group to include all users, except for the Company Administrator.</span></span>

6.  <span data-ttu-id="11053-127">Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="11053-127">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="11053-128">O grupo recém-criado pode ser encontrado na lista **Grupos** , no espaço de trabalho **Grupos** em **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="11053-128">You can find the newly created group in the **Groups** list, in the **Groups** workspace under **All Users**.</span></span> <span data-ttu-id="11053-129">Nesse local, também é possível editar ou excluir o grupo.</span><span class="sxs-lookup"><span data-stu-id="11053-129">From here, you can also edit or delete the group.</span></span>

<span data-ttu-id="11053-130">Para saber mais sobre como usar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](/intune-classic/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="11053-130">To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/intune-classic/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>

## <span data-ttu-id="11053-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="11053-131">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="11053-132">Criar políticas</span><span class="sxs-lookup"><span data-stu-id="11053-132">Create policies</span></span>](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  
