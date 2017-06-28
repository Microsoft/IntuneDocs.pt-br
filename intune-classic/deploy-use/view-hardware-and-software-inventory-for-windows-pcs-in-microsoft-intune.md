---
title: "Exibir o inventário de software e hardware para computadores Windows"
description: "Como exibir informações de hardware e software sobre áreas de trabalho do Windows gerenciadas como computadores com o cliente de software do Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 0fdb49e8742fa49f1c0c1b24d5f09bcaf08a0f0a
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---

# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a>Exibir o inventário de software e hardware para computadores Windows

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune coleta informações detalhadas sobre o hardware e software de áreas de trabalho gerenciadas como computadores, usando o cliente de software do Intune. Use as informações nos procedimentos a seguir para aprender a criar:

-   Um relatório que lista as informações sobre as funcionalidades de hardware dos computadores gerenciados.

-   Um relatório que lista o software instalado em cada computador.

-   Como atualizar um inventário de computadores para garantir que os dados no relatório são atuais.

## <a name="to-display-information-about-pcs-you-manage"></a>Para exibir informações sobre os computadores gerenciados

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Inventário de Computador**.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode escolher que apenas os computadores que executam o Windows 8.1 serão exibidos no relatório.

3.  Escolha **Exibir Relatório** para abrir o **Relatório de Inventário do Computador** em uma nova janela.

    Você pode classificar o relatório com base em qualquer uma das colunas, como **Nome**, **Tipo de Chassi** ou **Fabricante** selecionando cada título de coluna.

## <a name="to-display-software-installed-on-pcs-you-manage"></a>Para exibir o software instalado nos computadores gerenciados

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Software Detectados**.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório.

3.  Escolha **Exibir Relatório** para abrir o **Relatório de Software Detectado** em uma nova janela.

    O relatório pode ser classificado com base em qualquer uma das colunas, como **Nome**, **Editor** ou **Categoria** selecionando cada título de coluna. É possível expandir as atualizações na lista para mostrar mais detalhes (como os computadores nos quais elas estão instaladas) escolhendo a seta de direção ao lado do item de lista.

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>Para atualizar o inventário do computador e garantir que esteja atualizado

1.  No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contêm o computador para o qual você deseja atualizar o inventário).

2.  Selecione um computador ou pressione e mantenha a tecla **Ctrl** pressionada para selecionar vários computadores.

3.  Na barra de tarefas, clique em **Tarefas Remotas** &gt; **Atualizar Inventário**.

4.  Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.

    A caixa de diálogo **Status da tarefa** é exibida e mostra as tarefas remotas atuais, seus status, nome do dispositivo, todos os erros reportados e fornece um link para as informações sobre a solução problemas.

### <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
