---
title: "Como definir configurações de VPN do Intune"
titleSuffix: Azure portal
description: "Saiba como usar o Intune para configurar as conexões VPN nos dispositivos gerenciados."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 1/25/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 772b7f025adc7ae80d0f14c5c630209c4c7529b2
ms.sourcegitcommit: 93622d740cbd12043eedc25a9699cc4256e23e7e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-configure-vpn-settings-in-microsoft-intune"></a>Como definir configurações de VPN no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Use **perfis de VPN** no Microsoft Intune para atribuir configurações de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura.

Por exemplo, suponha que você deseje provisionar todos os dispositivos iOS com as configurações necessárias para conectar a um compartilhamento de arquivos na rede corporativa. Você cria um perfil de VPN que contém as configurações necessárias para conectar à rede corporativa e atribui esse perfil a todos os usuários com dispositivos iOS. Os usuários veem a conexão VPN na lista de redes disponíveis e podem se conectar com esforço mínimo.

## <a name="vpn-connection-types"></a>Tipos de conexão VPN

Você pode criar perfis VPN usando os seguintes tipos de conexão:

|Tipo de conexão|Android<br>Android for Work|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|-|-|-|-|-|-|-|
|Pulse Secure|Sim|Sim|Sim|Sim|Sim|Sim|
|Cisco (IPsec)|Não|Sim|Não|Não|Não|Não|
|Citrix|Sim|Sim|Não|Não|Não|Sim|
|F5 Microsoft Edge Client|Sim|Sim|Sim|Sim|Sim|Sim|
|Dell SonicWALL Mobile Connect|Sim|Sim|Sim|Sim|Sim|Sim|
|Check Point Capsule VPN|Sim|Sim|Sim|Sim|Sim|Sim|
|Cisco AnyConnect|Sim|Sim|Sim|Não|Não|Não|
|Automática|Não|Não|Não|Não|Não|Sim|
|IKEv2|Não|Não|Não|Não|Não|Sim|
|L2TP|Não|Não|Não|Não|Não|Sim|
|PPTP|Não|Não|Não|Não|Não|Sim|
|Personalizado|Não|Sim|Sim|Não|Não|Não|


> [!IMPORTANT]
> Antes de poder usar perfis VPN atribuídos em um dispositivo, você deve instalar o aplicativo VPN aplicável para o perfil. Você pode usar as informações no tópico [O que é gerenciamento no Microsoft Intune?](app-management.md) para ajudá-lo a atribuir o aplicativo usando o Intune.  

Saiba como criar perfis de VPN personalizados usando configurações de URI em [Criar perfis de VPN personalizados](custom-vpn-profiles-create.md).     

## <a name="create-a-device-profile-containing-vpn-settings"></a>Criar um perfil de dispositivo que contém configurações de VPN

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configuração do dispositivo**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de VPN.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo VPN:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **VPN**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas são diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android e do Android for Work](vpn-settings-android.md)
    - [Configurações do iOS](vpn-settings-ios.md)
    - [Configurações do macOS](vpn-settings-macos.md)
    - [Configurações do Windows Phone 8.1](vpn-settings-windows-phone-8-1.md)
    - [Configurações do Windows 8.1](vpn-settings-windows-8-1.md)
    - [Configurações do Windows 10](vpn-settings-windows-10.md) (incluindo o Windows Holographic for Business)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil é criado e exibido na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).


## <a name="methods-of-securing-vpn-profiles"></a>Métodos para proteger perfis de VPN

Perfis VPN podem usar uma série de tipos de conexão e protocolos diferentes, de fabricantes diferentes. Essas conexões geralmente são protegidas usando um destes dois métodos.

### <a name="certificates"></a>Certificados

Ao criar o perfil de VPN, escolha um perfil de certificado SCEP ou PKCS criado anteriormente no Intune. Isso é conhecido como certificado de identidade. Ele é usado para autenticar um perfil de certificado confiável (ou *certificado raiz*) que você criou para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é atribuído no computador que autentica a conexão de VPN, em geral, o servidor VPN.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Microsoft Intune](certificates-configure.md).

### <a name="user-name-and-password"></a>Nome e senha do usuário

O usuário autentica no servidor VPN, fornecendo seu nome de usuário e senha.
