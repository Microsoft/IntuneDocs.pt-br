---
title: Definir configurações de restrições de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Adicionar um perfil de dispositivo para restringir os recursos em dispositivos Android, macOS, iOS, Windows Phone e Windows 10 no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/27/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 56ddf28bb9e81417b4b91bb18baaba14f07fbdd9
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905046"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Definir configurações de restrição de dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

As restrições de dispositivo permitem controlar uma grande variedade de configurações e recursos que você gerencia em uma variedade de categorias, como:
- Segurança 
- Navegador
- Hardware
- Configurações de compartilhamento de dados

Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.

Aprenda as noções básicas sobre perfil de restrição de dispositivo e, em seguida, leia mais artigos de cada plataforma para saber mais sobre as particularidades dos dispositivos.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil de restrição de dispositivo.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa **Tipo de perfil**, escolha **Restrições de dispositivo**. Se você quiser criar um perfil de restrições de dispositivo para dispositivos Windows 10 Team como um Surface Hub, escolha **Restrições de dispositivos (Windows 10 Team)**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android](device-restrictions-android.md)
    - [Configurações do iOS](device-restrictions-ios.md)
    - [Configurações do macOS](device-restrictions-macos.md)
    - [Configurações do Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Configurações do Windows 10](device-restrictions-windows-10.md)
    - [Configurações do Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Configurações do Windows Holographic for Business](device-restrictions-windows-holographic.md)
    - [Configurações de perfil de trabalho Android](device-restrictions-android-for-work.md)
8. Quando terminar, volte para a página **Criar Perfil** e clique em **Criar**.

O perfil é criado e exibido na página da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->
