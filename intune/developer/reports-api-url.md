---
title: Ponto de extremidade de API do Intune Data Warehouse
titleSuffix: Microsoft Intune
description: Este tópico de referência descreve a estrutura de URL da API do Microsoft Intune Data Warehouse. Exemplos de filtro são fornecidos.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/03/2020
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e19cc606792c59d2f5676aeca41d862308f1ab32
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654134"
---
# <a name="intune-data-warehouse-api-endpoint"></a>Ponto de extremidade de API do Intune Data Warehouse

Você pode usar a API do Intune Data Warehouse com uma conta com credenciais do Azure AD e controles de acesso baseados em função específica. Em seguida, autorize o cliente REST com o Azure AD usando OAuth 2.0. E, finalmente, você formará uma URL significativa para chamar um recurso do data warehouse.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

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
| coleção de entidades | devicePropertyHistories | O nome da coleção de entidades do OData. Para obter mais informações sobre coleções e entidades no modelo de dados, consulte [Modelo de dados](reports-ref-data-model.md). |
| api-version | beta | Versão é a versão da API para acessar. Para obter mais informações, consulte [Versão](reports-api-url.md#api-version-information). |
| maxhistorydays | 7 | (Opcional) O número máximo de dias de histórico a ser recuperado. Esse parâmetro pode ser fornecido para qualquer coleção, mas só entrará em vigor para coleções que incluem `dateKey` como parte de sua propriedade de chave. Confira [Filtros de intervalo de DateKey](reports-api-url.md#datekey-range-filters) para obter mais informações. |

## <a name="api-version-information"></a>Informações de versão da API

Agora é possível usar a versão v1.0 do Intune Data Warehouse, definindo o parâmetro de consulta  `api-version=v1.0`. As atualizações em coleções no Data Warehouse são suplementares por natureza e não interrompem cenários existentes.

Você pode testar a funcionalidade mais recente do Data Warehouse usando a versão beta. Para usar a versão beta, a URL deve conter o parâmetro de consulta  `api-version=beta`. A versão beta oferece recursos antes que eles estejam disponíveis como um serviço com suporte. Como o Intune adiciona novos recursos, a versão beta pode ter dados e o comportamento diferentes dos contratos. Qualquer código personalizado ou quaiquer ferramentas de relatório dependentes da versão beta de relatório podem ser corrompidas com atualizações contínuas.

## <a name="odata-query-options"></a>Opções de consulta de OData

A versão atual dá suporte aos seguintes parâmetros de consulta OData: `$filter`, `$select`, `$skip,` e `$top`. Em `$filter`, somente `DateKey` ou `RowLastModifiedDateTimeUTC` podem ter suporte quando as colunas são aplicáveis, outras propriedades disparariam uma solicitação inválida.

## <a name="datekey-range-filters"></a>Filtros de intervalo de DateKey

Os filtros de intervalo de `DateKey` podem ser usados para limitar a quantidade de dados a serem baixados de algumas das coleções com `dateKey` como uma propriedade de chave. O filtro `DateKey` pode ser usado para otimizar o desempenho do serviço fornecendo o seguinte parâmetro de consulta `$filter`:

1. `DateKey` sozinho no `$filter`, dando suporte aos operadores `lt/le/eq/ge/gt` e unindo-se ao operador lógico `and`, em que eles podem ser mapeados para uma data de início e/ou data de término.
2. `maxhistorydays` é fornecido como a opção de consulta personalizada.<br>

## <a name="filter-examples"></a>Exemplos de filtro

> [!NOTE]
> Os exemplos de filtro pressupõem que hoje seja 21/02/2019.

|                             Filtro                             |           Otimização de desempenho           |                                          Descrição                                          |
|:--------------------------------------------------------------:|:--------------------------------------------:|:---------------------------------------------------------------------------------------------:|
|    `maxhistorydays=7`                                            |    Completo                                      |    Retorna dados com `DateKey` entre 20180214 e 20180221.                                     |
|    `$filter=DateKey eq 20180214`                                 |    Completo                                      |    Retorna dados com `DateKey` igual a 20180214.                                                    |
|    `$filter=DateKey ge 20180214 and DateKey lt 20180221`         |    Completo                                      |    Retorna dados com `DateKey` entre 20180214 e 20180220.                                     |
|    `maxhistorydays=7&$filter=DateKey eq 20180214`                |    Completo                                      |    Retorna dados com `DateKey` igual a 20180214. `maxhistorydays` é ignorado.                            |
|    `$filter=RowLastModifiedDateTimeUTC ge 2018-02-21T23:18:51.3277273Z`                                |    Completo                                       |    Dados de retorno com `RowLastModifiedDateTimeUTC` é maior ou igual a `2018-02-21T23:18:51.3277273Z`                             |
