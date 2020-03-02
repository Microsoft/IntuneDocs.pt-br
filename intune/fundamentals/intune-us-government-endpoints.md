---
title: Pontos de extremidade de rede para implantações do governo dos EUA – Microsoft Intune
titleSuffix: ''
description: Examine os pontos de extremidade do governo dos EUA para o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/30/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 5f6682cb-5fcd-4018-b7f7-71768ad3152e
ms.reviewer: kerimh
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7edf84ada3c84b7ad31748909ef81a877237fd5
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514465"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Pontos de extremidade do governo dos EUA para o Microsoft Intune

Esta página lista os pontos de extremidade de governo dos EUA necessários para as configurações de proxy em suas implantações do Intune.

Para gerenciar dispositivos por trás de firewalls e servidores proxy, habilite a comunicação para o Intune.

- O servidor proxy deve dar suporte a **HTTP (80)** e a **HTTPS (443)** , porque os clientes do Intune usam os dois protocolos
- Para algumas tarefas (como fazer o download de atualizações de software), o Intune exige acesso ao servidor proxy não autenticado manage.microsoft.com

É possível alterar as configurações do servidor proxy em computadores cliente individuais. Você também pode usar as definições da Política de Grupo para alterar as configurações de todos os computadores cliente que estejam em um servidor proxy especificado.

Os dispositivos gerenciados exigem configurações que permitem que **Todos os Usuários** acessem serviços através de firewalls.

Para mais informações sobre o registro automático do Windows 10 e o registro de dispositivos para clientes do governo dos EUA, confira [Configurar o registro para dispositivos Windows](../enrollment/windows-enroll.md#windows-10-auto-enrollment-and-device-registration).

As tabelas a seguir listam as portas e serviços que o cliente do Intune acessa:

|**Ponto de extremidade**|**Endereço IP**|
|---------------------|-----------|
|*.manage.microsoft.us | 52.243.26.209 <br> 52.247.173.11 <br> 52.227.183.12 <br>52.227.180.205 <br> 52.227.178.107 <br> 13.72.185.168 <br> 52.227.173.179 <br> 52.227.175.242 <br> 13.72.39.209 <br> 52.243.26.209 <br> 52.247.173.11 |
| enterpriseregistration.microsoftonline.us | 13.72.188.239 <br> 13.72.55.179 |

## <a name="us-government-customer-designated-endpoints"></a>Pontos de extremidade designados do cliente do governo dos EUA:
- Portal do Azure: https:\//portal.azure.us/ 
- Office 365: https:\//portal.office365.us/ 
- Portal da Empresa do Intune: https:\//portal.manage.microsoft.us/ 

## <a name="partner-service-endpoints-that-intune-depends-on"></a>Pontos de extremidade de serviço do parceiro dos quais o Intune depende:
- Serviço AAD Sync: https:\//syncservice.gov.us.microsoftonline.com/DirectoryService.svc
- Evo STS: https:\//login.microsoftonline.us
- Proxy do Directory: https:\//directoryproxy.microsoftazure.us/DirectoryProxy.svc
- AAD Graph: https:\//directory.microsoftazure.us and https:\//graph.microsoftazure.us
- MS Graph: https:\//graph.microsoft.us
- ADRS: https:\//enterpriseregistration.microsoftonline.us

## <a name="windows-push-notification-services"></a>Serviço de Notificação por Push do Windows
Em dispositivos gerenciados pelo Intune e com o MDM (gerenciamento de dispositivo móvel), o WNS (Serviços de Notificação por Push do Windows) é necessário para ações do dispositivo e outras atividades imediatas. Para obter mais informações, confira [Firewall corporativo e configurações de proxy para dar suporte ao tráfego do WNS](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <a name="apple-device-network-information"></a>Informações de rede de dispositivo Apple

|**Usada para**|**Nome do host (endereço IP/sub-rede)**|**Protocolo**|**Porta**|
|------------|-----------|------------|-----------|
|Recuperar e exibir o conteúdo dos servidores da Apple|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br>\*.phobos.itunes-apple.com.akadns.net|HTTP|80|
|Comunicação com os servidores do APNs|#-courier.push.apple.com<br>'#' é um número aleatório de 0 a 50.|TCP|5223 e 443|
|Várias funções, incluindo o acesso à Internet, à iTunes Store, à loja de aplicativos do macOS, ao iCloud, a mensagens etc.|phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net|HTTP/HTTPS|80 ou 443|

Para obter mais informações, consulte:

- [Portas TCP e UDP usadas pelos produtos de software da Apple](https://support.apple.com/HT202944)
- [Sobre as conexões de host do servidor do macOS, do iOS/iPadOS e do iTunes e os processos em segundo plano do iTunes](https://support.apple.com/HT201999)
- [Se os clientes do macOS e do iOS/iPadOS não estiverem obtendo notificações por push da Apple](https://support.apple.com/HT203609)

## <a name="next-steps"></a>Próximas etapas
[Pontos de extremidade de rede para o Microsoft Intune](intune-endpoints.md)

