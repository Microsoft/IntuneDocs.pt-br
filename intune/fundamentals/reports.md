---
title: Microsoft Intune reports
titleSuffix: Microsoft Intune
description: O Intune fornece tipos específicos de relatórios com exibições focadas que contêm dados consistentes e pontuais.
keywords: ''
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: ''
ms.suite: ems
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 05258c5363b43398dee1815bb91c50878803e426
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74391936"
---
# <a name="intune-reports"></a>Relatórios do Intune
Os relatórios do Microsoft Intune permitem que você monitore de forma mais eficiente e proativa a integridade e a atividade dos pontos de extremidade em sua organização, além de fornecerem outros dados de relatório no Intune. Por exemplo, você poderá ver relatórios sobre a conformidade, a integridade e as tendências do dispositivo. Além disso, poderá criar relatórios personalizados para obter dados mais específicos. 

> [!NOTE]
> As alterações de relatórios do Intune serão distribuídas gradualmente durante um período para ajudar você a se preparar e se adaptar à nova estrutura.

Os tipos de relatório são organizados nas seguintes áreas de foco:
- **Operacional** – fornece dados direcionados e pontuais que ajudam você a se concentrar e tomar medidas. Estes relatórios podem ser mais úteis para os administradores, os especialistas no assunto e a assistência técnica.
- **Organizacional** – fornece um resumo mais amplo de uma exibição geral, como o estado do gerenciamento de dispositivo. Estes relatórios podem ser mais úteis para gerentes e administradores.
- **Histórico** – fornece padrões e tendências ao longo de um período. Estes relatórios podem ser mais úteis para gerentes e administradores.
- **Especialista** – permite que você use dados brutos para criar seus próprios relatórios personalizados. Estes relatórios podem ser mais úteis para administradores.

A estrutura de relatórios fornece uma experiência de relatório consistente e mais abrangente. Os relatórios disponíveis fornecem a seguinte funcionalidade:
- **Pesquisar e classificar** – você pode pesquisar e classificar em todas as colunas, independentemente do tamanho do conjunto de dados.
- **Paginação de dados** – você pode examinar seus dados com base na paginação, seja página por página ou pulando para uma página específica.
- **Desempenho** – você pode gerar e exibir rapidamente relatórios criados a partir de grandes locatários.
- **Exportar** – você pode exportar rapidamente os dados de relatório gerados de grandes locatários.

### <a name="who-can-access-the-data"></a>Quem pode acessar os dados?

Os usuários com as seguintes permissões podem examinar os logs:

- Administrador Global
- Administrador de Serviços do Intune
- Administradores atribuídos a uma função do Intune com permissões de **Leitura**

## <a name="non-compliant-devices-report-operational"></a>Relatório de dispositivos fora de conformidade (operacional)
O relatório de dispositivos fora de conformidade exibem dados normalmente usados por funções de assistência técnica ou de administrador para identificar problemas e ajudar a corrigi-los. Os dados encontrados nesses relatórios são pontuais, destacam comportamentos inesperados e devem ser práticos. O relatório está disponível junto com a carga de trabalho, tornando o relatório de dispositivos fora de conformidade acessível sem sair dos fluxos de trabalho ativos. Esse relatório fornece recursos de filtragem, pesquisa, paginação e classificação. Além disso, você pode fazer uma busca detalhada para ajudar a solucionar problemas.

Para exibir o relatório de **Dispositivos fora de conformidade**, siga estas etapas:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Conformidade do dispositivo** > **Dispositivos fora de conformidade**.

    ![Relatório de dispositivo fora de conformidade](./media/intune-reports/intune-reports-02.png)

## <a name="device-compliance-report-organizational"></a>Relatório de conformidade do dispositivo (organizacional)
Os relatórios de conformidade do dispositivo devem ser amplos por natureza e fornecer uma exibição de relatório de dados mais tradicional para identificar métricas agregadas. Esse relatório foi projetado para trabalhar com grandes conjuntos de dados a fim de obter uma imagem completa da conformidade do dispositivo. Por exemplo, o relatório de conformidade do dispositivo mostra todos os estados de conformidade fornecendo uma visão mais ampla dos dados, independentemente do tamanho do conjunto de dados. Esse relatório mostra o detalhamento completo de registros, além de uma visualização prática de métricas agregadas. É possível gerá-lo aplicando filtros e selecionando o botão "Gerar relatório". Dessa forma, os dados serão atualizados para mostrar o estado mais recente com a capacidade de exibir os registros individuais que compõem os dados agregados. Como a maioria dos relatórios na nova estrutura, estes registros podem ser classificados e pesquisados para focar nas informações de que você precisa. 

Para ver um relatório gerado de estado do dispositivo, você pode usar as seguintes etapas:
1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Relatórios** para exibir o resumo dos relatórios.
3. Selecione **Conformidade do dispositivo**.
4. Selecione os filtros **Status de conformidade**, **Sistema operacional** e **Propriedade** para refinar o relatório.
5. Clique em **Gerar relatório** (ou **Gerar novamente**) para recuperar os dados atuais.

    ![Relatório de conformidade do dispositivo](./media/intune-reports/intune-reports-02a.png)

    > [!NOTE]
    > O relatório de **Conformidade do dispositivo** fornece um carimbo de data/hora de quando o relatório foi gerado pela última vez. 

Para informações relacionadas, confira [Impor a conformidade do Microsoft Defender ATP com Acesso Condicional no Intune](~/protect/advanced-threat-protection.md).

## <a name="reports-summary"></a>Resumo de relatórios 

O relatório de conformidade do dispositivo está disponível como o relatório de resumo na carga de trabalho de **Relatórios**. Use as seguintes etapas para exibir o relatório de conformidade do dispositivo:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Relatórios** para exibir o resumo dos relatórios.

    ![Resumo de relatórios do Intune](./media/intune-reports/intune-reports-01.png)

## <a name="device-compliance-trend-report-historical"></a>Relatório de tendências de conformidade do dispositivo (histórico)
Os relatórios de tendência de conformidade do dispositivo têm maior probabilidade de serem usados por administradores e arquitetos para identificar tendências de longo prazo na conformidade do dispositivo. Os dados agregados são exibidos durante um período e são úteis para decisões de investimento futuras, melhorias do processo ou investigação de anomalias. Os filtros também podem ser aplicados para conferir tendências específicas. Os dados fornecidos por esse relatório são um instantâneo do estado atual do locatário (quase em tempo real). 

Um relatório de tendência de conformidade do dispositivo para as tendências de conformidade do dispositivo pode mostrar a tendência de estados de conformidade do dispositivo durante um período. Você pode identificar onde os picos de conformidade ocorreram e concentrar seu tempo e esforço de acordo com essa informação.

Para exibir o relatório de **Tendências**, siga estas etapas:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Relatórios** > **Tendências** para exibir a conformidade do dispositivo durante uma tendência de 60 dias.

    ![Relatório de tendências do Intune](./media/intune-reports/intune-reports-03.png)

## <a name="azure-monitor-integration-reports-specialist"></a>Relatórios de integração do Azure Monitor (especialista)
Você pode personalizar seus relatórios para obter os dados que deseja. Os dados em seus relatórios poderão ficar disponíveis por meio do [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) usando [Log Analytics](reports.md#log-analytics) e [Pastas de trabalho do Azure Monitor](reports.md#workbooks). Essas soluções permitem criar consultas personalizadas, configurar alertas e desenvolver painéis para mostrar os dados de conformidade do dispositivo da maneira que você preferir. Além disso, você pode manter os logs de atividades na sua conta de armazenamento do Azure, integrá-los aos relatórios usando [ferramentas de SIEM (gerenciamento de eventos e informações de segurança)](https://docs.microsoft.com/microsoft-365/security/office-365-security/siem-server-integration) e correlacionar os relatórios com os logs de atividades do Azure AD. As pastas de trabalho do Azure Monitor podem ser usadas em conjunto com a importação de painéis para personalizar os relatórios.

> [!NOTE]
> Funcionalidades de relatório complexas requerem uma assinatura do Azure.

Um exemplo de relatório de especialista correlacionaria dados de propriedade do dispositivo com dados de registro da plataforma em um relatório personalizado. Em seguida, esse relatório personalizado poderia ser exibido em um painel existente no portal do Azure Active Directory.

Para criar e visualizar relatórios personalizados, siga estas etapas:

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Relatórios** > **Configurações de diagnóstico**, adicione uma [configuração de diagnóstico](reports.md#diagnostic-settings).

    ![Resumo de relatórios do Intune](./media/intune-reports/intune-reports-04.png)

3. Clique em **Adicionar configuração de diagnóstico** para exibir o painel de **Configurações de diagnóstico**. 
4. Adicione um **Nome** para as configurações de diagnóstico. 
5. Selecione as configurações **Enviar para o Log Analytics** e **DeviceComplianceOrg**.

    ![Resumo de relatórios do Intune](./media/intune-reports/intune-reports-04a.png)

6. Clique em **Salvar**.
7. Em seguida, selecione **Log analytics** para criar e executar uma nova consulta de log usando o [Log Analytics](reports.md#log-analytics).

   ![Log Analytics – Consulta de log](./media/intune-reports/intune-reports-05.png)

8. Selecione **Pastas de trabalho** para criar ou abrir um relatório interativo usando as [Pastas de trabalho do Azure Monitor](reports.md#workbooks).

   ![Pastas de trabalho – Relatórios interativos](./media/intune-reports/intune-reports-07.png)

### <a name="diagnostic-settings"></a>Configurações de diagnóstico
Cada recurso do Azure requer sua própria configuração de diagnóstico. A configuração de diagnóstico define o seguinte para um recurso:

- As categorias de logs e os dados de métrica enviados aos destinos definidos na configuração. As categorias disponíveis variam para diferentes tipos de recursos.
- Um ou mais destinos para enviar os logs. Os destinos atuais incluem workspace do Log Analytics, Hubs de Eventos e Armazenamento do Azure.
- Política de retenção para dados armazenados no Armazenamento do Azure.

Uma única configuração de diagnóstico pode definir um de cada um dos destinos. Se você quiser enviar dados para mais de um tipo de destino específico (por exemplo, dois workspaces do Log Analytics diferentes), crie várias configurações. Cada recurso pode ter até cinco configurações de diagnóstico.

Para obter mais informações sobre configurações de diagnóstico, confira [Criar configuração de diagnóstico para coletar logs e métricas de plataforma no Azure](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings).

### <a name="log-analytics"></a>Análise de log
O Log Analytics é a principal ferramenta no portal do Azure para escrever consultas de log e analisar interativamente os resultados das consultas. Mesmo que uma consulta de log seja usada em outro lugar no Azure Monitor, você normalmente escreverá e testará a consulta primeiro usando o Log Analytics. Para obter detalhes sobre como usar o Log Analytics e criar consultas de log, confira [Visão geral das consultas de log no Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview). 

### <a name="workbooks"></a>Pastas de trabalho
As pastas de trabalho combinam texto, consultas do Analytics, Métricas do Azure e os parâmetros em relatórios interativos avançados. As pastas de trabalho podem ser editadas por qualquer membro da equipe que tenha acesso aos mesmos recursos do Azure. Para obter mais informações sobre as pastas de trabalho, confira [Pastas de trabalho do Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/app/usage-workbooks). Você também pode trabalhar e contribuir com modelos de pastas de trabalho. Para saber mais, confira [Modelos das pastas de trabalho do Azure Monitor](https://go.microsoft.com/fwlink/?linkid=867045).

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre as seguintes tecnologias:
- [Blog – Estrutura de relatório do Microsoft Intune](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/New-Reporting-Framework-Coming-to-Intune/ba-p/1009553)
- [Azure Monitor](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-activity-logs-azure-monitor)
- [O que é o Log Analytics?](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview#what-is-log-analytics)
- [Consultas de log](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview)
- [Introdução ao Log Analytics no Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/get-started-portal)
- [Pastas de trabalho do Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/app/usage-workbooks)
- [Ferramentas de SIEM (gerenciamento de informações e eventos de segurança)](https://docs.microsoft.com/microsoft-365/security/office-365-security/siem-server-integration)
