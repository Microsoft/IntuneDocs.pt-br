---
title: Definir configurações de VPN em dispositivos macOS no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de VPN (rede virtual privada), incluindo os detalhes da conexão, túnel dividido, configurações de VPN personalizadas com os pares identificador, chave e valor, configurações de proxy com um script de configuração, endereço IP ou FQDN e porta TCP em Microsoft Intune em dispositivos que executam o macOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/09/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 044b35b34a9a5b01537e82dcfddca74a284ebdcc
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72491018"
---
# <a name="add-vpn-settings-on-macos-devices-in-microsoft-intune"></a>Adicionar configurações de VPN em dispositivos macOS no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam macOS.

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](vpn-settings-configure.md).

> [!NOTE]
> Essas configurações estão disponíveis para todos os tipos de registro. Para obter mais informações sobre os tipos de registro, consulte [registro do MacOS](../enrollment/macos-enroll.md).

## <a name="base-vpn-settings"></a>Configurações de VPN de base

**Nome da conexão**: insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Endereço IP ou FQDN**: forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação**: escolha como os dispositivos autenticam-se no servidor VPN:
  - **Certificados**: em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais informações sobre os perfis de certificado, consulte [Como configurar certificados](../protect/certificates-configure.md).
  - **Nome de usuário e senha**: os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de conexão**: selecione o tipo de conexão VPN na lista de fornecedores a seguir:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Pulse Secure**
  - **VPN personalizado**
- **Túnel dividido**: **Habilite** ou **Desabilite** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, mas usará a rede padrão do hotel para navegação regular na Web.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](../apps/apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você selecionou **VPN Personalizada**, defina essas configurações adicionais:

- **Identificador de VPN**: Insira um identificador para o aplicativo VPN que você está usando. Esse identificador é fornecido pelo seu provedor de VPN.
- **Digitar os pares chave-valor para os atributos personalizados de VPN**: adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Esses valores geralmente são fornecidos pelo seu provedor de VPN.

## <a name="proxy-settings"></a>Configurações de proxy

- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Insira a **URL do servidor Proxy** que contém o arquivo de configuração. Por exemplo, insira `http://proxy.contoso.com`.
- **Endereço**: digite o endereço do servidor proxy (como um endereço IP).
- **Número da porta**: insira o número da porta associada ao servidor proxy.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de VPN em dispositivos [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [Ios](vpn-settings-ios.md)e [Windows 10](vpn-settings-windows-10.md) .
