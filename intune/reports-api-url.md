---
title: Ponto de extremidade de API do Intune Data Warehouse
titlesuffix: Microsoft Intune
description: O tópico de referência descreve a estrutura de URL da API do Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/09/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c6709d68ce4bf847be3eb5cd5ae427db6d11aba8
ms.sourcegitcommit: 11bd3dbbc9dd762df7c6d20143f2171799712547
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2018
ms.locfileid: "48903583"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Ponto de extremidade de API do Intune Data Warehouse

Você pode usar a API do Intune Data Warehouse com uma conta com credenciais do Azure AD e controles de acesso baseados em função específica. Em seguida, autorize o cliente REST com o Azure AD usando OAuth 2.0. E, finalmente, você formará uma URL significativa para chamar um recurso do data warehouse.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Authorization

O Azure Active Directory (Azure AD) usa OAuth 2.0 para que você possa autorizar o acesso a aplicativos Web e APIs Web em seu locatário do Azure AD. Este guia é independente de linguagem e descreve como enviar e receber mensagens HTTP sem usar nenhuma biblioteca de software livre. O fluxo de código de autorização OAuth 2.0 é descrito na [seção 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) da especificação do OAuth 2.0.

Para obter mais informações, consulte [Autorizar o acesso a aplicativos Web usando o OAuth 2.0 e o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Estrutura de URL da API

Os pontos de extremidade de API do Data Warehouse leem as entidades para cada conjunto. A API dá suporte a um verbo HTTP **GET** e um subconjunto das opções de consulta.

A URL para Intune usa o seguinte formato:  
`https://fef.{location}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity-collection}?api-version={api-version}`

> [!NOTE]
> Na URL acima, substitua `{location}`, `{entity-collection}` e `{api-version}` com base nos detalhes fornecidos na tabela abaixo.

A URL contém os seguintes elementos:

| Elemento | Exemplo | Descrição |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| local | msua06 | A URL de base pode ser encontrada ao exibir a folha de API do Data Warehouse no portal do Azure. |
| coleção de entidades | datas | O nome da coleção de entidades do OData. Para obter mais informações sobre coleções e entidades no modelo de dados, consulte [Modelo de dados](reports-ref-data-model.md). |
| api-version | beta | Versão é a versão da API para acessar. Para obter mais informações, consulte [Versão](#API-version-information). |
| maxhistorydays | 7 | (Opcional) O número máximo de dias de histórico a ser recuperado. Esse parâmetro pode ser fornecido para qualquer coleção, mas só entrará em vigor para coleções que incluem `dateKey` como parte de sua propriedade de chave. Confira [Filtros de intervalo de DateKey](reports-api-url.md#datekey-range-filters) para obter mais informações. |

## <a name="api-version-information"></a>Informações de versão da API

A versão atual da API é: `beta`. 

## <a name="odata-query-options"></a>Opções de consulta de OData

A versão atual oferece dá suporte aos seguintes parâmetros de consulta OData: `$filter, $orderby, $select, $skip,` e `$top`.

## <a name="datekey-range-filters"></a>Filtros de intervalo de DateKey

Os filtros de intervalo de `DateKey` podem ser usados para limitar a quantidade de dados a serem baixados de algumas das coleções com `dateKey` como uma propriedade de chave. O filtro `DateKey` pode ser usado para otimizar o desempenho do serviço fornecendo o seguinte parâmetro de consulta `$filter`:

1.  `DateKey` sozinho no `$filter`, dando suporte aos operadores `lt/le/eq/ge/gt` e unindo-se ao operador lógico `and`, em que eles podem ser mapeados para uma data de início e/ou data de término.
2.  `maxhistorydays` é fornecido como a opção de consulta personalizada.<br>

## <a name="filter-examples"></a>Exemplos de filtro

> [!NOTE]
> Os exemplos de filtro pressupõem que hoje seja 21/2/2018.

|                             Filter                             |           Otimização de desempenho           |                                          Descrição                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Completo                                      |    Retorna dados com `DateKey` entre 20180214 e 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Completo                                      |    Retorna dados com `DateKey` igual a 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Completo                                      |    Retorna dados com `DateKey` entre 20180214 e 20180220.                                     |
|    `maxhistorydays=7&$filter=Id gt 1`                            |    Parcial; uma ID maior que 1 não será otimizada    |    Retorna dados com `DateKey` entre 20180214 e 20180221 e uma ID maior que 1.             |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Completo                                      |    Retorna dados com `DateKey` igual a 20180214. `maxhistorydays` é ignorado.                            |
|    `$filter=DateKey eq 20180214 and Id gt 1`                     |    Nenhum                                      |    Não tratado como um filtro de intervalo de `DateKey` e, portanto, não há nenhum aumento de desempenho.                              |
|    `$filter=DateKey ne 20180214`                                 |    Nenhum                                      |    Não tratado como um filtro de intervalo de `DateKey` e, portanto, não há nenhum aumento de desempenho.                              |
|    `maxhistorydays=7&$filter=DateKey eq 20180214 and Id gt 1`    |    Nenhum                                      |    Não tratado como um filtro de intervalo de `DateKey` e, portanto, não há nenhum aumento de desempenho. `maxhistorydays` é ignorado.    |
