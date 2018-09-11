---
title: Requisitos de rede e detalhes de largura de banda do Microsoft Intune
titlesuffix: ''
description: Examine os requisitos de configuração de rede e os detalhes de largura de banda do Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-classic; get-started
ms.openlocfilehash: 6eb6e07b3bb9da2723e57d9203288bebd8c7ab70
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253622"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Largura de banda e requisitos de configuração de rede do Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Este guia ajuda administradores do Intune a compreender os requisitos de rede para o serviço do Intune. Você pode usar essas informações para entender os requisitos de largura de banda e as configurações de porta e endereço IP necessárias para as configurações de proxy.

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
|Atualizações de definições de malware da Endpoint Protection|Varia<br /><br />Normalmente de 40 KB a 2 MB|**Diariamente**<br /><br />Até três vezes por dia.|
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


|          Setting           |           Valor recomendado           |                                                                                                  Detalhes                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Tamanho do cache         |             de 5 GB a 30 GB             | Esse valor varia de acordo com o número de computadores cliente na rede e as configurações usadas. Para impedir que arquivos sejam excluídos muito cedo, ajuste o tamanho do cache para o seu ambiente. |
| Tamanho do arquivo de cache individual |                950 MB                 |                                                                     Essa configuração pode não estar disponível em todos os servidores proxy de cache.                                                                     |
|   Tipos de objeto para armazenar em cache    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Os pacotes do Intune são arquivos CAB recuperados pelo download do Serviço de Transferência Inteligente em Segundo Plano (BITS) via HTTP.                                               |

Para obter informações sobre o uso de um servidor proxy para armazenar conteúdo em cache, consulte a documentação da sua solução de servidor proxy.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Usar o Serviço de Transferência Inteligente em Segundo Plano nos computadores
O Intune dá suporte ao Serviço de Transferência Inteligente em Segundo Plano (BITS) em um computador Windows para reduzir a largura de banda da rede usada durante as horas configuradas. Você pode configurar a política para BITS na página **Largura de banda da rede** da política do Agente do Intune.

Para saber mais sobre o BITS e computadores Windows, consulte [Serviço de Transferência Inteligente em Segundo Plano](http://technet.microsoft.com/library/bb968799.aspx) na biblioteca do TechNet.

### <a name="use-branchcache-on-computers"></a>Usar BranchCache nos computadores
Os clientes do Intune podem usar o BranchCache para reduzir o tráfego de rede de longa distância (WAN). Os seguintes sistemas operacionais dão suporte ao BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Para usar o BranchCache, o computador cliente deve estar com o BranchCache habilitado e configurado no **modo de cache distribuído**.

Por padrão, o BranchCache e o modo de cache distribuído serão habilitados em computadores quando o cliente do Intune estiver instalado. No entanto, se a Política de Grupo tiver desabilitado o BranchCache, o Intune não substituirá essa política e o BranchCache permanecerá desabilitado.

Se você usa o BranchCache, trabalhe com outros administradores em sua organização para gerenciar a Política de Grupo e a política de Firewall do Intune. Verifique se eles não implantam políticas que desabilitam exceções do BranchCache ou do Firewall. Para saber mais sobre o BranchCache, consulte [BranchCache Overview (Visão geral do BranchCache)](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Requisitos de comunicação de rede

Habilite as comunicações de rede entre os dispositivos que você gerencia e os sites necessários para os serviços baseados em nuvem.

O Intune não usa qualquer infraestrutura local, como servidores que executam o software do Intune, mas há opções para usar a infraestrutura local incluindo ferramentas de sincronização do Exchange e do Active Directory.

Para gerenciar computadores com firewalls e servidores proxy, você deve habilitar a comunicação para o Intune.

-   O servidor proxy deve dar suporte a **HTTP (80)** e a **HTTPS (443)**, porque os clientes do Intune usam os dois protocolos
-   O Intune exige acesso de servidor proxy não autenticado ao manage.microsoft.com para algumas tarefas, como baixar software e atualizações

É possível modificar as configurações do servidor proxy em computadores cliente individuais ou usar as definições da Política de Grupo para alterar as configurações de todos os computadores cliente que estejam em um servidor proxy especificado.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Os dispositivos gerenciados exigem configurações que permitem que **Todos os Usuários** acessem serviços através de firewalls.

As tabelas a seguir listam as portas e serviços que o cliente do Intune acessa:

|**Domínios**|**Endereço IP**|
|---------------------|-----------|
|login.microsoftonline.com | Obtenha mais informações sobre [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |40.86.181.86<br>13.82.59.78<br>13.74.184.100<br>40.68.188.2<br>13.75.42.6<br>52.230.25.184 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 104.40.82.191 <br>13.82.96.212 <br>52.169.9.87 <br>52.174.26.23 <br>40.83.123.72 <br>13.76.177.110 <br>52.234.146.75 |
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
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|enterpriseregistration.windows.net|52.175.211.189|

### <a name="apple-device-network-information"></a>Informações de rede de dispositivo Apple

|         nome_do_host         |                                        URL (endereço IP/sub-rede)                                        |  Protocolo  |     Porta     |                          Dispositivo                           |
|--------------------------|-------------------------------------------------------------------------------------------------------|------------|--------------|-----------------------------------------------------------|
|      Console de administração       |                                  gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |                    Apple iOS e macOS                    |
|      Console de administração       |                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |                    Apple iOS e macOS                    |
|      Console de administração       | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net |    HTTP    |      80      |                    Apple iOS e macOS                    |
|        Servidor de PI         |                gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8)                 |    TCP     |  2195, 2196  |         Para mensagens de nuvem de iOS da Apple e macOS.          |
|     Serviços de dispositivo      |                                        gateway.push.apple.com                                         |    TCP     |     2195     |                           Apple                           |
|     Serviços de dispositivo      |                                        feedback.push.apple.com                                        |    TCP     |     2196     |                           Apple                           |
|     Serviços de dispositivo      |   Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net   |    HTTP    |      80      |                           Apple                           |
| Dispositivos (Internet/Wi-Fi) |                                 #-courier.push.apple.com(17.0.0.0/8)                                  |    TCP     | 5223 e 443 | Apple apenas. &#39;#&#39; é um número aleatório de 0 a 200. |
| Dispositivos (Internet/Wi-Fi) |                           phobos.apple.comocsp.apple.comax.itunes.apple.com                           | HTTP/HTTPS |  80 ou 443   |                        Apple apenas                         |

