---
title: "Identificar cenários de caso de uso do Intune | Microsoft Docs"
description: "Este artigo ajuda a identificar cenários de caso de uso do Intune, bem como cenários de subcaso de uso para uma implementação somente em nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 031820d505e0e9cb007e47a5397934d0e505aed4
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="identify-intune-use-case-scenarios"></a>Identificar cenários de caso de uso do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Os cenários de caso de uso de gerenciamento de dispositivo móvel descrevem o tipo ou a função do usuário e a propriedade de seu dispositivo (por exemplo, corporativo ou pessoal). Os cenários de caso de uso são úteis pois permitem que você segmente os usuários em grupos gerenciáveis. Identificar os cenários de caso de uso é uma parte importante do processo de planejamento para uma implantação bem-sucedida do Intune.

Vejamos alguns exemplos para ajudar sua organização a identificar os cenários de caso de uso do Intune, bem como os grupos organizacionais, e as plataformas de dispositivos móveis associadas a cada caso de uso.

## <a name="use-case-scenarios"></a>Cenários de caso de uso

Você pode começar consultando as metas e os objetivos de implantação do Intune de sua organização, a fim de ajudar a identificar os principais cenários de caso de uso para sua implantação. Dentro do escopo de seu plano de implantação do Intune, você precisará responder às seguintes perguntas:

-   Você planeja dar suporte a dispositivos de propriedade corporativa?

-   Você planeja dar suporte a dispositivos BYOD (pessoais)?

### <a name="sub-use-case-scenarios"></a>Cenários de subcaso de uso

Depois de identificar os principais cenários de caso de uso, você precisará determinar se cada um deles também inclui subcasos de uso. Por exemplo, uma organização pode ter identificado requisitos para dar suporte a um cenário de caso de uso corporativo que inclui subcasos de uso adicionais:

-   Operador de informações

-   Executivos

-   Quiosque

Estes são alguns exemplos de cenários de caso de uso e de subcaso de uso. É possível utilizar a tabela abaixo para inserir os cenários de caso de uso e de subcaso de uso de sua organização:

| **Casos de uso** | **Subcasos de uso** |
|:---:|:---:|
| Corporativo | Operador de informações |              
| Corporativo | Executivos |           
| Corporativo | Quiosque |
| BYOD | Operador de informações |           
| BYOD | Executivos |

## <a name="identify-organizational-groups-associated-with-use-case-scenarios"></a>Identificar os grupos organizacionais associados aos cenários de caso de uso

Agora você precisa identificar os grupos organizacionais associados a cada cenário de caso de uso e de subcaso de uso. Estes são alguns exemplos de grupos organizacionais associados a cenários de caso de uso e de subcaso de uso que podem ser usados como modelo para inserir informações de sua organização:

| **Casos de uso** | **Subcasos de uso** | **Grupos organizacionais** |
|:---:|:---:|:---:|
| Corporativo | Operador de informações | RH, Finanças |               
| Corporativo | Executivo | RH, Finanças |            
| Corporativo | Quiosque | Varejo |
| BYOD | Operador de informações | Marketing, Vendas |            
| BYOD | Executivo | Marketing, Vendas |

## <a name="identify-mobile-device-platforms-for-use-case-scenarios"></a>Identificar as plataformas de dispositivo móvel para cenários de caso de uso

Aqui você identificará as plataformas de dispositivo móvel associadas a cada cenário de caso de uso. Por exemplo, seu cenário de caso de uso corporativo pode dar suporte às plataformas de dispositivos iOS e Android Samsung KNOX e sua política de BYOD pode incluir o suporte a plataformas de dispositivos móveis adicionais como Android (que não seja o Samsung KNOX) e Windows 10 Mobile. Este é um exemplo de plataformas de dispositivos móveis associadas a cada cenário de caso de uso. Use a tabela abaixo para inserir as plataformas de dispositivos de sua organização associadas aos cenários de caso de uso:

| **Casos de uso** | **Subcasos de uso** | **Grupos** | **Plataformas de dispositivos** |   
|:---:|:---:|:---:|:---:|
| Corporativo | Operador de informações | RH, Finanças | iOS |                                                           
| Corporativo | Executivos | RH, Finanças | iOS |                                                           
| Corporativo | Quiosque | Varejo | Android |
| BYOD | Operador de informações | Marketing, Vendas | iOS |                                                           
| BYOD | Executivos | Marketing, Vendas | iOS |

## <a name="next-steps"></a>Próximas etapas

A próxima seção fornece diretrizes sobre [como identificar os requisitos do Intune para cada cenário de caso de uso](section-3-determine-use-case-requirements.md).

