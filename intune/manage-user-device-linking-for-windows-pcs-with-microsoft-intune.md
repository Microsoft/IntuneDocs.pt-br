---
title: Gerenciar a vinculação de usuário e dispositivo para computadores Windows
titlesuffix: Microsoft Intune
description: Como vincular um usuário a um computador Windows gerenciado pelo Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic-keep
ms.openlocfilehash: 0354bf10601ed9a31cdc3beba1bf6825896a2016
ms.sourcegitcommit: 116be0eaa44fd5518ff34780d39569224ef4746b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36310939"
---
# <a name="manage-user-device-linking-for-windows-pcs"></a>Gerenciar a vinculação de usuário e dispositivo para computadores Windows

[!INCLUDE [classic-portal](includes/classic-portal.md)]

As informações descritas neste tópico se aplicam somente a áreas de trabalho do Windows que estão sendo gerenciadas como computadores por meio do cliente de software do Intune. 

Antes de poder implantar o software em um usuário, é necessário vincular o usuário a um computador. É possível vincular um usuário a vários computadores, mas cada computador pode ser vinculado a apenas um usuário. Os usuários são vinculados automaticamente aos computadores registrados por eles no Intune por meio do portal da empresa.

Para vincular um usuário a um computador:

1. No [Console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contém o computador que você deseja vincular a um usuário).

2. Selecione o computador que você deseja vincular a um usuário e escolha **Vincular Usuário**.

   A caixa de diálogo **Vincular Usuário** exibe uma lista de usuários disponíveis com o nome de exibição, ID de usuário e o número de computadores aos quais cada usuário está vinculado. Se um usuário já estiver vinculado ao computador selecionado, o nome e a ID desse usuário serão exibidos em **Usuário atual**. Se o computador não estiver vinculado a nenhum usuário, a opção **Nenhum Usuário** será exibida em **Usuário Atual**.

3. Realize um dos seguintes procedimentos:

   - Para deixar o computador vinculado ao usuário atual, se houver um, escolha **Cancelar**.

   - Para remover o link ao usuário atual, se houver um, escolha <strong>Remover link **&gt; **OK</strong>.

   - Para vincular o computador a um novo usuário, na lista **Todos os usuários**, selecione um usuário. Confirme se os dados do usuário estão corretos e escolha **OK**.

> [!TIP]
> Se você desejar restringir a capacidade dos usuários finais de se vincularem a computadores, habilite a opção **Restringir a capacidade dos usuários de se vincularem a computadores** na política **Configurações do Agente do Microsoft Intune**.

### <a name="see-also"></a>Consulte também

[Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)