---
title: Definir configurações de VPN a dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de VPN usando definições de configuração de VPN (rede virtual privada), incluindo detalhes de conexão, métodos de autenticação e túnel dividido nas configurações de base; as configurações personalizadas de VPN com o identificador e os pares chave-valor; as configurações de VPN por aplicativo que incluem URLs Safari e VPNs sob demanda com domínios de pesquisa SSIDs ou DNS; e as configurações de proxy para incluir um script de configuração, endereço IP ou FQDN e porta TCP no Microsoft Intune em dispositivos que executam o iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/13/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e45d51feb91e0e188971133185ac0f0f13e5b1f4
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74781134"
---
# <a name="add-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Adicionar configurações de VPN em dispositivos iOS no Microsoft Intune

O Microsoft Intune inclui várias configurações de VPN que podem ser implantadas em dispositivos iOS. Essas configurações são usadas para criar e configurar conexões VPN à rede da sua organização. Este artigo descreve essas configurações. Algumas configurações só estão disponíveis para alguns clientes VPN, como Citrix, Zscaler e outros.

## <a name="before-you-begin"></a>Antes de começar

[Crie um perfil de configuração do dispositivo](vpn-settings-configure.md).

> [!NOTE]
> Essas configurações estão disponíveis para todos os tipos de registro. Para obter mais informações sobre os tipos de registro, consulte [registro do IOS](../enrollment/ios-enroll.md).

## <a name="connection-type"></a>Tipo de conexão

Selecione o tipo de conexão VPN na lista de fornecedores a seguir:

- **Check Point Capsule VPN**
- **Cisco AnyConnect Herdado**: aplicável ao aplicativo [Cisco AnyConnect Herdado](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) versão 4.0.5x e a versões anteriores.
- **Cisco AnyConnect**: aplicável ao aplicativo [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) versão 4.0.7x e a versões posteriores.
- **SonicWall Mobile Connect**
- **F5 Access Herdado**: aplicável ao aplicativo F5 Access versão 2.1 e a versões anteriores.
- **F5 Access**: aplicável ao aplicativo F5 Access versão 3.0 e posteriores.
- **GlobalProtect da Palo Alto Networks (Herdado)** : aplicável ao aplicativo GlobalProtect da Palo Alto Networks versão 4.1 e a versões anteriores.
- **GlobalProtect da Palo Alto Networks**: aplicável ao aplicativo GlobalProtect da Palo Alto Networks versão 5.0 e posteriores.
- **Pulse Secure**
- **Cisco (IPsec)**
- **Citrix VPN**
- **SSO da Citrix**
- **Zscaler**: para usar o Acesso Condicional ou permitir que os usuários ignorem a tela de entrada do Zscaler, é necessário integrar o ZPA (Acesso Privado do Zscaler) à sua conta do Azure AD. Para obter etapas detalhadas, confira a [Documentação do Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad). 
- **IKEv2**: [as configurações IKEv2](#ikev2-settings) (neste artigo) descrevem as propriedades.
- **VPN personalizado**

> [!NOTE]
> Cisco, Citrix, F5 e Palo Alto anunciaram que seus clientes herdados não funcionam no iOS 12. Você deve migrar para os novos aplicativos o quanto antes. Para obter mais informações, confira o [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) (Blog da equipe de suporte do Microsoft Intune).

## <a name="base-vpn-settings"></a>Configurações de VPN de base

As configurações mostradas na lista a seguir são determinadas pelo tipo de conexão de VPN escolhido.  

- **Nome da conexão**: os usuários finais verão esse nome ao procurarem no dispositivo uma lista de conexões VPN disponíveis.
- **Nome de domínio personalizado** (somente Zscaler): preencha previamente o campo de entrada do aplicativo Zscaler com o domínio ao qual seus usuários pertencerem. Por exemplo, se for um nome de usuário `Joe@contoso.net`, o domínio `contoso.net` aparecerá estaticamente no campo quando o aplicativo for aberto. Se você não inserir um nome de domínio, a parte do domínio do UPN no Azure AD (Active Directory) será usada.
- **Endereço IP ou FQDN**: o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam. Por exemplo, insira `192.168.1.1` ou `vpn.contoso.com`.
- **Nome da nuvem da organização** (somente Zscaler): insira o nome da nuvem em que sua organização está provisionada. A URL usada para entrar no Zscaler tem o nome.  
- **Método de autenticação**: escolha como os dispositivos se autenticam no servidor VPN. 
  - **Certificados**: em **Certificado de autenticação**, selecione um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. [Configurar certificados](../protect/certificates-configure.md) apresenta algumas diretrizes sobre perfis de certificado.
  - **Nome de usuário e senha**: os usuários finais deverão fornecer um nome de usuário e uma senha para entrar no servidor VPN.  

    > [!NOTE]
    > Se o nome de usuário e senha forem usados como o método de autenticação para a VPN IPsec Cisco, eles deverão fornecer o SharedSecret por meio de um perfil personalizado do Apple Configurator.

  - **Credencial derivada**: Use um certificado derivado do cartão inteligente de um usuário. Se nenhum emissor de credencial derivado estiver configurado, o Intune solicitará que você adicione um. Para obter mais informações, consulte [usar credenciais derivadas no Microsoft Intune](../protect/derived-credentials.md).

- **URLs excluídas** (somente Zscaler): quando conectadas à VPN do Zscaler, as URLs listadas podem ser acessadas de fora da nuvem do Zscaler. 

- **Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.

- **Identificador de VPN** (VPN personalizada, Zscaler e Citrix): um identificador do aplicativo de VPN que você está usando e é fornecido pelo seu provedor de VPN.
  - **Inserir pares chave-valor para os atributos de VPN personalizados**: adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Lembre-se de que esses valores geralmente são fornecidos pelo seu provedor de VPN.

- **Habilitar o NAC (controle de acesso à rede)** (Citrix SSO, Acesso por F5): quando você escolhe **Concordo**, a ID do dispositivo é incluída no perfil da VPN. Essa ID pode ser usada para autenticação da VPN para permitir ou impedir o acesso à rede.

  **Ao usar o Acesso por F5**:

  - Confirme se você está usando F5 BIG-IP 13.1.1.5. O BIG-IP 14 não é compatível.
  - Integre o BIG-IP ao Intune para NAC. Confira o guia do F5 [Overview: Configuring APM for device posture checks with endpoint management systems](https://support.f5.com/kb/en-us/products/big-ip_apm/manuals/product/apm-client-configuration-7-1-6/6.html#guid-0bd12e12-8107-40ec-979d-c44779a8cc89) (Visão geral: como configurar o APM para verificações de postura do dispositivo com sistemas de gerenciamento de ponto de extremidade).
  - Habilite o NAC no perfil da VPN.

  **Ao usar o Citrix SSO com Gateway**, lembre-se de:

  - Confirmar se você está usando o Citrix Gateway 12.0.59 ou superior.
  - Confirmar se os usuários têm o SSO do Citrix 1.1.6 ou posterior instalado em seus dispositivos.
  - Integre o Citrix Gateway ao Intune para NAC. Confira o guia de implantação do Citrix [Como integrar o Microsoft Intune/Enterprise Mobility Suite com NetScaler (Cenário LDAP+OTP)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf).
  - Habilite o NAC no perfil da VPN.

  **Detalhes importantes**:  

  - Quando o NAC estiver habilitado, a VPN será desconectada a cada 24 horas. A VPN pode ser reconectada imediatamente.
  - A ID do dispositivo faz parte do perfil, mas não é mostrada no Intune. Essa ID não é armazenada em nenhum lugar pela Microsoft e não é compartilhada pela Microsoft.

  Para parceiros VPN que dão suporte à ID do dispositivo, o cliente VPN, como o Citrix SSO, pode obter a ID. Em seguida, ela poderá consultar o Intune para confirmar se o dispositivo está registrado e se o perfil de VPN está em conformidade ou não.

  - Para remover essa configuração, recrie o perfil e não selecione **Eu concordo**. Em seguida, reatribua o perfil.

## <a name="ikev2-settings"></a>Configurações IKEv2

Essas configurações se aplicam quando você escolhe o **tipo de conexão** > **IKEv2**.

- **Identificador remoto**: Insira o endereço IP da rede, o FQDN, o userfqdn ou o ASN1DN do servidor IKEv2. Por exemplo, insira `10.0.0.3` ou `vpn.contoso.com`. Normalmente, você insere o mesmo valor que o [**nome da conexão**](#base-vpn-settings) (neste artigo). Mas, isso depende de suas configurações de servidor IKEv2.

- **Tipo de autenticação de cliente**: escolha como o cliente VPN é autenticado para a VPN. Suas opções:
  - **Autenticação de usuário** (padrão): as credenciais de usuário são autenticadas para a VPN.
  - **Autenticação de computador**: as credenciais de dispositivo são autenticadas para a VPN.

- **Método de autenticação**: escolha o tipo de credenciais de cliente para enviar ao servidor. Suas opções:
  - **Certificados**: usa um perfil de certificado existente para autenticar para a VPN. Verifique se esse perfil de certificado já está atribuído ao usuário ou dispositivo. Caso contrário, a conexão VPN falhará.
    - **Tipo de certificado**: selecione o tipo de criptografia usado pelo certificado. Verifique se o servidor VPN está configurado para aceitar esse tipo de certificado. Suas opções:
      - **RSA** (padrão)
      - **ECDSA256**
      - **ECDSA384**
      - **ECDSA521**

  - **Nome de usuário e senha** (somente autenticação de usuários): quando os usuários se conectam à VPN, eles recebem seu nome de usuário e senha.
  - **Segredo compartilhado** (somente autenticação do computador): permite que você insira um segredo compartilhado para enviar ao servidor VPN.
    - **Segredo compartilhado**: Insira o segredo compartilhado, também conhecido como chave pré-compartilhada (PSK). Verifique se o valor corresponde ao segredo compartilhado configurado no servidor VPN.

- **Nome comum do emissor do certificado do servidor**: permite que o servidor VPN se autentique no cliente VPN. Insira o nome comum do emissor do certificado (CN) do certificado do servidor VPN que é enviado para o cliente VPN no dispositivo. Verifique se o valor CN corresponde à configuração no servidor VPN. Caso contrário, a conexão VPN falhará.
- **Nome comum do certificado do servidor**: Insira o CN para o próprio certificado. Se for deixado em branco, o valor do identificador remoto será usado.

- **Taxa de detecção de pares inativos**: escolha a frequência com que o cliente VPN verifica se o túnel VPN está ativo. Suas opções:
  - **Não configurado**: usa o padrão do sistema Ios, que pode ser o mesmo que escolher **médio**.
  - **Nenhum**: desabilita a detecção de pares inativos.
  - **Baixo**: envia uma mensagem de KeepAlive a cada 30 minutos.
  - **Médio** (padrão): envia uma mensagem de KeepAlive a cada 10 minutos.
  - **Alta**: envia uma mensagem de KeepAlive a cada 60 segundos.

- **Intervalo de versão do TLS mínimo**: Insira a versão mínima do TLS a ser usada. Insira `1.0`, `1.1`ou `1.2`. Se for deixado em branco, o valor padrão de `1.0` será usado.
- **Intervalo de versão do TLS máximo**: Insira a versão máxima do TLS a ser usada. Insira `1.0`, `1.1`ou `1.2`. Se for deixado em branco, o valor padrão de `1.2` será usado.
- **Sigilo perfeita no encaminhamento**: selecione **habilitar** para ativar o PFS (PFS de encaminhamento). O PFS é um recurso de segurança IP que reduz o impacto se uma chave de sessão for comprometida. **Desabilitar** (padrão) não usa PFS.
- **Verificação de revogação de certificado**: selecione **habilitar** para garantir que os certificados não sejam revogados antes de permitir que a conexão VPN seja realizada com sucesso. Essa verificação é de melhor esforço. Se o servidor VPN expirar antes de determinar se o certificado foi revogado, o acesso será concedido. **Desabilitar** (padrão) não verifica se há certificados revogados.

- **Configurar parâmetros de associação de segurança**: **não configurado** (padrão) usa o padrão do sistema Ios. Selecione **habilitar** para inserir os parâmetros usados ao criar associações de segurança com o servidor VPN:
  - **Algoritmo de criptografia**: selecione o algoritmo desejado:
    - DES
    - 3DES
    - AES-128
    - AES-256 (padrão)
    - AES-128-GCM
    - AES-256-GCM
  - **Algoritmo de integridade**: selecione o algoritmo desejado:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (padrão)
    - SHA2-384
    - SHA2-512
  - **Grupo Diffie-Hellman**: selecione o grupo desejado. O padrão é `2`de grupo.
  - **Tempo de vida** (minutos): escolha por quanto tempo a associação de segurança permanecerá ativa até que as chaves sejam giradas. Insira um valor inteiro entre `10` e `1440` (1440 minutos é 24 horas). O padrão é `1440`.

- **Configurar um conjunto separado de parâmetros para associações de segurança filho**: o Ios permite que você configure parâmetros separados para a conexão Ike e quaisquer conexões filho. 

  **Não configurado** (padrão) usa os valores inseridos na configuração anterior **definir parâmetros de associação de segurança** . Selecione **habilitar** para inserir os parâmetros usados ao criar associações de segurança *filho* com o servidor VPN:
  - **Algoritmo de criptografia**: selecione o algoritmo desejado:
    - DES
    - 3DES
    - AES-128
    - AES-256 (padrão)
    - AES-128-GCM
    - AES-256-GCM
  - **Algoritmo de integridade**: selecione o algoritmo desejado:
    - SHA1-96
    - SHA1-160
    - SHA2-256 (padrão)
    - SHA2-384
    - SHA2-512
  - **Grupo Diffie-Hellman**: selecione o grupo desejado. O padrão é `2`de grupo.
  - **Tempo de vida** (minutos): escolha por quanto tempo a associação de segurança permanecerá ativa até que as chaves sejam giradas. Insira um valor inteiro entre `10` e `1440` (1440 minutos é 24 horas). O padrão é `1440`.

## <a name="automatic-vpn-settings"></a>Configurações automáticas de VPN

- **VPN por aplicativo**: habilita a VPN por aplicativo. Permite que a conexão VPN sejam disparadas automaticamente quando determinados aplicativos são abertos. Também associe os aplicativos a esse perfil de VPN. Não há suporte para VPN por aplicativo em IKEv2. Para obter mais informações, confira [instruções para configurar a VPN por aplicativo para iOS](vpn-setting-configure-per-app.md). 
  - **Tipo de Provedor**: disponível somente para Pulse Secure e VPN Personalizada.
  - Ao usar um perfil **VPN para cada aplicativo** iOS com o Pulse Secure ou com uma VPN personalizada, opte por usar o túnel de camada de aplicativo (proxy de aplicativo) ou o túnel no nível do pacote (túnel de pacote). Defina o valor de **ProviderType** como **app-proxy** para o túnel de camada de aplicativo ou como **packet-tunnel** para o túnel de camada de pacote. Se você não tiver certeza de qual valor usar, verifique a documentação do seu provedor VPN.
  - **URLs do Safari que dispararão esta VPN**: adicione uma ou mais URLs de site. Quando essas URLs forem acessadas usando o navegador Safari no dispositivo, a conexão VPN será estabelecida automaticamente.

- **VPN sob demanda**: configure regras condicionais que controlem quando a conexão VPN é iniciada. Por exemplo, crie uma condição em que a conexão VPN é usada somente quando um dispositivo não está conectado a uma rede Wi-Fi da empresa. Ou crie uma condição. Por exemplo, se um dispositivo não puder acessar um domínio de pesquisa DNS, a conexão VPN não será iniciada.

  - **Domínios de pesquisa de DNS ou SSIDs**: selecione se essa condição usa **SSIDs** de rede sem fio ou **domínios de pesquisa de DNS**. Escolha **Adicionar** para configurar um ou mais SSIDs ou domínios de pesquisa.
  - **Investigação de cadeia de caracteres de URL**: opcional. Insira uma URL que a regra use como teste. Se o dispositivo acessar essa URL sem redirecionamento, a conexão VPN será iniciada. E o dispositivo se conectará à URL de destino. O usuário não verá o site da investigação de cadeia de caracteres da URL.

    Por exemplo, uma investigação de cadeia de caracteres de URL é uma URL de servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN. Ou, a URL testa a capacidade da VPN de se conectar a um site antes de conectar o dispositivo à URL de destino por meio da VPN.
.
  - **Ação de domínio**: escolha um dos seguintes itens:
    - Conectar se necessário
    - Nunca conectar
  - **Ação**: escolha um dos seguintes itens:
    - Connect
    - Avaliar a conexão
    - Ignorar
    - Desconectar

## <a name="proxy-settings"></a>Configurações de proxy

Se você estiver usando um proxy, defina as seguintes configurações. As configurações de proxy não estão disponíveis para conexões VPN do Zscaler.  

- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, `http://proxy.contoso.com`) que inclui o arquivo de configuração.
- **Endereço**: insira o endereço IP do nome do host totalmente qualificado do servidor proxy.
- **Número da porta**: insira o número da porta associada ao servidor proxy.

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](device-profile-assign.md) e [monitore seu status](device-profile-monitor.md).

Defina as configurações de VPN em dispositivos [Android](vpn-settings-android.md), [Android Enterprise](vpn-settings-android-enterprise.md), [MacOS](vpn-settings-macos.md)e [Windows 10](vpn-settings-windows-10.md) .
