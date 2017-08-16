---
title: Sincronizar dispositivos com o Intune
titleSuffix: Intune on Azure
description: "Saiba como sincronizar dispositivos com o Intune para obter as políticas e ações mais recentes."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 870eb3bf255cda92952a908596485d7b53259fb4
ms.sourcegitcommit: ee7f69efe9f32a1d6bdeb1fab73d03dbfe1ae58c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Sincronize dispositivos com o Intune para obter as políticas e ações mais recentes


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Sincronizar** força o dispositivo selecionado a fazer check-in no Intune imediatamente. Quando um dispositivo faz check-in, ele recebe imediatamente as ações pendentes ou políticas que foram atribuídas a ele.  Esta ação pode ajudá-lo a validar imediatamente e solucionar problemas das políticas que você atribuiu, sem aguardar o próximo check-in agendado.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Com suporte
- Windows Phone – Com suporte
- iOS – Com suporte
- macOS – Com suporte
- Android – Com suporte

## <a name="how-to-sync-a-device"></a>Como sincronizar um dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota **Sincronizar**.
7. Escolha **Sim** para confirmar a ação.

## <a name="next-steps"></a>Próximas etapas

Escolha **Ações de Dispositivo** para ver o status da ação de sincronização. 
