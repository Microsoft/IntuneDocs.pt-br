---
title: Associação de dispositivo do usuário – Intune Data Warehouse
titlesuffix: Microsoft Intune
description: A entidade UserDeviceAssociation contém associações de dispositivo de usuário em sua organização.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.openlocfilehash: 02c579a7371a59a46cfb0017e6aa1a17af92bd03
ms.sourcegitcommit: 1c9ef5cfac2fc024528d2cfc9d590fa68dd58080
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2018
ms.locfileid: "53429552"
---
# <a name="reference-for-user-device-association-entity"></a>Referência da entidade Associação de dispositivo de usuário

A entidade **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização.

## <a name="userdeviceassociation"></a>UserDeviceAssociation


|        Nome        |                                           Descrição                                            |        Exemplo         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      UserKey       |              Identificador exclusivo do usuário no data warehouse. (Chave substituta).               |          123           |
|     DeviceKey      |                      Identificador exclusivo do dispositivo no data warehouse.                      |          123           |
| CreatedDateTimeUTC |           Data e hora em que a associação de dispositivo de usuário foi criada. Usa o formato UTC.           | 23/11/2016 12:00:00 AM |
|     IsDeleted      | Indica que o usuário cancelou o registro desse dispositivo e que a associação não está mais em vigor. |       Verdadeiro/Falso       |
|  EndedDateTimeUTC  |              Data e hora em UTC em que IsDeleted foi alterado para <strong>True</strong>.               | 06/23/2017 12:00:00 AM |

## <a name="next-steps"></a>Próximas etapas

- Saiba mais sobre o [Intune Data Warehouse](reports-nav-create-intune-reports.md).