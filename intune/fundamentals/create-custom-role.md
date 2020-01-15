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
ms.openlocfilehash: 68c2dc7df123593513c14e16e2626c7426f50b01
ms.sourcegitcommit: e166b9746fcf0e710e93ad012d2f52e2d3ed2644
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "75207410"
---
# <a name="create-a-custom-role-in-intune"></a>Criar uma função personalizada no Intune

É possível criar uma função personalizada do Intune que inclui as permissões necessárias para uma função de trabalho específica. Por exemplo, se um grupo do departamento de TI gerencia aplicativos, políticas e perfis de configuração, você pode adicionar todas essas permissões juntas em uma única função personalizada. Após criar uma função personalizada, será possível [atribuí-la](assign-role.md) a usuários que precisam dessas permissões.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune**

## <a name="to-create-a-custom-role"></a>Para criar uma função personalizada

1. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Funções** > **Todas as funções** > **Adicionar**.

2. Na folha **Adicionar Função Personalizada**, insira um nome e uma descrição para a nova função e clique em **Permissões**.

3. Na folha **Permissões**, escolha as permissões que você deseja usar com essa função.

4. Na folha **Escopo (Marcas)** , escolha as marcas para esta função. Essa função pode acessar recursos que também têm essas marcas.

5. Quando terminar, escolha **OK**.

6. Na folha **Adicionar Função Personalizada**, clique em **Criar**. A nova função é exibida na lista na folha **Funções do Intune – Todas as funções**.


## <a name="copy-a-role"></a>Copiar uma função

Você também pode copiar uma função existente.

1. No [Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Funções** > **Todas as funções** > escolha uma função na lista > **Duplicar**.

2. Em **Duplicar função**, insira um nome. Use um nome exclusivo.

3. Todas as permissões e marcas de escopo da função original já estarão selecionadas. Você pode alterar posteriormente o **Nome**, a **Descrição**, as **Permissões** e o **Escopo (Marcas)** da função duplicada.

4. Selecione **Criar**. 

## <a name="next-steps"></a>Próximas etapas
- [Atribuir uma função a um usuário](assign-role.md)
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)
