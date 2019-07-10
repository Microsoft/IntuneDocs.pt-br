---
title: Guia de migração de gerenciamento de dispositivo móvel do Intune
titleSuffix: Microsoft Intune
description: Este guia orienta você passo a passo sobre os diversos detalhes envolvidos na migração de um provedor MDM de terceiros para o Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: b34143e17245de61026a536cc0b8c5e8a7f80107
ms.sourcegitcommit: bccfbf1e3bdc31382189fc4489d337d1a554e6a1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67549393"
---
# <a name="intune-migration-guide"></a>Guia de migração do Intune

![Arte do guia de migração de MDM do Microsoft Intune](./media/MDM-migration-guide-art.PNG)

Uma migração bem-sucedida para o Microsoft Intune começa com um plano sólido que considera o ambiente atual de MDM (gerenciamento de dispositivo móvel), as metas de negócios e os requisitos técnicos. Além disso, é necessário incluir os principais stakeholders que darão suporte ao seu plano de migração e colaborarão com ele.

Este guia orienta você passo a passo sobre os diversos detalhes envolvidos na migração de um provedor MDM de terceiros para o Intune.

## <a name="whats-included-in-this-guide"></a>O que está incluído neste guia?

Este guia divide a migração em duas fases e as duas incluem tarefas, estratégias e orientações táticas que ajudarão você a percorrer o processo de migração de MDM de ponta a ponta para o Intune.

- [Fase 1: Preparar o Intune para o gerenciamento de dispositivo móvel](migration-guide-prepare.md)

    - [Avaliar seus requisitos de migração de MDM](migration-guide-prepare.md#assess-mdm-requirements)

    - [Configuração básica](migration-guide-setup.md)

    - [Configurar políticas de gerenciamento de dispositivos e aplicativos](migration-guide-configure-policies.md)

    - [Configurar políticas de proteção do aplicativo](migration-guide-app-protection-policies.md)

    - [Considerações especiais de migração](migration-guide-considerations.md)

- [Fase 2: Campanha de migração](migration-guide-campaign.md)

    - [Plano de comunicação](migration-guide-communication-plan.md)

    - [Gerar adoção de usuário final com acesso condicional](migration-guide-drive-adoption.md)

    - [Ciclo de migração típico](migration-guide-cycle.md)
        - [Monitoramento da migração](migration-guide-cycle.md#monitoring-migration)
        - [Pós-migração](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a>Suposições

- Você já avaliou o Intune em um ambiente de PoC (prova de conceito) e decidiu usá-lo como a solução de MDM em sua organização.

- Você já está familiarizado com o Intune e seus recursos.

## <a name="before-you-begin"></a>Antes de começar

É importante reconhecer que a nova implantação do Intune pode ser diferente de sua implantação de MDM antiga. Ao contrário dos serviços de MDM tradicionais, o Intune centraliza no controle de acesso baseado em identidades e, portanto, não exige um dispositivo de proxy de rede para controlar o acesso a dados corporativos de dispositivos móveis fora do perímetro da rede da organização. A Microsoft oferece soluções para proteger os serviços de dados na própria nuvem por meio de um pacote integrado de serviços de nuvem, coletivamente chamado de oferta Cliente Corporativo + Segurança.

- Examine as [formas comuns para usar o Intune](common-scenarios.md).

## <a name="next-steps"></a>Próximas etapas

[Fase 1: Preparar o Intune para o gerenciamento de dispositivo móvel](migration-guide-prepare.md)
