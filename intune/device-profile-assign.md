---
title: Atribuir perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Use o Portal do Azure para atribuir perfis de dispositivo e políticas a usuários e a dispositivos. Saiba como excluir grupos de uma atribuição de perfil no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/01/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fa1a1b1085d196411a03a6228eefa808399397ea
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2018
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Atribuir perfis de usuário e dispositivo no Microsoft Intune

Após criar um perfil, será possível atribuí-lo a grupos do Azure AD (Active Directory).

## <a name="assign-a-device-profile"></a>Atribuir um perfil de dispositivo

1. No [Portal do Azure](https://portal.azure.com), selecione **Todos os serviços** e pesquise o **Microsoft Intune**.
2. No **Microsoft Intune**, selecione **Configuração do dispositivo** e selecione **Perfis**.
3. Na lista de perfis, selecione o perfil que você deseja atribuir e, em seguida, selecione **Atribuições**.
4. Escolha **Incluir** ou **Excluir** grupos e, em seguida, selecione grupos.  

    ![Captura de tela de opções para incluir ou excluir grupos de uma atribuição de perfil](./media/group-include-exclude.png)

5. Ao selecionar os grupos, você está escolhendo um grupo do Azure AD. Para selecionar vários grupos, mantenha a tecla **Ctrl** pressionada.
6. Quando terminar, selecione **Salvar**.

## <a name="exclude-groups-from-a-profile-assignment"></a>Excluir grupos de uma atribuição de perfil

Os perfis de configuração de dispositivo do Intune permitem que você exclua grupos da atribuição de política. Por exemplo, você pode atribuir um perfil de dispositivo para o grupo **Todos os usuários corporativos**, mas excluir os membros do grupo **Equipe de Gerenciamento Sênior**.

Ao excluir grupos de uma atribuição, exclua apenas usuários ou exclua somente grupos de dispositivos (não uma combinação de grupos), pois o Intune não considera as relações entre usuário e dispositivos. Talvez a inclusão de grupos de usuário durante a exclusão de grupos de dispositivos não crie os resultados esperados. Ao usar grupos mistos ou em caso de outros conflitos, a inclusão terá prioridade sobre a exclusão.

Por exemplo, digamos que você deseja atribuir um perfil de dispositivo para todos os dispositivos na sua organização, exceto os dispositivos de quiosque. você inclui o grupo **Todos os Usuários**, mas exclui o grupo **Todos os Dispositivos**. Nesse caso, todos os usuários e seus dispositivos obterão a política, mesmo se o dispositivo do usuário fizer parte do grupo **Todos os Dispositivos**.

A exclusão somente considera os membros diretos dos grupos e não inclui os dispositivos que estão associados a um usuário. Entretanto, dispositivos que não têm um usuário não recebem a política. Isso ocorre porque esses dispositivos não têm nenhuma relação com o grupo **Todos os Usuários**.

Se você incluir **Todos os Dispositivos** e excluir **Todos os Usuários**, todos os dispositivos receberão a política. Nesse cenário a intenção é excluir dessa política os dispositivos que têm um usuário associado. No entanto, isso não exclui os dispositivos pois a exclusão compara apenas os membros diretos do grupo.

>[!TIP]
>As exclusões não estão disponíveis para políticas de conformidade ou atribuição de aplicativo. Para excluir membros de uma atribuição, é possível usar as atribuições **Disponível** e **Não aplicável**. Por exemplo, você atribui um aplicativo a **Todos os usuários corporativos** com a designação **Disponível** e atribui o aplicativo à **Equipe de Gerenciamento Sênior** com a designação **Não aplicável**. O aplicativo é atribuído a todos os usuários, *exceto* aos usuários do grupo **Equipe de Gerenciamento Sênior**. Se você atribuir o aplicativo a **Todos os usuários corporativos** com a designação **Necessário**, os usuários do grupo **Equipe de Gerenciamento Sênior** também serão incluídos.

## <a name="next-steps"></a>Próximas etapas
Consulte [Como monitorar perfis de dispositivo](device-profile-monitor.md) para diretrizes sobre monitoramento das atribuições de perfil de dispositivo.
