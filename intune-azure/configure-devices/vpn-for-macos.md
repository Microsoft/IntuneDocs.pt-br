---
title: "Configurações de VPN do Intune para dispositivos macOS | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba mais sobre as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos macOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6cd3069a63bd657d1c9f5e33b96db39a3b3f98d2
ms.openlocfilehash: 6f7bcfaec34c4916f7c916210b00440062b83694


---

# <a name="vpn-settings-for-macos-devices-in-intune-azure-preview"></a>Configurações de VPN para dispositivos macOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.

## <a name="base-vpn-settings"></a>**Configurações de VPN de base**

**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](how-to-configure-certificates.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **VPN personalizado**
- **Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or Mac OS X app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you deploy the software. For more information, see [How to deploy and monitor apps](/intune-azure/manage-apps/deploy-apps). --->

## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você selecionou **VPN Personalizada**, defina essas configurações adicionais:

- **Identificador de VPN** Este é um identificador para o aplicativo VPN que você está usando e é fornecido pelo seu provedor VPN.
- **Digite os pares de chave-valor para os atributos personalizados de VPN** Adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.


## <a name="proxy-settings"></a>Configurações de proxy

- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
- **Número da porta** – Insira o número de porta associado ao servidor proxy.



<!--HONumber=Feb17_HO2-->


