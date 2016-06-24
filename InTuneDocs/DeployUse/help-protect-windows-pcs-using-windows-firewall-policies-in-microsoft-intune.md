---
# required metadata

title: Políticas de firewall para computadores Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Ajude a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune
O Microsoft Intune pode ajudá-lo a proteger seus computadores Windows gerenciados com o cliente do Intune, incluindo o uso de políticas que permitem que você defina as configurações de Firewall do Windows nos computadores.

Se você ainda não tiver instalado o cliente em seus computadores Windows com Intune, consulte [Install the Windows PC client with Microsoft Intune (Instalar o cliente do computador Windows com o Microsoft Intune)](install-the-windows-pc-client-with-microsoft-intune.md).

Use as informações nas seções a seguir para ajudar a configurar, implantar e monitorar as políticas de Firewall do Windows nos computadores Windows.

## Usar as políticas do Intune para gerenciar o Firewall do Windows
A política de Firewall do Windows permite criar e implantar as configurações que controlam o Firewall do Windows em computadores gerenciados. Não é possível gerenciar exceções personalizadas para o Firewall do Windows e essas configurações não afetam os firewalls de terceiros.

> [!NOTE]
> Se a política do Microsoft Intune e a Política de grupo estiverem configuradas para gerenciar a mesma configuração no computador, a configuração da Política de grupo substituirá a política do Microsoft Intune. Para obter informações sobre como evitar conflitos entre as políticas do Intune e a Política de grupo, consulte [Resolve GPO and Microsoft Intune policy conflicts (Resolver conflitos de política do Microsoft Intune e de GPO)](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Se você quiser implantar configurações de Firewall do Windows em computadores que executam o Windows Vista, você deve primeiro instalar o [Hotfix KB971800](http://support2.microsoft.com/kb/971800) nesses computadores.

> [!IMPORTANT]
> Para gerenciar o Firewall do Windows usando o Intune, você deve garantir que os dois serviços a seguir estejam habilitados nos computadores que você gerenciará:
>
> -   Firewall do Windows
> -   Agente de diretiva do IPsec

## Configurar uma política de Firewall do Windows

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Política** &gt; **Adicionar Política**.

2.  Defina e implante uma política de **Configurações de firewall do Windows** . É possível usar as configurações recomendadas ou personalizá-las. Se você precisar de mais informações sobre como criar e implantar políticas, consulte [Common Windows PC management tasks with the Microsoft Intune computer client (Tarefas comuns de gerenciamento de computador Windows com o cliente do computador Microsoft Intune)](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    A seção a seguir lista os valores que você pode configurar na política e também os valores padrão que serão usados se a política não for personalizada.

Após implantar uma política de Firewall do Windows, você pode exibir seu status na página **Todas as políticas** no espaço de trabalho **Política**.

## Configurações de política do Firewall do Windows

### Ativar Firewall do Windows

Essas configurações de política habilitam o Firewall do Windows nos computadores gerenciados, conectados a um domínio (por exemplo, no local de trabalho), uma rede privada (confiável) (como uma rede doméstica) ou uma rede não confiável, pública (como a de uma cafeteria). O valor padrão para cada uma dessas configurações é **Sim**, que é o valor mais seguro. 



### Bloquear todas as conexões de entrada, incluindo aquelas na lista de programas permitidos

Essas configurações de política definem o Firewall do Windows para bloquear o tráfego de entrada da rede quando o computador gerenciado é conectado a um domínio (por exemplo, no local de trabalho), uma rede privada (confiável) (como uma rede doméstica) ou uma rede não confiável, pública (como a de uma cafeteria). O valor padrão para cada uma dessas configurações é **Sim**, que é o valor mais seguro. 

> [!IMPORTANT]
> Se seu ambiente incluir computadores gerenciados que executam o Windows Vista sem service packs instalados, você deverá instalar a atualização associada ao [artigo 971800](http://go.microsoft.com/fwlink/?LinkId=188405) da Base de Dados de Conhecimento Microsoft ou desabilitar as configurações da política **Bloquear todas as conexões de entrada** nas políticas implantadas nesses computadores.

### Notificar o usuário quando o Firewall do Windows bloquear um novo programa

Essas configurações de política definem se o Firewall do Windows notifica o usuário do computador quando o tráfego de entrada da rede é bloqueado quando o computador gerenciado é conectado a um domínio (por exemplo, no local de trabalho), uma rede privada (confiável) (como uma rede doméstica) ou uma rede não confiável, pública (como a de uma cafeteria). O valor padrão para cada uma dessas configurações é **Sim**.


### Exceções predefinidas

Depois de configurar os valores básicos descritos acima, você pode configurar as exceções que permitem um determinado tráfego de rede através do firewall, independentemente dos valores configurados acima. Por padrão, nenhuma dessas definições são configuradas.

|Nome da configuração|Detalhes|
|------------------|--------------------|
|**BranchCache - Recuperação de Conteúdo**<br>(Windows 7 ou posterior)|Permite aos clientes BranchCache usar HTTP para recuperar conteúdo uns dos outros no modo distribuído e também do cache hospedado no modo de cache hospedado. Essa configuração usa HTTP.|
|**BranchCache - Cliente de Cache Hospedado**<br>(Windows 7 ou posterior)|Permite que os clientes BranchCache usem um cache hospedado. Essa configuração usa HTTPS.|
|**BranchCache - Servidor de Cache Hospedado**|Permite que os clientes BranchCache usem um cache hospedado para se comunicar com outros clientes. Essa configuração usa HTTPS.|
|**BranchCache - Descoberta de Mesmo Nível**<br>(Windows 7 ou posterior)|Permite que os clientes BranchCache usem o protocolo de descoberta WS para pesquisar a disponibilidade do conteúdo na sub-rede local.|
|**Serviço de Cache de Mesmo Nível de BITS**|Permite que os clientes usem BITS (Background Intelligent Transfer Service) para encontrar e compartilhar arquivos que estão armazenados no cache BITS em clientes na mesma sub-rede. Essa configuração usa WSDAPI e RPC.|
|**Conectar a um Projetor de Rede**|Permite aos usuários conectarem-se a projetores por meio de redes com ou sem fio para projetar apresentações. Essa configuração usa WSDAPI.|
|**Sistema de Rede Básico**|Permite que os clientes usem IPv4 e IPv6 para se conectarem aos recursos da rede.|
|**Coordenador de Transações Distribuídas**|Permite que os computadores gerenciados coordenem as transações que atualizam recursos protegidos para transações, como bancos de dados, filas de mensagens e sistemas de arquivos.|
|**Compartilhamento de Arquivos e Impressoras**|Permite que os usuários compartilhem arquivos e impressoras locais com outros usuários na rede. Essa configuração usa NetBIOS, LLMNR, SMB e RPC.|
|**HomeGroup**<br>(Windows 7 ou posterior)|Permite que os computadores gerenciados participem de uma rede de grupo doméstico.|
|**Serviço iSCSI**|Permite que os computadores gerenciados se conectem a servidores e dispositivos iSCSI.|
|**Serviço de Gerenciamento de Chaves**|Permite que computadores sejam contados para conformidade de licenças em ambientes corporativos.|
|**Extensores do Media Center**|Permite que os Media Center Extenders se comuniquem com computadores executando o Windows Media Center. Essa configuração usa SSDP e qWave.|
|**Serviço de Logon de Rede**|Configura um canal de segurança entre clientes de domínio e um controlador de domínio para autenticar usuários e serviços. Essa configuração usa RPC.|
|**Descoberta de Rede**|Permite que os computadores descubram outros dispositivos e sejam descobertos por outros dispositivos na rede. Essa configuração usa Serviços de Host e Publicação da Descoberta de Função, bem como protocolos de rede SSDP, NetBIOS, LLMNR e UPnP™.|
|**Alertas e Logs de Desempenho**|Permite que o serviço de Logs e Alertas de Desempenho seja gerenciado remotamente. Essa configuração usa RPC.|
|**Administração Remota**|Permite a administração remota do computador.|
|**Assistência Remota**|Permite que os usuários de computadores gerenciados solicitem assistência remota de outros usuários na rede. Essa configuração usa protocolos de rede SSDP, PNRP, Teredo e UPnP.|
|**Área de Trabalho Remota**|Permite que o computador use a Área de Trabalho Remota para acessar outros computadores.|
|**Gerenciamento Remoto do Log de Eventos**|Permite que o log de eventos do cliente seja exibido e gerenciado remotamente. Essa configuração usa Pipes Nomeados e RPC.|
|**Gerenciamento Remoto de Tarefas Agendadas**|Permite o gerenciamento remoto do serviço de agendamento de tarefas. Essa configuração usa RPC.|
|**Gerenciamento Remoto de Serviços**|Permite o gerenciamento remoto de serviços locais em clientes. Essa configuração usa Pipes Nomeados e RPC.|
|**Gerenciamento de Volumes Remoto**|Permite o gerenciamento remoto de volumes de disco de software e hardware. Essa configuração usa RPC.|
|**Roteamento e Acesso Remoto**|Permite conexões de entrada VPN e acesso remoto a computadores.|
|**SSTP (Secure Socket Tunneling Protocol)**|Permite conexões de entrada VPN a computadores gerenciados usando o SSTP (Secure Socket Tunneling Protocol). Essa configuração usa HTTPS.|
|**Interceptação SNMP**|Permite que os computadores gerenciados recebam tráfego de serviço de interceptação SNMP.|
|**Estrutura UPnP**|Configura o serviço de Estrutura UPnP nos computadores para permitir que eles descubram e usem dispositivos UPnP.|
|**Serviço de Registro de Nomes de Computador da Colaboração do Windows**|Permite que os computadores gerenciados localizem e se comuniquem com outros computadores usando o protocolo PNRP. Essa configuração usa SSDP e PNRP.|
|**Windows Media Player**|Permite que os usuários recebam mídia de streaming por UDP.|
|**Serviço de Compartilhamento de Rede do Windows Media Player**|Permite que os usuários compartilhem mídia por uma rede. Essa configuração usa os protocolos de rede SSDP, qWave e UPnP.|
|**Serviço de Compartilhamento de Rede do Windows Media Player (Internet)**<br>(Windows 7 ou posterior)|Permite que os usuários compartilhem mídia pela Internet.|
|**Espaço de Reunião do Windows**|Permite que os usuários colaborem por uma rede para compartilhar documentos, programas ou sua área de trabalho. Essa configuração usa DFSR e P2P.|
|**Base da Colaboração Ponto a Ponto do Windows**|Configura vários programas e tecnologias ponto a ponto para permitir que eles se conectem. Essa configuração usa SSDP e PNRP.|
|**Gerenciamento Remoto do Windows (Compatibilidade)**|Permite o gerenciamento remoto de computadores usando o WS-Management, um protocolo baseado em serviços Web para o gerenciamento remoto de dispositivos e sistemas operacionais.|
|**Windows Remote Management**<br>(Windows 8 ou posterior)|Permite o gerenciamento remoto de computadores usando o WS-Management, um protocolo baseado em serviços Web para o gerenciamento remoto de dispositivos e sistemas operacionais.|
|**Windows Virtual PC**<br>(Windows 7 ou posterior)|Permite que máquinas virtuais se comuniquem com outros computadores.|
|**Dispositivos Portáteis sem Fio**|Permite a transferência de mídia de um dispositivo de mídia ou câmera habilitada para rede para computadores gerenciados usando o MTP (Protocolo de Transferência de Mídia). Essa configuração usa protocolos de rede SSDP e UPnP.|

### Consulte também
[Políticas para proteger computadores Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)


<!--HONumber=May16_HO1-->


