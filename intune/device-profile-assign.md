---
title: Como atribuir perfis de dispositivo com o Intune
titleSuffix: Intune on Azure
description: "Depois de criar um perfil de dispositivo do Intune, use este tópico para saber como atribuí-lo a dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf6bd6cb301491c031e382236eee509e17f08383
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2017
---
<<<<<<< HEAD
# <span data-ttu-id="b744c-103">Como atribuir perfis de dispositivo do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b744c-103">How to assign Microsoft Intune device profiles</span></span>
<a id="how-to-assign-microsoft-intune-device-profiles" class="xliff"></a>

## <span data-ttu-id="b744c-104">Atribuir um perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b744c-104">Assign a device profile</span></span>
<a id="assign-a-device-profile" class="xliff"></a>

1. <span data-ttu-id="b744c-105">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="b744c-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="b744c-106">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b744c-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="b744c-107">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b744c-107">On the **Intune** blade, choose **Device configuration**.</span></span>
1. <span data-ttu-id="b744c-108">Na folha **Configurações do dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="b744c-108">On the **Device configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="b744c-109">Na folha da lista de perfis, escolha o perfil que você deseja gerenciar e, na folha <*nome do perfil*> **Relatórios**, escolha **Gerenciar** > **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="b744c-109">In the list of profiles blade, choose the profile you want to manage, and then, on the <*profile name*> **Reports** blade, choose **Manage** > **Assignments**.</span></span>
3. <span data-ttu-id="b744c-110">Na folha a seguir, escolha **Incluir** (para incluir grupos) ou **Excluir** (para excluir grupos) e clique em **Selecionar grupos**.</span><span class="sxs-lookup"><span data-stu-id="b744c-110">On the next blade, choose either **Include** (to include groups) or **Exclude** (to exclude groups), then choose **Select groups**.</span></span>
<span data-ttu-id="b744c-111">![Incluir e excluir grupos de uma atribuição de perfil.](./media/group-include-exclude.png)</span><span class="sxs-lookup"><span data-stu-id="b744c-111">![Include and exclude groups from a profile assignment.](./media/group-include-exclude.png)</span></span>
4. <span data-ttu-id="b744c-112">Na folha **Selecionar grupos**, escolha os grupos do Azure AD que você deseja incluir ou excluir da atribuição.</span><span class="sxs-lookup"><span data-stu-id="b744c-112">On the **Select groups** blade, choose the Azure AD groups, which you want to include in, or exclude from the assignment.</span></span> <span data-ttu-id="b744c-113">Você pode manter a tecla **CTRL** pressionada para selecionar vários grupos.</span><span class="sxs-lookup"><span data-stu-id="b744c-113">You can hold down the **CTRL** key to select multiple groups.</span></span>
4. <span data-ttu-id="b744c-114">Após terminar, na folha **Selecionar grupos**, escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b744c-114">When you are done, on the **Select groups** blade, choose **Select**.</span></span>



## <span data-ttu-id="b744c-115">Como excluir grupos de uma atribuição de perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b744c-115">How to exclude groups from a device profile assignment</span></span>
<a id="how-to-exclude-groups-from-a-device-profile-assignment" class="xliff"></a>

<span data-ttu-id="b744c-116">Os perfis de configuração de dispositivo do Intune permitem que você exclua grupos da atribuição de política.</span><span class="sxs-lookup"><span data-stu-id="b744c-116">Intune device configuration profiles let you exclude groups from policy assignment.</span></span> <span data-ttu-id="b744c-117">Por exemplo, você pode atribuir um perfil de dispositivo para o grupo **Todos os usuários corporativos**, mas excluir os membros do grupo **Equipe de Gerenciamento Sênior**.</span><span class="sxs-lookup"><span data-stu-id="b744c-117">For example, you could assign a device profile to the **All corporate users** group, but exclude any members of the **Senior Management Staff** group.</span></span>

<span data-ttu-id="b744c-118">Ao excluir grupos de uma atribuição, exclua apenas o usuário ou grupos de dispositivos, não uma combinação de grupos.</span><span class="sxs-lookup"><span data-stu-id="b744c-118">When you exclude groups from an assignment, exclude only user, or only device groups, not a mixture of groups.</span></span> <span data-ttu-id="b744c-119">O Intune não leva em conta as associações entre usuário e dispositivo ao excluir grupos.</span><span class="sxs-lookup"><span data-stu-id="b744c-119">Intune does not take into account any user to device association when excluding groups.</span></span> <span data-ttu-id="b744c-120">É improvável que você consiga os resultados necessários ao incluir grupos de usuários e excluir grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b744c-120">Including user groups while excluding device groups is unlikely to produce the results you need.</span></span> <span data-ttu-id="b744c-121">Se utilizar grupos mistos ou em caso de outros conflitos, a inclusão têm prioridade sobre a exclusão.</span><span class="sxs-lookup"><span data-stu-id="b744c-121">In case where mixed groups are used, or there are other conflicts, inclusion takes precedence over exclusion.</span></span>

<span data-ttu-id="b744c-122">Por exemplo, digamos que você deseja atribuir um perfil de dispositivo para todos os dispositivos na sua organização, exceto os dispositivos de quiosque.</span><span class="sxs-lookup"><span data-stu-id="b744c-122">For example, you want to assign a device profile to all devices in your organization, except kiosk devices.</span></span> <span data-ttu-id="b744c-123">você inclui o grupo **Todos os Usuários**, mas exclui o grupo **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b744c-123">You include the **All Users** group, but exclude the **All Devices** group.</span></span>

<span data-ttu-id="b744c-124">Nesse caso, todos os usuários e seus dispositivos obterão a política, mesmo se o dispositivo do usuário fizer parte do grupo **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b744c-124">In this case, all your users and their devices get the policy, even if the user’s device is part of the **All Devices** group.</span></span> 

<span data-ttu-id="b744c-125">A exclusão somente avalia os membros diretos dos grupos e não inclui os dispositivos que estão associados um usuário.</span><span class="sxs-lookup"><span data-stu-id="b744c-125">Exclusion only evaluates the direct members of the groups, and does not include devices that are associated with a user.</span></span> <span data-ttu-id="b744c-126">No entanto, dispositivos que não têm um usuário não obterão a política, pois eles não têm uma associação para o grupo **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="b744c-126">However, devices that don't have a user do not get the policy because they have no association to the **All Users** group.</span></span> 

<span data-ttu-id="b744c-127">Se você incluir **Todos os Dispositivos**, mas excluir **Todos os Usuários**, todos os dispositivos receberão a política.</span><span class="sxs-lookup"><span data-stu-id="b744c-127">If you include **All Devices**, but exclude **All Users**, all the devices receive the policy.</span></span> <span data-ttu-id="b744c-128">A intenção nesse caso é excluir dispositivos que têm um usuário associado dessa política.</span><span class="sxs-lookup"><span data-stu-id="b744c-128">The intent in this case is to exclude devices that have an associated user from this policy.</span></span> <span data-ttu-id="b744c-129">No entanto, ela não funciona, pois o recurso de exclusão compara apenas os membros diretos do grupo.</span><span class="sxs-lookup"><span data-stu-id="b744c-129">However, it does not because the exclusion feature only compares direct group members.</span></span> 

>[!Tip]
><span data-ttu-id="b744c-130">Exclusões não estão disponíveis no momento para políticas de conformidade ou atribuição de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b744c-130">Exclusions are not currently available for compliance policies or app assignment.</span></span> <span data-ttu-id="b744c-131">Para excluir membros de uma atribuição, você pode usar as intenções de atribuição Disponível e Não aplicável.</span><span class="sxs-lookup"><span data-stu-id="b744c-131">To exclude members from an assignment, you can use the Available, and Not applicable assignment intents.</span></span> <span data-ttu-id="b744c-132">Por exemplo, você pode atribuir um aplicativo **Todos os usuários corporativos** com a intenção **Disponível** e **Equipe de Gerenciamento Sênior** com a intenção **Não aplicável**.</span><span class="sxs-lookup"><span data-stu-id="b744c-132">For example, you assign an app to **All corporate users** with the **Available** intent, and to **Senior Management Staff** with the **Not applicable** intent.</span></span> <span data-ttu-id="b744c-133">o aplicativo é atribuído a todos os usuários, *exceto* aos usuários do grupo **Equipe de Gerenciamento Sênior**.</span><span class="sxs-lookup"><span data-stu-id="b744c-133">the app is assigned to all users *except* users in the **Senior Management Staff** group.</span></span> <span data-ttu-id="b744c-134">Se você atribuir o aplicativo a **Todos os usuários corporativos** com a intenção **Necessário**, os usuários do grupo **Equipe de Gerenciamento Sênior** não serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="b744c-134">If you assign the app to **All corporate users** with the **Required** intent, the users in the **Senior Management Staff** group are not excluded.</span></span>
 
    
## <span data-ttu-id="b744c-135">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b744c-135">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="b744c-136">Consulte [Como monitorar perfis de dispositivo](device-profile-monitor.md) para obter informações para ajudar a monitorar as atribuições de perfil de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b744c-136">See [How to monitor device profiles](device-profile-monitor.md) for information to help you monitor device profile assignments.</span></span>
=======
# Como atribuir perfis de dispositivo do Microsoft Intune
<a id="how-to-assign-microsoft-intune-device-profiles" class="xliff"></a>

## Atribuir um perfil de dispositivo
<a id="assign-a-device-profile" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
1. Na folha **Configurações do dispositivo**, escolha **Gerenciar** > **Perfis**.
2. Na folha da lista de perfis, escolha o perfil que você deseja gerenciar e, na folha <*nome do perfil*> **Relatórios**, escolha **Gerenciar** > **Atribuições**.
3. Na folha a seguir, escolha **Incluir** (para incluir grupos) ou **Excluir** (para excluir grupos) e clique em **Selecionar grupos**.
![Incluir e excluir grupos de uma atribuição de perfil.](./media/group-include-exclude.png)
4. Na folha **Selecionar grupos**, escolha os grupos do Azure AD que você deseja incluir ou excluir da atribuição. Você pode manter a tecla **CTRL** pressionada para selecionar vários grupos.
4. Após terminar, na folha **Selecionar grupos**, escolha **Selecionar**.



## Como excluir grupos de uma atribuição de perfil de dispositivo
<a id="how-to-exclude-groups-from-a-device-profile-assignment" class="xliff"></a>

Os perfis de configuração de dispositivo do Intune permitem que você exclua grupos da atribuição de política. Por exemplo, você pode atribuir um perfil de dispositivo para o grupo **Todos os usuários corporativos**, mas excluir os membros do grupo **Equipe de Gerenciamento Sênior**.

Ao excluir grupos de uma atribuição, exclua apenas o usuário ou grupos de dispositivos, não uma combinação de grupos. O Intune não leva em conta as associações entre usuário e dispositivo ao excluir grupos. É improvável que você consiga os resultados necessários ao incluir grupos de usuários e excluir grupos de dispositivos. Se utilizar grupos mistos ou em caso de outros conflitos, a inclusão têm prioridade sobre a exclusão.

Por exemplo, digamos que você deseja atribuir um perfil de dispositivo para todos os dispositivos na sua organização, exceto os dispositivos de quiosque. você inclui o grupo **Todos os Usuários**, mas exclui o grupo **Todos os Dispositivos**.

Nesse caso, todos os usuários e seus dispositivos obterão a política, mesmo se o dispositivo do usuário fizer parte do grupo **Todos os Dispositivos**. 

A exclusão somente avalia os membros diretos dos grupos e não inclui os dispositivos que estão associados um usuário. No entanto, dispositivos que não têm um usuário não obterão a política, pois eles não têm uma associação para o grupo **Todos os Usuários**. 

Se você incluir **Todos os Dispositivos**, mas excluir **Todos os Usuários**, todos os dispositivos receberão a política. A intenção nesse caso é excluir dispositivos que têm um usuário associado dessa política. No entanto, ela não funciona, pois o recurso de exclusão compara apenas os membros diretos do grupo. 

>[!Tip]
>Exclusões não estão disponíveis no momento para políticas de conformidade ou atribuição de aplicativo. Para excluir membros de uma atribuição, você pode usar as intenções de atribuição Disponível e Não aplicável. Por exemplo, você pode atribuir um aplicativo **Todos os usuários corporativos** com a intenção **Disponível** e **Equipe de Gerenciamento Sênior** com a intenção **Não aplicável**. o aplicativo é atribuído a todos os usuários, *exceto* aos usuários do grupo **Equipe de Gerenciamento Sênior**. Se você atribuir o aplicativo a **Todos os usuários corporativos** com a intenção **Necessário**, os usuários do grupo **Equipe de Gerenciamento Sênior** não serão excluídos.
 
    
## Próximas etapas
<a id="next-steps" class="xliff"></a>
Consulte [Como monitorar perfis de dispositivo](device-profile-monitor.md) para obter informações para ajudar a monitorar as atribuições de perfil de dispositivo.
>>>>>>> live
