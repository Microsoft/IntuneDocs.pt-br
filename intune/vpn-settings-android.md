---
title: Definir as configurações de VPN para dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
description: Ao criar um perfil de configuração de VPN para dispositivos Android e Android for Work, insira o nome da conexão, o endereço IP ou o FQDN do servidor VPN, escolha como os usuários se autenticam no servidor VPN e, em seguida, escolha os tipos de conexão Citrix, SonicWall, Check Point Capsule, Pulse Secure e Microsoft Edge.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aff0aad055aee08dfbf17622e3d9f9c3061165b8
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57233960"
---
# <a name="configure-vpn-settings-for-devices-running-android-in-intune"></a>Definir as configurações de VPN para dispositivos que executam o Android no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam Android.

Você pode definir as configurações de VPN para as seguintes plataformas:

- [Android](#android-vpn-settings)
- [Android Enterprise](#android-enterprise-vpn-settings)

Dependendo das configurações que você escolher, nem todos os valores a seguir serão configuráveis.

## <a name="android-vpn-settings"></a>Configurações de VPN no Android

- **Nome da conexão**: Insira um nome para essa conexão. Os usuários finais veem esse nome quando navegam na lista de conexões VPN disponíveis no dispositivo.
- **Endereço IP ou FQDN**: insira o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam. Por exemplo, insira **192.168.1.1** ou **vpn.contoso.com**.

  - **Método de autenticação**: escolha como os dispositivos se autenticam no servidor VPN. Suas opções:

    - **Certificados**: escolha um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. A opção [Configurar certificados](certificates-configure.md) lista as etapas para criar um perfil de certificado.
    - **Nome de usuário e senha**: ao entrar no servidor VPN, os usuários finais são solicitados a inserir um nome de usuário e uma senha.

- **Tipo de conexão**: escolha o tipo de conexão VPN. Suas opções:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **Citrix**

- **Impressão digital** (somente VPN do Check Point Capsule): insira uma cadeia de caracteres, como **Código de impressões digitais da Contoso**, para verificar se o servidor VPN é confiável. Uma impressão digital pode ser enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que tiver essa impressão digital durante a conexão. Se o dispositivo não tiver a impressão digital, ele solicitará ao usuário para que ele confie no servidor VPN enquanto mostra a impressão digital. O usuário verifica manualmente a impressão digital e escolhe Confiar para se conectar.
- **Inserir pares de chave e valor para os atributos de VPN da Citrix** (somente Citrix): insira pares de chave e valor fornecidos pela Citrix. Esses valores configuram as propriedades da conexão de VPN.

## <a name="android-enterprise-vpn-settings"></a>Configurações de VPN do Android Enterprise

- **Nome da conexão**: Insira um nome para essa conexão. Os usuários finais veem esse nome quando navegam na lista de conexões VPN disponíveis no dispositivo.
- **Endereço IP ou FQDN**: insira o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam. Por exemplo, insira **192.168.1.1** ou **vpn.contoso.com**.

  - **Método de autenticação**: escolha como os dispositivos se autenticam no servidor VPN. Suas opções:
  
    - **Certificados**: escolha um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. A opção [Configurar certificados](certificates-configure.md) lista as etapas para criar um perfil de certificado.
    - **Nome de usuário e senha**: ao entrar no servidor VPN, os usuários finais são solicitados a inserir um nome de usuário e uma senha.

- **Tipo de conexão**: escolha o tipo de conexão VPN. Suas opções:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **Acesso por F5**
  - **Pulse Secure**

## <a name="next-steps"></a>Próximas etapas
[Perfis de VPN no Intune](vpn-settings-configure.md)
