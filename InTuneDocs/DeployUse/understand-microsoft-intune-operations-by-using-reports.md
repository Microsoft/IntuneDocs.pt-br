---
title: "Entender as operações usando relatórios | Microsoft Intune"
description: "Crie e gerencie relatórios sobre software, hardware e licenças de software em sua organização."
keywords: 
author: Nbigman
manager: Arob98
ms.date: 06/21/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ms.reviewer: pbala
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 72288296d966b9b9fae4fd721b4460528213f626
ms.openlocfilehash: 10908e3bb8e235659db572667bd10820adf0be52


---

# Entender as operações do Microsoft Intune usando relatórios
Use as informações neste tópico para ajudá-lo a criar e gerenciar os relatórios do Microsoft Intune, que fornecem informações sobre software, hardware e licenças de software na sua organização.

## Usando relatórios
Os relatórios do Intune fornecem informações sobre software, hardware e licenças da sua empresa. Relatórios podem ajudá-lo a confirmar as necessidades atuais e a previsão de despesas futuras. O espaço de trabalho **Relatórios** oferece as ferramentas para criar e gerenciar relatórios. Para obter mais informações sobre os relatórios, confira [Entenda as operações do Microsoft Intune usando relatórios](understand-microsoft-intune-operations-by-using-reports.md).

### Tipos de relatório

|Tipo de relatório|Descrição|
|---------------|---------------|
|**Relatórios de atualizações**|Exibe as atualizações de software que foram bem-sucedidas nos computadores da sua organização, além das atualizações que falharam, estão pendentes ou são necessárias. Para mais informações sobre as atualizações de software, confira [Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Relatórios de Software Detectados**|Exibe o software instalado nos computadores da sua organização e inclui as versões de software. Você pode filtrar as informações exibidas com base no Editor do software e na categoria de software. Você pode expandir as atualizações nessa lista para mostrar mais detalhes (como os computadores nos quais está instalado) clicando na seta de direção ao lado do item de lista.<br /><br />Quando você desativa computadores ou altera suas associações de grupo no Intune, pode levar vários minutos para que essas alterações sejam refletidas no relatório de softwares detectados. Para obter os dados de inventário de software mais precisos, aguarde alguns minutos depois de desativar computadores ou alterar suas associações de grupo antes de executar um relatório de Softwares Detectado que inclua esses computadores.|
|**Relatórios de inventário do computador**|Exibe informações sobre os computadores gerenciados da sua organização. Use esse relatório para planejar aquisições de hardware e também para entender mais sobre as necessidades de hardware dos usuários da sua organização. Para obter mais informações sobre como trabalhar com computadores gerenciados, confira [Gerenciar computadores Windows com o Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Relatórios de inventário de dispositivos móveis**|Exibe informações sobre os dispositivos móveis na sua organização. É possível filtrar as informações exibidas com base em grupos, se o dispositivo é de jailbreak ou de raiz, e pelo sistema operacional.|
|**Relatórios de Aquisição de Licenças**|Exibe os títulos de software de todos os softwares licenciados em grupos de licenças selecionados, com base em seus contratos de licenciamento. Se as informações de licenças não tiverem sido atualizadas há mais de 24 horas, elas serão atualizadas quando você gerar um relatório de licenças. Um relatório de licenças não deve ser considerado um cálculo exato de títulos de software que estão sendo usados nem uma prova de conformidade com contratos. O relatório é uma ferramenta para ajudar a tomar decisões de licenciamento na sua empresa. O Intune pode não detectar alguns produtos que podem ter uma licença por volume da Microsoft. Os filtros disponíveis são:<br /><br />**Todos os contratos** exibe todos os produtos de software licenciados que são gerenciados pelo Intune.<br /><br />**Contratos de licenciamento por volume** exibe apenas produtos de software do VLSC.<br /><br />**Outros contratos de licenciamento de software** exibe produtos de software que são gerenciados fora do VLSC.|
|**Relatórios de Instalação de Licenças**|Compara os softwares instalados em computadores da sua organização com a cobertura do seu contrato de licença atual, de acordo com o Centro de Serviços de Licenciamento por Volume (VLSC). Filtros incluem:<br /><br />**Todos os contratos** exibe todos os produtos de software licenciados que são gerenciados pelo Intune.<br /><br />**Contratos de licenciamento por volume** exibe apenas produtos de software do VLSC.<br /><br />**Outros contratos de licenciamento de software** exibe produtos de software que são gerenciados fora do VLSC.|
|**Relatórios de termos e condições**|Mostre se os usuários aceitaram os termos e condições que você implantou e qual versão foi aceita. Você pode especificar que até 10 usuários cuja aceitação de quaisquer termos e condições implantados para eles sejam mostrados, ou mostrar o status de aceitação para um termo específico implantado a eles.|
|**Relatórios de aplicativos fora de conformidade**|Exibe informações sobre os usuários que têm aplicativos instalados que estão nas suas listas de aplicativos compatíveis e não compatíveis. Use esse relatório para encontrar usuários e dispositivos que não estão em conformidade com as políticas para aplicativos da sua empresa.|
|**Relatórios de conformidade de certificados**|Mostre quais certificados foram emitidos aos usuários e os dispositivos por meio do SCEP ou do PKCS #12 (.PFX). Use esse relatório para encontrar certificados emitidos, vencidos e revogados.|
|**Relatórios de Histórico de Dispositivo**|Mostre um registro em formato de histórico das ações de desativar, apagar e excluir. Use este relatório para ver quem iniciou ações em dispositivos no passado.|
|**Relatórios de atestado de integridade**|Mostre a integridade dos dispositivos móveis.|
|**Relatório de hardware do Mac OS X**|Exibe detalhes de hardware para todos os dispositivos Mac OS X nos grupos selecionados. Para obter informações sobre o inventário de hardware coletado desses dispositivos, confira [Entender seus dispositivos com o inventário do Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Relatório de software do Mac OS X**|Exibe o software instalado em todos os dispositivos Mac OS X nos grupos selecionados. O relatório lista o nome do software (como uma ID de pacote), a versão curta (ou amigável) do nome, a versão e o número de dispositivos instalados com o software.|

#### Para criar um relatório

1.  No console de administração do Intune, clique em **Relatórios** e, em seguida, clique no tipo de relatório que deseja gerar, descrito na tabela acima.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório de software detectado.

3.  Clique em **Exibir relatório** para abrir o relatório em uma nova janela.

Para classificar o relatório por qualquer uma das colunas exibidas, clique no título de coluna. Além disso, alguns relatórios permitem que você expanda os itens da lista para mostrar mais detalhes.

## Mais ações de relatório
Além disso, os relatórios dão suporte às seguintes ações:

|Ação|Mais informações|
|----------|--------------------|
|**Imprimir**|Em um relatório aberto, clique no ícone de impressão e siga as instruções.|
|**Exportar**|Em um relatório aberto, clique no ícone de exportação e siga as instruções. Você pode exportar um relatório para formato HTML ou de valores separados por vírgula (. csv).|
|**Salvar**|Na página **Criar novo relatório** , cada usuário pode salvar até 100 relatórios. Configure os parâmetros de relatório em seus requisitos e clique em **Salvar**ou **Salvar como** se desejar usar um nome diferente.|
|**Carregamento**|Na página **Criar novo relatório** , clique em **Carregar** para recuperar quaisquer configurações salvas anteriormente ou parâmetros de relatório.|
|**Excluir**|No espaço de trabalho **Relatórios** , selecione o tipo de relatório desejado, clique em **Carregar**e, em seguida, na lista de relatórios, clique no ícone excluir (x) próximo ao relatório.|

### Consulte também
[Monitoramento e relatórios com o Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)




<!--HONumber=Jul16_HO3-->


