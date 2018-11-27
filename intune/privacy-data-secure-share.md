---
title: Compartilhamento e segurança de dados no Intune
description: Saiba como os pessoais dados são protegidos e compartilhados no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 68921fd6-5f50-456c-a3af-83d7bc4b134b
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 8ce7b6020c9212a0379915e00e361853e2eb3259
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184107"
---
# <a name="data-security-and-sharing-in-intune"></a>Compartilhamento e segurança de dados no Intune


## <a name="data-security"></a>Segurança de dados

O Microsoft Intune é um componente fundamental da oferta de serviço de nuvem Microsoft Enterprise Mobility e Security Suite. Para dar suporte à [estratégia de governança de dados](https://www.microsoft.com/en-us/TrustCenter/Security/default.aspx), todos os serviços em nuvem da Microsoft são desenvolvidos com as metodologias [Privacidade da Microsoft](https://www.microsoft.com/en-us/trustcenter/privacy) e [Segurança da Microsoft](https://www.microsoft.com/en-us/trustcenter/security/).  

O Microsoft Intune segue as mesmas medidas técnicas e organizacionais usadas pelas equipes de serviço do Microsoft Azure para fornecer proteção contra processos de violação de dados.

Para obter mais informações, confira o [Portal de Confiança do Serviço](https://www.microsoft.com/en-us/TrustCenter/stp).

O Intune usa técnicas de minimização de dados, como

- agregação
- coleta de dados opcional para alguns recursos
- dados transformados em dados menos precisos ou confidenciais

O Intune também usa técnicas como segurança JIT e RBAC para dar suporte a incidentes, a fim de garantir a Proteção de Dados por Padrão. 

### <a name="data-breach-reporting"></a>Relatórios de violação de dados

Quando um CRSI (Incidente de Segurança Relatável para o Cliente) é identificado, os clientes são notificados. Esse processo inclui o trabalho com a equipe do Microsoft O365 para comunicar a notificação de violação para os clientes do Microsoft O365 que usam o Intune.

## <a name="data-sharing"></a>Compartilhamento de dados

Quando os administradores de locatários ativam determinadas funcionalidades (como o Programa de registro de dispositivos Apple), o Microsoft Intune obtém o consentimento do administrador para compartilhar os dados com terceiros apropriados. Nesses casos, o Intune pode compartilhar dados pessoais com:

- Terceiros que atuam como agentes da Microsoft.
- Terceiros que não atuam como agentes da Microsoft, mas somente quando os administradores de locatários concedem explicitamente a permissão do Intune para fazer isso.

Todos os outros terceiros que atuam como agentes da Microsoft são incluídos na [lista de Subcontratados do Online Services](https://aka.ms/Online_Serv_Subcontractor_List).

O compartilhamento de dados com essas entidades é feito para ajudar o cliente e o suporte técnico, a manutenção do serviço e outras operações.

O contrato de um locatário com o terceiro rege os dados pessoais do Intune mantidos no serviço do terceiro. Ele também concede ao Intune a permissão para transmitir os dados para o serviço do terceiro.  

Para obter informações sobre os dados compartilhados com determinados terceiros, confira os seguintes artigos:
- [Dados enviados pelo Intune à Apple](data-intune-sends-to-apple.md)
- [Dados enviados pelo Intune ao Google](data-intune-sends-to-google.md)
- [Dados enviados pela Apple ao Intune](data-apple-sends-to-intune.md)
- [Dados enviados pela Google ao Intune](data-google-sends-to-intune.md)
- [Informações compartilhadas do Jamf Pro com o Intune](conditional-access-integrate-jamf.md#information-shared-from-jamf-pro-to-intune)

### <a name="system-center-configuration-manager-data-sharing"></a>Compartilhamento de dados do System Center Configuration Manager

O Microsoft Intune não compartilha dados com o System Center Configuration Manager. O System Center Configuration Manager é um produto local implantado, gerenciado e operado diretamente pelo cliente. Os dados de diagnóstico e de uso coletados pelo Configuration Manager destinam-se apenas a melhorar a experiência de instalação, a qualidade e a segurança de versões futuras.

Para obter mais informações, confira [Dados de diagnóstico e de uso do SCCM](https://docs.microsoft.com/sccm/core/plan-design/diagnostics/diagnostics-and-usage-data.md). 


## <a name="next-steps"></a>Próximas etapas

Descubra como [exibir e corrigir](privacy-data-view-correct.md) dados pessoais no Intune.
