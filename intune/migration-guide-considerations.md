---
title: "Considerações especiais sobre a migração"
description: "A finalidade deste artigo é tecer considerações especiais sobre a migração antes de os clientes iniciarem uma campanha de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="special-migration-considerations"></a>Considerações especiais sobre a migração

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM atual.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Redefinição de fábrica para o programa DEP (Programa de Registro de Dispositivo) da Apple

O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final. Para manter os recursos de gerenciamento avançados do DEP, o dispositivo deve retornar ao estado inicial (novo) por meio da redefinição de fábrica a fim de ser registrado no Intune.

Para continuar usando o DEP para gerenciar os dispositivos no Intune, [configure o registro de dispositivo iOS com o Programa de registro de dispositivos](/intune/device-enrollment-program-enroll-ios).


## <a name="next-steps"></a>Próximas etapas 

[Fase 2: Campanha de migração](migration-guide-campaign.md)
