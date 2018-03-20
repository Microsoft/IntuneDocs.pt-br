---
title: "Configurações de VPN do Microsoft Intune para dispositivos que executam o iOS"
titlesuffix: 
description: "Conheça as definições do Intune que você pode usar para configurar as conexões VPN em dispositivos que executam o iOS."
keywords: 
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/5/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 70721d1d2f360527af0e269a93d6243b6a42431b
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Definir as configurações de VPN no Microsoft Intune para dispositivos que executam o iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam iOS.

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base


**Nome da conexão** – Insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Endereço IP ou FQDN** – forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão no servidor VPN:
    - **Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais informações sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – os usuários finais deverão fornecer um nome de usuário e uma senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **SonicWall Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Cisco (IPsec)**
    - **Citrix**
    - **VPN personalizado**
- **Túnel dividido** - **Habilite** ou **Desabilite** essa opção que permite que os dispositivos decidam qual conexão usarão dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, mas usará a rede padrão do hotel para navegação regular na Web.


## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você selecionou **VPN Personalizada**, como o tipo de conexão, defina essas configurações adicionais:

- **Identificador de VPN** Este é um identificador para o aplicativo VPN que você está usando e é fornecido pelo seu provedor VPN.
- **Digite os pares de chave-valor para os atributos personalizados de VPN** Adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.

## <a name="apps-per-app-vpn-settings"></a>Configurações de aplicativos (VPN por aplicativo)

- **VPN por aplicativo** – habilite essa opção se desejar que as URLs habilitem a conexão VPN quando forem acessadas de um navegador Safari. Para configurar isso, você deve selecionar **Certificados** como o método de autenticação nas configurações de VPN de base.
- **URLs que habilitam a conexão VPN ao usar o navegador Safari** – clique em Adicionar para adicionar uma ou mais URLs de site. Quando essas URLs forem visitadas, a conexão VPN será habilitada.

- **Regras de sob demanda** – Isso permite configurar regras condicionais que controlam quando a conexão VPN é iniciada. Por exemplo, você pode criar uma condição em que a conexão VPN é usada somente quando um dispositivo não está conectado a uma das redes Wi-Fi da empresa. Como alternativa, você poderia criar uma condição em que, se um dispositivo não puder acessar um domínio de pesquisa DNS especificado, a conexão VPN não será iniciada.

    - **Domínios de pesquisa de DNS ou SSIDs** – selecione se essa condição usará a rede sem fio **SSIDs** ou os **domínios de pesquisa de DNS**. Escolha Adicionar para configurar um ou mais SSIDs ou pesquisar domínios.
    - **Teste de cadeia de caracteres de URL** – opcionalmente, forneça uma URL que usa a regra como um teste. Se o dispositivo no qual esse perfil está instalado puder acessar essa URL sem redirecionamento, a conexão VPN será iniciada e o dispositivo se conectará à URL de destino. O usuário não verá o site da investigação de cadeia de caracteres da URL. Um exemplo de uma investigação de cadeia de caracteres de URL é o endereço de um servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN. Outra possibilidade é que a URL teste a capacidade da VPN de conectar-se a um site, antes de conectar o dispositivo à URL de destino por meio da VPN.
    - **Ação de domínio** – escolha uma das seguintes opções:
        - Conectar se necessário – 
        - Nunca conectar – 
    - **Ação** – escolha uma das seguintes opções:
        - Conectar – 
        - Avaliar conexão – 
        - Ignorar – 
        - Desconectar – 


## <a name="proxy-settings"></a>Configurações de proxy

- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
- **Número da porta** – Insira o número de porta associado ao servidor proxy.
