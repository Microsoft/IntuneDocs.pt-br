---
title: Filtrar políticas com marcas de escopo no Microsoft Intune – Azure | Microsoft Docs
description: Use marcas de escopo para filtrar os perfis de configuração para funções específicas.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2019
ms.topic: article
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 57a14e1e3c4caea570667096fec71cecf2d88ddf
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66045187"
---
# <a name="use-role-based-access-control-rbac-and-scope-tags-for-distributed-it"></a>Usar RBAC (controle de acesso baseado em função) e marcas de escopo para TI distribuída

Você pode usar marcas de escopo e controle de acesso baseado em função para que os administradores certos tenham o acesso e a visibilidade certos aos objetos certos do Intune. As funções determinam qual acesso os administradores têm a quais objetos. Marcas de escopo determinam quais objetos os administradores podem ver.

Por exemplo, digamos que um administrador de escritório regional de Seattle seja atribuído à função de Gerente de Política e Perfil. Você deseja que esse administrador veja e gerencie apenas os perfis e as políticas que se aplicam somente a dispositivos de Seattle. Para fazer isso, você pode:

1. Criar uma marca de escopo chamada Seattle.
2. Criar uma atribuição de função para a função de Gerenciador de Perfil e Política com: 
    - Membros (Grupos) = um grupo de segurança chamado administradores de TI de Seattle. Todos os administradores neste grupo terão permissão para gerenciar as políticas e os perfis de usuários/dispositivos no Escopo (Grupos).
    - Escopo (Grupos) = um grupo de segurança chamado Usuários de Seattle. Todos os usuários/dispositivos neste grupo podem ter seus perfis e políticas gerenciados pelos administradores nos Membros (Grupos). 
    - Escopo (Marcas) = Seattle. Os administradores no Membro (Grupos) podem ver os dispositivos que também têm a marca de escopo de Seattle.
3. Adicione a marca de escopo de Seattle às políticas e aos perfis que você deseja que os administradores em Membros (Grupos) possam acessar.
4. Adicione a marca de escopo de Seattle a dispositivos que você deseja que estejam visíveis aos administradores nos Membros (Grupos). 


## <a name="to-create-a-scope-tag"></a>Para criar uma marca de escopo

1. No Intune, escolha **Funções** > **Escopo (Marcas)**  > **Criar**.

    ![Captura de tela de criar uma marca de escopo.](./media/scope-tags/create-scope-tag.png)

2. Forneça um **Nome** e uma **Descrição**.
3. Escolha **Criar**.

## <a name="to-assign-a-scope-tag-to-a-role"></a>Para atribuir uma marca de escopo a uma função

1. No Intune, escolha **Funções** > **Todas as funções** > escolha uma função > **Atribuições** > **Atribuir**.

    ![Captura de tela de atribuir um escopo a uma função.](./media/scope-tags/assign-scope-to-role.png)

2. Dê um **Nome da atribuição** e uma **Descrição**.
3. Escolha **Membros (Grupos)**  > **Adicionar** > escolha os grupos que você deseja como parte dessa atribuição > **Selecionar** > **OK**. Os usuários neste grupo terão permissões para gerenciar as políticas e os perfis de usuários/dispositivos no Escopo (Grupos).

    ![Captura de tela da seleção de grupos de membros.](./media/scope-tags/select-member-groups.png)

4. Se você quiser gerenciar usuários/dispositivos em um conjunto específico de grupos, escolha **Escopo (Grupos)**  > **Grupos Selecionados** > **Selecionar grupos a incluir** > escolha os grupos > **Selecionar** > **OK**. Todos os usuários/dispositivos neste grupo podem ter seus perfis e políticas gerenciados pelos administradores nos Membros (Grupo).

    ![Captura de tela de selecionar grupos de escopo.](./media/scope-tags/select-scope-groups.png)

    Como alternativa, você pode escolher **Todos os Dispositivos**, **Todos os Usuários** ou **Todos os Usuários e Todos os Dispositivos**.

    ![Captura de tela de outras opções para selecionar grupos de escopo.](./media/scope-tags/scope-group-other-options.png)
    
5. Escolha **Escopo (Marcas)**  > **Adicionar** > escolha as marcas que você deseja adicionar a essa função > **Selecionar** > **OK**. Os usuários em Membros (Grupos) terão acesso às políticas e aos perfis que também têm a mesma marca de escopo.

    ![Captura de tela de selecionar marcas de escopo.](./media/scope-tags/select-scope-tags.png)

6. Selecione **OK**. 

## <a name="to-add-a-scope-tag-to-a-configuration-profile"></a>Para adicionar uma marca de escopo a um perfil de configuração
1. No Intune, selecione **Configuração do dispositivo** > **Perfis** > escolher um perfil.

    ![Captura de tela de selecionar perfil.](./media/scope-tags/choose-profile.png)

2. Escolha **Propriedades** > **Escopo (Marcas)**  > **Adicionar**.

    ![Captura de tela de adicionar marcas de escopo.](./media/scope-tags/add-scope-tags.png)

3. Em **Selecionar Marcas**, escolha as marcas que você deseja adicionar ao perfil.
4. Escolha **Selecionar** > **OK** > **Salvar**.

## <a name="to-assign-a-scope-tag-to-an-app-configuration-policy"></a>Para atribuir uma marca de escopo a uma política de configuração de aplicativos
Para dispositivos com o **Tipo de registro de dispositivo** definido como **Dispositivos gerenciados**:
1. Escolha **Aplicativos cliente** > **Políticas de configuração de aplicativos** > escolha uma política de configuração de aplicativos.
2. Escolha **Propriedades** > **Escopo (Marcas)** > escolha as marcas que você deseja atribuir à política.

Para dispositivos com o **Tipo de registro de dispositivo** definido como **Aplicativos gerenciados**:
1. Escolha **Aplicativos cliente** > **Políticas de configuração de aplicativos** > escolha uma política de configuração de aplicativos.
2. Escolha **Escopo (Marcas)** > escolha as marcas que você deseja atribuir à política.


## <a name="to-assign-a-scope-tag-to-an-ios-app-provisioning-profile"></a>Para atribuir uma marca de escopo a um perfil de provisionamento de aplicativo do iOS
1. No Intune, escolha **Aplicativos cliente** > **Perfis de provisionamento de aplicativo do iOS** > escolha um perfil.
2. Escolha **Propriedades** > **Escopo (Marcas)** > escolha as marcas que você deseja atribuir ao perfil.
3. Escolha **Selecionar** > **OK** > **Salvar**.

## <a name="to-assign-a-scope-tag-to-an-apple-volume-purchase-program-vpp-token"></a>Para atribuir uma marca de escopo a um token do VPP (Apple Volume Purchase Program)
1. No Intune, escolha **Aplicativos cliente** > **Tokens do Apple VPP** > escolha um token VPP.
2. Selecione **Escopo (Marcas)** > escolha as marcas que você deseja atribuir ao perfil. Os aplicativos VPP e livros eletrônicos associados ao token VPP herdam as marcas atribuídas.
3. Escolha **Selecionar** > **OK** > **Salvar**.

## <a name="scope-tag-details"></a>Detalhes da marca de escopo
Ao trabalhar com marcas de escopo, lembre-se destes detalhes:

- No momento, você pode atribuir as marcas de escopo para:
    - Atribuições de função
    - Políticas de conformidade do dispositivo
    - Perfis de configuração do dispositivo
    - Anéis de atualizações do Windows 10
    - Dispositivos gerenciados
    - Aplicativos
    - Políticas de configuração de aplicativos – dispositivos gerenciados
    - Scripts do PowerShell
    - Tokens de DEP
    - Perfil de provisionamento de aplicativo iOS
    - Tokens do VPP (Volume Purchase Program)
- Quando um administrador cria um objeto no Intune, todas as marcas de escopo atribuídas a esse administrador são atribuídas automaticamente ao novo objeto.
- RBAC do Intune não se aplica a funções do Azure Active Directory. Dessa forma, as funções de Administrador de Serviço e Administrador Global do Intune têm acesso de administrador total ao Intune, não importa quais marcas de escopo eles têm.
- Os administradores em uma atribuição de função com marcas de escopo também podem ver os objetos do Intune sem marcas de escopo.
- Você só pode atribuir uma marca de escopo que você tem em suas atribuições de função.
- Você pode apenas ter como destino grupos que estão listados no Escopo (Grupos) de sua atribuição de função.
- Se você tiver uma marca de escopo atribuída à sua função, não poderá excluir todas as marcas de escopo em um objeto do Intune. Pelo menos uma marca de escopo é necessária.

## <a name="next-steps"></a>Próximas etapas

Gerencie suas [funções](role-based-access-control.md) e seus [perfis](device-profile-assign.md).
