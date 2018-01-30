---
title: "Considerações especiais sobre a migração"
description: "Este artigo fornece considerações especiais de migração antes de iniciar uma campanha de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 86f3f7f2c8066e1b7b50dfc5931184c394d4f15b
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="special-migration-considerations"></a>Considerações especiais sobre a migração

Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM atual.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Redefinição de fábrica para o programa DEP (Programa de Registro de Dispositivo) da Apple

O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final. Para manter os recursos de gerenciamento avançados do DEP, o dispositivo deve retornar ao estado inicial (novo) por meio de uma redefinição de fábrica a fim de ser registrado no Intune.

Para continuar usando o DEP para gerenciar os dispositivos no Intune, [configure o registro de dispositivo iOS com o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Próximas etapas

[Fase 2: campanha de migração](migration-guide-campaign.md)
