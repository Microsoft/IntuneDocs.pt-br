---
# required metadata

title: Licenças do Microsoft Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gerenciar licenças do Intune
Um usuário precisa ter uma licença para sua assinatura do Intune antes que possa entrar para usar o serviço ou registrar seus dispositivos no gerenciamento. Quando um usuário tem uma licença, ele é membro do grupo de usuários [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]. Esse grupo inclui todos os usuários com uma licença para usar a assinatura. **Cada licença de usuário dá suporte ao registro de até cinco dispositivos**.

## Como as licenças do Intune são atribuídas
Quando contas do usuário são sincronizadas com o Active Directory local ou adicionadas manualmente à sua assinatura dos serviços de nuvem por meio do portal da conta, não lhes são atribuídas automaticamente licenças do Intune. Em vez disso, posteriormente, um administrador de locatários do Intune precisa editar a conta do usuário para atribuir uma licença ao usuário do portal da conta.

Quando sua assinatura compartilha o Azure AD com outros serviços de nuvem associados a ela, você também tem acesso a usuários que foram adicionados a esses serviços. Esses usuários não possuirão a licença do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] até que você a atribua a cada um.

> [!TIP]
> Se a opção de atribuir ou revogar uma licença do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] estiver desabilitada, sua assinatura poderá incluir opções de licenciamento por volume, como as disponíveis ao usar o [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Para obter informações sobre como atribuir ou revogar licenças, consulte a documentação das opções de licenciamento.

## Atribuir uma licença de usuário do Intune

Você usa o **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD.

1.  Entre no portal de conta do Intune usando suas credenciais de administrador de locatários.

2.  Selecione a conta de usuário a que deseja atribuir uma licença de usuário do Intune e habilite a caixa de seleção **Microsoft Intune** nas propriedades da conta de usuário.

3.  A conta de usuário será adicionada ao grupo de usuários do Microsoft Intune, o que concede ao usuário permissões para usar o serviço e registrar seus dispositivos para gerenciamento.

### Usar o PowerShell para gerenciar seletivamente licenças de usuário do EMS
As organizações que usam o EMS (Enterprise Mobility Suite) da Microsoft podem ter usuários que precisam apenas dos serviços do Azure Active Directory Premium ou do Intune no pacote do EMS. Você pode atribuir um serviço ou um subconjunto de serviços usando [cmdlets do PowerShell do Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx). 

Para atribuir seletivamente licenças de usuário para serviços do EMS, abra o PowerShell como administrador em um computador com o [Módulo do Azure Active Directory para Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) instalado. Você pode instalar o PowerShell em um computador local ou em um servidor do ADFS.

Você precisa criar uma nova definição de SKU de licença que se aplique apenas aos planos de serviço desejados. Para fazer isso, desabilite os planos que não deseja aplicar. Por exemplo, você pode criar uma definição de SKU de licença que não atribui uma licença do Intune. Para ver uma lista dos serviços disponíveis, digite:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Você pode executar o comando a seguir para excluir o plano de serviço do Intune. Você pode usar o mesmo método para expandir para um grupo de segurança inteiro ou pode usar filtros mais granulares. 

**Exemplo 1**
Criar um novo usuário na linha de comando e atribuir uma licença do EMS sem habilitar a parte do Intune da licença:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Verifique com:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Exemplo 2**
Desabilitar a parte do Intune da licença do EMS para um usuário a que já foi atribuída uma licença:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Verifique com:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Próximas etapas
Parabéns! Você acabou de concluir a etapa 4 do *Guia de início rápido do Intune*.
>[!div class="step-by-step"]

>[&larr; **Sincronizar usuários ao Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizar usuários e dispositivos** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->


