---
title: "Definir restrições de registro no Intune"
titleSuffix: Intune on Azure
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce779e8dad2c9813d5faf1f03bca9b33690508fe
ms.sourcegitcommit: b287025b1a0d09d41faf51cf98c34b676fa1d98e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2017
---
<<<<<<< HEAD
# <a name="add-groups-in-intune"></a><span data-ttu-id="d6e6d-104">Adicionar grupos no Intune</span><span class="sxs-lookup"><span data-stu-id="d6e6d-104">Add groups in Intune</span></span>
<span data-ttu-id="d6e6d-105">O Intune usa grupos do AD (Azure Active Directory) para gerenciar dispositivos e usuários.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-105">Intune uses Azure Active Directory (AD) groups to manage devices and users.</span></span> <span data-ttu-id="d6e6d-106">Como administrador do Intune, você pode configurar grupos para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-106">As an Intune admin, you can set up groups to suit your organizational needs.</span></span> <span data-ttu-id="d6e6d-107">Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-107">Create groups to organize users or devices by geographic location, department, or hardware characteristics.</span></span> <span data-ttu-id="d6e6d-108">Use grupos para gerenciar tarefas em grande escala.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-108">Use groups to manage tasks at scale.</span></span> <span data-ttu-id="d6e6d-109">Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-109">For example, you can set policies for many users or  deploy apps to a set of devices.</span></span>

<span data-ttu-id="d6e6d-110">Este tópico explica como adicionar grupos para serem usados no Intune.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-110">This topic explains how to add groups for use in Intune.</span></span>

<span data-ttu-id="d6e6d-111">Você pode adicionar os seguintes tipos de grupos:</span><span class="sxs-lookup"><span data-stu-id="d6e6d-111">You can add the following types of groups:</span></span>
- <span data-ttu-id="d6e6d-112">**Grupos atribuídos** – Adicione usuários ou dispositivos manualmente em um grupo estático</span><span class="sxs-lookup"><span data-stu-id="d6e6d-112">**Assigned groups** - Manually add users or devices into a static group</span></span>
- <span data-ttu-id="d6e6d-113">**Grupos dinâmicos** – (Azure Active Directory Premium) Permitem que você crie dinamicamente grupos de usuários ou dispositivos definidos com regras simples ou avançadas</span><span class="sxs-lookup"><span data-stu-id="d6e6d-113">**Dynamic groups** - (Azure Active Directory Premium) Let you dynamically build either user or device groups defined with either simple or advanced rules</span></span>

## <a name="add-a-new-group"></a><span data-ttu-id="d6e6d-114">Adicionar um novo grupo</span><span class="sxs-lookup"><span data-stu-id="d6e6d-114">Add a new group</span></span>

<span data-ttu-id="d6e6d-115">Use as etapas a seguir para criar um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-115">Use the following steps to create a new group.</span></span>
1. <span data-ttu-id="d6e6d-116">No Portal do Intune, acesse **Grupos** e escolha **Novo grupo** na folha **Todos os grupos**.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-116">In the Intune portal, go **Groups** and then choose **New group** in the **All groups** blade.</span></span>
  <span data-ttu-id="d6e6d-117">![Captura de tela do Portal do Intune com o novo grupo selecionado](./media/groups-add-new.png)</span><span class="sxs-lookup"><span data-stu-id="d6e6d-117">![Screenshot of the Intune portal with New Group selected](./media/groups-add-new.png)</span></span>
2. <span data-ttu-id="d6e6d-118">Especifique o **Nome** e a **Descrição** do novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-118">Specify the **Name** and **Description** of the new group.</span></span> <span data-ttu-id="d6e6d-119">Essas propriedades só aparecem no Portal do Intune e não são exibidas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-119">These properties only appear in the Intune portal and are not displayed to users.</span></span>

3. <span data-ttu-id="d6e6d-120">Escolha o **Tipo de associação**:</span><span class="sxs-lookup"><span data-stu-id="d6e6d-120">Choose **Membership type**:</span></span>
  - <span data-ttu-id="d6e6d-121">**Atribuído** para criar um grupo com membros atribuídos manualmente.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-121">**Assigned** to create group with manually assigned members.</span></span> <span data-ttu-id="d6e6d-122">Saiba mais sobre [Grupos atribuídos do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d6e6d-122">Learn more about [Azure AD assigned groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>
  - <span data-ttu-id="d6e6d-123">**Usuário Dinâmico** para criar um grupo de usuários definidos com uma **Consulta dinâmica**.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-123">**Dynamic User** to create a user group defined with a **Dynamic query**.</span></span>
  - <span data-ttu-id="d6e6d-124">**Dispositivo Dinâmico** para criar um grupo de dispositivos definidos com uma **Consulta dinâmica**.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-124">**Dynamic Device** to create a device group defined with a **Dynamic query**.</span></span>

  ![Captura de tela das propriedades do grupo do Intune com Nome, Descrição, Tipo de associação, Habilitar recursos do Office e Membros](./media/groups-add-properties.png)

  <span data-ttu-id="d6e6d-126">O Azure AD permite criar grupos dinâmicos com base nas regras que definem a associação.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-126">Azure AD lets you create dynamic groups based on rules that define membership.</span></span> <span data-ttu-id="d6e6d-127">Aprenda a [criar grupos dinâmicos com base em atributo](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="d6e6d-127">Learn to [create attribute-based dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

4. <span data-ttu-id="d6e6d-128">Você pode selecionar **Habilitar recursos do Office** para conceder acesso aos membros do grupo de usuários para aplicativos do Office 365 compartilhados.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-128">You can select **Enable Office features** to give user group members access to shared Office 365 apps.</span></span>
5. <span data-ttu-id="d6e6d-129">Escolha **Criar** para adicionar o novo grupo.</span><span class="sxs-lookup"><span data-stu-id="d6e6d-129">Choose **Create** to add the new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6e6d-130">Veja também</span><span class="sxs-lookup"><span data-stu-id="d6e6d-130">See also</span></span>
- [<span data-ttu-id="d6e6d-131">Gerenciar o acesso a recursos com grupos do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d6e6d-131">Manage access to resources with Azure Active Directory groups</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [<span data-ttu-id="d6e6d-132">Grupos clássicos do Intune no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="d6e6d-132">Intune classic groups in the Azure portal</span></span>](groups-get-started.md)
=======
# <a name="add-groups-in-intune"></a>Adicionar grupos no Intune
O Intune usa grupos do AD (Azure Active Directory) para gerenciar dispositivos e usuários. Como administrador do Intune, você pode configurar grupos para atender às necessidades da sua organização. Crie grupos para organizar usuários ou dispositivos por localização geográfica, departamento ou características de hardware. Use grupos para gerenciar tarefas em grande escala. Por exemplo, você pode definir políticas para vários usuários ou implantar aplicativos em um conjunto de dispositivos.

Este tópico explica como adicionar grupos para serem usados no Intune.

Você pode adicionar os seguintes tipos de grupos:
- **Grupos atribuídos** – Adicione usuários ou dispositivos manualmente em um grupo estático
- **Grupos dinâmicos** – (Azure Active Directory Premium) Permitem que você crie dinamicamente grupos de usuários ou dispositivos definidos com regras simples ou avançadas

## <a name="add-a-new-group"></a>Adicionar um novo grupo

Use as etapas a seguir para criar um novo grupo.
1. No Portal do Intune, acesse **Grupos** e escolha **Novo grupo** na folha **Todos os grupos**.
  ![Captura de tela do Portal do Intune com o novo grupo selecionado](./media/groups-add-new.png)
2. Especifique o **Nome** e a **Descrição** do novo grupo. Essas propriedades só aparecem no Portal do Intune e não são exibidas para os usuários.

3. Escolha o **Tipo de associação**:
  - **Atribuído** para criar um grupo com membros atribuídos manualmente. Saiba mais sobre [Grupos atribuídos do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
  - **Usuário Dinâmico** para criar um grupo de usuários definidos com uma **Consulta dinâmica**.
  - **Dispositivo Dinâmico** para criar um grupo de dispositivos definidos com uma **Consulta dinâmica**.

  ![Captura de tela das propriedades do grupo do Intune com Nome, Descrição, Tipo de associação, Habilitar recursos do Office e Membros](./media/groups-add-properties.png)

  O Azure AD permite criar grupos dinâmicos com base nas regras que definem a associação. Aprenda a [criar grupos dinâmicos com base em atributo](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

4. Você pode selecionar **Habilitar recursos do Office** para conceder acesso aos membros do grupo de usuários para aplicativos do Office 365 compartilhados.
5. Escolha **Criar** para adicionar o novo grupo.

## <a name="see-also"></a>Veja também
- [Gerenciar o acesso a recursos com grupos do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [Grupos clássicos do Intune no Portal do Azure](groups-get-started.md)
>>>>>>> live
