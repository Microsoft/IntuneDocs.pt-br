---
title: "Incluir e excluir atribuições de aplicativo"
titlesuffix: Microsoft Intune
description: "Saiba como usar o Intune para incluir e excluir atribuições de aplicativo."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/29/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ca1f45c3203645dc474fcb6411a8ad598ff83714
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Incluir e excluir atribuições de aplicativo no Microsoft Intune

Com o Intune, você pode determinar quem tem acesso a um aplicativo, atribuindo os grupos a serem incluídos e os grupos a serem excluídos. Para incluir e excluir atribuições de aplicativo a um grupo de usuários ou dispositivos você usa uma combinação de atribuições de grupo de inclusão e exclusão. Depois de selecionar um aplicativo, você pode escolher como ele é atribuído. Esse capacidade é útil quando você disponibiliza o aplicativo por meio da inclusão de um grande grupo e, em seguida, restringe os usuários selecionados por meio da exclusão de um grupo menor. O grupo menor poderia ser um grupo de teste ou grupo de executivos. 

Ao excluir grupos de uma atribuição, você deve excluir apenas grupos de usuários ou de dispositivos, não uma combinação de grupos. O Intune não considera as associações entre usuário e dispositivo ao excluir grupos. É improvável que você consiga os resultados necessários ao incluir grupos de usuários e excluir grupos de dispositivos, pois a inclusão terá precedência sobre a exclusão. Por exemplo, se você destinar um aplicativo iOS a **Todos os Usuários** e excluir **Todos os iPads**, o resultado será que qualquer usuário usando um iPad ainda poderá obter o aplicativo. Se, no entanto, você destinar o aplicativo iOS a **Todos os Dispositivos** e excluir **Todos os iPads**, a implantação será bem-sucedida.  

>[!NOTE]
>Ao configurar uma atribuição de grupo a um aplicativo, o tipo **Não Aplicável** ficará preterido e substituído pela funcionalidade de grupo de exclusão. 
>
>O Intune fornece os grupos **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console, com otimizações internas para sua conveniência. É altamente recomendável usar esses grupos para destinar a todos os usuários e todos os dispositivos em vez de usar outros grupos "Todos os usuários" e "Todos os dispositivos" que você mesmo tenha criado.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Incluindo e excluindo grupos durante a atribuição de aplicativos 
Para atribuir um aplicativo a grupos usando atribuição de inclusão e exclusão:
1. Selecione **Aplicativos móveis** na folha Microsoft Intune.
2. Selecione **Aplicativos** na folha **Aplicativos móveis**. A lista de aplicativos adicionados será exibida.
3. Selecione o aplicativo que você deseja atribuir. Será exibido um painel relacionado ao aplicativo. 
4. Selecione **Atribuições** na seção **Gerenciar**. 

    ![Atribuições de aplicativo do Intune](./media/apps-inc-exl-01.png)
5. Selecione **Adicionar grupo** para adicionar os grupos de usuários que são atribuídos ao aplicativo. 
6. Selecione um **Tipo de atribuição** entre os tipos disponíveis na folha **Adicionar grupo**.
7. Selecione **Disponível com ou sem registro** como o tipo de atribuição.

    ![Atribuições de aplicativo do Intune – Adicionar grupo](./media/apps-inc-exl-02.png)
8. Selecione **Grupos Incluídos** para selecionar o grupo de usuários ao qual você deseja disponibilizar esse aplicativo.

    >[!NOTE]
    >Ao adicionar um grupo, se nenhum outro grupo ainda tenha sido incluído para um determinado tipo de atribuição, ele será pré-selecionado e ficará inalterável para outros tipos de atribuição de inclusão. Assim, esse grupo que foi usado, não poderá ser usado como um grupo incluído.

9. Selecione **Sim** para disponibilizar este aplicativo para todos os usuários.

    ![Atribuições de aplicativo do Intune – Incluir grupos](./media/apps-inc-exl-03.png)
10. Clique em **OK** para definir o grupo a ser incluído.
11. Selecione **Grupos Excluídos** para selecionar os grupos de usuários aos quais você deseja tornar esse aplicativo não disponível. 
12. Selecione os grupos que deseja excluir, tornando este aplicativo não disponível.

    ![Atribuições de aplicativo do Intune – Excluir grupos](./media/apps-inc-exl-04.png)
13. Clique em **Selecionar** para concluir a seleção de grupos.
14. Clique em **OK** na folha **Adicionar grupo**. A lista de **Atribuições** de aplicativo é exibida.
15. Clique em **Salvar** para ativar suas atribuições de grupo para o aplicativo.

Ao fazer atribuições de grupo, os grupos que já tiverem sido atribuídos ou selecionados ficarão desabilitados. Se você quiser selecionar um grupo que esteja desabilitado, remova-o da lista atribuída do aplicativo. Você pode editar atribuições da lista de **Atribuições** do aplicativo selecionando a linha que contém a atribuição específica que você deseja alterar. Além disso, você pode remover uma atribuição ao clicar na elipse (...) no final de uma linha e selecionar **Remover**. Você também pode alterar o modo de exibição da lista **Atribuições** escolhendo agrupar por **Tipo de atribuição** ou **Incluído/Excluído**.

![Atribuições de aplicativo do Intune – Concluir](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Próximas etapas

* Para obter mais informações sobre inclusão e exclusão de atribuições de grupo para aplicativos, consulte o [Blog do Microsoft Intune](https://aka.ms/new_app_assignment_process).
