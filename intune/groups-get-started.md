---
title: "Grupos clássicos do Intune no Portal do Azure"
titleSuffix: Intune on Azure
description: "Conheça as novidades dos grupos no portal do Intune no Azure"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 323f384d-8a76-4adc-999b-e508d641bfa1
ms.custom: intune-azure
ms.openlocfilehash: 3e7cf02ed43507eabdf6038940058f94eb09b0fa
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
<<<<<<< HEAD
# <span data-ttu-id="0b364-103">Grupos clássicos do Intune no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="0b364-103">Intune classic groups in the Azure portal</span></span>
=======
# Grupos clássicos do Intune no Portal do Azure
>>>>>>> live
<a id="intune-classic-groups-in-the-azure-portal" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0b364-104">Ouvimos seus comentários e fizemos mudanças da maneira de trabalhar com grupos no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="0b364-104">We've heard your feedback and have made changes to how you work with groups in Microsoft Intune.</span></span>
<span data-ttu-id="0b364-105">Se você estiver usando o Intune no Portal do Azure, seus grupos do Intune serão migrados para os grupos de segurança do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0b364-105">If you are using Intune from the Azure portal, your Intune groups have been migrated to Azure Active Directory security groups.</span></span>

<<<<<<< HEAD
<span data-ttu-id="0b364-106">A vantagem é que você usará a mesma experiência de grupos em todos os seus aplicativos do Enterprise Mobility + Security e Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b364-106">The benefit to you is that you now use the same groups experience across all of your Enterprise Mobility + Security, and Azure AD apps.</span></span> <span data-ttu-id="0b364-107">Além disso, você pode usar o PowerShell e a API do Graph para estender e personalizar essa nova funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="0b364-107">Additionally, you can use PowerShell and Graph API to extend and customize this new functionality.</span></span>

<span data-ttu-id="0b364-108">Os grupos de segurança do Azure AD dão suporte a todos os tipos de implantações do Intune em usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0b364-108">Azure AD security groups support all types of Intune deployments to both users and devices.</span></span> <span data-ttu-id="0b364-109">Além disso, é possível usar os grupos dinâmicos do Azure AD que são atualizados automaticamente de acordo com os atributos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="0b364-109">Additionally, you can use Azure AD dynamic groups that automatically update based on the attributes you supply.</span></span> <span data-ttu-id="0b364-110">Por exemplo, você poderá criar um grupo de dispositivos que executa o iOS 9.</span><span class="sxs-lookup"><span data-stu-id="0b364-110">For example, you could create a group of devices that run iOS 9.</span></span> <span data-ttu-id="0b364-111">Sempre que um dispositivo com iOS 9 é registrado, ele é exibido automaticamente no grupo dinâmico.</span><span class="sxs-lookup"><span data-stu-id="0b364-111">Whenever a device running iOS 9 enrolls, the device automatically appears in the dynamic group.</span></span>

## <span data-ttu-id="0b364-112">O que não está disponível?</span><span class="sxs-lookup"><span data-stu-id="0b364-112">What is not available?</span></span>
=======
A vantagem é que você usará a mesma experiência de grupos em todos os seus aplicativos do Enterprise Mobility + Security e Azure AD. Além disso, você pode usar o PowerShell e a API do Graph para estender e personalizar essa nova funcionalidade.

Os grupos de segurança do Azure AD dão suporte a todos os tipos de implantações do Intune em usuários e dispositivos. Além disso, é possível usar os grupos dinâmicos do Azure AD que são atualizados automaticamente de acordo com os atributos fornecidos. Por exemplo, você poderá criar um grupo de dispositivos que executa o iOS 9. Sempre que um dispositivo com iOS 9 é registrado, ele é exibido automaticamente no grupo dinâmico.

## O que não está disponível?
>>>>>>> live
<a id="what-is-not-available" class="xliff"></a>

<span data-ttu-id="0b364-113">Alguns dos recursos de grupos do Intune que você talvez pode ter usado anteriormente não estão disponíveis no Azure AD:</span><span class="sxs-lookup"><span data-stu-id="0b364-113">Some of the Intune groups capabilities you previously might have used are not available in Azure AD:</span></span>

<<<<<<< HEAD
- <span data-ttu-id="0b364-114">Os grupos **Usuários Desagrupados** e **Dispositivos Desagrupados** do Intune não estão mais disponíveis.</span><span class="sxs-lookup"><span data-stu-id="0b364-114">The **Ungrouped Users** and **Ungrouped Devices** Intune groups are no longer available.</span></span>
- <span data-ttu-id="0b364-115">A opção para **Excluir membros específicos** de um grupo atualmente não existe no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="0b364-115">The option to **Exclude specific members** from a group does not exist in the Azure portal.</span></span> <span data-ttu-id="0b364-116">No entanto, você poderá usar um grupo de segurança do Azure AD com regras avançadas para replicar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="0b364-116">You can, however, use an Azure AD security group with advanced rules to replicate this behavior.</span></span> <span data-ttu-id="0b364-117">Por exemplo, é possível criar uma regra avançada que inclui todas as pessoas do seu departamento de vendas em um grupo de segurança e exclui os grupos que têm a palavra “Assistente” em seu título, com essa regra avançada:</span><span class="sxs-lookup"><span data-stu-id="0b364-117">For example, to create an advanced rule that includes all people in your Sales department in a security group, but excludes those groups with the word "Assistant" in their title, you could use this advanced rule:</span></span>
=======
- Os grupos **Usuários Desagrupados** e **Dispositivos Desagrupados** do Intune não estão mais disponíveis.
- A opção para **Excluir membros específicos** de um grupo atualmente não existe no Portal do Azure. No entanto, você poderá usar um grupo de segurança do Azure AD com regras avançadas para replicar esse comportamento. Por exemplo, é possível criar uma regra avançada que inclui todas as pessoas do seu departamento de vendas em um grupo de segurança e exclui os grupos que têm a palavra “Assistente” em seu título, com essa regra avançada:
>>>>>>> live

  <span data-ttu-id="0b364-118">`(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.</span><span class="sxs-lookup"><span data-stu-id="0b364-118">`(user.department -eq "Sales") -and -not (user.jobTitle -contains "Assistant")`.</span></span>
- <span data-ttu-id="0b364-119">O grupo **Todos os Dispositivos Gerenciados pelo Exchange ActiveSync** no console do Intune não foi migrado para o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b364-119">The **All Exchange ActiveSync Managed Devices** group in the Intune console was not migrated to Azure AD.</span></span> <span data-ttu-id="0b364-120">No entanto, você ainda poderá acessar informações sobre dispositivos gerenciados pelo EAS no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="0b364-120">You can, however, still access information about EAS-managed devices from the Azure portal.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="0b364-121">Como começar?</span><span class="sxs-lookup"><span data-stu-id="0b364-121">How to get started?</span></span>
<a id="how-to-get-started" class="xliff"></a>

- <span data-ttu-id="0b364-122">Leia os tópicos a seguir para saber mais sobre grupos de segurança do Azure AD e como eles funcionam:</span><span class="sxs-lookup"><span data-stu-id="0b364-122">Read the following topics to learn about Azure AD security groups and how they work:</span></span>
    -  <span data-ttu-id="0b364-123">[Gerenciando o acesso a recursos com grupos do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).</span><span class="sxs-lookup"><span data-stu-id="0b364-123">[Managing access to resources with Azure Active Directory groups](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).</span></span>
    -  <span data-ttu-id="0b364-124">[Gerenciando grupos no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).</span><span class="sxs-lookup"><span data-stu-id="0b364-124">[Managing groups in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).</span></span>
    -  <span data-ttu-id="0b364-125">[Usando atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).</span><span class="sxs-lookup"><span data-stu-id="0b364-125">[Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).</span></span>
-  <span data-ttu-id="0b364-126">Garanta que todos os administradores que precisam criar grupos são adicionados à função **Administrador de Serviços do Intune** do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b364-126">Ensure that admins who need to create groups are added to the **Intune Service Administrator** Azure AD role.</span></span> <span data-ttu-id="0b364-127">Observe que a função Administrador de Serviços do Azure AD não tem permissões para **Gerenciar Grupos**.</span><span class="sxs-lookup"><span data-stu-id="0b364-127">The Azure AD Service Admin role does not have **Manage Group** permissions.</span></span>
-  <span data-ttu-id="0b364-128">Se os grupos do Intune usaram a opção **Excluir membros específicos**, decida se você pode recriar esses grupos sem exclusões ou se precisa de regras avançadas para atender às necessidades corporativas.</span><span class="sxs-lookup"><span data-stu-id="0b364-128">If your Intune groups used the **Exclude specific members**  option, decide whether you can redesign these groups without exclusions, or if you need advanced rules to meet business needs.</span></span>


## <span data-ttu-id="0b364-129">O que aconteceu com os grupos do Intune?</span><span class="sxs-lookup"><span data-stu-id="0b364-129">What happened to Intune groups?</span></span>
<a id="what-happened-to-intune-groups" class="xliff"></a>
<span data-ttu-id="0b364-130">Quando os grupos são migrados do portal clássico do Intune para o portal do Azure, as seguintes regras são aplicadas:</span><span class="sxs-lookup"><span data-stu-id="0b364-130">When groups are migrated from the classic Intune portal to Intune in the Azure portal, the following rules are applied:</span></span>

| <span data-ttu-id="0b364-131">Grupos no Intune clássico</span><span class="sxs-lookup"><span data-stu-id="0b364-131">Groups in classic Intune</span></span>|<span data-ttu-id="0b364-132">Grupos no Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-132">Groups in Azure AD</span></span>|
=======
## Como começar?
<a id="how-to-get-started" class="xliff"></a>

- Leia os tópicos a seguir para saber mais sobre grupos de segurança do Azure AD e como eles funcionam:
    -  [Gerenciando o acesso a recursos com grupos do Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-manage-groups/).
    -  [Gerenciando grupos no Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-manage-groups/).
    -  [Usando atributos para criar regras avançadas](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/).
-  Garanta que todos os administradores que precisam criar grupos são adicionados à função **Administrador de Serviços do Intune** do Azure AD. Observe que a função Administrador de Serviços do Azure AD não tem permissões para **Gerenciar Grupos**.
-  Se os grupos do Intune usaram a opção **Excluir membros específicos**, decida se você pode recriar esses grupos sem exclusões ou se precisa de regras avançadas para atender às necessidades corporativas.


## O que aconteceu com os grupos do Intune?
<a id="what-happened-to-intune-groups" class="xliff"></a>
Quando os grupos são migrados do portal clássico do Intune para o portal do Azure, as seguintes regras são aplicadas:

| Grupos no Intune clássico|Grupos no Azure AD|
>>>>>>> live
|-----------------------------------------------------------------------|-------------------------------------------------------------|
|<span data-ttu-id="0b364-133">Grupo de usuários estático</span><span class="sxs-lookup"><span data-stu-id="0b364-133">Static user group</span></span>|<span data-ttu-id="0b364-134">Grupo de segurança estático do Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-134">Static Azure AD security group</span></span>|
|<span data-ttu-id="0b364-135">Grupo de usuários dinâmico</span><span class="sxs-lookup"><span data-stu-id="0b364-135">Dynamic user group</span></span>|<span data-ttu-id="0b364-136">Grupos de segurança estáticos do Azure AD com uma hierarquia de grupos de segurança do Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-136">Static Azure AD security groups with an Azure AD security group hierarchy</span></span>|
|<span data-ttu-id="0b364-137">Grupo de dispositivos estático</span><span class="sxs-lookup"><span data-stu-id="0b364-137">Static device group</span></span>|<span data-ttu-id="0b364-138">Grupo de segurança estático do Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-138">Static Azure AD security group</span></span>|
|<span data-ttu-id="0b364-139">Grupo de dispositivos dinâmico</span><span class="sxs-lookup"><span data-stu-id="0b364-139">Dynamic device group</span></span>|<span data-ttu-id="0b364-140">Grupo de segurança dinâmico do Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-140">Dynamic Azure AD security group</span></span>|
|<span data-ttu-id="0b364-141">Um grupo com uma condição de inclusão</span><span class="sxs-lookup"><span data-stu-id="0b364-141">A group with an include condition</span></span>|<span data-ttu-id="0b364-142">Grupo de segurança estático do Azure AD que contém membros estáticos ou dinâmicos da condição de inclusão no Intune</span><span class="sxs-lookup"><span data-stu-id="0b364-142">Static Azure AD security group containing any static or dynamic members from the include condition in Intune</span></span>|
|<span data-ttu-id="0b364-143">Um grupo com uma condição de exclusão</span><span class="sxs-lookup"><span data-stu-id="0b364-143">A group with an exclude condition</span></span>|<span data-ttu-id="0b364-144">Não migrado</span><span class="sxs-lookup"><span data-stu-id="0b364-144">Not migrated</span></span>|
|<span data-ttu-id="0b364-145">Grupos internos:</span><span class="sxs-lookup"><span data-stu-id="0b364-145">The built-in groups:</span></span><br><span data-ttu-id="0b364-146">- **Todos os usuários**</span><span class="sxs-lookup"><span data-stu-id="0b364-146">- **All Users**</span></span><br><span data-ttu-id="0b364-147">- **Usuários desagrupados**</span><span class="sxs-lookup"><span data-stu-id="0b364-147">- **Ungrouped Users**</span></span><br><span data-ttu-id="0b364-148">- **Todos os dispositivos**</span><span class="sxs-lookup"><span data-stu-id="0b364-148">- **All Devices**</span></span><br><span data-ttu-id="0b364-149">- **Dispositivos desagrupados**</span><span class="sxs-lookup"><span data-stu-id="0b364-149">- **Ungrouped devices**</span></span><br><span data-ttu-id="0b364-150">- **Todos os computadores**</span><span class="sxs-lookup"><span data-stu-id="0b364-150">- **All Computers**</span></span><br><span data-ttu-id="0b364-151">- **Todos os dispositivos móveis**</span><span class="sxs-lookup"><span data-stu-id="0b364-151">- **All Mobile Devices**</span></span><br><span data-ttu-id="0b364-152">- **Todos os dispositivos gerenciados do MDM**</span><span class="sxs-lookup"><span data-stu-id="0b364-152">- **All-MDM managed devices**</span></span><br><span data-ttu-id="0b364-153">- **Todos os dispositivos gerenciados do EAS**</span><span class="sxs-lookup"><span data-stu-id="0b364-153">- **All EAS-managed devices**</span></span>|<span data-ttu-id="0b364-154">Grupos de segurança do Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-154">Azure AD security groups</span></span>|

<<<<<<< HEAD
## <span data-ttu-id="0b364-155">Hierarquia de grupos</span><span class="sxs-lookup"><span data-stu-id="0b364-155">Group hierarchy</span></span>
=======
## Hierarquia de grupos
>>>>>>> live
<a id="group-hierarchy" class="xliff"></a>

<span data-ttu-id="0b364-156">No console clássico do Intune, todos os grupos tinham um grupo pai.</span><span class="sxs-lookup"><span data-stu-id="0b364-156">In the classic Intune console, all groups had a parent group.</span></span> <span data-ttu-id="0b364-157">Os grupos podem conter apenas membros do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="0b364-157">Groups could only contain members of their parent group.</span></span> <span data-ttu-id="0b364-158">No Azure AD, os grupos filhos podem conter membros que não fazem parte do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="0b364-158">In Azure AD, child groups can contain members not in their parent group.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="0b364-159">Atributos do grupo</span><span class="sxs-lookup"><span data-stu-id="0b364-159">Group attributes</span></span>
<a id="group-attributes" class="xliff"></a>
<span data-ttu-id="0b364-160">Os atributos são propriedades do dispositivo que podem ser usados na definição de grupos.</span><span class="sxs-lookup"><span data-stu-id="0b364-160">Attributes are device properties that may be used in defining groups.</span></span> <span data-ttu-id="0b364-161">Esta tabela descreve como esses critérios são migrados para grupos de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b364-161">This table describes how those criteria migrate to Azure AD security groups.</span></span>
=======
## Atributos do grupo
<a id="group-attributes" class="xliff"></a>
Os atributos são propriedades do dispositivo que podem ser usados na definição de grupos. Esta tabela descreve como esses critérios são migrados para grupos de segurança do Azure AD.
>>>>>>> live

| <span data-ttu-id="0b364-162">Atributo no Intune</span><span class="sxs-lookup"><span data-stu-id="0b364-162">Attribute in Intune</span></span>|<span data-ttu-id="0b364-163">Atributo no Azure AD</span><span class="sxs-lookup"><span data-stu-id="0b364-163">Attribute in Azure AD</span></span>|
|-----------------------------------------------------------------------|-------------------------------------------------------------|
<<<<<<< HEAD
|<span data-ttu-id="0b364-164">Atributo de Unidade Organizacional (OU) para grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0b364-164">Organizational Unit (OU) attribute for device groups</span></span>|<span data-ttu-id="0b364-165">Atributo OU para grupos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="0b364-165">OU attribute for dynamic groups.</span></span>|
|<span data-ttu-id="0b364-166">Atributo de nome de domínio para grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0b364-166">Domain name attribute for device groups</span></span>|<span data-ttu-id="0b364-167">Atributo de Nome de domínio para grupos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="0b364-167">Domain Name attribute for dynamic groups.</span></span>|
|<span data-ttu-id="0b364-168">Grupo de segurança como um atributo para grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="0b364-168">Security group as an attribute for user groups</span></span>|<span data-ttu-id="0b364-169">Grupos não podem ser atributos em consultas dinâmicas do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0b364-169">Groups cannot be attributes in Azure AD dynamic queries.</span></span> <span data-ttu-id="0b364-170">Grupos dinâmicos podem conter somente atributos específicos de dispositivo ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="0b364-170">Dynamic groups can only contain user or device-specific attributes.</span></span>|
|<span data-ttu-id="0b364-171">Atributo de gerente para grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="0b364-171">Manager attribute for user groups</span></span>|<span data-ttu-id="0b364-172">Regra avançada para atributo de *gerente* em grupos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="0b364-172">Advanced Rule for *manager* attribute in dynamic groups</span></span>|
|<span data-ttu-id="0b364-173">Todos os usuários do grupo de usuário pai</span><span class="sxs-lookup"><span data-stu-id="0b364-173">All users from the parent user group</span></span>|<span data-ttu-id="0b364-174">Grupo estático com aquele grupo como membro</span><span class="sxs-lookup"><span data-stu-id="0b364-174">Static group with that group as a member</span></span>|
|<span data-ttu-id="0b364-175">Todos os dispositivos móveis do grupo de dispositivo pai</span><span class="sxs-lookup"><span data-stu-id="0b364-175">All mobile devices from the parent device group</span></span>|<span data-ttu-id="0b364-176">Grupo estático com aquele grupo como membro</span><span class="sxs-lookup"><span data-stu-id="0b364-176">Static group with that group as a member</span></span>|
|<span data-ttu-id="0b364-177">Todos os dispositivos móveis gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="0b364-177">All mobile devices managed by Intune</span></span>|<span data-ttu-id="0b364-178">Atributo do Tipo de Gerenciamento com 'MDM' como valor para grupo dinâmico</span><span class="sxs-lookup"><span data-stu-id="0b364-178">Management Type attribute with ‘MDM’ as value for dynamic group</span></span>|
|<span data-ttu-id="0b364-179">Grupos aninhados dentro de grupos estáticos</span><span class="sxs-lookup"><span data-stu-id="0b364-179">Nested groups within static groups</span></span> |<span data-ttu-id="0b364-180">Grupos aninhados dentro de grupos estáticos</span><span class="sxs-lookup"><span data-stu-id="0b364-180">Nested groups within static groups</span></span>|
|<span data-ttu-id="0b364-181">Grupos aninhados dentro de grupos dinâmicos</span><span class="sxs-lookup"><span data-stu-id="0b364-181">Nested groups within dynamic groups</span></span>|<span data-ttu-id="0b364-182">Grupo dinâmico com um nível de aninhamento</span><span class="sxs-lookup"><span data-stu-id="0b364-182">Dynamic group with one level of nesting</span></span>|

## <span data-ttu-id="0b364-183">O que acontece com as políticas e os aplicativos já implantados?</span><span class="sxs-lookup"><span data-stu-id="0b364-183">What happens to policies and apps you previously deployed?</span></span>
<a id="what-happens-to-policies-and-apps-you-previously-deployed" class="xliff"></a>

<span data-ttu-id="0b364-184">As políticas e os aplicativos continuam sendo implantados em grupos, exatamente como antes.</span><span class="sxs-lookup"><span data-stu-id="0b364-184">Policies and apps continue to be deployed to groups, just like before.</span></span> <span data-ttu-id="0b364-185">No entanto, agora você gerenciará esses grupos no Portal do Azure, em vez de no console do Intune clássico.</span><span class="sxs-lookup"><span data-stu-id="0b364-185">However, you now manage these groups from the Azure portal, instead of the classic Intune console.</span></span>
=======
|Atributo de Unidade Organizacional (OU) para grupos de dispositivos|Atributo OU para grupos dinâmicos.|
|Atributo de nome de domínio para grupos de dispositivos|Atributo de Nome de domínio para grupos dinâmicos.|
|Grupo de segurança como um atributo para grupos de usuários|Grupos não podem ser atributos em consultas dinâmicas do Azure AD. Grupos dinâmicos podem conter somente atributos específicos de dispositivo ou de usuário.|
|Atributo de gerente para grupos de usuários|Regra avançada para atributo de *gerente* em grupos dinâmicos|
|Todos os usuários do grupo de usuário pai|Grupo estático com aquele grupo como membro|
|Todos os dispositivos móveis do grupo de dispositivo pai|Grupo estático com aquele grupo como membro|
|Todos os dispositivos móveis gerenciados pelo Intune|Atributo do Tipo de Gerenciamento com 'MDM' como valor para grupo dinâmico|
|Grupos aninhados dentro de grupos estáticos |Grupos aninhados dentro de grupos estáticos|
|Grupos aninhados dentro de grupos dinâmicos|Grupo dinâmico com um nível de aninhamento|

## O que acontece com as políticas e os aplicativos já implantados?
<a id="what-happens-to-policies-and-apps-you-previously-deployed" class="xliff"></a>

As políticas e os aplicativos continuam sendo implantados em grupos, exatamente como antes. No entanto, agora você gerenciará esses grupos no Portal do Azure, em vez de no console do Intune clássico.
>>>>>>> live
