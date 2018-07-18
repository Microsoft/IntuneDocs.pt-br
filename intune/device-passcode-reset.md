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
ms.openlocfilehash: a233c62b76901d9bad00aa6d8b2a8a4dd45dea96
ms.sourcegitcommit: 024cce10a99b12a13f32d3995b69c290743cafb8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2018
ms.locfileid: "39039294"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Redefinir ou remover uma senha de dispositivo no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Para criar uma nova senha para um dispositivo, use a ação **Remover senha**. Essa ação solicita uma redefinição de PIN apenas para o perfil de trabalho. Redefinições de PIN não são compatíveis com perfis de trabalho Android.

## <a name="work-profile-pin-reset-supported-platforms"></a>Plataformas compatíveis de redefinição de PIN do perfil de trabalho

- Dispositivos Android registrados com um perfil de trabalho, versão 8.0 e posteriores 
- Dispositivos Android na versão 6.0 ou anterior
- Dispositivos de quiosque Android Enterprise
- iOS 
     
## <a name="unsupported-platforms"></a>Plataformas sem suporte

- Dispositivos Android registrados com um perfil de Trabalho, versão 7.0 e anteriores
- Dispositivos Android na versão 7.0 ou posterior
- macOS
- Windows

## <a name="reset-a-passcode"></a>Redefinir uma senha

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e, em seguida, selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
4. Na lista de dispositivos que você gerencia, selecione um dispositivo e escolha **...Mais**. Em seguida, escolha a ação remota de dispositivo **Remover senha**.

## <a name="resetting-android-work-profile-passcodes"></a>Redefinindo senhas de perfil de trabalho Android

Os dispositivos de perfil de trabalho Android com suporte recebem uma nova senha de desbloqueio ou um novo desafio de perfil gerenciado para o usuário final. 

Para dispositivos de perfil de trabalho Android 8.0, os usuários finais são notificados para ativar a redefinição de senha logo após a conclusão do registro. A notificação será exibida se a senha de um perfil de trabalho for obrigatória e estiver definida. Depois que a senha for inserida, a notificação será descartada.

## <a name="resetting-ios-passcodes"></a>Redefinir senhas do iOS

Senhas são removidas dos dispositivos iOS. Quando há um conjunto de políticas de conformidade de senha, o dispositivo solicita que o usuário defina uma nova senha em Configurações. 

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação realizada, em **Dispositivos**, selecione **Ações do dispositivo**.
