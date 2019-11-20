---
title: Adicionar scripts do PowerShell a dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Crie e execute scripts do PowerShell, atribua a política de script a grupos do Azure Active Directory, use relatórios para monitorar os scripts e veja as etapas para excluir os scripts adicionados em dispositivos Windows 10 no Microsoft Intune. Veja também alguns problemas comuns e resoluções.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1d73d28f34258bce99199731579969604c0a3d97
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059717"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Use scripts do PowerShell em dispositivos Windows 10 no Intune

Use a extensão de gerenciamento do Microsoft Intune para carregar scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão de gerenciamento aprimora o MDM (gerenciamento de dispositivo móvel) do Windows 10 e facilita a mudança para o gerenciamento moderno.

Esse recurso aplica-se a:

- Windows 10 e posterior

## <a name="move-to-modern-management"></a>Mover para o gerenciamento moderno

O computador do usuário final está passando por uma transformação digital. A TI clássica tradicional concentra-se em uma plataforma de dispositivo único, em dispositivos de negócios, em usuários que trabalham no escritório e em diferentes processos de TI reativos e manuais. O local de trabalho moderno usa muitas plataformas que são de propriedade do usuário e da empresa, permite que usuários trabalhem de qualquer lugar e fornece processos de TI automatizados e proativos.

Serviços de MDM, como o Microsoft Intune, podem gerenciar dispositivos móveis e de desktop que executam o Windows 10. O cliente de gerenciamento interno do Windows 10 se comunica com o Intune para executar tarefas de gerenciamento da empresa. Talvez você precise de algumas tarefas, como configuração avançada de dispositivo e solução de problemas. Para gerenciamento de aplicativo do Win32, você pode usar o recurso [Gerenciamento de aplicativo Win32](app-management.md) em seus dispositivos com Windows 10.

A extensão de gerenciamento do Intune complementa os recursos de MDM internos do Windows 10. Você pode criar scripts do PowerShell para serem executados em dispositivos Windows 10. Por exemplo, crie um script do PowerShell que faça configurações avançadas do dispositivo. Em seguida, carregue o script no Intune, atribua o script a um grupo do Azure AD (Azure Active Directory) e execute-o. Em seguida, você pode monitorar o status de execução do script do início ao fim.

## <a name="prerequisites"></a>Pré-requisitos

A extensão de gerenciamento do Intune tem os pré-requisitos a seguir. Depois que os pré-requisitos forem atendidos, a extensão de gerenciamento do Intune será instalada automaticamente quando um script do PowerShell ou um aplicativo Win32 for atribuído ao usuário ou ao dispositivo.

- Dispositivos executando o Windows 10 versão 1607 ou posterior. Se o dispositivo é registrado usando o [registro automático em massa](../enrollment/windows-bulk-enroll.md), os dispositivos precisam executar o Windows 10 versão 1703 ou posterior. A extensão de gerenciamento do Intune não é compatível com o Windows 10 no modo S, já que o modo S não permite a execução de aplicativos que não fazem parte da loja. 
  
- Dispositivos que ingressaram no Azure AD (Active Directory), incluindo:  
  
  - Com ingresso híbrido realizado no Azure AD: Dispositivos ingressados no Azure AD (Active Directory) e também ingressados no AD (Active Directory) local. Para obter orientação, confira [Planejar sua implementação de ingresso híbrido no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).

- Dispositivos registrados no Intune, incluindo:

  - Dispositivos registrados em uma política de grupo (GPO). Veja [Registrar um dispositivo Windows 10 automaticamente usando a Política de Grupo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) para obter orientação.
  
  - Dispositivos manualmente registrados no Intune, que é quando:
  
    - O [Registro automático do Intune](../enrollment/quickstart-setup-auto-enrollment.md) está habilitado no Azure AD. O usuário final se conecta ao dispositivo usando uma conta de usuário local, ingressa o dispositivo manualmente no Azure AD e entra no dispositivo usando a conta do Azure AD.
    
    OU  
    
    - O usuário se conecta ao dispositivo usando sua conta do Azure AD e, em seguida, registra-se no Intune.

  - Dispositivos cogerenciados que usam o Configuration Manager e o Intune. Verifique se a carga de trabalho **Aplicativos de cliente** está definida como **Pilot Intune** ou **Intune**. Confira os seguintes artigos para obter diretrizes: 
  
    - [O que é cogerenciamento](https://docs.microsoft.com/sccm/comanage/overview) 
    - [carga de trabalho de aplicativos cliente](https://docs.microsoft.com/sccm/comanage/workloads#client-apps)
    - [Mudar as cargas de trabalho do Configuration Manager para o Intune](https://docs.microsoft.com/sccm/comanage/how-to-switch-workloads)
  
> [!TIP]
> Verifique se os dispositivos estão [unidos](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) ao Azure AD. Os dispositivos que estão apenas [registrados](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) no Azure AD não receberão seus scripts.

## <a name="create-a-script-policy-and-assign-it"></a>Criar uma política de script e atribuí-la

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar**.

    ![Adicionar e usar scripts do PowerShell no Microsoft Intune](./media/intune-management-extension/mgmt-extension-add-script.png)

3. Em **Noções Básicas**, insira as seguintes propriedades e selecione **Avançar**:
    - **Nome**: insira um nome para o script do PowerShell. 
    - **Descrição**: insira uma descrição para o script do PowerShell. Essa configuração é opcional, mas recomendada.
4. Em **Configurações de script**, insira as seguintes propriedades e selecione **Avançar**:
    - **Local do script**: navegue até o script do PowerShell. O script deve ter menos de 200 KB (ASCII).
    - **Executar este script usando as credenciais de logon**: selecione **Sim** para executar o script com as credenciais do usuário no dispositivo. escolha **Não** (padrão) para executar o script no contexto do sistema. Muitos administradores escolhem **Sim**. Se for necessário executar o script no contexto do sistema, escolha **Não**.
    - **Impor a verificação de assinatura de script**: selecione **Sim** se for necessário que o script seja assinado por um fornecedor confiável. selecione **Não** (padrão) se não houver um requisito para o script ser assinado. 
    - **Executar o script em um host do PowerShell de 64 bits**: selecione **Sim** para executar o script em um host do PS (PowerShell) de 64 bits em uma arquitetura de cliente de 64 bits. selecione **Não** (padrão) para executar o script em um host do PowerShell de 32 bits.

      Ao definir como **Sim** ou **Não**, use a tabela a seguir para um comportamento de política novo ou existente:

      | execute o script no host do PS de 64 bits | arquitetura do cliente | novo script do PS | script do PS de política existente |
      | --- | --- | --- | --- | 
      | Não | 32 bits  | Host do PS de 32 bits com suporte | É executado somente no host do PS de 32 bits, que funciona em arquiteturas de 32 bits e de 64 bits. |
      | Sim | 64 bits | Executa o script no host do PS de 64 bits para arquiteturas de 64 bits. Quando executados em 32 bits, o script é executado em um host do PS de 32 bits. | Executa o script no host do PS de 32 bits. Se essa configuração for alterada para 64 bits, o script será aberto (ele não será executado) em um host do PS de 64 bits e relatará os resultados. Quando executados em 32 bits, o script é executado em um host do PS de 32 bits. |

5. Selecione **Marcas de escopo**. As marcas de escopo são opcionais. [Usar o RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída](../fundamentals/scope-tags.md) traz mais informações.

    Para adicionar uma marca de escopo:

    1. Escolha **Selecionar marcas de escopo** > selecione uma marca de escopo existente na lista > **Selecionar**.

    2. Quando terminar, selecione **Avançar**.

6. Selecione **Atribuições** > **Selecionar grupos a serem incluídos**. Uma lista existente de grupos do Azure AD é mostrada.

    1. Selecione um ou mais grupos que contenham os usuários cujos dispositivos recebem o script. Escolha **Selecionar**. Os grupos escolhidos são mostrados na lista e receberão sua política.

        > [!NOTE]
        > Os scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo ou grupos de segurança de usuário do Azure AD.

    2. Selecione **Avançar**.

        ![Atribuir ou implantar o script do PowerShell em grupos de dispositivos no Microsoft Intune](./media/intune-management-extension/mgmt-extension-assignments.png)

7. Em **Examinar + adicionar**, é mostrado um resumo das configurações definidas. Selecione **Adicionar** para salvar o script. Quando você seleciona **Adicionar**, a política é implantada nos grupos escolhidos.

## <a name="important-considerations"></a>Considerações importantes

- Quando os scripts estão definidos para o contexto de usuário e o usuário final tem direitos de administrador, por padrão, o script do PowerShell é executado sob o privilégio de administrador.

- Os usuários finais não precisam entrar no dispositivo para executar scripts do PowerShell.

- O cliente da extensão de gerenciamento do Intune verifica no Intune uma vez por hora e após cada reinicialização se há novos scripts ou alterações. Depois de atribuir a política aos grupos do Azure AD, o script do PowerShell é executado e os resultados da execução são relatados. Após a execução do script, ele não será executado novamente, a menos que haja uma alteração no script ou na política.

## <a name="monitor-run-status"></a>Monitorar status de execução

Você pode monitorar o status de execução de scripts do PowerShell para usuários e dispositivos no portal do Azure.

No painel **Scripts do PowerShell**, selecione o script a ser monitorado, escolha **Monitorar** e, em seguida, escolha um dos seguintes relatórios:

- **Status do dispositivo**
- **Status do usuário**

## <a name="intune-management-extension-logs"></a>Logs da extensão de gerenciamento do Intune

Os logs do agente no computador cliente geralmente estão em `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Você pode usar [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) para exibir esses arquivos de log. 

![Captura de tela ou exemplo de logs do agente cmtrace no Microsoft Intune](./media/apps-win32-app-management/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Excluir um script

Em **scripts do PowerShell**, clique com o botão direito do mouse no script e selecione **Excluir**.

## <a name="common-issues-and-resolutions"></a>Problemas comuns e resoluções

### <a name="issue-intune-management-extension-doesnt-download"></a>Problema: A extensão de gerenciamento do Intune não baixa

**Possíveis resoluções**:

- O dispositivo não está ingressado no Azure AD. Verifique se os dispositivos atendem aos [pré-requisitos](#prerequisites) (neste artigo). 
- Não há scripts do PowerShell nem aplicativos Win32 atribuídos aos grupos aos quais o usuário ou dispositivo pertence.
- O dispositivo não pode fazer check-in com o serviço do Intune devido à ausência de acesso à Internet, acesso ao WNS (Serviços de Notificação por Push do Windows) e assim por diante.
- O dispositivo está no modo S. A extensão de gerenciamento do Intune não é compatível com dispositivos que executam no modo S. 

Passos para ver se o dispositivo é registrado automaticamente:

  1. Acesse **Configurações** > **Contas** > **Acessar conta corporativa ou de estudante**.
  2. Selecione a conta unida > **Informações**.
  3. Em **Relatório de Diagnóstico Avançado**, selecione **Criar Relatório**.
  4. Abra o `MDMDiagReport` em um navegador da Web.
  5. Procure a propriedade **MDMDeviceWithAAD**. Se a propriedade existe, o dispositivo é registrado automaticamente. Se essa propriedade não existe, o dispositivo não foi registrado automaticamente.

[Habilitar o registro automático do Windows 10](../enrollment/windows-enroll.md#enable-windows-10-automatic-enrollment) inclui as etapas para configurar o registro automático no Intune.

### <a name="issue-powershell-scripts-do-not-run"></a>Problema: os scripts do PowerShell não são executados

**Possíveis resoluções**:

- Os scripts do PowerShell não são executados em cada entrada. Eles são executados:

  - Quando o script é atribuído a um dispositivo
  - Se você alterar o script, carregue-o e atribua-o a um usuário ou dispositivo
  
    > [!TIP]
    > A **Extensão de gerenciamento do Microsoft Intune** é um serviço que é executado no dispositivo, assim como qualquer outro serviço listado no aplicativo de Serviços (services.msc). Após a reinicialização de um dispositivo, esse serviço também pode reiniciar e verificar se há qualquer script do PowerShell atribuído com o serviço Intune. Se o serviço **Extensão de Gerenciamento do Microsoft Intune** for definido como Manual, o serviço poderá não ser reiniciado depois que o dispositivo for reinicializado.

- Verifique se os dispositivos estão [unidos ao Azure AD](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Os dispositivos que só fazem parte de seu local de trabalho ou organização ([registrados](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) no Azure AD) não receberão os scripts.
- O cliente de extensão de gerenciamento do Intune verifica uma vez por hora se há alterações no script ou na política no Intune.
- Confirme se a extensão de gerenciamento do Intune foi baixada em `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Scripts não são executados nos Surface Hubs nem no Windows 10 no modo S.
- Examine os logs em busca de erros. Confira [Logs da extensão de gerenciamento do Intune](#intune-management-extension-logs) (neste artigo).
- Para possíveis problemas de permissão, certifique-se que as propriedades do script do PowerShell estejam definidas como `Run this script using the logged on credentials`. Verifique também se o usuário conectado tem as permissões apropriadas para executar o script.

- Para isolar problemas de script, faça o seguinte:

  - Examine a configuração de execução do PowerShell em seus dispositivos. Consulte a [Política de execução do PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) para obter orientação.
  - Execute um script de exemplo usando a extensão de gerenciamento do Intune. Por exemplo, crie o diretório `C:\Scripts` e dê controle total a todos. Execute o seguinte script:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Se tiver êxito, output.txt deve ser criado e deve incluir o texto "Script worked" (O script funcionou).

  - Para testar a execução do script sem o Intune, execute os scripts na conta do Sistema usando a [ferramenta psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) localmente:

    `psexec -i -s`  
    
  - Caso o script relate que obteve êxito quando, na verdade, não obteve, é possível que seu serviço de antivírus tenha colocado o AgentExecutor na área restrita. O script a seguir sempre relata uma falha no Intune. Como um teste, você pode usar este script:
  
    ```powershell
    Write-Error -Message "Forced Fail" -Category OperationStopped
    mkdir "c:\temp" 
    echo "Forced Fail" | out-file c:\temp\Fail.txt
    ```

    Se o script relatar que obteve êxito, confira `AgentExecutor.log` para confirmar a saída do erro. Se o script for executado, o comprimento deverá ser >2.

  - Para capturar os arquivos .error e .output, o snippet a seguir executa o script pelo AgentExecutor para PSx86 (`C:\Windows\SysWOW64\WindowsPowerShell\v1.0`). Ele mantém os logs para sua análise. Lembre-se que a Extensão de Gerenciamento do Intune limpa os logs após a execução do script:
  
    ```powershell
    $scriptPath = read-host "Enter the path to the script file to execute"
    $logFolder = read-host "Enter the path to a folder to output the logs to"
    $outputPath = $logFolder+"\output.output"
    $errorPath =  $logFolder+"\error.error"
    $timeoutPath =  $logFolder+"\timeout.timeout"
    $timeoutVal = 60000 
    $PSFolder = "C:\Windows\SysWOW64\WindowsPowerShell\v1.0"
    $AgentExec = "C:\Program Files (x86)\Microsoft Intune Management Extension\agentexecutor.exe"
    &$AgentExec -powershell  $scriptPath $outputPath $errorPath $timeoutPath $timeoutVal $PSFolder 0 0
    ```

## <a name="next-steps"></a>Próximas etapas

[Monitorar](../device-profile-monitor.md) e [solucionar problemas](../device-profile-troubleshoot.md) de seus perfis.
