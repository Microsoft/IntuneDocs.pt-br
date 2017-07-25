---
title: "Planejar seus grupos de dispositivos e usuários"
description: "Planeje grupos para atender às necessidades da organização."
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1362c42cb44848d5ab3a88d08b19d8f6aee195b9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="df6f2-103">Planejar seus grupos de dispositivos e usuários</span><span class="sxs-lookup"><span data-stu-id="df6f2-103">Plan your user and device groups</span></span>
<a id="plan-your-user-and-device-groups" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="df6f2-104">Os grupos no Intune oferecem grande flexibilidade quando você está gerenciando dispositivos e usuários.</span><span class="sxs-lookup"><span data-stu-id="df6f2-104">Groups in Intune give you great flexibility when you're managing your devices and users.</span></span> <span data-ttu-id="df6f2-105">Você pode configurar grupos para atender às suas necessidades organizacionais de acordo com:</span><span class="sxs-lookup"><span data-stu-id="df6f2-105">You can set up groups to suit your organizational needs according to:</span></span>

- <span data-ttu-id="df6f2-106">localização geográfica</span><span class="sxs-lookup"><span data-stu-id="df6f2-106">geographic location</span></span>
- <span data-ttu-id="df6f2-107">department</span><span class="sxs-lookup"><span data-stu-id="df6f2-107">department</span></span>
- <span data-ttu-id="df6f2-108">características de hardware</span><span class="sxs-lookup"><span data-stu-id="df6f2-108">hardware characteristics</span></span>
- <span data-ttu-id="df6f2-109">sistema operacional</span><span class="sxs-lookup"><span data-stu-id="df6f2-109">operating system</span></span>
- <span data-ttu-id="df6f2-110">se o dispositivo é de propriedade do usuário ou da empresa</span><span class="sxs-lookup"><span data-stu-id="df6f2-110">whether the device is user-owned or company-owned</span></span>


## <span data-ttu-id="df6f2-111">Como funcionam os grupos do Intune</span><span class="sxs-lookup"><span data-stu-id="df6f2-111">How Intune groups work</span></span>
<a id="how-intune-groups-work" class="xliff"></a>


<span data-ttu-id="df6f2-112">Esta é a exibição padrão do nó **Grupos** no console de administrador do Intune:</span><span class="sxs-lookup"><span data-stu-id="df6f2-112">This is the default view of the **Groups** node in the Intune admin console:</span></span>

![Captura de tela da exibição padrão do nó Grupos no console do Intune](../media/Intune_Planning_Groups_Default_small.png)

<span data-ttu-id="df6f2-114">As políticas são implantadas em grupos, de modo que a hierarquia de grupo é uma das suas principais considerações de design.</span><span class="sxs-lookup"><span data-stu-id="df6f2-114">Policies are deployed to groups, so group hierarchy is one of your key design considerations.</span></span> <span data-ttu-id="df6f2-115">É importante saber que você não pode alterar o grupo pai de um grupo depois de ter criado o grupo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-115">It's important to know that you cannot change a group’s parent group after you've created the group.</span></span> <span data-ttu-id="df6f2-116">A forma como você projeta seus grupos é extremamente importante desde o momento em que começa a usar o serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="df6f2-116">How you design your groups is critically important from the moment you start using the Intune service.</span></span> <span data-ttu-id="df6f2-117">Algumas das práticas recomendadas para a criação de uma hierarquia de grupo com base em suas necessidades organizacionais são descritas aqui.</span><span class="sxs-lookup"><span data-stu-id="df6f2-117">Some recommended practices for designing a group hierarchy based on your organizational needs are described here.</span></span>

## <span data-ttu-id="df6f2-118">Regras de associação de grupo</span><span class="sxs-lookup"><span data-stu-id="df6f2-118">Group membership rules</span></span>
<a id="group-membership-rules" class="xliff"></a>

- <span data-ttu-id="df6f2-119">Um grupo pode conter usuários ou dispositivos, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="df6f2-119">A group can contain either users or devices, but not both.</span></span>

    * <span data-ttu-id="df6f2-120">**Grupos de dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-120">**Device groups**.</span></span> <span data-ttu-id="df6f2-121">Inclui computadores e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="df6f2-121">This includes computers and mobile devices.</span></span> <span data-ttu-id="df6f2-122">Antes de adicionar um computador a um grupo, é preciso registrá-lo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-122">Before you can add a computer to a group, it must be enrolled.</span></span> <span data-ttu-id="df6f2-123">Antes de adicionar um dispositivo móvel a um grupo, o ambiente deve ser configurado para dar suporte a dispositivos móveis, e os dispositivos devem ser registrados ou descobertos no Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="df6f2-123">Before you can add a mobile device to a group, your environment must be configured to support mobile devices, and the device must be enrolled or discovered in Exchange ActiveSync.</span></span>

    * <span data-ttu-id="df6f2-124">**Grupos de usuários**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-124">**User groups**.</span></span> <span data-ttu-id="df6f2-125">Um grupo pode ter usuários de grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="df6f2-125">A group can have users from security groups.</span></span> <span data-ttu-id="df6f2-126">Sincronização de grupos de segurança com sua instância do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-126">Security groups sync with your instance of Active Directory.</span></span> <span data-ttu-id="df6f2-127">Se não sincronizar com o Active Directory, você poderá criar esses grupos manualmente.</span><span class="sxs-lookup"><span data-stu-id="df6f2-127">If you do not sync with Active Directory, you can manually create these groups.</span></span>

- <span data-ttu-id="df6f2-128">Um dispositivo ou um usuário pode pertencer a mais de um grupo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-128">A device or a user can belong to more than one group.</span></span>

- <span data-ttu-id="df6f2-129">Um grupo pode incluir e excluir membros com base nas seguintes regras de associação:</span><span class="sxs-lookup"><span data-stu-id="df6f2-129">A group can include and exclude members based on the following membership rules:</span></span>

    * <span data-ttu-id="df6f2-130">**Critérios de Associação**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-130">**Criteria Membership**.</span></span> <span data-ttu-id="df6f2-131">Essas são regras dinâmicas que o Intune executa para incluir ou excluir membros.</span><span class="sxs-lookup"><span data-stu-id="df6f2-131">These are dynamic rules that Intune runs to include or exclude members.</span></span> <span data-ttu-id="df6f2-132">Esses critérios usam grupos de segurança e outras informações sincronizadas com sua instância local do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-132">These criteria use security groups and other information synced with your local instance of Active Directory.</span></span> <span data-ttu-id="df6f2-133">Quando os dados ou o grupo de segurança mudam, a associação ao grupo muda quando você sincroniza com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-133">When the security group or data changes, the group membership changes when you sync with Active Directory.</span></span>

    * <span data-ttu-id="df6f2-134">**Associação Direta**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-134">**Direct Membership**.</span></span> <span data-ttu-id="df6f2-135">Essas são regras estáticas que agregam ou excluem membros explicitamente.</span><span class="sxs-lookup"><span data-stu-id="df6f2-135">These are static rules that explicitly add or exclude members.</span></span> <span data-ttu-id="df6f2-136">A lista de membros é estática.</span><span class="sxs-lookup"><span data-stu-id="df6f2-136">The membership list is static.</span></span>

-   <span data-ttu-id="df6f2-137">Os AD DS (Serviços de Domínio do Active Directory) não são necessários quando você cria grupos de usuários ou grupos de dispositivos que incluem usuários ou computadores.</span><span class="sxs-lookup"><span data-stu-id="df6f2-137">Active Directory Domain Services (AD DS) is not required when you create user groups or device groups that include users or computers.</span></span> <span data-ttu-id="df6f2-138">Mas, para que os grupos de dispositivos incluam dispositivos móveis, seu ambiente deve ser configurado para dar suporte a dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="df6f2-138">But, for device groups to include mobile devices, your environment must be configured to support mobile devices.</span></span>

    <span data-ttu-id="df6f2-139">Além disso, os dispositivos devem ser descobertos e adicionados ao Intune.</span><span class="sxs-lookup"><span data-stu-id="df6f2-139">Additionally, the devices must be discovered and added to Intune.</span></span>

## <span data-ttu-id="df6f2-140">Regras de relação de grupo</span><span class="sxs-lookup"><span data-stu-id="df6f2-140">Group relationship rules</span></span>
<a id="group-relationship-rules" class="xliff"></a>

- <span data-ttu-id="df6f2-141">Cada grupo criado deve ter um grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-141">Each group you create must have a parent group.</span></span> <span data-ttu-id="df6f2-142">Você não pode alterar o grupo pai de um grupo depois de ter criado o grupo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-142">You cannot change a group’s parent group after you've created the group.</span></span>

- <span data-ttu-id="df6f2-143">Ao adicionar usuários ou dispositivos a um grupo filho:</span><span class="sxs-lookup"><span data-stu-id="df6f2-143">When you add users or devices to a child group:</span></span>

    * <span data-ttu-id="df6f2-144">O grupo filho sempre é um subconjunto do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-144">The child group is always a subset of the parent group.</span></span>

    * <span data-ttu-id="df6f2-145">Novos membros adicionados a um grupo filho serão adicionados automaticamente ao seu respectivo grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-145">New members you add to a child group are automatically added to that group’s parent group.</span></span>

    * <span data-ttu-id="df6f2-146">Não é possível adicionar um membro a um grupo filho, quando esse membro tiver sido excluído do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-146">You cannot add a member to a child group when that member is excluded from the parent group.</span></span>

- <span data-ttu-id="df6f2-147">A associação de um grupo pai define a disponibilidade de associação ao grupo filho.</span><span class="sxs-lookup"><span data-stu-id="df6f2-147">The membership of a parent group defines the available membership for the child group.</span></span>

- <span data-ttu-id="df6f2-148">Quando você excluir um grupo pai, todos os grupos filho serão excluídos.</span><span class="sxs-lookup"><span data-stu-id="df6f2-148">When you delete a parent group, all child groups are deleted.</span></span>

- <span data-ttu-id="df6f2-149">É possível implantar o conteúdo e as políticas para um grupo pai e excluir a implantação em grupos filho.</span><span class="sxs-lookup"><span data-stu-id="df6f2-149">You can deploy content and policies to a parent group but exclude the deployment to child groups.</span></span>

- <span data-ttu-id="df6f2-150">Você poderá adicionar um usuário ou dispositivo específico a um grupo filho se o usuário ou dispositivo já não for membro do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-150">You can add a specific user or device to a child group if the user or device is not already a member of the parent group.</span></span> <span data-ttu-id="df6f2-151">Se você fizer isso, o novo membro do grupo filho será adicionado ao grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-151">If you do this, the new member of the child group will be added to the parent group.</span></span>

    <span data-ttu-id="df6f2-152">No entanto, não será possível adicionar um membro a um grupo filho se o membro for excluído do grupo pai.</span><span class="sxs-lookup"><span data-stu-id="df6f2-152">However, you cannot add a member to a child group if the member is excluded from the parent group.</span></span>

- <span data-ttu-id="df6f2-153">A associação ao grupo é recursiva.</span><span class="sxs-lookup"><span data-stu-id="df6f2-153">Group membership is recursive.</span></span> <span data-ttu-id="df6f2-154">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="df6f2-154">For example:</span></span>

    * <span data-ttu-id="df6f2-155">**Pat** é um membro de apenas um grupo, o grupo de segurança **Usuários de Laptop** .</span><span class="sxs-lookup"><span data-stu-id="df6f2-155">**Pat** is a member of only one group, the **Laptop Users** security group.</span></span>

    * <span data-ttu-id="df6f2-156">O grupo **Usuários de Laptop** é um membro do grupo de segurança **Usuários Aprovados** .</span><span class="sxs-lookup"><span data-stu-id="df6f2-156">The **Laptop Users** group is a member of the **Approved Users** security group.</span></span>

    * <span data-ttu-id="df6f2-157">Você cria um grupo no Intune que usa uma consulta de associação dinâmica que inclui os membros do grupo **Usuários Aprovados**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-157">You create a group in Intune that uses a dynamic membership query that includes the members of the **Approved Users** group.</span></span> <span data-ttu-id="df6f2-158">O resultado disso é que o seu grupo de usuários do Intune incluirá **Pat**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-158">The result is that your Intune user group includes **Pat**.</span></span>

> [!TIP]
> <span data-ttu-id="df6f2-159">Quando criar grupos, reflita sobre como você aplicará políticas.</span><span class="sxs-lookup"><span data-stu-id="df6f2-159">When you create groups, think about how you will apply policy.</span></span> <span data-ttu-id="df6f2-160">Por exemplo, você pode ter políticas específicas para sistemas operacionais do dispositivo ou políticas específicas para diferentes funções ou unidades organizacionais que você já definiu no serviço do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-160">For example, you might have policies that are specific to device operating systems, or policies that are specific to different roles or organizational units you've already defined in your Active Directory service.</span></span> <span data-ttu-id="df6f2-161">Alguns administradores consideram útil criar grupos de dispositivos específicos para iOS, Android e Windows.</span><span class="sxs-lookup"><span data-stu-id="df6f2-161">Some admins find it useful to create device groups that are specific to iOS, Android, and Windows.</span></span> <span data-ttu-id="df6f2-162">Isso vai além da criação de grupos de usuários para cada função organizacional.</span><span class="sxs-lookup"><span data-stu-id="df6f2-162">This is in addition to creating user groups for each organizational role.</span></span>

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <span data-ttu-id="df6f2-163">Grupos internos</span><span class="sxs-lookup"><span data-stu-id="df6f2-163">Built-in groups</span></span>
<a id="built-in-groups" class="xliff"></a>
<span data-ttu-id="df6f2-164">O Intune tem nove grupos internos que não podem ser editados nem excluídos: <!--maybe a screen shot would be best?--></span><span class="sxs-lookup"><span data-stu-id="df6f2-164">Intune has nine built-in groups that you cannot edit or delete: <!--maybe a screen shot would be best?--></span></span>

-   <span data-ttu-id="df6f2-165">**Todos os Usuários**</span><span class="sxs-lookup"><span data-stu-id="df6f2-165">**All Users**</span></span>
    -   <span data-ttu-id="df6f2-166">Usuários Desagrupados</span><span class="sxs-lookup"><span data-stu-id="df6f2-166">Ungrouped Users</span></span>
-   <span data-ttu-id="df6f2-167">**Todos os Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="df6f2-167">**All Devices**</span></span>
    -   <span data-ttu-id="df6f2-168">Todos os Computadores</span><span class="sxs-lookup"><span data-stu-id="df6f2-168">All Computers</span></span>
    -   <span data-ttu-id="df6f2-169">Todos os dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="df6f2-169">All Mobile Devices</span></span>
        -   <span data-ttu-id="df6f2-170">Todos os dispositivos gerenciados diretos</span><span class="sxs-lookup"><span data-stu-id="df6f2-170">All Direct Managed Devices</span></span>
        -   <span data-ttu-id="df6f2-171">Todos os dispositivos gerenciados do Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="df6f2-171">All Exchange ActiveSync Managed Devices</span></span>
    -   <span data-ttu-id="df6f2-172">Todos os dispositivos corporativos</span><span class="sxs-lookup"><span data-stu-id="df6f2-172">All Corporate-owned Devices</span></span>
    -   <span data-ttu-id="df6f2-173">Dispositivos Desagrupados</span><span class="sxs-lookup"><span data-stu-id="df6f2-173">Ungrouped Devices</span></span>

> [!NOTE]
> <span data-ttu-id="df6f2-174">Seu lema deve ser: *manter as coisas simples*.</span><span class="sxs-lookup"><span data-stu-id="df6f2-174">Let your motto be: *keep it simple*.</span></span> <span data-ttu-id="df6f2-175">Se sua organização não tiver necessidades específicas como as descritas a seguir, mantenha a simplicidade e use a estrutura de grupo e políticas padrão.</span><span class="sxs-lookup"><span data-stu-id="df6f2-175">If your organization does not have specific needs like those described in the following sections, keep it simple and go with the default group structure and policies.</span></span> <span data-ttu-id="df6f2-176">Isso tornará o serviço mais gerenciável no longo prazo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-176">This will make the service more manageable in the long term.</span></span> <span data-ttu-id="df6f2-177">A manutenção será mais fácil se você puder tratar seus usuários uniformemente.</span><span class="sxs-lookup"><span data-stu-id="df6f2-177">Maintenance will be easier if you can treat your users uniformly.</span></span> <span data-ttu-id="df6f2-178">Com pouca diferenciação por grupo, você terá menos políticas para manter.</span><span class="sxs-lookup"><span data-stu-id="df6f2-178">With little differentiation by group, you'll have fewer policies to maintain.</span></span>


### <span data-ttu-id="df6f2-179">Todos os usuários e dispositivos na sua organização</span><span class="sxs-lookup"><span data-stu-id="df6f2-179">All users and devices in your organization</span></span>
<a id="all-users-and-devices-in-your-organization" class="xliff"></a>
<span data-ttu-id="df6f2-180">Defina um grupo pai para todos os usuários e dispositivos na sua organização.</span><span class="sxs-lookup"><span data-stu-id="df6f2-180">Define a parent group for all users and devices in your organization.</span></span> <span data-ttu-id="df6f2-181">É provável que você tenha políticas que se aplicam a todos.</span><span class="sxs-lookup"><span data-stu-id="df6f2-181">You are likely to have policies that will apply to all.</span></span> <span data-ttu-id="df6f2-182">Você pode usar os grupos padrão do Intune **Todos os Usuários** e **Todos os Dispositivos** para esta finalidade.</span><span class="sxs-lookup"><span data-stu-id="df6f2-182">You can use the Intune default **All Users** and **All devices** groups for this purpose.</span></span> <span data-ttu-id="df6f2-183">Subgrupos que organizam os dispositivos por informações específicas, como o grupo de BYOD (traga seu próprio dispositivo) e o de dispositivos CO (corporativos), podem ser grupos filho dos grupos pai **Todos os Usuários** e **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-183">Sub-groups that organize devices by specifics, like a group for bring your own device (BYOD) and one for corporate-owned (CO) devices, can be child groups of the **All Users** and **All devices** parent groups.</span></span>

## <span data-ttu-id="df6f2-184">Personalizar grupos para sua organização</span><span class="sxs-lookup"><span data-stu-id="df6f2-184">Customize groups for your organization</span></span>
<a id="customize-groups-for-your-organization" class="xliff"></a>

### <span data-ttu-id="df6f2-185">Dispositivos de propriedade corporativa e BYOD</span><span class="sxs-lookup"><span data-stu-id="df6f2-185">BYOD and corporate-owned devices</span></span>
<a id="byod-and-corporate-owned-devices" class="xliff"></a>
<span data-ttu-id="df6f2-186">Se a sua organização permite que os funcionários usem os próprios dispositivos, fornece dispositivos da empresa ou trabalha com uma combinação de ambos, recomenda-se que você aplique políticas distintas a essas duas categorias de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="df6f2-186">If your organization allows employees to use their own devices, provides company-owned devices, or has a combination of both, we recommend that you apply separate policies for these categories of devices.</span></span>

<span data-ttu-id="df6f2-187">No caso de BYOD ou uma mistura de ambos, tenha cuidado em planejar políticas que não venham a infringir os regulamentos de privacidade locais.</span><span class="sxs-lookup"><span data-stu-id="df6f2-187">In the case of BYOD or a mix, be careful to plan policies that do not infringe on local privacy regulations.</span></span> <span data-ttu-id="df6f2-188">Crie um grupo pai para todos os usuários que levarão seus próprios dispositivos.</span><span class="sxs-lookup"><span data-stu-id="df6f2-188">Create a parent group for all users who will be bringing their own devices.</span></span> <span data-ttu-id="df6f2-189">Você pode usar esse grupo para aplicar políticas que se aplicam a todos os usuários nesta categoria.</span><span class="sxs-lookup"><span data-stu-id="df6f2-189">You can use this group to apply policies that are applicable to all users in this category.</span></span>

![Criar um grupo pai de BYOD](../media/Intune_Planning_Groups_BYOD_small.png)

<span data-ttu-id="df6f2-191">Da mesma forma, você pode criar um grupo para usuários de dispositivos CO em sua organização:</span><span class="sxs-lookup"><span data-stu-id="df6f2-191">Similarly, you can create a group for the CO device users in your organization:</span></span>

![Grupos de usuário irmãos para dispositivos BYOD e CO](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <span data-ttu-id="df6f2-193">Grupos para regiões geográficas</span><span class="sxs-lookup"><span data-stu-id="df6f2-193">Groups for geographic regions</span></span>
<a id="groups-for-geographic-regions" class="xliff"></a>
<span data-ttu-id="df6f2-194">Se sua organização precisar de políticas para regiões específicas, você poderá criar grupos com base na região geográfica.</span><span class="sxs-lookup"><span data-stu-id="df6f2-194">If your organization needs policies for specific regions, you can create groups based on geographic region.</span></span> <span data-ttu-id="df6f2-195">Você pode baseá-los em grupos regionais que já tenha sido criados em sua instância do Active Directory e sincronizá-los com o serviço do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-195">You can base them on regional groups that you might have already created in your instance of Active Directory, and sync them with your Azure Active Directory service.</span></span> <span data-ttu-id="df6f2-196">Você também pode criar grupos regionais diretamente no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-196">You also can create regional groups directly in Azure Active Directory.</span></span>

<span data-ttu-id="df6f2-197">As próximas capturas de tela mostram como criar grupos do Intune com base em grupos sincronizados com sua instância local do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-197">The next screenshots show you how to create Intune groups based on groups synced with your on-premises Active Directory instance.</span></span> <span data-ttu-id="df6f2-198">Esses exemplos pressupõem que você tenha um grupo de segurança do AD chamado **Grupo de Usuários dos EUA**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-198">These examples assume that you have an Active Directory security group called **US Users Group**.</span></span>

<span data-ttu-id="df6f2-199">Primeiro, forneça as informações gerais.</span><span class="sxs-lookup"><span data-stu-id="df6f2-199">First, provide general information.</span></span>

![Captura de tela da área Editar Grupo](../media/Intune_Planning_Groups_AD_General_small.png)

<span data-ttu-id="df6f2-201">Em **Critérios de Associação**, selecione o **Grupo de Usuários dos EUA**, sincronizado com o Active Directory, como o grupo de segurança a ser usado nas regras de associação.</span><span class="sxs-lookup"><span data-stu-id="df6f2-201">Under **Membership criteria**, select **US Users Group**, synced with Active Directory, as the security group to use under membership rules.</span></span>

![Captura de tela da caixa de diálogo Editar Grupo](../media/Intune_Planning_Groups_AD_Criteria_small.png)

<span data-ttu-id="df6f2-203">Examine suas entradas e escolha **Concluir** para criar o grupo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-203">Review your entries, and then choose **Finish** to create the group.</span></span>

![Captura de tela da caixa de diálogo Editar Grupo](../media/Intune_Planning_Groups_AD_Summary_small.png)

<span data-ttu-id="df6f2-205">Em nosso exemplo, também criamos um grupo chamado **MEA** para o Oriente Médio e a Ásia.</span><span class="sxs-lookup"><span data-stu-id="df6f2-205">In our example, we’ve also created a group called **MEA**, for the Middle East and Asia.</span></span>

> [!NOTE]
> <span data-ttu-id="df6f2-206">Se a associação de grupo não for preenchida com base nas associações de grupo de segurança, verifique se você atribuiu licenças do Intune aos membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-206">If group membership is not populated based on security group membership, make sure that you have assigned Intune licenses to group members.</span></span>

### <span data-ttu-id="df6f2-207">Grupos de hardware específico</span><span class="sxs-lookup"><span data-stu-id="df6f2-207">Groups for specific hardware</span></span>
<a id="groups-for-specific-hardware" class="xliff"></a>
<span data-ttu-id="df6f2-208">Se sua organização exigir políticas que se aplicam a tipos específicos de hardware, você poderá criar grupos com base nesse critério.</span><span class="sxs-lookup"><span data-stu-id="df6f2-208">If your organization requires policies that apply to specific hardware types, you can create groups based on this requirement.</span></span> <span data-ttu-id="df6f2-209">Você pode basear as políticas em grupos específicos já criados em sua instância local do Active Directory e sincronizá-los com o serviço do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-209">You can base the policies on specific groups that you have already created in your on-premises instance of Active Directory, and then sync them with Azure Active Directory.</span></span> <span data-ttu-id="df6f2-210">Você também pode criar grupos diretamente no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-210">You also can create groups directly in Azure Active Directory.</span></span> <span data-ttu-id="df6f2-211">Neste exemplo, usamos o **Grupo de Usuários dos EUA** como o grupo pai para o grupo **Usuários de Laptop**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-211">In this example, we use **US Users Group** as the parent group for the **Laptop Users** group.</span></span>

![Caixa de diálogo Selecionar Grupo de Segurança](../media/Intune_Planning_Groups_Laptop_small.png)

<span data-ttu-id="df6f2-213">Neste ponto, a hierarquia do grupo deve ser semelhante à seguinte captura de tela.</span><span class="sxs-lookup"><span data-stu-id="df6f2-213">At this point, your group's hierarchy should look similar to the next screenshot.</span></span> <span data-ttu-id="df6f2-214">Como você pode ver, agora existem membros no grupo **Usuários de Laptop** do Intune.</span><span class="sxs-lookup"><span data-stu-id="df6f2-214">You can see that there are now members in the Intune group **Laptop Users**.</span></span> <span data-ttu-id="df6f2-215">Todas as políticas aplicadas a esse grupo serão aplicadas a usuários de laptop BYOD da região dos EUA.</span><span class="sxs-lookup"><span data-stu-id="df6f2-215">Any policies applied to this group will be applied to BYOD laptop users from the U.S. region.</span></span>

![Exibição do grupo de Usuários de Laptop](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <span data-ttu-id="df6f2-217">Grupos para sistemas operacionais específicos</span><span class="sxs-lookup"><span data-stu-id="df6f2-217">Groups for specific operating systems</span></span>
<a id="groups-for-specific-operating-systems" class="xliff"></a>
<span data-ttu-id="df6f2-218">Se sua organização exigir políticas aplicáveis a sistemas operacionais específicos, como Android, iOS ou Windows, você poderá criar grupos com base nessa exigência.</span><span class="sxs-lookup"><span data-stu-id="df6f2-218">If your organization requires policies that apply to specific operating systems like Android, iOS, or Windows, you can create groups based on this requirement.</span></span> <span data-ttu-id="df6f2-219">Assim como em exemplos anteriores, você pode baseá-las em grupos específicos já criados em sua instância local do Active Directory e sincronizá-los com o serviço do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-219">As in earlier examples, you can base them on OS-specific groups that you have already created in your on-premises instance of Active Directory, and sync them with Azure Active Directory.</span></span> <span data-ttu-id="df6f2-220">Você também pode criá-las diretamente na sua instância do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-220">You also can create them directly in your instance of Azure Active Directory.</span></span>

<span data-ttu-id="df6f2-221">Usando o mesmo método dos exemplos anteriores, você pode criar grupos com base em usuários <!--devices?--> que usam plataformas de sistema operacional específicas.</span><span class="sxs-lookup"><span data-stu-id="df6f2-221">By using the same method from earlier examples, you can create groups based on users <!--devices?--> who use specific operating system platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="df6f2-222">Se você tiver usuários que usam vários sistemas operacionais/plataformas móveis e não tiver uma forma automatizada para categorizar os usuários como usuários Android, iOS ou Windows, considere a aplicação de políticas no nível do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-222">If you have users who use multiple mobile platforms or operating systems and you do not have an automated way to categorize users as Android users, iOS users, or Windows users, consider applying policies at the device level.</span></span> <span data-ttu-id="df6f2-223">Isso lhe dará mais flexibilidade para aplicar políticas específicas a um sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="df6f2-223">This will give you more flexibility to apply policies that are specific to an operating system.</span></span>
>
> <span data-ttu-id="df6f2-224">Você não pode provisionar grupos dinamicamente com base no sistema operacional do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="df6f2-224">You cannot provision groups dynamically based on the operating system of the device.</span></span> <span data-ttu-id="df6f2-225">Em vez disso, use grupos de segurança do Active Directory ou do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df6f2-225">Instead, do this by using Active Directory or Azure Active Directory security groups.</span></span>

![Grupo de Usuários de Laptop](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

<span data-ttu-id="df6f2-227">Depois que todos os seus grupos de usuários forem preenchidos com base nesses requisitos organizacionais, sua hierarquia de grupo deve ter esta aparência:</span><span class="sxs-lookup"><span data-stu-id="df6f2-227">After all of your user groups are populated based on your organizational requirements, your group hierarchy should look something like this:</span></span>

![Exibição de hierarquia de grupos](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

<span data-ttu-id="df6f2-229">Você pode usar essa hierarquia para aplicar as políticas da organização.</span><span class="sxs-lookup"><span data-stu-id="df6f2-229">You can use this hierarchy to apply the organization's policies.</span></span>

### <span data-ttu-id="df6f2-230">Grupos de dispositivos</span><span class="sxs-lookup"><span data-stu-id="df6f2-230">Device groups</span></span>
<a id="device-groups" class="xliff"></a>
<span data-ttu-id="df6f2-231">Você também pode criar grupos semelhantes para dispositivos conforme mostrado abaixo, começando com um amplo grupo que inclui todos os dispositivos dos funcionários para o cenário de BYOD.</span><span class="sxs-lookup"><span data-stu-id="df6f2-231">You also can create similar groups for devices as shown here, starting with a broad group that includes all employee-owned devices, for the BYOD scenario.</span></span>

![Caixa de diálogo Criar Grupo](../media/Intune_Planning_Groups_Device_General_small.png)

<span data-ttu-id="df6f2-233">Verifique se você selecionou **Todos os dispositivos (computadores e dispositivos móveis)** para que o grupo inclua todos os dispositivos BYO:</span><span class="sxs-lookup"><span data-stu-id="df6f2-233">Make sure that you select **All devices (computers and mobile)** so that the group will include all BYO devices:</span></span>

![Página Definir critérios de associação](../media/Intune_Planning_Groups_Device_Criteria_small.png)

<span data-ttu-id="df6f2-235">Examine suas entradas e escolha **Concluir** para criar o grupo de BYOD.</span><span class="sxs-lookup"><span data-stu-id="df6f2-235">Review your entries, and then choose **Finish** to create the BYOD group.</span></span>

![Caixa de diálogo Criar Grupo](../media/Intune_Planning_Groups_Device_Summary_small.png)

<span data-ttu-id="df6f2-237">Continue a criar grupos de dispositivos, até que você tenha uma hierarquia de grupos de dispositivos semelhante à hierarquia de grupos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="df6f2-237">Continue to create device groups until you have a device group hierarchy that is similar to the user group hierarchy.</span></span> <span data-ttu-id="df6f2-238">Seu nó de grupo no console do Intune será semelhante a este:</span><span class="sxs-lookup"><span data-stu-id="df6f2-238">Your group node in the Intune console will look similar to this:</span></span>

![Exibição de hierarquia de grupos do Intune](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <span data-ttu-id="df6f2-240">Convenções de nomenclatura e hierarquias de grupo</span><span class="sxs-lookup"><span data-stu-id="df6f2-240">Group hierarchies and naming conventions</span></span>
<a id="group-hierarchies-and-naming-conventions" class="xliff"></a>
<span data-ttu-id="df6f2-241">Para facilitar o gerenciamento de políticas, é recomendável nomear cada política de acordo com a finalidade, a plataforma e o escopo ao qual ela é aplicada.</span><span class="sxs-lookup"><span data-stu-id="df6f2-241">To make policy management easier, we recommend that you name each policy according to the purpose, platform, and scope to which you apply it.</span></span> <span data-ttu-id="df6f2-242">Use um padrão de nomenclatura que siga a estrutura de grupos que você criou quando se preparou para aplicar as políticas.</span><span class="sxs-lookup"><span data-stu-id="df6f2-242">Use a naming standard that follows the group structure that you created when you prepared to apply your policies.</span></span>

<span data-ttu-id="df6f2-243">Por exemplo, para uma política do Android que é aplicada a todos os dispositivos corporativos, Android e dispositivos móveis no nível regional dos EUA, a política pode ser nomeada como **CO_US_Mob_Android_General**.</span><span class="sxs-lookup"><span data-stu-id="df6f2-243">For instance, for an Android policy that applies to all corporate, Android, mobile devices at the U.S. regional level, you might name the policy **CO_US_Mob_Android_General**.</span></span>

![Criar política para Android](../media/Intune_planning_policy_android_small.png)

<span data-ttu-id="df6f2-245">Ao nomear as políticas dessa forma, você poderá identificar rapidamente as políticas e seu uso pretendido, bem como o escopo do nó **Políticas** do console, da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="df6f2-245">When you name your policies this way, you can quickly identify policies and their intended use and scope in the **Policies** node, like this:</span></span>

![Lista de política do Intune](../media/Intune_planning_policy_view_small.png)

## <span data-ttu-id="df6f2-247">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="df6f2-247">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="df6f2-248">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="df6f2-248">Create groups</span></span>](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
