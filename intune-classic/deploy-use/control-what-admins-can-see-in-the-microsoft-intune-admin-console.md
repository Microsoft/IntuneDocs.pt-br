---
title: "Personalizar as exibições do console para funções administrativas"
description: "Use este tópico para ajudá-lo a filtrar a exibição do console de administração do Intune para permitir que seus administradores vejam apenas os itens necessários para sua função."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9b2016bc4f2c7ef63722becc413422d618939336
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ed51f-103">Personalizar exibições do console do Intune de acordo com funções do administrador</span><span class="sxs-lookup"><span data-stu-id="ed51f-103">Customize Intune console views according to admin roles</span></span>
<a id="customize-intune-console-views-according-to-admin-roles" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ed51f-104">Você pode filtrar a exibição do console de administração do Microsoft Intune para permitir que seus administradores vejam apenas os itens que precisam ver para sua função.</span><span class="sxs-lookup"><span data-stu-id="ed51f-104">You can filter the Microsoft Intune administration console view to allow your admins to see only the items they need to see for their role.</span></span> <span data-ttu-id="ed51f-105">Por exemplo, você pode permitir que apenas os operadores do console de administração atualizem as definições de malware ou redefinam a senha em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ed51f-105">For example, you can allow only admin console operators to update malware definitions or reset the passcode on devices.</span></span> <span data-ttu-id="ed51f-106">Você faz isso usando a predefinição **designações**, que atribui a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="ed51f-106">You do this by using preset **designations** that you assign to specific users.</span></span> <span data-ttu-id="ed51f-107">Quando acessam o console de administração, esses usuários podem ver apenas itens específicos para suas designações.</span><span class="sxs-lookup"><span data-stu-id="ed51f-107">When these users access the admin console, they can only see items that are specific to their designation.</span></span>

## <span data-ttu-id="ed51f-108">Para criar uma exibição personalizada</span><span class="sxs-lookup"><span data-stu-id="ed51f-108">To create a custom view</span></span>
<a id="to-create-a-custom-view" class="xliff"></a>

1.  <span data-ttu-id="ed51f-109">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Admin** &gt; **Administradores de Serviço**.</span><span class="sxs-lookup"><span data-stu-id="ed51f-109">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Service Administrators**.</span></span>

2.  <span data-ttu-id="ed51f-110">Na lista de administradores de serviço, escolha o usuário cuja atribuição você deseja alterar e selecione **Gerenciar Acesso**.</span><span class="sxs-lookup"><span data-stu-id="ed51f-110">From the list of service administrators, choose the user whose designation you want to change, and then choose **Manage Access**.</span></span>

3.  <span data-ttu-id="ed51f-111">Na caixa de diálogo **Gerenciar Acesso** , escolha o nível de acesso que você deseja dar ao usuário selecionado.</span><span class="sxs-lookup"><span data-stu-id="ed51f-111">In the **Manage Access** dialog box, choose the level of access that you want to give the selected user.</span></span> <span data-ttu-id="ed51f-112">Você pode escolher:</span><span class="sxs-lookup"><span data-stu-id="ed51f-112">You can choose from:</span></span>

    -   <span data-ttu-id="ed51f-113">**Acesso completo**</span><span class="sxs-lookup"><span data-stu-id="ed51f-113">**Full access**</span></span>
    -   <span data-ttu-id="ed51f-114">**Acesso somente leitura**</span><span class="sxs-lookup"><span data-stu-id="ed51f-114">**Read-only access**</span></span>
    -   <span data-ttu-id="ed51f-115">**Assistência técnica – nó Grupos**</span><span class="sxs-lookup"><span data-stu-id="ed51f-115">**Helpdesk - Groups node**</span></span>

    <span data-ttu-id="ed51f-116">Acesso completo e acesso somente leitura são autoexplicativos.</span><span class="sxs-lookup"><span data-stu-id="ed51f-116">Full access and read-only access are self-explanatory.</span></span> <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

    <span data-ttu-id="ed51f-117">**Assistência técnica - Nó dos Grupos** restringe o que o administrador pode ver e fazer ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="ed51f-117">**Helpdesk - Groups Node** restricts what the admin can see and do to the following:</span></span>

    -   <span data-ttu-id="ed51f-118">Ver listas de usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ed51f-118">See lists of users and devices.</span></span> <span data-ttu-id="ed51f-119">O administrador não pode usar filtros para modificar a exibição.</span><span class="sxs-lookup"><span data-stu-id="ed51f-119">The admin cannot use filters to modify the view.</span></span> <span data-ttu-id="ed51f-120">No entanto, você pode usar a filtragem de grupo para modificar o que o administrador pode ver.</span><span class="sxs-lookup"><span data-stu-id="ed51f-120">However, you can use group filtering to modify what the admin can see.</span></span> <span data-ttu-id="ed51f-121">Para mais informações, consulte [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="ed51f-121">For more information, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

    -   <span data-ttu-id="ed51f-122">Imprimir a lista de usuários e dispositivos</span><span class="sxs-lookup"><span data-stu-id="ed51f-122">Print the list of users and devices</span></span>

    -   <span data-ttu-id="ed51f-123">Exportar a lista de usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ed51f-123">Export the list of users and devices</span></span>

    -   <span data-ttu-id="ed51f-124">Exibir as propriedades de um dispositivo ou usuário</span><span class="sxs-lookup"><span data-stu-id="ed51f-124">View the properties of a user or device</span></span>

    -   <span data-ttu-id="ed51f-125">Executar as seguintes tarefas remotas:</span><span class="sxs-lookup"><span data-stu-id="ed51f-125">Perform the following remote tasks:</span></span>

        -   <span data-ttu-id="ed51f-126">Executar uma verificação completa de malware</span><span class="sxs-lookup"><span data-stu-id="ed51f-126">Run a full malware scan</span></span>

        -   <span data-ttu-id="ed51f-127">Executar uma verificação rápida de malware</span><span class="sxs-lookup"><span data-stu-id="ed51f-127">Run a quick malware scan</span></span>

        -   <span data-ttu-id="ed51f-128">Reiniciar um computador</span><span class="sxs-lookup"><span data-stu-id="ed51f-128">Restart a computer</span></span>

        -   <span data-ttu-id="ed51f-129">Atualizar definições de malware</span><span class="sxs-lookup"><span data-stu-id="ed51f-129">Update malware definitions</span></span>

        -   <span data-ttu-id="ed51f-130">Atualizar políticas</span><span class="sxs-lookup"><span data-stu-id="ed51f-130">Refresh policies</span></span>

        -   <span data-ttu-id="ed51f-131">Atualizar o inventário</span><span class="sxs-lookup"><span data-stu-id="ed51f-131">Refresh inventory</span></span>

        -   <span data-ttu-id="ed51f-132">Bloquear um dispositivo remotamente</span><span class="sxs-lookup"><span data-stu-id="ed51f-132">Lock a device remotely</span></span>

        -   <span data-ttu-id="ed51f-133">Redefinir uma senha</span><span class="sxs-lookup"><span data-stu-id="ed51f-133">Reset a passcode</span></span>

<span data-ttu-id="ed51f-134">Na próxima vez em que o administrador configurado abrir o console de administração do Intune, ele receberá o nível de acesso designado.</span><span class="sxs-lookup"><span data-stu-id="ed51f-134">When the admin that you configured next opens the Intune admin console, they will be given the level of access that you designated.</span></span>
