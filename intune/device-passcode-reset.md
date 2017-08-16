---
title: Redefinir a senha de um dispositivo com o Intune
titleSuffix: Intune on Azure
description: Saiba como redefinir a senha nos dispositivos gerenciados com o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 30fac990d8b4a0a088180598e7787e23b1f708b7
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2017
---
# <a name="reset-the-passcode-on-intune-managed-devices"></a>Redefinir a senha em dispositivos gerenciados pelo Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação **Redefinir senha** gera uma nova senha para o dispositivo, que será exibida na folha <*nome do dispositivo*> **Visão Geral**.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Com suporte do Windows Phone 8.1 à Atualização do Windows 10 para Criadores não ingressada no Azure AD, Atualização do Windows 10 para Criadores e versões posteriores
- iOS – Com suporte
- macOS – Sem suporte
- Android – Com suporte em versões anteriores ao Android 7. Não há suporte para o Android for Work.

## <a name="how-to-reset-a-passcode"></a>Como redefinir uma senha

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Redefinir senha**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
