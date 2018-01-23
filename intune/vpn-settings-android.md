---
title: "Configurações de VPN do Intune para dispositivos Android"
titlesuffix: Azure portal
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos Android"
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 31d1e40c3cd352c00dd7a659f716b5690ea64ea1
ms.sourcegitcommit: 5877b650d93fc9a5e8f058f845acbdbfdff828b7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>Configurações de VPN para dispositivos Android no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Como administrador do Intune, você pode definir as configurações de VPN para as seguintes plataformas:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Dependendo das configurações escolhidas, nem todos os valores listados abaixo serão configuráveis.

## <a name="android-vpn-settings"></a>Configurações de VPN no Android
**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Impressão digital** (somente Check Point Capsule VPN) – Especifique uma cadeia de caracteres, (por exemplo "Código de impressões digitais da Contoso") que será usado para verificar se o servidor VPN é confiável. Uma impressão digital pode ser enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que apresentar essa impressão digital durante a conexão. Se o dispositivo ainda não tiver a impressão digital, ele solicitará ao usuário que confie no servidor VPN ao qual ele está se conectando enquanto mostra a impressão digital (o usuário verifica a impressão digital manualmente e clica em confiar para se conectar).
- **Insira os pares chave-valor para os atributos de VPN Citrix** (somente Citrix) – Insira os pares chave-valor fornecidos pela Citrix para configurar as propriedades de conexão de VPN.

## <a name="android-for-work-vpn-settings"></a>Configurações de VPN do Android for Work

**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

