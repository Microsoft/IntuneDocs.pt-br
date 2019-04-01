---
title: Filtrar políticas com marcas de escopo no Microsoft Intune – Azure | Microsoft Docs
description: Use marcas de escopo para filtrar os perfis de configuração para funções específicas.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bca2d52bb47a149c6a36bc1b8cbc4d65e50c0f4c
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57756795"
---
# <a name="use-rbac-and-scope-tags-for-distributed-it"></a>Usar marcas de escopo e o RBAC para distribuído IT

Você pode usar o controle de acesso baseado em função (RBAC) e marcas de escopo para certificar-se de que os administradores direita tem o acesso correto e a visibilidade aos objetos do Intune à direita. As funções determinam qual acesso de administradores têm a quais objetos. Marcas de escopo determinam quais objetos os administradores podem ver.

Por exemplo, digamos que um administrador de escritório regional de Seattle é atribuído à função de gerente de política e perfil. Você deseja que esse administrador para ver e gerenciar apenas os perfis e políticas que se aplicam somente a dispositivos de Seattle. Para fazer isso, você pode:

1. Crie uma marca de escopo chamada Seattle.
2. Crie uma atribuição de função para a função de Gerenciador de perfis e de política com: 
    - Membros (grupos) = um grupo de segurança chamado administradores de TI de Seattle. Todos os administradores desse grupo terão permissão para gerenciar políticas e perfis de usuários/dispositivos no escopo (grupos).
    - Escopo (grupos) = uma segurança do grupo de usuários de Seattle nomeados. Todos os usuários/dispositivos neste grupo pode ter seus perfis e políticas gerenciados pelos administradores nos membros (grupos). 
    - Escopo (marcas) = Seattle. Os administradores no membro (grupos) podem ver os dispositivos que também têm a marca de escopo de Seattle.
3. Adicione a marca de escopo de Seattle com as políticas e perfis que você deseja que os administradores em membros (grupos) para ser capaz de acessar.
4. Adicione a marca de escopo de Seattle para dispositivos que você deseja que seja visível para os administradores nos membros (grupos). 


## <a name="to-create-a-scope-tag"></a>Para criar uma marca de escopo

1. No Intune, escolha **funções** > **escopo (marcas)** > **criar**.

    ![Captura de tela de criar uma marca de escopo.](./media/scope-tags/create-scope-tag.png)

2. Forneça um **Nome** e uma **Descrição**.
3. Escolha **Criar**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Para atribuir uma marca de escopo a uma função

1. No Intune, escolha **funções** > **todas as funções** > escolha uma função > **atribuições** > **atribuir**.

    ![Captura de tela de atribuir um escopo a uma função.](./media/scope-tags/assign-scope-to-role.png)

2. Fornecer um **nome da atribuição** e **descrição**.
3. Escolher **membros (grupos)** > **Add** > escolha os grupos que você deseja como parte dessa atribuição > **selecione**  >   **Okey**. mUsers neste grupo terão permissões para gerenciar as políticas e perfis de usuários/dispositivos no escopo (grupos).

    ![Captura de tela de grupos de membros de select.](./media/scope-tags/select-member-groups.png)

4. Se você deseja gerenciar usuários/dispositivos em um conjunto específico de grupos, escolha **escopo (grupos)** > **grupos selecionados** > **selecionar grupos para incluir**> escolha os grupos > **selecionar** > **Okey**. Todos os usuários/dispositivos neste grupo pode ter seus perfis e políticas gerenciados pelos administradores nos membros (grupo).

    ![Captura de tela de grupos de escopo de select.](./media/scope-tags/select-scope-groups.png)

    Como alternativa, você pode escolher **todos os dispositivos**, **todos os usuários**, ou **todos os usuários & todos os dispositivos**.

    ![Captura de tela de outras opções para grupos de escopo de select.](./media/scope-tags/scope-group-other-options.png)
    
5. Escolher **escopo (marcas)** > **Add** > escolha as marcas que você deseja adicionar a esta função > **selecione** > **Okey**. Os usuários em membros (grupos) terá acesso às políticas e perfis que também têm a mesma marca de escopo.

    ![Captura de tela de marcas de escopo de select.](./media/scope-tags/select-scope-tags.png)

6. Selecione **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Para adicionar uma marca de escopo a um perfil de configuração
1. No Intune, escolha **configuração do dispositivo** > **perfis** > escolha um perfil.

    ![Captura de tela de perfil de select.](./media/scope-tags/choose-profile.png)

2. Escolher **propriedades** > **escopo (marcas)** > **adicionar**.

    ![Captura de tela de adicionar marcas de escopo.](./media/scope-tags/add-scope-tags.png)

3. Sob **selecionar marcas**, escolha as marcas que você deseja adicionar ao perfil.
4. Escolher **selecionar** > **Okey** > **salvar**.

## <a name="scope-tag-details"></a>Detalhes da marca de escopo
Ao trabalhar com marcas de escopo, lembre-se esses detalhes:

- No momento, você pode atribuir as marcas de escopo para:
    - Atribuições de função
    - Políticas de conformidade do dispositivo
    - Perfis de configuração do dispositivo
    - Anéis de atualizações do Windows 10
    - Dispositivos gerenciados
    - Aplicativos
    - Políticas de configuração de aplicativo – os dispositivos gerenciados
    - Scripts do PowerShell
    - Tokens de DEP
- Quando um administrador cria um objeto no Intune, todas as marcas de escopo atribuídas para esse administrador serão atribuídas automaticamente ao novo objeto.
- RBAC do Intune não se aplica a funções do Active Directory do Azure. Dessa forma, as funções de administradores de serviço do Intune e os administradores globais têm acesso de administrador completo para o Intune não importa quais marcas de escopo que eles têm.
- Os administradores em uma atribuição de função com marcas de escopo também podem ver os objetos do Intune sem marcas de escopo.
- Você só pode atribuir uma marca de escopo que você tem em suas atribuições de função.
- Você pode apenas os grupos de destino que estão listados no escopo (grupos) de sua atribuição de função.
- Se você tiver uma marca de escopo atribuída à sua função, você não pode excluir todas as marcas de escopo em um objeto do Intune. Marca de pelo menos um escopo é necessária.
- Se um usuário tiver várias atribuições de função, as permissões nessas atribuições de função estendem a objetos diferentes da seguinte maneira:
    - Atribuir permissões se aplicam somente aos objetos (como políticas ou aplicativos) na atribuição da função escopo (grupos). Atribuir permissões não se aplicam a objetos em outras atribuições de função, a menos que a atribuição de outra conceda especificamente.
    - Outras permissões (como criar e de leitura), se aplicam a todos os objetos do mesmo tipo (como todas as políticas ou todos os aplicativos) em qualquer uma das atribuições do usuário.
    - Permissões para objetos de tipos diferentes (como políticas ou aplicativos), não se aplicam ao outro. Uma permissão de leitura para uma política, por exemplo, não fornece uma permissão de leitura para aplicativos em atribuições do usuário.





## <a name="next-steps"></a>Próximas etapas

Gerencie suas [funções](role-based-access-control.md) e seus [perfis](device-profile-assign.md).
