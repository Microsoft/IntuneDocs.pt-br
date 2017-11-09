---
title: "Associação de Dispositivo do Usuário – Intune Data Warehouse | Microsoft Docs"
description: "Uma lista de alterações na API do Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: e9f9fccccef691333143b7523d1b325ee7d1915a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2017
---
# <a name="user-device-association"></a>Associação de Dispositivo de Usuário

A entidade **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização.

| Nome               | Descrição                                                                                      | Exemplo                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Identificador exclusivo do usuário no data warehouse. (Chave substituta).                              | 123                    |
| DeviceKey          | Identificador exclusivo do dispositivo no data warehouse.                                            | 123                    |
| CreatedDateTimeUTC | Data e hora em que a associação de dispositivo de usuário foi criada. Usa o formato UTC.                                | 23/11/2016 12:00:00 AM |
| IsDeleted          | Indica que o usuário cancelou o registro desse dispositivo e que a associação não está mais em vigor. | Verdadeiro/Falso             |
| EndedDateTimeUTC   | Data e hora em UTC em que IsDeleted foi alterado para **True**.                                              | 06/23/2017 12:00:00 AM |
