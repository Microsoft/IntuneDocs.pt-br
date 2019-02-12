---
title: Políticas de firewall para computadores Windows
titlesuffix: Microsoft Intune
description: O Intune pode ajudá-lo a proteger seus computadores gerenciados com o cliente do Intune, incluindo ajuda para definir as configurações do Firewall do Windows.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 30532c87fe8b6e9d96bf00d45a29f4da4a99b9da
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849776"
---
# <a name="help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune"></a>Ajude a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune

[!INCLUDE [classic-portal](includes/classic-portal.md)]

O Microsoft Intune pode ajudá-lo a proteger seus computadores Windows gerenciados com o cliente do Intune de várias maneiras. Uma maneira em que ele faz isso é fornecer políticas que permitem que você defina as configurações de Firewall do Windows em computadores.

Se você ainda não tiver instalado o cliente em seus computadores Windows com Intune, consulte [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) (Instalar o cliente do computador Windows com o Microsoft Intune).

Use as informações nas seções a seguir para ajudar a configurar, implantar e monitorar as políticas de Firewall do Windows nos computadores Windows.

## <a name="use-intune-policies-to-manage-windows-firewall"></a>Usar as políticas do Intune para gerenciar Firewall do Windows
A política de Firewall do Windows permite criar e implantar as configurações que controlam o Firewall do Windows em computadores gerenciados. Não é possível gerenciar exceções personalizadas para o Firewall do Windows e essas configurações não afetam os firewalls de terceiros.

> [!NOTE]
> Se a política do Microsoft Intune e a Política de grupo estiverem configuradas para gerenciar a mesma configuração no computador, a configuração da Política de grupo substituirá a política do Microsoft Intune. Para obter informações sobre como evitar conflitos entre a política do Intune e a Política de Grupo, consulte [Resolve GPO and Microsoft Intune policy conflicts](resolve-gpo-and-microsoft-intune-policy-conflicts.md) (Resolver conflitos de política de GPO e do Microsoft Intune).
>
> Se desejar implantar configurações de Firewall do Windows em computadores que executam o Windows Vista, você deverá primeiro instalar o [Hotfix KB971800](http://support2.microsoft.com/kb/971800) nesses computadores.

> [!IMPORTANT]
> Para gerenciar o Firewall do Windows usando o Intune, verifique se os dois serviços a seguir estão habilitados nos computadores que você gerencia:
>
> -   Firewall do Windows
> -   Agente de diretiva do IPsec

## <a name="configure-a-windows-firewall-policy"></a>Configurar uma política de Firewall do Windows

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Política** &gt; **Adicionar Política**.

2.  Defina e implante uma política de **Configurações de firewall do Windows** . É possível usar as configurações recomendadas ou personalizá-las. Se você precisar de mais informações sobre como criar e implantar políticas, consulte [Common Windows PC management tasks with the Microsoft Intune computer client](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md) (Tarefas comuns de gerenciamento de computador Windows com o cliente do computador Microsoft Intune).

    A seção a seguir lista os valores que você pode configurar na política e também os valores padrão que serão usados se a política não for personalizada.

Após implantar uma política de Firewall do Windows, você pode exibir seu status na página **Todas as políticas** no workspace **Política**.

## <a name="specify-policy-settings-for-windows-firewall"></a>Especificar as configurações de política do Firewall do Windows

### <a name="turn-on-windows-firewall"></a>Ativar Firewall do Windows

Essas configurações de política habilitam o Firewall do Windows nos computadores gerenciados que estão:
- Conectados a um domínio (por exemplo, no local de trabalho)
- Conectado a uma rede privada (confiável) (como uma rede doméstica)
- Conectados a uma rede pública não confiável (como uma cafeteria)

O valor padrão para cada uma dessas configurações é **Sim**, que é o valor mais seguro.



### <a name="block-all-incoming-connections-including-those-in-the-list-of-allowed-programs"></a>Bloquear todas as conexões de entrada, incluindo aquelas na lista de programas permitidos

Essas configurações de política configuram Firewall do Windows para bloquear o tráfego de entrada de rede em computadores gerenciados que estão:
- Conectado a um domínio (por exemplo, no local de trabalho)
- Conectado a uma rede privada (confiável) (como uma rede doméstica)
- Conectados a uma rede pública não confiável (como uma cafeteria)

O valor padrão para cada uma dessas configurações é **Sim**, que é o valor mais seguro.

> [!IMPORTANT]
> Se o seu ambiente incluir computadores gerenciados que executam o Windows Vista sem service packs instalados, você deverá instalar a atualização associada ao [artigo 971800](http://go.microsoft.com/fwlink/?LinkId=188405) da Base de Dados de Conhecimento Microsoft ou desabilitar as configurações da política **Bloquear todas as conexões de entrada** nas políticas implantadas nesses computadores.

### <a name="notify-the-user-when-windows-firewall-blocks-a-new-program"></a>Notificar o usuário quando o Firewall do Windows bloquear um novo programa

Essas configurações de política determinam se o Firewall do Windows notifica um usuário de computador quando o tráfego de entrada de rede for bloqueado quando o computador gerenciado estiver:
- Conectado a um domínio (por exemplo, no local de trabalho)
- Conectado a uma rede privada (confiável) (como uma rede doméstica)
- Conectado a uma rede pública não confiável (como uma cafeteria)

O valor padrão para cada uma dessas configurações é **Sim**.


### <a name="configure-predefined-exceptions"></a>Configurar exceções predefinidas

Você pode configurar as exceções que permitem tipos específicos de tráfego de rede através do firewall, independentemente dos valores configurados anteriormente. Nenhuma dessas definições são configuradas por padrão.

|Nome da configuração|Detalhes|
|------------------|--------------------|
|**BranchCache – Recuperação de Conteúdo**<br>(Windows 7 ou posterior)|Permite aos clientes BranchCache usar HTTP para recuperar conteúdo uns dos outros clientes BranchCache no modo distribuído e também do cache hospedado no modo de cache hospedado. Essa configuração usa HTTP.|
|**BranchCache – Cliente de Cache Hospedado**<br>(Windows 7 ou posterior)|Permite que os clientes BranchCache usem um cache hospedado. Essa configuração usa HTTPS.|
|**BranchCache – Servidor de Cache Hospedado**|Permite que os clientes BranchCache usem um cache hospedado para se comunicar com outros clientes. Essa configuração usa HTTPS.|
|**BranchCache – Descoberta de Pares**<br>(Windows 7 ou posterior)|Permite que os clientes BranchCache usem o protocolo de descoberta de serviços Web (WS-Discovery) para pesquisar a disponibilidade do conteúdo na sub-rede local.|
|**Cache par do BITS**|Permite que os clientes usem BITS (Background Intelligent Transfer Service) para encontrar e compartilhar arquivos que estão armazenados no cache BITS em clientes na mesma sub-rede. Essa configuração usa serviços Web em dispositivos (WSDAPI) e Chamada de procedimento remoto (RPC).|
|**Conectar a um Projetor de Rede**|Permite aos usuários conectarem-se a projetores por meio de redes com ou sem fio para projetar apresentações. Essa configuração usa WSDAPI.|
|**Rede Principal**|Permite que os clientes usem IPv4 e IPv6 para se conectarem aos recursos da rede.|
|**Coordenador de Transações Distribuídas**|Permite que computadores gerenciados coordenem as transações que atualizam recursos protegidos para transações, como bancos de dados, filas de mensagens e sistemas de arquivos.|
|**Compartilhamento de Arquivos e Impressoras**|Permite que os usuários compartilhem arquivos e impressoras locais com outros usuários na rede. Essa configuração usa NetBIOS, Resolução de Nome Multicast Local de Link (LLMNR), protocolo SMB (Server Message Block) e RPC.|
|**HomeGroup**<br>(Windows 7 ou posterior)|Permite que os computadores gerenciados participem de uma rede HomeGroup.|
|**Serviço iSCSI**|Permite que os computadores gerenciados se conectem a servidores e dispositivos iSCSI.|
|**Serviço de Gerenciamento de Chaves**|Permite que computadores sejam contados para conformidade de licenças em ambientes corporativos.|
|**Media Center Extenders**|Permite que os Media Center Extenders se comuniquem com computadores executando o Windows Media Center. Essa configuração usa Simple Service Discovery Protocol (SSDP) e qWave.|
|**Serviço de Logon de Rede**|Configura um canal de segurança entre clientes de domínio e um controlador de domínio para autenticar usuários e serviços. Essa configuração usa RPC.|
|**Descoberta de Rede**|Permite que os computadores descubram outros dispositivos e sejam descobertos por outros dispositivos na rede. Essa configuração usa Serviços de Host e Publicação da Descoberta de Função, bem como protocolos de rede SSDP, NetBIOS, LLMNR e UPnP™.|
|**Logs e Alertas de Desempenho**|Permite que o serviço de Logs e Alertas de Desempenho seja gerenciado remotamente. Essa configuração usa RPC.|
|**Administração Remota**|Permite a administração remota do computador.|
|**Assistência Remota**|Permite que os usuários de computadores gerenciados solicitem assistência remota de outros usuários na rede. Essa configuração usa protocolos de rede SSDP, protocolo PNRP, Teredo e UPnP.|
|**Área de Trabalho Remota**|Permite que o computador use a Área de Trabalho Remota para acessar outros computadores.|
|**Gerenciamento Remoto do Log de Eventos**|Permite que o log de eventos do cliente seja exibido e gerenciado remotamente. Essa configuração usa Pipes Nomeados e RPC.|
|**Gerenciamento Remoto de Tarefas Agendadas**|Permite o gerenciamento remoto do serviço de agendamento de tarefas. Essa configuração usa RPC.|
|**Gerenciamento Remoto de Serviços**|Permite o gerenciamento remoto de serviços locais em clientes. Essa configuração usa Pipes Nomeados e RPC.|
|**Gerenciamento de Volumes Remoto**|Permite o gerenciamento remoto de volumes de disco de software e hardware. Essa configuração usa RPC.|
|**Roteamento e Acesso Remoto**|Permite conexões de entrada VPN e acesso remoto a computadores.|
|**Protocolo SSTP**|Permite conexões de entrada VPN a computadores gerenciados com SSTP (Secure Socket Tunneling Protocol). Essa configuração usa HTTPS.|
|**Interceptação SNMP**|Permite que os computadores gerenciados recebam tráfego do serviço interceptação do protocolo SNMP.|
|**Estrutura UPnP**|Configura o serviço de Estrutura UPnP nos computadores para permitir que eles descubram e usem dispositivos UPnP.|
|**Serviço de Registro de Nomes de Computador da Colaboração do Windows**|Permite que os computadores localizem e se comuniquem com outros computadores usando SSDP e PNRP.|
|**Windows Media Player**|Permite que os usuários recebam mídia de streaming por protocolo UDP (User Datagram Protocol).|
|**Serviço de Compartilhamento de Rede do Windows Media Player**|Permite que os usuários compartilhem mídia por uma rede. Essa configuração usa os protocolos de rede SSDP, qWave e UPnP.|
|**Serviço de Compartilhamento de Rede do Windows Media Player (Internet)**<br>(Windows 7 ou posterior)|Permite que os usuários compartilhem mídia pela Internet.|
|**Espaço de Reunião do Windows**|Permite que os usuários colaborem por uma rede para compartilhar documentos, programas e suas áreas de trabalho. Essa configuração usa Replicação de Sistema de Arquivos Distribuído (DFSR) e P2P.|
|**Base da Colaboração Ponto a Ponto do Windows**|Configura vários programas e tecnologias ponto a ponto para permitir que eles se conectem. Essa configuração usa SSDP e PNRP.|
|**Gerenciamento Remoto do Windows (Compatibilidade)**|Permite o gerenciamento remoto de computadores gerenciados com o WS-Management, um protocolo baseado em serviços Web para o gerenciamento remoto de sistemas operacionais e dispositivos.|
|**Gerenciamento Remoto do Windows**<br>(Windows 8 ou posterior)|Permite o gerenciamento remoto de computadores gerenciados com o WS-Management, um protocolo baseado em serviços Web para o gerenciamento remoto de sistemas operacionais e dispositivos.|
|**Computador Virtual Windows**<br>(Windows 7 ou posterior)|Permite que máquinas virtuais se comuniquem com outros computadores.|
|**Dispositivos Portáteis sem Fio**|Permite a transferência de mídia de um dispositivo de câmera ou mídia habilitado para rede para computadores gerenciados com o MTP (Protocolo de Transferência de Mídia). Essa configuração usa protocolos de rede SSDP e UPnP.|

### <a name="see-also"></a>Consulte também
[Políticas para proteger computadores Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)
