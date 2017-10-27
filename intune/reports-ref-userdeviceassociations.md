---
title: "Associação de dispositivo do usuário | Microsoft Docs"
description: "Tópico de referência para a categoria Associação de dispositivo de usuário da coleção de entidades na API do Data Warehouse do Intune."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: BCDBABCB-A7B1-42F2-BDD1-D055E33F2239
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 490e29f87c65875a385472e6abe9400363383f9b
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/20/2017
---
# <a name="reference-for-user-device-association-entity"></a>Referência da entidade Associação de dispositivo de usuário

A categoria **Associação de dispositivo de usuário** contém a entidade **Associação de dispositivo de usuário** usada para definir as associações de dispositivo na organização.

**Associação de Dispositivo de Usuário**

A entidade **Associação de dispositivo de usuário** representa as associações de dispositivo definidas na organização.

| Nome               | Descrição                                                                                      | Exemplo                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Identificador exclusivo do usuário no data warehouse – chave alternativa.                             | 123                    |
| DeviceKey          | Identificador exclusivo do dispositivo no data warehouse.                                           | 123                    |
| CreatedDateTimeUTC | Data e hora em UTC em que a associação de dispositivo de usuário foi criada.                               | 23/11/2016 12:00:00 AM |
| IsDeleted          | Indica que o usuário cancelou o registro desse dispositivo e que a associação não está mais em vigor. | verdadeiro                   |
| EndedDateTimeUTC   | Data e hora em UTC em que IsDeleted foi alterado para **True**.                                         | 06/23/2017 12:00:00 AM |