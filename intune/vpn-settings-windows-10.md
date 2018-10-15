---
title: Definir as configurações de VPN do Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Conheça e leia sobre as configurações de VPN disponíveis no Microsoft Intune, para que elas são usadas e o que elas fazem, incluindo as regras de tráfego, de acesso condicional e as configurações de DNS e proxy para dispositivos Windows 10 e Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.reviewer: tycast
ms.custom: intune-azure
ms.openlocfilehash: faf07b58c4480689d5f6f44bf09d6100a2eae9db
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2018
ms.locfileid: "48827846"
---
# <a name="windows-10-vpn-settings-in-intune"></a>Configurações de VPN do Windows 10 no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

É possível configurar conexões VPN usando o Intune. Este artigo descreve essas configurações, as regras de tráfego, o acesso condicional e as configurações de DNS e de proxy.

Essas configurações se aplicam a:

- Dispositivos que executam o Windows 10
- Dispositivos que executam o Windows Holographic for Business

Dependendo das configurações escolhidas, nem todos os valores poderão ser configurados.

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Nome da conexão**: insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Servidores**: adicione um ou mais servidores VPN aos quais os dispositivos se conectarão. Quando você adiciona um servidor, insere as seguintes informações:
  - **Descrição**: insira um nome descritivo para o servidor como **Servidor VPN Contoso**
  - **Endereço IP ou FQDN**: insira o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectam, como **192.168.1.1** ou **vpn.contoso.com**
  - **Servidor padrão**: habilita esse servidor como o servidor padrão que os dispositivos usam para estabelecer a conexão. Defina apenas um servidor como padrão.
  - **Importar**: navegue até um arquivo separado por vírgulas que inclui uma lista de servidores no formato: descrição, endereço IP ou FQDN, servidor padrão. Escolha **OK** para importar esses servidores para a lista **Servidores**.
  - **Exportar**: exporta a lista de servidores para um arquivo csv (de valores separados por vírgula)

- **Registrar endereços IP com DNS interno**: selecione **Habilitar** para configurar o perfil VPN do Windows 10 para registrar dinamicamente os endereços IP atribuídos à interface VPN com o DNS interno. Selecione **Desabilitar** para não registrar dinamicamente os endereços IP.

- **Tipo de conexão**: selecione o tipo de conexão VPN na lista de fornecedores a seguir:

  - **Pulse Secure**
  - **F5 Edge Client**
  - **SonicWALL Mobile Connect**
  - **Check Point Capsule VPN**
  - **Citrix**
  - **Palo Alto Networks GlobalProtect**
  - **Automático**
  - **IKEv2**
  - **L2TP**
  - **PPTP**

  Quando você escolhe um tipo de conexão VPN, também pode ser solicitado a fornecer as seguintes configurações:  
    - **Always On**: **habilite** para conectar-se automaticamente à conexão VPN quando ocorrer o seguinte: 
      - Os usuários fazem logon em seus dispositivos
      - A rede no dispositivo muda
      - A tela do dispositivo é ativada novamente depois de ser desligada 

    - **Método de autenticação**: selecione o modo de autenticação desejado para os usuários no servidor VPN. Usar **certificados** fornece recursos avançados, como experiência sem toque, VPN sob demanda e VPN por aplicativo.
    - **Lembrar as credenciais a cada logon**: escolha para armazenar em cache as credenciais de autenticação.
    - **XML personalizado**: insira quaisquer comandos XML personalizados que configurem a conexão VPN.
    - **Xml EAP**: insira quaisquer comandos XML EAP que configurem a conexão VPN

#### <a name="pulse-secure-example"></a>Exemplo de Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

#### <a name="f5-edge-client-example"></a>Exemplo de F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

#### <a name="sonicwall-mobile-connect-example"></a>Exemplo do SonicWALL Mobile Connect
**Grupo de logon ou domínio**: essa propriedade não pode ser definida no perfil de VPN. Em vez disso, o Mobile Connect analisa esse valor quando o nome de usuário e domínio são inseridos nos formatos `username@domain` ou `DOMAIN\username`.

Exemplo:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

#### <a name="checkpoint-mobile-vpn-example"></a>Exemplo de VPN Móvel de Ponto de Verificação

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

#### <a name="writing-custom-xml"></a>Gravando XML personalizado
Para obter mais informações sobre como escrever comandos XML personalizados, consulte a documentação de VPN de cada fabricante.

Para obter mais informações sobre como criar XML EAP personalizado, consulte [Configuração de EAP](https://docs.microsoft.com/windows/client-management/mdm/eap-configuration).

## <a name="apps-and-traffic-rules"></a>Regras de Aplicativos e Tráfego

- **Associar WIP ou aplicativos a esta VPN**: habilite essa configuração se quiser que apenas alguns aplicativos usem a conexão VPN. Suas opções:

  - **Associe um WIP a essa conexão**: insira um **domínio WIP para esta conexão**
  - **Associe aplicativos a esta conexão**: você pode **Restringir a conexão VPN a esses aplicativos** e, em seguida, adicionar **Aplicativos Associados**. Os aplicativos que você insere automaticamente usam a conexão VPN. O tipo de aplicativo determina o identificador do aplicativo. Para um aplicativo universal, insira o nome da família de pacotes. Para um aplicativo da área de trabalho, insira o caminho do arquivo do aplicativo.
  >[!IMPORTANT]
  >É recomendável que você proteja todas as listas de aplicativos criadas para VPNs por aplicativo. Se um usuário não autorizado modificar esta lista e você o importar para a lista de aplicativos VPN por aplicativo, a VPN poderia ficar autorizada a acessar aplicativos que não deveria. Uma maneira de proteger as listas de aplicativo usando uma ACL (lista de controle de acesso).

- **Regras de tráfego de rede para esta conexão VPN**: selecione quais protocolos e quais intervalos de endereços e de portas locais e remotas serão habilitados para a conexão VPN. Se você não criar uma regra de tráfego de rede, todos os protocolos, portas e intervalos de endereços serão habilitados. Após você criar uma regra, a conexão VPN usará somente os protocolos, portas e intervalos de endereços que você especificar nesta regra.

## <a name="conditional-access"></a>Acesso condicional

- **Acesso condicional para esta conexão VPN**: habilita o fluxo de conformidade do dispositivo do cliente. Quando habilitado, o cliente da VPN comunica-se com o Azure AD (Active Directory) para obter um certificado para usar na autenticação. A VPN deve ser configurada para usar a autenticação de certificado e o servidor VPN deve confiar no servidor retornado pelo Azure AD.

- **SSO (logon único) com certificado alternativo**: para conformidade do dispositivo, use um certificado diferente do certificado de autenticação da VPN para autenticação Kerberos. Insira o certificado com as seguintes configurações:

  - **Nome**: nome do EKU (uso avançado de chave)
  - **Identificador de objeto**: identificador de objeto para EKU
  - **Hash do emissor**: impressão digital do certificado SSO

## <a name="dns-settings"></a>Configurações de DNS

- **Lista de pesquisa de sufixos DNS**: nos **sufixos DNS**, insira um sufixo DNS e **Adicionar**. É possível adicionar vários sufixos.

  Ao usar sufixos DNS, você pode procurar um recurso de rede usando o nome curto dele em vez do nome de domínio totalmente qualificado (FQDN). Ao pesquisar usando o nome curto, o sufixo é determinado automaticamente pelo servidor DNS. Por exemplo, `utah.contoso.com` está na lista de sufixos DNS. Você executa o ping `DEV-comp`. Nesse cenário, ele resolve para `DEV-comp.utah.contoso.com`.

  Sufixos DNS são resolvidos na ordem listada, e a ordem pode ser alterada. Por exemplo, `colorado.contoso.com` e `utah.contoso.com` estão na lista de sufixos DNS e ambos têm um recurso chamado `DEV-comp`. Como `colorado.contoso.com` é o primeiro na lista, ele é resolvido como `DEV-comp.colorado.contoso.com`.
  
  Para alterar a ordem, clique nos pontos à esquerda do sufixo DNS e, em seguida, arraste o sufixo para a parte superior:

  ![Selecione os três pontos e clique e arraste para mover o sufixo dns](./media/vpn-settings-windows10-move-dns-suffix.png)

- **Domínio e servidores para esta conexão VPN**: adicione o domínio e o servidor DNS para a VPN usar. Você pode escolher quais servidores DNS a conexão VPN usa depois que a conexão é estabelecida. Para cada servidor, digite:
- **Domínio**
- **Servidor DNS**
- **Proxy**

## <a name="proxy-settings"></a>Configurações de proxy

- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Insira a **URL do servidor proxy**, como `http://proxy.contoso.com`, que inclui o arquivo de configuração.
- **Endereço**: digite o endereço do servidor proxy, como um endereço IP ou `vpn.contoso.com`
- **Número da porta**: insira o número da porta TCP usado pelo servidor proxy
- **Ignorar proxy para endereços locais**: se você não quiser usar um servidor proxy para endereços locais, escolha Habilitar. Essa configuração se aplicará se o servidor VPN exigir um servidor proxy para a conexão.

## <a name="split-tunneling"></a>Túnel Dividido

- **Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.
- **Rotas de túnel dividido para essa conexão VPN**: adicionar rotas opcionais para provedores VPN de terceiros. Insira um prefixo de destino e um tamanho de prefixo para cada conexão.
