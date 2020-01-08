---
title: Adicionar configurações de VPN a dispositivos no Microsoft Intune – Azure | Microsoft Docs
description: Use configurações internas a fim de criar conexões de VPN (rede virtual privada) no Microsoft Intune para dispositivos Android, Android Enterprise, iOS, macOS e Windows.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b11cbd3427b3b8e0a43a6e6e2af5fa80da45e16a
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75206271"
---
# <a name="create-vpn-profiles-to-connect-to-vpn-servers-in-intune"></a>Criar perfis de VPN para se conectar a servidores VPN no Microsoft Intune



As VPNs proporcionam aos usuários acesso remoto seguro à rede da empresa. Os dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Os **perfis de VPN** do Microsoft Intune atribuem configurações de VPN a usuários e dispositivos na organização, de modo que eles possam se conectar à rede com facilidade e segurança.

Por exemplo, se você quiser definir todos os dispositivos iOS com as configurações necessárias para se conectar a um compartilhamento de arquivos na rede da empresa, crie um perfil VPN que inclui essas configurações. Em seguida, atribua esse perfil a todos os usuários que têm dispositivos iOS. Os usuários veem a conexão VPN na lista de redes disponíveis e podem se conectar com esforço mínimo.

> [!NOTE]
> Você pode usar [políticas de configuração personalizadas do Microsoft Intune](custom-settings-configure.md) para criar perfis VPN para as seguintes plataformas:
>
> * Android 4 e posterior
> * Dispositivos registrados que executam o Windows 8.1 e versões posteriores
> * Windows Phone 8.1 e posterior
> * Dispositivos registrados que executam o Windows 10 Desktop
> * Windows 10 Mobile
> * Windows Holographic for Business

## <a name="vpn-connection-types"></a>Tipos de conexão VPN

Você pode criar perfis VPN usando os seguintes tipos de conexão:

|Tipo de conexão|Plataforma|
|-|-|
|Automática|Windows 10|
|Check Point Capsule VPN|– Android<br/>– Perfis de trabalho do Android Enterprise<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|Cisco AnyConnect|– Android<br/>– Perfis de trabalho do Android Enterprise<br/>– Proprietário do dispositivo Android Enterprise (totalmente gerenciado)<br/>– iOS<br/>– macOS|
|Cisco (IPSec)|iOS|
|SSO da Citrix|– Android<br/>– Perfis de trabalho do Android Enterprise: usam a [política de configuração de aplicativo](../apps/app-configuration-policies-use-android.md)<br/>– Proprietário do dispositivo Android Enterprise (totalmente gerenciado): usam a [política de configuração de aplicativo](../apps/app-configuration-policies-use-android.md)<br/>– iOS<br/>– Windows 10|
|VPN personalizado|– iOS<br/>– macOS|
|Acesso por F5|– Android<br/>– Perfis de trabalho do Android Enterprise<br/>– Proprietário do dispositivo Android Enterprise (totalmente gerenciado)<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|IKEv2| – iOS<br/>– Windows 10|
|L2TP|Windows 10|
|Palo Alto Networks GlobalProtect|– Perfis de trabalho do Android Enterprise: usam a [política de configuração de aplicativo](../apps/app-configuration-policies-use-android.md)<br/>– iOS<br/>– Windows 10|
|PPTP|Windows 10|
|Pulse Secure|– Android<br/>– Perfis de trabalho do Android Enterprise<br/>– Proprietário do dispositivo Android Enterprise (totalmente gerenciado)<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|SonicWall Mobile Connect|– Android<br/>– Perfis de trabalho do Android Enterprise<br/>– iOS<br/>– macOS<br/>– Windows 10<br/>– Windows 8.1<br/>– Windows Phone 8.1|
|Zscaler|– Perfis de trabalho do Android Enterprise: usam a [política de configuração de aplicativo](../apps/app-configuration-policies-use-android.md)<br/>– iOS|

> [!IMPORTANT]
> Antes de poder usar perfis VPN atribuídos em um dispositivo, você deve instalar o aplicativo VPN aplicável para o perfil. Você pode usar as informações no artigo [O que é gerenciamento de aplicativos no Microsoft Intune?](../apps/app-management.md) para ajudá-lo a atribuir o aplicativo usando o Intune.  

Aprenda a criar perfis de VPN personalizados usando configurações de URI em [Criar um perfil com configurações personalizadas](custom-settings-configure.md).

## <a name="create-a-device-profile"></a>Criar um perfil de dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração** > **Criar perfil**.
3. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para o perfil. Nomeie seus perfis para que você possa identificá-los facilmente mais tarde. Por exemplo, um nome ideal de perfil é **Perfil VPN para toda a empresa**.
    - **Descrição**: Insira uma descrição para o perfil. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:

      - **Android**
      - **Android Enterprise** > **Somente Proprietário do Dispositivo**
      - **Android Enterprise** > **Somente Perfil de Trabalho**
      - **iOS/iPadOS**
      - **macOS**
      - **Windows Phone 8.1**
      - **Windows 8.1 e posterior**
      - **Windows 10 e posterior**

    - **Tipo de perfil**: Selecione **VPN**.

4. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Leia os artigos a seguir para saber mais sobre as configurações de cada plataforma:

    - [Configurações do Android](vpn-settings-android.md)
    - [Configurações do Android Enterprise](vpn-settings-android-enterprise.md)
    - [Configurações do iOS/iPadOS](vpn-settings-ios.md)
    - [Configurações do macOS](vpn-settings-macos.md)
    - [Configurações do Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Configurações do Windows 8.1](vpn-settings-windows-8-1.md)
    - [Configurações do Windows 10](vpn-settings-windows-10.md) (incluindo o Windows Holographic for Business)

5. Quando terminar, selecione **OK** > **Criar** para salvar suas alterações.

O perfil é criado e exibido na lista de perfis. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).

## <a name="secure-your-vpn-profiles"></a>Proteger perfis VPN

Perfis VPN podem usar uma série de tipos de conexão e protocolos diferentes, de fabricantes diferentes. Essas conexões geralmente são protegidas por meio dos métodos a seguir.

### <a name="certificates"></a>Certificados

Ao criar o perfil de VPN, escolha um perfil de certificado SCEP ou PKCS criado anteriormente no Intune. Esse perfil é conhecido como certificado de identidade. Ele é usado para autenticar um perfil de certificado confiável (ou *certificado raiz*) que você criou para permitir que o dispositivo do usuário consiga se conectar. O certificado confiável é atribuído no computador que autentica a conexão de VPN, em geral, o servidor VPN.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Microsoft Intune](../protect/certificates-configure.md).

### <a name="user-name-and-password"></a>Nome e senha do usuário

O usuário autentica no servidor VPN, fornecendo seu nome de usuário e senha.

## <a name="next-steps"></a>Próximas etapas

Depois que o perfil é criado, ele ainda não faz nada. Em seguida, [atribua o perfil](device-profile-assign.md) a alguns dispositivos.

Você pode também criar e usar VPNs por aplicativo em dispositivos [Android](android-pulse-secure-per-app-vpn.md) e [iOS](vpn-setting-configure-per-app.md).
