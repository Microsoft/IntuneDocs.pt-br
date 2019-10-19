---
title: Usar as configurações de VPN para dispositivos Android no Microsoft Intune – Azure | Microsoft Docs
description: Veja todas as configurações para criar conexões VPN em dispositivos Android no Microsoft Intune. Insira o nome da conexão, o endereço IP ou o FQDN do servidor VPN, escolha como os usuários se autenticam e escolha os tipos de conexão Citrix, SonicWall, Check Point e Pulse Secure.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/06/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8d9fefc2413e2dafbf5d0ad67ea15f5f8406cc1c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506552"
---
# <a name="android-device-settings-to-configure-vpn-in-intune"></a>Configurações do dispositivo Android para configurar a VPN no Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo lista e descreve as diferentes configurações de conexão VPN que você pode controlar em dispositivos Android. Como parte da sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para criar uma conexão VPN, escolha como a VPN é autenticada, selecione um tipo de servidor VPN e muito mais.

Como administrador do Intune, você pode criar e atribuir configurações de VPN a dispositivos Android. 

Para saber mais sobre perfis de VPN no Intune, confira [perfis de VPN](vpn-settings-configure.md).

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](vpn-settings-configure.md#create-a-device-profile) e escolha **Android**.

## <a name="base-vpn"></a>VPN base

- **Nome da conexão**: insira um nome para esta conexão. Os usuários finais veem esse nome quando navegam na lista de conexões VPN disponíveis no dispositivo. Por exemplo, insira `Contoso VPN`.
- **Endereço IP ou FQDN**: insira o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam. Por exemplo, insira **192.168.1.1** ou **vpn.contoso.com**.

  - **Método de autenticação**: escolha como os dispositivos se autenticam no servidor VPN. Suas opções:

    - **Certificados**: selecione um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. A opção [Configurar certificados](../protect/certificates-configure.md) lista as etapas para criar um perfil de certificado.
    - **Nome de usuário e senha**: ao entrar no servidor VPN, é solicitado que os usuários finais insiram um nome de usuário e uma senha.

- **Tipo de conexão**: selecione o tipo de conexão VPN. Suas opções:

  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **Acesso por F5**
  - **Pulse Secure**
  - **SSO da Citrix**

- **Impressão digital** (somente VPN do Check Point Capsule): insira uma cadeia de caracteres, como **Código de impressões digitais da Contoso**, para verificar se o servidor VPN é confiável. Uma impressão digital é enviada ao cliente para que o cliente saiba confiar em qualquer servidor que tenha a mesma impressão digital. Se o dispositivo não tiver a impressão digital, ele solicitará ao usuário para que ele confie no servidor VPN enquanto mostra a impressão digital. O usuário verifica manualmente a impressão digital e escolhe confiar para se conectar.
- **Inserir pares de chave e valor para os atributos de VPN do Citrix** (somente Citrix): insira pares de chave e valor, fornecidos pela Citrix. Esses valores configuram as propriedades da conexão de VPN. 

  Você também pode **importar** um arquivo de valores separados por vírgula (. csv) com chaves e pares de valores. Certifique-se de examinar os **meus dados tem cabeçalhos** e propriedades de **chave** .

  Depois de adicionar os pares de chave e valores, use **Exportar** para fazer backup dos dados em um arquivo. csv.

## <a name="next-steps"></a>Próximas etapas

[Atribuir o perfil](device-profile-assign.md) e [monitorar seu status](device-profile-monitor.md).

Você também pode criar perfis de VPN para dispositivos [Android Enterprise](vpn-settings-android-enterprise.md), [Ios](vpn-settings-ios.md), [MacOS](vpn-settings-macos.md), [Windows 10 e posterior](vpn-settings-windows-10.md), [Windows 8.1](vpn-settings-windows-8-1.md)e [Windows Phone 8,1](vpn-settings-windows-phone-8-1.md) .
