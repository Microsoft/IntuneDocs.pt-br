---
title: Configurações VPN para dispositivos iOS no Microsoft Intune – Azure | Microsoft Docs
description: Exiba as definições de configuração de VPN (rede virtual privada) disponíveis, incluindo detalhes de conexão, métodos de autenticação e túnel dividido nas configurações de base; as configurações personalizadas de VPN com o identificador e os pares de chave e valor; as configurações de VPN por aplicativo que incluem URLs Safari e VPNs sob demanda com domínios de pesquisa SSIDs ou DNS; e as configurações de proxy para incluir um script de configuração, endereço IP ou FQDN e porta TCP no Microsoft Intune em dispositivos que executam o iOS.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 8/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: deb6a230573ff20237e6eee386052baba472832a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313863"
---
# <a name="configure-vpn-settings-in-microsoft-intune-for-devices-running-ios"></a>Definir as configurações de VPN no Microsoft Intune para dispositivos que executam o iOS

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo mostra as configurações do Intune que você pode usar para configurar conexões VPN em dispositivos que executam iOS.

Dependendo das configurações que você escolher, nem todos os valores na lista a seguir serão configuráveis.

## <a name="base-vpn-settings"></a>Configurações de VPN de base
As configurações reais exibidas na lista a seguir são determinadas pelo tipo de conexão VPN selecionado.  
- **Nome da conexão**: os usuários finais verão esse nome ao procurarem no dispositivo uma lista de conexões VPN disponíveis.
- **Nome de domínio personalizado** (somente Zscaler): preencha previamente o campo de entrada do aplicativo Zscaler com o domínio ao qual seus usuários pertencerem. Por exemplo, se um nome de usuário for **Joe@contoso.net**, o domínio **contoso.net** será exibido estaticamente no campo quando o aplicativo for aberto. Se você não digitar um nome de domínio, será usada a parte de domínio do UPN no Azure Active Directory.
- **Endereço IP ou FQDN**: o endereço IP ou o FQDN (nome de domínio totalmente qualificado) do servidor VPN ao qual os dispositivos se conectam. Por exemplo, insira **192.168.1.1** ou **vpn.contoso.com**. 
- **Nome da nuvem da organização** (Zscaler): digite o nome da nuvem em que sua organização está provisionada. Examine a URL usada para entrar no Zscaler para localizar o nome.  
- **Método de autenticação**: escolha como os dispositivos se autenticam no servidor VPN. 
  - **Certificados**: em **Certificado de autenticação**, selecione um perfil de certificado SCEP ou PKCS existente para autenticar a conexão. [Configurar certificados](certificates-configure.md) apresenta algumas diretrizes sobre perfis de certificado.
  - **Nome de usuário e senha**: os usuários finais deverão fornecer um nome de usuário e uma senha para entrar no servidor VPN.  

    > [!NOTE]
    > Se o nome de usuário e senha forem usados como o método de autenticação para a VPN IPsec Cisco, eles deverão fornecer o SharedSecret por meio de um perfil personalizado do Apple Configurator.
  
- **Tipo de conexão**: selecione o tipo de conexão VPN na lista de fornecedores a seguir:
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
  - **Zscaler**: exige que você integre o ZPA (Zscaler Private Access) à sua conta do Azure Active Directory. Para obter etapas detalhadas, confira a [Documentação do Zscaler](https://help.zscaler.com/zpa/configuration-example-microsoft-azure-ad#Azure_UserSSO). 
  - **VPN personalizado**    

    > [!NOTE]
    > A Cisco, a Citrix, a F5 e a Palo Alto anunciaram que seus clientes herdados não funcionarão mais na próxima versão do iOS 12. Você deve migrar para os novos aplicativos o quanto antes. Para obter mais informações, confira o [Microsoft Intune Support Team Blog](https://go.microsoft.com/fwlink/?linkid=2013806&clcid=0x409) (Blog da equipe de suporte do Microsoft Intune).

* **URLs excluídas** (somente Zscaler): quando conectadas à VPN do Zscaler, as URLs listadas podem ser acessadas de fora da nuvem do Zscaler. 

- **Túnel dividido**: **Habilite** ou **Desabilite** para permitir que os dispositivos decidam qual conexão usar dependendo do tráfego. Por exemplo, um usuário em um hotel usa a conexão VPN para acessar arquivos de trabalho, mas utiliza a rede padrão do hotel para navegação regular na Web.   

## <a name="custom-vpn-settings"></a>Configurações de VPN personalizado

Se você tiver selecionado **VPN Personalizada** como o tipo de conexão, defina as configurações a seguir. Essas configurações também são visíveis para conexões do Zscaler e do Citrix.

- **Identificador de VPN**: um identificador para o aplicativo VPN que você está usando, fornecido pelo seu provedor de VPN.
- **Inserir pares chave-valor para os atributos de VPN personalizados**: adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN. Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.

## <a name="automatic-vpn-settings"></a>Configurações automáticas de VPN

- **VPN por aplicativo**: escolher essa opção habilita a VPN por aplicativo, autorizando a conexão VPN a ser disparada de forma automática quando determinados aplicativos são abertos. Além de escolher essa opção, você também precisará associar os aplicativos a este perfil VPN. Veja mais detalhes nas [instruções para configurar a VPN por aplicativo para iOS](vpn-setting-configure-per-app.md). 
  - A configuração **Tipo de Provedor** só está disponível para Pulse Secure e VPN personalizada.
  - Ao usar um perfil **VPN para cada aplicativo** iOS com o Pulse Secure ou com uma VPN personalizada, você pode optar por usar o túnel de camada de aplicativo (proxy de aplicativo) ou o túnel no nível do pacote (túnel de pacote). Defina o valor de **ProviderType** para **proxy de aplicativo** para o túnel de camada de aplicativo ou **túnel de pacote** para o túnel de camada de pacote. Se você não tiver certeza de qual valor usar, confira a documentação do seu provedor de VPN. 
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
Se você estiver usando um proxy, defina as seguintes configurações. As configurações de proxy não estão disponíveis para conexões VPN do Zscaler.  

- **Script de configuração automática**: use um arquivo para configurar o servidor proxy. Digite a **URL do servidor proxy** (por exemplo, **http://proxy.contoso.com**) que contém o arquivo de configuração.
- **Endereço**: insira o endereço IP do nome do host totalmente qualificado do servidor proxy.
- **Número da porta**: insira o número da porta associada ao servidor proxy.

## <a name="next-step"></a>Próxima etapa
[Criar perfis de VPN no Intune](vpn-settings-configure.md)  
