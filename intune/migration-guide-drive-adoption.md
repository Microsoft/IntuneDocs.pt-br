---
title: Gerar adoção de usuário final com acesso condicional
titleSuffix: Microsoft Intune
description: Saiba como usar o acesso condicional para o registro de unidade no Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: a37d6dac24049a10b5abaed41a44c0c391b095e6
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66050468"
---
# <a name="drive-end-user-adoption-with-conditional-access-in-microsoft-intune"></a>Gerar adoção do usuário final com acesso condicional no Microsoft Intune

A habilitação de recursos de acesso condicional com o Intune, tal como o bloqueio de email para dispositivos não registrados, pode ajudar a gerar registro e conformidade, mas isso não é obrigatório para o sucesso da migração. Seus objetivos para a adoção da migração e os requisitos de segurança devem determinar o sucesso.

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


Essa é uma abordagem entre várias. Você pode escolher um processo mais simples que adia todo o acesso condicional até que cada fase tenha sido instruída para o registro, ou um processo mais rígido que garante o acesso condicional desde o começo e exige conformidade total para todos os acessos.

-   Saiba mais sobre o [acesso condicional](conditional-access.md).

## <a name="task-list-for-conditional-access"></a>Lista de tarefas para acesso condicional

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a>Tarefa 1: Decidir como você implementará o acesso condicional

[Maneiras comuns de usar o acesso condicional](conditional-access-intune-common-ways-use.md).

### <a name="task-2-set-up-intune-conditional-access"></a>Tarefa 2: Configurar o acesso condicional do Intune

Selecione uma das seguintes opções:

-   [Configurar o acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [Instalar o Exchange Connector local com o Intune](exchange-connector-install.md)

-   [Configurar políticas de acesso condicional baseado no aplicativo para o Exchange Online](app-based-conditional-access-intune-create.md)

-   [Configurar políticas de acesso condicional baseado no aplicativo para o SharePoint Online](app-based-conditional-access-intune-create.md)

-   [Bloquear aplicativos que não usam autenticação moderna (ADAL)](app-modern-authentication-block.md)

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre o [ciclo de migração típico](migration-guide-cycle.md).
