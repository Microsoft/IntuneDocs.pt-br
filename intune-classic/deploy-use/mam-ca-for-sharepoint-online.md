---
title: "Criar uma política de acesso condicional baseada em aplicativo para o SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 2d9065281436d4c44e6af7d7a4401786a2a01965
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a>Definir uma política de acesso condicional baseada em aplicativo para o SharePoint Online

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

Este tópico fornece orientação sobre como configurar a política de acesso condicional com base no aplicativo para o SharePoint Online. A autoridade de certificação baseada em aplicativo ajuda os administradores a permitirem somente aplicativos móveis que têm políticas de proteção de aplicativo do Intune aplicadas.

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a>Para criar a política de autoridade de certificação baseada em aplicativo para o SharePoint Online

1. Acesse o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais.

    > [!NOTE]
    > Caso você seja novo na experiência do Portal do Azure, leia o tópico [Portal do Azure para políticas de proteção de aplicativo](azure-portal-for-microsoft-intune-mam-policies.md).

2. Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.

3. Escolha **Intune App Protection** > **Gerenciamento de aplicativos móveis do Intune** > **Todas as Configurações**.

4. Na folha Gerenciamento de aplicativo móvel do Intune, escolha o bloco SharePoint Online.

5. Na folha **Aplicativos permitidos**, escolha a opção **Permitir aplicativos que dão suporte às políticas de aplicativo do Intune** para permitir somente aplicativos com suporte para as políticas de proteção de aplicativo do Intune.

    > [!NOTE] 
    > Quando você seleciona a opção para permitir somente aplicativos com suporte das políticas de proteção de aplicativo do Intune, a lista que contém **somente** os aplicativos com suporte é exibida.

    ![Captura de tela da folha de aplicativos permitidos mostrando a lista de aplicativos](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a>Para atribuir políticas de autoridade de certificação baseadas em aplicativo para seus usuários

1. Abra a folha **Usuário de grupos restritos**, escolha **Adicionar grupo de usuário**.

2. Selecione um ou mais grupos de usuários ao(s) qual(is) essa política deve ser aplicada.

    ![Captura de tela da folha grupos de usuários com restrições com a opção adicionar grupo de usuários em destaque](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > Você pode desejar que alguns usuários no grupo de usuários que você selecionou na etapa anterior não sejam afetados por essa política. Nesses casos, adicione o grupo de usuários à lista de grupos de usuários isentos. 

3. Na folha **SharePoint Online**, escolha **Grupos de usuários isentos**, escolha **Adicionar grupo de usuário** para abrir a lista de grupos de usuários.

4. Selecione os grupos que você deseja isentar dessa política.  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>Para modificar ou excluir grupos de usuários de uma política de autoridade de certificação baseada em aplicativo existente

1. Abra a folha **Grupos de usuários restritos**, em seguida, realce o grupo de usuário que você deseja excluir.
2. Clique nas reticências para ver as opções de exclusão.
3. Escolha **Excluir** para remover o grupo de usuários da lista.

> [!NOTE] 
> Você pode seguir o mesmo procedimento em etapas para remover um grupo de usuários da lista **Grupo de usuários isentos**.

## <a name="next-steps"></a>Próximas etapas

[Bloquear aplicativos que não usam autenticação moderna](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a>Consulte também

[Proteger dados de aplicativo com as políticas de proteção de aplicativo](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[Configurar a autoridade de certificação baseada em aplicativo para o Exchange Online](mam-ca-for-exchange-online.md)
