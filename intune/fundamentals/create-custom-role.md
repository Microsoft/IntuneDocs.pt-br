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
ms.openlocfilehash: bfa2758546595d1e6237d88e128958c50759eb04
ms.sourcegitcommit: 5881979c45fc973cba382413eaa193d369b8dcf6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "77569176"
---
# <a name="create-a-custom-role-in-intune"></a>Criar uma função personalizada no Intune

É possível criar uma função personalizada do Intune que inclui as permissões necessárias para uma função de trabalho específica. Por exemplo, se um grupo do departamento de TI gerencia aplicativos, políticas e perfis de configuração, você pode adicionar todas essas permissões juntas em uma única função personalizada. Após criar uma função personalizada, será possível [atribuí-la](assign-role.md) a usuários que precisam dessas permissões.

Para criar, editar ou atribuir funções, sua conta deve ter uma das seguintes permissões no Azure AD:
- **Administrador Global**
- **Administrador de Serviços do Intune**

## <a name="to-create-a-custom-role"></a>Para criar uma função personalizada

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), acesse **Administração de locatários** > **Funções** > **Todas as funções** > **Criar**.

2. Na página **Noções Básicas**, insira um nome e uma descrição para a nova função e, em seguida, escolha **Avançar**.

3. Na página **Permissões**, escolha as permissões que você deseja usar com essa função.

4. Na página **Escopo (Marcas)** , escolha as marcas para esta função. Essa função pode acessar recursos que também têm essas marcas. Escolha **Próxima**.

5. Quando terminar, escolha **Criar** na página **Revisar + criar**. A nova função é exibida na lista na folha **Funções do Intune – Todas as funções**.

## <a name="copy-a-role"></a>Copiar uma função

Você também pode copiar uma função existente.

1. No [Centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), escolha **Administração de locatários** > **Funções** > **Todas as funções** > selecione a caixa de seleção para uma função na lista > **Duplicar**.

2. Na página **Noções Básicas**, insira um nome. Use um nome exclusivo.

3. Todas as permissões e marcas de escopo da função original já estarão selecionadas. Você pode alterar posteriormente o **Nome**, a **Descrição**, as **Permissões** e o **Escopo (Marcas)** da função duplicada.

4. Depois de fazer todas as alterações desejadas, escolha **Avançar** para acessar a página **Revisar + criar**. Selecione **Criar**. 

## <a name="next-steps"></a>Próximas etapas
- [Atribuir uma função a um usuário](assign-role.md)
- [Saiba mais sobre o controle de acesso baseado em função no Intune](role-based-access-control.md)


