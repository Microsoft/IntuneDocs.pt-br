---
title: "Linha do tempo da entidade Usuário do Data Warehouse | Microsoft Docs"
description: "O Intune Data Warehouse representa Usuários em uma linha do tempo."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363D148E-688F-4830-B6DE-AB4FE3648817
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ce43234003da859b81dd499f22f7280db5bda41b
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="user-lifetime-representation-in-the-intune-data-warehouse"></a>Representação do tempo de vida do usuário no Intune Data Warehouse

Você pode usar o mês de instantâneos de dados armazenados no Intune Data Warehouse para responder perguntas sobre tendências com base em tempo. Por exemplo, você pode examinar o número de usuários adicionados durante um mês. Você também pode perguntar sobre o número de usuários que foram removidos do sistema.

Para fornecer essa informação, o data warehouse armazena informações de histórico. Isso significa que ele pode rastrear o tempo de vida de uma entidade. O warehouse registra quando uma entidade foi criada, quando o estado da entidade é alterado e quando uma entidade é excluída. Com o histórico capturado com instantâneos diários de medidas quantitativas, você pode comparar um dia com o dia anterior etc.

Trabalhar com tempos de vida de entidade pode ser confuso, pois suas entidades mudam de estado. Isso significa que se você olhar para um instantâneo no dia 30, talvez não exista um registro de usuário em um estado ativo nos dados. No dia 29-28 o registro da entidade pode existir como ativo. E, então, antes do dia 28, o usuário nem existia.

Isso pode ficar mais claro se percorrermos o tempo de vida de uma entidade.

Vamos supor que um usuário, **Diogo Martins**, recebe uma licença em 01/06/2017, a tabela **Usuário** teria a seguinte entrada: 
 
| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Diogo Martins | FALSE | 01/06/2017 | 31/12/9999 | TRUE
 
Diogo Martins desiste de sua licença em 25/07/2017. A tabela **Usuário** tem as seguintes entradas. As alterações nos registros existentes são `marked`. 

| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Diogo Martins | FALSE | 01/06/2017 | `07/26/2017` | `FALSE` 
| Diogo Martins | TRUE | 26/07/2017 | 31/12/9999 | TRUE 

A primeira linha indica que Diogo Martins existiam no Intune de 01/06/2017 até 25/07/2017. O segundo registro indica que o usuário foi excluído em 25/07/2017 e não está mais presente no Intune.

Agora, vamos supor que Diogo Martins receba uma nova licença em 31/08/2017, a tabela Usuário teria as seguintes entradas:
 
| DisplayName | IsDeleted | StartDateInclusiveUTC | EndDateExclusiveUTC | IsCurrent 
| -- | -- | -- | -- | -- |
| Diogo Martins | FALSE | 01/06/2017 | 26/07/2017 | FALSE 
| Diogo Martins | TRUE | 26/07/2017 | `08/31/2017` | `FALSE` 
| Diogo Martins | FALSE | 31/08/2017 | 31/12/9999 | TRUE 
 
Uma pessoa que quiser ver o estado atual de todos os usuários aplicaria um filtro em que `IsCurrent = TRUE`. 
 
Uma pessoa que quiser ver somente os usuários existentes aplicaria um filtro em que `IsCurrent = TRUE AND IsDeleted = FALSE`.

## <a name="dimension-tables-in-the-entity-lifetime"></a>Tabelas de dimensões no tempo de vida da entidade

Para armazenar o histórico de alterações de estado em entidades, o Intune não exclui registros. Em vez disso, ele marca o registro como excluído. Isso é chamado de exclusão reversível. As tabelas de dimensões usam várias colunas de metadados para rastrear o tempo de vida dos registros. 

As colunas de metadados usadas normalmente são: 

| Nome da Propriedade de Metadados  | Interpretação dos Valores |
|--|--|
| IsDeleted | Indica se a entidade foi excluída no Intune. |
| StartDateInclusiveUTC  | A data UTC quando a entidade foi carregada no Intune Data Warehouse. A entidade pode ter sido criada antes de ser importada para o Intune Data Warehouse. |
| DeletedDateUTC  | A data UTC de exclusão da entidade do Intune. |  

Qualquer coluna de metadados que comece com o prefixo **Linha**, como **RowLastModifiedDateTimeUTC**, indica quando um registro foi criado ou modificado no Intune Data Warehouse. O warehouse segue o downstream, partindo dos dados no Intune. Esse valor não tem relação com o tempo de vida da entidade no Intune.  
 
Qualquer pessoa que queira ver apenas as entidades de dimensão que existem atualmente aplicaria um filtro em que **IsDeleted = FALSE**.

## <a name="next-steps"></a>Próximas etapas

 - Para saber mais sobre a entidade **Usuário Atual**, veja [Referência para a entidade de usuário atual](reports-ref-current-user.md).
 - Para saber mais sobre a entidade **Usuário**, veja [Referência para a entidade de usuário](reports-ref-user.md).