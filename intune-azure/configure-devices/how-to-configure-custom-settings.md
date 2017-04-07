---
title: "Como definir configurações personalizadas do dispositivo do Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para definir configurações personalizadas nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 029b5c4c011ddf3ff7dbb06c55b48ef0c18c725e
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Como definir configurações personalizadas do dispositivo no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="when-to-use-custom-settings"></a>Quando usar configurações personalizadas

Configurações personalizadas do dispositivo podem ser úteis quando o Intune não tem as configurações que você deseja para configurar internamente e disponíveis de outros perfis de dispositivo.
As configurações personalizadas são definidas forma diferente para cada plataforma. Por exemplo, com dispositivos com Android e Windows, você pode especificar que valores OMA-URI (Open Mobile Alliance Uniform Resource Identifier) controlam os recursos dos dispositivos. Para dispositivos da Apple, você pode importar um arquivo criado com o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Use as informações neste tópico para aprender as noções básicas sobre a definição de perfis com configuração personalizada e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-custom-settings"></a>Criar um perfil de dispositivo que contém configurações personalizadas

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil personalizado.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo personalizado:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android](custom-for-android.md)
    - [Configurações do iOS](custom-for-ios.md)
    - [Configurações do macOS](custom-for-macos.md)
    - [Configurações do Windows Phone 8.1](custom-for-windows-phone-8-1.md)
    - [Configurações do Windows 10](custom-for-windows-10.md)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


