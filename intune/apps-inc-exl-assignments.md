---
title: "Incluir e excluir atribuições de aplicativo no Microsoft Intune"
titlesuffix: 
description: "Saiba como usar o Microsoft Intune para incluir e excluir atribuições de aplicativo."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59f6df5-3317-4dff-8f19-fdeec33faedf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dbe8669dc2bf448e0738147758d90ba6d2d69b06
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2018
---
# <a name="include-and-exclude-app-assignments-in-microsoft-intune"></a>Incluir e excluir atribuições de aplicativo no Microsoft Intune

Com o Intune, você pode determinar quem tem acesso a um aplicativo, atribuindo os grupos a serem incluídos e os grupos a serem excluídos. No entanto, antes de atribuir grupos ao aplicativo, será necessário definir o tipo de atribuição de um aplicativo. O tipo de atribuição torna o aplicativo disponível, necessário ou desinstala o aplicativo. 

Ao concentrar-se na disponibilidade de um aplicativo, você deverá incluir e excluir atribuições de um grupo de usuários ou dispositivos usando uma combinação de atribuições de grupo de inclusão e exclusão. Esse capacidade é útil quando você disponibiliza o aplicativo por meio da inclusão de um grande grupo e, em seguida, restringe os usuários selecionados por meio da exclusão de um grupo menor. O grupo menor poderia ser um grupo de teste ou grupo de executivos. 

Ao excluir grupos de uma atribuição de aplicativo, é necessário excluir apenas grupos de usuários ou de dispositivos, não uma combinação de ambos. O Intune não considera as associações entre usuário e dispositivo ao excluir grupos. É improvável que você consiga os resultados necessários ao incluir grupos de usuários e excluir grupos de dispositivos, pois a inclusão terá precedência sobre a exclusão. Por exemplo, se você destinar um aplicativo iOS a **Todos os Usuários** e excluir **Todos os iPads**, o resultado será que qualquer usuário usando um iPad ainda poderá obter o aplicativo. Se, no entanto, você destinar o aplicativo iOS a **Todos os Dispositivos** e excluir **Todos os iPads**, a implantação será bem-sucedida.  

>[!NOTE]
>Ao configurar uma atribuição de grupo a um aplicativo, o tipo **Não Aplicável** ficará preterido e substituído pela funcionalidade de grupo de exclusão. 
>
>O Intune fornece os grupos **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console, com otimizações internas para sua conveniência. É altamente recomendável usar esses grupos para destinar a todos os usuários e todos os dispositivos em vez de usar outros grupos "Todos os usuários" e "Todos os dispositivos" que você mesmo tenha criado.  

## <a name="including-and-excluding-groups-when-assigning-apps"></a>Incluindo e excluindo grupos durante a atribuição de aplicativos 
Para atribuir um aplicativo a grupos usando atribuição de inclusão e exclusão:
1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Selecione **Aplicativos móveis** na folha Microsoft Intune.
4. Selecione **Aplicativos** na folha **Aplicativos móveis**. A lista de aplicativos adicionados será exibida.
5. Selecione o aplicativo que você deseja atribuir. Será exibido um painel relacionado ao aplicativo. 
6. Selecione **Atribuições** na seção **Gerenciar**. 

    ![Atribuições de aplicativo do Intune](./media/apps-inc-exl-01.png)
7. Selecione **Adicionar grupo** para adicionar os grupos de usuários que são atribuídos ao aplicativo. 
8. Selecione um **Tipo de atribuição** entre os tipos disponíveis no painel **Adicionar grupo**.
9. Selecione **Disponível com ou sem registro** como o tipo de atribuição.

    ![Atribuições de aplicativo do Intune – Adicionar grupo](./media/apps-inc-exl-02.png)
10. Selecione **Grupos Incluídos** para selecionar o grupo de usuários ao qual você deseja disponibilizar esse aplicativo.

    >[!NOTE]
    >Ao adicionar um grupo, se nenhum outro grupo ainda tenha sido incluído para um determinado tipo de atribuição, ele será pré-selecionado e ficará inalterável para outros tipos de atribuição de inclusão. Assim, esse grupo que foi usado, não poderá ser usado como um grupo incluído.

11. Selecione **Sim** para disponibilizar este aplicativo para todos os usuários.

    ![Atribuições de aplicativo do Intune – Incluir grupos](./media/apps-inc-exl-03.png)
12. Clique em **OK** para definir o grupo a ser incluído.
13. Selecione **Grupos Excluídos** para selecionar os grupos de usuários aos quais você deseja tornar esse aplicativo não disponível. 
14. Selecione os grupos que deseja excluir, tornando este aplicativo não disponível.

    ![Atribuições de aplicativo do Intune – Excluir grupos](./media/apps-inc-exl-04.png)
15. Clique em **Selecionar** para concluir a seleção de grupos.
16. Clique em **OK** na folha **Adicionar grupo**. A lista de **Atribuições** de aplicativo é exibida.
17. Clique em **Salvar** para ativar suas atribuições de grupo para o aplicativo.

Ao fazer atribuições de grupo, os grupos que já tiverem sido atribuídos ou selecionados ficarão desabilitados. Se você quiser selecionar um grupo que esteja desabilitado, remova-o da lista atribuída do aplicativo. Você pode editar atribuições da lista de **Atribuições** do aplicativo selecionando a linha que contém a atribuição específica que você deseja alterar. Além disso, você pode remover uma atribuição ao clicar na elipse (...) no final de uma linha e selecionar **Remover**. Você também pode alterar o modo de exibição da lista **Atribuições** escolhendo agrupar por **Tipo de atribuição** ou **Incluído/Excluído**.

![Atribuições de aplicativo do Intune – Concluir](./media/apps-inc-exl-05.png)

## <a name="next-steps"></a>Próximas etapas

- Para obter mais informações sobre inclusão e exclusão de atribuições de grupo para aplicativos, consulte o [Blog do Microsoft Intune](https://aka.ms/new_app_assignment_process).
- [Como monitorar informações e atribuições de aplicativo](apps-monitor.md)