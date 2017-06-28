---
title: Uso de largura de banda de rede do Intune
description: uso de largura de banda de rede do intune
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/07/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 030aa380a1491eb3be4fd8f480b0ddc9a7860448
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="intune-network-bandwidth-use"></a>Uso de largura de banda de rede do Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Este guia ajuda administradores do Intune a compreender os requisitos de rede para o serviço do Intune. Você pode usar essas informações para entender os requisitos de largura de banda e as configurações de porta e endereço IP necessárias para as configurações de proxy.

## <a name="average-network-traffic"></a>Tráfego médio da rede
A tabela relaciona o tamanho aproximado e a frequência em que o conteúdo comum viaja pela rede para cada cliente.

> [!NOTE]
> Para garantir que computadores e dispositivos móveis recebam o conteúdo e as atualizações necessárias do serviço do Intune, eles devem ser conectados periodicamente à Internet. O tempo necessário para receber atualizações ou conteúdo varia, mas como diretriz, eles devem permanecer conectados continuamente à Internet por pelo menos 1 hora por dia.

|Tipo de conteúdo|Tamanho aproximado|Frequência e detalhes|
|----------------|--------------------|-------------------------|
|Instalação do cliente do Intune<br /><br />**Os requisitos a seguir são adicionais à instalação do cliente do Intune**|126 MB|**Uma vez**<br /><br />O tamanho do download do cliente varia dependendo do sistema operacional do computador cliente.|
|Pacote de registro do cliente|16 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente do Endpoint Protection|66 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente do Operations Manager|11 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Agente de política|3 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Assistência Remota via agente do Microsoft Easy Assist|6 MB|**Uma vez**<br /><br />Downloads adicionais são possíveis quando há atualizações para este tipo de conteúdo.|
|Operações diárias do cliente|6 MB|**Diariamente**<br /><br />O cliente do Intune se comunica regularmente com o serviço do Intune para verificar se há atualizações e políticas e para informar o status do cliente ao serviço.|
|Atualizações de definições de malware da Endpoint Protection|Varia<br /><br />Normalmente de 40 KB a 2 MB|**Diariamente**<br /><br />Até três vezes por dia.|
|Atualização do mecanismo do Endpoint Protection|6 MB|**Mensalmente**|
|Atualizações de software|Varia<br /><br />O tamanho depende das atualizações implantadas.|**Mensalmente**<br /><br />Normalmente, atualizações de software versão na segunda terça-feira de cada mês.<br /><br />Um computador recém-registrado ou implantado pode usar mais largura de banda da rede enquanto baixar o conjunto completo de atualizações liberadas anteriormente.|
|Service packs|Varia<br /><br />O tamanho varia para cada implantação do service pack.|**Varia**<br /><br />Depende de quando você implanta os pacotes de serviço.|
|Distribuição de software|Varia<br /><br />O tamanho depende do software implantado.|**Varia**<br /><br />Depende de quando você implanta o software.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Maneiras de reduzir o uso de largura de banda de rede
Você pode usar os métodos a seguir para reduzir o uso de largura de banda da rede para os clientes do Intune.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Usar um servidor proxy para armazenar solicitações de conteúdo em cache
Você pode usar um servidor proxy que armazene o conteúdo em cache para reduzir downloads duplicados e reduzir o uso da largura de banda da rede pelos clientes que solicitam conteúdo da Internet.

Um servidor proxy de armazenamento em cache recebe solicitações de conteúdo dos computadores cliente na rede, recupera esse conteúdo da Internet e eles podem então armazenar tanto as respostas HTTP quanto os downloads binários em cache. O servidor usa as informações armazenadas em cache para responder às solicitações subsequentes dos computadores cliente do Intune.

A seguir, são mostradas as configurações típicas para usar em um servidor proxy que armazena o conteúdo em cache para os clientes do Intune.

|Configuração|Valor recomendado|Detalhes|
|-----------|---------------------|-----------|
|Tamanho do cache|de 5 GB a 30 GB|Esse valor varia de acordo com o número de computadores cliente na rede e as configurações usadas. Para impedir que arquivos sejam excluídos muito cedo, ajuste o tamanho do cache para o seu ambiente.|
|Tamanho do arquivo de cache individual|950 MB|Essa configuração pode não estar disponível em todos os servidores proxy de cache.|
|Tipos de objeto para armazenar em cache|HTTP<br /><br />HTTPS<br /><br />BITS|Os pacotes do Intune são arquivos CAB recuperados pelo download do Serviço de Transferência Inteligente em Segundo Plano (BITS) via HTTP.|
Para obter informações sobre o uso de um servidor proxy para armazenar conteúdo em cache, consulte a documentação da sua solução de servidor proxy.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Usar o Serviço de Transferência Inteligente em Segundo Plano nos computadores
O Intune dá suporte ao Serviço de Transferência Inteligente em Segundo Plano (BITS) em um computador Windows para reduzir a largura de banda da rede usada durante as horas configuradas. Você pode configurar a política para BITS na página **Largura de banda da rede** da política do Agente do Intune.

Para saber mais sobre o BITS e computadores Windows, consulte [Serviço de Transferência Inteligente em Segundo Plano](http://technet.microsoft.com/library/bb968799.aspx) na biblioteca do TechNet.

### <a name="use-branchcache-on-computers"></a>Usar BranchCache nos computadores
Os clientes do Intune podem usar o BranchCache para reduzir o tráfego de rede de longa distância (WAN). Os seguintes sistemas operacionais que têm suporte como clientes também têm suporte para BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Para usar o BranchCache, o computador cliente deve estar com o BranchCache habilitado e configurado no **modo de cache distribuído**.

Por padrão, o BranchCache e o modo de cache distribuído serão habilitados em um computador quando o cliente do Intune for instalado. No entanto, se o cliente já tiver a Política de Grupo que desabilita o BranchCache, o Intune não substituirá a política e o BranchCache permanecerá desabilitado no computador.

Se usar o BranchCache, será preciso comunicar-se com outros administradores em sua organização que gerenciam a Política de Grupo e a política de firewall do Intune para garantir que não implantem políticas que desabilitem o BranchCache ou as exceções do Firewall. Para saber mais sobre o BranchCache, consulte [BranchCache Overview (Visão geral do BranchCache)](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Requisitos de comunicação de rede

Você deve habilitar as comunicações de rede entre os dispositivos que você gerencia e utiliza para gerenciar sua assinatura do Intune e os sites necessários para serviços baseados em nuvem.

O Intune não usa qualquer infraestrutura local, como servidores que executam o software do Intune, mas há opções para usar a infraestrutura local incluindo ferramentas de sincronização do Exchange e do Active Directory.

Para gerenciar computadores com firewalls e servidores proxy, é preciso configurar firewalls e servidores proxy para permitir comunicações para o Intune. Para gerenciar computadores que estão em um servidor proxy, considere o seguinte:

-   O servidor proxy deve dar suporte a **HTTP (80)** e a **HTTPS (443)**, porque os clientes do Intune usam os dois protocolos
-   O Intune dá suporte a servidores proxy não autenticados

É possível modificar as configurações do servidor proxy em computadores cliente individuais ou usar as definições da Política de Grupo para alterar as configurações de todos os computadores cliente que estejam em um servidor proxy especificado.

Os dispositivos gerenciados exigem configurações que permitem que **Todos os Usuários** acessem serviços através de firewalls.

As tabelas a seguir listam as portas e serviços que o cliente do Intune acessa:

|**Domínios**|**Endereço IP**|
|---------------------|-----------|
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 |
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|

