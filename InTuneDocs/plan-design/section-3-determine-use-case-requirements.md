---
title: "Determinar os requisitos de cenários de caso de uso do Intune | Microsoft Docs"
description: "Este artigo ajuda a determinar os requisitos de cenários de caso de uso e de subcaso de uso do Intune para uma implementação somente em nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fd8cb5f7-19f0-4d80-8825-2bafa49624af
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 91b25fe35c6a1f8a554d543ca005cc3b482f22d7


---

# <a name="determine-intune-use-case-scenario-requirements"></a>Determinar os requisitos de cenários de caso de uso do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Nesta seção, você determinará os requisitos para cada grupo organizacional em cada cenário de caso de uso. Passar por esse processo ajudará você a se preparar melhor para as outras áreas de planejamento de implantação do Intune, como arquitetura e design, integração e distribuição. Ele também pode ajudar a identificar possíveis lacunas, bem como os desafios relacionados ao seu projeto de implantação do Intune.

Você poderá ter diferentes conjuntos de requisitos para cada um dos cenários de caso de uso/subcaso de uso e seus grupos organizacionais e as plataformas de dispositivos móveis associadas. Por exemplo, seus requisitos de cenários de caso de uso corporativo podem exigir que os dispositivos sejam registrados no Intune com um conjunto mais restritivo de configurações do dispositivo (por exemplo, PIN de seis caracteres, desabilitação de backup na nuvem), em comparação com o cenário de caso de uso BYOD (“traga seu próprio dispositivo”), em que exige configurações menos restritivas (por exemplo, PIN de quatro caracteres, permissão de backup na nuvem).

Você também pode ter grupos organizacionais para o cenário de caso de uso corporativo que têm diferentes conjuntos de requisitos (por exemplo, configurações de PIN, perfil de Wi-Fi ou VPN, aplicativos implantados). Além disso, seus requisitos podem ser determinados pelas funcionalidades da plataforma de dispositivo móvel (por exemplo, leitor de impressão digital, perfil de email).

Estes são alguns exemplos de requisitos de caso de uso de uma organização, mostrando diferentes conjuntos de requisitos para cada cenário de caso de uso/subcaso de uso, grupo organizacional e plataforma de dispositivo móvel. Também é possível usar a tabela abaixo para inserir os requisitos de caso de uso de sua organização:

| **Casos de uso** | **Subcasos de uso** | **Grupos** | **Plataformas de sistema operacional do dispositivo** | **Requirements** |
|:---:|:---:|:---:|:---:|:---:|
| Corporativo | Operador de Informações | RH, Finanças | iOS | Email seguro, configurações do dispositivo, Perfis, Aplicativos |                                                          
| Corporativo | Executivos | RH, Finanças | iOS | Email seguro, configurações do dispositivo, Perfis, Aplicativos |                                                         
| Corporativo | Quiosque | Varejo | Android | Configurações do dispositivo, Perfis, Aplicativos |
| BYOD | Operador de Informações | Marketing, Vendas | iOS | Email seguro, configurações do dispositivo, Perfis, Aplicativos |                                                         
| BYOD | Executivos | Marketing, Vendas | iOS | Email seguro, configurações do dispositivo, Perfis, Aplicativos |

## <a name="examples-of-requirements"></a>Exemplos de requisitos

Estes são mais alguns exemplos que podem ser usados na coluna “Requisitos” indicada na tabela acima:

- **Email seguro**
    - Acesso condicional ao Exchange Online/no Local
    - Políticas de proteção do aplicativo do Outlook
<br></br>
- **Configurações do dispositivo**
    - Configuração de PIN com quatro, seis caracteres
    - Restringir o backup na nuvem
<br></br>
- **Perfis**
    - Wi-Fi
    - VPN
    - Email (Windows 10 Mobile)
<br></br>
- **Apps**
    - Office 365 com políticas de proteção do aplicativo
    - LOB (linha de negócios) com políticas de proteção do aplicativo

## <a name="next-section"></a>Próxima seção

A próxima seção fornece diretrizes sobre [como desenvolver um plano de distribuição do Intune](section-4-develop-a-rollout-plan.md).



<!--HONumber=Dec16_HO5-->


