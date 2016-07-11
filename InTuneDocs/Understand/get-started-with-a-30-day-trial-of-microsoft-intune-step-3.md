---
title: "Criar grupos para organizar usuários e dispositivos de assinatura de avaliação | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9755499575118feecf33780ee29a70525f95508e
ms.openlocfilehash: f438b2b5e53d9bc119341effae1533d26cc9a47b


---

# Criar grupos para organizar usuários e dispositivos de assinatura de avaliação
Os grupos no Intune oferecem grande flexibilidade para o gerenciamento de dispositivos e usuários. Você pode configurar grupos para atender as suas necessidades organizacionais (por exemplo, por localização geográfica, departamento ou características de hardware) e usá-los para executar diversas tarefas administrativas em escala, da definição de políticas para um conjunto de usuários à implantação de aplicativos para um conjunto de dispositivos.

## Criar um grupo de dispositivos
Use grupos de dispositivos para implantar software e atualizações e configurar políticas de Configurações do Agente do Microsoft Intune e Configurações do Firewall do Windows. Por exemplo, configure um grupo "Meus Dispositivos de Avaliação" usando as seguintes etapas:

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.

2.  Em **Nome do grupo**, digite “Meus Dispositivos de Avaliação”, na lista de grupos pai, selecione **Todos os Dispositivos** e, em seguida, escolha **Avançar**.

3.  Na página **Definir critérios de associação** , selecione **Todos os dispositivos** , para indicar que o grupo inclui tanto dispositivos móveis quanto computadores.

4.  Na página **Definir Associação Direta**, selecione **Avançar**. Caso você tenha criado anteriormente um grupo que não incluiu todos os dispositivos e deseje adicionar dispositivos específicos ao seu novo grupo, você pode fazer isso aqui.

5.  Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.

O grupo recém-criado pode ser encontrado na lista **Grupos** , no espaço de trabalho **Grupos** em **Todos os Dispositivos**. Nesse local, também é possível editar ou excluir o grupo.

## Criar um grupo de usuários
Use grupos de usuários para implantar políticas de dispositivo e software. Por exemplo, configure um grupo "Meus Usuários de Avaliação" usando as seguintes etapas:

1.  No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Visão geral** &gt; **Criar Grupo**.

2.  Em **Nome do grupo**, digite “Meus Usuários de Avaliação” e, na lista de grupos pai, selecione **Todos os usuários** e, em seguida, escolha **Avançar**.

3.  Na página **Definir Critérios de Associação** , defina **Iniciar associação de grupo com** como **Todos os usuários no grupo Pai**.

4.  Ao lado de **Excluir membros destes grupos de segurança**, escolha **Procurar** e, em seguida, selecione **Administrador da Empresa**. Essa exclusão permitirá gerenciar o grupo Meus Usuários de Avaliação sem afetar a conta de Administrador da Empresa (também conhecida como administrador de locatários).

5.  Na página **Definir Associação Direta**, selecione **Avançar**. Você não precisa fazer nada aqui porque deseja que o grupo Meus usuários de avaliação inclua todos os usuários, exceto o Administrador da empresa.

6.  Na página **Resumo**, examine as ações que serão tomadas e, em seguida, escolha **Concluir**.

O grupo recém-criado pode ser encontrado na lista **Grupos** , no espaço de trabalho **Grupos** em **Todos os Usuários**. Nesse local, também é possível editar ou excluir o grupo.

Para saber mais sobre como usar grupos, consulte [Use groups to manage users and devices with Microsoft Intune](/Intune/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).

### Próximas etapas
Parabéns! Você concluiu a etapa 3 do passo a passo da *avaliação do Microsoft Intune*.

>[!div class="step-by-step"]

>[&larr; **Adicionar usuários**](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-2.md)     [**Criar políticas** &larr;](.\get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  



<!--HONumber=Jun16_HO4-->


