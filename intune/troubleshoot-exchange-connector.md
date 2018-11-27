---
title: Solucionar problemas no Exchange Connector
description: Solucione problemas relacionados ao Intune Exchange Connector local.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 6/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a7e3c742-295b-40bb-9afa-17f243062500
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 85b4764ef5797ad592744e3c519f82f3f1cdd1bb
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190040"
---
# <a name="troubleshoot-the-intune-on-premises-exchange-connector"></a>Solução de problemas do Intune Exchange Connector local

Este artigo descreve como solucionar problemas relacionados ao Intune Exchange Connector local.

## <a name="steps-for-checking-the-connector-configuration"></a>Etapas para verificar a configuração do conector 

Verifique a [instalação do Intune Exchange Connector local](exchange-connector-install.md) para ter certeza de que o conector está configurado corretamente. Veja abaixo alguns problemas comuns. Depois de fazer as correções, veja se o problema foi resolvido.

 - Na caixa de diálogo do Microsoft Intune Exchange Connector, verifique se você especificou uma conta de usuário que tenha as permissões apropriadas para executar os [cmdlets necessários do Windows PowerShell Exchange](exchange-connector-install.md#exchange-cmdlet-requirements).
- Habilite as notificações e especifique uma conta de notificação.
 - Ao configurar o Exchange Connector, especifique um CAS (servidor de Acesso para Cliente) que seja o mais próximo possível do servidor que hospeda o Exchange Connector. A latência de comunicação entre o CAS e o Exchange Connector pode atrasar a descoberta de dispositivo, especialmente, ao usar o Exchange Online Dedicado.
 - Um usuário com um dispositivo recém-registrado pode ter um atraso na obtenção de acesso até que o Exchange Connector seja sincronizado com o CAS do Exchange. Uma sincronização completa ocorre uma vez por dia e uma sincronização delta (rápida) ocorre várias vezes ao dia.  Você pode [forçar uma sincronização rápida ou completa manualmente](exchange-connector-install.md#manually-force-a-quick-sync-or-full-sync) para minimizar os atrasos.
 
## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>O dispositivo do Exchange ActiveSync não é descoberto no Exchange
[Monitore a atividade do Exchange Connector](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support) para ver se ele está sendo sincronizado com o Exchange Server. Se uma sincronização completa ou rápida foi concluída com êxito desde que o dispositivo foi associado, verifique outros possíveis problemas, listados abaixo. Se nenhuma sincronização ocorreu, colete os logs de sincronização e anexe-os a uma solicitação de suporte.

 - Verifique se os usuários têm uma licença do Intune; caso contrário, o Exchange Connector não descobrirá seus dispositivos.
 - Se o endereço SMTP primário de um usuário for diferente de seu UPN no Azure AD (Azure Active Directory), o Exchange Connector não descobrirá nenhum dispositivo desse usuário. Corrija o endereço SMTP primário para resolver o problema.
 - Se você tem servidores de caixas de correio do Exchange 2010 e do Exchange 2013 no ambiente, recomendamos apontar o Exchange Connector para um CAS do Exchange 2013. Caso contrário, se o Exchange Connector estiver configurado para se comunicar com um CAS do Exchange 2010, o Exchange Connector não descobrirá os dispositivos dos usuários do Exchange 2013. 
- Para ambientes do Exchange Online Dedicado, é necessário apontar o Exchange Connector para um CAS do Exchange 2013 (não 2010) no ambiente dedicado durante a configuração inicial, pois o conector se comunicará apenas com esse CAS ao executar cmdlets do PowerShell.


## <a name="using-powershell-to-get-more-data-on-exchange-connector-issues"></a>Usando o Powershell para obter mais dados sobre problemas do Exchange Connector
- Para obter uma lista de todos os dispositivos móveis para uma caixa de correio, use Get-ActiveSyncDeviceStatistics -mailbox mbx
- Para obter uma lista de endereços SMTP para uma caixa de correio, use Get-Mailbox -Identity user | select emailaddresses | fl
- Para obter informações detalhadas sobre o estado de acesso de um dispositivo, use Get-CASMailbox <upn> | fl

### <a name="next-steps"></a>Próximas etapas
Caso essas informações não ajudem você, [obtenha também o suporte para o Microsoft Intune](get-support.md).
