---
title: "Como definir as configurações de VPN do Intune | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: aprenda a usar o Intune para definir as conexões VPN nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 89afae81076d563f4ebba289f8fa82eaea6ab234
ms.openlocfilehash: 6ec26a2d3e0566a5c96e39d2b7e37fdad8a3780b


---

# <a name="how-to-configure-vpn-settings"></a>Como definir configurações de VPN 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa. Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN. Use **perfis de VPN** no Microsoft Intune para implantar configurações de VPN para usuários e dispositivos na organização, para que eles possam se conectar à rede de forma fácil e segura.

Por exemplo, suponha que você deseje provisionar todos os dispositivos iOS com as configurações necessárias para conectar a um compartilhamento de arquivos na rede corporativa. Você cria um perfil de VPN que contém as configurações necessárias para conectar à rede corporativa e atribui esse perfil a todos os usuários com dispositivos iOS. Os usuários veem a conexão VPN na lista de redes disponíveis e podem se conectar com esforço mínimo.

## <a name="vpn-connection-types"></a>Tipos de conexão VPN

Você pode criar perfis VPN usando os seguintes tipos de conexão:

|||
|-|-|
|Tipo de conexão|Android|iOS|macOS|Windows Phone 8.1|Windows 8.1|Windows 10|
|Pulse Secure|Sim|Sim|Sim|Sim|Sim|Sim|
|Cisco (IPsec)|Não|Sim|Não|Não|Não|Não|
|Citrix|Sim|Sim|Não|Não|Não|Não|
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
> Antes de poder usar perfis VPN implantados em um dispositivo, você deve instalar o aplicativo VPN aplicável para o perfil. Você pode usar as informações no tópico [O que é gerenciamento no Microsoft Intune?](/intune-azure/manage-apps/what-is-app-management) para ajudá-lo a implantar o aplicativo usando o Intune.  

Saiba como criar perfis de VPN personalizados usando configurações de URI em [Criar perfis de VPN personalizados](create-custom-vpn-profiles.md).     

## <a name="create-a-device-profile-containing-vpn-settings"></a>Criar um perfil de dispositivo que contém configurações de VPN

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Outros** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de VPN.
5. Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de VPN. No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo VPN:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **VPN**.
7. Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes. Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:
    - [Configurações do Android](vpn-for-android.md)
    - [Configurações do iOS](vpn-for-ios.md)
    - [Configurações do macOS](vpn-for-macos.md)
    - [Configurações do Windows Phone 8.1](vpn-for-windows-phone-8-1.md)
    - [Configurações do Windows 8.1](vpn-for-windows-8-1.md)
    - [Configurações do Windows 10](vpn-for-windows-10.md)
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.
Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](how-to-assign-device-profiles.md).


## <a name="methods-of-securing-vpn-profiles"></a>Métodos para proteger perfis de VPN

Perfis VPN podem usar uma série de tipos de conexão e protocolos diferentes, de fabricantes diferentes. Essas conexões geralmente são protegidas usando um destes dois métodos.

### <a name="certificates"></a>Certificados

Ao criar o perfil de VPN, escolha um perfil de certificado SCEP ou PKCS criado anteriormente no Intune. Isso é conhecido como certificado de identidade. Ele é usado para autenticar um perfil de certificado confiável (ou *certificado raiz*) que você criou para estabelecer que o dispositivo do usuário tem permissão para se conectar. O certificado confiável é implantado no computador que autentica a conexão de VPN, em geral, o servidor VPN.

Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Microsoft Intune](how-to-configure-certificates.md).

### <a name="user-name-and-password"></a>Nome e senha do usuário

O usuário autentica no servidor VPN, fornecendo seu nome de usuário e senha.



<!--HONumber=Feb17_HO1-->


