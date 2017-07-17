---
title: RBAC com o Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como o RBAC permite controlar quem pode executar ações e fazer alterações."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e2302b0e53254b945215aadbb13107c85f345412
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="513c6-103">RBAC (controle de administração baseada em funções) com o Intune</span><span class="sxs-lookup"><span data-stu-id="513c6-103">Role-based administration control (RBAC) with Intune</span></span>
<a id="role-based-administration-control-rbac-with-intune" class="xliff"></a>

<span data-ttu-id="513c6-104">O RBAC ajuda você a controlar quem pode realizar as várias tarefas do Intune em sua organização e a quem essas tarefas se aplicam.</span><span class="sxs-lookup"><span data-stu-id="513c6-104">RBAC helps you control who can perform various Intune tasks within your organization, and who those tasks apply to.</span></span> <span data-ttu-id="513c6-105">Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções.</span><span class="sxs-lookup"><span data-stu-id="513c6-105">You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.</span></span> <span data-ttu-id="513c6-106">Uma função é definida por:</span><span class="sxs-lookup"><span data-stu-id="513c6-106">A role is defined by:</span></span>

- <span data-ttu-id="513c6-107">**Definição de função**: o nome de uma função, os recursos gerenciados por ela e as permissões concedidas a cada recurso.</span><span class="sxs-lookup"><span data-stu-id="513c6-107">**Role definition**: The name of a role, the resources it manages, and the permissions granted for each resource.</span></span>
- <span data-ttu-id="513c6-108">**Membros**: os grupos de usuários que recebem as permissões.</span><span class="sxs-lookup"><span data-stu-id="513c6-108">**Members**: The user groups that are granted the permissions.</span></span>
- <span data-ttu-id="513c6-109">**Escopo**: os grupos de usuários ou dispositivos que podem ser gerenciados pelos membros.</span><span class="sxs-lookup"><span data-stu-id="513c6-109">**Scope**: The user or device groups that the members can manage.</span></span>
- <span data-ttu-id="513c6-110">**Atribuição**: após a configuração da definição, dos membros e do escopo, a função é atribuída.</span><span class="sxs-lookup"><span data-stu-id="513c6-110">**Assignment**: When the definition, members, and scope have been configured, the role is assigned.</span></span>

![Exemplo de RBAC do Intune](./media/intune-rbac-1.PNG)

<span data-ttu-id="513c6-112">Começando no novo portal do Intune, o **Azure AD (Azure Active Directory)** fornece duas Funções do Diretório que podem ser usadas com o Intune.</span><span class="sxs-lookup"><span data-stu-id="513c6-112">Starting at the new Intune portal, **Azure Active Directory (Azure AD)** provides two Directory Roles which can be used with Intune.</span></span> <span data-ttu-id="513c6-113">Essas funções recebem permissão total para realizar todas as atividades no Intune:</span><span class="sxs-lookup"><span data-stu-id="513c6-113">These roles are granted full permission to perform all activities in Intune:</span></span>

- <span data-ttu-id="513c6-114">**Administrador Global:** os usuários com essa função têm acesso a todos os recursos administrativos do Azure AD, bem como a serviços federados ao Azure AD, como o Exchange Online, SharePoint Online e Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="513c6-114">**Global Administrator:** Users with this role have access to all administrative features in Azure AD, as well as services that federate to Azure AD like Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="513c6-115">A pessoa que se inscreve no locatário do Azure AD se torna um administrador global.</span><span class="sxs-lookup"><span data-stu-id="513c6-115">The person who signs up for the Azure AD tenant becomes a global administrator.</span></span> <span data-ttu-id="513c6-116">Somente os administradores globais podem atribuir outras funções de administrador do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="513c6-116">Only global administrators can assign other Azure AD administrator roles.</span></span> <span data-ttu-id="513c6-117">Pode haver mais de um administrador global na sua organização.</span><span class="sxs-lookup"><span data-stu-id="513c6-117">There can be more than one global administrator at your organization.</span></span> <span data-ttu-id="513c6-118">Os administradores globais podem redefinir a senha de qualquer usuário e de todos os outros administradores.</span><span class="sxs-lookup"><span data-stu-id="513c6-118">Global admins can reset the password for any user and all other administrators.</span></span>

- <span data-ttu-id="513c6-119">**Administrador de Serviços do Intune:** os usuários com essa função têm permissões globais no Intune quando o serviço está presente.</span><span class="sxs-lookup"><span data-stu-id="513c6-119">**Intune Service Administrator:** Users with this role have global permissions within Intune when the service is present.</span></span> <span data-ttu-id="513c6-120">Além disso, essa função fornece a capacidade de gerenciar usuários, dispositivos e criar e gerenciar grupos.</span><span class="sxs-lookup"><span data-stu-id="513c6-120">Additionally, this role provides the ability to manage users, devices, and create and manage groups.</span></span>

- <span data-ttu-id="513c6-121">**Administrador de acesso condicional:** os usuários com essa função só têm permissões para exibir, criar, modificar e excluir as políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="513c6-121">**Conditional Access Administrator:** Users with this role only have permissions to view, create, modify and delete conditional access policies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="513c6-122">A função Administrador de Serviços do Intune não fornece a capacidade de gerenciar as configurações de acesso condicional do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="513c6-122">The Intune Service Administrator role does not provide the ability to manage Azure AD’s conditional access settings.</span></span>

    > [!TIP]
    > <span data-ttu-id="513c6-123">O Intune também mostra três extensões do Azure AD: **Usuários**, **Grupos** e **Acesso condicional**, que são controlados com o uso do RBAC do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="513c6-123">Intune also shows three Azure AD extensions: **Users**, **Groups** and **Conditional access** which are controlled using Azure AD RBAC.</span></span> <span data-ttu-id="513c6-124">Além disso, o **Administrador de Contas de Usuário** apenas realiza as atividades do usuário/grupo do AAD e não tem permissões totais para realizar todas as atividades no Intune.</span><span class="sxs-lookup"><span data-stu-id="513c6-124">Additionally, the **User Account Administrator** only performs AAD user/group activities and does not have full permissions to perform all activities in Intune.</span></span> <span data-ttu-id="513c6-125">Consulte [RBAC com o Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="513c6-125">Refer to [RBAC with Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) for more details.</span></span>

## <span data-ttu-id="513c6-126">Funções criadas no console clássico do Intune</span><span class="sxs-lookup"><span data-stu-id="513c6-126">Roles created in the Intune classic console</span></span>
<a id="roles-created-in-the-intune-classic-console" class="xliff"></a>

<span data-ttu-id="513c6-127">Somente os usuários **Administradores de Serviços** do Intune com permissões “Totais” são migrados do console clássico do Intune para o Intune no Azure.</span><span class="sxs-lookup"><span data-stu-id="513c6-127">Only Intune **Service Administrators** users with "Full" permissions get migrated from the Intune classic console to Intune on Azure.</span></span> <span data-ttu-id="513c6-128">Você precisa reatribuir o acesso “Somente Leitura” ou “Assistência técnica” aos usuários **Administradores de Serviços** do Intune nas funções do Intune no portal do Azure e removê-los do portal clássico.</span><span class="sxs-lookup"><span data-stu-id="513c6-128">You need to re-assign Intune **Service Administrators** users with "Read-Only" or "Helpdesk" access into the Intune roles in the Azure portal, and remove them from the classic portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="513c6-129">Talvez seja necessário manter o acesso de Administrador de Serviços do Intune no console clássico, caso os administradores ainda precisem ter acesso para gerenciar computadores usando o Intune.</span><span class="sxs-lookup"><span data-stu-id="513c6-129">You might need to keep the Intune Service Administrator access in the classic console if your admins still need access to manage PC’s using with Intune.</span></span>

## <span data-ttu-id="513c6-130">Funções internas</span><span class="sxs-lookup"><span data-stu-id="513c6-130">Built-in roles</span></span>
<a id="built-in-roles" class="xliff"></a>

<span data-ttu-id="513c6-131">As seguintes funções são internas do Intune e você pode atribuí-las a grupos sem nenhuma outra configuração:</span><span class="sxs-lookup"><span data-stu-id="513c6-131">The following roles are built into Intune and you can assign them to groups with no further configuration:</span></span>

- <span data-ttu-id="513c6-132">**Operador do Suporte Técnico**: realiza tarefas remotas em usuários e dispositivos e pode atribuir aplicativos ou políticas a usuários ou dispositivos.</span><span class="sxs-lookup"><span data-stu-id="513c6-132">**Help Desk Operator**: Performs remote tasks on users and devices and can assign applications or policies to users or devices.</span></span> 
- <span data-ttu-id="513c6-133">**Gerente de Política e Perfil**: gerencia a política de conformidade, os perfis de configuração, o registro da Apple e os identificadores de dispositivo corporativo.</span><span class="sxs-lookup"><span data-stu-id="513c6-133">**Policy and Profile Manager**: Manages compliance policy, configuration profiles, Apple enrollment and corporate device identifiers.</span></span>
- <span data-ttu-id="513c6-134">**Operador Somente Leitura**: exibe informações de usuário, dispositivo, registro, configuração e aplicativo, mas não pode fazer alterações no Intune.</span><span class="sxs-lookup"><span data-stu-id="513c6-134">**Read Only Operator**: Views user, device, enrollment, configuration and application information and cannot make changes to Intune.</span></span>
- <span data-ttu-id="513c6-135">**Gerente de Aplicativo**: gerencia aplicativos móveis e gerenciados e pode ler informações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="513c6-135">**Application Manager**: Manages mobile and managed applications, and can read device information.</span></span>

### <span data-ttu-id="513c6-136">Para atribuir uma função interna</span><span class="sxs-lookup"><span data-stu-id="513c6-136">To assign a built-in role</span></span>
<a id="to-assign-a-built-in-role" class="xliff"></a>

1. <span data-ttu-id="513c6-137">Nas **funções do Intune**, escolha a função interna que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="513c6-137">On the **Intune roles**, choose the built-in role you want to assign.</span></span>

2. <span data-ttu-id="513c6-138">Na folha <*nome da função*> – **Propriedades**, escolha **Gerenciar** e, em seguida, **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="513c6-138">On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="513c6-139">Não é possível excluir nem editar as funções internas</span><span class="sxs-lookup"><span data-stu-id="513c6-139">You cannot delete or edit the built-in roles</span></span>
    
3. <span data-ttu-id="513c6-140">Na folha da função personalizada, escolha **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="513c6-140">On the custom role blade, choose **Assign**.</span></span>

4. <span data-ttu-id="513c6-141">Na folha **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e, em seguida, escolha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="513c6-141">On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:</span></span>
    - <span data-ttu-id="513c6-142">**Membros** – Selecione um grupo que contém o usuário para o qual você deseja conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="513c6-142">**Members** - Select a group that contains the user you want to give the permissions to.</span></span>
    - <span data-ttu-id="513c6-143">**Escopo** – Selecione um grupo que contém os usuários que o membro acima terá permissão para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="513c6-143">**Scope** - Select a group containing the users who the member above will be allowed to manage.</span></span>
<br></br>
5. <span data-ttu-id="513c6-144">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="513c6-144">When you are done, click **OK**.</span></span> <span data-ttu-id="513c6-145">A nova atribuição é exibida na lista de atribuições.</span><span class="sxs-lookup"><span data-stu-id="513c6-145">The new assignment is displayed in the list of assignments.</span></span>

### <span data-ttu-id="513c6-146">Tabela do RBAC do Intune</span><span class="sxs-lookup"><span data-stu-id="513c6-146">Intune RBAC table</span></span>
<a id="intune-rbac-table" class="xliff"></a>

- <span data-ttu-id="513c6-147">Baixe a [tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) para ver mais detalhes sobre o que cada função pode fazer.</span><span class="sxs-lookup"><span data-stu-id="513c6-147">Download the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to see more details on what each role can do.</span></span>

## <span data-ttu-id="513c6-148">Funções personalizadas</span><span class="sxs-lookup"><span data-stu-id="513c6-148">Custom roles</span></span>
<a id="custom-roles" class="xliff"></a>

<span data-ttu-id="513c6-149">Você pode criar uma função personalizada que inclui as permissões necessárias para uma função de trabalho específica.</span><span class="sxs-lookup"><span data-stu-id="513c6-149">You can create a custom role that includes any permissions required for a specific job function.</span></span> <span data-ttu-id="513c6-150">Por exemplo, se um grupo do departamento de TI gerencia aplicativos, políticas e perfis de configuração, você pode adicionar todas essas permissões juntas em uma única função personalizada.</span><span class="sxs-lookup"><span data-stu-id="513c6-150">For example, if an IT department group manages applications, policies and configuration profiles, you can add all those permissions together in one custom role.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="513c6-151">Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:</span><span class="sxs-lookup"><span data-stu-id="513c6-151">To create, edit, or assign roles, your account must have one of the following permissions in Azure AD:</span></span>
> - <span data-ttu-id="513c6-152">**Administrador Global**</span><span class="sxs-lookup"><span data-stu-id="513c6-152">**Global Administrator**</span></span>
> - <span data-ttu-id="513c6-153">**Administrador de Serviços do Intune**</span><span class="sxs-lookup"><span data-stu-id="513c6-153">**Intune Service Administrator**</span></span>

### <span data-ttu-id="513c6-154">Para criar uma função personalizada</span><span class="sxs-lookup"><span data-stu-id="513c6-154">To create a custom role</span></span>
<a id="to-create-a-custom-role" class="xliff"></a>

1. <span data-ttu-id="513c6-155">Entre no [portal do Azure](https://portal.azure.com) com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="513c6-155">Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials.</span></span>

2. <span data-ttu-id="513c6-156">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="513c6-156">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="513c6-157">Escolha **Intune**. O Painel do Intune é aberto. Escolha **Funções do Intune**.</span><span class="sxs-lookup"><span data-stu-id="513c6-157">Choose **Intune**, the Intune Dashboard opens, choose **Intune roles**.</span></span>

4. <span data-ttu-id="513c6-158">Na folha **Funções do Intune**, escolha **Funções do Intune** e, depois, **Adicionar personalizada**.</span><span class="sxs-lookup"><span data-stu-id="513c6-158">On the **Intune roles** blade, choose **Intune roles**, choose **Add custom**.</span></span>

5. <span data-ttu-id="513c6-159">Na folha **Adicionar Função Personalizada**, insira um nome e uma descrição para a nova função e clique em **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="513c6-159">On the **Add Custom Role** blade, enter a name and description for the new role, then click **Permissions**.</span></span>

3. <span data-ttu-id="513c6-160">Na folha **Permissões**, escolha as permissões que você deseja usar com essa função.</span><span class="sxs-lookup"><span data-stu-id="513c6-160">On the **Permissions** blade, choose the permissions you want to use with this role.</span></span> <span data-ttu-id="513c6-161">Use a [tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) para ajudá-lo a decidir quais permissões você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="513c6-161">Use the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to help you decide which permissions you want to apply.</span></span>

4. <span data-ttu-id="513c6-162">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="513c6-162">When you are done, choose **OK**.</span></span>

5. <span data-ttu-id="513c6-163">Na folha **Adicionar Função Personalizada**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="513c6-163">On the **Add Custom Role** blade, click **Create**.</span></span> <span data-ttu-id="513c6-164">A nova função é exibida na lista da folha **Funções do Intune**.</span><span class="sxs-lookup"><span data-stu-id="513c6-164">The new role is displayed in the list on the **Intune roles** blade.</span></span>

### <span data-ttu-id="513c6-165">Para atribuir uma função personalizada</span><span class="sxs-lookup"><span data-stu-id="513c6-165">To assign a custom role</span></span>
<a id="to-assign-a-custom-role" class="xliff"></a>

1. <span data-ttu-id="513c6-166">Nas **funções do Intune**, escolha a função personalizada que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="513c6-166">On the **Intune roles**, choose the custom role you want to assign.</span></span>

2. <span data-ttu-id="513c6-167">Na folha <*nome da função*> – **Propriedades**, escolha **Gerenciar** e, em seguida, **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="513c6-167">On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**.</span></span> <span data-ttu-id="513c6-168">Nessa folha, também é possível editar ou excluir funções existentes.</span><span class="sxs-lookup"><span data-stu-id="513c6-168">On this blade, you can also edit or delete existing roles.</span></span>

3. <span data-ttu-id="513c6-169">Na folha da função personalizada, escolha **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="513c6-169">On the custom role blade, choose **Assign**.</span></span>

4. <span data-ttu-id="513c6-170">Na folha **Atribuições de Função**, insira um **Nome** e uma **Descrição** opcional para a atribuição e, em seguida, escolha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="513c6-170">On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:</span></span>
    - <span data-ttu-id="513c6-171">**Membros** – Selecione um grupo que contém o usuário para o qual você deseja conceder permissões.</span><span class="sxs-lookup"><span data-stu-id="513c6-171">**Members** - Select a group that contains the user you want to give the permissions to.</span></span>
    - <span data-ttu-id="513c6-172">**Escopo** – Selecione um grupo que contém os usuários que o membro acima terá permissão para gerenciar.</span><span class="sxs-lookup"><span data-stu-id="513c6-172">**Scope** - Select a group containing the users who the member above will be allowed to manage.</span></span>
<br></br>
5. <span data-ttu-id="513c6-173">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="513c6-173">When you are done, click **OK**.</span></span> <span data-ttu-id="513c6-174">A nova atribuição é exibida na lista de atribuições.</span><span class="sxs-lookup"><span data-stu-id="513c6-174">The new assignment is displayed in the list of assignments.</span></span>

## <span data-ttu-id="513c6-175">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="513c6-175">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="513c6-176">Usar a função de operador de assistência técnica do Intune com o portal de solução de problemas</span><span class="sxs-lookup"><span data-stu-id="513c6-176">Use the Intune Helpdesk operator role with the troubleshooting portal</span></span>](help-desk-operators.md)

## <span data-ttu-id="513c6-177">Consulte também</span><span class="sxs-lookup"><span data-stu-id="513c6-177">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="513c6-178">Atribuir funções usando o Azure AD</span><span class="sxs-lookup"><span data-stu-id="513c6-178">Assign roles using Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)