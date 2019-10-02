---
title: Requisitos de rede e detalhes de largura de banda do Microsoft Intune
titleSuffix: ''
description: Examine os requisitos de configuração de rede e os detalhes de largura de banda do Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5b4983031d0e5d0723e306a1b9cbefadac2f91fe
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727422"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Largura de banda e requisitos de configuração de rede do Intune

[!INCLUDE [both-portals](../../intune-classic/includes/note-for-both-portals.md)]

Você pode usar essas informações para entender os requisitos de largura de banda para suas implantações do Intune.

## <a name="average-network-traffic"></a>Tráfego médio da rede
A tabela relaciona o tamanho aproximado e a frequência em que o conteúdo comum viaja pela rede para cada cliente.

> [!NOTE]
> Para assegurar que os dispositivos recebam as atualizações e o conteúdo do Intune, é preciso conectá-los periodicamente à Internet. O tempo necessário para receber as atualizações ou o conteúdo pode variar, mas eles devem permanecer conectados de maneira contínua à Internet por pelo menos uma hora por dia.

|Tipo de conteúdo|Tamanho aproximado|Frequência e detalhes|
|----------------|--------------------|-------------------------|
|Instalação do cliente do Intune<br /><br />**Os requisitos a seguir são adicionais à instalação do cliente do Intune**|126 MB|**Uma vez**<br /><br />O tamanho do download do cliente varia dependendo do sistema operacional do computador cliente.|
|Pacote de registro do cliente|16 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente do Endpoint Protection|66 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente do Operations Manager|11 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente de política|3 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Assistência Remota via agente do Microsoft Easy Assist|6 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Operações diárias do cliente|6 MB|**Diariamente**<br /><br />O cliente do Intune se comunica regularmente com o serviço do Intune para verificar se há atualizações e políticas e para informar o status do cliente ao serviço.|
|Atualizações de definições de malware da Endpoint Protection|Varia<br /><br />Normalmente de 40 KB a 2 MB|**Diariamente**<br /><br />Até 3 vezes por dia.|
|Atualização do mecanismo do Endpoint Protection|6 MB|**Mensalmente**|
|Atualizações de software|Varia<br /><br />O tamanho depende das atualizações implantadas.|**Mensalmente**<br /><br />Normalmente, atualizações de software versão na segunda terça-feira de cada mês.<br /><br />Um computador recém-registrado ou implantado pode usar mais largura de banda da rede enquanto baixar o conjunto completo de atualizações liberadas anteriormente.|
|Service packs|Varia<br /><br />O tamanho varia para cada implantação do service pack.|**Varia**<br /><br />Depende de quando você implanta os pacotes de serviço.|
|Distribuição de software|Varia<br /><br />O tamanho depende do software implantado.|**Varia**<br /><br />Depende de quando você implanta o software.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Maneiras de reduzir o uso de largura de banda de rede
Você pode usar os métodos a seguir para reduzir o uso de largura de banda da rede para os clientes do Intune.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Usar um servidor proxy para armazenar solicitações de conteúdo em cache
Um servidor proxy pode armazenar em cache o conteúdo para reduzir downloads duplicados e para reduzir a largura de banda de rede do conteúdo da Internet.

Um servidor proxy de cache que recebe solicitações de conteúdo de clientes pode recuperar esse conteúdo e armazenar em cache respostas da Web e downloads. O servidor usa dados armazenados em cache para responder às solicitações subsequentes de clientes.

A seguir, são mostradas as configurações típicas para usar em um servidor proxy que armazena o conteúdo em cache para os clientes do Intune.


|          Configuração           |           Valor recomendado           |                                                                                                  Detalhes                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Tamanho do cache         |             de 5 GB a 30 GB             | Esse valor varia de acordo com o número de computadores cliente na rede e as configurações usadas. Para impedir que arquivos sejam excluídos muito cedo, ajuste o tamanho do cache para o seu ambiente. |
| Tamanho do arquivo de cache individual |                950 MB                 |                                                                     Essa configuração pode não estar disponível em todos os servidores proxy de cache.                                                                     |
|   Tipos de objeto para armazenar em cache    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Os pacotes do Intune são arquivos CAB recuperados pelo download do Serviço de Transferência Inteligente em Segundo Plano (BITS) via HTTP.                                               |
> [!NOTE]
> Se você usa um servidor proxy para armazenar solicitações de conteúdo em cache, a comunicação é criptografada apenas entre o cliente e o proxy e do proxy para o Intune. A conexão do cliente para o Intune não é criptografada de ponta a ponta.

Para obter informações sobre o uso de um servidor proxy para armazenar conteúdo em cache, consulte a documentação da sua solução de servidor proxy.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Usar o Serviço de Transferência Inteligente em Segundo Plano (BITS) nos computadores
Durante as horas de configuração, você pode usar o BITS em um computador Windows para reduzir a largura de banda da rede. Você pode configurar a política do BITS na página **Largura de banda da rede** da política do agente do Intune.

> [!NOTE]
> No caso do gerenciamento de MDM no Windows, somente a interface de gerenciamento do sistema operacional do tipo de aplicativo MobileMSI usa o BITS para fazer download. O AppX/MsiX usa sua própria pilha de download que não é do BITS e os aplicativos do Win32, por meio do agente do Intune, usam a Otimização de Entrega em vez do BITS.

Para saber mais sobre o BITS e computadores Windows, consulte [Serviço de Transferência Inteligente em Segundo Plano](https://technet.microsoft.com/library/bb968799.aspx) na biblioteca do TechNet.

### <a name="delivery-optimization"></a>Otimização de Entrega
A Otimização de Entrega permite que você use o Intune para reduzir o consumo de largura de banda quando seus dispositivos Windows 10 baixam aplicativos e atualizações. Usando um cache distribuído auto-organizado, os downloads podem ser obtidos de servidores tradicionais e de fontes alternativas (como pares de rede).

Para ver a lista completa de versões e tipos de conteúdo do Windows 10 com suporte pela Otimização de Entrega, confira o artigo sobre a [Otimização de Entrega para atualizações do Windows 10](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#requirements).

Você pode [configurar a Otimização de Entrega](../configuration/delivery-optimization-settings.md) como parte dos perfis de configuração do dispositivo.


### <a name="use-branchcache-on-computers"></a>Usar BranchCache nos computadores
Os clientes do Intune podem usar o BranchCache para reduzir o tráfego de rede de longa distância (WAN). Os seguintes sistemas operacionais dão suporte ao BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Para usar o BranchCache, o computador cliente deve estar com o BranchCache habilitado e configurado no **modo de cache distribuído**.

Por padrão, o BranchCache e o modo de cache distribuído são habilitados em computadores quando o cliente do Intune está instalado. No entanto, se a Política de Grupo desabilitou o BranchCache, o Intune não substitui essa política e o BranchCache permanece desabilitado.

Se você usa o BranchCache, trabalhe com outros administradores em sua organização para gerenciar a Política de Grupo e a política de Firewall do Intune. Verifique se eles não implantam políticas que desabilitam exceções do BranchCache ou do Firewall. Para saber mais sobre o BranchCache, consulte [BranchCache Overview (Visão geral do BranchCache)](https://technet.microsoft.com/library/hh831696.aspx).

> [!NOTE]
> Você pode usar o Microsoft Intune para gerenciar computadores Windows [como dispositivos móveis com o MDM (gerenciamento de dispositivo móvel)](../enrollment/windows-enroll.md) ou como computadores com o cliente de software do Intune. A Microsoft recomenda que os clientes [usem a solução de gerenciamento MDM](../enrollment/windows-enroll.md) sempre que possível. Quando gerenciado dessa forma, o BranchCache não tem suporte. Para saber mais, confira [Comparar o gerenciamento de computadores Windows como computadores ou dispositivos móveis](../pc-management-comparison.md).


## <a name="next-steps"></a>Próximas etapas

[Examinar os pontos de extremidade do Intune](../intune-endpoints.md)

