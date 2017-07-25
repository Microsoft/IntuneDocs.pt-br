---
title: "Crie grupos para organizar usuários e dispositivos"
description: "Criar usuários e grupos para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a6e9eb087b730c66bcf32f877fd22f2d3be0c121
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="701ca-103">Crie grupos para organizar usuários e dispositivos</span><span class="sxs-lookup"><span data-stu-id="701ca-103">Create groups to organize users and devices</span></span>
<a id="create-groups-to-organize-users-and-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="701ca-104">Este tópico informa os administradores como eles podem criar grupos de usuários do Intune.</span><span class="sxs-lookup"><span data-stu-id="701ca-104">This topic tells administrators how they can create groups of users in Intune.</span></span>

<span data-ttu-id="701ca-105">Os grupos no Intune oferecem grande flexibilidade para o gerenciamento de dispositivos e usuários.</span><span class="sxs-lookup"><span data-stu-id="701ca-105">Groups in Intune give you great flexibility for managing your devices and users.</span></span> <span data-ttu-id="701ca-106">Você pode configurar grupos para atender às suas necessidades organizacionais (por exemplo, por localização geográfica, departamento ou características de hardware) e usá-los para executar uma variedade de tarefas administrativas, da implantação de políticas para um conjunto de usuários à implantação de aplicativos para um conjunto de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="701ca-106">You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.</span></span>

## <span data-ttu-id="701ca-107">Gerenciamento de grupo migrando para o Azure AD</span><span class="sxs-lookup"><span data-stu-id="701ca-107">Group management moving to Azure AD</span></span>
<a id="group-management-moving-to-azure-ad" class="xliff"></a>

<span data-ttu-id="701ca-108">**A partir de novembro de 2016**, novas contas gerenciarão grupos de usuários e dispositivos no portal do Azure AD (Active Directory).</span><span class="sxs-lookup"><span data-stu-id="701ca-108">**Starting in November 2016**, new accounts will manage user and device groups in the Azure Active Directory (AD) portal.</span></span> <span data-ttu-id="701ca-109">Em dezembro de 2016, a equipe de produtos do Intune iniciará a migração de clientes existentes para a nova experiência de gerenciamento de grupos baseada no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="701ca-109">In December 2016, the Intune product team will begin to migrate existing customers to the new Azure AD-based group management experience.</span></span> <span data-ttu-id="701ca-110">Todos os grupos de dispositivos e usuários serão migrados para grupos de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="701ca-110">All user and device groups will be migrated to Azure AD security groups.</span></span> <span data-ttu-id="701ca-111">Não começaremos as migrações até que possamos minimizar o efeito sobre seu trabalho diário e quando esperarmos que não haja nenhum efeito sobre seus usuários.</span><span class="sxs-lookup"><span data-stu-id="701ca-111">We won’t start migrations until we can minimize any effect on your day-to-day work, and when we expect there will be no effect on your users.</span></span> <span data-ttu-id="701ca-112">Também notificaremos você antes de migrar sua conta.</span><span class="sxs-lookup"><span data-stu-id="701ca-112">We also will give you notice before we migrate your account.</span></span>


>[!IMPORTANT]
>
><span data-ttu-id="701ca-113">Se você abrir o espaço de trabalho Grupos no portal do Intune e vir **Grupos de usuários do Intune agora são gerenciados como grupos no Azure Active Directory** com um link para o portal do Azure Active Directory, então você já está usando a *nova* abordagem de grupos de segurança do Azure AD para o gerenciamento de grupos no Intune.</span><span class="sxs-lookup"><span data-stu-id="701ca-113">If you open the Groups workspace in the Intune portal and see **Intune user groups are now managed as groups in Azure Active Directory** with a link to the Azure Active Directory portal, then you are already using the *new* Azure AD security groups approach to group management in Intune.</span></span> <span data-ttu-id="701ca-114">Para saber como criar grupos, consulte [Gerenciar grupos no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="701ca-114">To learn how to create groups, see [Managing groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>
>
><span data-ttu-id="701ca-115">Caso não esteja vendo o link para o portal do Azure AD, você ainda está usando o portal do Intune para gerenciamento de grupos.</span><span class="sxs-lookup"><span data-stu-id="701ca-115">If you do not see the link to the Azure AD portal, you are still using the Intune portal for groups management.</span></span>

## <span data-ttu-id="701ca-116">Gerenciamento de grupos no portal do Intune</span><span class="sxs-lookup"><span data-stu-id="701ca-116">Group management in the Intune portal</span></span>
<a id="group-management-in-the-intune-portal" class="xliff"></a>

<span data-ttu-id="701ca-117">Os grupos de usuários e de dispositivos são criados no espaço de trabalho GRUPOS do console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="701ca-117">Device and user groups are both created in the GROUPS workspace of the Intune administration console.</span></span>

![Espaço de trabalho de grupos do console de administração](./media/groups.png)


> [!TIP]
> <span data-ttu-id="701ca-119">Para saber mais sobre como usar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="701ca-119">To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>


## <span data-ttu-id="701ca-120">Criar um grupo de dispositivos</span><span class="sxs-lookup"><span data-stu-id="701ca-120">Create a device group</span></span>
<a id="create-a-device-group" class="xliff"></a>
<span data-ttu-id="701ca-121">Use grupos de dispositivos para implantar aplicativos e atualizações e para configurar outros recursos.</span><span class="sxs-lookup"><span data-stu-id="701ca-121">Use device groups to deploy apps and updates, and configure other features.</span></span> <span data-ttu-id="701ca-122">Por exemplo, configure um grupo "Meus Dispositivos" usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="701ca-122">For example, set up a "My Devices" group using the following steps:</span></span>

1.  <span data-ttu-id="701ca-123">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** > **Visão Geral** > **Criar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="701ca-123">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.</span></span>

2.  <span data-ttu-id="701ca-124">Em **Nome do Grupo**, digite “Meus Dispositivos” e, na lista de grupos pai, selecione **Todos os Dispositivos** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="701ca-124">For the **Group name**, type “My Devices” and, from the parent group list, select **All Devices**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="701ca-125">Na página **Definir critérios de associação** , selecione **Todos os dispositivos** , para indicar que o grupo inclui tanto dispositivos móveis quanto computadores.</span><span class="sxs-lookup"><span data-stu-id="701ca-125">On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.</span></span>

4.  <span data-ttu-id="701ca-126">Na página **Definir Associação Direta**, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="701ca-126">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="701ca-127">Caso você tenha criado anteriormente um grupo que não incluiu todos os dispositivos e deseje adicionar dispositivos específicos ao seu novo grupo, você pode fazer isso aqui.</span><span class="sxs-lookup"><span data-stu-id="701ca-127">If you previously created a group that did not include all devices, and you wanted to add specific devices to your new group, you can do that here.</span></span>

5.  <span data-ttu-id="701ca-128">Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="701ca-128">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="701ca-129">O grupo recém-criado pode ser encontrado na lista **Grupos**, no espaço de trabalho **Grupos**, em **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="701ca-129">You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Devices**.</span></span> <span data-ttu-id="701ca-130">Nesse local, também é possível editar ou excluir o grupo.</span><span class="sxs-lookup"><span data-stu-id="701ca-130">From here, you can also edit or delete the group.</span></span>

## <span data-ttu-id="701ca-131">Criar um grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="701ca-131">Create a user group</span></span>
<a id="create-a-user-group" class="xliff"></a>
<span data-ttu-id="701ca-132">Use grupos de usuários para implantar políticas de dispositivo e software.</span><span class="sxs-lookup"><span data-stu-id="701ca-132">Use user groups to deploy software and device policies.</span></span> <span data-ttu-id="701ca-133">Por exemplo, configure um grupo "Usuários do Intune" usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="701ca-133">For example, set up an "Intune Users" group using the following steps:</span></span>

1.  <span data-ttu-id="701ca-134">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** > **Visão Geral** > **Criar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="701ca-134">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.</span></span>

2.  <span data-ttu-id="701ca-135">Em **Nome do Grupo**, digite “Usuários do Intune” e, na lista de grupos pai, selecione **Todos os Usuários** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="701ca-135">For the **Group name**, type “Intune Users” and, from the parent group list, select **All Users**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="701ca-136">Na página **Definir Critérios de Associação** , defina **Iniciar associação de grupo com** como **Todos os usuários no grupo Pai**.</span><span class="sxs-lookup"><span data-stu-id="701ca-136">On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.</span></span>

4.  <span data-ttu-id="701ca-137">Ao lado de **Excluir membros destes grupos de segurança**, escolha **Procurar** e, em seguida, selecione **Administrador da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="701ca-137">Beside **Exclude members from these security groups**, choose **Browse** and then select **Company Administrator**.</span></span> <span data-ttu-id="701ca-138">Essa exclusão permite gerenciar o grupo Usuários do Intune sem afetar a conta Administrador da empresa (também conhecida como administrador de locatários).</span><span class="sxs-lookup"><span data-stu-id="701ca-138">This exclusion lets you manage the Intune Users group without affecting the Company Administrator account (also known as the tenant administrator).</span></span>

5.  <span data-ttu-id="701ca-139">Na página **Definir Associação Direta**, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="701ca-139">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="701ca-140">Você não precisa fazer nada aqui porque deseja que o grupo Usuários do Intune inclua todos os usuários, exceto o Administrador da Empresa.</span><span class="sxs-lookup"><span data-stu-id="701ca-140">You don’t need to do anything here because you want the Intune Users group to include all users, except for the Company Administrator.</span></span>

6.  <span data-ttu-id="701ca-141">Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="701ca-141">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="701ca-142">O grupo recém-criado pode ser encontrado na lista **Grupos**, no espaço de trabalho **Grupos**, em **Todos os usuários**.</span><span class="sxs-lookup"><span data-stu-id="701ca-142">You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Users**.</span></span> <span data-ttu-id="701ca-143">Nesse local, também é possível editar ou excluir o grupo.</span><span class="sxs-lookup"><span data-stu-id="701ca-143">From here, you can also edit or delete the group.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="701ca-144">/intune/licenses-assign [&larr; **Gerenciar licenças do Intune**](/intune/licenses-assign)       [**Criar políticas e aplicativos** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)</span><span class="sxs-lookup"><span data-stu-id="701ca-144">/intune/licenses-assign [&larr; **Manage Intune licenses**](/intune/licenses-assign)       [**Create policies and apps** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)</span></span>  
