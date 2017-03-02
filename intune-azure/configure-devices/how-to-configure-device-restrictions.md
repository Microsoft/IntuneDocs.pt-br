---
title: "Definir configurações de restrição de dispositivo do Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para definir configurações e recursos nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b4d095506215b775d56d172e9aabae1737757310
ms.openlocfilehash: c6293e9c669266203705a8fe06c323869dc7881f
ms.lasthandoff: 02/16/2017


---

# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>Como definir as configurações de restrição de dispositivo no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Restrições de dispositivo permitem controlar uma grande variedade de configurações e recursos que você gerencia em uma gama de categorias, incluindo configurações de segurança, navegador, hardware e compartilhamento de dados. Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.

Use as informações neste tópico para aprender as noções básicas sobre a configuração de perfis de restrição de dispositivo e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações personalizadas. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa do tipo de **Perfil**, escolha **Restrições de dispositivo**. Se você quiser criar um perfil de restrições de dispositivo para dispositivos Windows 10 Team como um Surface Hub, escolha **Restrições de dispositivos (Windows 10 Team)**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android](device-restrictions-for-android.md)
    - [Configurações do iOS](device-restrictions-for-ios.md)
    - [Configurações do macOS](device-restrictions-for-macos.md)
    - [Configurações do Windows Phone 8.1](device-restrictions-for-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-for-windows-8-1.md)
    - [Configurações do Windows 10](device-restrictions-for-windows-10.md)
    - [Configurações do Windows 10 Team](device-restrictions-for-windows-10-team.md)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).

## <a name="example-of-device-restriction-settings"></a>Exemplo de configurações de restrição de dispositivo

Neste exemplo de alto nível, você criará uma política de restrição de dispositivo que bloqueia o uso do aplicativo de câmera interna em dispositivos Android.

![Como desabilitar a câmera em dispositivos Android](./media/disable-android-camera.png)


