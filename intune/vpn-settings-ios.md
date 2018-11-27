---
title: Adicionar configurações de VPN a dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Adicione ou crie um perfil de configuração de VPN usando definições de configuração de VPN (rede virtual privada), incluindo detalhes de conexão, métodos de autenticação e túnel dividido nas configurações de base; as configurações personalizadas de VPN com o identificador e os pares chave-valor; as configurações de VPN por aplicativo que incluem URLs Safari e VPNs sob demanda com domínios de pesquisa SSIDs ou DNS; e as configurações de proxy para incluir um script de configuração, endereço IP ou FQDN e porta TCP no Microsoft Intune em dispositivos que executam o iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/6/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: ea127fb72a2e24343185d06e26d883e1183e7c2b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185552"
---
# <a name="configure-vpn-settings-on-ios-devices-in-microsoft-intune"></a>Definir configurações de VPN em dispositivos iOS no Microsoft Intune

O Microsoft Intune inclui várias configurações de VPN que podem ser implantadas em dispositivos iOS. Essas configurações são usadas para criar e configurar conexões VPN à rede da sua organização. Este artigo descreve essas configurações. Algumas configurações só estão disponíveis para alguns clientes VPN, como Citrix, Zscaler e outros.

## <a name="connection-type"></a>Tipo de conexão

Selecione o tipo de conexão VPN na lista de fornecedores a seguir:

- **Check Point Capsule VPN**
- **Cisco AnyConnect Herdado**: aplicável ao aplicativo [Cisco AnyConnect Herdado](https://itunes.apple.com/app/cisco-legacy-anyconnect/id392790924) versão 4.0.5x e a versões anteriores.
- **Cisco AnyConnect**: aplicável ao aplicativo [Cisco AnyConnect](https://itunes.apple.com/app/cisco-anyconnect/id1135064690) versão 4.0.7x e a versões posteriores.
- **SonicWall Mobile Connect**
- **F5 Access Herdado**: aplicável ao aplicativo F5 Access versão 2.1 e a versões anteriores.
- **F5 Access**: aplicável ao aplicativo F5 Access versão 3.0 e posteriores.
- **GlobalProtect da Palo Alto Networks (Herdado)**: aplicável ao aplicativo GlobalProtect da Palo Alto Networks versão 4.1 e a versões anteriores.
- **GlobalProtect da Palo Alto Networks**: aplicável ao aplicativo GlobalProtect da Palo Alto Networks versão 5.0 e posteriores.
- **Pulse Secure**
- **Cisco (IPsec)**
- **Citrix VPN**
- **SSO da Citrix**
- **Zscaler**: exige que você integre o ZPA (Zscaler Private Access) à sua conta do Azure AD. Para obter etapas detalhadas, confira a [Documentação do Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
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
  - **Certificados**: em **Certificado de autenticação**, selecione um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. [Configurar certificados](certificates-configure.md) apresenta algumas diretrizes sobre perfis de certificado.
  - **Nome de usuário e senha**: os usuários finais deverão fornecer um nome de usuário e uma senha para entrar no servidor VPN.  

    > [!NOTE]
    > Se o nome de usuário e senha forem usados como o método de autenticação para a VPN IPsec Cisco, eles deverão fornecer o SharedSecret por meio de um perfil personalizado do Apple Configurator.

- **URLs excluídas** (somente Zscaler): quando conectadas à VPN do Zscaler, as URLs listadas podem ser acessadas de fora da nuvem do Zscaler. 

- **Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.

- **Identificador de VPN** (VPN personalizada, Zscaler e Citrix): um identificador do aplicativo de VPN que você está usando, fornecido pelo seu provedor de VPN.
  - **Inserir pares chave-valor para os atributos de VPN personalizados**: adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Lembre-se de que esses valores geralmente são fornecidos pelo seu provedor de VPN.

- **Habilitar o controle de acesso à rede (NAC)** (somente Citrix SSO): quando você escolhe **Concordo**, a ID do dispositivo é incluída no perfil da VPN. Essa ID pode ser usada para autenticação da VPN para permitir ou impedir o acesso à rede.

  **Ao usar o Citrix SSO com Gateway**, lembre-se de:

  - Confirmar se você está usando o Citrix Gateway 12.0.59 ou superior.
  - Confirmar se os usuários têm o SSO do Citrix 1.1.6 ou posterior instalado em seus dispositivos.
  - Integrar o Citrix Gateway com o Intune para NAC, como descrito em [Integração do Microsoft Intune/Enterprise Mobility + Security E3 com NetScaler (Cenário LDAP+OTP)](https://www.citrix.com/content/dam/citrix/en_us/documents/guide/integrating-microsoft-intune-enterprise-mobility-suite-with-netscaler.pdf) no guia de implantação do Citrix.
  - Habilite o NAC no perfil da VPN.

  Detalhes importantes:  

  - Quando o NAC estiver habilitado, a VPN será desconectada a cada 24 horas.
  - A ID do dispositivo faz parte do perfil, mas não pode ser vista no Intune. Essa ID não é armazenada em nenhum lugar pela Microsoft e não é compartilhada pela Microsoft. Depois que isso tiver suporte dos parceiros VPN, o cliente VPN, como SSO Citrix, poderá obter a ID e consultar o Intune para confirmar se o dispositivo está registrado e se o perfil de VPN está ou não em conformidade.
  - Para remover essa configuração, recrie o perfil e não selecione **Eu concordo**. Em seguida, reatribua o perfil.

## <a name="automatic-vpn-settings"></a>Configurações automáticas de VPN

- **VPN por aplicativo**: habilita a VPN por aplicativo. Permite que a conexão VPN sejam disparadas automaticamente quando determinados aplicativos são abertos. Também associe os aplicativos a esse perfil de VPN. Para obter mais informações, confira [instruções para configurar a VPN por aplicativo para iOS](vpn-setting-configure-per-app.md).
  - **Tipo de Provedor**: disponível somente para Pulse Secure e VPN Personalizada.
  - Ao usar um perfil **VPN para cada aplicativo** iOS com o Pulse Secure ou com uma VPN personalizada, opte por usar o túnel de camada de aplicativo (proxy de aplicativo) ou o túnel no nível do pacote (túnel de pacote). Defina o valor de **ProviderType** como **app-proxy** para o túnel de camada de aplicativo ou como **packet-tunnel** para o túnel de camada de pacote. Se você não tiver certeza de qual valor usar, verifique a documentação do seu provedor VPN.
  - **URLs do Safari que dispararão esta VPN**: adicione uma ou mais URLs de site. Quando essas URLs forem acessadas usando o navegador Safari no dispositivo, a conexão VPN será estabelecida automaticamente.

- **VPN sob demanda**: configure regras condicionais que controlem quando a conexão VPN é iniciada. Por exemplo, crie uma condição em que a conexão VPN é usada somente quando um dispositivo não está conectado a uma rede Wi-Fi da empresa. Ou crie uma condição em que, se um dispositivo não puder acessar um domínio de pesquisa DNS inserido, a conexão VPN não será iniciada.

  - **Domínios de pesquisa de DNS ou SSIDs**: selecione se essa condição usa **SSIDs** de rede sem fio ou **domínios de pesquisa de DNS**. Escolha **Adicionar** para configurar um ou mais SSIDs ou domínios de pesquisa.
  - **Investigação de cadeia de caracteres de URL**: opcional. Insira uma URL que a regra use como teste. Se o dispositivo com esse perfil acessar essa URL sem redirecionamento, a conexão VPN será iniciada. E o dispositivo se conectará à URL de destino. O usuário não verá o site da investigação de cadeia de caracteres da URL. Um exemplo de uma investigação de cadeia de caracteres de URL é o endereço de um servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN. Outra possibilidade é que a URL teste a capacidade da VPN de conectar-se a um site, antes de conectar o dispositivo à URL de destino por meio da VPN.
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

## <a name="next-step"></a>Próxima etapa
[Criar perfis de VPN no Intune](vpn-settings-configure.md)  
