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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f418149d8640f7fd663f0bbf4b3151ffb428a75e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728475"
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

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. No painel **Intune**, selecione **Dispositivos**.
4. No painel **Dispositivos**, selecione **Todos os dispositivos**.
5. Na lista de dispositivos que você gerencia, selecione um dispositivo iOS.
6. No painel do dispositivo, selecione **Usuários**.
7. Na lista, clique com o botão direito do mouse no usuário que você deseja remover e, em seguida, selecione **Remover usuário**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status da ação **Remover usuário**, selecione (**Dispositivos** > **Ações do dispositivo**).
