---
title: Gerenciar dispositivos com o Intune
titleSuffix: Intune on Azure
description: "Saiba como ver os dispositivos gerenciados com o Intune e executar várias operações neles."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5d78b4a87eaa366b7bb00356c4b98d609620dcf3
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles. Para acessar a carga de trabalho:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Você pode exibir informações sobre dispositivos e executar as ações de dispositivo remoto listadas.

## <a name="available-device-actions"></a>Ações do dispositivo disponíveis
As ações disponíveis dependem da plataforma e da configuração do dispositivo.

- [Exibir inventário de dispositivo](device-inventory.md)
- Executar ações remotas de dispositivo:
    - [Remover os dados da empresa](devices-wipe.md#remove-company-data)
    - [Redefinição de fábrica](devices-wipe.md#factory-reset)
    - [Bloqueio remoto](device-remote-lock.md) 
    - [Redefinir senha](device-passcode-reset.md)
    - [Bypass do bloqueio de ativação](device-activation-lock-bypass.md) (somente iOS)
    - [Novo Início](device-fresh-start.md) (somente Windows)
    - [Modo perdido](device-lost-mode.md) (somente iOS)
    - [Localizar dispositivo](device-locate.md) (somente iOS)
    - [Reiniciar](device-restart.md) (somente Windows)
    - [Redefinir o PIN do Windows 10](device-windows-pin-reset.md)
    - [Controle remoto para Android](device-profile-android-teamviewer.md)
    - [Sincronizar dispositivo](device-sync.md)


## <a name="next-steps"></a>Próximas etapas

- Escolha **Ações do Dispositivo** para ver o status das ações executadas nos dispositivos gerenciados.
![Monitorar ações do dispositivo](./media/monitor-device-actions.png)
