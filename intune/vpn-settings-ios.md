---
title: Configurações VPN para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Exiba as definições de configuração de VPN (rede virtual privada) disponíveis, incluindo detalhes de conexão, métodos de autenticação e túnel dividido nas configurações de base; as configurações personalizadas de VPN com o identificador e os pares de chave e valor; as configurações de VPN por aplicativo que incluem URLs Safari e VPNs sob demanda com domínios de pesquisa SSIDs ou DNS; e as configurações de proxy para incluir um script de configuração, endereço IP ou FQDN e porta TCP no Microsoft Intune em dispositivos que executam o iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 7/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d35c9e32b7a0720d5d84a93a7edde6f2bd51911f
ms.sourcegitcommit: 08e1b0d45c84eb9525a0a59f5540d41434da2814
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39146621"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Definir as configurações de VPN no Microsoft Intune para dispositivos que executam o iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam iOS.

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Nome da conexão**: insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem no dispositivo para uma lista de conexões VPN disponíveis.
- **Endereço IP ou FQDN**: insira o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam. Por exemplo, insira **192.168.1.1** ou **vpn.contoso.com**.
- **Método de autenticação**: escolha como os dispositivos autenticam-se no servidor VPN:
  - **Certificados**: em **Certificado de autenticação**, selecione um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. [Configurar certificados](certificates-configure.md) apresenta algumas diretrizes sobre perfis de certificado.
  - **Nome de usuário e senha**: os usuários finais deverão fornecer um nome de usuário e uma senha para entrar no servidor VPN.

    > [!NOTE]
    > Se o nome de usuário e senha forem usados como o método de autenticação para a VPN IPsec Cisco, eles deverão fornecer o SharedSecret por meio de um perfil personalizado do Apple Configurator.
  
- **Tipo de conexão**: selecione o tipo de conexão VPN na lista de fornecedores a seguir:
  - **Check Point Capsule VPN**
  - **Cisco AnyConnect**
  - **Cisco Legacy AnyConnect**
  - **SonicWall Mobile Connect**
  - **F5 Edge Client**
  - **Palo Alto Networks GlobalProtect**
  - **Pulse Secure**
  - **Cisco (IPsec)**
  - **Citrix**
  - **VPN personalizado**

    > [!NOTE]
    > - Os perfis do **Cisco Legacy AnyConnect VPN** são para o aplicativo [Cisco Legacy AnyConnect](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) versão 4.0.5x e versões mais antigas
    > - Os perfis do **Cisco AnyConnect VPN** são para o aplicativo [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) versão 4.0.7x e versões mais recentes

- **Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.

## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você tiver selecionado **VPN Personalizada** como o tipo de conexão, defina também as seguintes configurações:

- **Identificador de VPN**: um identificador para o aplicativo VPN que você está usando, fornecido pelo seu provedor de VPN.
- **Digitar os pares chave-valor para os atributos personalizados de VPN**: adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.

## <a name="automatic-vpn-settings"></a>Configurações automáticas de VPN

- **VPN por aplicativo**: escolher essa opção habilita a VPN por aplicativo, autorizando a conexão VPN a ser disparada de forma automática quando determinados aplicativos são abertos. Além de escolher essa opção, você também precisará associar os aplicativos a este perfil VPN. Veja mais detalhes nas [instruções para configurar a VPN por aplicativo para iOS](vpn-setting-configure-per-app.md). 
  - **URLs do Safari que dispararão esta VPN**: selecione para adicionar uma ou mais URLs de site. Quando essas URLs forem acessadas usando o navegador Safari no dispositivo, a conexão VPN será estabelecida automaticamente.

- **VPN sob demanda**: configure regras condicionais que controlem quando a conexão VPN é iniciada. Por exemplo, crie uma condição em que a conexão VPN é usada somente quando um dispositivo não está conectado a uma rede Wi-Fi da empresa. Ou crie uma condição em que, se um dispositivo não puder acessar um domínio de pesquisa DNS especificado, a conexão VPN não será iniciada.

  - **Domínios de pesquisa de DNS ou SSIDs**: selecione se essa condição usa **SSIDs** de rede sem fio ou **domínios de pesquisa de DNS**. Escolha **Adicionar** para configurar um ou mais SSIDs ou domínios de pesquisa.
  - **Investigação de cadeia de caracteres de URL**: opcional. Insira uma URL que a regra use como teste. Se o dispositivo no qual o perfil estiver instalado puder acessar essa URL sem redirecionamento, a conexão VPN será iniciada e o dispositivo se conectará à URL de destino. O usuário não verá o site da investigação de cadeia de caracteres da URL. Um exemplo de uma investigação de cadeia de caracteres de URL é o endereço de um servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN. Outra possibilidade é que a URL teste a capacidade da VPN de conectar-se a um site, antes de conectar o dispositivo à URL de destino por meio da VPN.
  - **Ação de domínio**: escolha um dos seguintes itens:
    - Conectar se necessário
    - Nunca conectar
  - **Ação**: escolha um dos seguintes itens:
    - Connect
    - Avaliar a conexão
    - Ignorar
    - Desconectar

## <a name="proxy-settings"></a>Configurações de proxy

- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Endereço**: insira o endereço IP do nome do host totalmente qualificado do servidor proxy.
- **Número da porta**: insira o número da porta associada ao servidor proxy.

## <a name="next-step"></a>Próxima etapa
[Criar perfis de VPN no Intune](vpn-settings-configure.md)
