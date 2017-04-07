---
title: "Considerações especiais sobre a migração | Microsoft Docs"
description: "A finalidade deste artigo é tecer considerações especiais sobre a migração antes de os clientes iniciarem uma campanha de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 634e84312fa1a93eb85bf70e1593ca11359b72ff
ms.lasthandoff: 03/27/2017


---

# <a name="phase-1-special-migration-considerations"></a>Fase 1: Considerações especiais de migração

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM atual.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Redefinição de fábrica para o programa DEP (Programa de Registro de Dispositivo) da Apple

O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final. Para manter os recursos de gerenciamento avançados do DEP, o dispositivo deve retornar ao estado inicial (novo) por meio da redefinição de fábrica a fim de ser registrado no Intune.

Para continuar usando o DEP para gerenciar os dispositivos no Intune:

1.  Integre o [DEP no Intune](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)

2.  Acesse sua conta de DEP da Apple e [atribua novamente os números de série do dispositivo DEP](https://help.apple.com/deployment/business/#/tesf9562af26) de seu provedor de MDM atual no Intune.

3.  [Sincronize](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) sua conta DEP com o Intune

4.  [Crie e atribua](https://docs.microsoft.com/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) os perfis de registro de DEP apropriados aos números de série no Intune.

5.  Realize uma redefinição de fábrica nos dispositivos (remotamente por meio de seu provedor de MDM atual, ou manualmente em cada dispositivo)

6.  Distribua os dispositivos aos usuários finais.

## <a name="next-steps"></a>Próximas etapas 

[Fase 2: Campanha de migração](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

