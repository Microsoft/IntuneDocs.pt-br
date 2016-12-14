---
title: "Estender o inventário de software e de hardware para computadores Windows | Microsoft Intune"
description: "Como exibir informações de hardware e software sobre computadores Windows que você gerencia com o Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 807599d4a6a979c88732ab969fdecb64552a83d5


---

# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a>Exibir o inventário de software e hardware para computadores Windows

O Intune coleta informações detalhadas sobre o hardware e o software dos computadores gerenciados. Use as informações nos procedimentos a seguir para aprender a criar:

-   Um relatório que relaciona as informações sobre os recursos de hardware dos computadores que você gerencia.

-   Um relatório que relaciona o software instalado em cada computador.

-   Como atualizar o inventário de um computador para garantir que os dados no relatório estejam atualizados.

## <a name="to-display-information-about-computers-you-manage"></a>Para exibir informações sobre os computadores que você gerencia

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Inventário de Computador**.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que somente computadores que executem Windows 8.1 sejam exibidos no relatório.

3.  Escolha **Exibir Relatório** para abrir o **Relatório de Inventário do Computador** em uma nova janela.

    Você pode classificar o relatório com base em qualquer uma das colunas, como **Nome**, **Tipo de Chassi** ou **Fabricante** selecionando cada título de coluna.

## <a name="to-display-software-installed-on-computers-you-manage"></a>Para exibir o software instalado nos computadores que você gerencia

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Software Detectados**.

2.  Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório.

3.  Escolha **Exibir Relatório** para abrir o **Relatório de Software Detectado** em uma nova janela.

    O relatório pode ser classificado com base em qualquer uma das colunas, como **Nome**, **Editor** ou **Categoria** selecionando cada título de coluna. Você pode expandir as atualizações nessa lista para mostrar mais detalhes (como os computadores nos quais está instalado) clicando na seta de direção ao lado do item de lista.

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>Para atualizar o inventário do computador e garantir que esteja atualizado

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contenha o computador para o qual deseja atualizar o inventário).

2.  Selecione um computador ou pressione e segure a tecla **Ctrl** para selecionar vários computadores.

3.  Na barra de tarefas, clique em **Tarefas Remotas** &gt; **Atualizar Inventário**.

4.  Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.

    A caixa de diálogo **Status da tarefa** é exibida e mostra as tarefas remotas atuais, seus status, nome do dispositivo, todos os erros reportados e fornece um link para as informações sobre a solução problemas.

### <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)


<!--HONumber=Nov16_HO4-->


