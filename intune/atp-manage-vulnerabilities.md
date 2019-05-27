---
title: Usar o Intune para corrigir as vulnerabilidades encontradas pela ATP do Microsoft Defender – Azure | Microsoft Docs
description: Veja como gerenciar tarefas de segurança pelo Gerenciamento de ameaças e vulnerabilidade, parte da ATP (Proteção Avançada contra Ameaças) do Microsoft Defender no console do Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6f6f319b5c38f290f3cdb6d4a04528f3b227212
ms.sourcegitcommit: f8bbd9bac2016a77f36461bec260f716e2155b4a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65733386"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Usar o Intune para corrigir as vulnerabilidades identificadas pela ATP do Microsoft Defender  

Ao integrar o Intune com a ATP (Proteção Avançada contra Ameaças) do Microsoft Defender, é possível utilizar o Gerenciamento de ameaças e vulnerabilidade (TVM) da ATP e o Intune para corrigir a vulnerabilidade do ponto de extremidade identificada pelo TVM. Essa integração oferece uma abordagem baseada em riscos para a descoberta e a priorização de vulnerabilidades que podem melhorar o tempo de resposta de correção em seu ambiente.  

O [Gerenciamento de ameaças e vulnerabilidade](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) faz parte da [Proteção Avançada contra Ameaças da Microsoft](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).  

## <a name="how-integration-works"></a>Como funciona a integração  

Depois de conectar o Intune à Proteção Avançada contra Ameaças da Microsoft, a ATP recebe detalhes sobre ameaças e vulnerabilidades de dispositivos gerenciados.  

No console da Central de Segurança do Windows Defender, os administradores de segurança da ATP analisam dados sobre as vulnerabilidades do ponto de extremidade. Depois, usam um único clique para criar tarefas de segurança que sinalizam os dispositivos vulneráveis para que sejam corrigidos. As tarefas de segurança são passadas imediatamente para o console do Intune, onde os administradores do Intune podem visualizá-las. A tarefa de segurança identifica o tipo de vulnerabilidade, a prioridade, o status e as etapas para corrigir a vulnerabilidade. O administrador do Intune escolhe aceitar ou rejeitar a tarefa.  

Quando uma tarefa é aceita, o administrador do Intune toma medidas para corrigir a vulnerabilidade pelo Intune, usando as diretrizes fornecidas como parte da tarefa de segurança.  

Ações comuns de correção incluem:  
- **Bloquear** a execução de um aplicativo.  
- **Implantar** uma atualização do sistema operacional para reduzir a vulnerabilidade.  
- **Modificar** um valor de registro.  
- **Desabilitar** ou **Habilitar** uma configuração para afetar a vulnerabilidade.  
- **Requer atenção** alerta o administrador sobre a ameaça quando não há nenhuma recomendação adequada para fornecer.  

Um exemplo de fluxo de trabalho:  
- Dentro da ATP do Microsoft Defender, é descoberta uma vulnerabilidade de um aplicativo chamado Contoso Media Player v4, e um administrador cria uma tarefa de segurança para atualizar esse aplicativo. O Contoso Media Player é um aplicativo não gerenciado que foi implantado com o Intune.  

  Essa tarefa de segurança é exibida no console do Intune com um status pendente:  
  ![Exibir a lista de tarefas de segurança no console do Intune](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- O administrador do Intune seleciona a tarefa de segurança para visualizar detalhes sobre ela.  O administrador seleciona **Aceitar**, que atualiza o status do Intune e da ATP para *Aceito*.  
  ![Aceitar ou rejeitar uma tarefa de segurança](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- O administrador, em seguida, corrige a tarefa com base na orientação fornecida.  A orientação varia de acordo com o tipo de correção necessária. Quando disponível, a orientação de remediação inclui links que abrem painéis relevantes para configurações no Intune. 

  Como o reprodutor de mídia neste exemplo não é um aplicativo gerenciado, o Intune só pode fornecer instruções de texto. Se o aplicativo fosse gerenciado, o Intune poderia fornecer instruções para baixar uma versão atualizada e fornecer um link para abrir a implantação para o aplicativo, de modo que os arquivos atualizados pudessem ser adicionados à implantação. 

- Depois de concluir a correção, o administrador do Intune abre a tarefa de segurança e seleciona **Concluir Tarefa**.  O status de correção é atualizado no Intune e na ATP, e os administradores de segurança confirmam o status revisado da vulnerabilidade.  

## <a name="prerequisites"></a>Pré-requisitos  

**Assinaturas**:  
- Microsoft Intune  
- Proteção Avançada contra Ameaças do Microsoft Defender ([Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink)).  

**Configurações do Intune para a ATP**:  
- Configure uma conexão de serviço a serviço com a ATP do Microsoft Defender.  
- Implante uma política de conformidade do dispositivo com um tipo de perfil da **ATP do Microsoft Defender (Windows 10 Desktop)** para dispositivos que terão os riscos avaliados pela ATP.
  Saiba mais sobre como configurar o Intune para trabalhar com a ATP em [Impor a conformidade para a ATP do Microsoft Defender com acesso condicional no Intune](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).  

## <a name="work-with-security-tasks"></a>Trabalhar com tarefas de segurança  

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) e acesse **Segurança do Dispositivo** > **Tarefas de Segurança**.  
2. Selecione uma tarefa na lista para abrir uma janela de recursos que exibe detalhes adicionais dessa tarefa de segurança.  
3. Ao visualizar a janela de recursos da tarefa de segurança, você pode selecionar links adicionais:  
   - APLICATIVOS GERENCIADOS: veja o aplicativo que está vulnerável. Quando a vulnerabilidade se aplica a vários aplicativos, você vê uma lista filtrada de aplicativos.  
   - DISPOSITIVOS: veja uma lista dos *dispositivos vulneráveis*, onde é possível analisar mais detalhes sobre uma entrada quanto à vulnerabilidade do dispositivo.  
   - SOLICITANTE: use este link para enviar um email ao administrador que enviou a tarefa de segurança.  
   - OBSERVAÇÕES: leia mensagens personalizadas enviadas pelo solicitante ao abrir a tarefa de segurança.  
4. Selecione **Aceitar** ou **Rejeitar** para enviar a notificação à ATP para a ação planejada. Ao aceitar ou rejeitar uma tarefa, você pode enviar observações, que são enviadas à ATP.  

5. Depois de aceitar uma tarefa, abra novamente a tarefa de segurança (se estiver fechada) e siga os detalhes de CORREÇÃO para corrigir a vulnerabilidade.  As instruções fornecidas pela ATP nos detalhes da tarefa de segurança variam de acordo com a vulnerabilidade envolvida.  

   Quando for possível fazer isso, as instruções de correção incluem links que abrem os objetos de configuração relevantes no console do Intune.  

6. Depois de concluir as etapas de correção, abra a tarefa de segurança e selecione **Concluir Tarefa**.  Essa ação atualiza o status da tarefa de segurança no Intune e na ATP.  

Após a correção bem-sucedida, a classificação de exposição a riscos na ATP pode cair, com base nas novas informações dos dispositivos corrigidos. 

## <a name="next-steps"></a>Próximas etapas
Saiba mais sobre o Intune e a [ATP do Microsoft Defender](https://docs.microsoft.com/intune/advanced-threat-protection)  
Consulte a [Defesa contra Ameaças Móveis](https://docs.microsoft.com/intune/mobile-threat-defense) do Intune  
Consulte o [Painel de Gerenciamento de ameaças e vulnerabilidade](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) na ATP do Microsoft Defender
