---
title: Determinar os requisitos de cenários de caso de uso
titleSuffix: Microsoft Intune
description: Este artigo ajuda você a determinar os requisitos de cenários de casos de uso e subcasos de uso do Intune para uma implementação somente em nuvem do Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: a03a92f715496b3c647a12bb99457d151ead54a3
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514924"
---
# <a name="determine-use-case-scenario-requirements"></a>Determinar os requisitos de cenários de caso de uso

Nesta seção, você determina os requisitos para cada grupo organizacional em cada cenário de caso de uso. Esse processo ajuda você a se preparar para as outras áreas de planejamento de implantação do Intune, como arquitetura e design, integração e distribuição. Ele também pode ajudar a identificar possíveis falhas e os desafios relacionados ao seu projeto de implantação do Intune.

Talvez você tenha diferentes conjuntos de requisitos para cada um dos cenários de casos de uso e subcasos de uso e seus grupos organizacionais e as plataformas de dispositivos móveis associadas. Por exemplo, seus requisitos de cenários de casos de uso corporativos podem exigir que os dispositivos se registrem no Intune com um conjunto mais restritivo de configurações de dispositivo, como um PIN de 6 caracteres ou com o backup na nuvem desabilitado. O cenário de caso de uso BYOD “Traga seu próprio dispositivo” pode ser menos restritivo e permite um PIN de 4 caracteres e o backup na nuvem.

Você também pode ter grupos organizacionais para o cenário de caso de uso corporativo que têm diferentes conjuntos de requisitos (por exemplo, configurações de PIN, perfil de Wi-Fi ou VPN, aplicativos implantados). Seus requisitos também podem ser determinados pelas funcionalidades da plataforma de dispositivo móvel (por exemplo, leitor de impressão digital, perfil de email).

Estes são alguns exemplos de requisitos de casos de uso de uma organização, mostrando diferentes conjuntos de requisitos para cada cenário de caso de uso e subcaso de uso, grupo organizacional e plataforma de dispositivo móvel. Também é possível usar a seguinte tabela para inserir os requisitos de caso de uso de sua organização:

| **Casos de uso** | **Subcasos de uso** | **Grupos** | **Plataformas de dispositivos** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Corporativo | Operador de informações | RH, Finanças | iOS/iPadOS | Email seguro, configurações de dispositivo, perfis, aplicativos |                                                          
| Corporativo | Executivos | RH, Finanças | iOS/iPadOS | Email seguro, configurações de dispositivo, perfis, aplicativos |                                                         
| Corporativo | Quiosque | Varejo | Android | Configurações de dispositivo, perfis, aplicativos |
| BYOD | Operador de informações | Marketing, Vendas | iOS/iPadOS | Email seguro, configurações de dispositivo, perfis, aplicativos |                                                         
| BYOD | Executivos | Marketing, Vendas | iOS/iPadOS | Email seguro, configurações de dispositivo, perfis, aplicativos |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para inserir os requisitos de casos de uso e subcasos de uso de sua organização.


## <a name="examples-of-requirements"></a>Exemplos de requisitos

Estes são mais alguns exemplos que podem ser usados na coluna “Requisitos”:

- **Email seguro**
  - Acesso condicional para o Exchange Online/Local
  - Políticas de proteção do aplicativo do Outlook

- **Configurações do dispositivo**
  - Configuração de PIN com quatro, seis caracteres
  - Restringir o backup na nuvem

- **Perfis**
  - Wi-Fi
  - VPN
  - Email (Windows 10 Mobile)

- **Apps**
  - Office 365 com políticas de proteção do aplicativo
  - LOB (linha de negócios) com políticas de proteção do aplicativo

## <a name="next-steps"></a>Próximas etapas

A próxima seção fornece diretrizes sobre [como desenvolver um plano de distribuição do Intune](planning-guide-rollout-plan.md).
