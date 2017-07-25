---
title: "Resolver conflitos de política do Intune e GPO"
description: "Saiba como resolver conflitos entre a Política de Grupo e as políticas de configuração do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 42debb9e26a226da6b2485a2ab1be2855d309747
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f0709-103">Resolver conflitos de política do Microsoft Intune e GPO (Objetos de Política de Grupo)</span><span class="sxs-lookup"><span data-stu-id="f0709-103">Resolve Group Policy Objects (GPO) and Microsoft Intune policy conflicts</span></span>
<a id="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f0709-104">O Intune usa políticas que ajudam a gerenciar as configurações em computadores Windows.</span><span class="sxs-lookup"><span data-stu-id="f0709-104">Intune uses policies that help you manage settings on Windows PCs.</span></span> <span data-ttu-id="f0709-105">Por exemplo, é possível usar uma política para controlar as configurações do Firewall do Windows nos computadores.</span><span class="sxs-lookup"><span data-stu-id="f0709-105">For example, you can use a policy to control settings for the Windows Firewall on PCs.</span></span> <span data-ttu-id="f0709-106">Várias configurações do Intune são semelhantes às configurações que podem ser feitas com a Política de Grupo do Windows.</span><span class="sxs-lookup"><span data-stu-id="f0709-106">Many Intune settings are similar to settings that you might configure with Windows Group Policy.</span></span> <span data-ttu-id="f0709-107">No entanto, é possível que, às vezes, os dois métodos entrem em conflito.</span><span class="sxs-lookup"><span data-stu-id="f0709-107">However, it is possible that, at times, the two methods might conflict with each another.</span></span>

<span data-ttu-id="f0709-108">Quando ocorrem conflitos, a Política de Grupo no nível de domínio tem precedência sobre a política do Intune, a menos que o computador não possa entrar no domínio.</span><span class="sxs-lookup"><span data-stu-id="f0709-108">When conflicts happen, domain-level Group Policy takes precedence over Intune policy, unless the PC can’t sign in to the domain.</span></span> <span data-ttu-id="f0709-109">Nesse caso, a política do Intune é aplicada ao computador cliente.</span><span class="sxs-lookup"><span data-stu-id="f0709-109">In this case, Intune policy is applied to the client PC.</span></span>

## <span data-ttu-id="f0709-110">O que fazer se você estiver usando a política de grupo</span><span class="sxs-lookup"><span data-stu-id="f0709-110">What to do if you are using Group Policy</span></span>
<a id="what-to-do-if-you-are-using-group-policy" class="xliff"></a>
<span data-ttu-id="f0709-111">Garanta que as políticas aplicadas não estão sendo gerenciadas pela Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="f0709-111">Make sure that policies that you apply are not being managed by Group Policy.</span></span> <span data-ttu-id="f0709-112">Para ajudar a evitar conflitos, é possível usar um ou mais dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="f0709-112">To help prevent conflicts, you can use one or more of the following methods:</span></span>

-   <span data-ttu-id="f0709-113">Mova seus computadores para uma OU (unidade organizacional) do Active Directory que não tenha configurações de Política de Grupo aplicadas antes de instalar o cliente do Intune.</span><span class="sxs-lookup"><span data-stu-id="f0709-113">Move your PCs to an Active Directory organizational unit (OU) that does not have Group Policy settings applied before you install the Intune client.</span></span> <span data-ttu-id="f0709-114">Você também pode bloquear a herança da Política de Grupo nas OUs que contenham computadores inscritos no Intune, aos quais você não deseja aplicar as configurações de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="f0709-114">You can also block Group Policy inheritance on OUs that contain PCs enrolled in Intune to which you do not want to apply Group Policy settings.</span></span>

-   <span data-ttu-id="f0709-115">Use um filtro do grupo de segurança para restringir somente GPOs para computadores não gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="f0709-115">Use a security group filter to restrict GPOs only to PCs that are not managed by Intune.</span></span>

-   <span data-ttu-id="f0709-116">Desabilite ou remova os Objetos da Política de Grupo que entram em conflito com as políticas do Intune.</span><span class="sxs-lookup"><span data-stu-id="f0709-116">Disable or remove the Group Policy Objects that conflict with the Intune policies.</span></span>

<span data-ttu-id="f0709-117">Para obter mais informações sobre o Active Directory e a Política de Grupo do Windows, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="f0709-117">For more information about Active Directory and Windows Group Policy, see your Windows Server Documentation.</span></span>

## <span data-ttu-id="f0709-118">Como filtrar os GPOs (Objetos da Política de Grupo) existentes para evitar conflitos com a política do Intune</span><span class="sxs-lookup"><span data-stu-id="f0709-118">How to filter existing GPOs to avoid conflicts with Intune policy</span></span>
<a id="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy" class="xliff"></a>
<span data-ttu-id="f0709-119">Se você identificou GPOs com configurações que entram em conflito com as políticas do Intune, é possível usar os filtros de grupo de segurança para restringir os GPOs apenas aos computadores não gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="f0709-119">If you have identified GPOs whose settings conflict with Intune policies, you can use security group filters to restrict those GPOs only to PCs that are not managed by Intune.</span></span>

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    -   For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


<span data-ttu-id="f0709-120">Você pode aplicar GPOs apenas aos grupos de segurança especificados na área **Filtragem de Segurança** do console do Gerenciamento de Política de Grupo de um GPO selecionado.</span><span class="sxs-lookup"><span data-stu-id="f0709-120">You can apply GPOs to only those security groups that are specified in the **Security Filtering** area of the Group Policy Management console for a selected GPO.</span></span> <span data-ttu-id="f0709-121">Por padrão, os GPOs aplicam-se a *Usuários Autenticados*.</span><span class="sxs-lookup"><span data-stu-id="f0709-121">By default, GPOs apply to *Authenticated Users*.</span></span>

-   <span data-ttu-id="f0709-122">No snap-in **Usuários e Computadores do Active Directory**, crie um novo grupo de segurança que contém computadores e contas de usuário que você não deseja que o Intune gerencie.</span><span class="sxs-lookup"><span data-stu-id="f0709-122">In the **Active Directory Users and Computers** snap-in, create a new security group that contains computers and user accounts that you do not want Intune to manage.</span></span> <span data-ttu-id="f0709-123">Por exemplo, você pode nomear o grupo *Não pertence ao Microsoft Intune*.</span><span class="sxs-lookup"><span data-stu-id="f0709-123">For example, you might name the group *Not In Microsoft Intune*.</span></span>

-   <span data-ttu-id="f0709-124">No console de Gerenciamento de Política de Grupo, na guia **Delegação** do GPO selecionado, clique com o botão direito do mouse no novo grupo de segurança para delegar as permissões **Leitura** e **Aplicar Política de Grupo** a usuários e computadores no grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="f0709-124">In the Group Policy Management console, on the **Delegation** tab for the selected GPO, right-click the new security group to delegate appropriate **Read** and **Apply Group Policy** permissions to both users and computers in the security group.</span></span> <span data-ttu-id="f0709-125">(As permissões para**Aplicar Política de Grupo** estão disponíveis na caixa de diálogo **Avançado** .)</span><span class="sxs-lookup"><span data-stu-id="f0709-125">(**Apply Group Policy** permissions are available on the **Advanced** dialog box.)</span></span>

-   <span data-ttu-id="f0709-126">Em seguida, aplique o novo filtro de grupo de segurança a um GPO selecionado e remova o filtro padrão **Usuários Autenticados**.</span><span class="sxs-lookup"><span data-stu-id="f0709-126">Then, apply the new security group filter to a selected GPO, and remove the **Authenticated Users** default filter.</span></span>

<span data-ttu-id="f0709-127">O novo grupo de segurança deve ser mantido como registro nas alterações de serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="f0709-127">The new security group must be maintained as enrollment in the Intune service changes.</span></span>

### <span data-ttu-id="f0709-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f0709-128">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="f0709-129">Gerenciar computadores Windows com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f0709-129">Manage Windows PCs with Microsoft Intune</span></span>](manage-windows-pcs-with-microsoft-intune.md)
