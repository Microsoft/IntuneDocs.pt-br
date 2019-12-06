---
title: Criar um perfil Wi-Fi para dispositivos no Microsoft Intune — Azure | Microsoft Docs
description: Confira as etapas para criar um perfil de configuração de dispositivo Wi-Fi no Microsoft Intune. Crie perfis para Android, Android Enterprise, Android Kiosk, iOS, macOS, Windows 10 e posteriores e Windows Holographic for Business. Use esses perfis para criar uma conexão Wi-Fi para usar certificados, escolher um tipo de EAP, selecionar um método de autenticação, ativar um proxy e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7fe0bed94c66a1b82ed26bdbd43f68073223101e
ms.sourcegitcommit: 16a9109b4028589c17695d41271ca4fee8b1d697
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74540688"
---
# <a name="add-and-use-wi-fi-settings-on-your-devices-in-microsoft-intune"></a>Adicionar e usar configurações de Wi-Fi em seus dispositivos no Microsoft Intune

O Wi-Fi é uma rede sem fio usada por muitos dispositivos móveis para obter acesso à rede. O Microsoft Intune inclui configurações de Wi-Fi internas que podem ser implantadas em usuários e dispositivos em sua organização. Esse grupo de configurações é chamado de "perfil" e pode ser atribuído a usuários e grupos diferentes. Após a atribuição, seus usuários poderão acessar a rede Wi-Fi de sua organização sem ter que configurá-la por conta própria.

Por exemplo, você instala uma nova rede Wi-Fi chamada Wi-Fi da Contoso. Em seguida, deseja configurar todos os dispositivos iOS para se conectarem a essa rede. Este é o processo:

1. Crie um perfil de Wi-Fi que inclua as configurações para se conectar à rede sem fio Wi-Fi da Contoso.
2. Atribua o perfil a um grupo que inclua todos os usuários de dispositivos iOS.
3. Os usuários encontram a nova rede Wi-Fi da Contoso na lista de redes sem fio em seus dispositivos. Eles podem então se conectar à rede, usando o método de autenticação de sua escolha.

Este artigo lista as etapas para criar um perfil de Wi-Fi. Ele também inclui links que descrevem as diferentes configurações para cada plataforma.

## <a name="supported-device-platforms"></a>Plataformas de dispositivos com suporte

Perfis de Wi-Fi dão suporte às seguintes plataformas de dispositivo:

- Android 4 e posterior
- Android Enterprise e Kiosk
- iOS 8.0 e posterior
- macOS X 10.11 e mais recente
- Windows 10 e posteriores, Windows 10 Mobile e Windows Holographic for Business

> [!NOTE]
> Para dispositivos que executam o Windows 8.1, você pode importar uma configuração de Wi-Fi previamente exportada de outro dispositivo.

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um bom nome de perfil seria **Perfil Wi-Fi para toda a empresa**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:

      - **Android**
      - **Android Enterprise**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows 8.1 e posterior**
      - **Windows 10 e posterior**

    - **Tipo de perfil**: Selecione **Wi-Fi**.

      > [!TIP]
      >
      > - Para dispositivos **Android Enterprise** executados como um dispositivo dedicado (quiosque), você pode escolher **Somente proprietário do dispositivo** > **Wi-Fi**.
      > - Para **Windows 8.1 e posteriores**, você pode escolher **Importação de Wi-Fi**. Essa opção possibilita importar as configurações de Wi-Fi como um arquivo XML previamente exportado de um dispositivo diferente.

4. Algumas das configurações de Wi-Fi são diferentes para cada plataforma. Para ver as configurações de uma plataforma específica, escolha uma plataforma:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise](wi-fi-settings-android-enterprise.md), inclusive dispositivos dedicados
    - [iOS/iPadOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 e posterior](wi-fi-settings-windows.md)
    - [Windows 8.1 e posteriores](wi-fi-settings-import-windows-8-1.md), incluindo o Windows Holographic for Business

5. Quando concluir, selecione **Criar perfil** > **Criar**.

O perfil é criado e exibido na lista de perfis (**Configuração do dispositivo** > **Perfis**).

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

[Solucionar problemas nos perfis de Wi-Fi no Intune](troubleshoot-wi-fi-profiles.md).
