---
title: "Guia de migração de MDM (gerenciamento de dispositivo móvel) do Intune | Microsoft Docs"
description: "A finalidade deste guia é mostrar aos clientes os diversos detalhes envolvidos na migração de um provedor de MDM de terceiros para o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 8da2695c4c6dc8b45559323b83a4bb77167303b7
ms.openlocfilehash: 444cb61ea57b92924a681c564a1a913f4204ea89
ms.lasthandoff: 03/28/2017


---

# <a name="intune-migration-guide"></a>Guia de migração do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Arte do guia de migração de MDM do Intune](../media/MDM-migration-guide-art.PNG)

Uma migração bem-sucedida para o Intune começa com um plano sólido que considera o ambiente atual de MDM, as metas do negócio e os requisitos técnicos. Além disso, você precisa contar com as principais partes interessadas que oferecerão suporte e colaborarão com seu plano de migração.

A finalidade deste guia é mostrar a você os diversos detalhes envolvidos na migração de um provedor de MDM de terceiros para o Intune.

## <a name="whats-included-in-this-guide"></a>O que está incluído neste guia?

Este guia inclui duas fases, e as duas incluem tarefas, estratégias e orientações táticas que ajudarão você a percorrer o processo de migração de MDM de ponta a ponta para o Intune.

-   [Fase 1: Preparar o Intune para o MDM (gerenciamento de dispositivo móvel)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Avaliar seus requisitos de migração de MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Configuração básica](https://docs.microsoft.com/intune/plan-design/migration-phase1-basic-setup)

    -   [Configurar políticas de gerenciamento de dispositivos e aplicativos](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Configurar políticas de proteção de aplicativo (opcional)](https://docs.microsoft.com/intune/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Considerações especiais de migração](https://docs.microsoft.com/intune/plan-design/migration-phase1-special-migration-considerations)

-   [Fase 2: Campanha de migração](https://docs.microsoft.com/intune/plan-design/migration-phase2-migration-campaign)

    -   [Plano de comunicação](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

    -   [Gerar adoção de usuário final com acesso condicional](https://docs.microsoft.com/intune/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Ciclo de migração típico](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle)
        -   [Monitoramento da migração](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Pós-migração](https://docs.microsoft.com/intune/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Suposições

-   Você já avaliou o Intune em um ambiente de PoC (prova de conceito) e decidiu usá-lo como a solução de MDM em sua organização.

-   Você já está familiarizado com o Intune e seus recursos. 

> [!NOTE]
> Confira o [guia de avaliação do Intune](https://docs.microsoft.com/intune/understand-explore/sign-up-for-30-day-trial-microsoft-intune) se quiser se familiarizar mais com o Intune antes de migrar.

## <a name="before-you-begin"></a>Antes de começar

É importante reconhecer que a nova implantação do Intune pode ser diferente de sua implantação de MDM antiga. Ao contrário dos serviços de MDM tradicionais, o Intune centraliza no controle de acesso baseado em identidades e, portanto, não exige um dispositivo de proxy de rede para controlar o acesso a dados corporativos de dispositivos móveis fora do perímetro da rede da organização. A Microsoft oferece soluções para proteger os serviços de dados na própria nuvem por meio de um conjunto integrado de serviços de nuvem, coletivamente chamado de oferta Cliente Empresarial + Segurança.

-   Examine as [formas comuns de usar o Intune](https://docs.microsoft.com/intune/understand-explore/common-ways-to-use-intune)e comece a compilar as respostas para as perguntas na [Fase 1: Avaliar os requisitos de MDM](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Próximas etapas

[Fase 1: Preparar o Intune para o MDM (gerenciamento de dispositivo móvel)](https://docs.microsoft.com/intune/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

