---
title: Criar uma função personalizada no Intune
description: Saiba como criar uma função personalizada no Microsoft Intune.
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
ms.openlocfilehash: b60e4d801d09a834e11119260d3054cf43251bbd
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72502966"
---
# <a name="create-a-custom-role-in-intune"></a>Criar uma função personalizada no Intune

É possível criar uma função personalizada do Intune que inclui as permissões necessárias para uma função de trabalho específica. Por exemplo, se um grupo do departamento de TI gerencia aplicativos, políticas e perfis de configuração, você pode adicionar todas essas permissões juntas em uma única função personalizada. Após criar uma função personalizada, será possível [atribuí-la](assign-role.md) a usuários que precisam dessas permissões.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune**

## <a name="to-create-a-custom-role"></a>Para criar uma função personalizada

1. Entre no [portal do Azure](https://portal.azure.com) com suas credenciais do Intune.

2. Escolha **Todos os serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune** > **Funções** > **Todas as funções** > **Adicionar**.

4. Na folha **Adicionar Função Personalizada**, insira um nome e uma descrição para a nova função e clique em **Permissões**.

5. Na folha **Permissões**, escolha as permissões que você deseja usar com essa função.

6. Na folha **Escopo (Marcas)** , escolha as marcas para esta função. Essa função pode acessar recursos que também têm essas marcas.

7. Quando terminar, escolha **OK**.

8. Na folha **Adicionar Função Personalizada**, clique em **Criar**. A nova função é exibida na lista na folha **Funções do Intune – Todas as funções**.

## <a name="next-steps"></a>Próximas etapas
- [Atribuir uma função a um usuário](assign-role.md)
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)
