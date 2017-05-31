---
title: "Configurações de VPN do Intune para dispositivos macOS | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos macOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 4737fc863e3eda92eafd0536a07abf4100ebe9cc
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a>Configurações de VPN para dispositivos macOS no Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.

## <a name="base-vpn-settings"></a>**Configurações de VPN de base**

**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **VPN personalizado**
- **Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você selecionou **VPN Personalizada**, defina essas configurações adicionais:

- **Identificador de VPN** Este é um identificador para o aplicativo VPN que você está usando e é fornecido pelo seu provedor VPN.
- **Digite os pares de chave-valor para os atributos personalizados de VPN** Adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.


## <a name="proxy-settings"></a>Configurações de proxy

- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
- **Número da porta** – Insira o número de porta associado ao servidor proxy.

