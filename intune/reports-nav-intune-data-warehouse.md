---
title: API Intune Date Warehouse | Microsoft Docs
description: "Use a API para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a0d6bcb4ccac3563dd642ec0ad621645b7053dea
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2017
---
#  <a name="intune-data-warehouse-api"></a>API Intune Data Warehouse

A API do Data Warehouse do Intune permite acessar os dados do Intune em um formato legível para o computador para que eles sejam usados em sua ferramenta de análise favorita. Use a API para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa. A API usa o protocolo OData, que segue os padrões para:

  -   Cabeçalhos de solicitação e resposta
  -   Códigos de status
  -   Métodos de HTTP
  -   Convenções de URL
  -   Tipos de mídia
  -   Formatos de carga
  -   Opções de consulta

O OData (Protocolo Open Data) é uma organização para o Avanço de Padrões de informações estruturadas (OASIS) que define a prática recomendada para criação e consumo de APIs RESTful. O Intune Data Warehouse usa a versão 4.0 do OData.

Esta seção de referência fornece uma visão geral dos pontos de extremidade, métodos HTTP com suporte, formatos de carga de retorno e documentação do modelo de dados do Intune Data Warehouse.

> [!Important]  
> Você pode testar a funcionalidade mais recente do Data Warehouse usando a versão beta. Para usar a versão beta, a URL deve conter o parâmetro de consulta `api-version=beta`. A versão beta oferece recursos antes que eles estejam disponíveis como um serviço com suporte. Como o Intune adiciona novos recursos, a versão beta pode ter dados e o comportamento diferentes dos contratos. Qualquer código personalizado ou quaiquer ferramentas de relatório dependentes da versão beta de relatório podem ser corrompidas com atualizações contínuas. <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

## <a name="odata-custom-client"></a>Cliente personalizado do OData

Você pode acessar o modelo de dados do Data Warehouse do Intune por meio de pontos de extremidade RESTful. Para obter acesso aos seus dados, seu cliente deve ser autorizado no Azure AD (Azure Active Directory) usando OAuth 2.0. Primeiro você configura um aplicativo Web e um aplicativo cliente no Azure e concede permissões para o cliente. Seu cliente local obterá a autorização e, assim, poderá se comunicar com os pontos de extremidade do Data Warehouse.

Para obter mais informações, consulte [Obter dados da API do Data Warehouse com um cliente REST](reports-proc-data-rest.md)

> [!Note]  
> Você pode acessar o [repositório do Data Warehouse do Intune do GitHub](https://github.com/Microsoft/Intune-Data-Warehouse) no Github para obter exemplos de código.

## <a name="interacting-with-the-api"></a>Interação com a API

A API requer autorização com o Azure AD. O Azure AD usa OAuth 2.0. Uma vez autorizado, você pode obter dados da API usando um verbo HTTP GET e entrar em contato com as coleções de entidades expostas. Para obter detalhes, consulte:

 -  [Autorização](reports-api-url.md)
 -  [Estrutura de URL da API](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Modelo de dados do Intune Data Warehouse

OData define um modelo de dados abstrato e um protocolo que permite que qualquer cliente acesse informações expostas por qualquer fonte de dados. O tópico de documentação do modelo de dados contém uma explicação sobre os namespaces, entidades e objetos de retorno no modelo de dados do Intune Data Warehouse. Para saber mais, consulte [Modelo de dados do Data Warehouse](reports-ref-data-model.md).

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre como trabalhar com o Azure AD lendo os [Cenários de autenticação do Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).

Localize recursos do OData em [odata.org](http://www.odata.org).
  
Examine o padrão do OData Versão 4.0 em [OData Versão 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
