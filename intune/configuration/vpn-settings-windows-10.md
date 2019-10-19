---
title: Configurações de VPN do Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Saiba mais e leia sobre todas as configurações de VPN disponíveis no Microsoft Intune, para que elas são usadas e o que elas fazem, incluindo regras de tráfego, acesso condicional e configurações de DNS e proxy para dispositivos Windows 10 e Windows Holographic for Business.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/12/2018
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: tycast
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 122872eff92a37c8724fd4a853091e51a0a54c66
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506539"
---
# <a name="windows-10-and-windows-holographic-device-settings-to-add-vpn-connections-using-intune"></a>Configurações de dispositivos Windows 10 e Windows Holographic para adicionar conexões VPN usando o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Você pode adicionar e configurar conexões VPN para dispositivos usando o Microsoft Intune. Este artigo lista e descreve os recursos e as configurações geralmente usadas durante a criação de VPNs (redes virtuais privadas). Essas configurações de VPN e esses recursos são usados em perfis de configuração de dispositivo no Intune que são enviados por push ou implantados em dispositivos.

Como parte de sua solução de MDM (gerenciamento de dispositivo móvel), use essas configurações para permitir ou desabilitar recursos, incluindo o uso de um fornecedor VPN, habilitar o Always On, usar o DNS, adicionar um proxy, entre outros.

Essas configurações se aplicam a dispositivos que executam:

- Windows 10
- Windows Holographic for Business

Dependendo das configurações escolhidas, nem todos os valores poderão ser configurados.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo VPN](vpn-settings-configure.md).

## <a name="base-vpn-settings"></a>Configurações de VPN de base

- **Nome da conexão**: insira um nome para esta conexão. Os usuários finais verão esse nome quando navegarem na lista de conexões VPN disponíveis no dispositivo.
- **Servidores**: adicione um ou mais servidores VPN aos quais os dispositivos se conectarão. Quando você adiciona um servidor, insere as seguintes informações:
  - **Descrição**: insira um nome descritivo para o servidor como **Servidor VPN Contoso**
  - **Endereço IP ou FQDN**: insira o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam, como **192.168.1.1** ou **vpn.contoso.com**
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
  - **Always On**: escolha **Habilitar** para se conectar automaticamente à conexão VPN quando os seguintes eventos ocorrerem: 
    - Os usuários fazem logon em seus dispositivos
    - A rede no dispositivo muda
    - A tela do dispositivo é ativada novamente depois de ser desligada 

  - **Método de autenticação**: selecione o modo de autenticação desejado para os usuários no servidor VPN. Usar **certificados** fornece recursos avançados, como experiência sem toque, VPN sob demanda e VPN por aplicativo.
  - **Lembrar as credenciais a cada logon**: escolha para armazenar em cache as credenciais de autenticação.
  - **XML personalizado**: insira quaisquer comandos XML personalizados que configurem a conexão VPN.
  - **Xml EAP**: insira quaisquer comandos XML EAP que configurem a conexão VPN

### <a name="pulse-secure-example"></a>Exemplo de Pulse Secure

```
<pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

### <a name="f5-edge-client-example"></a>Exemplo de F5 Edge Client

```
<f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

### <a name="sonicwall-mobile-connect-example"></a>Exemplo do SonicWALL Mobile Connect
**Grupo de logon ou domínio**: essa propriedade não pode ser definida no perfil de VPN. Em vez disso, o Mobile Connect analisa esse valor quando o nome de usuário e domínio são inseridos nos formatos `username@domain` ou `DOMAIN\username`.

Exemplo:

```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

### <a name="checkpoint-mobile-vpn-example"></a>Exemplo de VPN Móvel de Ponto de Verificação

```
<CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

### <a name="writing-custom-xml"></a>Gravando XML personalizado
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

- **Lista de pesquisa de sufixos DNS**: nos **sufixos DNS**, insira um sufixo DNS e **Adicionar**. Você pode adicionar vários sufixos.

  Ao usar sufixos DNS, você pode procurar um recurso de rede usando o nome curto dele em vez do nome de domínio totalmente qualificado (FQDN). Ao pesquisar usando o nome curto, o sufixo é determinado automaticamente pelo servidor DNS. Por exemplo, `utah.contoso.com` está na lista de sufixos DNS. Você executa o ping `DEV-comp`. Nesse cenário, ele resolve para `DEV-comp.utah.contoso.com`.

  Sufixos DNS são resolvidos na ordem listada, e a ordem pode ser alterada. Por exemplo, `colorado.contoso.com` e `utah.contoso.com` estão na lista de sufixos DNS e ambos têm um recurso chamado `DEV-comp`. Como `colorado.contoso.com` é o primeiro na lista, ele é resolvido como `DEV-comp.colorado.contoso.com`.
  
  Para alterar a ordem, clique nos pontos à esquerda do sufixo DNS e, em seguida, arraste o sufixo para a parte superior:

  ![Selecione os três pontos e clique e arraste para mover o sufixo dns](./media/vpn-settings-windows-10/vpn-settings-windows10-move-dns-suffix.png)

- **Regras de tabela de políticas de resolução de nomes (NRPT)** : as regras de tabela de políticas de resolução de nomes (NRPT) definem como o DNS resolve nomes quando conectados à VPN. Depois que a conexão VPN for estabelecida, escolha quais servidores DNS serão usados pela conexão VPN.

  Você pode adicionar regras à tabela que incluem o domínio, o servidor DNS, o proxy e outros detalhes para resolver o domínio inserido. A conexão VPN usa essas regras quando os usuários se conectam aos domínios inseridos.

  Selecione **Adicionar** para adicionar uma nova regra. Para cada servidor, digite:

  - **Domínio**: insira o FQDN (nome de domínio totalmente qualificado) ou um sufixo DNS para aplicar a regra. Você também pode inserir um ponto (.) no início de um sufixo DNS. Por exemplo, insira `contoso.com` ou `.allcontososubdomains.com`.
  - **Servidores DNS**: insira o endereço IP ou o servidor DNS que resolve o domínio. Por exemplo, insira `10.0.0.3` ou `vpn.contoso.com`.
  - **Proxy**: insira o servidor proxy da Web que resolve o domínio. Por exemplo, insira `http://proxy.com`.
  - **Conectar-se automaticamente**: quando essa opção está **Habilitada**, o dispositivo se conecta automaticamente à VPN quando um dispositivo se conecta a um domínio inserido por você, por exemplo, `contoso.com`. Quando essa opção é definida como **Não configurado** (padrão), o dispositivo não se conecta automaticamente à VPN
  - **Persistente**: quando essa opção é definida como **Habilitado**, a regra permanece na NRPT (Tabela de Políticas de Resolução de Nomes) até que a regra seja removida manualmente do dispositivo, mesmo depois que a VPN é desconectada. Quando essa opção é definida como **Não configurado** (padrão), as regras da NRPT no perfil de VPN são removidas do dispositivo quando a VPN é desconectada.

## <a name="proxy-settings"></a>Configurações de proxy

- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Insira a **URL do servidor proxy**, como `http://proxy.contoso.com`, que inclui o arquivo de configuração.
- **Endereço**: digite o endereço do servidor proxy, como um endereço IP ou `vpn.contoso.com`
- **Número da porta**: insira o número da porta TCP usado pelo servidor proxy
- **Ignorar proxy para endereços locais**: se você não quiser usar um servidor proxy para endereços locais, escolha Habilitar. Essa configuração se aplicará se o servidor VPN exigir um servidor proxy para a conexão.

## <a name="split-tunneling"></a>Túnel Dividido

- **Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.
- **Rotas de túnel dividido para essa conexão VPN**: adicionar rotas opcionais para provedores VPN de terceiros. Insira um prefixo de destino e um tamanho de prefixo para cada conexão.

## <a name="trusted-network-detection"></a>Detecção de Rede Confiável

**Sufixos DNS de rede confiável**: quando os usuários já estão conectados a uma rede confiável, você pode impedir que os dispositivos se conectem automaticamente a outras conexões VPN.

Em **Sufixos DNS**, insira um sufixo DNS no qual deseja confiar, por exemplo, contoso.com, e selecione **Adicionar**. Você pode adicionar quantos sufixos desejar.

Se um usuário estiver conectado a um sufixo DNS na lista, ele não se conectará automaticamente a outra conexão VPN. O usuário continuará usando a lista confiável de sufixos DNS que você inserir. A rede confiável ainda será usada, mesmo se algum gatilho automático for definido.

Por exemplo, se o usuário já estiver conectado a um sufixo DNS confiável, os gatilhos automáticos a seguir serão ignorados. Especificamente, os sufixos DNS na lista cancelam todos os outros gatilhos automáticos de conexão, incluindo:

- Always On
- Gatilho baseado em aplicativo
- Gatilho automático de DNS

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de VPN em dispositivos [Android](vpn-settings-android.md), [iOS](vpn-settings-ios.md) e [macOS](vpn-settings-macos.md).
