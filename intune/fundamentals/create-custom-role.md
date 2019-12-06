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
ms.openlocfilehash: 3ca83287c58f8d2fb7c8eec5f8cc793e2c67b77a
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390695"
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


## <a name="copy-a-role"></a>Copiar uma função

Você também pode copiar uma função existente.

1. Entre no [portal do Azure](https://portal.azure.com) com suas credenciais do Intune e selecione **Intune**.

2. Selecione **Funções** > **Todas as funções** > selecione uma função na lista > **Duplicar**.

3. Em **Duplicar função**, insira um nome. Use um nome exclusivo.

4. Todas as permissões e marcas de escopo da função original já estarão selecionadas. Você pode alterar posteriormente o **Nome**, a **Descrição**, as **Permissões** e o **Escopo (Marcas)** da função duplicada.

5. Selecione **Criar**. 

## <a name="next-steps"></a>Próximas etapas
- [Atribuir uma função a um usuário](assign-role.md)
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)
