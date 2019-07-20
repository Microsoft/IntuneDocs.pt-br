---
title: Linha do tempo da entidade Usuário do Data Warehouse
titleSuffix: Microsoft Intune
description: Saiba como o Microsoft Intune Data Warehouse representa Usuários em uma linha do tempo.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/26/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 363D148E-688F-4830-B6DE-AB4FE3648817
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b61f4ded04d01f04727768557e6730c34fd4760c
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67882451"
---
# <a name="user-lifetime-representation-in-the-microsoft-intune-data-warehouse"></a>Representação do tempo de vida do usuário no Microsoft Intune Data Warehouse

Você pode usar o mês de instantâneos de dados armazenados no Intune Data Warehouse para responder perguntas sobre tendências com base em tempo. Por exemplo, você pode examinar o número de usuários adicionados durante um mês. Você também pode perguntar sobre o número de usuários que foram removidos do sistema.

Para fornecer esse insight de tipo, o data warehouse armazena informações de histórico. O data warehouse pode controlar o tempo de vida de uma entidade. O warehouse registra quando uma entidade foi criada, quando o estado da entidade é alterado e quando uma entidade é excluída. Com o histórico capturado com instantâneos diários de medidas quantitativas, você pode comparar um dia com o dia anterior etc.

Trabalhar com tempos de vida de entidade pode ser confuso, pois suas entidades mudam de estado. Isso significa que se você olhar para um instantâneo no dia 30, talvez não exista um registro de usuário em um estado ativo nos dados. No dia 29-28 o registro da entidade pode existir como ativo. E, então, antes do dia 28, o usuário nem existia.

Este cenário poderá ficar mais claro se você percorrer o tempo de vida de uma entidade.

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

- Para saber mais sobre a entidade **Usuário atual**, consulte [Reference for current user entity](reports-ref-current-user.md) (Referência para a entidade de usuário atual).
- Para saber mais sobre a entidade **Usuário**, consulte [Reference for user entity](reports-ref-user.md) (Referência para a entidade de usuário).
