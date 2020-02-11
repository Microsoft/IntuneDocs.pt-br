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
ms.subservice: fundamentals
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: pjain
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 780a248f16a8a5028875c9c2401921ea23d0af24
ms.sourcegitcommit: 70b40aa4743c8396f8d6a0163893c4a337d67c48
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76540921"
---
# <a name="assign-a-role-to-an-intune-user"></a>Atribuir uma função a um usuário do Intune

É possível atribuir uma função [interna](role-based-access-control.md#built-in-roles) ou [personalizada](create-custom-role.md) a um usuário do Intune.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune**

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), acesse **Administração de locatários** > **Funções** > **Todas as funções**.

2. Na folha **Funções do Intune – Todas as funções**, escolha a função interna que você deseja atribuir.

3. Na folha <*nome da função*> – **Visão Geral**, escolha **Gerenciar** > **Atribuições**.

4. Na folha da função personalizada, escolha **Atribuir**.

5. Na folha **Atribuições de Função**, insira um **Nome de Atribuição** e uma **Descrição de atribuição** opcional para a atribuição.

6. Para **Membros (Grupos)** , escolha um grupo que contém o usuário para o qual você deseja conceder permissões.

7. Para **Escopo (Grupos)** , escolha um grupo que contém os usuários/dispositivos que o membro acima terá permissão para gerenciar.

8. Para **Escopo (Marcas)** , escolha as marcas nas quais essa atribuição de função será aplicada.

9. Quando terminar, escolha **OK**. A nova atribuição é exibida na lista de atribuições.


## <a name="next-steps"></a>Próximas etapas
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)
- [Criar uma função personalizada](create-custom-role.md)
