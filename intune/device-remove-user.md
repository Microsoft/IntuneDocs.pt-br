---
title: "Remover um usuário de um dispositivo iOS com o Intune"
titlesuffix: Azure portal
description: "Saiba como remover um usuário de um dispositivo iOS compartilhado com o Intune.”"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f16d42406fa7961cc165adcbd1e7c4c7ab5d78b4
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
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
