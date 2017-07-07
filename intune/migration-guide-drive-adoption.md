---
title: "Gerar adoção de usuário final com acesso condicional"
description: "A finalidade deste artigo é fornecer informações sobre como usar o acesso condicional para gerar registro no Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0b2fbcc1d63f229e1b63873841bc300bdde92fa3
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a>Gerar adoção de usuário final com acesso condicional

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

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

-   Saiba mais sobre o [acesso condicional](/intune/conditional-access).

## <a name="task-list-for-conditional-access"></a>Lista de tarefas para acesso condicional

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Tarefa 1: Decidir como você pretende implementar o acesso condicional

[Maneiras comuns de usar o acesso condicional](/intune/conditional-access-intune-common-ways-use).

### <a name="task-2-set-up-intune-conditional-access"></a>Tarefa 2: Configurar o acesso condicional do Intune

Selecione uma das seguintes opções:

-   [Configurar o acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Instalar o Exchange Connector local com o Intune](/intune/exchange-connector-install)

-   [Configurar políticas de acesso condicional baseado no aplicativo para o Exchange Online](/intune/app-based-conditional-access-intune-exchange-online-create)

-   [Configurar políticas de acesso condicional baseado no aplicativo para o SharePoint Online](/intune/app-based-conditional-access-intune-sharepoint-online-create)

-   [Bloquear aplicativos que não usam autenticação moderna (ADAL)](/intune/app-modern-authentication-block)

## <a name="next-steps"></a>Próximas etapas

[Ciclo de migração típico](migration-guide-cycle.md)
