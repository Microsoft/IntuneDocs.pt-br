---
title: "Usar configurações de dispositivo personalizadas no Microsoft Intune – Azure | Microsoft Docs"
description: "Adicionar ou criar um perfil para usar configurações personalizadas para dispositivos Windows, Android e iOS usando o Microsoft Intune"
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: adecb332c91f17cf92362295b6b0c81445f5acaf
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="create-a-profile-with-custom-settings-in-intune"></a>Criar um perfil com configurações personalizadas no Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune pode não ter todas as configurações nativas que você precisa ou gostaria. Ou então, pode ser útil usar uma configuração disponível em outros perfis de dispositivo. Para adicionar essas configurações, crie um perfil de dispositivo e defina o perfil com as configurações personalizadas do dispositivo.

Este artigo lista as etapas básicas para criar um perfil com configurações personalizadas. Ele também inclui links para obter detalhes sobre a criação de configurações personalizadas com as diferentes plataformas.

## <a name="custom-settings-on-different-platforms"></a>Configurações personalizadas em diferentes plataformas
As configurações personalizadas são definidas forma diferente para cada plataforma. Por exemplo, para controlar recursos em dispositivos Android e Windows, você pode inserir valores OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Para dispositivos da Apple, você pode importar um arquivo criado com o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).

## <a name="create-the-profile"></a>Criar o perfil

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo**, escolha **Perfis**e, em seguida, **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil personalizado.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo na qual as configurações personalizadas serão aplicadas. Você pode escolher uma das seguintes plataformas SQL:

    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**

6. Na lista suspensa de tipos de **Perfil**, escolha **Personalizado**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Os links a seguir fornecem mais detalhes sobre as configurações personalizadas para cada plataforma:

    - [Configurações do Android](custom-settings-android.md)
    - [Configurações do iOS](custom-settings-ios.md)
    - [Configurações do macOS](custom-settings-macos.md)
    - [Configurações do Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Configurações do Windows 10](custom-settings-windows-10.md)
    - [Configurações do Windows Holographic for Business](custom-settings-windows-holographic.md)
    - [Configurações do Android for Work](custom-settings-android-for-work.md)

8. Quando terminar, selecione **Criar**.

O perfil é criado e exibido na lista de perfis. Para atribuir esse perfil a grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).
