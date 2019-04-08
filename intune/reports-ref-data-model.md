---
title: Modelo de dados do Data Warehouse
titleSuffix: Microsoft Intune
description: O Microsoft Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do ambiente móvel em constante mudança.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 43e555a27565de43d417adc473d48254d8b7d5a2
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798166"
---
# <a name="microsoft-intune-data-warehouse-data-model"></a>Modelo de dados do Microsoft Intune Data Warehouse

O Intune Data Warehouse coleta amostras de dados diariamente para fornecer uma exibição histórica do ambiente de dispositivos móveis em constante mudança. A exibição é composta por entidades relacionadas no tempo.

## <a name="entities-entity-sets"></a>Entidade: conjuntos de entidades

O warehouse expõe dados nas seguintes áreas de alto nível:

  -  Uso e aplicativos habilitados pela proteção do aplicativo
  -  Inventário, propriedades e dispositivos registrados
  -  Inventário de aplicativos e software
  -  Políticas de conformidade e configuração do dispositivo

Essas áreas contêm entidades que são significativas para seu ambiente do Intune. Encontre detalhes sobre os conjuntos de entidade nos tópicos a seguir:

  -  [Aplicativo](reports-ref-application.md)
  -  [Data](reports-ref-date.md)
  -  [Dispositivos](reports-ref-devices.md)
  -  [Extensão de Gerenciamento do Intune](reports-ref-intunemanagementextension.md)
  -  [Política](reports-ref-policy.md)
  -  [Gerenciamento de aplicativo móvel (MAM)](reports-ref-mobile-app-management.md)
  -  [Usuário](reports-ref-user.md)
  -  [Usuário Atual](reports-ref-current-user.md)
  -  [Associações de Dispositivo de Usuário](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a>Relações: modelo de esquema em estrela

O warehouse organiza as entidades em relações que são significativas para o tipo de perguntas que você deseja fazer. Por exemplo, você pode examinar o número de instalações de um aplicativo do Android desenvolvido internamente. A estrutura do data warehouse permite que você se aprofunde no seu ambiente móvel. Por sua vez, as ferramentas analíticas, como o Microsoft Power BI, podem usar o modelo de dados de Data Warehouse para criar visualizações e dashboards dinâmicos.

As entidades e relações usam um modelo de esquema em estrela. Um esquema em estrela correlaciona fatos na dimensão de tempo. Um *fatos* no contexto do modelo é uma medida quantitativa, como o número de dispositivos, o número de aplicativos ou a hora do registro. Tabelas de fatos armazenam muitos dados. Elas podem ficar muito grandes e, portanto, normalmente limitam informações a 30 dias. Um *dimensão* fornece um contexto para os fatos. Onde o fato mede o que aconteceu, as dimensões indicam para quem isso aconteceu. As tabelas de dimensão, por exemplo, a tabela **Usuário**, são menores e podem reter dados por períodos mais longos do que as tabelas de fatos. 

Um modelo de esquema em estrela é otimizado para análise de dados e flexibilidade para que você possa criar os relatórios necessários para entender seu ambiente móvel em evolução.

## <a name="time-daily-snapshots"></a>Tempo: Instantâneos diários

O warehouse segue o downstream, partindo dos seus dados no Intune. O Intune tira um instantâneo diário à meia-noite UTC, e armazena o instantâneo no warehouse. A duração dos instantâneos mantidos varia de acordo com a tabela de fatos. Algumas podem manter por sete dias, outras por 30 dias e algumas por períodos até mais longos.

## <a name="next-steps"></a>Próximas etapas

 - Saiba mais sobre como o data warehouse controla o tempo de vida de um usuário no Intune em [Representação de tempo de vida do usuário no Intune Data Warehouse](reports-ref-user-timeline.md).
 - Saiba mais sobre como trabalhar com os data warehouses em [Criar data warehouse de primeiros dados](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse).
 - Saiba mais sobre como trabalhar com o Power BI e um data warehouse em [Criar um novo relatório do Power BI importando um conjunto de dados](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/). 
