---
title: Atribuir uma função a um usuário do Intune
description: Saiba como atribuir uma função interna ou personalizada a um usuário no Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: a22fef1c04ae52a8a4cc65eaadc1ef6fcd524c19
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66043588"
---
# <a name="assign-a-role-to-an-intune-user"></a>Atribuir uma função a um usuário do Intune

É possível atribuir uma função [interna](role-based-access-control.md#built-in-roles) ou [personalizada](create-custom-role.md) a um usuário do Intune.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune**

Para obter uma lista completa das permissões de cada função interna, confira a [Tabela do RBAC do Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a).

1. Entre no [portal do Azure](https://portal.azure.com).

2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.

3. Na folha **Intune**, escolha **Funções** > **Todas as funções**.

4. Na folha **Funções do Intune – Todas as funções**, escolha a função interna que você deseja atribuir.

5. Na folha <*nome da função*> – **Visão Geral**, escolha **Gerenciar** > **Atribuições**.

6. Na folha da função personalizada, escolha **Atribuir**.

7. Na folha **Atribuições de Função**, insira um **Nome de Atribuição** e uma **Descrição de atribuição** opcional para a atribuição.

8. Para **Membros (Grupos)**, escolha um grupo que contém o usuário para o qual você deseja conceder permissões.

9. Para **Escopo (Grupos)**, escolha um grupo que contém os usuários/dispositivos que o membro acima terá permissão para gerenciar.

10. Para **Escopo (Marcas)**, escolha as marcas nas quais essa atribuição de função será aplicada.

11. Quando terminar, escolha **OK**. A nova atribuição é exibida na lista de atribuições.


## <a name="next-steps"></a>Próximas etapas
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)
- [Criar uma função personalizada](create-custom-role.md)
