---
title: "Como definir configurações de Wi-Fi do Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para definir as conexões Wi-Fi nos dispositivos gerenciados."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3378df904936def8737ca3b5b791feebdb95823b
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Como definir configurações de Wi-Fi no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Use os perfis de Wi-Fi do Microsoft Intune para atribuir configurações de rede sem fio para usuários e dispositivos na organização. Quando você atribui um perfil de Wi-Fi, os usuários terão acesso à rede Wi-Fi corporativa sem precisar configurá-lo por conta própria.

Por exemplo, você pode instalar uma nova rede Wi-Fi chamada Contoso Wi-Fi e configurar todos os dispositivos iOS para se conectarem a essa rede. Este é o processo:

1. Crie um perfil de Wi-Fi contendo as configurações necessárias para conectar à rede sem fio Contoso Wi-Fi.
2. Atribua o perfil a um grupo que contém todos os usuários de dispositivos iOS.
3. Os usuários encontram a nova rede Contoso Wi-Fi na lista de redes sem fio em seus dispositivos e podem facilmente se conectar a ela.

Perfis de Wi-Fi dão suporte às seguintes plataformas de dispositivo:

- Android 4 e posterior
- iOS 8.0 e posterior
- macOS (Mac OS X 10.9 e posterior)

Para dispositivos que executam o Windows 8.1, Windows 10 e Windows Mobile 10, você pode importar uma configuração de Wi-Fi previamente exportada de outro dispositivo.

Use as informações neste tópico para aprender as noções básicas sobre a configuração de um perfil de Wi-Fi e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Criar um perfil de dispositivo que contém configurações de Wi-Fi

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de Wi-Fi.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de Wi-Fi. No momento, é possível escolher uma das seguintes plataformas para as configurações de Wi-Fi:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows 8.1 e posterior (importar um perfil)**
6. Na lista suspensa de tipos de **Perfil**, escolha **Wi-Fi básico** ou **Wi-Fi empresarial**.
    >[!TIP]
    >Use **Wi-Fi básico** para fornecer recursos básicos como nome de rede e SSID. **Wi-Fi corporativa** permite que você forneça informações mais avançadas, como o protocolo EAP (Extensible Authentication Protocol) se sua rede Wi-Fi o utilizar. **Importação de Wi-Fi** (para Windows 8.1 e Windows 10) permite que você importe as configurações de Wi-Fi como um arquivo XML previamente exportado de um dispositivo diferente.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android](wi-fi-settings-android.md)
    - [Configurações do iOS](wi-fi-settings-ios.md)
    - [Configurações do macOS](wi-fi-settings-macos.md)
    - [Configurações do Windows Phone 8.1](wi-fi-settings-import-windows-8-1.md)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).


