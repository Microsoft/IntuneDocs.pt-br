---
title: Acesso do aplicativo para o Exchange Online
description: "Este tópico descreve como você pode configurar uma política de acesso condicional para aplicativos MAM."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2ef4a0c0e642026d625d7139b2ea2629cdd96930
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="270b0-103">Crie um acesso condicional para o Exchange Online para permitir apenas aplicativos com suporte para MAM</span><span class="sxs-lookup"><span data-stu-id="270b0-103">Create an Exchange Online conditional access to only allow apps supported by MAM</span></span>
<a id="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="270b0-104">Este tópico fornece instruções passo a passo sobre como configurar o acesso condicional para o Exchange Online para permitir apenas aplicativos móveis com suporte para políticas de proteção de aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="270b0-104">This topic gives you step-by-step instructions on how to set up conditional access for  Exchange Online to only allow mobile apps that support Intune app protection policies.</span></span>


## <span data-ttu-id="270b0-105">Criar uma política do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="270b0-105">Create an Exchange Online policy</span></span>
<a id="create-an-exchange-online-policy" class="xliff"></a>
1.  <span data-ttu-id="270b0-106">Entre no [portal do Azure](https://portal.azure.com) que inclui o recurso de acesso do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="270b0-106">Sign into the [Azure portal](https://portal.azure.com) that includes the app access feature.</span></span> <span data-ttu-id="270b0-107">Caso você seja novo na experiência do portal do Azure, leia o tópico [Portal do Azure para políticas de proteção de aplicativo](azure-portal-for-microsoft-intune-mam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="270b0-107">If you are new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.</span></span>

2.  <span data-ttu-id="270b0-108">Escolha **Mais serviços** e digite "Intune".</span><span class="sxs-lookup"><span data-stu-id="270b0-108">Choose **More services**, and type: "Intune".</span></span>

3.  <span data-ttu-id="270b0-109">Escolha **Proteção de Aplicativo do Intune**.</span><span class="sxs-lookup"><span data-stu-id="270b0-109">Choose **Intune App Protection**.</span></span>

4.  <span data-ttu-id="270b0-110">Na folha **Gerenciamento de aplicativo móvel do Intune**, escolha **Todas as Configurações**.</span><span class="sxs-lookup"><span data-stu-id="270b0-110">On the **Intune mobile application management** blade choose **All Settings**.</span></span>

5.  <span data-ttu-id="270b0-111">Na seção **Acesso condicional**, escolha **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="270b0-111">On the **Conditional access** section, choose **Exchange Online**.</span></span>

    ![Captura de tela da folha de configurações mostrando a seção acesso condicional com a opção Exchange Online em destaque](../media/MAM-conditional-access-1.png)

6. <span data-ttu-id="270b0-113">Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir que somente aplicativos com suporte para as políticas de proteção de aplicativo do Intune acessem o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="270b0-113">On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online.</span></span> <span data-ttu-id="270b0-114">Ao selecionar essa opção, a lista de aplicativos com suporte é exibida.</span><span class="sxs-lookup"><span data-stu-id="270b0-114">When you select this option, the list of supported apps is displayed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="270b0-115">Todos os clientes de email do Exchange Active Sync, incluindo os de email interno no iOS e no Android que se conectam ao Exchange Online, serão impedidos de enviar ou receber emails.</span><span class="sxs-lookup"><span data-stu-id="270b0-115">All Exchange Active Sync mail clients, including the built-in mail clients on iOS and >Android that connect to Exchange Online, will be prevented from sending or receiving >email.</span></span> <span data-ttu-id="270b0-116">Em vez disso, os usuários receberão um único email informando que eles precisam usar o aplicativo de email do Outlook.</span><span class="sxs-lookup"><span data-stu-id="270b0-116">Users will instead receive a single email informing them that they need to use the >Outlook mail app.</span></span>

7. <span data-ttu-id="270b0-117">Para aplicar essa política aos usuários, abra a folha **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuário**.</span><span class="sxs-lookup"><span data-stu-id="270b0-117">To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**.</span></span> <span data-ttu-id="270b0-118">Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="270b0-118">Select one or more user groups that should get this policy.</span></span>

    ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](../media/mam-ca-add-user-group.png)

8. <span data-ttu-id="270b0-120">Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política.</span><span class="sxs-lookup"><span data-stu-id="270b0-120">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="270b0-121">Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos.</span><span class="sxs-lookup"><span data-stu-id="270b0-121">In such cases, add the group of users to the exempted user groups list.</span></span> <span data-ttu-id="270b0-122">Na folha **Exchange Online**, escolha **Grupos de usuários isentos**.</span><span class="sxs-lookup"><span data-stu-id="270b0-122">From the **Exchange Online** blade, choose **Exempted user groups**.</span></span> <span data-ttu-id="270b0-123">Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="270b0-123">Choose **Add user group** to open the list of user groups.</span></span> <span data-ttu-id="270b0-124">Selecione os grupos que você deseja isentar dessa política.</span><span class="sxs-lookup"><span data-stu-id="270b0-124">Select the groups you want to exempt from this policy.</span></span>  

## <span data-ttu-id="270b0-125">Modifique uma política existente</span><span class="sxs-lookup"><span data-stu-id="270b0-125">Modify an existing policy</span></span>
<a id="modify-an-existing-policy" class="xliff"></a>
### <span data-ttu-id="270b0-126">Adicione ou exclua grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="270b0-126">Add or delete user groups</span></span>
<a id="add-or-delete-user-groups" class="xliff"></a>

<span data-ttu-id="270b0-127">Para **excluir um grupo de usuários** da lista de **grupos de usuários com restrições**, abra a folha **Grupos de usuários com restrições**, realce o grupo de usuários que você deseja excluir e, em seguida, clique em **reticências(...)** para ver a opção **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="270b0-127">To **delete a user group** from the **restricted user groups** list, open the **Restricted user groups** blade, highlight the user group you want to delete, and click on the **ellipses(...)** to see the **Delete** option.</span></span> <span data-ttu-id="270b0-128">Escolha **Excluir** para remover o grupo de usuários da lista.</span><span class="sxs-lookup"><span data-stu-id="270b0-128">Choose **Delete** to remove the user group from the list.</span></span> <span data-ttu-id="270b0-129">Você pode seguir o mesmo procedimento para remover um grupo de usuários da lista do **grupo de usuários isentos**.</span><span class="sxs-lookup"><span data-stu-id="270b0-129">You can follow the same procedure to remove a user group from the **exempted user group** list.</span></span>


## <span data-ttu-id="270b0-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="270b0-130">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="270b0-131">Bloquear aplicativos que não têm autenticação moderna</span><span class="sxs-lookup"><span data-stu-id="270b0-131">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)
### <span data-ttu-id="270b0-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="270b0-132">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="270b0-133">Proteger dados de aplicativo com as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="270b0-133">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
