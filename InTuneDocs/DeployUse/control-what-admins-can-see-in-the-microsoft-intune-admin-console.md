---
title: "Personalizar exibições do console para funções do administrador | Microsoft Intune"
description: "Use este tópico para ajudá-lo a filtrar a exibição do console de administração do Intune para permitir que seus administradores vejam apenas os itens necessários para sua função."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 132648f4c4d13983b169fa8497deae9787fe6db5


---

# Personalizar exibições do console do Intune de acordo com funções do administrador
Você pode filtrar a exibição do console de administração do Microsoft Intune para permitir que seus administradores vejam apenas os itens que precisam ver para sua função. Por exemplo, você pode permitir que apenas os operadores do console de administração atualizem as definições de malware ou redefinam a senha em dispositivos. Você faz isso usando a predefinição **designações**, que atribui a usuários específicos. Quando esses usuários acessam o console do administrador, eles veem apenas itens específicos para suas designações.

## Como criar uma exibição personalizada

1.  No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Admin** &gt; **Administradores de Serviço**.

2.  Na lista de administradores de serviço, escolha o usuário cuja atribuição você deseja alterar e selecione **Gerenciar Acesso**.

3.  Na caixa de diálogo **Gerenciar Acesso** , escolha o nível de acesso que você deseja dar ao usuário selecionado. Você pode escolher:

    -   **Acesso completo**
    -   **Acesso somente leitura**
    -   **Assistência técnica - Nó dos Grupos**

    Acesso completo e acesso somente leitura são autoexplicativos. <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] admin console:--->

    **Assistência técnica - Nó dos Grupos** restringe o que o administrador pode ver e fazer ao seguinte:

    -   Ver listas de usuários e dispositivos. O administrador não pode usar filtros para modificar a exibição. No entanto, você pode usar a filtragem de grupo para modificar o que o administrador pode ver. Para mais informações, consulte [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md) (Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune).

    -   Imprimir a lista de usuários e dispositivos

    -   Exportar a lista de usuários e dispositivos.

    -   Exibir as propriedades de um dispositivo ou usuário

    -   Executar as seguintes tarefas remotas:

        -   Executar uma verificação completa de malware

        -   Executar uma verificação rápida de malware

        -   Reiniciar um computador

        -   Atualizar definições de malware

        -   Atualizar políticas

        -   Atualizar o inventário

        -   Bloquear um dispositivo remotamente

        -   Redefinição de senha

Na próxima vez em que o administrador configurado abrir o console de administração do Intune, ele receberá o nível de acesso designado.



<!--HONumber=Jul16_HO3-->


