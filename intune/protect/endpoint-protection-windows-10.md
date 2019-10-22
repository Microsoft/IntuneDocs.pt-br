---
title: Configurações de proteção para dispositivos Windows 10 no Microsoft Intune – Azure | Microsoft Docs
description: Em dispositivos Windows 10, use ou defina as configurações de proteção de ponto de extremidade para habilitar recursos do Windows Defender, incluindo o Application Guard, Firewall, SmartScreen, criptografia e BitLocker, Exploit Guard, Controle de Aplicativos, Central de Segurança e segurança em dispositivos locais no Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/08/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: karthig
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40865dcca0b0109ae36f65b6691672c0035732b5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502276"
---
# <a name="windows-10-and-later-settings-to-protect-devices-using-intune"></a>Configurações do Windows 10 (e posterior) para proteger dispositivos usando o Intune  

[!INCLUDE [azure_portal](../includes/azure_portal.md)]  

O Microsoft Intune inclui muitas configurações para ajudar a proteger seus dispositivos. Este artigo descreve todas as configurações que você pode habilitar e definir em dispositivos Windows 10 e mais recente. Essas configurações são criadas em um perfil de configuração do Endpoint Protection no Intune para controle da segurança, incluindo o BitLocker e o Windows Defender.  

Para configurar o Windows Defender Antivírus, confira [Restrições de dispositivo do Windows 10](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).  

## <a name="before-you-begin"></a>Antes de começar  

[Crie um perfil de configuração do dispositivo do Endpoint Protection](endpoint-protection-configure.md).  

Para obter mais informações sobre provedores de serviços de configuração (CSPs), consulte [referência do provedor de serviços de configuração](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).  

## <a name="windows-defender-application-guard"></a>Windows Defender Application Guard  

Ao usar o Microsoft Edge, o Windows Defender Application Guard protege seu ambiente contra sites que não são confiáveis para sua organização. Quando os usuários visitam sites que não estão listados no limite de rede isolada, os sites são abertos em uma sessão de navegação virtual do Hyper-V. Os sites confiáveis são definidos por um limite de rede, que são configurados em Configuração do Dispositivo.  

O Application Guard só está disponível para dispositivos Windows 10 (64 bits). Usar esse perfil instala um componente do Win32 para ativar o Application Guard.  

- **Application Guard**  
  **Padrão**: não configurado  
   CSP do Application Guard: [configurações/AllowWindowsDefenderApplicationGuard](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#allowwindowsdefenderapplicationguard)  

  - **Habilitado para Edge** – ative esse recurso, que abre sites não confiáveis em um contêiner de navegação virtualizado do Hyper-V.  
  - **Não configurado** -qualquer site (confiável e não confiável) pode ser aberto no dispositivo.  

- **Comportamento da área de transferência**  
  **Padrão**: não configurado  
   CSP do Application Guard: [configurações/ClipboardSettings](https://go.microsoft.com/fwlink/?linkid=872351)  

  Escolha quais ações de copiar e colar são permitidas entre o computador local e o navegador virtual do Application Guard.  
  - **Não configurado**  
  - **Permitir copiar e colar do PC para o navegador somente**  
  - **Permitir copiar e colar do navegador para o PC somente**  
  - **Permitir copiar e colar entre PC e navegador**  
  - **Bloquear copiar e colar entre PC e navegador**  

- **Conteúdo da área de transferência**  
  Essa configuração está disponível somente quando o *comportamento da área de transferência* é definido como uma das configurações de *permissão* .  
  **Padrão**: não configurado  
  CSP do Application Guard: [configurações/ClipboardFileType](https://docs.microsoft.com/windows/client-management/mdm/windowsdefenderapplicationguard-csp#clipboardfiletype)  

  Selecione o conteúdo da área de transferência permitido.  
  - **Não configurado**  
  - **Text**  
  - **Imagens**  
  - **Texto e imagens**  

- **Conteúdo externo em sites empresariais**  
  **Padrão**: não configurado  
  CSP do Application Guard: [configurações/BlockNonEnterpriseContent](https://go.microsoft.com/fwlink/?linkid=872352)  

  - **Bloquear** – impede o carregamento do conteúdo de sites não aprovados.  
  - **Não configurado** – permite abrir sites não empresariais no dispositivo.  
 
- **Imprimir por meio do navegador virtual**  
  **Padrão**: não configurado  
  CSP do Application Guard: [configurações/PrintingSettings](https://go.microsoft.com/fwlink/?linkid=872354)  

  - **Permitir** – permite a impressão do conteúdo selecionado do navegador virtual.  
  - **Não configurado** Desabilitar todos os recursos de impressão.  

  Ao *permitir* a impressão, você pode definir a seguinte configuração:
  - **Tipo (s) de impressão** Selecione uma ou mais das seguintes opções:  
    - PDF  
    - XPS  
    - Impressoras locais
    - Impressoras de rede  

- **Coletar logs**  
  **Padrão**: não configurado  
  CSP do Application Guard: [auditoria/AuditApplicationGuard](https://go.microsoft.com/fwlink/?linkid=872418)  

  - **Permitir** – coleta logs de eventos que ocorrem em uma sessão de navegação do Application Guard.  
  - **Não configurado** – não coleta logs na sessão de navegação.  

- **Manter os dados do navegador gerados pelo usuário**  
  **Padrão**: não configurado  
  CSP do Application Guard: [configurações/AllowPersistence](https://go.microsoft.com/fwlink/?linkid=872419)  

  - **Permitir** salva os dados do usuário (como senhas, favoritos e cookies) criados durante uma sessão de navegação virtual do Application Guard.  
  - **Não configurado** descarta os dados e arquivos baixados pelo usuário quando o dispositivo é reiniciado ou quando um usuário sai do serviço.  

- **Aceleração gráfica**  
 **Padrão**: não configurado  
  CSP do Application Guard: [configurações/AllowVirtualGPU](https://go.microsoft.com/fwlink/?linkid=872420)  
      
  - **Habilitar** – carrega mais rapidamente sites e vídeos com uso intenso de elementos gráficos ao obter acesso a uma unidade de processamento gráfico virtual.  
  - **Não configurado** Use a CPU do dispositivo para gráficos; Não use a unidade de processamento gráfico virtual.  

- **Baixar arquivos no sistema de arquivos host**  
  **Padrão**: não configurado  
  CSP do Application Guard: [configurações/SaveFilesToHost](https://go.microsoft.com/fwlink/?linkid=872421)  

  - **Habilitar** – permite que os usuários baixem arquivos do navegador virtualizado no sistema operacional do host.  
  - **Não configurado** – mantém os arquivos localmente no dispositivo e não baixa arquivos no sistema de arquivos de host.  

## <a name="windows-defender-firewall"></a>Windows Defender Firewall  
 
### <a name="global-settings"></a>Configurações globais  

Essas configurações são aplicáveis a todos os tipos de rede.  

- **Protocolo FTP**  
  **Padrão**: não configurado  
   CSP do firewall: [MdmStore/global/DisableStatefulFtp](https://go.microsoft.com/fwlink/?linkid=872536)  

  - **Bloquear** – desabilita o FTP com estado.  
  - **Não configurado** – o firewall realiza a filtragem do FTP com estado para permitir conexões secundárias.  

- **Tempo ocioso da associação de segurança antes da exclusão**  
  **Padrão**: *não configurado*  
   CSP do firewall: [MdmStore/global/SaIdleTime](https://go.microsoft.com/fwlink/?linkid=872539)  

   Especifique um tempo ocioso em segundos, após o qual as associações de segurança são excluídas.   

- **Codificação de chave pré-compartilhada**  
  **Padrão**: não configurado  
   CSP do firewall: [MdmStore/global/PresharedKeyEncoding](https://go.microsoft.com/fwlink/?linkid=872541)  

   - **Enable** -codificar chaves distorcedas usando UTF-8.  
   - **Não configurado** – codifique chaves distorcidos usando o valor do repositório local.  

- **Isenções do IPsec**  
  **Padrão**: *0 selecionado*  
   CSP do firewall: [MdmStore/global/IPsecExempt](https://go.microsoft.com/fwlink/?linkid=872547)

   Selecione um ou mais dos seguintes tipos de tráfego a serem isentos do IPsec:  
   - **Códigos de tipo ICMP do IPv6 de descoberta de vizinho**  
   - **ICMP**  
   - **Códigos de tipo ICMP do IPv6 de descoberta de roteador**  
   - **Tráfego de rede DHCP do IPv4 e IPv6**  

- **Verificação da lista de certificados revogados**  
  **Padrão**: não configurado  
  CSP do firewall: [MdmStore/global/CRLcheck](https://go.microsoft.com/fwlink/?linkid=872548)  

  Escolha como o dispositivo verifica a lista de certificados revogados. As opções incluem:  
  - **Desabilitar verificação de CRL**  
  - **Falha na verificação de CRL somente no certificado revogado**  
  - **Falha na verificação de CRL em qualquer erro encontrado**.  
 

- **Encontrar uma correspondência oportuna de conjunto de autenticação por módulo de chave**  
  **Padrão**: não configurado  
  CSP do firewall: [MdmStore/global/OpportunisticallyMatchAuthSetPerKM](https://go.microsoft.com/fwlink/?linkid=872550)  
  
  - **Habilitar** – força os módulos de chave a ignorar somente os conjuntos de autenticação aos quais eles não dão suporte.  
  - **Não configurado** – os módulos para chave deverão ignorar o conjunto completo de autenticação se eles não derem suporte a todos os pacotes de autenticação especificados no conjunto.  


- **Enfileiramento de pacotes**  
  **Padrão**: não configurado  
  CSP do firewall: [MdmStore/global/EnablePacketQueue](https://go.microsoft.com/fwlink/?linkid=872551)  

  Especifique como o dimensionamento de software no lado do recebimento é habilitado para o recebimento criptografado e o encaminhamento de texto não criptografado para o cenário de gateway de túnel IPsec. Essa configuração confirma que a ordem de pacote é preservada. As opções incluem:  
  - **Não configurado**  
  - **Desabilitar todos os enfileiramentos de pacotes**  
  - **Enfileirar somente pacotes criptografados de entrada**  
  - **Os pacotes de fila após a descriptografia são executados somente para encaminhamento**  
  - **Configurar pacotes de entrada e de saída**  

### <a name="network-settings"></a>Configurações de rede  

As configurações a seguir são listadas neste artigo uma única vez, mas todas se aplicam aos três tipos de rede específicos:  
- **Rede de domínio (local de trabalho)**  
- **Rede privada (detectável)**  
- **Rede pública (não detectável)**  

#### <a name="general-settings"></a>Configurações gerais  

- **Windows Defender Firewall**  
  **Padrão**: não configurado  
  CSP do firewall: [EnableFirewall](https://go.microsoft.com/fwlink/?linkid=872558)  
  
  - **Habilitar** – ativa o firewall e a segurança avançada. 
  - **Não configurado** permite todo o tráfego de rede, independentemente de outras configurações de política.  

- **Modo oculto**  
  **Padrão**: não configurado  
  CSP do firewall: [DisableStealthMode](https://go.microsoft.com/fwlink/?linkid=872559)  
  - **Não configurado**  
  - O **bloqueio** do firewall está impedido de operar no modo furtivo. O bloqueio do modo furtivo permite bloquear também a **Isenção de pacote protegido por IPsec**.  
  - **Permitir** -o firewall opera no modo furtivo, o que ajuda a evitar respostas para solicitações de investigação.  

- **Isenção de pacote protegido por IPsec com modo furtivo**  
  **Padrão**: não configurado  
  CSP do firewall: [DisableStealthModeIpsecSecuredPacketExemption](https://go.microsoft.com/fwlink/?linkid=872560)  

  Essa opção será ignorada se o *modo stealth* estiver definido como *Bloquear*.  

  - **Não configurado**  
  - **Bloquear** -os pacotes protegidos por IPsec não recebem isenções.  
  - **Permitir** -habilitar isenções. O modo stealth do firewall não deve impedir que o computador host responda ao tráfego de rede não solicitado que é protegido pelo IPsec.  

- **Blindado**  
  **Padrão**: não configurado  
  CSP do firewall: [blindado](https://go.microsoft.com/fwlink/?linkid=872561)  
    - **Não configurado**  
    - **Bloquear** – quando o Windows Defender firewall está ativado e essa configuração é definida como *Bloquear*, todo o tráfego de entrada é bloqueado, independentemente de outras configurações de política. 
    - **Allow** -quando definido como *permitir*, essa configuração é desativada e o tráfego de entrada é permitido com base em outras configurações de política.

- **Respostas unicast para difusões multicast**  
  **Padrão**: não configurado  
  CSP do firewall: [DisableUnicastResponsesToMulticastBroadcast](https://go.microsoft.com/fwlink/?linkid=872562)  
  
  Normalmente, você não deseja receber respostas unicast para mensagens de difusão ou multicast. Essas respostas podem indicar um ataque DoS (negação de serviço) ou um invasor tentando investigar um computador ativo conhecido.  
  - **Não configurado**  
  - **Bloquear** – desabilitar respostas unicast para difusões multicast.  
  - **Permitir** – permite respostas unicast para difusões multicast.  

- **Notificações de entrada**  
  **Padrão**: não configurado  
  CSP do firewall: [DisableInboundNotifications](https://go.microsoft.com/fwlink/?linkid=8725630)  

  - **Não configurado**  
  - **Bloquear** -ocultar notificações a serem usadas quando um aplicativo for impedido de escutar em uma porta.  
  - **Permitir** – habilita essa configuração e pode mostrar uma notificação para os usuários quando um aplicativo é impedido de escutar em uma porta.  

- **Ação padrão para conexões de saída**  
  **Padrão**: não configurado  
  CSP do firewall: [outboundaction](https://aka.ms/intune-firewall-outboundaction)  
  
  Configure a ação padrão que o firewall executa em conexões de saída. Essa configuração será aplicada ao Windows versão 1809 e superior.  

  - **Não configurado**  
  - **Bloquear** -a ação de firewall padrão não é executada no tráfego de saída, a menos que seja explicitamente especificado para não bloquear.  
  - **Permitir** -ações de firewall padrão executadas em conexões de saída.  

- **Ação padrão para conexões de entrada**  
  **Padrão**: não configurado  
  CSP do firewall: [DefaultInboundAction](https://go.microsoft.com/fwlink/?linkid=872564)  
 
  - **Não configurado**  
  - **Bloquear** – a ação de firewall padrão não é executada em conexões de entrada.  
  - **Permitir que** ações de firewall padrão sejam executadas em conexões de entrada.  

#### <a name="rule-merging"></a>Mesclagem de regra  

- **Regras do Windows Defender Firewall de aplicativo autorizado no repositório local**  
  **Padrão**: não configurado  
  CSP do firewall: [AuthAppsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872565)  

  - **Não configurado**  
  - **Bloquear** – as regras de firewall de aplicativo autorizado no repositório local são ignoradas e não são impostas.  
  - **Permitir** -
   Escolher **Habilitar** aplica regras de firewall no repositório local para que elas sejam reconhecidas e impostas.  

- **Regras do Windows Defender Firewall de porta global no repositório local**  
  **Padrão**: não configurado  
  CSP do firewall: [GlobalPortsAllowUserPrefMerge](https://go.microsoft.com/fwlink/?linkid=872566)  

  - **Não configurado**  
  - **Bloquear** -as regras de firewall de porta global no repositório local são ignoradas e não são impostas.  
  - **Permitir** – aplicar regras de firewall de porta global no repositório local para que elas sejam reconhecidas e impostas.  

- **Regras do Windows Defender Firewall no repositório local**  
  **Padrão**: não configurado  
  CSP do firewall: [AllowLocalPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872567)  

  - **Não configurado**  
  - As regras de firewall de **bloqueio** do repositório local são ignoradas e não são impostas.
  - **Permitir** – aplicar regras de firewall no repositório local para que elas sejam reconhecidas e impostas.  

- **Regras do IPsec do repositório local**  
  **Padrão**: não configurado  
  CSP do firewall: [AllowLocalIpsecPolicyMerge](https://go.microsoft.com/fwlink/?linkid=872568)  

  - **Não configurado**  
  - **Bloquear** – as regras de segurança da conexão no armazenamento local são ignoradas e não são impostas, independentemente das versões de regra de segurança da conexão ou do esquema.  
  - **Permitir** – aplicar regras de segurança da conexão no repositório local, independentemente das versões do esquema ou da regra de segurança da conexão.  

### <a name="firewall-rules"></a>Regras de firewall  

Você pode **Adicionar** uma ou mais regras de firewall personalizadas. Para obter mais informações, consulte [adicionar regras personalizadas de firewall para dispositivos Windows 10](endpoint-protection-configure.md#add-custom-firewall-rules-for-windows-10-devices).  

As regras de firewall personalizadas dão suporte às seguintes opções:  

#### <a name="general-settings"></a>Configurações gerais:  

- **Nome**  
  **Padrão**: *sem nome*  

  Especifique um nome amigável para a regra. Esse nome aparecerá na lista de regras para ajudá-lo a identificá-lo.  

- **Descrição**  
  **Padrão**: *sem descrição*  

  Forneça uma descrição da regra.  

- **Direção**   
  **Padrão**: não configurado  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/Direction](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#direction)  
  
  Especifique se essa regra se aplica ao tráfego de **entrada**ou de **saída** . Quando definido como **não configurado**, a regra se aplica automaticamente ao tráfego de saída.  

- **Ação**  
  **Padrão**: não configurado  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/Action](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#action)e [FirewallRules/*FirewallRuleName*/Action/Type](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#type)  

  Selecione de **permitir** ou **Bloquear**. Quando definido como **não configurado**, a regra assume como padrão permitir o tráfego.  

- **Tipo de rede**  
  **Padrão**: 0 selecionado  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/Profiles](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#profiles)  

  Selecione até três tipos de tipos de rede aos quais essa regra pertence. As opções incluem **domínio**, **privado**e **público**.  Se nenhum tipo de rede for selecionado, a regra se aplicará a todos os três tipos de rede.  

#### <a name="application-settings"></a>Configurações do aplicativo  

- **Aplicativo (s)**  
  **Padrão**: todos  

  Controlar conexões para um aplicativo ou programa. Selecione uma das seguintes opções e, em seguida, conclua a configuração adicional:  
  - **Nome da família de pacotes** – especifique um nome de família de pacotes. Para localizar o nome da família de pacotes, use o comando **Get-AppxPackage**do PowerShell.   
    CSP do firewall: [FirewallRules/*FirewallRuleName*/app/PackageFamilyName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#packagefamilyname)  
 
  - **Caminho do arquivo** – você deve especificar um caminho de arquivo para um aplicativo no dispositivo cliente, que pode ser um caminho absoluto ou um caminho relativo. Por exemplo: C:\Windows\System\Notepad.exe ou%WINDIR%\Notepad.exe.  
    CSP do firewall: [FirewallRules/*FirewallRuleName*/app/FilePath](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#filepath)  

  - **Serviço do Windows** – especifique o nome curto do serviço do Windows se ele for um serviço e não um aplicativo que envia ou recebe tráfego. Para localizar o nome curto do serviço, use o comando do PowerShell **Get-Service**.  
    CSP do firewall: [FirewallRules/*FirewallRuleName*/app/ServiceName](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#servicename)  

  - **Tudo**– *nenhuma configuração adicional está disponível*.  

#### <a name="ip-address-settings"></a>Configurações de endereço IP  

Especifique os endereços locais e remotos aos quais essa regra se aplica.  

- **Endereços locais**    
  **Padrão**: qualquer endereço  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  

  Selecione **qualquer endereço** ou **endereço especificado**.  

  Ao usar o *endereço especificado*, você adiciona um ou mais endereços como uma lista separada por vírgulas de endereços locais que são cobertos pela regra. Os tokens válidos incluem:  
  - Use um asterisco "*" para *qualquer* endereço local. Se você usar um asterisco, ele deverá ser o único token que você usar.  
  - Para especificar uma sub-rede, use a máscara de sub-rede ou a notação de prefixo de rede. Se nem uma máscara de sub-rede nem um prefixo de rede for especificado, a máscara de sub-rede padrão será 255.255.255.255.  
  - Um endereço IPv6 válido.  
  - Um intervalo de endereços IPv4 no formato "endereço inicial do endereço final" sem espaços incluídos.  
  - Um intervalo de endereços IPv6 no formato "endereço inicial de endereço final" sem espaços incluídos.  

- **Endereços remotos**  
  **Padrão**: qualquer endereço  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/RemoteAddressRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteaddressranges)  
 
  Selecione **qualquer endereço** ou **endereço especificado**.  

  Ao usar o *endereço especificado*, você adiciona um ou mais endereços como uma lista separada por vírgulas de endereços remotos que são cobertos pela regra. Os tokens não diferenciam maiúsculas de minúsculas. Os tokens válidos incluem:  
  - Use um asterisco "*" para *qualquer* endereço remoto. Se você usar um asterisco, ele deverá ser o único token que você usar.  
  - DefaultGateway  
  - "DHCP"  
  - "DNS"  
  - "WINS"  
  - "Intranet" (com suporte nas versões 1809 e posteriores do Windows)  
  - "RmtIntranet" (com suporte nas versões 1809 e posteriores do Windows)  
  - "Internet" (com suporte no Windows versões 1809 e posteriores)  
  - "Ply2Renders" (com suporte nas versões 1809 e posteriores do Windows)  
  - "LocalSubnet" indica qualquer endereço local na sub-rede local.  
  - Para especificar uma sub-rede, use a máscara de sub-rede ou a notação de prefixo de rede. Se nem uma máscara de sub-rede nem um prefixo de rede for especificado, a máscara de sub-rede padrão será 255.255.255.255.  
  - Um endereço IPv6 válido.  
  - Um intervalo de endereços IPv4 no formato "endereço inicial do endereço final" sem espaços incluídos.  
  - Um intervalo de endereços IPv6 no formato "endereço inicial de endereço final" sem espaços incluídos.  

#### <a name="port-and-protocol-settings"></a>Configurações de porta e protocolo  
Especifique as portas locais e remotas às quais essa regra se aplica.  

- **Protocolo**  
  **Padrão**: qualquer  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/Protocol](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#protocol)  
  Selecione uma das seguintes opções e conclua as configurações necessárias:  
  - **Tudo** – nenhuma configuração adicional está disponível.  
  - **TCP** – configurar portas locais e remotas. Ambas as opções dão suporte a todas as portas ou portas especificadas. Insira as portas especificadas usando uma lista separada por vírgulas.  
    - **Portas locais** -CSP de firewall: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Portas remotas** -CSP de firewall: [FirewallRules/*FirewallRuleName*/RemotePortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **UDP** – configurar portas locais e remotas. Ambas as opções dão suporte a todas as portas ou portas especificadas. Insira as portas especificadas usando uma lista separada por vírgulas.  
    - **Portas locais** -CSP de firewall: [FirewallRules/*FirewallRuleName*/LocalPortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#localportranges)  
    - **Portas remotas** -CSP de firewall: [FirewallRules/*FirewallRuleName*/RemotePortRanges](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#remoteportranges)  
  - **Personalizado** – especifique um número de **protocolo** personalizado de 0 a 255.  

#### <a name="advanced-configuration"></a>Configuração avançada  
- **Tipos de interface**  
  **Padrão**: 0 selecionado  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/InterfaceTypes](https://docs.microsoft.com/windows/client-management/mdm/firewall-csp#interfacetypes)  

  Selecione entre as seguintes opções:  
  - **Acesso remoto**  
  - **Sem fio**  
  - **Rede local**  

- **Permitir conexões somente desses usuários**  
  **Padrão**: todos os usuários *(o padrão é todos os usos quando nenhuma lista é especificada)*  
  CSP do firewall: [FirewallRules/*FirewallRuleName*/LocalUserAuthorizationList](https://aka.ms/intunefirewallauthorizedusers)  

  Especifique uma lista de usuários locais autorizados para esta regra. Uma lista de usuários autorizados não poderá ser especificada se essa regra se aplicar a um serviço do Windows.  


## <a name="windows-defender-smartscreen-settings"></a>Configurações do Windows Defender SmartScreen  
 
O Microsoft Edge deve ser instalado no dispositivo.  

- **SmartScreen para aplicativos e arquivos**  
  **Padrão**: não configurado  
   CSP do SmartScreen: [SmartScreen/EnableSmartScreenInShell](https://go.microsoft.com/fwlink/?linkid=872784)  

  - **Não configurado** -desabilita o uso do SmartScreen.  
  - **Habilitar** – habilite o Windows SmartScreen para execução de arquivos e aplicativos em execução. O SmartScreen é um componente baseado em nuvem para anti-phishing e antimalware.  

- **Execução de arquivos não verificados**  
  **Padrão**: não configurado  
   CSP do SmartScreen: [SmartScreen/PreventOverrideForFilesInShell](https://go.microsoft.com/fwlink/?linkid=872783)

  - **Não configurado** – desabilita esse recurso e permite aos usuários finais executar arquivos que ainda não foram verificados.  
  - **Bloquear** – impede que os usuários finais executem arquivos que não foram verificados pelo Windows SmartScreen.  

## <a name="windows-encryption"></a>Criptografia do Windows  
 
### <a name="windows-settings"></a>Configurações do Windows  

Essas configurações de criptografia se aplicam a todas as versões do Windows 10.  

- **Criptografar dispositivos**  
  **Padrão**: não configurado  
  CSP do BitLocker: [RequireDeviceEncryption](https://go.microsoft.com/fwlink/?linkid=872523)  

  - **Exigir** – solicita aos usuários que habilitem a criptografia de dispositivo. Dependendo da edição do Windows e a configuração do sistema, os usuários podem ser solicitados a:  
    - Confirmar que a criptografia de outro provedor não está habilitada.  
    - Desativar a Criptografia de Unidade de Disco BitLocker e, em seguida, ativar o BitLocker novamente.  
  - **Não configurado**  
  
  Se a criptografia do Windows for ativada enquanto outro método de criptografia está ativo, o dispositivo pode se tornar instável.  

- **Criptografar cartão de armazenamento (somente dispositivos móveis)**  
  *Essa configuração só se aplica ao Windows 10 Mobile.*  
  **Padrão**: não configurado  
  CSP do BitLocker: [RequireStorageCardEncryption](https://go.microsoft.com/fwlink/?linkid=872524)  

  - Escolha **Exigir** para criptografar os cartões de armazenamento removíveis usados pelo dispositivo.  
  - **Não configurado** – não exige a criptografia do cartão de memória e não solicita ao usuário para ativá-la.  

### <a name="bitlocker-base-settings"></a>Configurações base do BitLocker  

As configurações básicas são as configurações universais do BitLocker para todos os tipos de unidades de dados. Essas configurações gerenciam quais tarefas de criptografia de unidade ou opções de configuração o usuário final pode modificar em todos os tipos de unidades de dados.  

- **Aviso para outras criptografias de disco**  
  **Padrão**: não configurado  
  CSP do BitLocker: [AllowWarningForOtherDiskEncryption](https://go.microsoft.com/fwlink/?linkid=872525)  

  - **Bloquear** – desabilita o prompt de aviso se outro serviço de criptografia de disco está no dispositivo.  
  - **Não configurado** -permite que o aviso para outra criptografia de disco seja mostrado.  

  Quando definido como *Bloquear*, você pode definir a seguinte configuração:  

  - **Permitir que usuários padrão habilitem a criptografia durante o ingresso no Azure AD**  
    *Essa configuração se aplica somente a dispositivos Unidos Azure Active Directory (Azure ADJ) e depende da configuração anterior, `Warning for other disk encryption`.*  
    **Padrão**: não configurado  
    CSP do BitLocker: [AllowStandardUserEncryption](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowstandarduserencryption)

     - **Permitir** -usuários padrão (não administradores) podem habilitar a criptografia BitLocker quando conectado.  
     - **Não configurado** só Administradores podem habilitar a criptografia do BitLocker no dispositivo.  

- **Configurar métodos de criptografia**  
  **Padrão**: não configurado  
  CSP do BitLocker: [EncryptionMethodByDriveType](https://go.microsoft.com/fwlink/?linkid=872526)  

  - **Habilitar** – configure os algoritmos de criptografia para o sistema operacional, os dados e as unidades removíveis.  
  - **Não configurado** – o BitLocker usa o XTS-AES de 128 bits como o método de criptografia padrão ou usa o método de criptografia especificado por qualquer script de instalação.  

  Quando está como *Habilitar*, você pode definir as seguintes configurações:  

  - **Criptografia para unidades do sistema operacional**  
    **Padrão**: XTS-AES 128-bit  
   
    Escolha o método de criptografia para unidades do sistema operacional. Recomendamos que você use o algoritmo XTS-AES.  
    - **AES-CBC 128 bits**  
    - **AES-CBC 256 bits**  
    - **XTS-AES 128-bit**  
    - **XTS-AES 256-bit**  

  - **Criptografia para unidades de dados fixas**  
    **Padrão**: AES-CBC 128 bits  
   
    Escolha o método de criptografia para unidades de dados fixas (internas). Recomendamos que você use o algoritmo XTS-AES.  
    - **AES-CBC 128 bits**  
    - **AES-CBC 256 bits**  
    - **XTS-AES 128-bit**  
    - **XTS-AES 256-bit**  

  - **Criptografia para unidades de dados removíveis**  
    **Padrão**: AES-CBC 128 bits  

    Escolha o método de criptografia para unidades de dados removíveis. Se a unidade removível é usada com dispositivos que não executam o Windows 10, recomendamos o uso do algoritmo AES-CBC.  
    - **AES-CBC 128 bits**  
    - **AES-CBC 256 bits**  
    - **XTS-AES 128-bit**  
    - **XTS-AES 256-bit**  

### <a name="bitlocker-os-drive-settings"></a>Configurações de unidade do sistema operacional do BitLocker  

Essas configurações aplicam-se especificamente às unidades de dados do sistema operacional.  

- **Autenticação adicional na inicialização**  
  **Padrão**: não configurado  
  CSP do BitLocker: [SystemDrivesRequireStartupAuthentication](https://go.microsoft.com/fwlink/?linkid=872527)  

  - **Exigir** – configure os requisitos de autenticação da inicialização do computador, incluindo o uso do TPM (Trusted Platform Module).  
  - **Não configurado** – configure apenas as opções básicas em dispositivos com um TPM.  

  Quando está como *Exigir*, você pode definir as seguintes configurações:  

  - **BitLocker com chip do TPM não compatível**  
    **Padrão**: não configurado  

    - **Bloquear** – desabilita o uso do BitLocker quando um dispositivo não tem um chip de TPM compatível.  
    - **Não configurado** – os usuários podem usar o BitLocker sem um chip de TPM compatível. O BitLocker pode exigir uma senha ou uma chave de inicialização.  

  - **Inicialização do TPM compatível**  
    **Padrão**: Permitir TPM  

    Configure se o TPM é permitido, obrigatório ou não permitido.  

    - **Permitir TPM**  
    - **Não permitir TPM**  
    - **Exigir TPM**  

  - **PIN de inicialização do TPM compatível**  
    **Padrão**: permitir PIN de inicialização com TPM  

    Escolha permitir, não permitir ou exigir o uso de um PIN de inicialização com o chip do TPM. A habilitação de um PIN de inicialização exige a interação do usuário final.  

    - **Permitir PIN de inicialização com TPM**  
    - **Não permitir PIN de inicialização com TPM**  
    - **Exigir o PIN de inicialização com o TPM**

  - **Chave de inicialização do TPM compatível**  
    **Padrão**: permitir chave de inicialização com TPM  

    Escolha permitir, não permitir ou exigir o uso de uma chave de inicialização com o chip do TPM. A habilitação de uma chave de inicialização exige a interação do usuário final.  

    - **Permitir chave de inicialização com TPM**  
    - **Não permitir chave de inicialização com TPM**  
    - **Exigir chave de inicialização com TPM**  

  - **PIN e chave de inicialização do TPM compatível**  
    **Padrão**: permitir chave de inicialização e PIN com TPM  

    Escolha permitir, não permitir ou exigir o uso de um PIN e uma chave de inicialização com o chip do TPM. A habilitação de uma chave de inicialização e um PIN exige a interação do usuário final.  
    - **Permitir chave de inicialização e PIN com TPM**  
    - **Não permitir chave de inicialização e PIN com TPM**  
    - **Exigir chave de inicialização e PIN com TPM**   

- **Tamanho mínimo do PIN**  
    **Padrão**: não configurado  
    CSP do BitLocker: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)   

    - **Habilitar** Configure um comprimento mínimo para o PIN de inicialização do TPM.  
    - **Não configurado** – os usuários podem configurar um PIN de inicialização de qualquer tamanho entre 6 e 20 dígitos.  

  Quando está como *Habilitar*, você pode definir a seguinte configuração:  

  - **Número mínimo de caracteres**  
    **Padrão**: *não CONfigurada* CSP do BitLocker: [SystemDrivesMinimumPINLength](https://go.microsoft.com/fwlink/?linkid=872528)  

    Insira o número de caracteres necessário para o PIN de inicialização de **4**-**20**.  

- **Recuperação de unidade do sistema operacional**  
  **Padrão**: não configurado   
  CSP do BitLocker: [SystemDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872529)  

  - **Habilitar** – controla como as unidades do sistema operacional protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis.  
  - **Não configurado** – as opções de recuperação padrão são compatíveis com a recuperação do BitLocker. Por padrão, um DRA é permitido, as opções de recuperação são escolhidas pelo usuário, incluindo a senha e a chave de recuperação, e as informações de recuperação não são copiadas em backup no AD DS.  

  Quando está como *Habilitar*, você pode definir as seguintes configurações:  

  - **Agente de recuperação de dados baseado em certificado**  
    **Padrão**: não configurado  
     
    - **Bloquear** – impedir o uso do agente de recuperação de dados com unidades de sistema operacional protegidas pelo BitLocker.  
    - **Não configurado** -permite que os agentes de recuperação de dados sejam usados com unidades do sistema operacional protegidas pelo BitLocker.  

  - **Criação de senha de recuperação pelo usuário**  
    **Padrão**: permitir senha de recuperação de 48 dígitos  

    Escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
    - **Permitir senha de recuperação de 48 dígitos**  
    - **Não permitir senha de recuperação de 48 dígitos**  
    - **Exigir senha de recuperação de 48 dígitos**  

  - **Criação de chave de recuperação pelo usuário**  
    **Padrão**: permitir chave de recuperação de 256 bits  

    Escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.  
    - **Permitir chave de recuperação de 256 bits**  
    - **Não permitir chave de recuperação de 256 bits**  
    - **Exigir chave de recuperação de 256 bits**  

  - **Opções de recuperação no assistente de instalação do BitLocker**  
    **Padrão**: não configurado  

    - **Bloquear** – os usuários não podem ver nem alterar as opções de recuperação. Quando definido como 
    - **Não configurado** – os usuários podem ver e alterar as opções de recuperação ao ativarem o BitLocker. 
 
  - **Salvar informações de recuperação do BitLocker para Azure Active Directory**  
    **Padrão**: não configurado  

    - **Habilitar** – armazena as informações de recuperação do BitLocker no Azure AD (Azure Active Directory).  
    - **Não configurado** -as informações de recuperação do BitLocker não são armazenadas no AAD.  

  - **Informações de recuperação do BitLocker armazenadas no Azure Active Directory**  
    **Padrão**: faz o backup de pacotes de chaves e senhas de recuperação  

    Configure quais partes das informações de recuperação do BitLocker são armazenadas no Azure AD. Escolha:  
    - **Fazer backup de pacotes de chaves e senhas de recuperação**  
    - **Fazer backup somente de senhas de recuperação**  

  - **Rotação de senha de recuperação controlada pelo cliente**  
    **Padrão**: rotação de chaves habilitada para dispositivos ingressados no Azure AD  
    CSP do BitLocker: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    Essa configuração inicia uma rotação de senha de recuperação controlada pelo cliente após uma recuperação de unidade do sistema operacional (seja usando bootmgr ou WinRE).  

    - Não configurado  
    - Rotação de chaves desabilitada  
    - Rotação de chaves habilitada para deices unida do Azure AD  
    - Rotação de chaves habilitada para o Azure AD e dispositivos ingressados no híbrido  

  - **Armazenar informações de recuperação em Azure Active Directory antes de habilitar o BitLocker**  
    **Padrão**: não configurado  
 
     Impedir que os usuários habilitem o BitLocker, a menos que o computador faça o backup com êxito das informações de recuperação do BitLocker para Azure Active Directory.  

    - **Exigir** – impede os usuários de ativar o BitLocker, a menos que as informações de recuperação do BitLocker sejam armazenadas com êxito no Azure AD.  
    - **Não configurado** – permite que os usuários ativem o BitLocker, mesmo se as informações de recuperação não forem armazenadas com êxito no Azure AD.  

- **URL e mensagem de recuperação pré-inicialização**  
  **Padrão**: não configurado  
  CSP do BitLocker: [SystemDrivesRecoveryMessage](https://go.microsoft.com/fwlink/?linkid=872530)  

  - **Habilitar** -configurar a mensagem e a URL que são exibidas na tela de recuperação de chave de pré-inicialização.  
  - **Não configurado** – desabilita esse recurso.  
  
  Quando está como *Habilitar*, você pode definir a seguinte configuração:  
  - **Mensagem de recuperação pré-inicialização**  
    **Padrão**: usa a mensagem e URL de recuperação padrão   
 
    Configure como a mensagem de recuperação pré-inicialização é exibida para os usuários. Escolha:  
    - **Usar mensagem e URL de recuperação padrão**  
    - **Usar mensagem e URL de recuperação vazia**  
    - **Usar mensagem de recuperação personalizada**  
    - **Usar URL de recuperação personalizada**  

### <a name="bitlocker-fixed-data-drive-settings"></a>Configurações de unidades de dados fixas do BitLocker  

Essas configurações se aplicam especificamente a unidades de dados fixas.  

- **Acesso de gravação a unidades de dados fixas não protegidas pelo BitLocker**  
  **Padrão**: não configurado  
  CSP do BitLocker: [FixedDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872534)  

  - **Bloquear** – fornece acesso somente leitura às unidades de dados que não são protegidas pelo BitLocker.  
  - **Não configurado** -por padrão, acesso de leitura e gravação a unidades de dados que não são criptografadas.  

- **Recuperação de unidade fixa**  
  **Padrão**: não configurado  
  CSP do BitLocker: [FixedDrivesRecoveryOptions](https://go.microsoft.com/fwlink/?linkid=872538)  

  - **Habilitar** – controla como as unidades fixas protegidas pelo BitLocker são recuperadas quando as informações de inicialização necessárias não estão disponíveis.  
  - **Não configurado** – desabilita esse recurso.  

  Quando está como *Habilitar*, você pode definir as seguintes configurações:  

  - **Agente de recuperação de dados**  
    **Padrão**: não configurado  
 
    - **Bloquear** – impede o uso do agente de recuperação de dados com o Editor de Política das unidades fixas protegidas pelo BitLocker. 
    - **Não configurado** – habilita o uso de agentes de recuperação de dados com unidades fixas protegidas pelo BitLocker.  

  - **Criação de senha de recuperação pelo usuário**  
    **Padrão**: permitir senha de recuperação de 48 dígitos  

    Escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma senha de recuperação de 48 dígitos.  
    - **Permitir senha de recuperação de 48 dígitos**  
    - **Não permitir senha de recuperação de 48 dígitos**  
    - **Exigir senha de recuperação de 48 dígitos**  

  - **Criação de chave de recuperação pelo usuário**  
    **Padrão**: permitir chave de recuperação de 256 bits

    Escolha se é permitido, obrigatório ou não permitido que os usuários gerem uma chave de recuperação de 256 bits.
    - **Permitir chave de recuperação de 256 bits**  
    - **Não permitir chave de recuperação de 256 bits**  
    - **Exigir chave de recuperação de 256 bits**  

  - **Opções de recuperação no assistente de instalação do BitLocker**  
    **Padrão**: não configurado  

    - **Bloquear** – os usuários não podem ver nem alterar as opções de recuperação. Quando definido como 
    - **Não configurado** – os usuários podem ver e alterar as opções de recuperação ao ativarem o BitLocker.
 
  - **Salvar informações de recuperação do BitLocker para Azure Active Directory**  
    **Padrão**: não configurado  

    - **Habilitar** – armazena as informações de recuperação do BitLocker no Azure AD (Azure Active Directory).  
    - **Não configurado** -as informações de recuperação do BitLocker não são armazenadas no AAD.

  - **Informações de recuperação do BitLocker armazenadas no Azure Active Directory**  
    **Padrão**: faz o backup de pacotes de chaves e senhas de recuperação  

    Configure quais partes das informações de recuperação do BitLocker são armazenadas no Azure AD. Escolha:  
    - **Fazer backup de pacotes de chaves e senhas de recuperação**  
    - **Fazer backup somente de senhas de recuperação**  

  - **Rotação de senha de recuperação controlada pelo cliente**  
    **Padrão**: rotação de chaves habilitada para dispositivos ingressados no Azure AD  
    CSP do BitLocker: [ConfigureRecoveryPasswordRotation](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp)  
    
    Essa configuração inicia uma rotação de senha de recuperação controlada pelo cliente após uma recuperação de unidade do sistema operacional (seja usando bootmgr ou WinRE).  

    - Não configurado  
    - Rotação de chaves desabilitada  
    - Rotação de chaves habilitada para deices unida do Azure AD  
    - Rotação de chaves habilitada para o Azure AD e dispositivos ingressados no híbrido  

  - **Armazenar informações de recuperação em Azure Active Directory antes de habilitar o BitLocker**  
    **Padrão**: não configurado  
 
    Impedir que os usuários habilitem o BitLocker, a menos que o computador faça o backup com êxito das informações de recuperação do BitLocker para Azure Active Directory.  

    - **Exigir** – impede os usuários de ativar o BitLocker, a menos que as informações de recuperação do BitLocker sejam armazenadas com êxito no Azure AD.  
    - **Não configurado** – permite que os usuários ativem o BitLocker, mesmo se as informações de recuperação não forem armazenadas com êxito no Azure AD.  

### <a name="bitlocker-removable-data-drive-settings"></a>Configurações de unidade de dados removíveis do BitLocker  

Essas configurações se aplicam especificamente a unidades de dados removíveis.  

- **Acesso de gravação a unidades de dados removíveis não protegidas pelo BitLocker**  
  **Padrão**: não configurado  
  CSP do BitLocker: [RemovableDrivesRequireEncryption](https://go.microsoft.com/fwlink/?linkid=872540)  

  - **Bloquear** – fornece acesso somente leitura às unidades de dados que não são protegidas pelo BitLocker.  
  - **Não configurado** -por padrão, acesso de leitura e gravação a unidades de dados que não são criptografadas.  

  Quando está como *Habilitar*, você pode definir a seguinte configuração:  

  - **Acesso de gravação a dispositivos configurados em outra organização**  
    **Padrão**: não configurado  

    - **Bloquear** – impede o acesso de gravação a dispositivos configurados em outra organização.  
    - **Não configurado** -negar acesso de gravação.  
 
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard  

Use a [proteção contra Exploit](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) para gerenciar e reduzir a superfície de ataque de aplicativos usados por seus funcionários.  

### <a name="attack-surface-reduction"></a>Redução da superfície de ataque  

As regras de redução da superfície de ataque ajudam a evitar comportamentos que o malware geralmente usa para infectar computadores com código mal-intencionado.  

#### <a name="attack-surface-reduction-rules"></a>Regras de Redução da superfície de ataque  

- **Sinalizar roubo de credencial do subsistema da autoridade de segurança local do Windows**  
  **Padrão**: não configurado  
  Regra: [bloquear o roubo de credenciais do subsistema da autoridade de segurança local do Windows (lsass.exe)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-credential-stealing-from-the-windows-local-security-authority-subsystem-lsassexe)

  Ajude a impedir que aplicativos e ações, que normalmente são usados por malwares em busca de exploração, infectem computadores.  

  - **Não configurado**  
  - **Habilitar** – sinaliza o roubo de credenciais do subsistema da autoridade de segurança local do Windows (lsass.exe).  
  - **Somente auditoria**  

- **Criação de processo do Adobe Reader (beta)**  
  **Padrão**: não configurado  
  Regra: [bloquear o Adobe Reader de criar processos filho](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-adobe-reader-from-creating-child-processes)  

  - **Não configurado**  
  - **Habilitar** -bloquear processos filho que são criados a partir do Adobe Reader.  
  - **Somente auditoria**  

#### <a name="rules-to-prevent-office-macro-threats"></a>Regras para impedir ameaças a macros do Office  

Impeça que os aplicativos do Office executem as seguintes ações:  

- **Injeção de aplicativos do Office em outros processos (sem exceções)**  
  **Padrão**: não configurado  
  Regra: [bloquear aplicativos do Office para evitar que injetem um código em outros processos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-applications-from-injecting-code-into-other-processes)  

  - **Não configurado**  
  - **Bloqueie a injeção** de aplicativos do Office em outros processos.  
  - **Somente auditoria**  

- **Criação de conteúdo executável por aplicativos/macros do Office**  
  **Padrão**: não configurado  
  Regra: [bloquear aplicativos do Office para impedir que criem um conteúdo executável](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-applications-from-creating-executable-content)  

  - **Não configurado**  
  - **Bloqueie o** bloqueio de aplicativos e macros do Office de criar conteúdo executável.  
  - **Somente auditoria**  

- **Inicialização de processos filhos por aplicativos do Office**  
  **Padrão**: não configurado  
  Regra: [impedir que todos os aplicativos do Office criem processos filho](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-all-office-applications-from-creating-child-processes)  

  - **Não configurado**  
  - **Bloquear o** bloqueio de aplicativos do Office para iniciar processos filho.  
  - **Somente auditoria**  
  
- **Importações do Win32 de código de macro do Office**  
  **Padrão**: não configurado  
  Regra: [bloquear chamada à API do Win32 desde macros do Office](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-win32-api-calls-from-office-macros)  

  - **Não configurado**  
  - **Bloco** -bloquear importações do Win32 do código de macro no Office.  
  - **Somente auditoria**  
  
- **Criação de processos de produtos de comunicação do Office**  
  **Padrão**: não configurado  
  Regra: [bloquear o aplicativo de comunicação do Office de criar processos filho](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-office-communication-application-from-creating-child-processes)  

  - **Não configurado**  
  - **Habilitar** -Bloquear criação de processo filho de aplicativos de comunicações do Office.  
  - **Somente auditoria**  

#### <a name="rules-to-prevent-script-threats"></a>Regras para impedir ameaças de script  

Bloqueie o seguinte para ajudar a prevenir ameaças de script:  

- **Código de js/vbs/ps/macro ofuscado**  
  **Padrão**: não configurado  
  Regra: [bloquear a execução de scripts potencialmente ofuscados](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-execution-of-potentially-obfuscated-scripts)    

  - **Não configurado**  
  - **Bloquear-bloquear** qualquer código js/vbs/PS/macro ofuscado.  
  - **Somente auditoria**  

- **Execução de conteúdo baixado da Internet pelo js/vbs (sem exceções)**  
  **Padrão**: não configurado  
  Regra: [bloquear o JavaScript ou o VBScript para impedir que iniciem um conteúdo executável baixado](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-javascript-or-vbscript-from-launching-downloaded-executable-content)  

  - **Não configurado**  
  - **Bloquear** -bloquear js/vbs da carga de execução baixada da Internet.  
  - **Somente auditoria**  

- **Criação de processo usando comandos WMI e PSExec**  
  **Padrão**: não configurado  
  Regra: [bloquear criações de processo provenientes de comandos PSExec e WMI](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-process-creations-originating-from-psexec-and-wmi-commands)  

  - **Não configurado**  
  - **Bloquear** – impede as criações de processos provenientes de comandos PSExec e WMI.  
  
  - **Somente auditoria**  

- **Processos não assinados e não confiáveis executados de um USB**  
  **Padrão**: não configurado  
  Regra: [bloquear processos não assinados e não confiáveis executados de USB](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-untrusted-and-unsigned-processes-that-run-from-usb)    

  - **Não configurado**  
  - **Bloquear** – impede processos não assinados e não confiáveis executados de um USB.  
  - **Somente auditoria**  
  
- **Executáveis que não atendem um critério de prevalência, idade ou lista confiável**  
  **Padrão**: não configurado  
  Regra: [bloquear a execução de arquivos executáveis, a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion)    

  - **Não configurado**  
  - **Bloquear** – impede a execução de arquivos executáveis, a menos que eles atendam a um critério de prevalência, de idade ou de lista confiável.  
  - **Somente auditoria**  

#### <a name="rules-to-prevent-email-threats"></a>Regras para impedir ameaças de email  

Bloqueie o seguinte para ajudar a prevenir ameaças por email:  

- **Execução de conteúdo executável (exe, dll, ps, js, vbs, etc.) proveniente do email (cliente de webmail/email) (sem exceções)**  
  **Padrão**: não configurado  
  Regra: [bloquear o conteúdo executável do cliente de email e de webmail](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#block-executable-content-from-email-client-and-webmail)  

  - **Não configurado**  
  - **Bloquear** – impede a execução de conteúdo executável (exe, dll, ps, js, vbs etc.) proveniente do email (cliente de webmail/email).  
  - **Somente auditoria**  

#### <a name="rules-to-protect-against-ransomware"></a>Regras para proteger-se contra ransomware  

- **Proteção avançada contra ransomware**  
  Padrão: não configurado  
  Regra: [usar a proteção avançada contra ransomware](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction#use-advanced-protection-against-ransomware)  

  - **Não configurado**  
  - **Habilitar** – usa proteção agressiva contra ransomware.  
  - **Somente auditoria**  

#### <a name="attack-surface-reduction-exceptions"></a>Exceções de redução da superfície de ataque

- **Arquivos e pastas a serem excluídos das regras de redução da superfície de ataque**  
  CSP do defender: [AttackSurfaceReductionOnlyExclusions](https://go.microsoft.com/fwlink/?linkid=872981)  

  - **Importe** um arquivo. csv que contenha arquivos e pastas para excluir das regras de redução da superfície de ataque.  
  - **Adicione** arquivos ou pastas locais manualmente.  

> [!IMPORTANT]  
> Para permitir a instalação e a execução corretas de aplicativos Win32 LOB, as configurações de antimalware devem excluir os seguintes diretórios da verificação:  
> **Em computadores cliente x64**:  
> *C:\Arquivos de Programa (x86)\Microsoft Intune Management Extension\Content*  
> *C:\windows\IMECache*  
>  
> **Em computadores cliente x86**:  
> *C:\Arquivos de Programa\Microsoft Intune Management Extension\Content*  
> *C:\windows\IMECache*  

### <a name="controlled-folder-access"></a>Acesso controlado à pasta  

Ajude a [proteger dados valiosos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/controlled-folders) contra ameaças e aplicativos mal-intencionados, como ransomware.  

- **Proteção de pasta**  
  **Padrão**: não configurado  
  CSP do defender: [EnableControlledFolderAccess](https://go.microsoft.com/fwlink/?linkid=872614)  

  Proteger arquivos e pastas contra alterações não autorizadas por aplicativos não amigáveis.  

  - **Não configurado**  
  - **Habilitar**  
  - **Somente auditoria**  
  - **Bloquear modificação de disco**  
  - **Modificação de disco de auditoria**  

  Quando você seleciona uma configuração diferente de *não configurado*, você pode configurar:  
  - **Lista de aplicativos que têm acesso a pastas protegidas**  
    CSP do defender: [ControlledFolderAccessAllowedApplications](https://go.microsoft.com/fwlink/?linkid=872616)  

    - **Importe** um arquivo. csv que contenha uma lista de aplicativos.  
    - **Adicione** aplicativos a essa lista manualmente.  

  - **Lista de pastas adicionais que precisam ser protegidas**  
    CSP do defender: [ControlledFolderAccessProtectedFolders](https://go.microsoft.com/fwlink/?linkid=872617)  

    - **Importe** um arquivo. csv que contenha uma lista de pastas.  
    - **Adicione** pastas a essa lista manualmente.  

### <a name="network-filtering"></a>Filtragem de rede  

Bloquear conexões de saída de qualquer aplicativo para endereços IP ou domínios com baixa reputação. Há suporte para a filtragem de rede no modo de auditoria e de bloqueio.  

- **Proteção de rede**  
  **Padrão**: não configurado  
  CSP do defender: [EnableNetworkProtection](https://go.microsoft.com/fwlink/?linkid=872618)  

  A intenção dessa configuração é proteger os usuários finais de aplicativos com acesso a golpes de phishing, sites de Hospedagem de exploração e conteúdo mal-intencionado na Internet. Ele também impede que navegadores de terceiros se conectem a sites perigosos.  

  - **Não configurado** – desabilita esse recurso. Os usuários e aplicativos não estão impedidos de se conectar a domínios perigosos. Os administradores não podem ver essa atividade na Central de Segurança do Windows Defender.  
  - **Habilitar** -ativar a proteção de rede e impedir que usuários e aplicativos se conectem a domínios perigosos. Os administradores podem ver essa atividade na Central de Segurança do Windows Defender.  
  - **Somente auditoria**:-os usuários e aplicativos não são impedidos de se conectar a domínios perigosos. Os administradores podem ver essa atividade na Central de Segurança do Windows Defender.  

### <a name="exploit-protection"></a>Proteção contra explorações  
 

- **Carregar XML**  
  **Padrão**: *não configurado*  

  Para usar a proteção contra Exploit para [proteger dispositivos contra explorações](https://docs.microsoft.com/en-us/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection), crie um arquivo XML que inclui as configurações de mitigação do sistema e do aplicativo que você deseja. Há dois métodos para criar o arquivo XML:  

  - *PowerShell*: use um ou mais dos cmdlets *Get-ProcessMitigation*, *Set-ProcessMitigation* e *ConvertTo-ProcessMitigationPolicy* do PowerShell. Os cmdlets definem configurações de mitigação e exportam uma representação XML deles.  

  - *Interface do usuário da Central de Segurança do Windows Defender* – na Central de Segurança do Windows Defender, clique no controle de aplicativo e navegador e, em seguida, role até a parte inferior da tela resultante para localizar o Exploit Protection. Primeiro, use as guias Configurações do sistema e Configurações do programa para definir as configurações de mitigação. Em seguida, localize o link Exportar configurações na parte inferior da tela para exportar uma representação XML delas.  

- **Edição de usuário da interface de proteção de exploração**  
  **Padrão**: não configurado  
  CSP ExploitGuard: [ExploitProtectionSettings](https://go.microsoft.com/fwlink/?linkid=872887)  


  - **Bloquear** – carregar um arquivo XML que permite configurar a memória, o fluxo de controle e as restrições de política. As configurações no arquivo XML podem ser usadas para bloquear um aplicativo contra explorações.  
  - **Não configurado** -nenhuma configuração personalizada é usada.  

## <a name="windows-defender-application-control"></a>Controle de Aplicativos do Windows Defender  

Escolha aplicativos adicionais que precisam ser auditados pelo ou que podem ser confiáveis para execução pelo controle de aplicativos do Windows Defender. Os componentes do Windows e todos os aplicativos da Windows Store são automaticamente confiáveis para execução.  


- **Políticas de integridade de código de controle de aplicativo**  
  **Padrão**: não configurado  
   CSP: [CSP do AppLocker](https://go.microsoft.com/fwlink/?linkid=874543)  

  - **Impor** -escolha as políticas de integridade de código de controle de aplicativo para os dispositivos dos usuários.  
  
    Depois de habilitado em um dispositivo, o Controle do Aplicativo só poderá ser desabilitado quando se alterar o modo de *Impor* para *Somente auditoria*. Alterar o modo de *Impor* para *Não Configurado* resultará no Controle do Aplicativo continuar a ser imposto nos dispositivos atribuídos.  

  - **Não configurado** -o controle de aplicativo não é adicionado aos dispositivos. No entanto, as configurações que foram adicionadas anteriormente continuam a ser impostas em dispositivos atribuídos. 
 
  - **Somente auditoria** -os aplicativos não são bloqueados. Todos os eventos são registrados nos logs do cliente local.  

## <a name="windows-defender-credential-guard"></a>Windows Defender Credential Guard  

O Windows Defender Credential Guard protege contra ataques de roubo de credenciais. Ele isola segredos de modo que apenas o software do sistema privilegiado possa acessá-los.  

- **Credential Guard**  
  **Padrão**: Desabilitar  
  [CSP DeviceGuard](https://go.microsoft.com/fwlink/?linkid=872424)  

  - **Desabilitar** – desativará o Credential Guard remotamente se ele tiver sido ativado anteriormente com a opção **Habilitado sem bloqueio de UEFI**.  

  - **Habilitar com bloqueio de UEFI** – o Credential Guard não pode ser desabilitado remotamente usando uma chave do Registro ou uma Política de Grupo.  

    > [!NOTE]
    > Se você usar essa configuração e depois quiser desabilitar o Credential Guard, deverá definir a Política de Grupo como **Desabilitada**. Além disso, limpe fisicamente as informações de configuração de UEFI de cada computador. Enquanto a configuração da UEFI for mantida, o Credential Guard estará habilitado.  

  - **Habilitar sem bloqueio de UEFI** – permite que o Credential Guard seja desabilitado remotamente usando uma Política de Grupo. Os dispositivos que usam essa configuração devem estar executando, Windows 10 versão 1511 e mais recentes.  

  Ao *habilitar* o Credential Guard, os seguintes recursos obrigatórios também são habilitados:  
  
  - **VBS** (Segurança baseada em virtualização)  
    É ativada durante a próxima reinicialização. A segurança baseada em virtualização usa o Hipervisor do Windows para dar suporte aos serviços de segurança.  
  - **Inicialização Segura com acesso direto à memória**  
    Ativa a VBS com as proteções Inicialização Segura e DMA (acesso direto à memória). Proteções de AMD exigem suporte de hardware e são habilitadas somente em dispositivos configurados corretamente.  

## <a name="windows-defender-security-center"></a>Central de Segurança do Windows Defender  

A Central de Segurança do Windows Defender funciona como um aplicativo ou um processo separado de cada um dos recursos individuais. Ele exibe notificações por meio da Central de Ações. Funciona como um coletor ou um único lugar para ver o status e executar algumas etapas de configuração para cada um dos recursos. Encontre mais informações nos documentos do [Windows Defender](https://docs.microsoft.com/windows/threat-protection/windows-defender-security-center/windows-defender-security-center).  

### <a name="windows-defender-security-center-app-and-notifications"></a>Aplicativo Central de Segurança do Windows Defender e notificações  

Bloqueie o acesso de usuário final às várias áreas do aplicativo da Central de Segurança do Windows Defender. Ocultar uma seção também bloqueia as notificações relacionadas.  

- **Proteção contra vírus e ameaças**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableVirusUI](https://go.microsoft.com/fwlink/?linkid=873662)  

  Configure se os usuários finais podem exibir a área de proteção contra vírus e ameaças na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas à proteção contra vírus e ameaças.  

  - **Não configurado**  
  - **Ocultar**  

- **Proteção contra ransomware**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [HideRansomwareDataRecovery](https://go.microsoft.com/fwlink/?linkid=873664)  

  Configurar se os usuários finais puderem exibir a área de proteção contra ransomware na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas à proteção contra ransomware.  

  - **Não configurado**  
  - **Ocultar**  

- **Proteção da conta**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableAccountProtectionUI](https://go.microsoft.com/fwlink/?linkid=873666)  

  Configurar se os usuários finais puderem exibir a área proteção da conta na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas à proteção da conta.  

  - **Não configurado**  
  - **Ocultar**  

- **Proteção de firewall e rede**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableNetworkUI](https://go.microsoft.com/fwlink/?linkid=873668)  

  Configurar se os usuários finais puderem exibir a área de proteção de firewall e rede na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas ao firewall e à proteção de rede.  

  - **Não configurado**  
  - **Ocultar**  

- **Controle de aplicativo e navegador**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableAppBrowserUI](https://go.microsoft.com/fwlink/?linkid=873669)  

  Configurar se os usuários finais puderem exibir a área de controle do aplicativo e do navegador na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas ao aplicativo e ao controle de navegador.  

  - **Não configurado**  
  - **Ocultar**  

- **Proteção de hardware**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableDeviceSecurityUI](https://go.microsoft.com/fwlink/?linkid=873670)  

  Configurar se os usuários finais puderem exibir a área de proteção de hardware na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas à proteção de hardware.  

  - **Não configurado**  
  - **Ocultar**  

- **Integridade e desempenho do dispositivo**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableHealthUI](https://go.microsoft.com/fwlink/?linkid=873671)  

  Configurar se os usuários finais puderem exibir a área de desempenho e integridade do dispositivo na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas ao desempenho e à integridade do dispositivo.  
  
  - **Não configurado**  
  - **Ocultar**  

- **Opções da família**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableFamilyUI](https://go.microsoft.com/fwlink/?linkid=873673)  

  Configurar se os usuários finais puderem exibir a área de opções da família na central de segurança do Windows Defender. Ocultar esta seção também bloqueará todas as notificações relacionadas às opções da família.  
  
  - **Não configurado**  
  - **Ocultar**  

- **Notificações das áreas exibidas do aplicativo**  
  **Padrão**: não configurado  
  CSP WindowsDefenderSecurityCenter: [DisableNotifications](https://go.microsoft.com/fwlink/?linkid=873675)  

  Escolha quais notificações serão exibidas aos usuários finais. As notificações não críticas incluem resumos de atividades do Windows Defender Antivírus, incluindo notificações após a conclusão das verificações. Todas as outras notificações são consideradas críticas.  

  - **Não configurado**  
  - **Bloquear notificações não críticas**  
  - **Bloquear todas as notificações**  

- **Ícone da central de segurança do Windows na bandeja do sistema**  
  **Padrão**: não configurado  

  Configure a exibição do controle da área de notificação. O usuário precisa sair e entrar ou reiniciar o computador para que essa configuração entre em vigor.  
  
  - **Não configurado**  
  - **Ocultar**  

- **Botão limpar TPM**  
  **Padrão**: não configurado  

  Configure a exibição do botão limpar TPM.  
  
  - **Não configurado**  
  - **Desabilitar**  

- **Aviso de atualização de firmware do TPM**  
  **Padrão**: não configurado  
  
  Configure a exibição do firmware do TPM de atualização quando um firmware vulnerável for detectado.  

  - **Não configurado**  
  - **Ocultar**  

- **Proteção contra violações**  
  **Padrão**: não configurado

  Ativar ou desativar a proteção contra violação em dispositivos. Para usar a proteção contra violações, você deve [integrar a proteção avançada contra ameaças do Microsoft defender com o Intune](advanced-threat-protection.md)e ter [Enterprise Mobility + Security licenças E5](../fundamentals/licenses.md).  
  - **Não configurado** -nenhuma alteração é feita nas configurações do dispositivo.
  - **Habilitado** -a proteção contra violação está ativada e as restrições são impostas nos dispositivos.
  - **Desabilitado** -a proteção contra violações está desativada e as restrições não são impostas.

### <a name="it-contact-information"></a>Informações de contato de TI  

Forneça as informações de contato de TI que aparecem no aplicativo da Central de Segurança do Windows Defender e as notificações do aplicativo.  

Você pode escolher **Exibir no aplicativo e em notificações**, **Exibir somente no aplicativo**, **Exibir somente em notificações** ou **Não exibir**. Insira o **nome da organização de TI** e, pelo menos, uma das seguintes opções de contato:  


- **Informações de contato de TI**  
  **Padrão**: não exibir  
  CSP WindowsDefenderSecurityCenter: [EnableCustomizedToasts](https://go.microsoft.com/fwlink/?linkid=873676)  
  
  Configure onde exibir informações de contato para os usuários finais.  
  
  - **Exibir no aplicativo e em notificações**  
  - **Exibir somente no aplicativo**  
  - **Exibir somente em notificações**  
  - **Não exibir**  

  Quando configurado para exibir, você pode definir as seguintes configurações:  

  - **Nome da organização de TI**  
    **Padrão**: *não configurado*  
    CSP WindowsDefenderSecurityCenter: [CompanyName](https://go.microsoft.com/fwlink/?linkid=873677)  

  - **Número de telefone ou ID do Skype do departamento de TI**  
    **Padrão**: *não configurado*  
    CSP WindowsDefenderSecurityCenter: [telefone](https://go.microsoft.com/fwlink/?linkid=873678) 

  - **Endereço de email do departamento de TI**  
    **Padrão**: *não configurado*  
    CSP WindowsDefenderSecurityCenter: [email](https://go.microsoft.com/fwlink/?linkid=873679)  

  - **URL do site de suporte de TI**  
    **Padrão**: *não configurado*  
    CSP WindowsDefenderSecurityCenter: [URL](https://go.microsoft.com/fwlink/?linkid=873680)  
 
## <a name="local-device-security-options"></a>Opções de segurança de dispositivo local  

Use estas opções para definir as configurações de segurança locais em dispositivos Windows 10.  

### <a name="accounts"></a>Contas  

- **Adicionar novas contas Microsoft**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [Accounts_BlockMicrosoftAccounts](https://go.microsoft.com/fwlink/?linkid=867916)  


  - **Bloquear** – impede os usuários de adicionar novas contas Microsoft ao dispositivo.  
  - **Não configurado** -os usuários podem usar contas da Microsoft no dispositivo.  

- **Logon remoto sem senha**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867890)  


   - **Bloquear** – permite que somente contas locais com senhas em branco entrem usando o teclado do dispositivo.  
   - **Não configurado** – permite que contas locais com senhas em branco entrem em locais diferentes do dispositivo físico.  

#### <a name="admin"></a>Administrador  

- **Conta do administrador local**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [Accounts_LimitLocalAccountUseOfBlankPasswordsToConsoleLogonOnly](https://go.microsoft.com/fwlink/?linkid=867850)  


  - **Bloquear** Impedir o uso de uma conta de administrador local.  
  - **Não configurado**  

- **Renomear a conta do administrador**  
  **Padrão**: *não configurado*  
  CSP LocalPoliciesSecurityOptions: [Accounts_RenameAdministratorAccount](https://go.microsoft.com/fwlink/?linkid=867917)  
 

  Defina um nome de conta diferente a ser associado ao SID (identificador de segurança) da conta do "Administrador".  

 #### <a name="guest"></a>Convidado  

- **Conta Convidado**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [LocalPoliciesSecurityOptions](https://go.microsoft.com/fwlink/?linkid=867853)  

  - **Bloquear** – impedir o uso de uma conta de convidado.  
  - **Não configurado**  

- **Renomear a conta Convidado**  
  **Padrão**: *não configurado*  
  CSP LocalPoliciesSecurityOptions: [Accounts_RenameGuestAccount](https://go.microsoft.com/fwlink/?linkid=867918)  
  
  Defina um nome de conta diferente a ser associado ao SID (identificador de segurança) da conta "Convidado".  

### <a name="devices"></a>Dispositivos  

- **Desencaixar dispositivo sem logon**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [Devices_AllowUndockWithoutHavingToLogon](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-devices-allowundockwithouthavingtologon)  

  
  - **Bloquear** – os usuários podem pressionar o botão físico de ejetar do dispositivo portátil encaixado para desencaixar o dispositivo com segurança.  
  - **Não configurado** -um usuário deve entrar no dispositivo e receber permissão para desencaixar o dispositivo.  

- **Instalar drivers de impressora para impressoras compartilhadas**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [Devices_PreventUsersFromInstallingPrinterDriversWhenConnectingToSharedPrinters](https://go.microsoft.com/fwlink/?linkid=867921)  


  - **Habilitado** – qualquer usuário pode instalar um driver de impressora como parte da conexão com uma impressora compartilhada.  
  - **Não configurado** – somente os Administradores podem instalar um driver de impressora como parte da conexão a uma impressora compartilhada.  

- **Restringir o acesso de CD-ROM ao usuário ativo local**  
  **Padrão**: não configurado  
  CSP: [Devices_RestrictCDROMAccessToLocallyLoggedOnUserOnly](https://go.microsoft.com/fwlink/?linkid=867922)  


  - **Habilitado** – somente o usuário conectado interativamente pode usar a mídia de CD-ROM. Se essa política está habilitada e ninguém está conectado interativamente, o CD-ROM é acessado pela rede.  
  - **Não configurado** -qualquer pessoa tem acesso ao CD-ROM.  

- **Formatar e ejetar a mídia removível**  
  **Padrão**: administradores  
  CSP: [Devices_AllowedToFormatAndEjectRemovableMedia](https://go.microsoft.com/fwlink/?linkid=867920)  
 

  Defina quem tem permissão para formatar e ejetar a mídia NTFS removível:  
  - **Não configurado**  
  - **Administradores**  
  - **Administradores e Usuários Avançados**  
  - **Administradores e Usuários Interativos**  

### <a name="interactive-logon"></a>Logon interativo  

- **Minutos de inatividade do bloqueio de tela até a proteção de tela ser ativada**  
  **Padrão**: *não configurado*  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_MachineInactivityLimit](https://go.microsoft.com/fwlink/?linkid=867891)  


  Insira o máximo de minutos de inatividade na tela de entrada da área de trabalho interativa até a proteção de tela ser iniciada. (**0** - **99999**)  

- **Exigir CTRL+ALT+DEL para fazer logon**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_DoNotRequireCTRLALTDEL](https://go.microsoft.com/fwlink/?linkid=867951)  


  - **Habilitar** – para que os usuários não precisem pressionar CTRL+ALT+DEL ao entrar.  
  - **Não configurado** – exige que os usuários pressionem CTRL+ALT+DEL antes de fazer logon no Windows.  

- **Comportamento de remoção do cartão inteligente**  
  **Padrão**: Bloquear estação de trabalho   
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_SmartCardRemovalBehavior](https://go.microsoft.com/fwlink/?linkid=868437)  
    
  Determina o que acontece quando o cartão inteligente de um usuário conectado é removido do leitor de cartão inteligente. Suas opções:  

  - **Bloquear Estação de Trabalho** – a estação de trabalho é bloqueada quando o cartão inteligente é removido. Essa opção permite que os usuários deixem a área, levem o cartão inteligente com eles e ainda mantenham uma sessão protegida.  
  - **Nenhuma ação**  
  - **Forçar Logoff** – o logoff do usuário é feito automaticamente quando o cartão inteligente é removido.  
  - **Desconectar em caso de uma sessão de Serviços de Área de Trabalho Remota** – a remoção do cartão inteligente desconecta a sessão sem fazer logoff do usuário. Essa opção permite que o usuário insira o cartão inteligente e retome a sessão mais tarde, ou em outro computador equipado com o leitor de cartão inteligente, sem precisar entrar novamente. Se a sessão for local, essa política funcionará de modo idêntico a Bloquear a Estação de Trabalho.  

#### <a name="display"></a>Monitor  

- **Informações do usuário na tela de bloqueio**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_DisplayUserInformationWhenTheSessionIsLocked](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-localpoliciessecurityoptions#localpoliciessecurityoptions-interactivelogon-displayuserinformationwhenthesessionislocked)  

  Configure as informações do usuário exibidas quando a sessão é bloqueada. Se não configurado, o nome de exibição do usuário, o domínio e o nome de usuário serão mostrados.  

  - **Não configurado**  
  - **Nome de exibição do usuário, domínio e nome de usuário**  
  - **Somente nome de exibição do usuário**  
  - **Não exibir informações do usuário**  

- **Ocultar o último usuário conectado**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_DoNotDisplayLastSignedIn](https://go.microsoft.com/fwlink/?linkid=868437)  
  
  
  - **Enable** -oculta o nome de usuário.  
  - **Não configurado** -mostra o último nome de usuário.  

- **Ocultar nome de usuário na entrada**
  **padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_DoNotDisplayUsernameAtSignIn](https://go.microsoft.com/fwlink/?linkid=867959)  

  
  - **Enable** -oculta o nome de usuário.  
  - **Não configurado** -mostra o último nome de usuário.  

- **Título da mensagem de logon**  
  **Padrão**: *não configurado*  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_MessageTitleForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867964)  

  Defina o título da mensagem para os usuários que estão se conectando.  

- **Texto da mensagem de logon**  
  **Padrão**: *não configurado*  
  CSP LocalPoliciesSecurityOptions: [InteractiveLogon_MessageTextForUsersAttemptingToLogOn](https://go.microsoft.com/fwlink/?linkid=867962)  

  Defina o texto da mensagem para os usuários que estão se conectando.  
  
### <a name="network-access-and-security"></a>Acesso e segurança de rede

- **Acesso anônimo a Compartilhamentos e Pipes Nomeados**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [NetworkAccess_RestrictAnonymousAccessToNamedPipesAndShares](https://go.microsoft.com/fwlink/?linkid=868432)  

  - **Não configurado** – restringe o acesso anônimo às configurações de compartilhamento e Pipe Nomeado. Aplica-se às configurações que podem ser acessadas anonimamente.  
  - **Bloquear** -desabilitar esta política, disponibilizando o acesso anônimo.  

- **Enumeração anônima de contas do SAM**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSAMAccounts](https://go.microsoft.com/fwlink/?linkid=868434)  
  
  - **Não configurado** -os usuários anônimos podem enumerar contas Sam.  
  - **Bloquear** – impede a enumeração anônima de contas do SAM.  

- **Enumeração anônima de compartilhamentos e contas do SAM**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [NetworkAccess_DoNotAllowAnonymousEnumerationOfSamAccountsAndShares](https://go.microsoft.com/fwlink/?linkid=868435)  

  - **Não configurado** – os usuários anônimos podem enumerar os nomes de contas de domínio e compartilhamentos de rede.  
  - **Bloquear** – impede compartilhamentos e a enumeração anônima de contas do SAM. 

- **Valor do hash do LAN Manager armazenado na alteração de senha**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [NetworkSecurity_DoNotStoreLANManagerHashValueOnNextPasswordChange](https://go.microsoft.com/fwlink/?linkid=868431)  
   
  Determine se o valor de hash para senhas é armazenado na próxima vez em que a senha for alterada. 
  - **Não configurado** -o valor de hash não está armazenado  
  - **Bloquear** – o LM (Gerenciador de LAN) armazena o valor de hash para a nova senha.  

- **Solicitações de autenticação PKU2U**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [NetworkSecurity_AllowPKU2UAuthenticationRequests](https://go.microsoft.com/fwlink/?linkid=867892)  

  - **Não configurado**-permitir solicitações PU2U.  
  - **Bloqueie as** solicitações de autenticação PKU2U para o dispositivo.  

- **Restringir conexões RPC remotas com o SAM**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [NetworkAccess_RestrictClientsAllowedToMakeRemoteCallsToSAM](https://go.microsoft.com/fwlink/?linkid=867893)  
  
  - **Não configurado** -use o descritor de segurança padrão, que pode permitir que usuários e grupos façam chamadas RPC remotas para o Sam.
  - **Permitir** -negar que usuários e grupos façam chamadas RPC remotas para o Sam (Gerenciador de contas de segurança), que armazena contas de usuário e senhas. **Permitir** também permite que você altere a cadeia de caracteres SDDL (linguagem de definição de descritor de segurança) padrão para permitir ou negar explicitamente usuários e grupos para fazer essas chamadas remotas.  

    - **Descritor de segurança**  
      **Padrão**: *não configurado*  
    
- **Segurança mínima de sessão para clientes baseados em NTLM SSP**  
  **Padrão**: nenhum  
  CSP LocalPoliciesSecurityOptions: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedClients](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedclients)  
  
  Essa configuração de segurança permite que um servidor exija a negociação de criptografia de 128 bits e/ou segurança de sessão NTLMv2.  

  - **Nenhum**  
  - **Exigir segurança de sessão NTLMv2**  
  - **Exigir criptografia de 128 bits**  
  - **Exigir criptografia de 128 bits e NTLMv2**  
 
- **Segurança mínima de sessão para servidores baseados em NTLM SSP**  
  **Padrão**: nenhum  
  CSP LocalPoliciesSecurityOptions: [NetworkSecurity_MinimumSessionSecurityForNTLMSSPBasedServers](https://aka.ms/policy-csp-localpoliciessecurityoptions-networksecurity-minimumsessionsecurityforntlmsspbasedservers)  

  Essa configuração de segurança determina qual protocolo de autenticação de desafio/resposta é usado para logons de rede.  

  - **Nenhum**  
  - **Exigir segurança de sessão NTLMv2**  
  - **Exigir criptografia de 128 bits**  
  - **Exigir criptografia de 128 bits e NTLMv2**  

- **Nível de autenticação do LAN Manager**  
  **Padrão**: LM e NTLM  
  CSP LocalPoliciesSecurityOptions: [NetworkSecurity_LANManagerAuthenticationLevel](https://aka.ms/policy-csp-localpoliciessecurityoptions-lanmanagerauthenticationlevel)  


  - **LM e NTLM**  
  - **LM, NTLM e NTLMv2**  
  - **NTLM**  
  - **NTLMv2**  
  - **NTLMv2 e não LM**  
  - **NTLMv2 e não LM ou NTLM**  
  
- **Logons de convidado não seguros**  
  **Padrão**: não configurado  
  CSP LanmanWorkstation: [LanmanWorkstation](https://aka.ms/policy-csp-lanmanworkstation-enableinsecureguestlogons)  

  Se você habilitar essa configuração, o cliente SMB rejeitará logons de convidado inseguros.  

  - **Não configurado**  
  - **Bloquear** – o cliente SMB rejeita logons de convidado inseguros.  

### <a name="recovery-console-and-shutdown"></a>Console de recuperação e desligamento  

- **Limpar arquivo de paginação de memória virtual ao desligar**  
  **Padrão**: não configurado  
   CSP LocalPoliciesSecurityOptions: [Shutdown_ClearVirtualMemoryPageFile](https://go.microsoft.com/fwlink/?linkid=867914)  


  - **Habilitar** – limpa o arquivo de paginação de memória virtual quando o dispositivo for desligado.  
  - **Não configurado** – não limpa a memória virtual.  

- **Desligar sem fazer logon**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [Shutdown_AllowSystemToBeShutDownWithoutHavingToLogOn](https://go.microsoft.com/fwlink/?linkid=867912)  

  
  - **Bloquear** – oculta a opção de desligamento na tela de entrada do Windows. Os usuários precisam entrar no dispositivo e, em seguida, desligá-lo.  
  - **Não configurado** – permite que os usuários desliguem o dispositivo na tela de entrada do Windows.  

### <a name="user-account-control"></a>Controle de conta de usuário  

- **Integridade de UIA sem localização segura**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867897)  
  
  - Os aplicativos de **bloco** que estão em um local seguro no sistema de arquivos serão executados somente com a integridade do UIAccess.  
  - **Não configurado** – permite que os aplicativos sejam executados com a integridade de UIAccess, mesmo se eles não estiverem em um local seguro no sistema de arquivos.  

- **Virtualizar falhas de gravação de arquivos e do Registro para locais por usuário**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_VirtualizeFileAndRegistryWriteFailuresToPerUserLocations](https://go.microsoft.com/fwlink/?linkid=867900)  

  - **Habilitada** – aplicativos que gravam dados em locais protegidos apresentam falhas.  
  - **Não configurado** – falhas de gravação de aplicativos são direcionadas em tempo de execução a localizações de usuário definidas tanto para o sistema de arquivos quanto para o Registro.  

- **Elevar somente arquivos executáveis assinados e validados**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_OnlyElevateUIAccessApplicationsThatAreInstalledInSecureLocations](https://go.microsoft.com/fwlink/?linkid=867965)  

  - **Habilitado** – impõe a validação de caminho de certificação de PKI para um arquivo executável antes que ele possa ser executado.  
  - **Não configurado** – não impõe a validação de caminho de certificação de PKI antes da execução de um arquivo executável.  

#### <a name="uia-elevation-prompt-behavior"></a>Comportamento da solicitação de elevação de UIA  

- **Solicitação de elevação para administradores**  
  **Padrão**: solicita o consentimento para binários que não forem do Windows  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_BehaviorOfTheElevationPromptForAdministrators](https://go.microsoft.com/fwlink/?linkid=867895)  

  Defina o comportamento da solicitação de elevação de administradores no Modo de Aprovação de Administrador.  

  - **Não configurado**  
  - **Elevar sem solicitar**  
  - **Solicitar credenciais na área de trabalho protegida**  
  - **Solicitar credenciais**  
  - **Solicitar consentimento**  
  - **Solicitar consentimento para binários não Windows**  


- **Solicitação de elevação para usuários padrão**  
  **Padrão**: solicita credenciais  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_BehaviorOfTheElevationPromptForStandardUsers](https://go.microsoft.com/fwlink/?linkid=867896)  

  Define o comportamento da solicitação de elevação para usuários padrão.  

  - **Não configurado**  
  - **Negar automaticamente solicitações de elevação**  
  - **Solicitar credenciais na área de trabalho protegida**  
  - **Solicitar credenciais**  

- **Encaminhar solicitações de elevação para a área de trabalho interativa do usuário**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_SwitchToTheSecureDesktopWhenPromptingForElevation](https://go.microsoft.com/fwlink/?linkid=867899)  


  - **Habilitado** -todas as solicitações de elevação para ir para a área de trabalho do usuário interativo em vez da área de trabalho segura. As configurações de política de comportamento de solicitação para administradores e usuários padrão são usadas.  
  - **Não configurado** – força todas as solicitações de elevação a serem encaminhadas para a área de trabalho protegida, independentemente das configurações de política de comportamento de prompts para administradores e usuários padrão.

- **Prompt com privilégios elevados para instalações de aplicativo**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_DetectApplicationInstallationsAndPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867901)  

   - **Habilitado** – pacotes de instalação do aplicativo não são detectados ou solicitados a fornecer elevação.
   - **Não configurado** – o usuário é solicitado a fornecer um nome de usuário administrativo e uma senha quando um pacote de instalação de aplicativo exige privilégios elevados.

- **Solicitação de elevação de UIA sem a área de trabalho protegida**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_AllowUIAccessApplicationsToPromptForElevation](https://go.microsoft.com/fwlink/?linkid=867894)  

- **Habilitar** – permite que aplicativos de UIAccess solicitem elevação sem usar a área de trabalho protegida.  
- **Não configurado** -as solicitações de elevação usam uma área de trabalho segura.  

#### <a name="admin-approval-mode"></a>Modo de Aprovação de Administrador  

- **Modo de Aprovação de Administrador para conta de administrador interno**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_UseAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867902)  

  - **Habilitado** – permite que a conta de administrador interno use o Modo de Aprovação de Administrador. Qualquer operação que exija a elevação de privilégio solicita que o usuário aprove a operação.  
  - **Não configurado** – executa todos os aplicativos com privilégios completos de administrador.  

- **Executar todos os administradores no Modo de Aprovação de Administrador**  
  **Padrão**: Não configurado  
  CSP LocalPoliciesSecurityOptions: [UserAccountControl_RunAllAdministratorsInAdminApprovalMode](https://go.microsoft.com/fwlink/?linkid=867898)  


  - **Habilitado**– habilitar o modo de aprovação de administrador.  
  - **Não configurado** – desabilita o Modo de Aprovação de Administrador e todas as configurações de política do UAC relacionadas.  

### <a name="microsoft-network-client"></a>Cliente da Rede Microsoft  

- **Assinar as comunicações digitalmente (se o servidor concordar)**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [MicrosoftNetworkClient_DigitallySignCommunicationsIfServerAgrees](https://go.microsoft.com/fwlink/?linkid=868423)  

  Determina se o cliente SMB negocia a assinatura de pacotes SMB.  
  - **Bloquear** – o cliente SMB nunca negocia a assinatura de pacote SMB.
  - **Não configurado** – o cliente de rede Microsoft solicita que o servidor execute a assinatura de pacote SMB na configuração da sessão. Se a assinatura de pacote estiver habilitada no servidor, a assinatura de pacote será negociada.  

- **Enviar senha não criptografada para servidores SMB de terceiros**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [MicrosoftNetworkClient_SendUnencryptedPasswordToThirdPartySMBServers](https://go.microsoft.com/fwlink/?linkid=868426)  


  - **Bloquear** – o redirecionador do protocolo SMB pode enviar senhas em texto não criptografado para servidores SMB não Microsoft que não dão suporte à criptografia de senha durante a autenticação.  
  - **Não configurado** -bloqueia o envio de senhas de texto sem formatação. As senhas são criptografadas.  

- **Assinar as comunicações digitalmente (sempre)**  
  **Padrão**: não configurado  
  CSP LocalPoliciesSecurityOptions: [MicrosoftNetworkClient_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868425)  


  - **Habilitar** – o cliente de rede da Microsoft não se comunica com o servidor de rede da Microsoft, a menos que o servidor concorde em executar a assinatura do pacote SMB.  
  - **Não configurado** -a assinatura de pacote SMB é negociada entre o cliente e o servidor.  

### <a name="microsoft-network-server"></a>Microsoft Network Server  
  
- **Assinar as comunicações digitalmente (se o cliente concordar)**  
  **Padrão**: não configurado  
  CSP: [MicrosoftNetworkServer_DigitallySignCommunicationsIfClientAgrees](https://go.microsoft.com/fwlink/?linkid=868429)  

  - **Habilitar** – o servidor da rede Microsoft negocia a assinatura de pacote SMB conforme solicitado pelo cliente. Ou seja, se a assinatura de pacote estiver habilitada no cliente, a assinatura de pacote será negociada.  
  - **Não configurado** -o cliente SMB nunca negocia a assinatura de pacote SMB.  

- **Assinar as comunicações digitalmente (sempre)**  
  **Padrão**: não configurado  
  CSP: [MicrosoftNetworkServer_DigitallySignCommunicationsAlways](https://go.microsoft.com/fwlink/?linkid=868428)  

  - **Habilitar** – o servidor de rede da Microsoft não se comunica com um cliente de rede da Microsoft, a menos que o cliente concorde em executar a assinatura do pacote SMB.  
  - **Não configurado** -a assinatura de pacote SMB é negociada entre o cliente e o servidor.  

## <a name="xbox-services"></a>Serviços do Xbox

- **Tarefa de salvamento de jogo do Xbox**  
  **Padrão**: não configurado  
  CSP: [TaskScheduler/EnableXboxGameSaveTask](https://go.microsoft.com/fwlink/?linkid=875480)  
   
  Essa configuração determina se a tarefa de salvamento do jogo Xbox está habilitada ou desabilitada.  
  - **Enabled**
  - **Não configurado**

- **Serviço de gerenciamento de acessórios do Xbox**  
  **Padrão**: manual  
  CSP: [systemservices/ConfigureXboxAccessoryManagementServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875481)  

  Essa configuração determina o tipo de início do serviço de gerenciamento de acessórios.  
  - **Manual**
  - **Automático**
  - **Desabilitado**

- **Serviço do Gerenciador de autenticação Xbox Live**  
  **Padrão**: manual  
  CSP: [systemservices/ConfigureXboxLiveAuthManagerServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875482)  
 
  Essa configuração determina o tipo de início do serviço do Gerenciador de autenticação dinâmica.  
  - **Manual**
  - **Automático**
  - **Desabilitado**
 
- **Serviço de salvamento do jogo Xbox Live**  
  **Padrão**: manual  
  CSP: [systemservices/ConfigureXboxLiveGameSaveServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875483)  

  Essa configuração determina o tipo de início do serviço de salvamento de jogo ao vivo.  
  - **Manual**
  - **Automático**
  - **Desabilitado**

- **Serviço de rede Xbox Live**  
  **Padrão**: manual  
  CSP: [systemservices/ConfigureXboxLiveNetworkingServiceStartupMode](https://go.microsoft.com/fwlink/?linkid=875484)  

  Essa configuração determina o tipo de início do serviço de rede.  
  - **Manual**
  - **Automático**
  - **Desabilitado**

## <a name="next-steps"></a>Próximas etapas

O perfil foi criado, mas não está fazendo nada ainda. Em seguida, [atribua o perfil](../configuration/device-profile-assign.md) e [monitore seu status](../configuration/device-profile-monitor.md).  

Definir configurações de proteções de ponto de extremidade em dispositivos [macOS](endpoint-protection-macos.md).  
