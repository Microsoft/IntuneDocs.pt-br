---
title: "Atribuir licenças do Intune"
description: "Atribuir licenças a usuários para sua assinatura do Intune"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2ad754ce3d81469bb172081b6b7f43937f45ffd9
ms.sourcegitcommit: cccbb6730a8c84dc3a62093b8910305081ac9d24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2018
---
# <a name="assign-intune-licenses-to-your-user-accounts"></a>Atribuir licenças do Intune a suas contas de usuário

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Se você adicionar usuários manualmente ou sincronizar a partir de seu Active Directory local, primeiro atribua a cada usuário uma licença do Intune para que eles possam registrar seus dispositivos no Intune. Para obter uma lista das licenças, consulte [Licenças que incluem o Intune](licenses.md).

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Atribuir uma licença do Intune no Centro de administração do Office 365

Use o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do seu Active Directory local ao Azure AD.

1.  Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) usando suas credenciais de administrador de locatário e escolha **Usuários** > **Usuários Ativos**.

2.  Selecione a conta de usuário a qual você deseja atribuir uma licença de usuário do Intune e escolha **Licenças de produto** > **Editar**.

3.  Mude **Intune** ou **Enterprise Mobility + Security** para **Ativado** e escolha **Salvar**.

  ![Imagem da atribuição de Licença do produto no Portal do Office 365.](./media/office-assign-license.png)

4. Agora, a conta de usuário tem as permissões necessárias para usar o serviço e registrar os dispositivos no gerenciamento.

> [!NOTE]
> Os usuários serão exibidos no console de Administração somente após o registro de um dispositivo. Além disso, você pode selecionar um grupo de usuários para editar simultaneamente, selecionando adicionar ou substituir uma licença para todos os usuários selecionados.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Use o School Data Sync para atribuir licenças a usuários no Intune para Educação
Se você for uma organização educativa, poderá usar o SDS (School Data Sync) para atribuir licenças do Intune para Educação para os usuários sincronizados. Basta escolher a caixa de seleção do Intune para Educação quando você estiver configurando seu perfil de SDS.  

![Imagem da configuração de perfil do SDS](./media/i4e-sds-profile-setup-setting.png)

Quando você atribui uma licença do Intune para Educação, certifique-se de que a licença do Intune A Direct também seja atribuída.

![Imagem da configuração da licença do produto](./media/i4e-set-licenses.png)

Veja esta [visão geral do School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91) para saber mais sobre o SDS.

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Como as licenças de usuário e dispositivo afetam o acesso a serviços
* Cada **usuário** ao qual você atribui uma licença de software de usuário pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para gerenciar aplicativos e até 15 dispositivos.
* Cada **dispositivo** ao qual você atribui uma licença de software de dispositivo pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para uso por qualquer número de usuários.
* Se um dispositivo for usado por mais de um usuário, cada um deles precisará de uma licença de software de dispositivo ou todos os usuários precisarão de uma licença de software de usuário.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Usar o PowerShell para gerenciar seletivamente licenças de usuário do EMS
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

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Verifique com:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
