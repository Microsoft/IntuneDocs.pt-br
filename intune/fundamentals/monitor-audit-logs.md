---
title: Auditar alterações e eventos no Microsoft Intune – Azure | Microsoft Docs
description: Saiba como examinar os logs de auditoria que registram as atividades do Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: d6af0718f2b926383bb943b6321b4d5839346ce7
ms.sourcegitcommit: df8e2c052fafb2d5d4e9b4fcd831ae0ecf7f8d16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991982"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Usar logs de auditoria para acompanhar e monitorar eventos no Microsoft Intune

Os logs de auditoria incluem um registro das atividades que geram uma alteração no Microsoft Intune. Ações de criar, atualizar (editar), excluir, atribuir e ações remotas criam eventos de auditoria que os administradores podem examinar para a maioria das cargas de trabalho do Intune. Por padrão, a auditoria está habilitada para todos os clientes. Não pode ser desabilitado.

> [!NOTE]
> Eventos de auditoria começaram a ser gravados na versão de recursos de dezembro de 2017. Eventos anteriores não estão disponíveis.

## <a name="who-can-access-the-data"></a>Quem pode acessar os dados?

Os usuários com as seguintes permissões podem examinar os logs de auditoria:

- Administrador Global
- Administrador de Serviços do Intune
- Os administradores atribuídos a uma função do Intune com permissões de **Dados de auditoria** - **Leitura**

## <a name="audit-logs-for-intune-workloads"></a>Logs de auditoria de cargas de trabalho do Intune

Você pode examinar os logs de auditoria no grupo de monitoramento de cada carga de trabalho do Intune:

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Administração de locatário** > **logs de auditoria**.
3. Para filtrar os resultados, selecione **Filtrar** e refine os resultados usando as opções a seguir.
    - **Categoria**: como **conformidade**, **dispositivo**e **função**.
    - **Atividade**: as opções listadas aqui são restritas pela opção escolhida em **categoria**.
    - **Intervalo de datas**: você pode escolher os logs para o mês, a semana ou o dia anterior.
4. Escolha **Aplicar**.
4. Selecione um item na lista para ver os detalhes da atividade.

## <a name="route-logs-to-azure-monitor"></a>Rotear logs ao Azure Monitor

Logs de auditoria e logs operacionais também podem ser roteados para o Azure Monitor. Em **Logs de auditoria**, selecione **Exportar Configurações de Dados**:

![Exporte dados de log para o monitor do Azure selecionando Exportar configurações de exportação de dados no Intune](./media/monitor-audit-logs/audit-logs-export-data-settings.png)

> [!NOTE]
> Para obter mais informações sobre esse recurso e revisar os pré-requisitos para usá-lo, consulte [enviar dados de log para armazenamento, hubs de eventos ou log Analytics](review-logs-using-azure-monitor.md).

> [!NOTE]
> **Iniciado por (ator)** inclui informações sobre quem executou a tarefa e em que local ela foi executada. Por exemplo, se você executar a atividade no Intune no Portal do Azure, então **Aplicativo** sempre listará a **extensão do Portal do Microsoft Intune**, e **ID do Aplicativo** sempre usará o mesmo GUID.
>
> A seção **Destino(s)** lista vários destinos e as propriedades que foram alteradas.  

## <a name="use-graph-api-to-retrieve-audit-events"></a>Usar a API do Graph para recuperar os eventos de auditoria

Para obter detalhes sobre como usar a API do Graph para obter até um ano de eventos de auditoria, veja [Listar auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Próximas etapas

[Enviar dados de log para o armazenamento, hubs de eventos ou análise de logs](review-logs-using-azure-monitor.md).

[Examine os logs de proteção do aplicativo de cliente](../apps/app-protection-policy-settings-log.md).
