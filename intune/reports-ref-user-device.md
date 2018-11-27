---
title: Associação de dispositivo do usuário – Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Uma lista de alterações na API do Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: a207c0f9e7f1890d88ca233df6f4c53a32aed51b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189785"
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

