---
title: "Definir as configurações de recurso de dispositivo do Intune"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para configurar recursos nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: fddd4963ceea09b37ad4d8c739f437dbcf3b053e
ms.lasthandoff: 04/26/2017


---

# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Como definir as configurações de recurso de dispositivo no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

As restrições de dispositivo permitem que você controle os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.

Use as informações neste tópico para aprender as noções básicas sobre a configuração de perfis de recurso de dispositivo e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de recursos do dispositivo.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações. No momento, é possível escolher uma das seguintes plataformas para os recursos do dispositivo:
    - **iOS**
    - **macOS**
6. Na lista suspensa do **Tipo de perfil**, escolha **Recursos do dispositivo**. 
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do AirPrint para iOS e MacOS](air-print-settings-for-ios-and-macos.md)
     - [Configurações do AirPlay para iOS](airplay-settings-for-ios-devices.md)
    - [Configurações do layout da Tela inicial para iOS](home-screen-settings-for-ios.md)
    - [Configurações de notificação de aplicativos para iOS](app-notification-settings-for-ios.md)
    - [Definições de configuração de dispositivo compartilhado para iOS](shared-device-settings-for-ios.md)

8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).




