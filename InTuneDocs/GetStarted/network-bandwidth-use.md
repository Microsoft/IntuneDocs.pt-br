---
title: Uso de largura de banda de rede do Intune | Microsoft Intune
description: uso de largura de banda de rede do intune
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2a192c71b1b82f59b34ea614d09d895174f8112b
ms.openlocfilehash: 2a600b7948c55a408314aedc3895c25fcc09251d


---

# Uso de largura de banda de rede do Intune

Antes de configurar o [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], examine este tópico e outros requisitos listados em [O que saber antes de começar a usar Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Use as informações nas seções a seguir para planejar o tráfego de rede dos clientes do [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)].

## Tráfego médio da rede
A tabela a seguir relaciona o tamanho aproximado e a frequência em que o conteúdo comum viaja pela rede para cada cliente.

> [!NOTE]
> Para garantir que computadores e dispositivos móveis recebam o conteúdo e as atualizações necessárias do serviço do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], eles devem ser conectados periodicamente à Internet. O tempo necessário para receber atualizações ou conteúdo varia, mas como diretriz, eles devem permanecer conectados continuamente à Internet por pelo menos 1 hora por dia.

|Tipo de conteúdo|Tamanho aproximado|Frequência e detalhes|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] Instalação do cliente<br /><br />**Os requisitos a seguir são adicionais à instalação do cliente do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]**|126 MB|**Uma vez**<br /><br />O tamanho do download do cliente varia dependendo do sistema operacional do computador cliente.|
|Pacote de registro do cliente|16 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente do Endpoint Protection|66 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente do Operations Manager|11 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente de política|3 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Assistência Remota via agente do Microsoft Easy Assist|6 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Operações diárias do cliente|6 MB|**Diariamente**<br /><br />O cliente do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se comunica regularmente com o serviço do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] para verificar se há atualizações e políticas e para informar o status do cliente ao serviço.|
|Atualizações de definições de malware da Endpoint Protection|Varia<br /><br />Normalmente de 40 KB a 2 MB|**Diariamente**<br /><br />Até três vezes por dia.|
|Atualização do mecanismo do Endpoint Protection|6 MB|**Mensalmente**|
|Atualizações de software|Varia<br /><br />O tamanho depende das atualizações implantadas.|**Mensalmente**<br /><br />Normalmente, atualizações de software versão na segunda terça-feira de cada mês.<br /><br />Um computador recém-registrado ou implantado pode usar mais largura de banda da rede enquanto baixar o conjunto completo de atualizações liberadas anteriormente.|
|Service packs|Varia<br /><br />O tamanho varia para cada implantação do service pack.|**Varia**<br /><br />Depende de quando você implanta os pacotes de serviço.|
|Distribuição de software|Varia<br /><br />O tamanho depende do software implantado.|**Varia**<br /><br />Depende de quando você implanta o software.|

## Maneiras de reduzir o uso de largura de banda de rede
Você pode usar os métodos a seguir para reduzir o uso de largura de banda da rede para os clientes do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

### Usar um servidor proxy para armazenar solicitações de conteúdo em cache
Você pode usar um servidor proxy que armazene o conteúdo em cache para reduzir downloads duplicados e reduzir o uso da largura de banda da rede pelos clientes que solicitam conteúdo da Internet.

Um servidor proxy de armazenamento em cache recebe solicitações de conteúdo dos computadores cliente na rede, recupera esse conteúdo da Internet e eles podem então armazenar tanto as respostas HTTP quanto os downloads binários em cache. O servidor usa as informações armazenadas em cache para responder às solicitações subsequentes dos computadores cliente do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

A seguir são mostradas as configurações típicas para usar em um servidor proxy que armazena o conteúdo em cache para os clientes do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

|Configuração|Valor recomendado|Detalhes|
|-----------|---------------------|-----------|
|Tamanho do cache|de 5 GB a 30 GB|Esse valor varia de acordo com o número de computadores cliente na rede e as configurações usadas. Para impedir que arquivos sejam excluídos muito cedo, ajuste o tamanho do cache para o seu ambiente.|
|Tamanho do arquivo de cache individual|950 MB|Essa configuração pode não estar disponível em todos os servidores proxy de cache.|
|Tipos de objeto para armazenar em cache|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] são arquivos CAB recuperados pelo download do Serviço de Transferência Inteligente em Segundo Plano (BITS) via HTTP.|
Para obter informações sobre o uso de um servidor proxy para armazenar conteúdo em cache, consulte a documentação da sua solução de servidor proxy.

### Usar o Serviço de Transferência Inteligente em Segundo Plano nos computadores
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] dá suporte ao Serviço de Transferência Inteligente em Segundo Plano (BITS) em um computador Windows para reduzir a largura de banda da rede usada durante as horas configuradas. Você pode configurar a política para BITS na página **Largura de banda da rede** da política do Agente do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Para saber mais sobre o BITS e computadores Windows, consulte [Serviço de Transferência Inteligente em Segundo Plano](http://technet.microsoft.com/library/bb968799.aspx) na biblioteca do TechNet.

### Usar BranchCache nos computadores
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] podem usar o BranchCache para reduzir o tráfego de rede de longa distância (WAN). Os seguintes sistemas operacionais que têm suporte como clientes também têm suporte para BranchCache:

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

Para usar o BranchCache, o computador cliente deve estar com o BranchCache habilitado e configurado no **modo de cache distribuído**.

Por padrão, o BranchCache e o modo de cache distribuído são habilitados em um computador quando o cliente do [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] é instalado. No entanto, se o cliente já tiver a Política de Grupo que desabilita o BranchCache, o [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] não substituirá a política e o BranchCache permanecerá desabilitado no computador.

Se usar o BranchCache, será preciso comunicar-se com outros administradores em sua organização que gerenciam a Política de grupo e a política de firewall do [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] para garantir que eles não implantem políticas que desativem o BranchCache ou as exceções do Firewall. Para saber mais sobre o BranchCache, consulte [BranchCache Overview (Visão geral do BranchCache)](http://technet.microsoft.com/library/hh831696.aspx).

### Consulte também
[O que saber antes de começar a usar o Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


