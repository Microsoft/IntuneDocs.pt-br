---
title: Adicionar scripts do PowerShell a dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Crie e execute scripts do PowerShell, atribua a política de script a grupos do Azure Active Directory, use relatórios para monitorar os scripts e veja as etapas para excluir os scripts adicionados em dispositivos Windows 10 no Microsoft Intune. Veja também alguns problemas comuns e resoluções.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/28/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f17bdf21db61616f88cef4d257fbcd28d941dae8
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66373465"
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

A extensão de gerenciamento do Intune tem os pré-requisitos a seguir. Quando eles forem atendidos, a extensão de gerenciamento do Intune será instalada automaticamente quando um script do PowerShell ou aplicativo do Win32 for atribuído ao usuário ou dispositivo.

- Dispositivos executando o Windows 10 versão 1607 ou posterior. Se o dispositivo é registrado usando o [registro automático em massa](windows-bulk-enroll.md), os dispositivos precisam executar o Windows 10 versão 1703 ou posterior. A extensão de gerenciamento do Intune não é compatível com o Windows 10 no modo S, já que o modo S não permite a execução de aplicativos que não fazem parte da loja. 
  
- Dispositivos que ingressaram no Azure AD (Active Directory), incluindo:
  
  - Com ingresso híbrido realizado no Azure AD: Dispositivos ingressados no Azure AD (Active Directory) e também ingressados no AD (Active Directory) local. Para obter orientação, confira [Planejar sua implementação de ingresso híbrido no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan).

- Dispositivos registrados no Intune, incluindo:

  - Dispositivos registrados em uma política de grupo (GPO). Veja [Registrar um dispositivo Windows 10 automaticamente usando a Política de Grupo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) para obter orientação.
  
  - Dispositivos manualmente registrados no Intune, que é quando:
  
    - O usuário se conecta ao dispositivo usando uma conta de usuário local e, em seguida, ingressa o dispositivo manualmente no Azure AD (e o registro automático para o Intune está habilitado no Azure AD).
    
    Ou
    
    - O usuário se conecta ao dispositivo usando sua conta do Azure AD e, em seguida, registra-se no Intune.

  - Dispositivos cogerenciados que usam o Configuration Manager e o Intune. Para obter orientação, confira [O que é cogerenciamento](https://docs.microsoft.com/sccm/comanage/overview).

## <a name="create-a-script-policy"></a>Criar uma política de script 

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
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

> [!NOTE]
> O script do PowerShell será executado sob privilégio de administrador (por padrão) quando estiver definido como o contexto de usuário e o usuário final do dispositivo tiver privilégios de administrador.

## <a name="assign-the-policy"></a>Atribuir a política

1. No painel **Scripts do PowerShell**, selecione o script a ser atribuído e, em seguida, escolha **Gerenciar** > **Atribuições**.

    ![Atribuir ou implantar o script do PowerShell em grupos de dispositivos no Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Escolha **Selecionar Grupos** para listar os grupos disponíveis do Azure AD. 
3. Selecione um ou mais grupos que contenham os usuários cujos dispositivos recebem o script. **Selecione** para atribuir a política aos grupos selecionados.

> [!NOTE]
> - Os usuários finais não precisam entrar no dispositivo para executar scripts do PowerShell.
> - Os scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo ou grupos de segurança de usuário do Azure AD.

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

#### <a name="issue-intune-management-extension-doesnt-download"></a>Problema: A extensão de gerenciamento do Intune não baixa

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

[Habilitar o registro automático do Windows 10](windows-enroll.md#enable-windows-10-automatic-enrollment) inclui as etapas para configurar o registro automático no Intune.

#### <a name="issue-powershell-scripts-do-not-run"></a>Problema: os scripts do PowerShell não são executados

**Possíveis resoluções**:

- Os scripts do PowerShell não são executados em cada entrada. Eles são executados:

  - Quando o script é atribuído a um dispositivo
  - Se você alterar o script, carregue-o e atribua-o a um usuário ou dispositivo
  
    > [!TIP]
    > A **Extensão de gerenciamento do Microsoft Intune** é um serviço que é executado no dispositivo, assim como qualquer outro serviço listado no aplicativo de Serviços (services.msc). Após a reinicialização de um dispositivo, esse serviço também pode reiniciar e verificar se há qualquer script do PowerShell atribuído com o serviço Intune. Se o serviço **Extensão de Gerenciamento do Microsoft Intune** for definido como Manual, o serviço poderá não ser reiniciado depois que o dispositivo for reinicializado.

- O cliente de extensão de gerenciamento do Intune verifica uma vez por hora se há alterações no script ou na política no Intune.
- Confirme se a extensão de gerenciamento do Intune foi baixada em `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Scripts não são executados nos Surface Hubs nem no Windows 10 no modo S.
- Examine os logs em busca de erros. Veja [solucionar problemas de scripts](#troubleshoot-scripts) (neste artigo).
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

## <a name="next-steps"></a>Próximas etapas

[Monitorar](device-profile-monitor.md) e [solucionar problemas](device-profile-troubleshoot.md) de seus perfis.
