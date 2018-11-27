---
title: Introdução ao gerenciamento de usuários
titlesuffix: Microsoft Intune
description: Adicionar um usuário ao Intune e atribuir uma licença para que ele acesse recursos da empresa em dispositivos móveis.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: fc5d2a6f17bdac8711348c136ee390a400fc21bd
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52182492"
---
# <a name="get-started-managing-users"></a>Introdução ao gerenciamento de usuários

Pense em todas as diferentes pessoas em sua organização. Cada uma delas que usa dados da empresa precisará de um usuário para gerenciar o acesso a esses dados no Intune.

## <a name="how-do-i-create-a-user"></a>Como eu crio um usuário?

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Depois de abrir o painel **Microsoft Intune**, selecione **Usuários**. Na página **Todos os Usuários**, selecione **+ Novo usuário**.
4. Insira os detalhes do usuário, como **Nome** e **Nome de usuário**. A parte do nome de usuário correspondente ao nome de domínio deve ser um dos seguintes domínios:
    - o nome de domínio padrão inicial “contoso.onmicrosoft.com”, ou
    - um nome de domínio verificado não federado, tal como “contoso.com”.
5. Em **Grupos**, escolha [um grupo](get-started-groups.md) ao qual adicionar o usuário.
6. Salve a senha do usuário gerada automaticamente para que você possa usá-la para entrar em um dispositivo de teste. Você deve fornecer essa senha para usuários para que eles podem alterá-la para uma senha normal que pode ser lembrada.
7. No painel **Usuário**, selecione **Criar**.

## <a name="assigning-licenses-to-users"></a>Atribuir licenças a usuários

Depois de criar um usuário, será necessário usar o [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) para atribuir uma licença do Intune a esse usuário. Sem atribuir uma licença, não será possível registrar seus dispositivos no gerenciamento.

1. Entre no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) com as mesmas credenciais que você usou para entrar no Intune.
2. Selecione **Usuários** > **Usuários Ativos** e selecione o usuário que você criou anteriormente.
3. Pode ser necessário aguardar um pouco para que todas as informações do usuário sejam carregadas. Depois de carregadas, selecione **Editar** nas **Licenças de produto** do usuário.
4. Atribua um **Local** ao usuário e mude o Intune para **ativado**.

   > [!NOTE]
   > Isso usa uma das suas licenças para este usuário. Se você estiver usando o ambiente em tempo real, poderá desligar o uso dessa licença mais tarde para reatribuí-la a um usuário real.

5. Selecione **Salvar**.

## <a name="next-steps"></a>Próximas etapas

[Introdução aos grupos](get-started-groups.md) – organize os usuários em grupos para facilitar o gerenciamento de políticas e dos aplicativos que eles podem acessar.
