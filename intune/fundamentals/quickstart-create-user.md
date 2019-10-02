---
title: Início Rápido – Criar um usuário no Intune
description: Início Rápido – Criar um usuário no Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: quickstart
ms.date: 03/25/2019
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 16d8eb3b3a0117495fe8740160e9ebcec299d764
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71727084"
---
# <a name="quickstart-create-a-user-in-intune-and-assign-them-a-license"></a>Início Rápido: Criar um usuário no Intune e atribuir uma licença

Neste início rápido, você criará um usuário e, em seguida, o atribuirá a uma licença do Intune. Ao usar o Intune, cada pessoa que você deseja que tenha acesso aos dados da empresa precisa ter sua própria conta de usuário. Os administradores do Intune podem configurar os usuários mais tarde para gerenciar o controle de acesso.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um [Administrador Global ou um Administrador de Serviços do Intune](users-add.md#types-of-administrators). Se você criar uma assinatura de avaliação do Intune, a conta com a qual criou a assinatura será a de Administrador global.

## <a name="create-a-user"></a>Criar um usuário

Os usuários precisam ter uma conta de usuário para se registrarem no gerenciamento de dispositivo do Intune. Para criar um novo usuário:

1. No Intune, escolha **Usuários** > **Todos os usuários** > **Novo usuário**.
![Navegador](./media/quickstart-create-user/create-user.png)
2. Na caixa **Nome**, insira um nome como *Dewey Kellum*.
3. Na caixa **Nome de usuário**, insira um identificador de usuário como Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Se você ainda não tiver configurado seu nome de domínio do cliente, use o nome de domínio verificado usado para criar a assinatura do Intune (ou [avaliação gratuita](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Escolha **Mostrar senha** e anote a senha gerada automaticamente para que você possa entrar em um dispositivo de teste.
5. Escolha **Criar**.

## <a name="assign-a-license-to-the-user"></a>Atribuir uma licença ao usuário

Depois de criar um usuário, será necessário usar o [Centro de administração do Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a ele. Se você não atribuir uma licença ao usuário, ele não poderá registrar o dispositivo dele no Intune. 

Para atribuir uma licença do Intune a um usuário:

1. Entre no [Centro de administração do Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.
2. Escolha **Usuários** > **Usuários Ativos** > e escolha o usuário que você acabou de criar.
3. Ao lado de **Licenças de produto**, selecione **Editar**.
4. Em **Local**, escolha um local para o usuário.
5. Clique em **Ativado** ao lado da licença do Intune (ou de outra licença sua que inclua o Intune). O [nome do produto](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** exibido é usado como o plano do serviço de gerenciamento do Azure 

   > [!NOTE]
   > Essa configuração usa uma das suas licenças para este usuário. Se você estiver usando um ambiente de avaliação, depois precisará reatribuir essa licença a um usuário real em um ambiente dinâmico.
6. Escolha **Salvar** > **Fechar**.

O novo usuário ativo do Intune agora mostrará que está usando uma licença do **Intune**.

## <a name="clean-up-resources"></a>Limpar os recursos

Caso não precise mais desse usuário, exclua-o navegando até o [Centro de administração do Microsoft 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) e escolha **Usuários** > **Usuários ativos** > *escolha o usuário na lista* > **Excluir usuário** > **Excluir usuário** > **Confirmar alterações** > **Fechar**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um usuário e atribuiu uma licença do Intune a ele. Para obter mais informações sobre como adicionar usuários ao Intune, confira [Adicionar usuários e conceder permissão administrativa ao Intune](users-add.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início rápido: Criar um grupo para gerenciar usuários](../quickstart-create-group.md)
