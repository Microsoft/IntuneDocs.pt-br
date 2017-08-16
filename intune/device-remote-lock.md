---
title: Bloquear dispositivos gerenciados remotamente com o Intune
titleSuffix: Intune on Azure
description: Saiba como usar o Intune para bloquear os dispositivos gerenciados remotamente.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab885fa6f693e65295986c182353f4918024281f
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Bloquear dispositivos gerenciados remotamente com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O dispositivo **Bloqueio remoto** bloqueia o dispositivo selecionado. O proprietário do dispositivo deve usar a senha para desbloqueá-lo. Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Com suporte no Windows 8.1 e versões posteriores
- iOS – Com suporte
- macOS – Sem suporte
- Android – Com suporte

## <a name="how-to-remote-lock-a-device"></a>Como bloquear um dispositivo remotamente

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Bloqueio remoto**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
