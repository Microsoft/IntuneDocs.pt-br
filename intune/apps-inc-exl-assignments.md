---
title: Incluir e excluir atribuições de aplicativo no Microsoft Intune
titlesuffix: ''
description: Saiba como usar o Microsoft Intune para incluir e excluir atribuições de aplicativo.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b4a45ac5a73d199ec883e3dda95a97a8f3c09d9a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52181506"
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Incluir e excluir atribuições de aplicativo no Microsoft Intune

No Intune, você pode determinar quem tem acesso a um aplicativo atribuindo grupos de usuários para incluir ou excluir. Antes de atribuir grupos ao aplicativo, é necessário definir o tipo de atribuição de um aplicativo. O tipo de atribuição torna o aplicativo disponível, necessário ou desinstala o aplicativo. 

Para definir a disponibilidade de um aplicativo, você deverá incluir e excluir atribuições de aplicativo a um grupo de usuários ou dispositivos usando uma combinação de atribuições de grupo de inclusão e exclusão. Esse capacidade é útil quando você disponibiliza o aplicativo por meio da inclusão de um grande grupo e, em seguida, restringe os usuários selecionados por meio da exclusão de um grupo menor. O grupo menor pode ser um grupo de teste ou executivo. 

Ao excluir grupos de uma atribuição de aplicativo, é necessário excluir apenas grupos de usuários ou grupos de dispositivos. Você não pode excluir uma mistura de grupos de usuários e grupos de dispositivos. 

O Intune não considera a associação de usuário a dispositivo ao excluir grupos. É improvável que você consiga os resultados necessários ao incluir grupos de usuários e excluir grupos de dispositivos. A inclusão tem precedência sobre a exclusão. Por exemplo, se você direcionar o aplicativo iOS para a **Todos os Usuários** e excluir **Todos os iPads**, o resultado será que qualquer usuário usando um iPad ainda obterá o aplicativo. No entanto, se você direcionar o aplicativo iOS a **Todos os Dispositivos** e excluir **Todos os iPads**, a implantação será bem-sucedida.  

> [!NOTE]
> Quando você configura uma atribuição de grupo a um aplicativo, o tipo **Não Aplicável** é preterido e substituído pela funcionalidade de grupo de exclusão. 
>
> O Intune fornece grupos de **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console. Os grupos têm otimizações internas para sua conveniência. É altamente recomendável usar esses grupos para direcionar a todos os usuários e todos os dispositivos, em vez de quaisquer grupos de "todos os usuários" e "todos os dispositivos" que você mesmo possa criar.  
>
> O Android Enterprise dá suporte para inclusão e exclusão de grupos. É possível aproveitar os grupos internos **Todos os Usuários** e **Todos os Dispositivos** para a atribuição de aplicativos do Android Enterprise. 


## <a name="include-and-exclude-groups-when-assigning-apps"></a>Incluir e excluir grupos ao atribuir aplicativos 
Para atribuir um aplicativo a grupos usando a atribuição de incluir e excluir:
1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. No menu **Intune**, selecione **Aplicativos clientes**.
4. No painel **Aplicativos clientes**, selecione **Aplicativos**. A lista de aplicativos adicionados é mostrada.
5. Selecione o aplicativo que você deseja atribuir. Um painel exibe informações sobre o aplicativo. 
6. Na seção **Gerenciar** do menu, selecione **Atribuições**. 

    ![Atribuições de aplicativo do Intune](./media/apps-inc-exl-01.png)
7. Selecione **Adicionar grupo** para adicionar os grupos de usuários que são atribuídos ao aplicativo. 
8. No painel **Adicionar grupo**, selecione um **Tipo de atribuição** nos tipos de atribuição disponíveis.
9. Para o tipo de atribuição, selecione **Disponível com ou sem registro**.

    ![Atribuições de aplicativo do Intune – Adicionar grupo](./media/apps-inc-exl-02.png)
10. Selecione **Grupos Incluídos** para selecionar o grupo de usuários ao qual você deseja disponibilizar esse aplicativo.

    > [!NOTE]
    > Quando você adiciona um grupo, se nenhum outro grupo já tiver sido incluído para um tipo específico de atribuição, o aplicativo será pré-selecionado e não poderá ser modificado para outros tipos de atribuição de inclusão. O grupo que foi usado não pode ser usado como um grupo incluído.

11. Selecione **Sim** para disponibilizar este aplicativo para todos os usuários.

    ![Atribuições de aplicativo do Intune – Incluir grupos](./media/apps-inc-exl-03.png)
12. Selecione **OK** para definir o grupo a ser incluído.
13. Selecione **Grupos Excluídos** para selecionar os grupos de usuários aos quais você deseja tornar esse aplicativo indisponível. 
14. Selecione os grupos a excluir. Isso torna este aplicativo indisponível a esses grupos.

    ![Atribuições de aplicativo do Intune – Excluir grupos](./media/apps-inc-exl-04.png)
15. Escolha **Selecionar** para concluir a seleção de grupo.
16. No painel **Adicionar grupo**, selecione **OK**. A lista **Atribuições** do aplicativo é exibida.
17. Clique em **Salvar** para ativar suas atribuições de grupo para o aplicativo.

Ao fazer atribuições de grupo, grupos que já foram atribuídos não estarão disponíveis para modificação. Se você quiser selecionar um grupo que não esteja disponível no momento, remova o aplicativo da lista atribuída do aplicativo. 

Para editar atribuições na lista **Atribuições** do aplicativo, selecione a linha que contém a atribuição específica que você deseja alterar. Você também pode remover uma atribuição selecionando as reticências (**…**) no final de uma linha e selecionando **Remover**. Para alterar a exibição da lista **Atribuições**, agrupe por **Tipo de atribuição** ou por **Incluído/Excluído**.

![Atribuições de aplicativo do Intune – Concluir](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações sobre inclusão e exclusão de atribuições de grupo para aplicativos, consulte o [Blog do Microsoft Intune](https://aka.ms/new_app_assignment_process).
- Saiba [como monitorar informações e atribuições de aplicativo](apps-monitor.md).
