---
title: Criar perfil de dispositivo VPN no Microsoft Intune – Azure | Microsoft Docs
description: Para dispositivos iOS, exiba os tipos de conexão de VPN (rede virtual privada), crie um perfil de dispositivo VPN no Portal do Azure e veja suas opções para proteger o perfil VPN com certificados, ou o nome de usuário e a senha no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b2d0bde56c6622648d47fe47458bdac62d7843ca
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838447"
---
# <a name="create-vpn-profiles-in-intune"></a>Criar perfis de VPN no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Use **perfis de VPN** no Microsoft Intune para atribuir configurações de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura.

Por exemplo, suponha que você deseje provisionar todos os dispositivos iOS com as configurações necessárias para conectar a um compartilhamento de arquivos na rede corporativa. Você cria um perfil VPN que contém as configurações para se conectar à rede corporativa. Em seguida, você atribui esse perfil a todos os usuários que têm dispositivos iOS. Os usuários veem a conexão VPN na lista de redes disponíveis e podem se conectar com esforço mínimo.

Você pode usar políticas de configuração personalizadas do Intune para criar perfis de VPN para as seguintes plataformas:

* Android 4 e posterior
* Dispositivos registrados que executam o Windows 8.1 e versões posteriores
* Windows Phone 8.1 e posterior
* Dispositivos registrados que executam o Windows 10 Desktop
* Windows 10 Mobile
* Windows Holographic for Business

## <a name="vpn-connection-types"></a>Tipos de conexão VPN

Você pode criar perfis VPN usando os seguintes tipos de conexão:

|Tipo de conexão|Android<br>Perfis de trabalho Android|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Automática|Não|Não|Não|Não|Não|Sim|
|Check Point Capsule VPN|Sim|Sim|Sim|Sim|Sim|Sim|
|Cisco AnyConnect|Sim|Sim|Sim|Não|Não|Não|
|SonicWall Mobile Connect|Sim|Sim|Sim|Sim|Sim|Sim|
|F5 Microsoft Edge Client|Sim|Sim|Sim|Sim|Sim|Sim|
|Palo Alto Networks GlobalProtect|Não|Sim|Não|Não|Não|Sim|
|Pulse Secure|Sim|Sim|Sim|Sim|Sim|Sim|
|Cisco (IPsec)|Não|Sim|Não|Não|Não|Não|
|Citrix|Sim (Somente Android)|Sim|Não|Não|Não|Sim|
|IKEv2|Não|Não|Não|Não|Não|Sim|
|L2TP|Não|Não|Não|Não|Não|Sim|
|PPTP|Não|Não|Não|Não|Não|Sim|
|Zscaler|Não|Sim|Não|Não|Não|Não|
|VPN personalizado|Não|Sim|Sim|Não|Não|Não|

> [!IMPORTANT]
> Antes de poder usar perfis VPN atribuídos em um dispositivo, você deve instalar o aplicativo VPN aplicável para o perfil. Você pode usar as informações no artigo [O que é gerenciamento de aplicativos no Microsoft Intune?](app-management.md) para ajudá-lo a atribuir o aplicativo usando o Intune.  

Aprenda a criar perfis de VPN personalizados usando configurações de URI em [Criar um perfil com configurações personalizadas](custom-settings-configure.md).

## <a name="create-a-device-profile-containing-vpn-settings"></a>Criar um perfil de dispositivo que contém configurações de VPN

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre por **Intune** e selecione **Microsoft Intune**.
3. Selecione **Configuração do dispositivo** > **Perfis** > **Criar perfil**.
4. Insira um **Nome** e uma **Descrição** para o perfil VPN.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo VPN:
   - **Android**
   - **Android Enterprise**
   - **iOS**
   - **macOS**
   - **Windows Phone 8.1**
   - **Windows 8.1 e posterior**
   - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **VPN**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
   - [Configurações do Android e do perfil de trabalho Android](vpn-settings-android.md)
   - [Configurações do iOS](vpn-settings-ios.md)
   - [Configurações do macOS](vpn-settings-macos.md)
   - [Configurações do Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
   - [Configurações do Windows 8.1](vpn-settings-windows-8-1.md)
   - [Configurações do Windows 10](vpn-settings-windows-10.md) (incluindo o Windows Holographic for Business)
8. Ao terminar, escolha **Criar** seu perfil

O perfil é criado e exibido na lista de perfis. Para atribuir esse perfil a grupos, consulte [atribuir perfis de dispositivo](device-profile-assign.md).

## <a name="methods-of-securing-vpn-profiles"></a>Métodos para proteger perfis de VPN

Perfis VPN podem usar uma série de tipos de conexão e protocolos diferentes, de fabricantes diferentes. Essas conexões geralmente são protegidas usando um destes dois métodos.

### <a name="certificates"></a>Certificados

Ao criar o perfil de VPN, escolha um perfil de certificado SCEP ou PKCS criado anteriormente no Intune. Esse perfil é conhecido como certificado de identidade. Ele é usado para autenticar um perfil de certificado confiável (ou *certificado raiz*) que você criou para permitir que o dispositivo do usuário consiga se conectar. O certificado confiável é atribuído no computador que autentica a conexão de VPN, em geral, o servidor VPN.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Microsoft Intune](certificates-configure.md).

### <a name="user-name-and-password"></a>Nome e senha do usuário

O usuário autentica no servidor VPN, fornecendo seu nome de usuário e senha.
