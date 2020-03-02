---
title: Restringir recursos de dispositivos com políticas no Microsoft Intune – Microsoft Azure | Microsoft Docs
description: Adicionar um perfil de dispositivo para restringir recursos em dispositivos Android, macOS, iOS, iPadOS, Windows Phone e Windows 10 no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/18/2020
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 53985a9af523ecf60efda5c5c651161c132e326c
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77511214"
---
# <a name="configure-device-restriction-settings-in-microsoft-intune"></a>Definir configurações de restrição de dispositivo no Microsoft Intune



O Microsoft Intune inclui políticas de restrição de dispositivo que ajudam os administradores a controlar dispositivos Android, iOS/iPadOS, macOS e Windows. Com essas restrições, você pode controlar várias funcionalidades e configurações para proteger os recursos da organização. Por exemplo, os administradores podem:

- Permitir ou bloquear a câmera do dispositivo
- Controlar o acesso ao Google Play, lojas de aplicativos, exibição de documentos e jogos.
- Bloquear aplicativos internos e criar uma lista de aplicativos permitidos ou proibidos
- Permitir ou impedir o backup de arquivos em contas de armazenamento e na nuvem
- Definir um comprimento mínimo da senha e bloquear senhas simples

Esses recursos estão disponíveis no Intune e podem ser configurados pelo administrador. O Intune usa "perfis de configuração" para criar e personalizar essas configurações de acordo com as necessidades da sua organização. Depois de adicionar esses recursos em um perfil, você pode enviar por push ou implantar o perfil para dispositivos em sua organização.

Este artigo mostra como criar um perfil de restrições de dispositivos. Além disso, você pode ver todas as configurações disponíveis para diferentes plataformas.

## <a name="create-the-profile"></a>Criar o perfil

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política é **iOS/iPadOS: bloquear câmera em dispositivos**.
    - **Descrição**: Insira uma descrição para a política. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:  

        - **Android**
        - **Android Enterprise**
        - **iOS/iPadOS**
        - **macOS**
        - **Windows Phone 8.1**
        - **Windows 8.1 e posterior**
        - **Windows 10 e posterior**

    - **Tipo de perfil**: Escolha **Restrições de dispositivo**.

        Para criar um perfil de restrições de dispositivo para dispositivos com Windows 10 Team, como um Surface Hub, escolha **Restrições do dispositivo (Windows 10 Team)** .

4. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Escolha sua plataforma para ver as configurações detalhadas:

    - [Configurações do Android](../device-restrictions-android.md)
    - [Configurações do Android Enterprise](../device-restrictions-android-for-work.md)
    - [Configurações do iOS/iPadOS](device-restrictions-ios.md)
    - [Configurações do macOS](device-restrictions-macos.md)
    - [Configurações do Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Configurações do Windows 10](device-restrictions-windows-10.md)
    - [Configurações do Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Configurações do Windows Holographic for Business](device-restrictions-windows-holographic.md)

5. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista de perfis.

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele está pronto para ser atribuído. Em seguida, [atribua o perfil](../device-profile-assign.md) e [monitore seu status](../device-profile-monitor.md).

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/device-restrictions-configure/disable-android-camera.png)

-->
