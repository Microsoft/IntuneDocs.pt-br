---
title: "Identificar os cenários de caso de uso"
description: "Este artigo ajuda você a identificar cenários de casos de uso e subcasos de uso do Intune para uma implementação somente na nuvem do Microsoft Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Identificar cenários de casos de uso do gerenciamento de dispositivo móvel

Identificar os cenários de casos de uso é uma parte importante do processo de planejamento para uma implantação bem-sucedida do Intune. Os cenários de casos de uso são úteis, pois permitem segmentar os usuários em grupos gerenciáveis por tipo de usuário ou função e pela propriedade do dispositivo do usuário (por exemplo, da empresa ou pessoal).

Vejamos alguns exemplos para ajudar sua organização a identificar os cenários de casos de uso do Intune, bem como os grupos organizacionais e as plataformas de dispositivos móveis associadas a cada caso de uso.

## <a name="device-ownership"></a>Propriedade do dispositivo
Comece consultando as metas e os objetivos de implantação do Intune de sua organização, a fim de ajudar a identificar os principais cenários de casos de uso de sua implantação. Dentro do escopo do plano de implantação do Intune, responda às seguintes perguntas:

-   Você planeja dar suporte a dispositivos de propriedade corporativa?

-   Você planeja dar suporte a dispositivos BYOD (pessoais)?

Elas não são do tipo opções e/ou. Você pode achar necessário dar suporte a ambas as formas de propriedade do dispositivo para atender às suas metas organizacionais. Os subcasos de uso ajudarão a esclarecer os locais em que devem ser aplicadas diferentes políticas de gerenciamento de dispositivos.

### <a name="user-type-or-device-role"></a>Tipo de usuário ou função do dispositivo

Determine se cada cenário de caso de uso também inclui subcasos de uso. Por exemplo, sua organização pode ter identificado requisitos para dar suporte a um cenário de caso de uso corporativo que inclui subcasos de uso adicionais com base no tipo de usuário ou na função do dispositivo, como:

-   Operador de informações

-   Executivo

-   Quiosque

Estes são alguns exemplos de cenários de casos de uso e subcasos de uso:

| **Casos de uso** | **Subcasos de uso** |
|:---:|:---:|
| Corporativo | Operador de informações |              
| Corporativo | Executivos |           
| Corporativo | Quiosque |
| BYOD | Operador de informações |           
| BYOD | Executivos |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para inserir os cenários de casos de uso e subcasos de uso de sua organização.

## <a name="organizational-groups-for-your-scenarios"></a>Grupos organizacionais para seus cenários

Agora você precisa identificar os grupos organizacionais associados a cada cenário de caso de uso e subcaso de uso. Por exemplo:

| **Casos de uso** | **Subcasos de uso** | **Grupos organizacionais** |
|:---:|:---:|:---:|
| Corporativo | Operador de informações | RH, Finanças |               
| Corporativo | Executivo | RH, Finanças |            
| Corporativo | Quiosque | Varejo |
| BYOD | Operador de informações | Marketing, Vendas |            
| BYOD | Executivo | Marketing, Vendas |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Plataformas de dispositivos móveis para seus cenários

A próxima etapa é identificar as plataformas de dispositivos móveis associadas a cada cenário de caso de uso. Pode haver mais de uma.

Por exemplo, seu cenário de caso de uso corporativo pode dar suporte a plataformas de dispositivos iOS e Android Samsung KNOX. Sua política BYOD pode incluir suporte para plataformas de dispositivos móveis adicionais como Android (não Samsung KNOX) e Windows 10 Mobile. Aproveitando os exemplos anteriores, associamos as plataformas de dispositivos móveis a cada cenário de caso de uso.

| **Casos de uso** | **Subcasos de uso** | **Grupos** | **Plataformas de dispositivos** |   
|:---:|:---:|:---:|:---:|
| Corporativo | Operador de informações | RH, Finanças | iOS |                                                           
| Corporativo | Executivos | RH, Finanças | iOS |                                                           
| Corporativo | Quiosque | Varejo | Android |
| BYOD | Operador de informações | Marketing, Vendas | iOS |                                                           
| BYOD | Executivos | Marketing, Vendas | iOS |

## <a name="next-steps"></a>Próximas etapas

A próxima seção fornece diretrizes sobre [como identificar os requisitos do Intune para cada cenário de caso de uso](planning-guide-requirements.md).
