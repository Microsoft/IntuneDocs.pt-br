---
title: Solucionar problemas do Endpoint Protection no Intune — Azure | Microsoft Docs
description: Solucione problemas ao usar o Endpoint Protection do Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e31df2d2-bb1b-491b-9a71-04e0b18829c1
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: f828394c48b5b7d55d9180da875d9cb3062f23c6
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181676"
---
# <a name="troubleshoot-endpoint-protection-in-intune"></a>Solucionar problemas do Endpoint Protection no Intune

Use as informações para ajudar a solucionar problemas ao usar o Endpoint Protection. Você também pode [revisar logs de eventos e códigos de erro para solucionar problemas com o Windows Defender AV](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus).

Caso essas informações não ajudem, [obtenha também o suporte para o Microsoft Intune](get-support.md).

### <a name="error-messages"></a>Mensagens de erro
Esta seção descreve possíveis causas e soluções para os erros e avisos a seguir.

|Item de status|Possíveis causas|Possíveis soluções|
|---------------|--------------------|-----------------------|
|**Mecanismo do Endpoint Protection indisponível**|O mecanismo Endpoint Protection do Intune foi corrompido ou excluído.|Se o mecanismo Endpoint Protection do Intune estiver corrompido, você poderá tentar atualizar ou reinstalar o software.<br /><br />Para forçar uma atualização imediata, escolha **Atualizar** no software cliente do Endpoint Protection (na barra de tarefas em computadores gerenciados).<br /><br />Se o mecanismo não puder ser atualizado, você deverá reinstalar o mecanismo do Endpoint Protection.<br /><br />Na lista de programas instalados no Painel de Controle do computador gerenciado, localize **Agente do Endpoint Protection do Microsoft Intune** e desinstale o aplicativo.<br /><br />Durante a próxima sincronização de atualizações, o Microsoft Online Management Update Manager irá detectar o programa ausente e reinstalá-lo no horário agendado.|
|**Endpoint Protection desabilitado**|O Endpoint Protection do Intune foi desabilitado por um administrador usando um perfil de configuração ou por um usuário em um computador gerenciado.|Habilite a proteção de ponto de extremidade. Confira [Adicionar configurações de proteção de ponto de extremidade](endpoint-protection-configure.md) no Intune ou [Ativar o Windows Defender para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows).|
|**Proteção em tempo real desabilitada**|A proteção em tempo real foi desabilitada por um administrador usando uma política ou por um usuário em um computador gerenciado.|Habilite a proteção de ponto de extremidade. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus) no Intune ou [ative a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows). |
|**Verificação de download desabilitada**|A verificação de download foi desabilitada por um administrador usando um perfil, ou por um usuário em um computador gerenciado.|Ative a verificação. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus) no Intune ou [ative a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows). |
|**Monitoramento de atividades de arquivos e programas desabilitado**|O monitoramento de atividades de arquivos e programas foi desabilitado por um administrador usando um perfil ou por um usuário em um computador gerenciado.|Habilite a atividade de arquivo e programa. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus) no Intune ou [ative a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows). |
|**Monitoramento de comportamento desabilitado**|O monitoramento de comportamento foi desativado por um administrador usando um perfil ou por um usuário em um computador gerenciado.|Habilite o monitoramento de comportamento. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus) no Intune ou [ative a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows). |
|**Verificação de script desabilitada**|A varredura de scripts foi desabilitada por um administrador usando um perfil ou por um usuário em um computador gerenciado.|Habilite a verificação de script. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus) no Intune ou [ative a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows). |
|**Sistema de Inspeção de Rede desabilitado**|O Sistema de Inspeção de Rede foi desabilitado por um administrador usando um perfil ou por um usuário em um computador gerenciado.|Habilite o Sistema de Inspeção de Rede (NIS). Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus) no Intune ou [ative a proteção em tempo real para acessar os recursos da empresa](/intune-user-help/turn-on-defender-windows). |
|**Definições de malware desatualizadas**|O computador pode ter ficado desconectado da Internet por um longo período, e suas definições de malware talvez ainda não tenham sido atualizadas. Esse status aparece quando as definições de malware no computador estão desatualizadas há 14 dias ou mais.|Se as definições de malware estiverem desatualizadas, é possível atualizá-las usando o [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Verificação completa vencida**|Uma verificação completa não é realizada há 14 dias. Isso pode ser causado por uma reinicialização do computador durante uma verificação completa.|Se uma verificação completa estiver atrasada, é possível executar uma verificação completa única ou agendar verificações completas recorrentes. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus). |
|**Verificação rápida vencida**|Uma verificação rápida não é realizada há 14 dias. Isso pode ser causado por uma reinicialização durante uma verificação rápida.|Se uma verificação rápida estiver atrasada, é possível executar uma verificação rápida única ou agendar verificações rápidas recorrentes. Confira [Windows Defender Antivírus](device-restrictions-windows-10.md#windows-defender-antivirus).|
|**Outro aplicativo do Endpoint Protection em execução**|Outro aplicativo de proteção de ponto de extremidade está sendo executado, e o computador está em estado íntegro.|Por padrão, se outro aplicativo de proteção de ponto de extremidade estiver instalado e o Intune detectar esse aplicativo, o dispositivo poderá se tornar instável.|

### <a name="next-steps"></a>Próximas etapas
Caso essas informações não ajudem, [obtenha também o suporte para o Microsoft Intune](get-support.md).
