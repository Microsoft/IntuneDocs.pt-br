---
title: Gerenciar dispositivos com o Intune
titleSuffix: Intune on Azure
description: "Saiba como ver os dispositivos gerenciados com o Intune e executar várias operações neles."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/05/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f066e62e323fffb7c6954d83b2b55ee63f4be46
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2017
---
# <a name="what-is-microsoft-intune-device-management"></a>O que é o gerenciamento de dispositivo do Microsoft Intune?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A carga de trabalho **Dispositivos** fornece ideias sobre os dispositivos gerenciados e permite que você execute tarefas remotas neles. Para acessar a carga de trabalho:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.

Agora é possível realizar as seguintes ações:

- [Exibir inventário de dispositivo](device-inventory.md)
- Executar ações remotas de dispositivo:
    - [Remover os dados da empresa](device-company-data-remove.md) 
    - [Redefinição de fábrica](device-factory-reset.md)
    - [Bloqueio remoto](device-remote-lock.md)
    - [Redefinir senha](device-passcode-reset.md)
    - [Bypass de Bloqueio de Ativação](device-activation-lock-bypass.md)
    - [Começar do zero](device-fresh-start.md)
    - [Modo perdido](device-lost-mode.md)
    - [Localizar dispositivo](device-locate.md)
    - [Reiniciar](device-restart.md)
    - [Redefinir o PIN do Windows 10](device-windows-pin-reset.md)
    - [Controle remoto para Android](device-profile-android-teamviewer.md)


## <a name="support-for-each-device-action"></a>Suporte para cada ação de dispositivo

Use a tabela a seguir para entender as plataformas de dispositivo com suporte em cada ação.

|||||||
|-|-|-|-|-|-|
|Ação do dispositivo|Windows|Windows Phone|iOS|macOS|Android|
|**Remover os dados da empresa**|Sim|Sim|Sim|Sim|Sim|
|**Redefinição de fábrica**|Windows 8.1 e posterior (dispositivos não gerenciados por EAS)|Sim|Sim|Não|Não há suporte para o Android for Work|
|**Excluir**|Sim|Sim|Sim|Sim|Sim|
|**Bloqueio remoto**|Não|Windows Phone 8.1 e posterior|Sim|Não|Sim|
|**Redefinir senha**|Não|Windows Phone 8.1 para atualização do Windows 10 para Criadores não ingressado no Azure AD, Atualização do Windows 10 para Criadores e posterior – todos|Sim|Não|Anteriores ao Android 7, sem suporte para o Android for Work|
|**Nova senha** (para dispositivos Windows 10)|Não|Atualização do Windows 10 para Criadores e posterior (ingressado no Azure AD)|Não|Não|Não há suporte para o Android for Work|
|**Bypass de Bloqueio de Ativação**|Não|Não|Somente dispositivos corporativos|Não|Não|
|**Modo perdido**|Não|Não|iOS 9.3 e posterior, supervisionado e corporativo|Não|Não|
|**Localizar dispositivo**|Não|Não|Modo perdido do iOS 9.3 e posterior, supervisionado e corporativo|Não|Não|
|**Fazer logoff do usuário atual**|Não|Não|iOS 9.3 e posterior (somente dispositivos iPad compartilhados)|Não|Não|
|**Reiniciar**|Windows 8.1 e posterior|Windows Phone 8.1 e posterior|Não|Não|Não|
|**Começar do zero**|Atualização do Windows 10 para Criadores e posterior|Não|Não|Não|Não|
|**Nova sessão de Assistência Remota**|Não|Não|Não|Não|Sim|
|**Remover usuário**|Não|Não|iOS 9.3 e posterior (somente dispositivos iPad compartilhados)|Não|Não|

## <a name="next-steps"></a>Próximas etapas

- Escolha **Ações do Dispositivo** para ver o status das ações executadas nos dispositivos gerenciados. 
![Monitorar ações do dispositivo](./media/monitor-device-actions.png)