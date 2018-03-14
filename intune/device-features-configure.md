---
title: "Definir as configurações de recurso de dispositivo do Microsoft Intune"
titleSuffix: 
description: Saiba como usar o Microsoft Intune para configurar recursos nos dispositivos gerenciados.
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6cd646976deb1599c4cbc9154b6f2a487029dd79
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
#<a name="configure-device-feature-settings-in-microsoft-intune"></a>Definir as configurações de recurso de dispositivo no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Os recursos de dispositivo permitem que você controle os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.

Use as informações neste artigo para aprender as noções básicas sobre a configuração de perfis de recurso de dispositivo e leia outros artigos para cada plataforma a fim de saber mais sobre as particularidades dos dispositivos.

## <a name="create-a-device-profile-containing-device-feature-settings"></a>Criar um perfil de dispositivo que contém as configurações de recurso de dispositivo

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na página **Intune**, escolha **Configuração do dispositivo**.
2. Na página **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
3. Na página de perfis, escolha **Criar perfil**.
4. Na página **Criar perfil**, insira um **Nome** e uma **Descrição** para o perfil de recursos do dispositivo.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações. No momento, é possível escolher uma das seguintes plataformas para os recursos do dispositivo:
    - **iOS**
    - **macOS**
6. Na lista suspensa **Tipo de perfil**, escolha **Recursos do dispositivo**. 
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos artigos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do AirPrint para iOS e MacOS](air-print-settings-ios-macos.md)
    - [Configurações do AirPlay para iOS](airplay-settings-ios.md)
    - [Configurações do layout da Tela inicial para iOS](home-screen-settings-ios.md)
    - [Configurações de notificação de aplicativos para iOS](app-notification-settings-ios.md)
    - [Definições de configuração de dispositivo compartilhado para iOS](shared-device-settings-ios.md)
    - [Configure o Intune para Logon Único de dispositivo iOS](sso-ios.md)
    - [Configurações de filtro de conteúdo da Web para iOS](web-content-filter-settings-ios.md)

8. Após terminar, selecione **OK**, volte para a página **Criar perfil** e escolha **Criar**.

O perfil é criado e exibido na página da lista de perfis.
## <a name="next-steps"></a>Próximas etapas

Se você quiser atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).



