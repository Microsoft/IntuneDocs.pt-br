---
title: "Atribuir licenças do Intune"
description: "Atribuir licenças a usuários para sua assinatura do Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 317fad8beb708a10a4dbf81a04f03c2faab41925
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="d6660-103">Atribuir licenças do Intune a suas contas de usuário</span><span class="sxs-lookup"><span data-stu-id="d6660-103">Assign Intune licenses to your user accounts</span></span>
=======
# Atribuir licenças do Intune a suas contas de usuário
>>>>>>> live
<a id="assign-intune-licenses-to-your-user-accounts" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<<<<<<< HEAD
<span data-ttu-id="d6660-104">Se você adicionar usuários manualmente ou sincronizar a partir de seu Active Directory local, primeiro atribua a cada usuário uma licença do Intune para que eles possam registrar seus dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="d6660-104">Whether you manually add users or synchronize from your on-premises Active Directory, you must first assign each user an Intune license before users can enroll their devices in Intune.</span></span>

## <span data-ttu-id="d6660-105">Atribuir uma licença do Intune no Centro de administração do Office 365</span><span class="sxs-lookup"><span data-stu-id="d6660-105">Assign an Intune license in the Office 365 Admin center</span></span>
<a id="assign-an-intune-license-in-the-office-365-admin-center" class="xliff"></a>

<span data-ttu-id="d6660-106">Use o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d6660-106">You can use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts synchronized from your on-premises Active Directory to Azure AD.</span></span>

1.  <span data-ttu-id="d6660-107">Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) usando suas credenciais de administrador de locatário e escolha **Usuários** > **Usuários Ativos**.</span><span class="sxs-lookup"><span data-stu-id="d6660-107">Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) using your tenant administrator credentials, and then choose **Users** > **Active Users**.</span></span>

2.  <span data-ttu-id="d6660-108">Selecione a conta de usuário a qual você deseja atribuir uma licença de usuário do Intune e escolha **Licenças de produto** > **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d6660-108">Select the user account that you want to assign an Intune user license to, and then choose **Product licenses** > **Edit**.</span></span>

3.  <span data-ttu-id="d6660-109">Mude **Intune** ou **Enterprise Mobility + Security** para **Ativado** e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d6660-109">Toggle **Intune** or **Enterprise Mobility + Security** to **On**, and choose **Save**.</span></span>

  ![Imagem da atribuição de Licença do produto no Portal do Office 365.](./media/office-assign-license.png)

4. <span data-ttu-id="d6660-111">Agora, a conta de usuário tem as permissões necessárias para usar o serviço e registrar os dispositivos no gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d6660-111">The user account now has the permissions needed to use the service and enroll devices into management.</span></span>

> [!NOTE]
> <span data-ttu-id="d6660-112">Os usuários serão exibidos no console de Administração somente após o registro de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6660-112">Users will appear in the Admin console only after they have enrolled a device.</span></span> <span data-ttu-id="d6660-113">Além disso, você pode selecionar um grupo de usuários para editar simultaneamente, selecionando adicionar ou substituir uma licença para todos os usuários selecionados.</span><span class="sxs-lookup"><span data-stu-id="d6660-113">Also, you can select a group of users to edit at once,  either selecting to add or replace a license for all selected users.</span></span>

## <span data-ttu-id="d6660-114">Use o School Data Sync para atribuir licenças a usuários no Intune para Educação</span><span class="sxs-lookup"><span data-stu-id="d6660-114">Use School Data Sync to assign licenses to users in Intune for Education</span></span>
<a id="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education" class="xliff"></a>
<span data-ttu-id="d6660-115">Se você for uma organização educativa, poderá usar o SDS (School Data Sync) para atribuir licenças do Intune para Educação para os usuários sincronizados.</span><span class="sxs-lookup"><span data-stu-id="d6660-115">If you are an educational organization, you can use School Data Sync (SDS) to assign Intune for Education licenses to synced users.</span></span> <span data-ttu-id="d6660-116">Basta escolher a caixa de seleção do Intune para Educação quando você estiver configurando seu perfil de SDS.</span><span class="sxs-lookup"><span data-stu-id="d6660-116">Just choose the Intune for Education checkbox when you're setting up your SDS profile.</span></span>  

![Imagem da configuração de perfil do SDS](./media/i4e-sds-profile-setup-setting.png)

<span data-ttu-id="d6660-118">Quando você atribui uma licença do Intune para Educação, certifique-se de que a licença do Intune A Direct também seja atribuída.</span><span class="sxs-lookup"><span data-stu-id="d6660-118">When you assign an Intune for Education license, make sure that Intune A Direct license is also assigned.</span></span>

![Imagem da configuração da licença do produto](./media/i4e-set-licenses.png)

<span data-ttu-id="d6660-120">Veja esta [visão geral do School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) para saber mais sobre o SDS.</span><span class="sxs-lookup"><span data-stu-id="d6660-120">See this [overview of School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) to learn more about SDS.</span></span>

## <span data-ttu-id="d6660-121">Como as licenças de usuário e dispositivo afetam o acesso a serviços</span><span class="sxs-lookup"><span data-stu-id="d6660-121">How user and device licenses affect access to services</span></span>
<a id="how-user-and-device-licenses-affect-access-to-services" class="xliff"></a>
* <span data-ttu-id="d6660-122">Cada **usuário** ao qual você atribui uma licença de software de usuário pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para gerenciar aplicativos e até 15 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d6660-122">Each **user** that you assign a user software license to may access and use the online services and related software (including System Center software) to manage applications and up to 15 devices.</span></span>
* <span data-ttu-id="d6660-123">Cada **dispositivo** ao qual você atribui uma licença de software de dispositivo pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para uso por qualquer número de usuários.</span><span class="sxs-lookup"><span data-stu-id="d6660-123">Each **device** that you assign a device software license to may access and use the online services and related software (including System Center software) for use by any number of users.</span></span>
* <span data-ttu-id="d6660-124">Se um dispositivo for usado por mais de um usuário, cada um deles precisará de uma licença de software de dispositivo ou todos os usuários precisarão de uma licença de software de usuário.</span><span class="sxs-lookup"><span data-stu-id="d6660-124">If a device is used by more than one user, each requires a device software license or all users require a user software license.</span></span>

## <span data-ttu-id="d6660-125">Usar o PowerShell para gerenciar seletivamente licenças de usuário do EMS</span><span class="sxs-lookup"><span data-stu-id="d6660-125">Use PowerShell to selectively manage EMS user licenses</span></span>
<a id="use-powershell-to-selectively-manage-ems-user-licenses" class="xliff"></a>
<span data-ttu-id="d6660-126">As organizações que usam o Microsoft Enterprise Mobility + Security (conhecido anteriormente como Enterprise Mobility Suite) podem ter usuários que precisam apenas do Azure Active Directory Premium ou dos serviços do Intune no pacote do EMS.</span><span class="sxs-lookup"><span data-stu-id="d6660-126">Organizations that use Microsoft Enterprise Mobility + Security (formerly Enterprise Mobility Suite) might have users who only require Azure Active Directory Premium or Intune services in the EMS package.</span></span> <span data-ttu-id="d6660-127">Você pode atribuir um serviço ou um subconjunto de serviços usando os [cmdlets do PowerShell do Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).</span><span class="sxs-lookup"><span data-stu-id="d6660-127">You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).</span></span>

<span data-ttu-id="d6660-128">Para atribuir seletivamente licenças de usuário para serviços do EMS, abra o PowerShell como administrador em um computador com o [Módulo do Azure Active Directory para Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) instalado.</span><span class="sxs-lookup"><span data-stu-id="d6660-128">To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed.</span></span> <span data-ttu-id="d6660-129">Você pode instalar o PowerShell em um computador local ou em um servidor do ADFS.</span><span class="sxs-lookup"><span data-stu-id="d6660-129">You can install PowerShell on a local computer or on an ADFS server.</span></span>

<span data-ttu-id="d6660-130">Você precisa criar uma nova definição de SKU de licença que se aplique apenas aos planos de serviço desejados.</span><span class="sxs-lookup"><span data-stu-id="d6660-130">You must create a new license SKU definition that applies only to the desired service plans.</span></span> <span data-ttu-id="d6660-131">Para fazer isso, desabilite os planos que não deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="d6660-131">To do this, disable the plans you don’t want to apply.</span></span> <span data-ttu-id="d6660-132">Por exemplo, você pode criar uma definição de SKU de licença que não atribui uma licença do Intune.</span><span class="sxs-lookup"><span data-stu-id="d6660-132">For example, you might create a license SKU definition that does not assign an Intune license.</span></span> <span data-ttu-id="d6660-133">Para ver uma lista dos serviços disponíveis, digite:</span><span class="sxs-lookup"><span data-stu-id="d6660-133">To see a list of available services, type:</span></span>

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

<span data-ttu-id="d6660-134">Você pode executar o comando a seguir para excluir o plano de serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="d6660-134">You can run the following command to exclude the Intune service plan.</span></span> <span data-ttu-id="d6660-135">Você pode usar o mesmo método para expandir para um grupo de segurança inteiro ou pode usar filtros mais granulares.</span><span class="sxs-lookup"><span data-stu-id="d6660-135">You can use the same method to expand to an entire security group or you can use more granular filters.</span></span>

<span data-ttu-id="d6660-136">**Exemplo 1**</span><span class="sxs-lookup"><span data-stu-id="d6660-136">**Example 1**</span></span><br>
<span data-ttu-id="d6660-137">Criar um novo usuário na linha de comando e atribuir uma licença do EMS sem habilitar a parte do Intune da licença:</span><span class="sxs-lookup"><span data-stu-id="d6660-137">Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:</span></span>
=======
Se você adicionar usuários manualmente ou sincronizar a partir de seu Active Directory local, primeiro atribua a cada usuário uma licença do Intune para que eles possam registrar seus dispositivos no Intune.

## Atribuir uma licença do Intune no Centro de administração do Office 365
<a id="assign-an-intune-license-in-the-office-365-admin-center" class="xliff"></a>

Use o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD.

1.  Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) usando suas credenciais de administrador de locatário e escolha **Usuários** > **Usuários Ativos**.

2.  Selecione a conta de usuário a qual você deseja atribuir uma licença de usuário do Intune e escolha **Licenças de produto** > **Editar**.

3.  Mude **Intune** ou **Enterprise Mobility + Security** para **Ativado** e escolha **Salvar**.

  ![Imagem da atribuição de Licença do produto no Portal do Office 365.](./media/office-assign-license.png)

4. Agora, a conta de usuário tem as permissões necessárias para usar o serviço e registrar os dispositivos no gerenciamento.

> [!NOTE]
> Os usuários serão exibidos no console de Administração somente após o registro de um dispositivo. Além disso, você pode selecionar um grupo de usuários para editar simultaneamente, selecionando adicionar ou substituir uma licença para todos os usuários selecionados.

## Use o School Data Sync para atribuir licenças a usuários no Intune para Educação
<a id="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education" class="xliff"></a>
Se você for uma organização educativa, poderá usar o SDS (School Data Sync) para atribuir licenças do Intune para Educação para os usuários sincronizados. Basta escolher a caixa de seleção do Intune para Educação quando você estiver configurando seu perfil de SDS.  

![Imagem da configuração de perfil do SDS](./media/i4e-sds-profile-setup-setting.png)

Quando você atribui uma licença do Intune para Educação, certifique-se de que a licença do Intune A Direct também seja atribuída.

![Imagem da configuração da licença do produto](./media/i4e-set-licenses.png)

Veja esta [visão geral do School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) para saber mais sobre o SDS.

## Como as licenças de usuário e dispositivo afetam o acesso a serviços
<a id="how-user-and-device-licenses-affect-access-to-services" class="xliff"></a>
* Cada **usuário** ao qual você atribui uma licença de software de usuário pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para gerenciar aplicativos e até 15 dispositivos.
* Cada **dispositivo** ao qual você atribui uma licença de software de dispositivo pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para uso por qualquer número de usuários.
* Se um dispositivo for usado por mais de um usuário, cada um deles precisará de uma licença de software de dispositivo ou todos os usuários precisarão de uma licença de software de usuário.

## Usar o PowerShell para gerenciar seletivamente licenças de usuário do EMS
<a id="use-powershell-to-selectively-manage-ems-user-licenses" class="xliff"></a>
As organizações que usam o Microsoft Enterprise Mobility + Security (conhecido anteriormente como Enterprise Mobility Suite) podem ter usuários que precisam apenas do Azure Active Directory Premium ou dos serviços do Intune no pacote do EMS. Você pode atribuir um serviço ou um subconjunto de serviços usando os [cmdlets do PowerShell do Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).

Para atribuir seletivamente licenças de usuário para serviços do EMS, abra o PowerShell como administrador em um computador com o [Módulo do Azure Active Directory para Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) instalado. Você pode instalar o PowerShell em um computador local ou em um servidor do ADFS.

Você precisa criar uma nova definição de SKU de licença que se aplique apenas aos planos de serviço desejados. Para fazer isso, desabilite os planos que não deseja aplicar. Por exemplo, você pode criar uma definição de SKU de licença que não atribui uma licença do Intune. Para ver uma lista dos serviços disponíveis, digite:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Você pode executar o comando a seguir para excluir o plano de serviço do Intune. Você pode usar o mesmo método para expandir para um grupo de segurança inteiro ou pode usar filtros mais granulares.

**Exemplo 1**<br>
Criar um novo usuário na linha de comando e atribuir uma licença do EMS sem habilitar a parte do Intune da licença:
>>>>>>> live

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


<<<<<<< HEAD
<span data-ttu-id="d6660-138">Verifique com:</span><span class="sxs-lookup"><span data-stu-id="d6660-138">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

<span data-ttu-id="d6660-139">**Exemplo 2**</span><span class="sxs-lookup"><span data-stu-id="d6660-139">**Example 2**</span></span><br>
<span data-ttu-id="d6660-140">Desabilitar a parte do Intune da licença do EMS para um usuário a que já foi atribuída uma licença:</span><span class="sxs-lookup"><span data-stu-id="d6660-140">Disable the Intune portion of EMS license for a user that is already assigned with a license:</span></span>
=======
Verifique com:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Exemplo 2**<br>
Desabilitar a parte do Intune da licença do EMS para um usuário a que já foi atribuída uma licença:
>>>>>>> live

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

<<<<<<< HEAD
<span data-ttu-id="d6660-141">Verifique com:</span><span class="sxs-lookup"><span data-stu-id="d6660-141">Verify with:</span></span>
=======
Verifique com:
>>>>>>> live

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
