---
title: Mensagens comuns do Endpoint Protection no Microsoft Intune – Azure | Microsoft Docs
description: Veja as mensagens comuns e possíveis soluções ao usar e solucionar problemas do Gerenciador de Ponto de Extremidade e do Microsoft Defender no Microsoft Intune.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/13/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 819586a923f5c0f3a81a6d59c4a3895898182f6b
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74059168"
---
# <a name="endpoint-protection-issues-and-possible-solutions-in-microsoft-intune"></a>Problemas e possíveis soluções do Endpoint Protection no Microsoft Intune

Este artigo lista e descreve as possíveis causas e soluções para alguns erros e avisos. Use as informações para ajudá-lo a solucionar problemas ao usar o Endpoint Protection.

## <a name="microsoft-defender-error-codes"></a>Códigos de erro do Microsoft defender

Revise os logs de eventos e códigos de erro para [solucionar problemas com o Microsoft Defender AV](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

## <a name="common-intune-errors-and-possible-resolutions"></a>Erros comuns do Intune e as possíveis resoluções

### <a name="endpoint-protection-engine-unavailable"></a>Mecanismo do Endpoint Protection Indisponível

**Possível causa**: o mecanismo Endpoint Protection do Intune foi corrompido ou excluído.

**Soluções possíveis**:

- se o Endpoint Protection estiver corrompido ou não estiver atualizado, então, atualize ou reinstale o programa.
- Force uma atualização imediata. No programa de cliente do Endpoint Protection (possivelmente na barra de tarefas), escolha **Atualizar**.
- No Painel de Controle > Programas, selecione **Agente do Endpoint Protection do Microsoft Intune**. Desinstale o aplicativo.
- Durante a próxima sincronização de atualizações, o Microsoft Online Management Update Manager irá detectar o programa ausente e reinstalá-lo no horário agendado.

### <a name="features-are-disabled"></a>Os recursos estão desabilitados

Você pode receber uma mensagem de que alguns recursos estão desabilitados. Essas mensagens poderão ocorrer se o Gerenciador de Ponto de Extremidade do Intune ou o Microsoft Defender for desabilitado por um administrador usando um perfil de configuração. Ou for desabilitado por um usuário final no dispositivo. Possíveis mensagens:

`Endpoint Protection disabled`  
`Real-time protection disabled`  
`Download scanning disabled`  
`File and program activity monitoring disabled`  
`Behavior monitoring disabled`  
`Script scanning disabled`  
`Network Inspection System disabled`  

**Soluções possíveis**: habilitar esses recursos. Para obter diretrizes, confira:

- [Adicionar configurações do Endpoint Protection](../protect/endpoint-protection-configure.md)
- [Microsoft defender antivírus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus)
- [Usuários finais: ativar a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows)

### <a name="malware-definitions-out-of-date"></a>Definições de malware desatualizadas

Esse status mostra quando as definições de malware no dispositivo estão desatualizadas há 14 dias ou mais. Por exemplo, a mensagem pode mostrar se o dispositivo está desconectado da Internet ou se as definições de malware estão desatualizadas.

**Soluções possíveis**: se as definições de malware estiverem desatualizadas, atualize-as usando o [Microsoft Defender Antivírus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="full-scan-overdue-or-quick-scan-overdue"></a>Verificação completa ou rápida vencida

Uma verificação completa ou rápida não foi realizada há 14 dias. Esse cenário poderá acontecer se o dispositivo for reiniciado durante uma verificação completa.

**Soluções possíveis**: se uma verificação estiver vencida, você pode executar uma verificação única ou agendar verificações recorrentes. Consulte [Microsoft defender antivírus](../configuration/device-restrictions-windows-10.md#microsoft-defender-antivirus).

### <a name="another-endpoint-protection-application-running"></a>Outro aplicativo de proteção de ponto de extremidade em execução

Outro aplicativo de proteção de ponto de extremidade está sendo executado, e o dispositivo está em estado íntegro.

**Soluções possíveis**: por padrão, se outro aplicativo de proteção de ponto de extremidade estiver instalado e o Intune detectar esse aplicativo, o dispositivo poderá se tornar instável.

## <a name="next-steps"></a>Próximas etapas

Obtenha [ajuda do suporte da Microsoft](get-support.md) ou use os [fóruns da comunidade](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
