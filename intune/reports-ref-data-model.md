---
title: Modelo de dados do Data Warehouse | Microsoft Docs
description: "O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do ambiente móvel em constante mudança."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d52e240763263ac4f761a8635ee6694a45168354
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2017
---
# <a name="data-warehouse-data-model"></a>Modelo de dados do Data Warehouse

O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do ambiente móvel em constante mudança.

Os dados extraídos de seu locatário são adicionados a um data warehouse. O warehouse é um conjunto de entidades e relações que são significativas para o tipo de perguntas que você deseja fazer. Por exemplo, é possível examinar o número de instalações de um aplicativo do Android desenvolvido internamente por dia durante a última semana para avaliar se há uma tendência crescente de instalações. A estrutura do data warehouse permite que você se aprofunde no seu ambiente móvel. Por sua vez, as ferramentas analíticas, como o Microsoft Power BI, podem usar o modelo de dados de Data Warehouse para criar visualizações e dashboards dinâmicos.

A estrutura do Intune Data Warehouse usa um modelo de esquema em estrela. Um esquema em estrela organiza fatos na dimensão de tempo. Um *fatos* no contexto do modelo é uma medida quantitativa, como o número de dispositivos, o número de aplicativos ou a hora do registro. Uma *dimensão* no contexto do modelo é um conjunto de categorias e suas relações hierárquicas. Por exemplo, os dias são agrupados em meses e os meses são agrupados em anos. Um modelo de esquema em estrela é otimizado para análise de dados e flexibilidade para que você possa criar os relatórios necessários para entender seu ambiente móvel em evolução.

O warehouse expõe dados nas seguintes categorias de alto nível:
  -  Uso e aplicativos habilitados pela proteção do aplicativo
  -  Inventário, propriedades e dispositivos registrados
  -  Inventário de aplicativos e software
  -  Políticas de conformidade e configuração do dispositivo

**Conjuntos de entidades do modelo de dados**

Conjuntos de entidades são conhecidos como coleções de entidades no modelo de dados. Esses conjuntos contêm entidades que definem os dados coletados no modelo. Cada conjunto de entidades fornece um ponto de acesso para o modelo de dados do Data Warehouse. Encontre detalhes sobre as seguintes categorias de entidades:

  -  [Data](reports-ref-date.md)
  -  [Usuário](reports-ref-user.md)
  -  [Gerenciamento de aplicativo móvel (MAM)](reports-ref-mobile-app-management.md)
  -  [Dispositivos](reports-ref-devices.md)
  -  [Aplicativo](reports-ref-application.md)
  -  [Política](reports-ref-policy.md)
  -  [Associação de dispositivo de usuário](reports-ref-userdeviceassociations.md)

<!-- ## Data Model relationships

For more information on the relationships in the data model, see [Relationships of Entities](reports-api-entity-relationships.md). -->