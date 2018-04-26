---
title: Redefinir senhas de dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Remova ou redefina a senha usando a ação remover senha nos dispositivos que você gerencia ou monitora com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/29/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 905c51dcbc5b7731be207c25ffd368b339dbec57
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Redefinir ou remover uma senha de dispositivo no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Para criar uma nova senha para um dispositivo, use a ação **Remover senha**.

## <a name="supported-platforms"></a>Plataformas com Suporte

- Dispositivos Android registrados com um perfil de Trabalho, versão 7.0 e posteriores
- Dispositivos Android na versão 6.0 ou anterior
- iOS 
     
## <a name="unsupported-platforms"></a>Plataformas sem suporte

- Dispositivos Android registrados com um perfil de Trabalho, versão 6.0 e anteriores
- Dispositivos Android na versão 7.0 ou posterior
- macOS
- Windows

## <a name="reset-a-passcode"></a>Redefinir uma senha

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e, em seguida, selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, selecione um dispositivo e escolha **...Mais**. Em seguida, escolha a ação remota de dispositivo **Remover senha**.

## <a name="resetting-android-for-work-passcodes"></a>Redefinindo senhas do Android for Work

Dispositivos Android for Work compatíveis recebem uma nova senha de desbloqueio de dispositivo ou um desafio de perfil gerenciado para o usuário final. Para dispositivos no Android 7.0 ou posterior com perfis de Trabalho, os usuários finais recebem notificações para ativar o token de redefinição de senha imediatamente após o registro ser concluído. A notificação será exibida se a senha de um perfil de trabalho for obrigatória e estiver definida. Depois que a senha for inserida, a notificação será descartada.

## <a name="resetting-ios-passcodes"></a>Redefinir senhas do iOS

Senhas são removidas dos dispositivos iOS. Se houver uma política de conformidade de senha definida, o dispositivo solicitará que o usuário defina uma nova senha nas Configurações. 

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação realizada, em **Dispositivos**, selecione **Ações do dispositivo**.
