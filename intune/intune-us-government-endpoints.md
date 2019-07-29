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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9828b04ae30d8f35313564b93dfc9b997795bf76
ms.sourcegitcommit: 8d12ab22e23552f9addaef4c28b732fb211945a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2019
ms.locfileid: "68306714"
---
# <a name="us-government-endpoints-for-microsoft-intune"></a>Pontos de extremidade do governo dos EUA para o Microsoft Intune

Esta página lista os pontos de extremidade de governo dos EUA necessários para as configurações de proxy em suas implantações do Intune.

Para gerenciar dispositivos por trás de firewalls e servidores proxy, habilite a comunicação para o Intune.

- O servidor proxy deve dar suporte a **HTTP (80)** e a **HTTPS (443)** , porque os clientes do Intune usam os dois protocolos
- Para algumas tarefas (como fazer o download de atualizações de software), o Intune exige acesso ao servidor proxy não autenticado manage.microsoft.com

É possível alterar as configurações do servidor proxy em computadores cliente individuais. Você também pode usar as definições da Política de Grupo para alterar as configurações de todos os computadores cliente que estejam em um servidor proxy especificado.

Os dispositivos gerenciados exigem configurações que permitem que **Todos os Usuários** acessem serviços através de firewalls.

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
