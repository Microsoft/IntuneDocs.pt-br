---
title: "Remover um usuário de um dispositivo iOS com o Microsoft Intune"
titlesuffix: 
description: "Saiba como remover um usuário de um dispositivo iOS compartilhado com o Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce1b6b439c287b67a7c9e776edf136e78e5ecf5b
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Remover um usuário de um dispositivo iOS compartilhado


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação **Remover Usuário** exclui um usuário escolhido do cache local em um dispositivo iPad compartilhado que foi configurado para gerenciar o aplicativo Classroom para iOS com um [perfil de educação do iOS](education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores (apenas em dispositivos iPad compartilhados)
- macOS – Sem suporte
- Android – Sem suporte

## <a name="how-to-remove-a-user"></a>Como remover um usuário

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo iOS.
6. Na folha desse dispositivo, escolha **Usuários**.
7. Na lista, clique com botão direito do mouse do usuário que você deseja remover e, em seguida, escolha **Remover usuário**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos**, escolha **Ações do dispositivo**.
