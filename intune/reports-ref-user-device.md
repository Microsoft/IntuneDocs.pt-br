---
title: Associação de dispositivo do usuário – Intune Data Warehouse
titleSuffix: Microsoft Intune
description: A entidade UserDeviceAssociation contém associações de dispositivo de usuário em sua organização.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4593fd5e76bf51b11ef9796bacc8c562241eaca2
ms.sourcegitcommit: c8cb314256c4896e838918f015ffaefb8f00ace5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "70001737"
---
# <a name="reference-for-user-device-association-entity"></a>Referência da entidade Associação de dispositivo de usuário

A entidade **userDeviceAssociation** contém associações de dispositivo de usuário em sua organização.

## <a name="userdeviceassociations"></a>userDeviceAssociations


|        Nome        |                                           Descrição                                            |        Exemplo         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      userKey       |              Identificador exclusivo do usuário no data warehouse. (Chave substituta).               |          123           |
|     deviceKey      |                      Identificador exclusivo do dispositivo no data warehouse.                      |          123           |
| createdDateTimeUTC |           Data e hora em que a associação de dispositivo de usuário foi criada. Usa o formato UTC.           | 23/11/2016 12:00:00 AM |
|     isDeleted      | Indica que o usuário cancelou o registro desse dispositivo e que a associação não está mais em vigor. |       Verdadeiro/Falso       |
|  endedDateTimeUTC  |              Data e hora em UTC em que IsDeleted foi alterado para <strong>True</strong>.               | 06/23/2017 12:00:00 AM |

## <a name="next-steps"></a>Próximas etapas

- Saiba mais sobre o [Intune Data Warehouse](reports-nav-create-intune-reports.md).
