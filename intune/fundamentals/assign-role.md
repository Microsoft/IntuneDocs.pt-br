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
ms.openlocfilehash: 19fff092f7eccfc6de2a027c7834c52698176cbf
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569159"
---
# <a name="assign-a-role-to-an-intune-user"></a>Atribuir uma função a um usuário do Intune

É possível atribuir uma função [interna](role-based-access-control.md#built-in-roles) ou [personalizada](create-custom-role.md) a um usuário do Intune.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune**

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), acesse **Administração de locatários** > **Funções** > **Todas as funções**.

2. Na folha **Funções do Intune – Todas as funções**, escolha a função interna que você deseja atribuir > **Atribuições** > **Atribuir**.

5. Na página **Configurações Básicas**, insira um **Nome de atribuição** e uma **Descrição de atribuição** opcional e, em seguida, escolha **Avançar**.

6. Na página **Grupos de Administradores**, escolha um grupo que contém o usuário para o qual você deseja conceder permissões. Escolha **Avançar**

7. Na página **Escopo (Grupos)** , escolha um grupo que contém os usuários/dispositivos que o membro acima terá permissão para gerenciar. Escolha **Próxima**.

8. Para **Escopo (Marcas)** , escolha as marcas nas quais essa atribuição de função será aplicada. Escolha **Próxima**.

9. Quando terminar, escolha **Criar** na página **Revisar + Criar**. A nova atribuição é exibida na lista de atribuições.

## <a name="next-steps"></a>Próximas etapas
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)
- [Criar uma função personalizada](create-custom-role.md)


