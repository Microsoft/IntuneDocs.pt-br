---
title: Adicionar scripts do PowerShell no Microsoft Intune para dispositivos Windows 10 – Azure | Microsoft Docs
description: Adicionar scripts do PowerShell, atribuir a política de script para grupos do Azure Active Directory, usar relatórios para monitorar os scripts e ver as etapas para excluir os scripts que você adicionar em dispositivos Windows 10 no Microsoft Intune. Veja também alguns problemas comuns e resoluções.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 444fd63f8c582d35891dfa5aedb9eadd6626e541
ms.sourcegitcommit: 4bd992da609b8bcc85edc2d64fe8128546aa4617
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2019
ms.locfileid: "55303388"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10

Use a extensão de gerenciamento do Intune para carregar scripts do PowerShell no Intune para execução em dispositivos com Windows 10. A extensão de gerenciamento aprimora o MDM (gerenciamento de dispositivo móvel) do Windows 10 e facilita a mudança para o gerenciamento moderno.

## <a name="moving-to-modern-management"></a>Mover para o gerenciamento moderno

O computador do usuário final está passando por uma transformação digital. A TI clássica tradicional concentra-se em uma plataforma de dispositivo único, em dispositivos de negócios, em usuários que trabalham no escritório e em uma variedade de processos de TI manuais e reativos. O local de trabalho moderno usa muitas plataformas que são de propriedade do usuário e da empresa, permite que usuários trabalhem de qualquer lugar e fornece processos de TI automatizados e proativos.

Serviços de MDM, como o Microsoft Intune, podem gerenciar dispositivos móveis e de desktop que executam o Windows 10. O cliente de gerenciamento interno do Windows 10 se comunica com o Intune para executar tarefas de gerenciamento da empresa. Há algumas tarefas que talvez sejam necessárias, como configuração avançada de dispositivo, solução de problemas e gerenciamento de aplicativo Win32 herdado que atualmente não estão disponíveis no Windows 10 MDM. Para esses recursos, você pode executar o cliente de software do Intune em seus dispositivos Windows 10. [Comparar o gerenciamento de computadores Windows como computadores ou dispositivos móveis](pc-management-comparison.md) é um ótimo recurso.

A extensão de gerenciamento do Intune complementa os recursos de MDM internos do Windows 10. Você pode criar scripts do PowerShell para executar nos dispositivos com Windows 10. Por exemplo, você pode criar um script do PowerShell que instala um aplicativo Win32 herdado, carrega o script no Intune, atribui o script a um grupo do Azure AD (Azure Active Directory) e executa o script. Em seguida, você pode monitorar o status de execução do script do início ao fim.

## <a name="prerequisites"></a>Pré-requisitos

A extensão de gerenciamento do Intune tem os seguintes pré-requisitos:

- Dispositivos devem ser Unidos ou registrados para o Azure AD e o Azure AD está configurado para [registro automático no Intune](windows-enroll.md#enable-windows-10-automatic-enrollment). A extensão de gerenciamento do Intune dá suporte a dispositivos Windows ingressados no Azure AD, no domínio híbrido e como cogerenciados.
- Os dispositivos devem executar o Windows 10, versão 1607 ou posteriores.
- O agente de extensão de gerenciamento do Intune é instalado quando um script do PowerShell ou um aplicativo Win32 é implantado em um grupo de segurança de usuários ou dispositivos.

## <a name="create-a-powershell-script-policy"></a>Criar uma política de script do PowerShell 

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Microsoft Intune**.
2. Selecione **Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar**.
3. Insira um **Nome** e **Descrição** para o script do PowerShell. Para **Local do script**, procure pelo script do PowerShell. O script deve ter menos de 200 KB (ASCII) ou 100 KB (Unicode).
4. Escolha **Configurar**. Em seguida, escolha executar o script com as credenciais do usuário no dispositivo (**Sim**) ou no contexto do sistema (**Não**). Por padrão, o script é executado no contexto do sistema. Selecione **Sim**, a menos que seja necessário executar o script no contexto do sistema. 
  ![Adicionar painel de script do PowerShell](./media/mgmt-extension-add-script.png)
5. Escolha se o script deve ser assinado por um distribuidor confiável (**Sim**). Por padrão, não há nenhum requisito para o script ser assinado. 
6. Selecione **OK** e, em seguida, **Criar** para salvar o script.

## <a name="assign-a-powershell-script-policy"></a>Atribuir uma política de script do PowerShell

1. No painel **Scripts do PowerShell**, selecione o script a ser atribuído e, em seguida, escolha **Gerenciar** > **Atribuições**.

    ![Adicionar painel de script do PowerShell](./media/mgmt-extension-assignments.png)

2. Escolha **Selecionar Grupos** para listar os grupos disponíveis do Azure AD. 
3. Selecione um ou mais grupos que contenham os usuários cujos dispositivos recebem o script. **Selecione** para atribuir a política aos grupos selecionados.

> [!NOTE]
> - Os usuários finais não precisam entrar no dispositivo para executar scripts do PowerShell.
> - Os scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do Azure AD.
> - Os scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do Azure AD.

O cliente da extensão de gerenciamento do Intune confere o Intune uma vez a cada hora. Depois de atribuir a política aos grupos do Azure AD, o script do PowerShell é executado e os resultados da execução são relatados.

## <a name="monitor-run-status-for-powershell-scripts"></a>Monitorar status de execução para scripts do PowerShell

Você pode monitorar o status de execução de scripts do PowerShell para usuários e dispositivos no portal do Azure.

No painel **Scripts do PowerShell**, selecione o script a ser monitorado, escolha **Monitorar** e, em seguida, escolha um dos seguintes relatórios:

- **Status do dispositivo**
- **Status do usuário**

## <a name="troubleshoot-powershell-scripts"></a>Solucionar problemas de scripts do PowerShell

Os logs do agente no computador cliente geralmente estão em `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Você pode usar [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) para exibir esses arquivos de log. 

![Captura de tela dos logs do agente](./media/apps-win32-app-10.png)  

## <a name="delete-a-powershell-script"></a>Excluir um script do PowerShell

Em **scripts do PowerShell**, clique com o botão direito do mouse no script e selecione **Excluir**.

## <a name="common-issues-and-resolutions"></a>Problemas comuns e resoluções

Os scripts do PowerShell não são executados em cada entrada. Eles são executados somente após a reinicialização, ou se o serviço **Extensão de Gerenciamento do Microsoft Intune** for reiniciado. O cliente da extensão de gerenciamento do Intune verifica uma vez por hora se há alterações no script ou na política do Intune.

#### <a name="issue-intune-management-extension-doesnt-download"></a>Problema: A extensão de gerenciamento do Intune não baixa

**Possíveis resoluções**:

- Verifique se os dispositivos são registrados automaticamente no Azure AD. Para confirmar, no dispositivo: 

  1. Acesse **Configurações** > **Contas** > **Acessar conta corporativa ou de estudante**.
  2. Selecione a conta unida > **Informações**.
  3. Em **Relatório de Diagnóstico Avançado**, selecione **Criar Relatório**.
  4. Abra o `MDMDiagReport` em um navegador da Web e vá até a seção **Fontes de configuração registradas**.
  5. Procure a propriedade **MDMDeviceWithAAD**. Se essa propriedade não existir, seu dispositivo não terá sido automaticamente registrado.

    [Habilitar o registro automático do Windows 10](windows-enroll.md#enable-windows-10-automatic-enrollment) contém as etapas para isso.

#### <a name="issue-the-powershell-scripts-do-not-run"></a>Problema: Os scripts do PowerShell não são executados

**Possíveis resoluções**:

- Confirme se a extensão de gerenciamento do Intune foi baixada em `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Os scripts não são executados em Surface Hubs.
- Verifique os logs em `\ProgramData\Microsoft\IntuneManagementExtension\Logs` para ver se há erros.
- Para possíveis problemas de permissão, certifique-se que as propriedades do script do PowerShell estejam definidas como `Run this script using the logged on credentials`. Verifique também se o usuário conectado tem as permissões apropriadas para executar o script.
- Para isolar problemas de script, execute um script de exemplo. Por exemplo, crie o diretório `C:\Scripts` e dê controle total a todos. Execute o seguinte script:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Se tiver êxito, output.txt deve ser criado e deve incluir o texto "Script worked" (O script funcionou).

- Para testar a execução do script sem o Intune, execute os scripts sob o Contexto do Sistema usando a [ferramenta psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) localmente:

  `psexec -i -s`

## <a name="next-steps"></a>Próximas etapas

[Monitorar](device-profile-monitor.md) e [solucionar problemas](device-profile-troubleshoot.md) de seus perfis.
