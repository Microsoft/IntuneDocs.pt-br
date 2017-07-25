---
title: "Política de acesso condicional baseado em aplicativo com o Intune"
description: "Este tópico descreve como você pode configurar uma política de acesso condicional baseado em aplicativo com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="b7f7c-103">Configurar políticas de acesso condicional baseado em aplicativo</span><span class="sxs-lookup"><span data-stu-id="b7f7c-103">Set up app-based conditional access policies</span></span>
=======
# Configurar políticas de acesso condicional baseado em aplicativo
>>>>>>> live
<a id="set-up-app-based-conditional-access-policies" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="b7f7c-104">Este tópico fornece instruções sobre como configurar políticas de acesso condicional baseado em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-104">This topic provides instructions on how to set up app-based conditional access policies for apps that are part of the list of approved apps.</span></span> <span data-ttu-id="b7f7c-105">A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-105">The list of approved apps consists of apps that were tested by Microsoft.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7f7c-106">Este tópico descreve as etapas para adicionar uma política de acesso condicional baseado em aplicativo usando o Exchange Online, mas é possível usar as mesmas etapas ao adicionar outros aplicativos como o SharePoint Online, Microsoft Teams, etc. na lista de aplicativos aprovados.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-106">This topic walks through the steps to add an app-based conditional access policy using Exchange Online, but you can use the same steps when adding other apps like SharePoint Online, Microsoft Teams, etc. from the list of approved apps.</span></span>

## <span data-ttu-id="b7f7c-107">Para criar uma política de acesso condicional baseado no aplicativo</span><span class="sxs-lookup"><span data-stu-id="b7f7c-107">To create an app-based conditional access policy</span></span>
<a id="to-create-an-app-based-conditional-access-policy" class="xliff"></a>
1.  <span data-ttu-id="b7f7c-108">Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-108">Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="b7f7c-109">Escolha **Mais serviços** e digite "Intune".</span><span class="sxs-lookup"><span data-stu-id="b7f7c-109">Choose **More services**, and type: "Intune".</span></span>

3.  <span data-ttu-id="b7f7c-110">Escolha **Proteção de Aplicativo do Intune**.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-110">Choose **Intune App Protection**.</span></span>

4.  <span data-ttu-id="b7f7c-111">Na folha **Gerenciamento de aplicativo móvel do Intune**, escolha **Todas as Configurações**.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-111">On the **Intune mobile application management** blade choose **All Settings**.</span></span>

5.  <span data-ttu-id="b7f7c-112">Na seção **Acesso condicional**, escolha **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-112">On the **Conditional access** section, choose **Exchange Online**.</span></span>

    ![Captura de tela da folha de configurações mostrando a seção acesso condicional com a opção Exchange Online em destaque](./media/MAM-conditional-access-1.png)

6. <span data-ttu-id="b7f7c-114">Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir que somente aplicativos com suporte para as políticas de proteção de aplicativo do Intune acessem o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-114">On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online.</span></span> <span data-ttu-id="b7f7c-115">Ao selecionar essa opção, a lista de aplicativos com suporte é exibida.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-115">When you select this option, the list of supported apps is displayed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7f7c-116">Todos os clientes de email do Exchange Active Sync, incluindo os de email interno no iOS e no Android que se conectam ao Exchange Online, serão impedidos de enviar ou receber emails.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-116">All Exchange Active Sync mail clients, including the built-in mail clients on iOS and Android that connect to Exchange Online, will be prevented from sending or receiving email.</span></span> <span data-ttu-id="b7f7c-117">Em vez disso, os usuários receberão um único email informando que eles precisam usar o aplicativo de email do Outlook.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-117">Users will instead receive a single email informing them that they need to use the Outlook mail app.</span></span>

7. <span data-ttu-id="b7f7c-118">Para aplicar essa política aos usuários, abra a folha **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuário**.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-118">To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**.</span></span> <span data-ttu-id="b7f7c-119">Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-119">Select one or more user groups that should get this policy.</span></span>

    ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](./media/mam-ca-add-user-group.png)

8. <span data-ttu-id="b7f7c-121">Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-121">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="b7f7c-122">Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-122">In such cases, add the group of users to the exempted user groups list.</span></span> <span data-ttu-id="b7f7c-123">Na folha **Exchange Online**, escolha **Grupos de usuários isentos**.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-123">From the **Exchange Online** blade, choose **Exempted user groups**.</span></span> <span data-ttu-id="b7f7c-124">Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-124">Choose **Add user group** to open the list of user groups.</span></span> <span data-ttu-id="b7f7c-125">Selecione os grupos que você deseja isentar dessa política.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-125">Select the groups you want to exempt from this policy.</span></span>

## <span data-ttu-id="b7f7c-126">Para modificar ou excluir grupos de usuários de uma política de autoridade de certificação baseada em aplicativo existente</span><span class="sxs-lookup"><span data-stu-id="b7f7c-126">To modify or delete user groups from an existing app-based CA policy</span></span>
<a id="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy" class="xliff"></a>

1. <span data-ttu-id="b7f7c-127">Abra a folha **Grupos de usuários restritos**, em seguida, realce o grupo de usuário que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-127">Open the **Restricted user groups** blade, then highlight the user group you want to delete.</span></span>
2. <span data-ttu-id="b7f7c-128">Clique nas reticências para ver as opções de exclusão.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-128">Click on the ellipse to see the delete options.</span></span>
3. <span data-ttu-id="b7f7c-129">Escolha **Excluir** para remover o grupo de usuários da lista.</span><span class="sxs-lookup"><span data-stu-id="b7f7c-129">Choose **Delete** to remove the user group from the list.</span></span>

## <span data-ttu-id="b7f7c-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b7f7c-130">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="b7f7c-131">Bloquear aplicativos que não têm autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="b7f7c-131">Block apps that do not have modern authentication</span></span>](app-modern-authentication-block.md)

### <span data-ttu-id="b7f7c-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b7f7c-132">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="b7f7c-133">Proteger dados de aplicativo com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b7f7c-133">Protect app data with app protection policies</span></span>](app-protection-policies.md)
=======
Este tópico fornece instruções sobre como configurar políticas de acesso condicional baseado em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

> [!IMPORTANT]
> Este tópico descreve as etapas para adicionar uma política de acesso condicional baseado em aplicativo usando o Exchange Online, mas é possível usar as mesmas etapas ao adicionar outros aplicativos como o SharePoint Online, Microsoft Teams, etc. na lista de aplicativos aprovados.

## Para criar uma política de acesso condicional baseado no aplicativo
<a id="to-create-an-app-based-conditional-access-policy" class="xliff"></a>
1.  Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.

2.  Escolha **Mais serviços** e digite "Intune".

3.  Escolha **Proteção de Aplicativo do Intune**.

4.  Na folha **Gerenciamento de aplicativo móvel do Intune**, escolha **Todas as Configurações**.

5.  Na seção **Acesso condicional**, escolha **Exchange Online**.

    ![Captura de tela da folha de configurações mostrando a seção acesso condicional com a opção Exchange Online em destaque](./media/MAM-conditional-access-1.png)

6. Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir que somente aplicativos com suporte para as políticas de proteção de aplicativo do Intune acessem o Exchange Online. Ao selecionar essa opção, a lista de aplicativos com suporte é exibida.

    > [!NOTE]
    > Todos os clientes de email do Exchange Active Sync, incluindo os de email interno no iOS e no Android que se conectam ao Exchange Online, serão impedidos de enviar ou receber emails. Em vez disso, os usuários receberão um único email informando que eles precisam usar o aplicativo de email do Outlook.

7. Para aplicar essa política aos usuários, abra a folha **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuário**. Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.

    ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](./media/mam-ca-add-user-group.png)

8. Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política. Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos. Na folha **Exchange Online**, escolha **Grupos de usuários isentos**. Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários. Selecione os grupos que você deseja isentar dessa política.

## Para modificar ou excluir grupos de usuários de uma política de autoridade de certificação baseada em aplicativo existente
<a id="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy" class="xliff"></a>

1. Abra a folha **Grupos de usuários restritos**, em seguida, realce o grupo de usuário que você deseja excluir.
2. Clique nas reticências para ver as opções de exclusão.
3. Escolha **Excluir** para remover o grupo de usuários da lista.

## Próximas etapas
<a id="next-steps" class="xliff"></a>
[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)

### Consulte também
<a id="see-also" class="xliff"></a>

[Proteger dados de aplicativo com as políticas de proteção de aplicativo](app-protection-policies.md)
>>>>>>> live
