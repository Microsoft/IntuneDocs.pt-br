---
title: "Determinar grupos de destino e períodos da distribuição do Intune | Microsoft Docs"
description: "Este artigo ajuda a determinar os grupos de destino e os períodos da distribuição para uma implementação somente na nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: f807d6e4b20b98ecf622d1ebdd9db33b132a2e6a
ms.openlocfilehash: 36530602813467c184b4f262719a56cedbaa2ba9


---

# <a name="develop-an-intune-rollout-plan"></a>Desenvolver um plano de distribuição do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Esta seção ajudará você a determinar os grupos organizacionais que serão afetados pela distribuição do Intune, bem como o período da distribuição para cada grupo e as abordagens de registro que serão usadas.

## <a name="determine-intune-rollout-targeted-groups-and-timeframes"></a>Determinar grupos de destino e períodos da distribuição do Intune

É importante identificar primeiro os grupos de destino da distribuição do Intune. Já falamos sobre os grupos de destino na seção Identificar cenários de caso de uso do Intune deste guia.

Em segundo lugar, você precisará determinar o período que cada grupo será afetado pela distribuição do Intune. Normalmente, isso exige uma conversa com a equipe de implantação do Intune e com os grupos de destino, para ajudar a determinar o período da distribuição mais apropriado para cada grupo.

Por exemplo, a equipe de implantação do Intune pode abordar fatores como a disposição do grupo a mudanças, o número de usuários e dispositivos, os tipos de plataformas de dispositivo, os requisitos, a localização geográfica e os riscos para os negócios, a fim de determinar o período da distribuição.

Em geral, as organizações optam por iniciar a distribuição do Intune com um piloto inicial, visando um pequeno grupo de usuários no departamento de TI. Em seguida, o piloto pode ser expandido para incluir um conjunto mais amplo de usuários de TI e a participação de outros grupos organizacionais. Após um piloto bem-sucedido, as organizações estarão prontas para iniciar uma distribuição de produção completa, visando o restante dos grupos da organização. Veja abaixo alguns exemplos de diferentes grupos de distribuição e fases:

-   **Piloto:** a primeira fase a ser distribuída deve ser usuários pilotos. Os usuários piloto devem entender que são os primeiros usuários de uma solução nova e devem estar dispostos a fornecer comentários para ajudar a melhorar a configuração, a documentação e as notificações, além de facilitar o trabalho de todos os outros usuários nas próximas fases de distribuição. Esses usuários não devem ser Executivos nem VIPs.

-   **Departamentos:** cada departamento pode ser uma fase de distribuição. Nesse cenário, você visará todo o departamento ao mesmo tempo. Nesse tipo de distribuição, cada fase provavelmente usará o dispositivo móvel da mesma maneira e acessará os mesmos aplicativos. Provavelmente, os usuários também terão os mesmos tipos de políticas.

-   **Geografia:** esse tipo de implantação consiste na implantação em todos os usuários de uma geografia específica, seja o mesmo continente, país, região ou o mesmo edifício da empresa. Esse tipo de implantação em fases permite a capacidade de se concentrar em um local específico de usuários. Isso poderá permitir uma abordagem mais [diferenciada](#user-assisted-enrollment) conforme o número de locais de implantação do Intune é reduzido ao mesmo tempo. Como há a probabilidade de diferentes departamentos ou casos de uso estarem no mesmo local, outros casos de uso podem ser implantados simultaneamente.

-   **Plataforma:** esse tipo de implantação consiste na implantação de plataformas semelhantes ao mesmo tempo. Um exemplo pode ser todos os dispositivos iOS no primeiro mês, seguido pelo Android e, depois, pelo Windows. Esse tipo de implantação em fases ajuda a simplificar o suporte de assistência técnica. O suporte de assistência técnica precisará dar suporte apenas a uma única plataforma por vez.

Este é um exemplo de um plano de distribuição do Intune que inclui grupos de destino e linhas do tempo:

| **Fase de distribuição** | **Julho** | **Agosto** | **Setembro** | **Outubro** |
|:---:|:---:|:---:|:---:|:---:|
| Piloto Limitado | TI (50 usuários) |  |  |  |                                                         
| Piloto Expandido | TI (200 usuários), Executivos de TI (10 usuários) |  |  |  |                                                         
| Fase 1 da distribuição de produção |  | Vendas e Marketing (2.000 usuários) |  |  |
| Fase 2 da distribuição de produção |  |  | Varejo (1.000 usuários) |  |
| Fase 3 da distribuição de produção |  |  |  | RH (50 usuários), Finanças (40 usuários), Executivos (30 usuários) |

## <a name="determine-the-intune-enrollment-approach"></a>Determinar a abordagem de registro do Intune

Agora que você determinou os grupos de destino e os períodos para a distribuição do Intune, a próxima etapa é escolher a abordagem de registro do Intune mais apropriada para cada grupo. Há diferentes abordagens de registro que as organizações podem usar para a implementação do Intune. Algumas abordagens comuns de registro incluem autoatendimento do usuário, registro assistido e feira de tecnologia de TI.

### <a name="user-self-service"></a>Autoatendimento do usuário

Com essa abordagem, o usuário é responsável pelo registro de seu próprio dispositivo, geralmente seguindo as instruções de registro fornecidas por sua organização de TI. Essa abordagem é mais usada nas organizações e é mais escalonável que o registro assistido do usuário.

### <a name="user-assisted-enrollment"></a>Registro assistido do usuário

Conhecido como a abordagem “diferenciada”, em que um membro da equipe de TI ajudará o usuário no processo de registro, pessoalmente ou por meio do Skype. Essa abordagem geralmente é usada com a equipe executiva e com outros grupos que podem precisar de mais assistência durante o processo de registro.

### <a name="it-tech-fair"></a>Feira de tecnologia de TI

Outra opção para o registro de usuário do Intune é realizar uma feira técnica de TI. Nesse evento, o grupo de TI montará uma cabine de assistência de registro do Intune, na qual os usuários poderão receber informações sobre o registro do Intune, fazer perguntas e obter assistência com o processo de registro. O uso dessa opção pode ser útil para o grupo de TI e o usuário, especialmente durante as fases iniciais da distribuição do Intune.

Este é um exemplo de um plano de distribuição do Intune com grupos de destino, linhas do tempo e abordagens de registro:

| **Fase de distribuição** | **Julho** | **Agosto** | **Setembro** | **Outubro** |
|:---:|:---:|:---:|:---:|:---:|
| Piloto Limitado |  |  |  |  |                                                         
| Autoatendimento | TI |  |  |  |
| Piloto Expandido |  |  |  |  |                                                         
| Autoatendimento | TI |  |  |  |
| Diferenciado | Executivos de TI |  |  |  |
| Fase 1 da distribuição de produção |  | Vendas, Marketing |  |  |
| Autoatendimento |  | Vendas e marketing |  |  |
| Fase 2 da distribuição de produção |  |  | Varejo |  |
| Autoatendimento |  |  |  |  |
| Fase 3 da distribuição de produção |  |  | Varejo |  |
| Autoatendimento |  |  |  | RH, Finanças |
| Diferenciado |  |  |  | Executivos |

## <a name="next-section"></a>Próxima seção

A próxima seção fornece diretrizes sobre como [desenvolver um plano de comunicação para a distribuição do Intune](section-5-develop-a-rollout-communication-plan.md).



<!--HONumber=Dec16_HO5-->


