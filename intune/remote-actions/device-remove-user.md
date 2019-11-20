---
title: Remover um usuário de um dispositivo iOS com o Microsoft Intune
titleSuffix: ''
description: Saiba como remover um usuário de um dispositivo iOS compartilhado com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 772cdbe203b0489a9b2312a1cc10ea1b3182b35d
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73713155"
---
# <a name="remove-a-user-from-a-shared-ios-device"></a>Remover um usuário de um dispositivo iOS compartilhado


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A ação **Remover usuário** exclui um usuário escolhido do cache local em um dispositivo iPad compartilhado. O dispositivo iPad deve ser configurado para gerenciar o aplicativo Sala de aula do iOS usando um [perfil de educação iOS](../fundamentals/education-settings-configure-ios.md). 

## <a name="supported-platforms"></a>Plataformas com Suporte

- Windows – Sem suporte
- Windows Phone – Sem suporte
- iOS – Com suporte no iOS 9.3 e versões posteriores (apenas em dispositivos iPad compartilhados)
- macOS – Sem suporte
- Android – Sem suporte

## <a name="remove-a-user"></a>Remover um usuário

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Todos os dispositivos**.
3. Na lista de dispositivos que você gerencia, selecione um dispositivo iOS.
4. No painel do dispositivo, selecione **Usuários**.
5. Na lista, clique com o botão direito do mouse no usuário que você deseja remover e, em seguida, selecione **Remover usuário**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status da ação **Remover usuário**, selecione (**Dispositivos** > **Ações do dispositivo**).
