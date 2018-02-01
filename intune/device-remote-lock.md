---
title: Bloquear dispositivos gerenciados remotamente com o Intune
titlesuffix: Azure portal
description: Saiba como usar o Intune para bloquear os dispositivos gerenciados remotamente.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecd7fa03b35e91b5a77906858fb251348796704d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Bloquear dispositivos gerenciados remotamente com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O dispositivo **Bloqueio remoto** bloqueia o dispositivo selecionado. O proprietário do dispositivo deve usar a senha para desbloqueá-lo. Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.

## <a name="supported-platforms"></a>Plataformas com Suporte

O bloqueio remoto é compatível com as seguintes plataformas:

|Plataforma|Status de suporte|
|---|---|
|Android|Sim|
|iOS|Sim|
|macOS|Sim|
|Windows 10|Sim|
|Windows 10 Mobile|Sim|
|Windows Phone|Sim, para Windows Phone 8.1 e posterior|

> [!NOTE]  
> Para dispositivos macOS, você define um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

## <a name="how-to-remote-lock-a-device"></a>Como bloquear um dispositivo remotamente

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Bloqueio remoto**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
