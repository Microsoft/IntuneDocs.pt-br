---
title: Iniciar uma campanha de migração do Intune
titleSuffix: Microsoft Intune
description: Este artigo fornece diretrizes de como iniciar uma campanha de migração do Microsoft Intune.
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
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 490f2c538a9fd5c10f9812679c9f72fd78fefed5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72505359"
---
# <a name="phase-2-migration-campaign"></a>Fase 2: Campanha de migração

Escolha uma abordagem de migração mais adequada às suas necessidades e ajuste as táticas de implementação com base em seus requisitos específicos. O restante deste guia fornecerá a você as ferramentas necessárias para atingir a meta de registrar os dispositivos de usuários no Intune.

## <a name="keys-to-a-successful-migration"></a>Segredos para uma migração bem-sucedida

Estas são as chaves para migrar com êxito de um provedor de MDM de terceiros para o Intune:

- Comunicação clara e útil pode minimizar a insatisfação e o tempo de inatividade do usuário final.

- Tenha instruções de migração específicas e concretas.

- Todos os dispositivos gerenciados devem ter seu registro cancelado no provedor de MDM existente antes que possam ser registrados no Intune.

- Forneça aos usuários finais a orientação do seu provedor de MDM existente sobre como cancelar o registro de seus dispositivos.

- Use uma abordagem em fases. Comece com um pequeno grupo de usuários piloto e adicione aos poucos mais grupos de usuários até atingir a implantação completa.

- Monitore o carregamento do suporte técnico e o sucesso do registro de cada ciclo. Reserve um tempo na agenda para garantir que os critérios de sucesso possam ser avaliados para cada grupo antes de migrar o próximo. Sua implantação piloto deve validar o seguinte:

  - Se as taxas de êxito e falha de registro estão dentro das expectativas.

  - Produtividade do usuário:

    - Se os recursos corporativos, como VPN, Wi-Fi, email e certificados, estão funcionando.

    - Os aplicativos provisionados podem ser acessados.

  - Segurança de dados:

    - O relatório de conformidade está ocorrendo.

    - As proteções de aplicativo móvel são impostas.

Quando você estiver satisfeito com a primeira fase da migração, repita o [ciclo de migração](migration-guide-cycle.md) para a próxima fase.

- Repita os ciclos em fases até que todos os usuários sejam migrados para o Intune.

- Verifique se a equipe de suporte técnico está pronta para dar suporte a usuários finais durante toda a campanha de migração. Execute uma migração voluntária até que você possa estimar a carga de trabalho de chamada de suporte.

- Não defina prazos para o registro até que a população restante possa ser atendida por seu suporte técnico

> [!IMPORTANT]
> Não configure o Intune e sua solução existente de MDM de terceiros para aplicar os controles de acesso aos recursos, como o Exchange ou SharePoint Online. Além disso, os dispositivos só devem ser registrados em uma solução por vez.

## <a name="next-steps"></a>Próximas etapas

Crie seu [plano de comunicação](migration-guide-communication-plan.md).
