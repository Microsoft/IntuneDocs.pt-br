---
title: Adicionar scripts do PowerShell no Microsoft Intune para dispositivos Windows 10 – Azure | Microsoft Docs
description: Adicionar scripts do PowerShell, atribuir a política de script para grupos do Azure Active Directory, usar relatórios para monitorar os scripts e ver as etapas para excluir os scripts que você adicionar em dispositivos Windows 10 no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2c4fb7000d808d860494d2af572c821b42fa6d5c
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579176"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Gerenciar scripts do PowerShell no Intune para dispositivos Windows 10
A extensão de gerenciamento do Intune permite que você carregue scripts do PowerShell no Intune para serem executados em dispositivos Windows 10. A extensão de gerenciamento complementa os recursos de gerenciamento de dispositivo móvel (MDM) do Windows 10 e facilita a mudança para o gerenciamento moderno.

## <a name="moving-to-modern-management"></a>Mover para o gerenciamento moderno
O computador do usuário final está passando por uma transformação digital. A TI clássica tradicional concentra-se em uma plataforma de dispositivo único, em dispositivos de negócios, em usuários que trabalham no escritório e em uma variedade de processos de TI manuais e reativos. No entanto, o local de trabalho moderno habilita diversas plataformas de dispositivos que são de propriedade do usuário e dos negócios, permite que usuários trabalhem de qualquer lugar e fornece processos de TI automatizados e proativos. 

Serviços de MDM, como o Microsoft Intune, podem gerenciar dispositivos Windows 10 usando o protocolo MDM. O cliente de gerenciamento interno do Windows 10 pode se comunicar com o Intune para executar tarefas de gerenciamento da empresa. Ele o ajuda a migrar para o gerenciamento moderno em dispositivos Windows 10. No entanto, há determinados recursos que talvez sejam necessários, como configuração avançada de dispositivo, que não estão disponíveis nos recursos de MDM internos do Windows 10.

A extensão de gerenciamento do Intune complementa os recursos de MDM internos do Windows 10. Você pode criar scripts do PowerShell para executar nos dispositivos Windows 10 que fornecem os recursos necessários. Você pode criar um script do PowerShell que configura suas definições personalizadas, carregar o script no Intune, atribuir o script a um grupo do Azure AD (Active Directory) e executar o script em dispositivos Windows 10. O script pode ser monitorado para ver o status de execução dele em dispositivos Windows 10 do início ao fim.

## <a name="prerequisites"></a>Pré-requisitos
A extensão de gerenciamento do Intune tem os seguintes pré-requisitos:
- Os dispositivos devem ser associados ao Azure AD. A extensão de gerenciamento do Intune dá suporte a dispositivos Windows ingressados no Azure Active Directory, ingressados no Domínio Híbrido e registrados como Cogerenciados.
- Os dispositivos devem executar o Windows 10, versão 1607 ou posteriores.
- O registro automático do MDM deve ser [habilitado no Azure AD](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment), e os dispositivos devem ser registrados automaticamente no Intune.

## <a name="create-a-powershell-script-policy"></a>Criar uma política de script do PowerShell 
1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Scripts do PowerShell** > **Adicionar**.
4. Insira um **Nome** e **Descrição** para o script do PowerShell. Para **Local do script**, procure pelo script do PowerShell. O script deve ser menor que 200 KB (ASCII) ou 100 KB (Unicode).
5. Escolha **Configurar**. Em seguida, escolha executar o script com as credenciais do usuário no dispositivo (**Sim**) ou no contexto do sistema (**Não**). Por padrão, o script é executado no contexto do sistema. Selecione **Sim**, a menos que seja necessário executar o script no contexto do sistema. 
  ![Adicionar painel de script do PowerShell](./media/mgmt-extension-add-script.png)
6. Escolha se o script deve ser assinado por um distribuidor confiável (**Sim**). Por padrão, não há nenhum requisito para o script ser assinado. 
7. Selecione **OK** e, em seguida, **Criar** para salvar o script.

## <a name="assign-a-powershell-script-policy"></a>Atribuir uma política de script do PowerShell
1. No painel **Scripts do PowerShell**, selecione o script a ser atribuído e, em seguida, escolha **Gerenciar** > **Atribuições**.
  ![Adicionar painel de script do PowerShell](./media/mgmt-extension-assignments.png)
 
2. Escolha **Selecionar Grupos** para listar os grupos disponíveis do Azure AD. 
3. Selecione um ou mais grupos que contenham os usuários cujos dispositivos recebem o script. **Selecione** para atribuir a política aos grupos selecionados.

> [!NOTE]
> - Os usuários finais não precisam fazer logon no dispositivo para executar scripts do PowerShell. 
> - Scripts do PowerShell no Intune podem ser direcionados para grupos de segurança de dispositivo do AAD.

A extensão de gerenciamento do Intune é sincronizada com o Intune uma vez a cada hora. Depois de atribuir a política aos grupos do Azure AD, o script do PowerShell é executado e os resultados da execução são relatados. 
 
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
