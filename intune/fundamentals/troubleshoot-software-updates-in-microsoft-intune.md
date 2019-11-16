---
title: Solução de problemas de atualizações de software no Microsoft Intune – Azure | Microsoft Docs
description: Solucione problemas de atualização de software no Microsoft Intune.
keywords: ''
author: Brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: d17b70f4-17b4-4d89-88fd-70fa4f34fbea
ROBOTS: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7da927754971fb66a5d8442d0cdf18e0ebfbcd4a
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059069"
---
# <a name="troubleshoot-software-updates-in-microsoft-intune"></a>Solucionar problemas de atualização de software no Microsoft Intune

Ajude a solucionar problemas de atualização de software no Microsoft Intune. Para ver uma lista de descrições e códigos de erro, acesse [Códigos de erro do agente de atualização de software no Microsoft Intune](../protect/software-update-agent-error-codes.md).

## <a name="windows-7-devices-with-many-superseded-updates-stop-reporting-to-intune"></a>Dispositivos do Windows 7 com muitas atualizações substituídas param de enviar relatórios ao Intune

Os clientes do Microsoft Intune podem experimentar um ou mais dos seguintes sintomas:

- Os dispositivos repentinamente param de enviar relatórios ao Intune.  
- Os dispositivos apresentam uma alta utilização da CPU.
- Os aplicativos são instalados lentamente quando realizado pelo Intune.
- O Microsoft Intune Center mostra o seguinte erro: `An error occurred while updating your computer. Error found: Code 0x800705b4`.
- O Console de Administração do Intune > Grupos > Todos os dispositivos > Status mostra: `One or more agents that are installed on this computer have errors. The information for this computer may not be accurate or up-to-date.`

Esse problema pode ocorrer se as atualizações substituídas (que foram trocadas por outra atualização) não foram recusadas por um longo período. Durante determinados processos, como a instalação de um aplicativo, o Windows verifica todas as atualizações substituídas em sequência, para que as atualizações e suas sucessoras sejam mapeadas corretamente. Se a lista de atualizações substituídas ficar muito grande, essa tarefa de verificação poderá causar alta utilização da CPU devido à carga de processamento e ao tempo necessário. Esse problema afeta principalmente os dispositivos do Windows 7 devido ao grande número de atualizações substituídas que estão disponíveis para o Windows 7. Sistemas operacionais mais recentes talvez não tenham tantas atualizações substituídas disponíveis e podem não ser suscetíveis a esse problema.

**Resolução**

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Atualizações de Software**.
3. Recuse todas as atualizações substituídas que podem ser aplicáveis ao Windows 7 ou aos aplicativos, como o Microsoft Office, que foram instalados nos clientes afetados.
4. Reinicie os clientes afetados.

Se você estiver executando o Windows 7, certifique-se de que a seguinte atualização é instalada:[3050265 Cliente do Windows Update para Windows 7: junho de 2015](https://support.microsoft.com/kb/3050265).

## <a name="next-steps"></a>Próximas etapas

Obtenha [ajuda do suporte da Microsoft](get-support.md) ou use os [fóruns da comunidade](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).