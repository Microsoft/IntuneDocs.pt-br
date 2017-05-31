---
title: "Gerar adoção do usuário final com acesso condicional | Microsoft Docs"
description: "A finalidade deste artigo é fornecer informações sobre como usar o acesso condicional para gerar registro no Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 55e437fa33af9d27223798cbac9f541b0bc1be2d
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="phase-2-drive-end-user-adoption-with-conditional-access"></a>Fase 2: Gerar adoção do usuário final com acesso condicional

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

A ativação de recursos de acesso condicional com o Intune, como o bloqueio de email para dispositivos não registrados, pode ajudar a gerar registro e conformidade, mas isso não é obrigatório para o sucesso da migração. Seus objetivos para a adoção da migração e os requisitos de segurança devem determinar o sucesso.

## <a name="migration-campaign-with-conditional-access"></a>Campanha de migração com acesso condicional

Está é uma abordagem típica para aprimorar uma campanha de migração com acesso condicional:

1.  Defina as regras de acesso condicional que serão aplicadas a todos os usuários, mas exclua especificamente os usuários que precisam migrar do provedor de MDM antigo. Você pode criar um grupo de usuários do Azure AD com todos os usuários com acesso condicional excluído.

2.  À medida que os usuários migrarem, remova-os do grupo de exclusão de acesso condicional.

3.  Após a conclusão da migração, configure todas as políticas de acesso condicional para bloquear por padrão, a menos que o Intune permita o acesso.

### <a name="advantages"></a>Vantagens

-   Fornece controle de acesso para novas contas de usuário ou para contas de usuário que não eram gerenciadas pela solução anterior.

-   Fornece um período de carência para migração aos usuários da solução anterior.

-   Minimiza a perda de produtividade

### <a name="disadvantages"></a>Desvantagens

-   Os usuários da solução anterior poderiam acessar recursos usando dispositivos não gerenciados até que o acesso condicional fosse habilitado para eles.

> [!TIP]
> Essa é uma abordagem entre várias. Você pode escolher um processo mais simples que adia todo o acesso condicional até que cada fase tenha sido instruída para o registro, ou um processo mais rígido que garante o acesso condicional desde o começo e exige conformidade total para todos os acessos.

-   Saiba mais sobre o [acesso condicional](https://docs.microsoft.com/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Lista de tarefas para acesso condicional

### <a name="task-1-get-ready-for-intune-conditional-access"></a>Tarefa 1: Preparar-se para acesso condicional do Intune

-   Saiba [como configurar o acesso condicional](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).

### <a name="task-2-set-up-intune-conditional-access"></a>Tarefa 2: Configurar o acesso condicional do Intune

Escolha um dos tipos de política de acesso condicional a seguir para saber mais:

-   [Exchange Online e novo Exchange Online dedicado](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)

-   [Exchange local e Exchange Online dedicado herdado](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)

-   [SharePoint Online](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)

-   [Skype for Business Online](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)

-   [Dynamics CRM Online](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)

-   [Exemplo de cenários de acesso por email](/intune-classic/deploy-use/restrict-email-access-example-scenarios)

## <a name="next-steps"></a>Próximas etapas

[Fase 2: Ciclo de migração típico](/intune-classic/plan-design/migration-phase2-typical-migration-cycle)

