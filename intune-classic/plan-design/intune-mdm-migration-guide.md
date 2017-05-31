---
title: "Guia de migração de MDM (gerenciamento de dispositivo móvel) do Intune | Microsoft Docs"
description: "A finalidade deste guia é mostrar aos clientes os diversos detalhes envolvidos na migração de um provedor de MDM de terceiros para o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: cce6d997c1aad73819b8cfcf31a1505f0ce75923
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="intune-migration-guide"></a>Guia de migração do Intune

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

![Arte do guia de migração de MDM do Intune](../media/MDM-migration-guide-art.PNG)

Uma migração bem-sucedida para o Intune começa com um plano sólido que considera o ambiente atual de MDM, as metas do negócio e os requisitos técnicos. Além disso, você precisa contar com as principais partes interessadas que oferecerão suporte e colaborarão com seu plano de migração.

A finalidade deste guia é mostrar a você os diversos detalhes envolvidos na migração de um provedor de MDM de terceiros para o Intune.

## <a name="whats-included-in-this-guide"></a>O que está incluído neste guia?

Este guia inclui duas fases, e as duas incluem tarefas, estratégias e orientações táticas que ajudarão você a percorrer o processo de migração de MDM de ponta a ponta para o Intune.

-   [Fase 1: preparar o Intune para gerenciamento de dispositivo móvel] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

    -   [Avaliar seus requisitos de migração de MDM](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements)

    -   [Configuração básica](/intune-classic/plan-design/migration-phase1-basic-setup)

    -   [Configurar políticas de gerenciamento de dispositivos e aplicativos](/intune-classic/plan-design/migration-phase1-configure-device-and-app-management-policies)

    -   [Configurar políticas de proteção do aplicativo] (/intune-classic/plan-design/migration-phase1-configure-app-protection-policies)

    -   [Considerações especiais de migração](/intune-classic/plan-design/migration-phase1-special-migration-considerations)

-   [Fase 2: Campanha de migração](/intune-classic/plan-design/migration-phase2-migration-campaign)

    -   [Plano de comunicação](/intune-classic/plan-design/migration-phase2-communication-plan)

    -   [Gerar adoção de usuário final com acesso condicional](/intune-classic/plan-design/migration-phase2-drive-end-user-adoption-with-conditional-access)
    
    -   [Ciclo de migração típico](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)
        -   [Monitoramento da migração](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#monitoring-migration)
        -   [Pós-migração](/intune-classic/plan-design/migration-phase2-typical-migration-cycle#post-migration)

## <a name="assumptions"></a>Suposições

-   Você já avaliou o Intune em um ambiente de PoC (prova de conceito) e decidiu usá-lo como a solução de MDM em sua organização.

-   Você já está familiarizado com o Intune e seus recursos. 

> [!NOTE]
> Confira o [guia de avaliação do Intune](/intune-classic/understand-explore/sign-up-for-30-day-trial-microsoft-intune) se quiser se familiarizar mais com o Intune antes de migrar.

## <a name="before-you-begin"></a>Antes de começar

É importante reconhecer que a nova implantação do Intune pode ser diferente de sua implantação de MDM antiga. Ao contrário dos serviços de MDM tradicionais, o Intune centraliza no controle de acesso baseado em identidades e, portanto, não exige um dispositivo de proxy de rede para controlar o acesso a dados corporativos de dispositivos móveis fora do perímetro da rede da organização. A Microsoft oferece soluções para proteger os serviços de dados na própria nuvem por meio de um conjunto integrado de serviços de nuvem, coletivamente chamado de oferta Cliente Empresarial + Segurança.

-   Examine as [formas comuns para usar o Intune](/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management#assess-mdm-requirements).

## <a name="next-steps"></a>Próximas etapas

[Fase 1: preparar o Intune para gerenciamento de dispositivo móvel] (/intune-classic/plan-design/migration-phase1-prepare-intune-for-mobile-device-management)

