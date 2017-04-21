---
title: "Configurar políticas de proteção de aplicativo durante uma migração do Intune | Microsoft Docs"
description: "A finalidade deste artigo é mostrar as etapas necessárias para configurar políticas de proteção de aplicativo durante uma migração do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: f30ab8799b2e049372139c7f9ee7213547736bb0
ms.lasthandoff: 04/14/2017


---

# <a name="phase-1-configure-app-protection-policies-optional"></a>Fase 1: Configurar políticas de proteção de aplicativo (opcional)

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

As políticas de proteção de aplicativo permitem que você criptografe aplicativos, defina um PIN quando o aplicativo for acessado, bloqueie a execução dos aplicativos em dispositivos desbloqueados ou modificados, além de muitas outras proteções. Se o telefone do usuário for perdido ou roubado, você poderá apagar remota e seletivamente os dados corporativos, deixando os dados pessoais intactos por meio da aplicação de políticas de proteção do aplicativo móvel.

As políticas de proteção de aplicativo aplicam a segurança no nível do aplicativo e não exigem o registro do dispositivo. Elas podem ser usadas com dispositivos registrados no Intune ou não. Além disso, pode ser usada com dispositivos registrados em um provedor de MDM de terceiros.

## <a name="app-protection-policies-with-lob-apps"></a>Políticas de proteção de aplicativo com aplicativos LOB

Também é possível estender as políticas de proteção de aplicativo móvel aos seus aplicativos LOB (linha de negócios) aproveitando o [SDK de Aplicativo do Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) ou a Microsoft Intune App Wrapping Tool para as plataformas [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) e [Android](https://www.microsoft.com/download/details.aspx?id=47267).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Como as políticas de proteção de aplicativo ajudam durante a migração?

A migração exige a remoção de dispositivos do provedor antigo de MDM e o registro deles no Intune. Planeje bem essa ação e estimule os usuários finais a deixarem o provedor antigo de MDM e a registrarem-se imediatamente no Intune. No entanto, durante a migração alguns usuários, cujos dispositivos não são gerenciados pelo provedor de MDM, podem atrasar a conclusão do processo de registro.

Esse período pode deixar sua organização mais vulnerável a roubos de dispositivo e perda de dados corporativos se o acesso aos recursos corporativos ainda for permitido, e/ou perda de produtividade do usuário se o acesso aos recursos corporativos for bloqueado.

O Intune pode oferecer proteção de dados corporativos durante a migração para que você ainda tenha cobertura de segurança para seus dados corporativos quando não houver gerenciamento no nível do dispositivo.

Quando você desabilita o acesso condicional no provedor antigo de MDM, os usuários ainda podem ser produtivos enquanto você os integra ao Intune.

## <a name="task-list-for-app-protection-policies"></a>Lista de tarefas para políticas de proteção de aplicativo

-   Tarefa 1: Saiba [como se preparar para configurar as políticas de proteção de aplicativo móvel](https://docs.microsoft.com/intune/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)

-   Tarefa 2: Saiba [como criar e implantar as políticas de proteção de aplicativo móvel](https://docs.microsoft.com/intune/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="next-steps"></a>Próximas etapas 

[Fase 1: Considerações especiais de migração](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

