---
title: Auditoria de alterações e eventos no Microsoft Intune – Azure | Microsoft Docs
description: Saiba como examinar os logs de auditoria que registram as atividades do Microsoft Intune.
keywords: ''
ms.author: dougeby
author: dougeby
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 93072ba4730de0252f54d93fa1169062d496ce38
ms.sourcegitcommit: 1069b3b1ed593c94af725300aafd52610c7d8f04
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58394894"
---
# <a name="use-audit-logs-to-track-and-monitor-events-in-microsoft-intune"></a>Usar logs de auditoria para acompanhar e monitorar eventos no Microsoft Intune

Os logs de auditoria incluem um registro das atividades que geram uma alteração no Microsoft Intune. Criar, atualizar (Editar), delete, atribuir e ações remotas criam eventos de auditoria que os administradores podem examinar para a maioria das cargas de trabalho do Intune. Por padrão, a auditoria está habilitada para todos os clientes. Ele não pode ser desabilitado.

> [!NOTE]
> Comecei a gravar na versão de dezembro de 2017 recurso de eventos de auditoria. Eventos anteriores não estão disponíveis.

## <a name="who-can-access-the-data"></a>Quem pode acessar os dados?

Os usuários com as seguintes permissões podem examinar os logs de auditoria:

- Administrador Global
- Administrador de Serviços do Intune
- Os administradores atribuídos a uma função do Intune com permissões de **Dados de auditoria** - **Leitura**

## <a name="audit-logs-for-intune-workloads"></a>Logs de auditoria de cargas de trabalho do Intune

Você pode examinar os logs de auditoria no grupo de monitoramento de cada carga de trabalho do Intune:

1. No [portal do Azure](https://portal.azure.com/), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Escolha a carga de trabalho que você deseja examinar os logs de auditoria. Por exemplo, selecione **dispositivos**.
3. Sob **Monitoring**, escolha **logs de auditoria**.

## <a name="route-logs-to-azure-monitor"></a>Rotear logs ao Azure Monitor

Logs de auditoria e logs operacionais também podem ser roteada para o Azure Monitor. Na **logs de auditoria**, selecione **configurações de exportação de dados**:

![Exportar dados de log para o Azure monitor, selecionando configurações de exportação de dados no Intune](./media/audit-logs-export-data-settings.png)

Para saber mais informações sobre esse recurso, confira [Enviar dados de log para o armazenamento, hubs de eventos ou análise de logs](review-logs-using-azure-monitor.md).

## <a name="review-audit-events"></a>Examinar eventos de auditoria

![Escolha os logs de auditoria no Intune para ver as ações e datas quando os eventos aconteceram](./media/monitor-audit-logs.png "logs de auditoria")

Um log de auditoria tem um modo de exibição de lista padrão que mostra os itens a seguir:

- Data e hora da ocorrência
- Iniciado por (Ator)
- Nome do aplicativo
- Atividade
- Destino(s)
- Category
- Status

Para obter informações mais específicas sobre um evento, selecione um item na lista:

![Obter informações mais específicas sobre quem fez o que na auditoria faz logon no Intune](./media/monitor-audit-log-detail.png "detalhes de log de auditoria")

> [!NOTE]
> **Iniciado por (ator)** inclui informações sobre quem executou a tarefa e, em que ele foi executado. Por exemplo, se você executar a atividade no Intune no Portal do Azure, então **Aplicativo** sempre listará a **extensão do Portal do Microsoft Intune**, e **ID do Aplicativo** sempre usará o mesmo GUID.
> 
> A seção **Destino(s)** lista vários destinos e as propriedades que foram alteradas.  

## <a name="filter-audit-events"></a>Filtrar eventos de auditoria

Cada carga de trabalho tem um item de menu que filtra previamente a categoria de eventos de auditoria associada a esse painel. Uma opção de filtro separada permite alterar categorias diferentes, e detalhes de ação do evento nessa categoria. Você pode pesquisar pelo UPN, como o usuário que realizou a ação. Um filtro de intervalo de datas permite as opções de 24 horas, sete dias ou 30 dias. Por padrão, os últimos 30 dias dos eventos de auditoria são exibidos.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Usar a API do Graph para recuperar os eventos de auditoria

Para obter detalhes sobre como usar a API do graph para obter até um ano de eventos de auditoria, consulte [List auditEvents](https://docs.microsoft.com/graph/api/intune-auditing-auditevent-list?view=graph-rest-1.0).

## <a name="next-steps"></a>Próximas etapas

[Enviar dados de log para o armazenamento, hubs de eventos ou log analytics](review-logs-using-azure-monitor.md).

[Examine os logs de proteção do aplicativo de cliente](app-protection-policy-settings-log.md).
