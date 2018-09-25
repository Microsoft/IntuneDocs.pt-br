---
title: Como definir configurações de Wi-Fi do Intune
titleSuffix: Microsoft Intune
description: Saiba como usar o Microsoft Intune para configurar conexões Wi-Fi nos dispositivos que você gerencia.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: df2e2f81008c6dedf5660a8a9eff4bf2cfe2ec6b
ms.sourcegitcommit: 77540295381a59918eb638ce9c1870209cf8af02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2018
ms.locfileid: "46505726"
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>Como definir configurações de Wi-Fi no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Use os perfis de Wi-Fi do Microsoft Intune para atribuir configurações de rede sem fio para usuários e dispositivos na organização. Quando você atribui um perfil de Wi-Fi, os usuários têm acesso à rede Wi-Fi corporativa sem precisar configurá-lo por conta própria.

Por exemplo, você pode instalar uma nova rede Wi-Fi chamada Contoso Wi-Fi e configurar todos os dispositivos iOS para se conectarem a essa rede. Este é o processo:

1. Crie um perfil de Wi-Fi contendo as configurações necessárias para conectar à rede sem fio Contoso Wi-Fi.
2. Atribua o perfil a um grupo que contém todos os usuários de dispositivos iOS.
3. Os usuários encontram a nova rede Contoso Wi-Fi na lista de redes sem fio em seus dispositivos e podem facilmente se conectar a ela.

## <a name="supported-device-platforms"></a>Plataformas de dispositivos com suporte

Perfis de Wi-Fi dão suporte às seguintes plataformas de dispositivo:

- Android 4 e posterior
- Perfis de trabalho Android
- iOS 8.0 e posterior
- macOS (Mac OS X 10.11 e posteriores)

Para dispositivos que executam o Windows 8.1, Windows 10, Windows Mobile 10 e Windows Holographic for Business você pode importar uma configuração de Wi-Fi previamente exportada de outro dispositivo.

Use as informações neste tópico para aprender as noções básicas sobre a configuração de um perfil de Wi-Fi e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Criar um perfil de dispositivo que contém configurações de Wi-Fi

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No painel **Intune**, escolha **Configuração do dispositivo**.
2. No painel **Configuração do dispositivo**, na seção **Gerenciar**, escolha **Perfis**.
3. No painel de perfis, escolha **Criar perfil**.
4. No painel **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de Wi-Fi.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de Wi-Fi. No momento, é possível escolher uma das seguintes plataformas para as configurações de Wi-Fi:
    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**


6. Para dispositivos Android ou Apple, na lista suspensa **Tipo de WiFi**, escolha **Básica** ou **Corporativa**. Você pode usar a **Básica** para fornecer recursos básicos como o nome da rede e o SSID. A **Corporativa** permite que você forneça informações mais avançadas, como o protocolo EAP (Protocolo de Autenticação Extensível), caso sua rede Wi-Fi use esse protocolo. 

   O perfil de **Importação de Wi-Fi** (para Windows 8.1 e posterior) permite que você importe as configurações de Wi-Fi como um arquivo XML previamente exportado de um dispositivo diferente.
1. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android e do perfil de trabalho Android](wi-fi-settings-android.md)
    - [Configurações do iOS](wi-fi-settings-ios.md)
    - [Configurações do macOS](wi-fi-settings-macos.md)
    - [Configurações do Windows 8.1 e posterior](wi-fi-settings-import-windows-8-1.md) (incluindo o Windows Holographic for Business)
1. Quando terminar, volte para o painel **Criar perfil** e pressione **Criar**.

O perfil é criado e aparece no painel da lista de perfis.

## <a name="next-steps"></a>Próximas etapas

Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
