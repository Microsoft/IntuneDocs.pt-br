---
title: Início Rápido – Criar um grupo para gerenciar usuários
titlesuffix: Microsoft Intune
description: Neste início rápido você usará o Microsoft Intune para criar um grupo com base em usuários existentes.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 723f4b4e-3090-4811-84ff-6af652abea5a
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3a4468f2e6919349095d934790740afc8c347282
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581510"
---
# <a name="quickstart-create-a-group-to-manage-users"></a>Início Rápido: criar um grupo para gerenciar usuários

Neste início rápido, você usará o Intune para criar um grupo com base em usuários existentes. Os grupos são usados para gerenciar os usuários e controlar o acesso dos funcionários aos recursos da empresa. Esses recursos podem fazer parte da intranet da empresa ou recursos externos, como sites do SharePoint, aplicativos SaaS ou aplicativos Web.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

>[!NOTE]
>O Intune fornece os grupos **Todos os Usuários** e **Todos os Dispositivos** pré-criados no console, com otimizações internas para sua conveniência.

## <a name="prerequisites"></a>Pré-requisitos

- Para concluir esse início rápido, é preciso [criar um usuário](quickstart-create-user.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune. O Intune encontra-se no portal do Azure, escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.

## <a name="create-a-group"></a>Criar um grupo
1. Depois de abrir o painel do **Microsoft Intune**, selecione **Grupos** > **Novo grupo**.
2. No painel **Grupo**, selecione **Tipo de grupo** > **Segurança**.
3. Defina o **Nome** como “Testadores Contoso” e adicione uma **Descrição** para o grupo.
4. Defina o **Tipo de associação** como **Atribuído**. 
5. Clique em **Membros** e selecione **Membros** para o grupo da lista existente.

    ![Captura de tela da criação de um grupo no Microsoft Intune](./media/quickstart-use-groups-01.png)

6. Clique em **Selecionar**.
7. Clique em **Criar**.

Se um grupo foi criado com êxito, ele aparecerá na lista de **Todos os grupos**. 

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você usará o Intune para criar um grupo com base em usuários existentes.

> [!div class="nextstepaction"]
> [Criar uma política de conformidade do dispositivo](quickstart-create-policy.md)
