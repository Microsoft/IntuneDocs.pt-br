---
title: "Determinar os grupos direcionados para distribuição e cronogramas"
description: "Este artigo ajuda você a decidir quais grupos serão distribuídos para o Intune e os cronogramas para essas implantações."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a63f78f-a7e7-4f44-9288-16b28d5d58ca
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6edb71b7d97ac3c20b4207d2cac42669ac35c4c0
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="develop-a-rollout-plan"></a>Desenvolver um plano de distribuição

Seu plano de distribuição identifica os grupos organizacionais que você deseja direcionar para a distribuição do Intune, o cronograma de distribuição para cada grupo e as abordagens de registro que você usará.

## <a name="targeted-groups-and-timeframes"></a>Grupos direcionados e cronogramas

Primeiro, examine os grupos que são direcionados com a distribuição do Intune e que você identificou nos [cenários de casos de uso](planning-guide-scenarios.md).

Em segundo lugar, determine o cronograma para cada grupo direcionado. Normalmente, essa tarefa exige uma conversa entre a equipe de implantação do Intune e os grupos direcionados, para determinar o cronograma de distribuição mais apropriado para cada grupo. Os pontos a serem abordados em uma discussão desse tipo incluem:
* A disposição do grupo para mudanças
* O número de usuários e dispositivos
* Tipos de plataformas de dispositivo
* Requisitos
* Localização geográfica
* Risco para os negócios

## <a name="rollout-phases"></a>Fases de distribuição
Em geral, as organizações optam por iniciar a distribuição do Intune com um piloto inicial, visando um pequeno grupo de usuários no departamento de TI. O piloto pode ser expandido para incluir um conjunto mais amplo de usuários de TI e pode incluir a participação de outros grupos organizacionais.

### <a name="pilot"></a>Piloto
A primeira fase a ser distribuída deve ser para usuários pilotos. Os usuários pilotos devem entender que eles são os primeiros usuários de uma nova solução. Eles devem estar dispostos a fornecer comentários para ajudar a melhorar a configuração, a documentação, as notificações e facilitar o caminho de todos os outros usuários nas fases de distribuição posteriores. Esses usuários não devem ser executivos nem VIPs.

O piloto é uma boa oportunidade de testar os [desafios](planning-guide-deployment-goals.md) e refinar os [requisitos](planning-guide-requirements.md) coletados anteriormente.

Inclua o plano de [comunicação](planning-guide-communication-plan.md), o plano de [suporte](planning-guide-support-plan.md) e o [teste e validação](planning-guide-test-validation.md) para solucionar problemas quando o impacto para os usuários ainda é pequeno.

### <a name="production-rollout"></a>Distribuição de produção
Após um piloto bem-sucedido, você está pronto para iniciar uma distribuição de produção completa, direcionando o restante dos grupos de sua organização. Alguns exemplos de grupos de distribuição diferentes e fases são:

-   **Departamentos** <br/>Cada departamento pode ser uma fase de distribuição. Você pode direcionar todo o departamento de uma só vez. Nesse tipo de distribuição, os usuários de cada departamento tendem a usar o dispositivo móvel da mesma maneira e acessar os mesmos aplicativos. Os usuários provavelmente terão os mesmos tipos de políticas.

-   **Geografia** <br/>Nessa abordagem, você implanta em todos os usuários em uma geografia específica, seja o mesmo continente, país, região ou o edifício da mesma empresa. Esse tipo de implantação em fases permite focalizar a localização específica de usuários. Isso poderá permitir que você forneça mais de uma abordagem [diferenciada](#user-assisted-enrollment) devido ao número de localizações de implantação do Intune ser simultaneamente reduzido. Como há a probabilidade de diferentes departamentos ou casos de uso estarem no mesmo local, outros casos de uso podem ser implantados simultaneamente.

-   **Plataforma** <br/>Esse tipo de implantação consiste na implantação de plataformas semelhantes ao mesmo tempo. Um exemplo pode ser todos os dispositivos iOS no primeiro mês, seguido pelo Android e, depois, pelo Windows. Esse tipo de implantação em fases ajuda a simplificar o suporte da assistência técnica, porque a assistência técnica precisaria apenas dar suporte a uma única plataforma por vez.

Este é um exemplo de um plano de distribuição do Intune que inclui grupos de destino e linhas do tempo:

| **Fase de distribuição** | **Julho** | **Agosto** | **Setembro** | **Outubro** |
|:---:|:---:|:---:|:---:|:---:|
| Piloto Limitado | TI (50 usuários) |  |  |  |                                                         
| Piloto Expandido | TI (200 usuários), Executivos de TI (10 usuários) |  |  |  |                                                         
| Fase 1 da distribuição de produção |  | Vendas e Marketing (2.000 usuários) |  |  |
| Fase 2 da distribuição de produção |  |  | Varejo (1.000 usuários) |  |
| Fase 3 da distribuição de produção |  |  |  | RH (50 usuários), Finanças (40 usuários), Executivos (30 usuários) |

[Baixe um modelo da tabela acima](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) para inserir as fases de distribuição de sua organização.
## <a name="match-rollout-groups-to-enrollment-approaches"></a>Fazer a correspondência entre grupos de distribuição e abordagens de registro

Agora que você determinou os grupos direcionados e os cronogramas para a distribuição do Intune, a próxima etapa é escolher a abordagem de registro do Intune mais apropriada para cada grupo. Há diferentes métodos de registro que podem ser usados, incluindo:
* Autoatendimento do usuário
* Registro assistido do usuário
* Feira de tecnologia de TI

### <a name="user-self-service"></a>Autoatendimento do usuário

Nesse caso, o usuário é responsável pelo registro de seu próprio dispositivo, geralmente, seguindo as instruções de registro fornecidas por sua organização de TI. Essa abordagem é mais usada nas organizações e é mais escalonável que o registro assistido do usuário.

### <a name="user-assisted-enrollment"></a>Registro assistido do usuário

Isso é conhecido como uma abordagem “diferenciada”. Um membro da equipe de TI ajuda o usuário pelo processo de registro, pessoalmente ou com o Skype. Essa abordagem geralmente é usada com a equipe executiva e com outros grupos que podem precisar de mais assistência durante o processo de registro.

### <a name="it-tech-fair"></a>Feira de tecnologia de TI

Outra opção para o registro de usuário do Intune é realizar uma feira técnica de TI. Nesse evento, o grupo de TI monta uma cabine de assistência de registro do Intune, na qual os usuários poderão receber informações sobre o registro do Intune, fazer perguntas e obter assistência com o processo de registro. Essa opção pode ser útil para o grupo de TI e os usuários, especialmente durante as fases iniciais da distribuição do Intune.

Este é um exemplo atualizado do plano de distribuição do Intune acima para incluir as abordagens de registro:

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

## <a name="next-steps"></a>Próximas etapas

A próxima seção fornece diretrizes sobre como [desenvolver um plano de comunicação para a distribuição do Intune](planning-guide-communication-plan.md).
