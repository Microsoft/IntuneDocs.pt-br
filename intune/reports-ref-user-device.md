---
title: Associação de dispositivo do usuário – Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Uma lista de alterações na API do Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e78d2c75710b97ec67b64bd745629e7863778bd0
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="user-device-association"></a>Associação de Dispositivo de Usuário

A entidade **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização.


|        Nome        |                                           Descrição                                            |        Exemplo         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Identificador exclusivo do usuário no data warehouse. (Chave substituta).               |          123           |
|     DeviceKey      |                      Identificador exclusivo do dispositivo no data warehouse.                      |          123           |
| CreatedDateTimeUTC |           Data e hora em que a associação de dispositivo de usuário foi criada. Usa o formato UTC.           | 23/11/2016 12:00:00 AM |
|     IsDeleted      | Indica que o usuário cancelou o registro desse dispositivo e que a associação não está mais em vigor. |       Verdadeiro/Falso       |
|  EndedDateTimeUTC  |              Data e hora em UTC em que IsDeleted foi alterado para <strong>True</strong>.               | 06/23/2017 12:00:00 AM |

