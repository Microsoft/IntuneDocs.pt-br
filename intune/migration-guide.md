---
title: "Guia de migração de gerenciamento de dispositivo móvel do Intune"
description: "Este guia orienta você passo a passo sobre os diversos detalhes envolvidos na migração de um provedor MDM de terceiros para o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 888624530fe77f22ea9391b688fa9f9b92f0ac75
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="intune-migration-guide"></a>Guia de migração do Intune

![Arte do guia de migração de MDM do Intune](./media/MDM-migration-guide-art.PNG)

Uma migração bem-sucedida para o Intune começa com um plano sólido que considera o ambiente atual de MDM (gerenciamento de dispositivo móvel), as metas de negócios e os requisitos técnicos. Além disso, você precisa contar com as principais partes interessadas que oferecerão suporte e colaborarão com seu plano de migração.

Este guia orienta você passo a passo sobre os diversos detalhes envolvidos na migração de um provedor MDM de terceiros para o Intune.

## <a name="whats-included-in-this-guide"></a>O que está incluído neste guia?

Este guia divide a migração em duas fases e as duas incluem tarefas, estratégias e orientações táticas que ajudarão você a percorrer o processo de migração de MDM de ponta a ponta para o Intune.

-   [Fase 1: Preparar o Intune para o gerenciamento de dispositivo móvel](migration-guide-prepare.md)

    -   [Avaliar seus requisitos de migração de MDM](migration-guide-prepare.md#assess-mdm-requirements)

    -   [Configuração básica](migration-guide-setup.md)

    -   [Configurar políticas de gerenciamento de dispositivos e aplicativos](migration-guide-configure-policies.md)

    -   [Configurar políticas de proteção do aplicativo](migration-guide-app-protection-policies.md)

    -   [Considerações especiais de migração](migration-guide-considerations.md)

-   [Fase 2: campanha de migração](migration-guide-campaign.md)

    -   [Plano de comunicação](migration-guide-communication-plan.md)

    -   [Gerar adoção de usuário final com acesso condicional](migration-guide-drive-adoption.md)

    -   [Ciclo de migração típico](migration-guide-cycle.md)
        -   [Monitoramento da migração](migration-guide-cycle.md#monitoring-migration)
        -   [Pós-migração](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Suposições

-   Você já avaliou o Intune em um ambiente de PoC (prova de conceito) e decidiu usá-lo como a solução de MDM em sua organização.

-   Você já está familiarizado com o Intune e seus recursos.

## <a name="before-you-begin"></a>Antes de começar

É importante reconhecer que a nova implantação do Intune pode ser diferente de sua implantação de MDM antiga. Ao contrário dos serviços de MDM tradicionais, o Intune centraliza no controle de acesso baseado em identidades e, portanto, não exige um dispositivo de proxy de rede para controlar o acesso a dados corporativos de dispositivos móveis fora do perímetro da rede da organização. A Microsoft oferece soluções para proteger os serviços de dados na própria nuvem por meio de um pacote integrado de serviços de nuvem, coletivamente chamado de oferta Cliente Corporativo + Segurança.

-   Examine as [formas comuns para usar o Intune](common-scenarios.md).

## <a name="next-steps"></a>Próximas etapas

[Fase 1: Preparar o Intune para o gerenciamento de dispositivo móvel](migration-guide-prepare.md)
