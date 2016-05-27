---
# required metadata

title: Gerenciar alertas | Microsoft Intune
description:
keywords:
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 74dc4ce4-21da-4f40-a07f-3eea34561eee

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Gerenciar alertas no Microsoft Intune
Use o espaço de trabalho **Alertas** no console de administração do Intune para avaliar a integridade geral dos dispositivos na sua empresa e identificar problemas.

#### Para exibir alertas ativos

1.  No console do administrador do Intune, siga um destes procedimentos:

    -   **Para exibir informações gerais sobre alertas**, incluindo os três principais alertas e o número total de alertas ativos, clique em **Visão Geral do Sistema**. Você pode clicar nos links desses alertas para fazer uma busca por informações mais detalhadas.

    -   **Para exibir dados de resumo para alertas**, clique em **Alertas &gt; Visão Geral**. Na página **Visão geral de alertas**, a área **Resumo de tipo de alertas** exibe um resumo de alertas. Alertas críticos são exibidos primeiro. Você pode clicar nos links desses alertas para fazer uma busca por informações mais detalhadas.

        > [!NOTE]
        > Em alguns casos, um tipo de alerta pode aparecer mais de uma vez na lista **Resumo de Tipos de Alertas**.
        > 
        > Por exemplo, as seguintes instâncias do tipo de alerta Espaço Livre no Disco Lógico podem aparecer na lista:
        > 
        > -   Espaço Livre no Disco Lógico 3
        > -   2 Espaço Livre em Disco Lógico
        > 
        > Esse comportamento ocorre quando o mesmo tipo de alerta é gerado para dispositivos que executam diferentes sistemas operacionais. No exemplo, a primeira instância do tipo de alerta Espaço Livre em Disco Lógico, Espaço Livre em Disco Lógico 3, pode ter sido gerada por computadores que executam o Windows® 7. A segunda instância do tipo de alerta Espaço Livre em Disco Lógico pode ter sido gerada por computadores que executam o Windows Vista®.

    -   **Para exibir todos os alertas ativos**, clique em **Alertas &gt; Todos os Alertas**. A página **Alertas** exibe uma lista de todos os alertas ativos com as seguintes colunas:

        1.  **Nome** – O nome do tipo de alerta que gerou o alerta.

        2.  **Origem** – Um link para a origem do alerta. Se o limite de exibição do tipo de alerta estiver definido como **Exibir Todos**, o link exibirá um único dispositivo afetado. Se o limite de exibição do tipo de alerta estiver definido como um valor, esse link exibirá uma lista de cada dispositivo afetado pelo alerta.

        3.  **Última modificação** – indica o horário em que o alerta foi modificado pela última vez. Se um alerta estiver fechado, o horário do fechamento será exibido.

        4.  **Severidade** – indica a gravidade do alerta

## Exibindo alertas do quadro de avisos
Os alertas do quadro de avisos fornecem importantes comunicados de serviço como uma atualização de serviço, manutenção ou paralisação futura. Use este procedimento para exibir e gerenciar alertas do quadro de avisos.

#### Exibir e gerenciar alertas do quadro de avisos

1.  No console de administração do Intune, clique em **Visão Geral do Sistema**.

2.  Se houver comunicados importantes de serviço, eles serão exibidos na área **Quadro de Avisos**.

3.  Se desejar exportar um alerta do quadro de avisos para um arquivo de valores separados por vírgula (.csv) ou HTML, no console de administração do Intune, clique em **Alertas &gt; Todos os Alertas &gt;; Avisos**. Selecione um aviso, clique no ícone exportar lista e siga as instruções.

## Revisando os status do Intune
No espaço de trabalho **Visão Geral do Sistema**, exiba os resumos de Status de Sistema para Endpoint Protection, Atualizações, Integridade do Agente, Política e Software para ajudá-lo a identificar e priorizar problemas que exigem atenção imediata. Também é fornecido um link para o resumo **Status do Serviço** nas mensagens de erro quando o sistema é interrompido. O resumo **Status do Serviço** mostra detalhes sobre o problema em cada local e sempre indica o horário da última atualização.

#### Para exibir o status da sua assinatura

1.  No console de administração do Intune, clique em **Visão Geral do Sistema**.

2.  Na **Área de Status do Sistema**, você pode examinar o status de vários componentes do Microsoft Intune. Muitos dos itens contém links que permitem fazer uma busca detalhada para obter mais informações. Por exemplo, em **Endpoint Protection**, ao selecionar o número de instâncias, será exibido o espaço de trabalho **Endpoint Protection** com uma lista de malwares detectados. A seleção do número de dispositivos exibirá o espaço de trabalho **Grupos** com uma lista de dispositivos encontrados com malware.

## Fechando e reativando alertas
Os alertas do Intune ficam ativos até que ocorra um dos seguintes eventos:

-   O problema que gerou o alerta é resolvido.

-   O alerta é fechado manualmente.

-   Cinco dias depois que o alerta foi gerado. Após 45 dias, o alerta expira e é fechado automaticamente.

Alertas marcados como fechados são excluídos permanentemente após 90 dias.

#### Para fechar um alerta manualmente

1.  No console do administrador do Intune, siga um destes procedimentos:

    1.  **Para fechar um alerta da Lista de alertas** – Clique em **Alertas &gt; Todos os Alertas**. Selecione um alerta e clique em **Fechar alerta**.

    2.  **Para fechar um alerta de um dispositivo específico** – Clique em **Grupos &gt; Todos os Dispositivos**. Selecione um dispositivo e clique em **Exibir Propriedades**. Em seguida, na guia **Alertas**, selecione um alerta e clique em **Fechar Alerta**.

    3.  **Para fechar um alerta do quadro de avisos** – Clique em **Visão Geral do Sistema**. Clique no **X** ao lado do alerta no quadro de avisos.

#### Para exibir e reativar alertas fechados

1.  No console de administração do Intune, clique em **Alertas &gt; Todos os Alertas**.

2.  Na lista **Filtros**, clique em **Fechado**.

    Os nomes e as informações adicionais sobre os alertas aparecem no painel da lista de gerenciamento. Os detalhes sobre o alerta selecionado aparecem no painel de visualização.

3.  Para reativar o alerta selecionado, clique em **Reativar Alerta**.

### Consulte também
[Ser notificado pelos alertas do Microsoft Intune](get-notified-by-microsoft-intune-alerts.md)



<!--HONumber=May16_HO1-->


