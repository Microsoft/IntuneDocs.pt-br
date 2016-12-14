---
title: "Licenças do Microsoft Intune | Microsoft Intune"
description: "Atribuir licenças a usuários para sua assinatura do Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: f0f9d60a27afa580aaba8a3c24fff6325ae53f08


---

# <a name="manage-intune-licenses"></a>Gerenciar licenças do Intune
Antes que os usuários possam entrar para usar o serviço do Intune ou registrar seus dispositivos no gerenciamento, você deve primeiro atribuir a cada usuário uma licença para sua assinatura do Intune usando o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854).

As organizações que usam o EMS (Enterprise Mobility + Security) da Microsoft podem ter usuários que precisam apenas dos serviços do Azure Active Directory Premium ou do Intune no pacote do EMS. Você pode atribuir um serviço ou um subconjunto de serviços usando os [cmdlets do PowerShell do Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx). Para obter mais informações, consulte [Manage Intune licenses using PowerShell](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md) (Gerenciar licenças do Intune usando o PowerShell).

## <a name="how-intune-licenses-are-assigned"></a>Como as licenças do Intune são atribuídas
Quando contas do usuário forem sincronizadas com o Active Directory local ou adicionadas manualmente à sua assinatura dos serviços de nuvem por meio do [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), não lhes serão atribuídas automaticamente licenças do Intune. Em vez disso, posteriormente, um administrador de locatários do Intune precisa editar a conta do usuário para atribuir uma licença ao usuário do portal do Office 365.

Quando sua assinatura compartilha o Azure AD com outros serviços de nuvem associados a ela, você também tem acesso a usuários que foram adicionados a esses serviços. Esses usuários não possuirão a licença do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] até que você a atribua a cada um.

> [!TIP]
> Se a opção de atribuir ou revogar uma licença do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] estiver desabilitada, sua assinatura poderá incluir opções de licenciamento por volume, como as disponíveis ao usar o [Enterprise Mobility Suite + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Para obter informações sobre como atribuir ou revogar licenças, consulte a documentação das opções de licenciamento.

## <a name="assign-an-intune-user-license"></a>Atribuir uma licença de usuário do Intune

Você usa o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD.

1.  Entre no [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) usando suas credenciais de administrador de locatário e selecione **Pessoas** > **Todos os Usuários**.

2.  Selecione a conta de usuário para a qual deseja atribuir uma licença de usuário do Intune e selecione **Microsoft Intune** (autônomo) ou **Enterprise Mobility Suite**.

3.  Agora, a conta de usuário tem as permissões necessárias para usar o serviço e registrar dispositivos no gerenciamento.

> [!NOTE]
> Os usuários serão exibidos no console depois de registrar um dispositivo.

### <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Usar o PowerShell para gerenciar seletivamente licenças de usuário do EMS
As organizações que usam o Microsoft Enterprise Mobility + Security (conhecido anteriormente como Enterprise Mobility Suite) podem ter usuários que precisam apenas do Azure Active Directory Premium ou dos serviços do Intune no pacote do EMS. Você pode atribuir um serviço ou um subconjunto de serviços usando os [cmdlets do PowerShell do Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx).

Para atribuir seletivamente licenças de usuário para serviços do EMS, abra o PowerShell como administrador em um computador com o [Módulo do Azure Active Directory para Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) instalado. Você pode instalar o PowerShell em um computador local ou em um servidor do ADFS.

Você precisa criar uma nova definição de SKU de licença que se aplique apenas aos planos de serviço desejados. Para fazer isso, desabilite os planos que não deseja aplicar. Por exemplo, você pode criar uma definição de SKU de licença que não atribui uma licença do Intune. Para ver uma lista dos serviços disponíveis, digite:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Você pode executar o comando a seguir para excluir o plano de serviço do Intune. Você pode usar o mesmo método para expandir para um grupo de segurança inteiro ou pode usar filtros mais granulares.

**Exemplo 1**<br>
Criar um novo usuário na linha de comando e atribuir uma licença do EMS sem habilitar a parte do Intune da licença:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Verifique com:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Exemplo 2**<br>
Desabilitar a parte do Intune da licença do EMS para um usuário a que já foi atribuída uma licença:

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

Verifique com:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

>[!div class="step-by-step"]

>[&larr; **Sincronizar usuários ao Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizar usuários e dispositivos** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  



<!--HONumber=Dec16_HO2-->

