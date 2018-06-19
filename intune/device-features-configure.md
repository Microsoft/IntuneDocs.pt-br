---
title: Criar perfil de dispositivo iOS ou macOS com o Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de dispositivo iOS ou macOS e, em seguida, defina as configurações de AirPrint, de AirPlay, de layout da tela inicial, de notificações do aplicativo, de dispositivo compartilhado, de logon único e de filtro de conteúdo da Web no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d823a7f8d3478c0ff6c0049a6bbaa76bb4247479
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31022026"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Adicionar configurações de recursos do dispositivo iOS ou macOS no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Os recursos do dispositivo permitem controlar uma variedade de configurações e recursos nos dispositivos iOS e macOS, como:

- Configurações de AirPrint e AirPlay
- Layout da tela inicial
- Notificações de aplicativos
- Configuração de dispositivo compartilhado
- Configuração de logon único
- Filtragem de conteúdo da Web

Este artigo mostra as noções básicas de como configurar perfis de recurso do dispositivo iOS. Em seguida, você poderá acessar artigos adicionais para definir configurações específicas da plataforma dos dispositivos.

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e, em seguida, selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Digite as seguintes propriedades:

   - **Nome**: insira um nome descritivo para o novo perfil.
   - **Descrição:** insira uma descrição para o perfil. (Isso é opcional, mas recomendado.)
   - **Plataforma**: selecione seu tipo de plataforma:
     - **iOS**
     - **macOS**
   - **Tipo de perfil**: selecione os **Recursos do dispositivo**.
   - **Configurações**: as configurações dependem da plataforma escolhida. Os artigos a seguir descrevem as configurações de cada tipo de perfil:

     - [Configurações do AirPrint para iOS e MacOS](air-print-settings-ios-macos.md)
     - [Configurações do AirPlay para iOS](airplay-settings-ios.md)
     - [Configurações do layout da Tela inicial para iOS](home-screen-settings-ios.md)
     - [Configurações de notificação de aplicativos para iOS](app-notification-settings-ios.md)
     - [Definições de configuração de dispositivo compartilhado para iOS](shared-device-settings-ios.md)
     - [Configurar o Intune para logon único de dispositivo iOS](sso-ios.md)
     - [Configurações de filtro de conteúdo da Web para iOS](web-content-filter-settings-ios.md)

5. Quando terminar, selecione **OK** e escolha **Criar** para salvar suas alterações.

O perfil será criado e aparecerá na lista.

## <a name="next-step"></a>Próxima etapa

Para atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).