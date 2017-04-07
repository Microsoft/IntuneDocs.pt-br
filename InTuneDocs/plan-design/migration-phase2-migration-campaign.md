---
title: "Iniciar uma campanha de migração do Intune | Microsoft Docs"
description: "A finalidade deste artigo é fornecer orientações sobre como iniciar uma campanha de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab5aa4e12d951d818c5afb4e1ac5e866b05733fb
ms.openlocfilehash: 506b0360fb7b1f28c4c9ad3265e24c0ffa0b065d
ms.lasthandoff: 03/27/2017


---

# <a name="phase-2-migration-campaign"></a>Fase 2: Campanha de migração

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

As organizações devem usar abordagens de migração mais adequadas às suas necessidades e ajustar as táticas de implementação com base em suas necessidades específicas. O restante deste guia fornecerá a você as ferramentas necessárias para atingir o objetivo de registrar os dispositivos de usuários no Intune.

## <a name="keys-to-a-successful-migration"></a>Segredos para uma migração bem-sucedida

Estas são as principais lições aprendidas durante a migração de um provedor de MDM de terceiros para o Intune:

-   A comunicação é essencial para minimizar o tempo de inatividade e a satisfação do usuário final.

-   Tenha instruções de migração específicas e concretas.

-   Todos os dispositivos gerenciados devem ter seu registro cancelado no provedor de MDM existente antes do registro no Intune.

-   Forneça aos usuários finais a orientação do provedor de MDM existente sobre como cancelar o registro de seus dispositivos.

-   Use uma abordagem em fases. Comece com um pequeno grupo de usuários piloto e adicione aos poucos mais grupos de usuários até atingir a implantação completa.

-   Monitore a carga do suporte técnico e o sucesso do registro de cada ciclo. Reserve um tempo na agenda para garantir que os critérios de sucesso possam ser avaliados para cada grupo antes de migrar o próximo. Sua implantação piloto deve validar o seguinte:

    -   Se as taxas de êxito e falha de registro estão dentro das expectativas.

    -   Produtividade do usuário:

        -   Se os recursos corporativos, como VPN, Wi-Fi, email e certificados, estão funcionando.

        -   Se os aplicativos provisionados podem ser acessados.

    -   Segurança de dados:

        -   Relatório de conformidade

        -   Proteções de aplicativo móvel impostas

-   Quando você estiver satisfeito com a primeira fase da migração, repita o Ciclo de migração (descrito abaixo em Ciclo típico de migração) para a próxima fase.

-   Repita os ciclos em fases até que todos os usuários sejam migrados para o Intune.

-   Certifique-se de que a equipe de suporte técnico esteja pronta para dar suporte a usuários finais durante toda a campanha de migração. Execute uma migração voluntária até que você possa estimar a carga de trabalho de chamada de suporte.

-   Não defina prazos para o registro até que a população restante possa ser atendida por seu suporte técnico

> [!IMPORTANT] 
> Não configure o Intune e sua solução existente de MDM de terceiros para aplicar os controles de acesso aos recursos, como o Exchange ou SharePoint Online. Além disso, os dispositivos só devem ser registrados em uma solução por vez.

## <a name="next-steps"></a>Próximas etapas

[Fase 2: Plano de comunicação](https://docs.microsoft.com/intune/plan-design/migration-phase2-communication-plan)

