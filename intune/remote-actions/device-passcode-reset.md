---
title: Redefinir senhas de dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Remova ou redefina a senha usando a ação remover senha nos dispositivos que você gerencia ou monitora com o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 09/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: cd6e58efa096c006780c17d991a9ea5da26099d4
ms.sourcegitcommit: 51591b862d97904291af7aa53a6eb341b11a761e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77415555"
---
# <a name="reset-or-remove-a-device-passcode-in-intune"></a>Redefinir ou remover uma senha de dispositivo no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este documento aborda a redefinição de senha no nível do dispositivo e do perfil corporativo em dispositivos Android Enterprise (anteriormente chamado de Android for Work ou AfW). É importante observar essa distinção, já que pode haver variação de requisitos para cada um. Uma redefinição de senha no nível do dispositivo redefine a senha para todo o dispositivo. Uma redefinição de senha no nível do perfil de trabalho redefine a senha somente para o perfil de trabalho do usuário em dispositivos Android Enterprise.

## <a name="supported-platforms-for-device-level-passcode-reset"></a>Plataformas compatíveis com a redefinição de senha no nível do dispositivo

| Plataforma | Compatível? |
| ---- | ---- |
| Dispositivos Android na versão 6.x ou anterior | Sim |
| Dispositivos Android Enterprise registrados como Proprietário do Dispositivo | Sim |
| Dispositivos iOS/iPadOS | Sim |
| Dispositivos iOS/iPadOS registrados com o Registro de Usuário | Não |
| Dispositivos Android registrados com um perfil corporativo | Não |
| Dispositivos Android na versão 7.0 ou posterior | Não |
| macOS | Não |
| Windows | Não |

Para dispositivos Android, isso significa que a redefinição de senha no nível do dispositivo só é compatível com dispositivos que executam as versões 6.x ou anterior, ou em dispositivos Android Enterprise em execução no modo de quiosque. Isso ocorre porque o Google removeu a compatibilidade com o recurso de redefinição de senha de um dispositivo Android 7 de dentro do aplicativo concedido pelo Administrador do Dispositivo e se aplica a todos os fornecedores de MDM.

## <a name="supported-platforms-for-android-enterprise-work-profile-passcode-reset"></a>Plataformas compatíveis com a redefinição de senha de perfil de trabalho do Android Enterprise

| Plataforma | Compatível? |
| ---- | ---- |
| Dispositivos Android Enterprise registrados com um perfil de trabalho e que executam versões 8.0 e posteriores | Sim |
| Dispositivos Android Enterprise registrados com um perfil de trabalho e que executam versões 7.0 e anteriores | Não |
| Dispositivos Android que executam versões 7.x e anteriores | Não |

Para criar uma nova senha de perfil de trabalho, use a ação de Redefinir senha. Essa ação solicita uma redefinição de senha e cria uma nova senha temporária somente para o perfil de trabalho. 

## <a name="reset-a-passcode"></a>Redefinir uma senha


1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) com qualquer uma das seguintes funções: Administrador Global do Azure Active Directory, Administrador de Serviço do Intune do Azure Active Directory, Operador de Helpdesk ou Administrador de Função.
2. Selecione **Dispositivos** e, em seguida, **Todos os dispositivos**.
3. Na lista de dispositivos que você gerencia, selecione um dispositivo e escolha **...Mais**. Em seguida, escolha a ação remota de dispositivo **Remover senha**.

## <a name="reset-android-work-profile-passcodes"></a>Redefinir senhas de perfil de trabalho do Android

Os dispositivos Android Enterprise compatíveis registrados com um perfil de trabalho recebem uma nova senha de desbloqueio do perfil gerenciado ou um desafio do perfil gerenciado para o usuário final.

Para dispositivos Android Enterprise que executam versões 8.x ou posteriores e registrados com um perfil de trabalho, os usuários finais serão notificados para ativar sua redefinição de senha logo após o registro ser concluído. A notificação será exibida se uma senha de perfil de trabalho for obrigatória e estiver definida. Depois que a senha for inserida, a notificação será descartada.


## <a name="remove-iosipados-passcodes"></a>Remover senhas do iOS/iPadOS

Em vez de redefinidas, as senhas são removidas dos dispositivos iOS/iPadOS. Se houver um conjunto de políticas de conformidade de senha, o dispositivo solicitará que o usuário defina uma nova senha em Configurações.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação realizada, em **Dispositivos**, selecione **Ações do dispositivo**.
