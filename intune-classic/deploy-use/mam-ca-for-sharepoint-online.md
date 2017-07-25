---
title: "Criar uma política de acesso condicional baseada em aplicativo para o SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 2d9065281436d4c44e6af7d7a4401786a2a01965
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="26142-102">Definir uma política de acesso condicional baseada em aplicativo para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="26142-102">Set up app-based conditional access (CA) policies for SharePoint Online</span></span>
<a id="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online" class="xliff"></a>

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="26142-103">Este tópico fornece orientação sobre como configurar a política de acesso condicional com base no aplicativo para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="26142-103">This topic provides guidance on how to set up app-based conditional access policy for SharePoint Online.</span></span> <span data-ttu-id="26142-104">A autoridade de certificação baseada em aplicativo ajuda os administradores a permitirem somente aplicativos móveis que têm políticas de proteção de aplicativo do Intune aplicadas.</span><span class="sxs-lookup"><span data-stu-id="26142-104">App-based CA helps admins to only allow mobile apps that have Intune app protection policies applied to.</span></span>

## <span data-ttu-id="26142-105">Para criar a política de autoridade de certificação baseada em aplicativo para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="26142-105">To create the app-based CA policy for SharePoint Online</span></span>
<a id="to-create-the-app-based-ca-policy-for-sharepoint-online" class="xliff"></a>

1. <span data-ttu-id="26142-106">Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="26142-106">Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26142-107">Caso você seja novo na experiência do Portal do Azure, leia o tópico [Portal do Azure para políticas de proteção de aplicativo](azure-portal-for-microsoft-intune-mam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="26142-107">If you're new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.</span></span>

2. <span data-ttu-id="26142-108">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="26142-108">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="26142-109">Escolha **Intune App Protection** > **Gerenciamento de aplicativos móveis do Intune** > **Todas as Configurações**.</span><span class="sxs-lookup"><span data-stu-id="26142-109">Choose **Intune App Protection** > **Intune mobile application management** > **All Settings**.</span></span>

4. <span data-ttu-id="26142-110">Na folha Gerenciamento de aplicativo móvel do Intune, escolha o bloco SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="26142-110">On the Intune mobile application management blade, choose the SharePoint Online tile.</span></span>

5. <span data-ttu-id="26142-111">Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir somente aplicativos com suporte para as políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="26142-111">On the **Allowed apps** blade, choose **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="26142-112">Quando você seleciona a opção para permitir somente aplicativos com suporte das políticas de proteção de aplicativo do Intune, a lista que contém **somente** os aplicativos com suporte é exibida.</span><span class="sxs-lookup"><span data-stu-id="26142-112">When you select the option to only allow apps that are supported by Intune app protection policies, a list containing **only** the supported apps is displayed.</span></span>

    ![Captura de tela da folha de aplicativos permitidos mostrando a lista de aplicativos](../media/mam-ca-spo-allowed-apps.png)

## <span data-ttu-id="26142-114">Para atribuir políticas de autoridade de certificação baseadas em aplicativo para seus usuários</span><span class="sxs-lookup"><span data-stu-id="26142-114">To assign app-based CA policies to your users</span></span>
<a id="to-assign-app-based-ca-policies-to-your-users" class="xliff"></a>

1. <span data-ttu-id="26142-115">Abra a folha **Usuário de grupos restritos**, escolha **Adicionar grupo de usuário**.</span><span class="sxs-lookup"><span data-stu-id="26142-115">Open the **Restricted user groups** blade, then choose **Add user group**.</span></span>

2. <span data-ttu-id="26142-116">Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="26142-116">Select one or more user groups that should get this policy.</span></span>

    ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="26142-118">Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política.</span><span class="sxs-lookup"><span data-stu-id="26142-118">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="26142-119">Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos.</span><span class="sxs-lookup"><span data-stu-id="26142-119">In such cases, add the group of users to the exempted user groups list.</span></span> 

3. <span data-ttu-id="26142-120">Na folha **SharePoint Online**, escolha **Grupos de usuários isentos**, escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="26142-120">On the **SharePoint Online** blade, choose **Exempted user groups**, then choose **Add user group** to open the list of user groups.</span></span>

4. <span data-ttu-id="26142-121">Selecione os grupos que você deseja isentar dessa política.</span><span class="sxs-lookup"><span data-stu-id="26142-121">Select the groups you want to exempt from this policy.</span></span>  

## <span data-ttu-id="26142-122">Para modificar ou excluir grupos de usuários de uma política de autoridade de certificação baseada em aplicativo existente</span><span class="sxs-lookup"><span data-stu-id="26142-122">To modify or delete user groups from an existing app-based CA policy</span></span>
<a id="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy" class="xliff"></a>

1. <span data-ttu-id="26142-123">Abra a folha **Grupos de usuários restritos**, em seguida, realce o grupo de usuário que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="26142-123">Open the **Restricted user groups** blade, then highlight the user group you want to delete.</span></span>
2. <span data-ttu-id="26142-124">Clique nas reticências para ver as opções de exclusão.</span><span class="sxs-lookup"><span data-stu-id="26142-124">Click on the ellipse to see the delete options.</span></span>
3. <span data-ttu-id="26142-125">Escolha **Excluir** para remover o grupo de usuários da lista.</span><span class="sxs-lookup"><span data-stu-id="26142-125">Choose **Delete** to remove the user group from the list.</span></span>

> [!NOTE] 
> <span data-ttu-id="26142-126">Você pode seguir o mesmo procedimento em etapas para remover um grupo de usuários da lista **Grupo de usuários isentos**.</span><span class="sxs-lookup"><span data-stu-id="26142-126">You can follow the steps procedure to remove a user group from the **Exempted user group** list.</span></span>

## <span data-ttu-id="26142-127">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="26142-127">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="26142-128">Bloquear aplicativos que não usam autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="26142-128">Block apps that do not use modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

## <span data-ttu-id="26142-129">Consulte também</span><span class="sxs-lookup"><span data-stu-id="26142-129">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="26142-130">Proteger dados de aplicativo com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="26142-130">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="26142-131">Configurar a autoridade de certificação baseada em aplicativo para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="26142-131">Configure app-based CA for Exchange Online</span></span>](mam-ca-for-exchange-online.md)
