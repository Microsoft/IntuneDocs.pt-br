---
title: Atribuir licenças do Microsoft Intune
description: Atribuir licenças aos usuários para que possam se registrar no Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: dcdc2b69de52ea3bf23f4e3c5d11399b62bc8daa
ms.sourcegitcommit: 60f0ff6d2efbae0f2ce14b9a9f3f9267309e209b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73414087"
---
# <a name="assign-licenses-to-users-so-they-can-enroll-devices-in-intune"></a>Atribuir licenças aos usuários para que possam registrar dispositivos no Intune

Se você adicionar usuários manualmente ou sincronizar a partir de seu Active Directory local, primeiro atribua a cada usuário uma licença do Intune para que eles possam registrar seus dispositivos no Intune. Para obter uma lista das licenças, consulte [Licenças que incluem o Intune](../licenses.md).

## <a name="assign-an-intune-license-in-the-microsoft-365-admin-center"></a>Atribuir uma licença do Intune no Centro de administração do Microsoft 365

Use o [centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) para adicionar manualmente usuários baseados em nuvem e atribuir licenças a contas de usuário baseadas em nuvem e contas sincronizadas do Active Directory local ao Azure AD.

1. Entre no [centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) usando suas credenciais de administrador de locatário e escolha **Usuários** > **Usuários Ativos**.

2. Selecione a conta de usuário a qual você deseja atribuir uma licença de usuário do Intune e escolha **Licenças de produto** > **Editar**.

3. Mude **Intune** ou **Enterprise Mobility + Security** para **Ativado** e escolha **Salvar**.

   ![Captura de tela do portal da seção Licenças do produto do centro de administração do Microsoft 365.](./media/licenses-assign/office-assign-license.png)

4. Agora, a conta de usuário tem as permissões necessárias para usar o serviço e registrar os dispositivos no gerenciamento.

> [!NOTE]
> Os usuários aparecerão no portal clássico do Intune somente depois que tiverem registrado um dispositivo usando o cliente de computador do Intune. Além disso, você pode selecionar um grupo de usuários para editar simultaneamente, selecionando adicionar ou substituir uma licença para todos os usuários selecionados.

## <a name="assign-an-intune-license-by-using-azure-active-directory"></a>Atribuir uma licença do Intune usando o Azure Active Directory

Você também pode atribuir licenças do Intune aos usuários usando o Azure Active Directory. Para saber mais, confira o artigo [Licenciar usuários no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal). 

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Use o School Data Sync para atribuir licenças a usuários no Intune para Educação

Se você for uma organização educativa, poderá usar o SDS (School Data Sync) para atribuir licenças do Intune para Educação para os usuários sincronizados. Basta escolher a caixa de seleção do Intune para Educação quando você estiver configurando seu perfil de SDS.  

![Captura de tela da configuração de perfil do SDS](./media/licenses-assign/i4e-sds-profile-setup-setting.png)

Quando você atribui uma licença do Intune para Educação, certifique-se de que a licença do Intune A Direct também seja atribuída.

![Captura de tela da configuração da licença do produto](./media/licenses-assign/i4e-set-licenses.png)

Veja esta [visão geral do School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91) para saber mais sobre o SDS.

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Como as licenças de usuário e dispositivo afetam o acesso a serviços

* Cada **usuário** ao qual você atribui uma licença de software de usuário pode acessar e usar os serviços online e o software relacionado (incluindo o software do System Center) para gerenciar aplicativos e até 15 dispositivos MDM. O agente de computador do Intune permite 5 máquinas virtuais e uma máquina virtual por licença de usuário.
* Você pode comprar licenças para qualquer dispositivo separadamente das licenças de usuário. As licenças de dispositivos não precisam ser atribuídas aos dispositivos. Cada dispositivo que acessa e usa os serviços online e o software relacionado (incluindo o software System Center) deve ter uma licença de dispositivo.
* Se um dispositivo for usado por mais de um usuário, cada um deles precisará de uma licença de software de dispositivo ou todos os usuários precisarão de uma licença de software de usuário.

## <a name="understanding-the-type-of-licenses-you-have-purchased"></a>Noções básicas sobre o tipo de licenças adquiridas

A maneira como você adquiriu o Intune determina as informações de assinatura:

- Se você adquirir o Intune por meio de um Contrato Enterprise, as informações de assinatura estarão disponíveis no portal de licença de Volume em **Assinaturas**.
- Se você adquiriu o Intune por meio de um Provedor de soluções de nuvem, verifique com seu revendedor.
- Se você adquiriu o Intune com um CC# ou fatura, então suas licenças serão baseadas no usuário.

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

![PoSH-AddLic-Verify](./media/licenses-assign/posh-addlic-verify.png)
