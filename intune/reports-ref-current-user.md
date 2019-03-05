---
title: Usuário atual – Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria Usuário Atual de coleções de entidade na API do Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/11/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 08c837ea56276083851977fb4f1972961132296b
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233042"
---
# <a name="reference-for-current-user-entity"></a>Referência da entidade de usuário atual

A categoria **Usuário Atual** contém as propriedades de usuário no modelo de dados. A coleção de entidade **Usuário Atual** é limitada a usuários ativos no momento. A entidade contém todos os usuários do Azure Active Directory atribuídos no momento a uma licença. A licença pode ser uma licença do Intune, uma licença Híbrida ou uma licença do Microsoft Office 365. Se um usuário tiver sido removido, ele não será representado na coleção Usuário Atual. Para uma coleção que contém um histórico das alterações no estado do usuário, veja [Referência de entidade do usuário](reports-ref-user.md).


## <a name="current-user"></a>Usuário atual

A entidade **Usuário Atual** lista todos os usuários do Azure AD (Azure Active Directory) com licenças atribuídas em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| UserKey |Identificador exclusivo do usuário no data warehouse – chave alternativa. |123 |
| UserId |Identificador exclusivo do usuário – semelhante à UserKey, mas é uma chave natural. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Endereço de email do usuário. |John@constoso.com |
| UPN | Nome UPN do usuário. | John@constoso.com |
| DisplayName |Nome de exibição do usuário. |John |
| IntuneLicensed |Especifica se este usuário é Intune licenciado ou não. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC em que esse usuário foi criado no data warehouse. |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que esse usuário foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="next-steps"></a>Próximas etapas
 - Use a coleção de entidades **Usuários** para expandir os dados de usuário para usuários que não estão ativos no momento. Para saber mais, veja [Referência para entidade de usuário](reports-ref-user.md).
 - Saiba mais sobre como o data warehouse controla o tempo de vida de um usuário no Intune, veja [Representação de tempo de vida do usuário no Intune Data Warehouse](reports-ref-user-timeline.md).
