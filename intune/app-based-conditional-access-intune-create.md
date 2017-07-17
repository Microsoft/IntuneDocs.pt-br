---
title: "Política de acesso condicional baseado em aplicativo com o Intune"
description: "Este tópico descreve como você pode configurar uma política de acesso condicional baseado em aplicativo com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f054868d0bae061f348239614f3a40b96a15b1
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# Configurar políticas de acesso condicional baseado em aplicativo
<a id="set-up-app-based-conditional-access-policies" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico fornece instruções sobre como configurar políticas de acesso condicional baseado em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

> [!IMPORTANT]
> Este tópico descreve as etapas para adicionar uma política de acesso condicional baseado em aplicativo usando o Exchange Online, mas é possível usar as mesmas etapas ao adicionar outros aplicativos como o SharePoint Online, Microsoft Teams, etc. na lista de aplicativos aprovados.

## Para criar uma política de acesso condicional baseado no aplicativo
<a id="to-create-an-app-based-conditional-access-policy" class="xliff"></a>
1.  Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.

2.  Escolha **Mais serviços** e digite "Intune".

3.  Escolha **Proteção de Aplicativo do Intune**.

4.  Na folha **Gerenciamento de aplicativo móvel do Intune**, escolha **Todas as Configurações**.

5.  Na seção **Acesso condicional**, escolha **Exchange Online**.

    ![Captura de tela da folha de configurações mostrando a seção acesso condicional com a opção Exchange Online em destaque](./media/MAM-conditional-access-1.png)

6. Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir que somente aplicativos com suporte para as políticas de proteção de aplicativo do Intune acessem o Exchange Online. Ao selecionar essa opção, a lista de aplicativos com suporte é exibida.

    > [!NOTE]
    > Todos os clientes de email do Exchange Active Sync, incluindo os de email interno no iOS e no Android que se conectam ao Exchange Online, serão impedidos de enviar ou receber emails. Em vez disso, os usuários receberão um único email informando que eles precisam usar o aplicativo de email do Outlook.

7. Para aplicar essa política aos usuários, abra a folha **Grupos de usuários com restrições** e escolha **Adicionar grupo de usuário**. Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.

    ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](./media/mam-ca-add-user-group.png)

8. Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política. Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos. Na folha **Exchange Online**, escolha **Grupos de usuários isentos**. Escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários. Selecione os grupos que você deseja isentar dessa política.

## Para modificar ou excluir grupos de usuários de uma política de autoridade de certificação baseada em aplicativo existente
<a id="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy" class="xliff"></a>

1. Abra a folha **Grupos de usuários restritos**, em seguida, realce o grupo de usuário que você deseja excluir.
2. Clique nas reticências para ver as opções de exclusão.
3. Escolha **Excluir** para remover o grupo de usuários da lista.

## Próximas etapas
<a id="next-steps" class="xliff"></a>
[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)

### Consulte também
<a id="see-also" class="xliff"></a>

[Proteger dados de aplicativo com as políticas de proteção de aplicativo](app-protection-policies.md)
