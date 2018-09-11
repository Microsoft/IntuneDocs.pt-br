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
ms.openlocfilehash: 23619048faca4cdf9d64b15b0db7c09cb958a082
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43314033"
---
# <a name="special-migration-considerations"></a>Considerações especiais sobre a migração

Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM existente.

## <a name="wipe-for-apples-device-enrollment-program-dep"></a>Apagamento para o DEP (Programa de registro de dispositivos) da Apple

O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final. Para manter os recursos de gerenciamento avançados do DEP, o dispositivo precisa ser retornado ao estado de configuração inicial (novo) por meio de um apagamento para ser registrado no Intune.

Para continuar usando o DEP para gerenciar os dispositivos no Intune, [configure o registro de dispositivo iOS com o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Próximas etapas

[Fase 2: campanha de migração](migration-guide-campaign.md)
