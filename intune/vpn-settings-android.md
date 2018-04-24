---
title: Configurações de VPN do Microsoft Intune para dispositivos que executam o Android
titlesuffix: ''
description: Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos que executam o Android
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7c3b4964baec0ae957cfb392843ce527bf13934e
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-android"></a>Definir as configurações de VPN no Microsoft Intune para dispositivos que executam o Android 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam Android.


Você pode definir as configurações de VPN para as seguintes plataformas:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Dependendo das configurações que você escolher, nem todos os valores a seguir serão configuráveis.

## <a name="android-vpn-settings"></a>Configurações de VPN no Android
**Nome da conexão** – Insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Endereço IP ou FQDN** – forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão no servidor VPN:
    - **Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Impressão digital** (somente Check Point Capsule VPN) – Especifique uma cadeia de caracteres, (por exemplo "Código de impressões digitais da Contoso") que é usada para verificar se o servidor VPN é confiável. Uma impressão digital pode ser enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que apresentar essa impressão digital durante a conexão. Se o dispositivo ainda não tem a impressão digital, ele solicita ao usuário que confie no servidor VPN ao qual ele está se conectando enquanto mostra a impressão digital (o usuário verifica a impressão digital manualmente e clica em confiar para se conectar).
- **Insira os pares chave-valor para os atributos de VPN Citrix** (somente Citrix) – Insira os pares chave-valor fornecidos pela Citrix para configurar as propriedades de conexão de VPN.

## <a name="android-for-work-vpn-settings"></a>Configurações de VPN do Android for Work

**Nome da conexão** – Insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Endereço IP ou FQDN** – forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão no servidor VPN:
    - **Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

