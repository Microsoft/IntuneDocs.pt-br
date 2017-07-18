---
title: "Configurar políticas de proteção de aplicativo durante uma migração do Intune"
description: "Este artigo fornece as etapas necessárias para configurar políticas de proteção de aplicativo durante uma migração do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: c58ce51731b476cfca71851430297aff3edc5cd6
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="configure-app-protection-policies-optional"></a>Configurar políticas de proteção de aplicativo (opcional)


As políticas de proteção do aplicativo permitem a você:
* Criptografar aplicativos
* Definir um PIN quando o aplicativo é acessado
* Bloquear a execução de aplicativos em dispositivos desbloqueados ou modificados, além de muitas outras proteções.

Se o telefone do usuário for perdido ou roubado, você poderá apagar seletivamente os dados corporativos, deixando os dados pessoais intactos.

As políticas de proteção de aplicativo aplicam a segurança no nível do aplicativo e não exigem o registro do dispositivo. Você pode usá-las com dispositivos registrados no Intune ou não. Além disso, você pode aplicá-las a dispositivos registrados em um provedor de MDM de terceiros.

## <a name="app-protection-policies-with-lob-apps"></a>Políticas de proteção de aplicativo com aplicativos LOB

Também é possível estender as políticas de proteção de aplicativo móvel aos seus aplicativos LOB (linha de negócios) usando o [SDK de Aplicativo do Microsoft Intune](app-sdk-get-started.md) ou a Microsoft Intune App Wrapping Tool para as plataformas [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) e [Android](https://www.microsoft.com/download/details.aspx?id=47267).

## <a name="how-do-app-protection-policies-help-during-migration"></a>Como as políticas de proteção de aplicativo ajudam durante a migração?

Em uma migração, você deve remover dispositivos do provedor de MDM antigo e registrá-los no Intune. Planeje bem essa ação e estimule os usuários finais a deixarem o provedor antigo de MDM e a registrarem-se imediatamente no Intune. No entanto, durante a migração alguns usuários, cujos dispositivos não são gerenciados pelo provedor de MDM, podem atrasar a conclusão do processo de registro.

Esse período pode deixar sua organização mais vulnerável a roubos de dispositivo e perda de dados corporativos se o acesso aos recursos corporativos ainda for permitido. Ele também poderá levar à redução da produtividade do usuário se o acesso aos recursos corporativos for bloqueado.

O Intune pode oferecer proteção de dados corporativos durante a migração para que você ainda tenha cobertura de segurança para seus dados corporativos quando não houver gerenciamento no nível do dispositivo.

Quando você desabilita o acesso condicional no provedor antigo de MDM, os usuários ainda podem ser produtivos enquanto você os integra ao Intune.

## <a name="task-list-for-app-protection-policies"></a>Lista de tarefas para políticas de proteção de aplicativo

1. [Criar uma política de proteção de aplicativo](app-protection-policies.md#create-an-app-protection-policy)
2. [Implantar uma política](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a>Próximas etapas

[Considerações especiais de migração](migration-guide-considerations.md)
