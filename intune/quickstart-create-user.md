---
title: Início Rápido – Criar um usuário no Intune
description: Início Rápido – Criar um usuário no Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 09/21/2018
ms.author: erikje
ms.openlocfilehash: 6a1d591e635dccd99551d9b8d40e099724a85d77
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581512"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Início Rápido: criar um usuário e atribuir uma licença a ele

Neste início rápido, você criará um usuário e atribuirá uma licença a ele. Ao usar o Intune, cada pessoa que você deseja que tenha acesso aos dados da empresa precisa ter uma conta de usuário. Os administradores do Intune podem configurar esses usuários para gerenciar o controle de acesso.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um Administrador Global ou um Administrador de Serviços do Intune.

## <a name="create-a-user"></a>Criar um usuário

As pessoas precisam ter uma conta de usuário para se registrarem no gerenciamento de dispositivo do Intune.

1. No Intune, escolha **Usuários** > **Todos os usuários** > **Novo usuário**.
![Navegador](media/quickstart-create-user/create-user.png)
2. Na caixa **Nome**, digite *Dewey Kellum*.
3. Na caixa **Nome de usuário**, digite *Dewey@contoso.onmicrosoft.com*.
4. Escolha **Grupos** > **Todos** > **Selecionar**.
5. Escolha **Mostrar senha** e anote a senha gerada automaticamente para que você possa entrar em um dispositivo de teste.
6. Escolha **Criar**.

## <a name="assign-a-license-to-the-user"></a>Atribuir uma licença ao usuário

Depois de criar um usuário, será necessário usar o [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a esse ele. Sem atribuir uma licença, não será possível registrar o dispositivo no Intune. 

1. Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.
2. Escolha **Usuários** > **Usuários Ativos** > escolha o usuário que você acabou de criar.
3. Em **Local**, escolha um local para o usuário.
3. Escolha **Licenças de produto** e defina **Enterprise Mobility + Security E3** (ou outra licença você tem que inclui o Intune) para **Ativado**.
   > [!NOTE]
   > Isso usa uma das suas licenças para este usuário. Se você estiver usando o ambiente em tempo real, poderá desligar o uso dessa licença mais tarde para reatribuí-la a um usuário real.
5. Selecione **Salvar**.

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não precisar mais desse usuário, poderá excluí-lo escolhendo **Usuários** > **Todos os usuários** > escolha o usuário na lista > **Excluir usuário** > **Sim**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um usuário e atribuiu uma licença a ele. Agora você pode atribuir esse usuário a um grupo.

> [!div class="nextstepaction"]
> [Criar um grupo](quickstart-create-group.md)
