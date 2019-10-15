---
title: Configurações de dispositivo compartilhado do Windows Holographic for Business – Microsoft Intune – Azure | Microsoft Docs
description: Adicione e use o Windows Holographic for Business para configurar dispositivos que são compartilhados ou usados por vários usuários no Microsoft Intune. Veja uma lista das configurações de Gerenciamento de Contas e o que elas fazem nos dispositivos, incluindo o Microsoft HoloLens.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 84a4db5639a03720b03da665c9df09fbc39d9df5
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71734317"
---
# <a name="windows-holographic-for-business-settings-to-manage-shared-devices-using-intune"></a>Configurações do Windows Holographic for Business para gerenciar dispositivos compartilhados usando o Intune

Os dispositivos Windows Holographic for Business, como o Microsoft HoloLens, podem ser usados por vários usuários. Os dispositivos que têm vários usuários são chamados de dispositivos compartilhados e são uma parte das soluções de MDM (gerenciamento de dispositivo móvel).

Usando o Microsoft Intune, os usuários podem entrar nesses dispositivos compartilhados com uma conta Convidado. Conforme eles usam o dispositivo, eles só obtém acesso aos recursos que você permite.

Este artigo lista e descreve as configurações usadas em um perfil de configuração do dispositivo do Windows Holographic for Business. Quando o perfil é criado no Intune, em seguida, você implanta ou atribui o perfil a grupos de dispositivos em sua organização. Você também pode atribuir esse perfil a um grupo de dispositivos com tipos de dispositivo e versões de sistema operacional mistas.

Para obter mais informações sobre este recurso no Intune, confira [Controlar o acesso, contas e recursos de energia em um computador compartilhado ou em dispositivos multiusuário](shared-user-device-settings.md). Para obter mais informações sobre o CSP do Windows, confira [CSP de AccountManagement](https://docs.microsoft.com/windows/client-management/mdm/accountmanagement-csp).

## <a name="before-your-begin"></a>Antes de começar

[Crie o perfil](shared-user-device-settings.md).

## <a name="shared-multi-user-device-settings"></a>Configurações de dispositivo multiusuário compartilhado

> [!NOTE]
> Os dispositivos que executam o Windows Holographic for Business, incluindo o Microsoft HoloLens, só dão suporte às configurações de **Gerenciamento de contas**. Se você definir uma das outras configurações mostradas no Intune, incluindo **Modo de computador compartilhado**, ela não afetará esses dispositivos.

- **Gerenciamento de conta**: definido para **Habilitar** para excluir automaticamente as contas locais criadas por convidados e as contas do AD e do Azure AD. Quando um usuário se desconecta do dispositivo ou quando a manutenção do sistema é executada, essas contas são excluídas. Quando essa opção estiver habilitada, também defina:
  - **Exclusão da Conta**: escolha quando as contas são excluídas: **no limite de espaço de armazenamento**, **no limite de espaço de armazenamento e no limite inativo** ou **imediatamente depois do logoff**. Insira também:
    - **Iniciar limite de exclusão (%)** : insira um percentual (0 a 100) de espaço em disco. Quando o espaço total de disco/armazenamento fica abaixo do valor inserido, as contas armazenadas em cache são excluídas. Ele exclui continuamente as contas para recuperar o espaço em disco. As contas que estão inativas por mais tempo são excluídas primeiro.
    - **Parar limite de exclusão (%)** : insira um percentual (0 a 100) de espaço em disco. Quando o espaço total de disco/armazenamento atende ao valor inserido, a exclusão é interrompida.

  Defina essa opção como **Desabilitar** para manter as contas locais, do AD e do Azure AD criadas por convidados.

  > [!NOTE]
  > Os dispositivos Microsoft HoloLens só dão suporte às configurações de **Gerenciamento de contas**.

## <a name="next-steps"></a>Próximas etapas

- [Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).
- Confira as configurações do [Windows 10 e mais recente](shared-user-device-settings-windows.md).