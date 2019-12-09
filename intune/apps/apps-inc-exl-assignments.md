---
title: Incluir e excluir atribuições de aplicativo no Microsoft Intune
titleSuffix: ''
description: Saiba como usar o Microsoft Intune para incluir e excluir atribuições de aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 40cbb62a620d6e174ab8acb76798ba53080b78cf
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563970"
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Incluir e excluir atribuições de aplicativo no Microsoft Intune

No Intune, você pode determinar quem tem acesso a um aplicativo atribuindo grupos de usuários para incluir ou excluir. Antes de atribuir grupos ao aplicativo, é necessário definir o tipo de atribuição de um aplicativo. O tipo de atribuição torna o aplicativo disponível, necessário ou desinstala o aplicativo. 

Para definir a disponibilidade de um aplicativo, você deverá incluir e excluir atribuições de aplicativo a um grupo de usuários ou dispositivos usando uma combinação de atribuições de grupo de inclusão e exclusão. Esse capacidade é útil quando você disponibiliza o aplicativo por meio da inclusão de um grande grupo e, em seguida, restringe os usuários selecionados por meio da exclusão de um grupo menor. O grupo menor pode ser um grupo de teste ou executivo. 

Como prática recomendada, crie e atribua aplicativos especificamente para seus grupos de usuários e separadamente para seus grupos de dispositivos. Para obter mais informações dos grupos, confira [Adicionar grupos para organizar usuários e dispositivos](~/fundamentals/groups-add.md).  

Existem cenários importantes ao incluir ou excluir atribuições de aplicativos:

- A exclusão tem precedência sobre a inclusão nos seguintes cenários do mesmo tipo de grupo:
    - Incluir grupos de usuários e excluir grupos de usuários ao atribuir aplicativos
    - Incluir grupos de dispositivos e excluir grupos de dispositivos ao atribuir aplicativos

    Por exemplo, se você atribuir um grupo de dispositivos ao grupo de usuários **Todos os usuários corporativos**, mas excluir membros do grupo de usuários **Pessoal da gerência sênior**, **Todos os usuários corporativos**, menos o **Pessoal da gerência sênior** receberão a atribuição porque ambos os grupos são de usuários.
- O Intune não avalia as relações de grupo de usuário para dispositivo. Se você atribuir aplicativos a grupos mistos, os resultados talvez não sejam os desejados ou esperados.

    Por exemplo, se você atribuir um grupo de dispositivos ao grupo de usuários **Todos os usuários** , mas excluir um grupo de dispositivos **Todos os dispositivos pessoais**. Nessa atribuição de aplicativo a grupos mistos, o grupo **Todos os usuários** recebe o aplicativo. A exclusão não é aplicada.

Como resultado, não é recomendável atribuir aplicativos a grupos mistos.

> [!NOTE]
> Quando você configura uma atribuição de grupo a um aplicativo, o tipo **Não Aplicável** é preterido e substituído pela funcionalidade de grupo de exclusão. 
>
> O Intune fornece grupos de **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console. Os grupos têm otimizações internas para sua conveniência. É altamente recomendável usar esses grupos para direcionar a todos os usuários e todos os dispositivos, em vez de quaisquer grupos de "todos os usuários" e "todos os dispositivos" que você mesmo possa criar.  
>
> O Android Enterprise dá suporte para inclusão e exclusão de grupos. É possível aproveitar os grupos internos **Todos os Usuários** e **Todos os Dispositivos** para a atribuição de aplicativos do Android Enterprise. 

## <a name="include-and-exclude-groups-when-assigning-apps"></a>Incluir e excluir grupos ao atribuir aplicativos 
Para atribuir um aplicativo a grupos usando a atribuição de incluir e excluir:
1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Aplicativos** > **Todos os aplicativos**. A lista de aplicativos adicionados é mostrada.
3. Selecione o aplicativo que você deseja atribuir. Um painel exibe informações sobre o aplicativo. 
4. Na seção **Gerenciar** do menu, selecione **Atribuições**. 

    ![Incluir as atribuições de aplicativo durante a atribuição de aplicativos](./media/apps-inc-exl-assignments/apps-inc-exl-01.png)

5. Selecione **Adicionar grupo** para adicionar os grupos de usuários que são atribuídos ao aplicativo. 
6. No painel **Adicionar grupo**, selecione um **Tipo de atribuição** nos tipos de atribuição disponíveis.
7. Para o tipo de atribuição, selecione **Disponível com ou sem registro**.

    ![Atribuições de aplicativo do Intune – Adicionar grupo](./media/apps-inc-exl-assignments/apps-inc-exl-02.png)
8. Selecione **Grupos Incluídos** para selecionar o grupo de usuários ao qual você deseja disponibilizar esse aplicativo.

    > [!NOTE]
    > Quando você adiciona um grupo, se nenhum outro grupo já tiver sido incluído para um tipo específico de atribuição, o aplicativo será pré-selecionado e não poderá ser modificado para outros tipos de atribuição de inclusão. O grupo que foi usado não pode ser usado como um grupo incluído.

9. Selecione **Sim** para disponibilizar este aplicativo para todos os usuários.

    ![Atribuições de aplicativo do Intune – Incluir grupos](./media/apps-inc-exl-assignments/apps-inc-exl-03.png)
10. Selecione **OK** para definir o grupo a ser incluído.
11. Selecione **Grupos Excluídos** para selecionar os grupos de usuários aos quais você deseja tornar esse aplicativo indisponível. 
12. Selecione os grupos a excluir. Isso torna este aplicativo indisponível a esses grupos.

    ![Atribuições de aplicativo do Intune – Excluir grupos](./media/apps-inc-exl-assignments/apps-inc-exl-04.png)
13. Escolha **Selecionar** para concluir a seleção de grupo.
14. No painel **Adicionar grupo**, selecione **OK**. A lista **Atribuições** do aplicativo é exibida.
15. Clique em **Salvar** para ativar suas atribuições de grupo para o aplicativo.

Ao fazer atribuições de grupo, grupos que já foram atribuídos não estarão disponíveis para modificação. Se você quiser selecionar um grupo que não esteja disponível no momento, remova o aplicativo da lista atribuída do aplicativo. 

Para editar atribuições na lista **Atribuições** do aplicativo, selecione a linha que contém a atribuição específica que você deseja alterar. Você também pode remover uma atribuição selecionando as reticências ( **…** ) no final de uma linha e selecionando **Remover**. Para alterar a exibição da lista **Atribuições**, agrupe por **Tipo de atribuição** ou por **Incluído/Excluído**.

![Atribuições de aplicativo do Intune – Concluir](./media/apps-inc-exl-assignments/apps-inc-exl-05.png)

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações sobre inclusão e exclusão de atribuições de grupo para aplicativos, consulte o [Blog do Microsoft Intune](https://aka.ms/new_app_assignment_process).
- Saiba [como monitorar informações e atribuições de aplicativo](apps-monitor.md).
