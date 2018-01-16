---
title: "Usuário – Intune Data Warehouse | Microsoft Docs"
description: "Tópico de referência para a categoria de Usuário de coleções de entidade na API Intune Data Warehouse."
keywords: Intune Data Warehouse
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 917c9585ffe17f9d090c519f716d284aa1b932b8
ms.sourcegitcommit: b2467a653ffd36c2248a30b69cb88e3dc7cca2ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2017
---
# <a name="reference-for-user-entity"></a>Referência para entidade de usuário

A categoria **Usuário** contém a entidade de **Usuário** que define as propriedades de usuário no modelo de dados.

## <a name="user"></a>Usuário

A entidade **Usuário** lista todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa.

A coleção de entidades **Usuário** contém dados do usuário. Esses registros incluem estados do usuário durante o período de coleta de dados, mesmo se o usuário tiver sido removido. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados do mês anterior. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| UserKey |Identificador exclusivo do usuário no data warehouse – chave alternativa. |123 |
| UserId |Identificador exclusivo do usuário – semelhante à UserKey, mas é uma chave natural. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Endereço de email do usuário. |John@constoso.com |
| UPN | Nome principal de usuário do usuário. | John@constoso.com |
| DisplayName |Nome de exibição do usuário. |John |
| IntuneLicensed |Especifica se este usuário é Intune licenciado ou não. |Verdadeiro/Falso |
| IsDeleted | Indica se todas as licenças do usuário expiraram e se o usuário foi, portanto, removido do Intune. Para um único registro, esse sinalizador não é alterado. Em vez disso, um novo registro é criado para um novo estado do usuário. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Se IsDeleted = FALSE, DateTime em UTC de quando o usuário recebeu uma licença e começou a ter presença no Intune. Se IsDeleted = verdadeiro, DateTime em UTC de quando as licenças do usuário expiraram e foram removidas do Intune. |23/11/2016 12:00:00 AM |
| EndDateExclusiveUTC |Se IsDeleted = FALSE, DateTime em UTC de quando a licença do usuário expirou e foi removida do Intune. A licença expirou em algum momento durante o dia anterior. Se IsDeleted = TRUE, DateTime em UTC de quando o usuário recuperou uma nova licença e foi recriado no Intune.  |23/11/2016 12:00:00 AM |
| IsCurrent |Indica se este registro representa o estado mais recente do usuário. Podem existir vários registros para um único usuário, mas somente um deles representa o estado atual.  |Verdadeiro/Falso |
| RowLastModifiedDateTimeUTC |Data e hora em UTC de quando o registro foi modificado pela última vez no data warehouse  |23/11/2016 12:00:00 AM |

## <a name="next-steps"></a>Próximas etapas
 - Use a coleção de entidades **Usuário Atual** para limitar os dados de usuário para usuários que estão ativos no momento. Para saber mais, confira [Referência para entidade de usuário atual](reports-ref-current-user.md).
 - Para saber mais sobre como o data warehouse controla o tempo de vida de um usuário no Intune, veja [Representação de tempo de vida do usuário no Intune Data Warehouse](reports-ref-user-timeline.md).
