---
title: Entender as operações usando relatórios
description: Crie e gerencie relatórios sobre software, hardware e licenças de software em sua organização.
keywords: ''
author: dougeby
ms.author: angrobe
manager: angrobe
ms.date: 04/23/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 857309c2-61c9-4c22-becf-4839fedeaece
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pbala
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 919178b20094cb210b3d0b05c42b9b7d97759637
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
---
# <a name="understand-microsoft-intune-operations-by-using-reports"></a>Entender as operações do Microsoft Intune usando relatórios

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Use as informações neste tópico para ajudá-lo a criar e gerenciar os relatórios do Microsoft Intune, que fornecem informações sobre software, hardware e licenças de software na sua organização.

## <a name="using-reports"></a>Uso de relatórios
Os relatórios do Intune fornecem informações sobre software, hardware e licenças da sua empresa. Relatórios podem ajudá-lo a confirmar as necessidades atuais e a previsão de despesas futuras. O espaço de trabalho **Relatórios** oferece as ferramentas para criar e gerenciar relatórios. 

## <a name="report-types"></a>Tipos de relatório

|Tipo de relatório|Descrição|
|---------------|---------------|
|**Relatórios de Atualizações**|Mostram as atualizações de software que foram bem-sucedidas nos computadores de sua organização. Também mostram as atualizações que falharam, estão pendentes ou são necessárias. Para mais informações sobre as atualizações de software, veja [Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).|
|**Relatórios de Software Detectados**|Mostram o software instalado nos computadores de sua organização. As versões de software são incluídas. Você pode filtrar as informações exibidas com base no Editor do software e na categoria de software. Você pode expandir as atualizações nessa lista para mostrar mais detalhes (como os computadores nos quais uma atualização está instalada) clicando na seta de direção ao lado do item de lista.<br /><br />Quando você desativa computadores ou altera suas associações de grupo no Intune, pode levar vários minutos para que essas alterações sejam refletidas no relatório de Software Detectado. Para obter os dados de inventário de software mais precisos, aguarde alguns minutos depois de desativar computadores ou alterar suas associações de grupo antes de executar um relatório de Softwares Detectado que inclua esses computadores.|
|**Relatórios de inventário de computador**|Exibe informações sobre os computadores gerenciados da sua organização. Use esse relatório para planejar aquisições de hardware e também para entender mais sobre as necessidades de hardware dos usuários da sua organização. Para obter mais informações sobre como trabalhar com computadores gerenciados, confira [Gerenciar computadores Windows com o Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md).|
|**Relatórios de Inventário de Dispositivo Móvel**|Exibe informações sobre os dispositivos móveis na sua organização. É possível filtrar as informações exibidas com base em grupos, se o dispositivo é de jailbreak ou de raiz, e pelo sistema operacional.|
|**Relatórios de Aquisição de Licenças**|Exibe os títulos de software de todos os softwares licenciados em grupos de licenças selecionados, com base em seus contratos de licenciamento. Se as informações de licenças não tiverem sido atualizadas há mais de 24 horas, elas serão atualizadas quando você gerar um relatório de licenças. Um relatório de licenças não deve ser considerado um cálculo exato de títulos de software que estão sendo usados nem uma prova de conformidade com contratos. O relatório é uma ferramenta para ajudar a tomar decisões de licenciamento na sua empresa. O Intune pode não detectar alguns produtos que podem ter uma licença por volume da Microsoft. Os filtros disponíveis são:<br /><br />**Todos os contratos** exibe todos os produtos de software licenciados que são gerenciados pelo Intune.<br /><br />**Contratos de licenciamento por volume** mostra apenas produtos de software do VLSC (Centro de Serviços de Licenciamento por Volume).<br /><br />**Outros contratos de licenciamento de software** exibe produtos de software que são gerenciados fora do VLSC.|
|**Relatórios de Instalação de Licenças**|Comparam o software instalado nos computadores de sua organização à cobertura do contrato de licença atual, de acordo com o VLSC. Filtros incluem:<br /><br />**Todos os contratos** exibe todos os produtos de software licenciados que são gerenciados pelo Intune.<br /><br />**Contratos de licenciamento por volume** exibe apenas produtos de software do VLSC.<br /><br />**Outros contratos de licenciamento de software** exibe produtos de software que são gerenciados fora do VLSC.|
|**Relatórios de Termos e Condições**|Mostre se os usuários aceitaram os termos e as condições que você implantou e qual versão foi aceita. Você pode mostrar a aceitação dos termos e condições que foram implantados para até 10 usuários ou mostrar o status de aceitação para um termo específico que foi implantado para eles.|
|**Relatórios de Aplicativos Incompatíveis**|Exibe informações sobre os usuários que têm aplicativos instalados que estão nas suas listas de aplicativos em conformidade e sem conformidade. Use esse relatório para encontrar usuários e dispositivos que não estão em conformidade com as políticas para aplicativos da sua empresa.|
|**Relatórios de Conformidade de Certificado**|Mostre quais certificados foram emitidos aos usuários e os dispositivos por meio do SCEP ou do PKCS #12 (.PFX). Use esse relatório para encontrar certificados emitidos, vencidos e revogados.|
|**Relatórios de Histórico do Dispositivo**|Mostre um registro em formato de histórico das ações de desativar, apagar e excluir. Use este relatório para ver quem iniciou ações em dispositivos no passado.|
|**Relatórios de Atestado de Integridade**|Mostre a integridade dos dispositivos móveis.|
|**Relatório de Hardware Mac OS X**|Exibe detalhes de hardware para todos os dispositivos Mac OS X nos grupos selecionados. Para obter informações sobre o inventário de hardware coletado desses dispositivos, confira [Entender seus dispositivos com o inventário do Microsoft Intune](understand-your-devices-with-inventory-in-microsoft-intune.md).|
|**Relatório de Software Mac OS X**|Exibe o software que está instalado em todos os dispositivos Mac OS X nos grupos que você selecionou. O relatório lista o nome do software (como uma ID de pacote), a versão curta (ou amigável) do nome, a versão e o número de dispositivos instalados com o software.|
|**Relatórios de Proteção de Informações do Windows**|Mostra informações sobre as operações de WIP (Proteção de Informações do Windows) em dispositivos que você gerencia.|
|**Relatórios de Atestado de Integridade**|Mostra informações relatadas pelo serviço de Atestado de integridade do Windows para dispositivos que você gerencia.|

## <a name="to-create-a-report"></a>Para criar um relatório

1.  No console de administração do Intune, escolha **Relatórios**. Em seguida, escolha o tipo de relatório que você deseja gerar, conforme descrito na tabela anterior.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório de Software Detectado.

3.  Escolha **Exibir relatório** para abrir o relatório em uma nova janela.

Para classificar o relatório por qualquer uma das colunas exibidas, escolha o título de coluna. Além disso, alguns relatórios permitem que você expanda os itens da lista para mostrar mais detalhes.

## <a name="more-report-actions"></a>Mais ações de relatório
Além disso, os relatórios dão suporte às seguintes ações:

|Ação|Mais informações|
|----------|--------------------|
|**Imprimir**|Em um relatório aberto, escolha o ícone de impressão e siga as instruções.|
|**Exportarar**|Em um relatório aberto, escolha o ícone de exportação e siga as instruções. Você pode exportar um relatório para formato HTML ou de valores separados por vírgula (. csv).|
|**Salvar**|Na página **Criar novo relatório** , cada usuário pode salvar até 100 relatórios. Configure os parâmetros de relatório em seus requisitos e escolha **Salvar**ou **Salvar como** se desejar usar um nome diferente.|
|**Carregar**|Na página **Criar novo relatório** , escolha **Carregar** para recuperar quaisquer configurações salvas anteriormente ou parâmetros de relatório.|
|**Excluir**|No espaço de trabalho **Relatórios**, selecione o tipo de relatório desejado e escolha **Carregar**. Em seguida, na lista de relatórios, escolha o ícone Excluir (x) ao lado do relatório.|


