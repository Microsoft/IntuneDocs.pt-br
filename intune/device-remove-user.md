---
title: Remover um usuário de um dispositivo iOS com o Microsoft Intune
titlesuffix: ''
description: Saiba como remover um usuário de um dispositivo iOS compartilhado com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67a5f60e0877ebc8994ed7d3191a81f51d19c40a
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31020768"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Remover um usuário de um dispositivo iOS compartilhado


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação **Remover usuário** exclui um usuário escolhido do cache local em um dispositivo iPad compartilhado. O dispositivo iPad deve ser configurado para gerenciar o aplicativo Sala de aula do iOS usando um [perfil de educação iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores (apenas em dispositivos iPad compartilhados)
- macOS – Sem suporte
- Android – Sem suporte

## <a name="remove-a-user"></a>Remover um usuário

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, selecione **Dispositivos**.
4. No painel **Dispositivos**, selecione **Todos os dispositivos**.
5. Na lista de dispositivos que você gerencia, selecione um dispositivo iOS.
6. No painel do dispositivo, selecione **Usuários**.
7. Na lista, clique com o botão direito do mouse no usuário que você deseja remover e, em seguida, selecione **Remover usuário**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status da ação **Remover usuário**, selecione (**Dispositivos** > **Ações do dispositivo**).
