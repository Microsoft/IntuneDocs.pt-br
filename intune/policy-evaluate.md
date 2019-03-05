---
title: Descobrir quantos usuários são afetados por uma política
titlesuffix: Microsoft Intune
description: Descobrir quantos usuários são afetados por uma política
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/09/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 38e8a2e2-2329-11e8-b467-0ed5f89f718b
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12e770a549d300b10000fa83ab68a0b6f3393b71
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238346"
---
# <a name="evaluate-how-many-users-are-targeted-by-a-policy"></a>Avaliar quantos usuários são afetados por uma política
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Você pode usar o botão **Avaliar** para localizar quantos usuários são afetados por uma política de conformidade ou de configuração do dispositivo. Esse recurso calcula somente os usuários, não os dispositivos.

1.  No [Intune no Portal do Azure](https://aka.ms/intuneportal), escolha **Conformidade do dispositivo** ou **Configuração do dispositivo** e, em seguida, **Políticas**.
2.  Escolha uma das políticas ou criar uma nova e escolha **Atribuições**.
3.  Escolha **Avaliar**. Uma mensagem é exibida mostrando quantos usuários essa política afeta.

Se o botão **Avaliar** botão estiver desabilitado, verifique se a política foi atribuída a um ou mais grupos.

