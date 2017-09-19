---
title: "Como definir configurações personalizadas do dispositivo do Intune"
titleSuffix: Azure portal
description: "Saiba como usar o Intune para definir configurações personalizadas nos dispositivos gerenciados."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 607b517ae65309c2d01fa0d173e513c029a6869d
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Como definir configurações personalizadas do dispositivo no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Quando usar configurações personalizadas

Configurações personalizadas do dispositivo podem ser úteis quando o Intune não tem as configurações que você deseja para configurar internamente e disponíveis de outros perfis de dispositivo.
As configurações personalizadas são definidas forma diferente para cada plataforma. Por exemplo, com dispositivos com Android e Windows, você pode especificar que valores OMA-URI (Open Mobile Alliance Uniform Resource Identifier) controlam os recursos dos dispositivos. Para dispositivos da Apple, você pode importar um arquivo criado com o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

Use as informações neste tópico para aprender as noções básicas sobre a definição de perfis com configuração personalizada e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-custom-settings"></a>Criar um perfil de dispositivo que contém configurações personalizadas

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
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
    - [Configurações do Android](custom-settings-android.md)
    - [Configurações do iOS](custom-settings-ios.md)
    - [Configurações do macOS](custom-settings-macos.md)
    - [Configurações do Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Configurações do Windows 10](custom-settings-windows-10.md)
    - [Configurações do Android for Work](custom-settings-android-for-work.md)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
