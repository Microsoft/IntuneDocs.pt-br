---
title: "Criar perfil de dispositivo iOS ou macOS com o Microsoft Intune – Azure | Microsoft Docs"
description: "Adicione ou crie um perfil de dispositivo iOS ou macOS e, em seguida, defina as configurações de AirPrint, AirPlay, layout da tela inicial, notificações do aplicativo, dispositivo compartilhado, logon único e configurações de filtro de conteúdo da Web no Microsoft Intune"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3de7d1bccd57da1290987a714416373cbdd2b0d
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Adicionar configurações de recursos do dispositivo iOS ou macOS no Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Os recursos do dispositivo permitem controlar uma variedade de configurações e recursos nos dispositivos iOS e macOS, como:

- Configurações de AirPrint e AirPlay
- Layout da tela inicial
- Notificações de aplicativos
- Configuração de dispositivo compartilhado
- Configurar logon único
- Filtragem de conteúdo da Web

Este artigo mostra as noções básicas de como configurar perfis de recurso do dispositivo iOS. Em seguida, você poderá acessar artigos adicionais para definir configurações específicas da plataforma dos dispositivos.

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e, em seguida, selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo**, escolha **Perfis**e, em seguida, selecione **Criar perfil**.
4. Digite as seguintes propriedades:

  - **Nome**: insira um nome descritivo para o novo perfil
  - **Descrição**: (opcional mas recomendado) insira uma descrição para o perfil
  - **Plataforma**: selecione o tipo de plataforma:
    - **iOS**
    - **macOS**
  - **Tipo de perfil**: selecione os **Recursos do dispositivo**
  - **Configurações**: as configurações dependem da plataforma escolhida. Os artigos a seguir descrevem as configurações de cada tipo de perfil:

    - [Configurações do AirPrint para iOS e MacOS](air-print-settings-ios-macos.md)
    - [Configurações do AirPlay para iOS](airplay-settings-ios.md)
    - [Configurações do layout da Tela inicial para iOS](home-screen-settings-ios.md)
    - [Configurações de notificação de aplicativos para iOS](app-notification-settings-ios.md)
    - [Definições de configuração de dispositivo compartilhado para iOS](shared-device-settings-ios.md)
    - [Configure o Intune para Logon Único de dispositivo iOS](sso-ios.md)
    - [Configurações de filtro de conteúdo da Web para iOS](web-content-filter-settings-ios.md)

5. Quando terminar, selecione **OK** e escolha **Criar** para salvar suas alterações.

O perfil será criado e aparecerá na lista.

## <a name="next-step"></a>Próxima etapa

Para atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).