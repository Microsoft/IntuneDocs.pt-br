---
title: Criar perfil de dispositivo iOS ou macOS com o Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de dispositivo iOS ou macOS e, em seguida, defina as configurações de AirPrint, de layout da tela inicial, de notificações do aplicativo, de dispositivo compartilhado, de logon único e de filtro de conteúdo da Web no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 4542a65afa87668702620a1b50443c9844692a87
ms.sourcegitcommit: e08a26558174be3ea8f3d20646e577f1493ea21a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54831268"
---
# <a name="add-ios-or-macos-device-feature-settings-in-intune"></a>Adicionar configurações de recursos do dispositivo iOS ou macOS no Intune

O Intune inclui muitos recursos e configurações que ajudam os administradores a controlarem dispositivos iOS e macOS. Por exemplo, os administradores podem:

- Permitir aos usuários acesso a impressoras AirPrint em sua rede
- Adicionar aplicativos e pastas à tela inicial, incluindo a adição de novas páginas
- Escolher se, e como, as notificações de aplicativo são exibidas
- Configurar a tela de bloqueio para mostrar uma mensagem ou a marca do ativo, especialmente para dispositivos compartilhados
- Conceder aos usuários uma experiência de logon único segura para compartilhar credenciais entre aplicativos
- Filtrar sites que usem linguagem adulta e permitir ou bloquear sites específicos

Esses recursos estão disponíveis no Intune e podem ser configurados pelo administrador. O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, você pode enviar por push ou implantar o perfil para dispositivos iOS e macOS em sua organização.

Este artigo mostra como criar um perfil de configuração de dispositivos. Você também pode ver todas as configurações disponíveis para dispositivos [iOS](ios-device-features-settings.md) e [macOS](macos-device-features-settings.md).

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: insira um nome descritivo para o novo perfil.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Selecione sua plataforma:
        - **iOS**
        - **macOS**
    - **Tipo de perfil**: Selecione **Recursos do dispositivo**.
    - **Configurações**: Insira as configurações que você deseja definir. Para obter uma lista de todas as configurações e o que elas fazem, confira:

        - [iOS](ios-device-features-settings.md)
        - [macOS](macos-device-features-settings.md)

4. Quando terminar, selecione **OK** e escolha **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista. [Atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele está pronto para ser atribuído. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Exiba todas as configurações de recurso de dispositivo para dispositivos [iOS](ios-device-features-settings.md) e [macOS](macos-device-features-settings.md).