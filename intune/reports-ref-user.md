---
title: "Usuário – Intune Data Warehouse | Microsoft Docs"
description: "Tópico de referência para a categoria de Usuário de coleções de entidade na API Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8088127f5968c0b4f07f83b1dad02ba90f4e6b9a
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2017
---
# <a name="reference-for-user-entity"></a>Referência para entidade de usuário

A categoria **Usuário** contém a entidade de **Usuário** que define as propriedades de usuário e agente no modelo de dados.

**Usuário**

A entidade **Usuário** lista todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| UserKey |Identificador exclusivo do usuário no data warehouse – chave alternativa. |123 |
| UserId |Identificador exclusivo do usuário – semelhante à UserKey, mas é uma chave natural. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Endereço de email do usuário. |John@constoso.com |
| DisplayName |Nome de exibição do usuário. |John |
| IntuneLicensed |Especifica se este usuário é Intune licenciado ou não. |Verdadeiro/Falso |
| IsDeleted |Indica se este registro de usuário foi atualizado.  Verdadeiro – esse usuário tem um novo registro com campos atualizados nesta tabela. Falso – o registro mais recente para este usuário. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC em que esse usuário foi criado no data warehouse. |23/11/2016 12:00:00 AM |
| EndDateExclusiveUTC |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| IsCurrent |Indica se este registro de usuário é atual ou não no data warehouse. |Verdadeiro/Falso |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que esse usuário foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

