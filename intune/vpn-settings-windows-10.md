---
title: "Configurações de VPN do Intune para dispositivos Windows 10"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos Windows 10."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e7fb7697f50706566210063605e9b5d750e0c90
ms.sourcegitcommit: 5a4529aae710ca2abac5b4d2cfd92cb2df7e67cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2017
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>Configurações de VPN para dispositivos Windows 10 no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.


## <a name="base-vpn-settings"></a>Configurações de VPN de base


- **Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectarão.
    - **Adicionar** – Abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:
        - **Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.
        - **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
        - **Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usarão para estabelecer a conexão. Verifique se você definiu apenas um servidor como padrão.
    - **Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importá-los para a lista **Servidores**.
    - **Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).

**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
- **Pulse Secure**
- **F5 Edge Client**
- **Dell SonicWALL Mobile Connect**
- **Check Point Capsule VPN**
- **Automático**
- **IKEv2**
- **L2TP**
- **PPTP**

**Grupo de logon ou domínio** (somente Dell SonicWALL Mobile Connect) – Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.

**XML Personalizado**/**XML EAP** – Especifique os comandos XML personalizados para configurar a conexão VPN.

**Exemplo do Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Exemplo do CheckPoint Mobile VPN:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Exemplo do Dell SonicWALL Mobile Connect:**

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Exemplo do F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.

**Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.
- **Rotas de túnel dividido para essa conexão VPN** – Adicionar rotas opcionais para provedores VPN de terceiros. Especifique um prefixo de destino e um tamanho de prefixo para cada um.

## <a name="apps-and-traffic-rules"></a>Regras de Aplicativos e Tráfego

**Restringir a conexão VPN para esses aplicativos** – Habilite esta opção se você quiser apenas que os aplicativos que você especificar usem a conexão VPN.
**Aplicativos associados** – Forneça uma lista de aplicativos que usarão automaticamente a conexão VPN. O tipo de aplicativo determinará o identificador do aplicativo. Para um aplicativo universal, forneça o nome da família de pacotes. Para um aplicativo da área de trabalho, forneça o caminho do arquivo do aplicativo.

>[!IMPORTANT]
>É recomendável que você proteja todas as listas de aplicativos compiladas para uso na configuração de VPN por aplicativo. Se um usuário não autorizado modificar sua lista e você o importar para a lista de aplicativo VPN por aplicativo, você potencialmente autorizará o acesso VPN para aplicativos que não deveriam ter acesso. É uma maneira de proteger as listas de aplicativo usando uma ACL (lista de controle de acesso).

**Regras de tráfego de rede para esta conexão VPN** – Selecione quais protocolos e quais intervalos de endereços e de portas locais e remotas serão habilitados para a conexão VPN. Se você não criar uma regra de tráfego de rede, todos os protocolos, portas e intervalos de endereços serão habilitados. Após você criar uma regra, a conexão VPN usará somente os protocolos, portas e intervalos de endereços que você especificar na regra.


## <a name="conditional-access"></a>Acesso condicional

**Acesso condicional para esta conexão VPN** – habilita o fluxo de conformidade do dispositivo do cliente. Quando habilitada, o cliente da VPN tentará se comunicar com o Azure Active Directory para obter um certificado a ser usado para autenticação. A VPN deve ser configurada para usar a autenticação de certificado e o servidor VPN deve confiar no servidor retornado pelo Azure Active Directory.

**SSO (logon único) com certificado alternativo** – para conformidade do dispositivo, use um certificado diferente do certificado de autenticação da VPN para a autenticação Kerberos. Especifique o certificado com as seguintes configurações: 

- **Uso avançado de chave** – nome do EKU (uso avançado de chave).
- **Identificador de objeto** – identificador de objeto para EKU.
- **Hash do emissor** – impressão digital do certificado SSO.

## <a name="dns-settings"></a>Configurações de DNS

**Nomes e servidores DNS para esta conexão VPN** – Selecione quais servidores DNS a conexão VPN usará depois que a conexão for estabelecida.
Para cada servidor. especifique:
- **Nome DNS**
- **Servidor DNS**
- **Proxy**

## <a name="proxy-settings"></a>Configurações de proxy

- **Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão. Para obter mais informações, consulte a documentação do Windows Server.
- **Automático** – Use um arquivo de configuração para definir o servidor proxy. Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.
    - **Endereço** – Insira o endereço do servidor proxy (como um endereço IP).
    - **Número da porta** – Insira o número de porta associado ao servidor proxy.
- **Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar. Para obter mais informações, consulte a documentação do Windows Server.
