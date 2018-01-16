---
title: "Remover um usuário de um dispositivo iOS com o Intune"
titlesuffix: Azure portal
description: "Saiba como remover um usuário de um dispositivo iOS compartilhado com o Intune.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b99e42318a5432f0ad27fb7d6dc2054220b3a0a
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2018
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a>Remover um usuário de um dispositivo iOS compartilhado com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação **Remover Usuário** exclui um usuário escolhido do cache local em um dispositivo iPad compartilhado que foi configurado para gerenciar o aplicativo Classroom para iOS com um [perfil de educação do iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores (apenas em dispositivos iPad compartilhados)
- macOS – Sem suporte
- Android – Sem suporte

## <a name="how-to-remove-a-user"></a>Como remover um usuário

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo iOS.
6. Na folha desse dispositivo, escolha **Usuários**.
7. Na lista, clique com botão direito do mouse do usuário que você deseja remover e, em seguida, escolha **Remover usuário**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
