---
title: "Gerenciar licenças do Intune usando o PowerShell"
description: "Gerenciar licenças do Intune com o PowerShell"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 35bb4e87888a8769b3606659b93e3a73480b566f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="97bcd-103">Gerenciar licenças do Intune usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="97bcd-103">Manage Intune licenses using PowerShell</span></span>
<a id="manage-intune-licenses-using-powershell" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="97bcd-104">Este tópico informa os administradores como eles usam o PowerShell para gerenciar licenças de usuário do Intune.</span><span class="sxs-lookup"><span data-stu-id="97bcd-104">This topic tells administrators how they use PowerShell to manage Intune user licenses.</span></span>

<span data-ttu-id="97bcd-105">Antes que os usuários possam entrar para usar o serviço do Intune ou registrar seus dispositivos no gerenciamento, ele deverão primeiro ser atribuídos a uma licença para sua assinatura do Intune, conforme descrito em [Manage Intune licenses](/intune/licenses-assign) (Gerenciar licenças do Intune).</span><span class="sxs-lookup"><span data-stu-id="97bcd-105">Before users can sign in to use the Intune service or enroll their devices into management, you must first assign each user a license to your Intune subscription, as described in [Manage Intune licenses](/intune/licenses-assign).</span></span> <span data-ttu-id="97bcd-106">No entanto, as organizações que usam Microsoft Enterprise Mobility + Security podem ter usuários que precisam apenas dos serviços do Azure Active Directory Premium ou do Intune no pacote do EMS.</span><span class="sxs-lookup"><span data-stu-id="97bcd-106">However, organizations that use Microsoft Enterprise Mobility + Security might have users who only require Azure Active Directory Premium or Intune services in the EMS package.</span></span> <span data-ttu-id="97bcd-107">Você pode atribuir um serviço ou um subconjunto de serviços usando os [cmdlets do PowerShell do Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).</span><span class="sxs-lookup"><span data-stu-id="97bcd-107">You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).</span></span>

<span data-ttu-id="97bcd-108">Para atribuir seletivamente licenças de usuário para serviços do EMS, abra o PowerShell como administrador em um computador com o [Módulo do Azure Active Directory para Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) instalado.</span><span class="sxs-lookup"><span data-stu-id="97bcd-108">To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed.</span></span> <span data-ttu-id="97bcd-109">Você pode instalar o PowerShell em um computador local ou em um servidor do ADFS.</span><span class="sxs-lookup"><span data-stu-id="97bcd-109">You can install PowerShell on a local computer or on an ADFS server.</span></span>

<span data-ttu-id="97bcd-110">Você precisa criar uma nova definição de SKU de licença que se aplique apenas aos planos de serviço desejados.</span><span class="sxs-lookup"><span data-stu-id="97bcd-110">You must create a new license SKU definition that applies only to the desired service plans.</span></span> <span data-ttu-id="97bcd-111">Para fazer isso, desabilite os planos que não deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="97bcd-111">To do this, disable the plans you don’t want to apply.</span></span> <span data-ttu-id="97bcd-112">Por exemplo, você pode criar uma definição de SKU de licença que não atribui uma licença do Intune.</span><span class="sxs-lookup"><span data-stu-id="97bcd-112">For example, you might create a license SKU definition that does not assign an Intune license.</span></span> <span data-ttu-id="97bcd-113">Para ver uma lista dos serviços disponíveis, digite:</span><span class="sxs-lookup"><span data-stu-id="97bcd-113">To see a list of available services, type:</span></span>

    (Get-MsolAccountSku | Where {$\_.SkuPartNumber -eq "EMS"}).ServiceStatus

<span data-ttu-id="97bcd-114">Você pode executar o comando a seguir para excluir o plano de serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="97bcd-114">You can run the following command to exclude the Intune service plan.</span></span> <span data-ttu-id="97bcd-115">Você pode usar o mesmo método para expandir para um grupo de segurança inteiro ou pode usar filtros mais granulares.</span><span class="sxs-lookup"><span data-stu-id="97bcd-115">You can use the same method to expand to an entire security group or you can use more granular filters.</span></span>

<span data-ttu-id="97bcd-116">**Exemplo 1** Criar um novo usuário na linha de comando e atribuir uma licença do EMS sem habilitar a parte do Intune da licença:</span><span class="sxs-lookup"><span data-stu-id="97bcd-116">**Example 1** Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:</span></span>

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


<span data-ttu-id="97bcd-117">Verifique com:</span><span class="sxs-lookup"><span data-stu-id="97bcd-117">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

<span data-ttu-id="97bcd-118">**Exemplo 2** Desabilitar a parte do Intune da licença do EMS para um usuário para o qual já foi atribuída uma licença:</span><span class="sxs-lookup"><span data-stu-id="97bcd-118">**Example 2** Disable the Intune portion of EMS license for a user that is already assigned with a license:</span></span>

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

<span data-ttu-id="97bcd-119">Verifique com:</span><span class="sxs-lookup"><span data-stu-id="97bcd-119">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### <span data-ttu-id="97bcd-121">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="97bcd-121">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="97bcd-122">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="97bcd-122">Congratulations!</span></span> <span data-ttu-id="97bcd-123">Você acabou de concluir a etapa 4 do *Intune quick start guide* (Guia de início rápido do Intune).</span><span class="sxs-lookup"><span data-stu-id="97bcd-123">You have just completed step 4 of the *Intune quick start guide*.</span></span>
>[!div class="step-by-step"]
<span data-ttu-id="97bcd-124">(/intune/custom-domain-name-configure) [&larr; **Sincronizar usuários com o Intune**](/intune/custom-domain-name-configure)     [**Organizar usuários e dispositivos** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)</span><span class="sxs-lookup"><span data-stu-id="97bcd-124">(/intune/custom-domain-name-configure) [&larr; **Sync users to Intune**](/intune/custom-domain-name-configure)     [**Organize users and devices** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)</span></span>  
