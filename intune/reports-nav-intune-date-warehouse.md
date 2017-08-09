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
ms.openlocfilehash: 5f03fd3a1557ef5d013fe695016ed0e3b119ee62
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2017
---
#  <a name="intune-data-warehouse-api"></a>API Intune Data Warehouse

A API Intune Data Warehouse permite acessar os dados do Intune em um formato legível para o computador para uso em sua ferramenta favorita de análise. Use a API para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa. A API usa o protocolo OData, que segue os padrões para:

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

<!-- ## OData custom client

You can access the Intune Data Warehouse data model through RESTful endpoints. To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0. You first set up a web app and a client app in Azure, grant permissions to the client. Your local client will get authorization, can then communicate with the Data Warehouse endpoints.

For more information, see [Get data from the Data Warehouse API with a REST client](Get-data-REST.md) -->

## <a name="interacting-with-the-api"></a>Interação com a API

A API requer autorização com o Azure AD. O Azure AD usa OAuth 2.0. Uma vez autorizado, você pode obter dados da API usando um verbo HTTP GET e entrar em contato com as coleções de entidades expostas. Para obter detalhes, consulte:

 -  [Autorização](reports-api-url.md)
 -  [Estrutura de URL da API](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a>Modelo de dados do Intune Data Warehouse

OData define um modelo de dados abstrato e um protocolo que permite que qualquer cliente acesse informações expostas por qualquer fonte de dados. O tópico de documentação do modelo de dados contém uma explicação sobre os namespaces, entidades e objetos de retorno no modelo de dados do Intune Data Warehouse. Para saber mais, consulte [Modelo de dados do Data Warehouse](reports-ref-data-model.md).

## <a name="for-more-information"></a>Para obter mais informações

[Cenários de autenticação para o Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios)  
[odata.org](http://www.odata.org)  
[Versão 4.0 do OData](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)  
