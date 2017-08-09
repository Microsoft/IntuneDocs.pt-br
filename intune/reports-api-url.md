---
title: Ponto de extremidade do Intune Data Warehouse | Microsoft Docs
description: "O tópico de referência descreve a estrutura de URL da API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7723bb42eedcd97142f039ca52b60911fa91838b
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Ponto de extremidade de API do Intune Data Warehouse

Você pode usar a API do Intune Data Warehouse com uma conta com credenciais do Azure AD e controles de acesso baseados em função específica. Em seguida, autorize o cliente REST com o Azure AD usando OAuth 2.0. E, finalmente, você formará uma URL significativa para chamar um recurso do data warehouse.

## <a name="azure-ad-and-intune-credential-requirements"></a>Requisitos de credencial do Intune e Azure AD

Autenticação e autorização têm base em credenciais do Azure AD e controle de acesso com base em função do Intune (RBAC). Todos os administradores globais e administradores de serviço do Intune para seu locatário têm acesso à API por padrão. Use funções do Intune para fornecer acesso a mais usuários, oferecendo a eles acesso para o **recurso de Emissão de relatórios**.

Os requisitos para acessar a API são:

  -  A licença do Intune deve ser atribuída ao usuário
  -  O usuário deve ser um destes:
      -  Administrador global do Azure AD
      -  Um administrador de serviços do Intune
      -  Usuário com acesso baseado em função para o recurso de **relatórios**

## <a name="authorization"></a>Authorization

O Azure Active Directory (Azure AD) usa OAuth 2.0 para que você possa autorizar o acesso a aplicativos Web e APIs Web em seu locatário do Azure AD. Este guia é independente de linguagem e descreve como enviar e receber mensagens HTTP sem usar qualquer uma das nossas bibliotecas de código-fonte aberto. O fluxo de código de autorização OAuth 2.0 é descrito na [seção 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) da especificação do OAuth 2.0.

Para obter mais informações, consulte [Autorizar o acesso a aplicativos Web usando o OAuth 2.0 e o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>Estrutura de URL da API

Os pontos de extremidade de API do Data Warehouse leem as entidades para cada conjunto. A API dá suporte a um verbo HTTP **GET** e um subconjunto das opções de consulta.

A URL para Intune usa o seguinte formato:  
https://fef.{***location***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{***entity-collection***}?api-version={***api-version***}

A URL contém os seguintes elementos:

| Elemento | Exemplo | Descrição |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| local | msua06 | A URL de base pode ser encontrada ao exibir a folha de API do Data Warehouse no portal do Azure. |
| coleção de entidades | datas | O nome da coleção de entidades do OData. Para obter mais informações sobre coleções e entidades no modelo de dados, consulte [Modelo de dados](reports-ref-data-model.md). |
| api-version | beta | Versão é a versão da API para acessar. Para obter mais informações, consulte [Versão](#API-version-information). |


## <a name="api-version-information"></a>Informações de versão da API

A versão atual da API é: `beta`. 

## <a name="odata-query-options"></a>Opções de consulta de OData

A versão atual dá suporte aos seguintes parâmetros de consulta OData: `$skip, $top, $filter, $orderby`.