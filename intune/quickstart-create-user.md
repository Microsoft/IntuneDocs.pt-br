---
title: Início Rápido – Criar um usuário no Intune
description: Início Rápido – Criar um usuário no Intune.
services: microsoft-intune
author: ErikjeMS
ms.service: microsoft-intune
ms.topic: quickstart
ms.date: 10/30/2018
ms.author: erikje
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.openlocfilehash: b5653c67766a3312cf7ce2872e8b0cd4301b0e8b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189479"
---
# <a name="quickstart-create-a-user-and-assign-a-license-to-it"></a>Início Rápido: criar um usuário e atribuir uma licença a ele

Neste início rápido, você criará um usuário e atribuirá uma licença a esse usuário. Ao usar o Intune, cada pessoa que você deseja que tenha acesso aos dados da empresa precisa ter uma conta de usuário. Os administradores do Intune depois podem configurar esses usuários para gerenciar o controle de acesso.

Se você não tiver uma assinatura do Intune, [inscreva-se para uma conta de avaliação gratuita](free-trial-sign-up.md).

## <a name="sign-in-to-intune"></a>Entrar no Intune

Entre no [Intune](https://aka.ms/intuneportal) como um [administrador global ou um administrador de serviços do Intune](users-add.md#types-of-administrators). Se você tiver criado uma assinatura de avaliação do Intune, a conta com a qual você criou a assinatura será a de administrador Global.

## <a name="create-a-user"></a>Criar um usuário

As pessoas precisam ter uma conta de usuário para se registrarem no gerenciamento de dispositivo do Intune.

1. No Intune, escolha **Usuários** > **Todos os usuários** > **Novo usuário**.
![Navegador](media/quickstart-create-user/create-user.png)
2. Na caixa **Nome**, insira um nome como *Dewey Kellum*.
3. Na caixa **Nome de usuário**, insira um identificador de usuário como Dewey@contoso.onmicrosoft.com.

    > [!NOTE]
    > Se você ainda não tiver configurado seu nome de domínio do cliente, use o nome de domínio verificado que você usou para criar a assinatura do Intune (ou [avaliação gratuita](free-trial-sign-up.md#sign-up-for-a-microsoft-intune-free-trial)). 

4. Escolha **Mostrar senha** e anote a senha gerada automaticamente para que você possa entrar em um dispositivo de teste.
5. Escolha **Criar**.

## <a name="assign-a-license-to-the-user"></a>Atribuir uma licença ao usuário

Depois de criar um usuário, será necessário usar o [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a esse ele. Sem atribuir uma licença, não será possível registrar o dispositivo no Intune. 

1. Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.
2. Escolha **Usuários** > **Usuários Ativos** > escolha o usuário que você acabou de criar.
3. Ao lado de **Licenças de produto**, selecione **Editar**.
4. Em **Local**, escolha um local para o usuário.
5. Clique em **Ligar** ao lado de licença do Intune (ou outra licença sua que inclua o Intune). O [nome do produto](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)** exibido é usado como o plano do serviço de gerenciamento do Azure 

   > [!NOTE]
   > Essa configuração usa uma das suas licenças para este usuário. Se você estiver usando um ambiente de avaliação, depois precisará reatribuir essa licença a um usuário real em um ambiente dinâmico.
6. Escolha **Salvar** > **Fechar**.

O novo usuário ativo do Intune agora mostrará que está usando uma licença do **Intune**.

## <a name="clean-up-resources"></a>Limpar os recursos

Se você não precisar mais desse usuário, poderá excluí-lo navegando até o [portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) e escolhendo **Usuários** > **Usuários ativos** > *escolha o usuário na lista* > **Excluir usuário** > **Excluir usuário** > **Confirmar alterações** > **Fechar**.

## <a name="next-steps"></a>Próximas etapas

Neste início rápido, você criou um usuário e atribuiu uma licença a ele. Para obter mais informações sobre como adicionar usuários ao Intune, confira [Adicionar usuários e conceder permissão administrativa ao Intune](users-add.md).

Para seguir esta série de guias de início rápido do Intune, vá para o próximo início rápido.

> [!div class="nextstepaction"]
> [Início Rápido: Criar um grupo para gerenciar usuários](quickstart-create-group.md)
