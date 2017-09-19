---
title: Redefinir a senha de um dispositivo com o Intune
titlesuffix: Azure portal
description: Saiba como redefinir a senha nos dispositivos gerenciados com o Intune.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3defec3624944918d14b9c4527487c368c487dd6
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
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
