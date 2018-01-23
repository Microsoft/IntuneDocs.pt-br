---
title: "Associação de Dispositivo do Usuário – Intune Data Warehouse | Microsoft Docs"
description: "Uma lista de alterações na API do Intune Data Warehouse."
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095395be4c86780ad65ba1e24b856f6eef8d41ae
ms.sourcegitcommit: d44c32aad3e84f6c0b296bdb010981d3a818befb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2018
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
