---
title: "Como funciona um ciclo de migração típico do Intune | Microsoft Docs"
description: "A finalidade deste artigo é explicar como funciona um ciclo de migração do Intune e dar exemplos de como o cliente lida com os ciclos de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 7130d09d7340aba94f3f9ac72743a281e0aa45ca
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-typical-migration-cycle"></a>Fase 2: Ciclo de migração típico

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Normalmente, as organizações começam sua migração no Intune com um pequeno projeto piloto, visando um subconjunto de seus usuários no departamento de TI. Além disso, talvez sua organização precise discutir fatores como a disposição do grupo em mudar, o número de usuários, a complexidade, os requisitos, o local e os riscos comerciais, a fim de ajudar a determinar o cronograma da migração.

Veja um exemplo de como os grupos-alvo poderão ser agendados:

  | **Grupos-alvo da migração** | **Período 1** | **Período 2** | **Período 3** | **Período 4** | **...**
|:---:|:---:|:---:|:---:|:---:|:---:|
| Organização de TI piloto limitada (50 usuários) | Anunciar plano | Instruir para o registro | Definir prazo | Impor acesso condicional |  |                                                        
| Organização de TI piloto expandida (200 usuários) |  | Anunciar plano | Instruir para o registro | Definir prazo | Impor acesso condicional | 
| Usuários com conhecimentos técnicos da fase 1 de migração (2000) |  |  | Anunciar plano | Instruir para o registro | Definir prazo | 
| Fase 2 da migração, Leste dos EUA |  |  |  | Anunciar plano | Instruir para o registro | 
| Todas as regiões |  |  |  |  | Anunciar plano | 

## <a name="customer-migration-case-study"></a>Estudo de caso de migração do cliente

### <a name="adatum-corporation"></a>Adatum Corporation

- Confira como a [Adatum Corporation passou pelo processo de migração de um provedor de MDM de terceiros para o Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).

## <a name="monitoring-migration"></a>Monitorando a migração

O Microsoft Intune fornece várias maneiras de monitorar a migração:

1.  Exibições de grupo de usuários do Intune

2.  Conjunto de relatórios internos, e

3.  Alertas no console.

Você deve controlar quantos usuários registraram dispositivos após cada fase para que você possa:

-   Avaliar a eficiência de seu plano de comunicação.

-   Estimar o impacto da aplicação do acesso condicional.

Saiba [como monitorar uma migração do Intune](/intune-classic/deploy-use/understand-microsoft-intune-operations-by-using-reports).

## <a name="post-migration"></a>Pós-migração

Você precisará desativar o provedor de MDM anterior e/ou cancelar a assinatura do serviço após a migração para o Intune. Além disso, será necessário remover quaisquer requisitos de infraestrutura desnecessários seguindo as instruções do provedor de MDM.

