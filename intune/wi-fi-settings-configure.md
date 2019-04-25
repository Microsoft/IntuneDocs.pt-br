---
title: Criar um perfil Wi-Fi para dispositivos no Microsoft Intune — Azure | Microsoft Docs
description: Confira as etapas para criar um perfil de configuração de dispositivo Wi-Fi no Microsoft Intune. Crie perfis para Android, Android Enterprise, Android Kiosk, iOS, macOS, Windows 10 e posteriores e Windows Holographic for Business. Use esses perfis para criar uma conexão Wi-Fi para usar certificados, escolher um tipo de EAP, selecionar um método de autenticação, ativar um proxy e muito mais.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/16/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 708c4d4572d84f17a711ac6deb16c02d82b9eea7
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61514966"
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
- macOS (Mac OS X 10.11 e posteriores)
- Windows 10 e posteriores, Windows 10 Mobile e Windows Holographic for Business

> [!NOTE]
> Para dispositivos que executam o Windows 8.1, você pode importar uma configuração de Wi-Fi previamente exportada de outro dispositivo.

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** e selecione **Microsoft Intune**. 
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição** para o perfil Wi-Fi.
4. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo para aplicar as configurações de Wi-Fi. Suas opções:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**

5. Em **Tipo de perfil**, escolha **Wi-Fi**.

    - Para dispositivos **Android Enterprise** executados como um quiosque, você pode escolher **Somente proprietário do dispositivo** > **Wi-Fi**.
    - Para **Windows 8.1 e posteriores**, você pode escolher **Importação de Wi-Fi**. Essa opção possibilita importar as configurações de Wi-Fi como um arquivo XML previamente exportado de um dispositivo diferente.

6. Algumas das configurações de Wi-Fi são diferentes para cada plataforma. Para ver as configurações de uma plataforma específica, escolha:

    - [Android](wi-fi-settings-android.md)
    - [Android Enterprise e Kiosk](wi-fi-settings-android-enterprise.md)
    - [iOS](wi-fi-settings-ios.md)
    - [macOS](wi-fi-settings-macos.md)
    - [Windows 10 e posterior](wi-fi-settings-windows.md)
    - [Windows 8.1 e posteriores](wi-fi-settings-import-windows-8-1.md), incluindo o Windows Holographic for Business

    A maioria das plataformas tem as configurações **Básico** e **Enterprise** . **Básico** inclui recursos como o nome da rede e o SSID. **Enterprise** permite fornecer informações mais avançadas, como o EAP (Extensible Authentication Protocol).

7. Quando terminar de adicionar suas configurações de Wi-Fi, selecione **Criar perfil** > **Criar** para adicionar o perfil de configuração. O perfil é criado e exibido na lista de perfis (**Configuração do dispositivo** > **Perfis**).

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada. Em seguida, [atribua esse perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).
