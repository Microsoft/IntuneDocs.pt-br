---
title: Adicionar scripts do PowerShell a dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Crie e execute scripts do PowerShell, atribua a política de script a grupos do Azure Active Directory, use relatórios para monitorar os scripts e veja as etapas para excluir os scripts adicionados em dispositivos Windows 10 no Microsoft Intune. Veja também alguns problemas comuns e resoluções.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/03/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 66a23b75913f6465064a988bd8f2ba9c2b4c36d6
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514101"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Use scripts do PowerShell em dispositivos Windows 10 no Intune

Use a extensão de gerenciamento do Microsoft Intune para carregar scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão de gerenciamento aprimora o MDM (gerenciamento de dispositivo móvel) do Windows 10 e facilita a mudança para o gerenciamento moderno.

Esse recurso aplica-se a:

- Windows 10 e posterior

## <a name="move-to-modern-management"></a>Mover para o gerenciamento moderno

O computador do usuário final está passando por uma transformação digital. A TI clássica tradicional concentra-se em uma plataforma de dispositivo único, em dispositivos de negócios, em usuários que trabalham no escritório e em diferentes processos de TI reativos e manuais. O local de trabalho moderno usa muitas plataformas que são de propriedade do usuário e da empresa, permite que usuários trabalhem de qualquer lugar e fornece processos de TI automatizados e proativos.

Serviços de MDM, como o Microsoft Intune, podem gerenciar dispositivos móveis e de desktop que executam o Windows 10. O cliente de gerenciamento interno do Windows 10 se comunica com o Intune para executar tarefas de gerenciamento da empresa. Talvez você precise de algumas tarefas, como configuração avançada de dispositivo e solução de problemas. Para gerenciamento de aplicativo do Win32, você pode usar o recurso [Gerenciamento de aplicativo Win32](apps-win32-app-management.md) em seus dispositivos com Windows 10.

A extensão de gerenciamento do Intune complementa os recursos de MDM internos do Windows 10. Você pode criar scripts do PowerShell para executar nos dispositivos com Windows 10. Por exemplo, você pode criar um script do PowerShell que executa configurações de dispositivo avançadas, carrega o script no Intune, atribui o script a um grupo do Azure AD (Azure Active Directory) e executa o script. Em seguida, você pode monitorar o status de execução do script do início ao fim.

## <a name="prerequisites"></a>Pré-requisitos

A extensão de gerenciamento do Intune tem os seguintes pré-requisitos:

- Os dispositivos devem ser ingressados ou registrados no Azure AD e configurados no Azure AD e no Intune para [registro automático](quickstart-setup-auto-enrollment.md). A extensão de gerenciamento do Intune dá suporte a dispositivos Windows ingressados no Azure AD, no domínio híbrido do Azure AD e registrados como cogerenciados.
- Os dispositivos devem executar o Windows 10, versão 1607 ou posteriores.
- O agente de extensão de gerenciamento do Intune é instalado quando um script do PowerShell ou um aplicativo Win32 é implantado em um grupo de segurança de usuários ou dispositivos.

## <a name="create-a-script-policy"></a>Criar uma política de script 

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar**.
3. Insira as seguintes propriedades:
    - **Nome**: insira um nome para o script do PowerShell. 
    - **Descrição**: insira uma descrição para o script do PowerShell. Essa configuração é opcional, mas recomendada. 
    - **Local do script**: navegue até o script do PowerShell. O script deve ter menos de 200 KB (ASCII).
4. Escolha **Configurar** e insira as seguintes propriedades:
    - **Executar este script usando as credenciais de logon**: selecione **Sim** para executar o script com as credenciais do usuário no dispositivo. escolha **Não** (padrão) para executar o script no contexto do sistema. Muitos administradores escolhem **Sim**. Se for necessário executar o script no contexto do sistema, escolha **Não**.
    - **Impor a verificação de assinatura de script**: selecione **Sim** se for necessário que o script seja assinado por um fornecedor confiável. selecione **Não** (padrão) se não houver um requisito para o script ser assinado. 
    - **Executar o script em um host do PowerShell de 64 bits**: selecione **Sim** para executar o script em um host do PS (PowerShell) de 64 bits em uma arquitetura de cliente de 64 bits. selecione **Não** (padrão) para executar o script em um host do PowerShell de 32 bits.

      Ao definir como **Sim** ou **Não**, use a tabela a seguir para um comportamento de política novo ou existente:

      | execute o script no host do PS de 64 bits | arquitetura do cliente | novo script do PS | script do PS de política existente |
      | --- | --- | --- | --- | 
      | Não | 32 bits  | Host do PS de 32 bits com suporte | É executado somente no host do PS de 32 bits, que funciona em arquiteturas de 32 bits e de 64 bits. |
      | Sim | 64 bits | Executa o script no host do PS de 64 bits para arquiteturas de 64 bits. Quando executados em 32 bits, o script é executado em um host do PS de 32 bits. | Executa o script no host do PS de 32 bits. Se essa configuração for alterada para 64 bits, o script será aberto (ele não será executado) em um host do PS de 64 bits e relatará os resultados. Quando executados em 32 bits, o script é executado em um host do PS de 32 bits. |

    ![Adicionar e usar scripts do PowerShell no Microsoft Intune](./media/mgmt-extension-add-script.png)
5. Selecione **OK** > **Criar** para salvar o script.

## <a name="assign-the-policy"></a>Atribuir a política

1. No painel **Scripts do PowerShell**, selecione o script a ser atribuído e, em seguida, escolha **Gerenciar** > **Atribuições**.

    ![Atribuir ou implantar o script do PowerShell em grupos de dispositivos no Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Escolha **Selecionar Grupos** para listar os grupos disponíveis do Azure AD. 
3. Selecione um ou mais grupos que contenham os usuários cujos dispositivos recebem o script. **Selecione** para atribuir a política aos grupos selecionados.

> [!NOTE]
> - Os usuários finais não precisam entrar no dispositivo para executar scripts do PowerShell.
> - Os scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do Azure AD.
> - Os scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do Azure AD.

O cliente da extensão de gerenciamento do Intune verifica uma vez por hora e após cada reinicialização com o Intune para novos scripts ou alterações. Depois de atribuir a política aos grupos do Azure AD, o script do PowerShell é executado e os resultados da execução são relatados. Após a execução do script, ele não será executado novamente, a menos que haja uma alteração no script ou na política.

## <a name="monitor-run-status"></a>Monitorar status de execução

Você pode monitorar o status de execução de scripts do PowerShell para usuários e dispositivos no portal do Azure.

No painel **Scripts do PowerShell**, selecione o script a ser monitorado, escolha **Monitorar** e, em seguida, escolha um dos seguintes relatórios:

- **Status do dispositivo**
- **Status do usuário**

## <a name="troubleshoot-scripts"></a>Solucionar problemas de scripts

Os logs do agente no computador cliente geralmente estão em `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Você pode usar [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) para exibir esses arquivos de log. 

![Captura de tela ou exemplo de logs do agente cmtrace no Microsoft Intune](./media/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Excluir um script

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

#### <a name="issue-powershell-scripts-do-not-run"></a>Problema: os scripts do PowerShell não são executados

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
