---
title: Considerações especiais sobre a migração
titlesuffix: Microsoft Intune
description: Este artigo fornece considerações especiais de migração antes de iniciar uma campanha de migração para o Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: bd59cf3a4764cc66d0e7d1f47e69c2ff93352387
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
ms.locfileid: "29925974"
---
# <a name="special-migration-considerations"></a>Considerações especiais sobre a migração

Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM existente.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Redefinição de fábrica para o programa DEP (Programa de Registro de Dispositivo) da Apple

O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final. Para manter os recursos de gerenciamento avançados do DEP, o dispositivo deve retornar ao estado inicial (novo) por meio de uma redefinição de fábrica a fim de ser registrado no Intune.

Para continuar usando o DEP para gerenciar os dispositivos no Intune, [configure o registro de dispositivo iOS com o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Próximas etapas

[Fase 2: campanha de migração](migration-guide-campaign.md)
