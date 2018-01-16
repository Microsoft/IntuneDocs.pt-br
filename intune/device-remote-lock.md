---
title: Bloquear dispositivos gerenciados remotamente com o Intune
titlesuffix: Azure portal
description: Saiba como usar o Intune para bloquear os dispositivos gerenciados remotamente.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 45d27b709ba8d4ff1d8fb4417a217ad008c19c36
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Bloquear dispositivos gerenciados remotamente com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O dispositivo **Bloqueio remoto** bloqueia o dispositivo selecionado. O proprietário do dispositivo deve usar a senha para desbloqueá-lo. Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Com suporte no Windows 8.1 e versões posteriores
- iOS – Com suporte
- macOS – Com suporte

    > [!Note]  
    > Defina um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.
- Android – Com suporte

## <a name="how-to-remote-lock-a-device"></a>Como bloquear um dispositivo remotamente

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Bloqueio remoto**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
