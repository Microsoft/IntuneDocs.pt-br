---
title: Início Rápido – Criar um usuário no Intune
description: Início Rápido – Criar um usuário no Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 01/17/2020
ms.author: erikje
ms.manager: dougeby
ms.assetid: 820fcb18-0927-4ebd-be79-dce92b51c261
ms.reviewer: dougeby
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: f6aa57b71e052e3fc8566fcdff8bdd9ef5d1c39e
ms.sourcegitcommit: 139853f8d6ea61786da7056cfb9024a6459abd70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2020
ms.locfileid: "76754483"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-the-user-a-license"></a>Início Rápido: Criar um usuário no Intune e atribuir uma licença ao usuário

Neste início rápido, você criará um usuário e atribuirá uma licença do Intune para ele. Quando você usa o Intune, cada pessoa que você deseja que tenha acesso aos dados da empresa precisa ter sua própria conta de usuário. Os administradores do Intune podem configurar os usuários mais tarde para gerenciar o controle de acesso.

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura do Microsoft Intune. [Inscreva-se para uma avaliação gratuita](../fundamentals/free-trial-sign-up.md).

## <a name="sign-in-to-intune-in-microsoft-endpoint-manager"></a>Entrar no Intune no Gerenciador de Ponto de Extremidade da Microsoft

Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) como [Administrador global ou Administrador de serviços do Intune](users-add.md#types-of-administrators). Se você criar uma assinatura de avaliação do Intune, a conta com a qual criou a assinatura será a de Administrador global.

## <a name="create-a-user"></a>Criar um usuário

Um usuário precisa ter uma conta de usuário para se inscrever no gerenciamento de dispositivo do Intune. Para criar um novo usuário:

1. No Gerenciador de Ponto de Extremidade da Microsoft, selecione **Usuários** > **Todos os usuários** > **Novo usuário**:  ![No Gerenciador de Ponto de Extremidade da Microsoft, selecione Novo usuário](./media/quickstart-create-user/create-user.png)
2. Na caixa **Nome**, insira um nome, como *Davi Barros*:  ![Adicionar detalhes do usuário](./media/quickstart-create-user/create-user-02.png)
3. Na caixa **Nome de usuário**, informe um identificador do usuário, como Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Se você ainda não tiver configurado seu nome de domínio do cliente, use o nome de domínio verificado usado para criar a assinatura do Intune (ou [avaliação gratuita](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Selecione **Mostrar senha** e lembre-se de anotar a senha gerada automaticamente para que você possa entrar em um dispositivo de teste.
5. Selecione **Criar**.

## <a name="assign-a-license-to-the-user"></a>Atribuir uma licença ao usuário

Depois de criar um usuário, será necessário usar o [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a ele. Se você não atribuir uma licença ao usuário, ele não poderá registrar o dispositivo dele no Intune.

Para atribuir uma licença do Intune a um usuário:

1. Entre no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.
2. Selecione **Usuários** > **Usuários Ativos** e selecione o usuário que você acabou de criar.
3. Selecione a guia **Licenças e Aplicativos**.
4. Em **Selecionar local**, escolha um local para o usuário, se ainda não estiver definido.
2. Marque a caixa de seleção **Intune** na seção **Licenças**. Se outra licença incluir o Intune, você poderá selecioná-la. O [nome do produto](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference) exibido é usado como o plano de serviço no gerenciamento do Azure.

    ![Selecionar o local e a licença do Intune](./media/quickstart-create-user/create-user-03.png)

   > [!NOTE]
   > Essa configuração usa uma das suas licenças para o usuário. Se você estiver usando um ambiente de avaliação, depois precisará reatribuir essa licença a um usuário real em um ambiente dinâmico.

6. Selecione **Salvar alterações**.

O novo usuário ativo do Intune agora mostrará que está usando uma licença do **Intune**.

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não precisar mais desse usuário, poderá excluí-lo acessando o [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) e selecionando **Usuários** > *o usuário* > *o ícone Excluir usuário* > **Excluir usuário** > **Fechar**.

   ![Selecionar o ícone Excluir](./media/quickstart-create-user/create-user-04.png)

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um usuário e atribuiu uma licença do Intune para ele. Para obter mais informações sobre como adicionar usuários ao Intune, confira [Adicionar usuários e conceder permissão administrativa ao Intune](users-add.md).

Para continuar esta série de guias de início rápido do Intune, vá para o próximo início rápido:

> [!div class="nextstepaction"]
> [Início rápido: Criar um grupo para gerenciar usuários](../quickstart-create-group.md)
