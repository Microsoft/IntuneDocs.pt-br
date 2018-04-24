---
title: Exibir as configurações de VPN no Microsoft Intune – Azure | Microsoft Docs
description: Conheça e leia sobre as configurações de VPN disponíveis no Microsoft Intune, para que elas são usadas e o que elas fazem, incluindo as regras de tráfego, de acesso condicional e as configurações de DNS e proxy para dispositivos Windows 10 e Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 3/8/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: 9464b73acc43b9625560156617359c374d7100fb
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="read-about-the-vpn-settings-in-intune"></a>Leia sobre as configurações de VPN no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

É possível configurar conexões VPN usando o Intune. Este artigo descreve essas configurações, as regras de tráfego, o acesso condicional e as configurações de DNS e de proxy.

Essas configurações se aplicam a:

- Dispositivos que executam o Windows 10
- Dispositivos que executam o Windows Holographic for Business

Dependendo das configurações escolhidas, nem todos os valores poderão ser configurados.

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Nome da conexão**: insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Servidores**: adicione um ou mais servidores VPN aos quais os dispositivos se conectarão.
  - **Adicionar**: abre **Adicionar Linha**, na qual é possível especificar as seguintes informações:
    - **Descrição**: insira um nome descritivo para o servidor como **Servidor VPN Contoso**
    - **Endereço IP ou FQDN**: insira o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectam, como **192.168.1.1** ou **vpn.contoso.com**
    - **Servidor padrão**: habilita esse servidor como o servidor padrão que os dispositivos usam para estabelecer a conexão. Defina apenas um servidor como padrão.
  - **Importar**: navegue até um arquivo separado por vírgulas que contém uma lista de servidores no formato: descrição, endereço IP ou FQDN, Servidor padrão. Escolha **OK** para importar esses servidores para a lista **Servidores**.
  - **Exportar**: exporta a lista de servidores para um arquivo csv (de valores separados por vírgula)

**Tipo de conexão**: selecione o tipo de conexão VPN na lista de fornecedores a seguir:

- **Automático**
- **Check Point Capsule VPN**
- **Citrix VPN**
- **SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**

**Grupo de logon ou domínio** (somente SonicWALL Mobile Connect): essa propriedade não pode ser definida no perfil de VPN. Em vez disso, o Mobile Connect analisa esse valor quando o nome de usuário e domínio são inseridos nos formatos `username@domain` ou `DOMAIN\username`.

**XML personalizado**/**XML EAP**: especifique os comandos XML personalizados para configurar a conexão VPN.

**Exemplo do Pulse Secure:**

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Exemplo do CheckPoint Mobile VPN:**

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Exemplo do SonicWALL Mobile Connect:**

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Exemplo do F5 Edge Client:**

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Para obter mais informações sobre como escrever comandos XML personalizados, consulte a documentação de VPN de cada fabricante.

Para obter mais informações sobre como criar XML EAP personalizado, consulte [Configuração de EAP](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

**Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.
- **Rotas de túnel dividido para essa conexão VPN**: adicionar rotas opcionais para provedores VPN de terceiros. Insira um prefixo de destino e um tamanho de prefixo para cada um.

## <a name="apps-and-traffic-rules"></a>Regras de Aplicativos e Tráfego

**Restringir a conexão VPN a esses aplicativos**: habilite esta configuração se você quiser que apenas alguns aplicativos usem a conexão VPN.
**Aplicativos associados**: insira uma lista de aplicativos que usam a conexão VPN automaticamente. O tipo de aplicativo determina o identificador do aplicativo. Para um aplicativo universal, insira o nome da família de pacotes. Para um aplicativo da área de trabalho, insira o caminho do arquivo do aplicativo.

>[!IMPORTANT]
>É recomendável que você proteja todas as listas de aplicativos criadas para VPNs por aplicativo. Se um usuário não autorizado modificar esta lista e você o importar para a lista de aplicativos VPN por aplicativo, a VPN poderia ficar autorizada a acessar aplicativos que não deveria. Uma maneira de proteger as listas de aplicativo usando uma ACL (lista de controle de acesso).

**Regras de tráfego de rede para esta conexão VPN**: selecione quais protocolos e quais intervalos de endereços e de portas locais e remotas serão habilitados para a conexão VPN. Se você não criar uma regra de tráfego de rede, todos os protocolos, portas e intervalos de endereços serão habilitados. Após você criar uma regra, a conexão VPN usará somente os protocolos, portas e intervalos de endereços que você especificar nesta regra.

## <a name="conditional-access"></a>Acesso condicional

**Acesso condicional para esta conexão VPN**: habilita o fluxo de conformidade do dispositivo do cliente. Quando habilitada, o cliente da VPN tenta se comunicar com o Azure Active Directory para obter um certificado para usar na autenticação. A VPN deve ser configurada para usar a autenticação de certificado e o servidor VPN deve confiar no servidor retornado pelo Azure Active Directory.

**SSO (logon único) com certificado alternativo**: para conformidade do dispositivo, use um certificado diferente do certificado de autenticação da VPN para autenticação Kerberos. Insira o certificado com as seguintes configurações:

- **Uso avançado de chave**: nome do EKU (uso avançado de chave)
- **Identificador de objeto**: identificador de objeto para EKU
- **Hash do emissor**: impressão digital do certificado SSO

## <a name="dns-settings"></a>Configurações de DNS

**Nomes e servidores DNS para esta conexão VPN**: selecione quais servidores DNS a conexão VPN usará depois que ela for estabelecida.
Para cada servidor, digite:
- **Nome DNS**
- **Servidor DNS**
- **Proxy**

## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy**: se o servidor VPN exigir um servidor proxy para a conexão, escolha se você deseja que os dispositivos detectem automaticamente as configurações de conexão.
- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Insira o **URL do servidor Proxy**, como `http://proxy.contoso.com`, que contém o arquivo de configuração.
- **Usar servidor proxy**: habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
  - **Endereço**: digite o endereço do servidor proxy (como um endereço IP)
  - **Número da porta**: insira o número da porta associada ao servidor proxy
- **Bypass de proxy para endereços locais**: se o servidor VPN exigir um servidor proxy para a conexão, selecione essa configuração se você não quiser usar o servidor proxy para endereços locais que você inserir.
