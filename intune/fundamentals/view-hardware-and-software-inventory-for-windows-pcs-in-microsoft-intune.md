---
title: Exibir o inventário de software e hardware para computadores Windows
titleSuffix: Microsoft Intune
description: Como exibir informações de hardware e software sobre áreas de trabalho do Windows gerenciadas como computadores com o cliente de software do Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 06/26/2019
ms.topic: archived
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ea74904657ec5457454e4371fb956648c74c422
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72504804"
---
# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a>Exibir o inventário de software e hardware para computadores Windows

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

> [!NOTE]
> As informações descritas neste tópico se aplicam somente a áreas de trabalho do Windows que estão sendo gerenciadas como computadores por meio do cliente de software do Intune. Se você quiser exibir o inventário de computadores Windows registrados como dispositivos móveis, consulte [Exibir detalhes do dispositivo no Intune](../remote-actions/device-inventory.md).

O Intune coleta informações detalhadas sobre o hardware e software de áreas de trabalho gerenciadas como computadores, usando o cliente de software do Intune. Use as informações nos procedimentos a seguir para aprender a criar:

- Um relatório que lista as informações sobre as funcionalidades de hardware dos computadores gerenciados.

- Um relatório que lista o software instalado em cada computador.

- Como atualizar um inventário de computadores para garantir que os dados no relatório sejam atuais.

## <a name="to-display-information-about-pcs-you-manage"></a>Para exibir informações sobre os computadores gerenciados

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Inventário de Computador**.

2. Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode escolher que apenas computadores que executem o Windows 8.1 sejam exibidos no relatório.

3. Escolha **Exibir Relatório** para abrir o **Relatório de Inventário do Computador** em uma nova janela.

    Você pode classificar o relatório com base em qualquer uma das colunas, como **Nome**, **Tipo de Chassi** ou **Fabricante** selecionando cada título de coluna.

## <a name="to-display-software-installed-on-pcs-you-manage"></a>Para exibir o software instalado nos computadores gerenciados

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Relatórios** &gt; **Relatórios de Software Detectados**.

2. Na página **Criar novo relatório** , aceite os valores padrão ou personalize-os para filtrar os resultados que serão passados como retorno pelo relatório. Por exemplo, você pode selecionar que apenas o software fornecido pela Microsoft seja exibido no relatório.

3. Escolha **Exibir Relatório** para abrir o **Relatório de Software Detectado** em uma nova janela.

    O relatório pode ser classificado com base em qualquer uma das colunas, como **Nome**, **Editor** ou **Categoria** selecionando cada título de coluna. É possível expandir as atualizações na lista para mostrar mais detalhes (como os computadores nos quais elas estão instaladas) escolhendo a seta de direção ao lado do item de lista.

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>Para atualizar o inventário do computador e garantir que esteja atualizado

1. No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contêm o computador para o qual você deseja atualizar o inventário).

2. Selecione um computador ou pressione e mantenha a tecla **Ctrl** pressionada para selecionar vários computadores.

3. Na barra de tarefas, clique em **Tarefas Remotas** &gt; **Atualizar Inventário**.

4. Para exibir o status da tarefa, selecione **Tarefas Remotas** no canto inferior direito da página.

    A caixa de diálogo **Status da tarefa** é exibida e mostra as tarefas remotas atuais, seus status, nome do dispositivo, todos os erros reportados e fornece um link para as informações sobre a solução problemas.

## <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
