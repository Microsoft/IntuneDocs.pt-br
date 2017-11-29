---
title: "Usuário – Intune Data Warehouse | Microsoft Docs"
description: "Tópico de referência para a categoria de Usuário de coleções de entidade na API Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6f321a3a9ac09c004639a3db15df280fbdb5be3c
ms.sourcegitcommit: d26930f45ba9e6292a49bcb08defb5b3f14b704b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2017
---
# <a name="reference-for-current-user-entity"></a>Referência da entidade de usuário atual

A categoria **Usuário Atual** contém as propriedades de usuário e agente no modelo de dados. A coleção de entidade **Usuário Atual** é limitada a usuários ativos no momento. A entidade contém todos os usuários do Azure Active Directory atribuídos no momento a uma licença. A licença pode ser uma licença do Intune, uma licença Híbrida ou uma licença do Microsoft Office 365. Se um usuário tiver sido removido, ele não será representado durante o período de coleta de dados. Para uma coleção que contém um histórico das alterações no estado do usuário, veja [Referência de entidade do usuário](reports-ref-user.md).


## <a name="user"></a>User

A entidade **Usuário** lista todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| UserKey |Identificador exclusivo do usuário no data warehouse – chave alternativa. |123 |
| UserId |Identificador exclusivo do usuário – semelhante à UserKey, mas é uma chave natural. |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |Endereço de email do usuário. |John@constoso.com |
| UPN | Nome principal de usuário do usuário. | John@constoso.com |
| DisplayName |Nome de exibição do usuário. |John |
| IntuneLicensed |Especifica se este usuário é Intune licenciado ou não. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC em que esse usuário foi criado no data warehouse. |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que esse usuário foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="next-steps"></a>Próximas etapas
 - Use a coleção de entidades **Usuários** para expandir os dados de usuário para usuários que não estão ativos no momento. Para saber mais, veja [Referência para entidade de usuário](reports-ref-user.md). 
 - Saiba mais sobre como o data warehouse controla o tempo de vida de um usuário no Intune, veja [Representação de tempo de vida do usuário no Intune Data Warehouse](reports-ref-user-timeline.md).