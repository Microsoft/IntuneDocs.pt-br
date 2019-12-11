---
title: Usuário – Intune Data Warehouse
titleSuffix: Microsoft Intune
description: Tópico de referência para a categoria de Usuário de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 996e28f9dceff88637c93e667597e3364215b965
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72505625"
---
# <a name="reference-for-user-entity"></a>Referência para a entidade de usuário

A categoria **Users** contém a entidade **user** que define as propriedades de usuário no modelo de dados.

## <a name="users"></a>usuários

A entidade **usuário** lista todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa.

A coleção de entidades **usuário** contém dados do usuário. Esses registros incluem estados do usuário durante o período de coleta de dados, mesmo se o usuário tiver sido removido. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados do mês anterior. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

|          Propriedade          |                                                                                                           Descrição                                                                                                          |                Exemplo               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| userKey                    | Identificador exclusivo do usuário no data warehouse – chave alternativa.                                                                                                                                                         | 123                                  |
| userId                     | O identificador exclusivo do usuário – semelhante à UserKey, mas é uma chave natural.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| userEmail                  | Endereço de email do usuário.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Nome UPN do usuário.                                                                                                                                                                                               | John@constoso.com                    |
| displayName                | Nome de exibição do usuário.                                                                                                                                                                                                      | John                                 |
| intuneLicensed             | Especifica se este usuário é Intune licenciado ou não.                                                                                                                                                                              | Verdadeiro/Falso                           |
| isDeleted                  | Indica se todas as licenças do usuário expiraram e se o usuário foi, portanto, removido do Intune. Para um único registro, esse sinalizador não é alterado. Em vez disso, um novo registro é criado para um novo estado do usuário. | Verdadeiro/Falso                           |
| RowLastModifiedDateTimeUTC | A data e a hora em UTC de quando o registro foi modificado pela última vez no data warehouse                                                                                                                                                 | 23/11/2016 0:00                      |


## <a name="next-steps"></a>Próximas etapas
- Use a coleção de entidades **Usuário Atual** para limitar os dados de usuário para usuários que estão ativos no momento. Para saber mais, veja [Referência para entidade de usuário atual](../reports-ref-current-user.md).
- Saiba mais sobre como o data warehouse controla o tempo de vida de um usuário no Intune em [Representação de tempo de vida do usuário no Intune Data Warehouse](reports-ref-user-timeline.md).
