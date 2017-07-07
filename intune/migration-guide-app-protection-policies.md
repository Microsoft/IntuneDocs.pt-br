---
title: "Configurar políticas de proteção de aplicativo durante uma migração do Intune"
description: "A finalidade deste artigo é mostrar as etapas necessárias para configurar políticas de proteção de aplicativo durante uma migração do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbe2c794a68ab37722c56448560a3c64f6087969
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="configure-app-protection-policies-optional"></a>Configurar políticas de proteção de aplicativo (opcional)

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

As políticas de proteção de aplicativo permitem que você criptografe aplicativos, defina um PIN quando o aplicativo for acessado, bloqueie a execução dos aplicativos em dispositivos desbloqueados ou modificados, além de muitas outras proteções. Se o telefone do usuário for perdido ou roubado, você poderá apagar remota e seletivamente os dados corporativos, deixando os dados pessoais intactos por meio da aplicação de políticas de proteção do aplicativo móvel.

As políticas de proteção de aplicativo aplicam a segurança no nível do aplicativo e não exigem o registro do dispositivo. Elas podem ser usadas com dispositivos registrados no Intune ou não. Além disso, pode ser usada com dispositivos registrados em um provedor de MDM de terceiros.

## <a name="app-protection-policies-with-lob-apps"></a>Políticas de proteção de aplicativo com aplicativos LOB

Também é possível estender as políticas de proteção de aplicativo móvel aos seus aplicativos LOB (linha de negócios) aproveitando o [SDK de Aplicativo do Microsoft Intune](/intune-classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management) ou a Microsoft Intune App Wrapping Tool para as plataformas [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) e [Android](https://www.microsoft.com/download/details.aspx?id=47267).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Como as políticas de proteção de aplicativo ajudam durante a migração?

A migração exige a remoção de dispositivos do provedor antigo de MDM e o registro deles no Intune. Planeje bem essa ação e estimule os usuários finais a deixarem o provedor antigo de MDM e a registrarem-se imediatamente no Intune. No entanto, durante a migração alguns usuários, cujos dispositivos não são gerenciados pelo provedor de MDM, podem atrasar a conclusão do processo de registro.

Esse período pode deixar sua organização mais vulnerável a roubos de dispositivo e perda de dados corporativos se o acesso aos recursos corporativos ainda for permitido, e/ou perda de produtividade do usuário se o acesso aos recursos corporativos for bloqueado.

O Intune pode oferecer proteção de dados corporativos durante a migração para que você ainda tenha cobertura de segurança para seus dados corporativos quando não houver gerenciamento no nível do dispositivo.

Quando você desabilita o acesso condicional no provedor antigo de MDM, os usuários ainda podem ser produtivos enquanto você os integra ao Intune.

## <a name="task-list-for-app-protection-policies"></a>Lista de tarefas para políticas de proteção de aplicativo

1. [Criar uma política de proteção de aplicativo](/intune/app-protection-policies#create-an-app-protection-policy)
2. [Implantar uma política](/intune/app-protection-policies#deploy-a-policy-to-users)


## <a name="next-steps"></a>Próximas etapas 

[Considerações especiais de migração](migration-guide-considerations.md)
