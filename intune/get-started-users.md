---
title: "Introdução aos usuários"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fc1c4f6d18fd78f455be8e333bb765080184c908
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="4f496-102">Introdução aos usuários</span><span class="sxs-lookup"><span data-stu-id="4f496-102">Get started with users</span></span>
<a id="get-started-with-users" class="xliff"></a>

![Um usuário genérico no Azure](/intune/media/generic-intune-user.png)

<span data-ttu-id="4f496-104">O Azure AD gerencia os grupos de objetos – como dispositivos e aplicativos – da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4f496-104">Azure AD manages your organization’s groups of objects – like devices and apps – and also groups of users.</span></span> <span data-ttu-id="4f496-105">Você pode agrupar usuários ou dispositivos em vez de precisar gerenciar cada dispositivo individualmente.</span><span class="sxs-lookup"><span data-stu-id="4f496-105">You can group users or devices together instead of having to manage each device individually.</span></span> <span data-ttu-id="4f496-106">Isso permite atribuir facilmente aplicativos e configurações para um grande número de usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4f496-106">This lets you easily assign apps and settings to large numbers of users and devices.</span></span>

## <span data-ttu-id="4f496-107">Como eu crio um usuário?</span><span class="sxs-lookup"><span data-stu-id="4f496-107">How do I create a user?</span></span>
<a id="how-do-i-create-a-user" class="xliff"></a>

1. <span data-ttu-id="4f496-108">Entre no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="4f496-108">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="4f496-109">Usando **Pesquisar recursos**, pesquise **Usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="4f496-109">Using **Search resources**, search for **Users and groups**.</span></span>
3. <span data-ttu-id="4f496-110">Depois de abrir a folha **Usuários e grupos**, selecione **Todos os usuários** e **+ Novo usuário**.</span><span class="sxs-lookup"><span data-stu-id="4f496-110">Once you've opened the **Users and groups** blade, select **All users**, , then select **+ New user**.</span></span>
4. <span data-ttu-id="4f496-111">Insira os detalhes do usuário, como **Nome** e **Nome de usuário**.</span><span class="sxs-lookup"><span data-stu-id="4f496-111">Enter details for the user, such as **Name** and **User name**.</span></span> <span data-ttu-id="4f496-112">A parte do nome de domínio do nome de usuário deve ser o nome de domínio inicial padrão “contoso.onmicrosoft.com” ou um nome de domínio não federado verificado como “contoso.com”.</span><span class="sxs-lookup"><span data-stu-id="4f496-112">The domain name portion of the user name must either be the initial default domain name “contoso.onmicrosoft.com” domain name, or a verified, non-federated domain name such as “contoso.com.”</span></span>
5. <span data-ttu-id="4f496-113">Em **Grupos**, escolha o grupo de teste ao qual o usuário será adicionado.</span><span class="sxs-lookup"><span data-stu-id="4f496-113">Under **Groups**, choose the test group to add the user to.</span></span>
6. <span data-ttu-id="4f496-114">Salve a senha do usuário gerada automaticamente para que você possa usá-la para fazer logon em um dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="4f496-114">Save the automatically generated user password so that you can use it to log in to a test device.</span></span> <span data-ttu-id="4f496-115">Você deve fornecer essa senha para usuários para que eles podem alterá-la para uma senha normal que pode ser lembrada.</span><span class="sxs-lookup"><span data-stu-id="4f496-115">You must give this password to users so that they can change it to a normal password that they can remember.</span></span>
7. <span data-ttu-id="4f496-116">Na folha **Usuário**, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="4f496-116">On the **User** blade, select **Create**.</span></span>

## <span data-ttu-id="4f496-117">Atribuir licenças a usuários</span><span class="sxs-lookup"><span data-stu-id="4f496-117">Assigning licenses to users</span></span>
<a id="assigning-licenses-to-users" class="xliff"></a>

<span data-ttu-id="4f496-118">Depois de criar um usuário, será necessário usar o [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="4f496-118">After you've created a user, you need to use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to assign an Intune license to that user.</span></span> <span data-ttu-id="4f496-119">Sem atribuir uma licença, não será possível registrar seus dispositivos no gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="4f496-119">Without assigning them a license, they can't enroll their device into management.</span></span>

1. <span data-ttu-id="4f496-120">Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.</span><span class="sxs-lookup"><span data-stu-id="4f496-120">Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) with the same credentials you used to sign in to Intune.</span></span>
2. <span data-ttu-id="4f496-121">Selecione **Usuários** > **Usuários Ativos** e selecione o usuário que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4f496-121">Select **Users** > **Active Users**, then select the user you previously created.</span></span>
3. <span data-ttu-id="4f496-122">Pode ser necessário aguardar um pouco para que todas as informações do usuário sejam carregadas.</span><span class="sxs-lookup"><span data-stu-id="4f496-122">You may need to wait a moment for all of the user's information to load.</span></span> <span data-ttu-id="4f496-123">Depois de carregadas, selecione **Editar** nas **Licenças de produto** do usuário.</span><span class="sxs-lookup"><span data-stu-id="4f496-123">Once it loads, select **Edit** for the user's **Product licenses**.</span></span>
4. <span data-ttu-id="4f496-124">Atribua um **Local** ao usuário e mude o Intune para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="4f496-124">Assign the user a **Location**, then switch Intune to **on**.</span></span>

 > [!NOTE]
 > <span data-ttu-id="4f496-125">Isso usa uma das suas licenças para este usuário.</span><span class="sxs-lookup"><span data-stu-id="4f496-125">This uses one of your licenses for this user.</span></span> <span data-ttu-id="4f496-126">Se você estiver usando o ambiente em tempo real, poderá desligar o uso dessa licença mais tarde para reatribuí-la a um usuário real.</span><span class="sxs-lookup"><span data-stu-id="4f496-126">If you are using your live environment, you can turn off using this license later to reassign it to a real user.</span></span>

5. <span data-ttu-id="4f496-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4f496-127">Select **Save**.</span></span>
