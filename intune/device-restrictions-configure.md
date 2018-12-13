---
title: Definir configurações de restrições de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Adicionar um perfil de dispositivo para restringir os recursos em dispositivos Android, macOS, iOS, Windows Phone e Windows 10 no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 11b241a14ed70a2e999fa505449cd12cdd1e025e
ms.sourcegitcommit: ecd6aebe50b1440a282dfdda771e37fbb8750d42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2018
ms.locfileid: "52728779"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Definir configurações de restrição de dispositivo no Microsoft Intune

As restrições de dispositivo permitem controlar uma grande variedade de configurações e recursos que você gerencia em uma variedade de categorias, como:
- Segurança 
- Navegador
- Hardware
- Configurações de compartilhamento de dados

Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.

Aprenda as noções básicas sobre perfil de restrição de dispositivo e, em seguida, leia mais artigos de cada plataforma para saber mais sobre as particularidades dos dispositivos.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
3. Insira um **Nome** e uma **Descrição** para o perfil de restrição de dispositivo.
4. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:

    - **Android**
    - **Android Enterprise**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**

5. Na lista suspensa **Tipo de perfil**, escolha **Restrições de dispositivo**. Para criar um perfil de restrições de dispositivo para dispositivos com Windows 10 Team, como um Surface Hub, escolha **Restrições do dispositivo (Windows 10 Team)**.
6. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Escolha as configurações detalhadas da sua plataforma:

    - [Configurações do Android](device-restrictions-android.md)
    - [Configurações do Android Enterprise](device-restrictions-android-for-work.md)
    - [Configurações do iOS](device-restrictions-ios.md)
    - [Configurações do macOS](device-restrictions-macos.md)
    - [Configurações do Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Configurações do Windows 10](device-restrictions-windows-10.md)
    - [Configurações do Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Configurações do Windows Holographic for Business](device-restrictions-windows-holographic.md)

7. Quando terminar, volte para a página **Criar perfil** e selecione **Criar**.

O perfil é criado e exibido na página da lista de perfis. 

## <a name="next-step"></a>Próxima etapa

Depois que o perfil é criado, ele está pronto para ser atribuído. Consulte [atribuir perfis de dispositivo](device-profile-assign.md) para ver as etapas. 

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
