---
title: Configurar política de acesso condicional baseada em aplicativo com o Intune
description: Saiba como criar uma política de acesso condicional baseada em aplicativo com o Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b7e3654021935495189b62da5257793383586137
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Configurar políticas de acesso condicional baseadas em aplicativo com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo descreve como configurar políticas de acesso condicional baseadas em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

> [!IMPORTANT]
> Este artigo descreve as etapas para adicionar uma política de acesso condicional baseada em aplicativo usando o Exchange Online, mas é possível usar as mesmas etapas ao adicionar outros aplicativos como o SharePoint Online, Microsoft Teams, etc. na lista de aplicativos aprovados.

## <a name="to-create-an-app-based-conditional-access-policy"></a>Para criar uma política de acesso condicional baseado no aplicativo
1.  Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.

2.  Escolha **Todos os serviços** e digite "Intune".

3.  Escolha **Proteção de Aplicativo do Intune**.

4.  Em **Proteção de Aplicativo do Intune**, na seção **Acesso condicional**, escolha **Exchange Online**.

    ![Captura de tela do painel de configurações mostrando a seção acesso condicional com a opção Exchange Online em destaque](./media/MAM-conditional-access-1.png)

6. No painel **Aplicativos permitidos**, escolha a opção **Permitir aplicativos compatíveis com as políticas de aplicativo do Intune** para permitir que somente aplicativos compatíveis com as políticas de proteção de aplicativo do Intune acessem o Exchange Online. Ao selecionar essa opção, a lista de aplicativos com suporte é exibida.

    > [!NOTE]
    > Todos os clientes de email do Exchange Active Sync, incluindo os clientes de email interno no iOS e no Android que se conectam ao Exchange Online, são impedidos de enviar ou receber emails. Em vez disso, os usuários receberão um único email informando que eles precisam usar o aplicativo de email do Outlook.

7. Para aplicar essa política aos usuários, abra o painel **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuários**. Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.

    ![Captura de tela do painel grupo de usuários com restrições com a opção adicionar grupo de usuários em destaque](./media/mam-ca-add-user-group.png)

8. Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política. Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos. No painel **Exchange Online**, escolha **Grupos de usuários isentos**. Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários. Selecione os grupos que você deseja isentar dessa política.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Para modificar ou excluir grupos de usuários de uma política de autoridade de certificação baseada em aplicativo existente

1. Abra o painel **Grupos de usuários com restrições** e, em seguida, realce o grupo de usuários que você deseja excluir.
2. Clique nas reticências para ver as opções de exclusão.
3. Escolha **Excluir** para remover o grupo de usuários da lista.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Criar políticas de acesso condicional baseadas em aplicativo em cargas de trabalho do Azure AD

A partir da versão 1708 do Intune, os administradores de TI podem criar políticas de acesso condicional baseadas em aplicativo da carga de trabalho do Azure AD. Esse recurso traz facilidade, pois você não precisa alternar entre as cargas de trabalho do Azure e do Intune.

> [!IMPORTANT]
> Você precisa ter uma licença Premium do Azure AD para criar políticas de acesso condicional do Azure AD no portal do Intune no Azure.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Para criar uma política de acesso condicional baseado no aplicativo

> [!IMPORTANT]
> Você precisa ter [políticas de proteção de aplicativo do Intune](app-protection-policies.md) aplicadas aos seus aplicativos antes de usar políticas de acesso condicional baseadas em aplicativo.

1. No **Painel do Intune**, escolha **Acesso condicional**.

2. No painel **Políticas**, escolha **Nova política** para criar a nova política de acesso condicional baseada em aplicativo.

4. Depois de inserir um nome para a política e definir as configurações disponíveis na seção **Atribuições**, escolha **Conceder** na seção **Controles de acesso**.

5. Escolha **Exigir o aplicativo do cliente aprovado**, escolha **Selecionar** e, em seguida, escolha **Criar** para salvar a nova política.

## <a name="next-steps"></a>Próximas etapas
[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)

### <a name="see-also"></a>Consulte também

[Proteger dados de aplicativo com políticas de proteção de aplicativo](app-protection-policies.md)
[Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
