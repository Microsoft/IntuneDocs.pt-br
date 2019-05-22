---
title: Atribuir perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Use o Portal do Azure para atribuir perfis de dispositivo e políticas a usuários e a dispositivos. Saiba como excluir grupos de uma atribuição de perfil no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/08/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0c950efdd95fd8d856ec677385712a022dead870
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59570501"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Atribuir perfis de usuário e dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Você cria um perfil e ele inclui todas as configurações inseridas. A próxima etapa é implantar ou "atribuir" o perfil aos grupos de usuário ou de dispositivos do Azure Active Directory (Azure AD). Quando atribuído, os usuários e os dispositivos recebem seu perfil e as configurações inseridas são aplicadas.

Este artigo mostra como atribuir um perfil e inclui algumas informações sobre como usar marcas de escopo em seus perfis.

## <a name="assign-a-device-profile"></a>Atribuir um perfil de dispositivo

1. No [portal do Azure](https://portal.azure.com), selecione **Todos os Serviços** > filtre por **Intune** > selecione **Intune**.
2. Selecione **Configuração do dispositivo** > **Perfis**. Todos os perfis são listados.
3. Escolha o perfil que você deseja atribuir > **Atribuições**.
4. Escolha se deseja **Incluir** ou **Excluir** grupos e, em seguida, escolha os grupos. Ao selecionar os grupos, você está escolhendo um grupo do Azure AD. Para escolher vários grupos, mantenha a tecla **Ctrl** pressionada e escolha os grupos.

    ![Captura de tela de opções para incluir ou excluir grupos de uma atribuição de perfil](./media/group-include-exclude.png)

5. **Salve** suas alterações.

### <a name="evaluate-how-many-users-are-targeted"></a>Avaliar quantos usuários são afetados

Ao atribuir o perfil, também é possível **Avaliar** quantos usuários são afetados. Esse recurso calcula os usuários, não os dispositivos.

1. No Intune, escolha **Configuração do Dispositivo** > **Perfis**.
2. Escolha um perfil > **Atribuições** > **Avaliar**. Uma mensagem mostra quantos usuários esse perfil afeta.

Se o botão **Avaliar** estiver desabilitado, verifique se o perfil foi atribuído a um ou mais grupos.


## <a name="use-scope-tags"></a>Usar marcas de escopo

Ao criar ou atualizar um perfil, também é possível adicionar marcas de escopo a ele.

As **marcas de escopo** são uma ótima maneira de atribuir e filtrar políticas para grupos específicos, como Recursos humanos ou Todos os funcionários de determinado local geográfico. Saiba mais em [Usar o RBAC e marcas de escopo na TI distribuída](scope-tags.md).

## <a name="exclude-groups-from-a-profile-assignment"></a>Excluir grupos de uma atribuição de perfil

Os perfis de configuração de dispositivo do Intune permitem que você exclua grupos da atribuição de política. Por exemplo, você pode atribuir um perfil de dispositivo para o grupo **Todos os usuários corporativos**, mas excluir os membros do grupo **Equipe de gerenciamento sênior**.

Ao excluir grupos, apenas usuários ou somente grupos de dispositivos (não uma combinação de grupos) de uma atribuição, o Intune não considera as relações entre usuário e dispositivos. Incluir grupos de usuários e excluir grupos de dispositivos pode não atingir os resultados esperados. Ao usar grupos mistos ou em caso de outros conflitos, a inclusão terá prioridade sobre a exclusão.

Por exemplo, digamos que você deseja atribuir um perfil de dispositivo para todos os dispositivos na sua organização, exceto os dispositivos de quiosque. você inclui o grupo **Todos os Usuários**, mas exclui o grupo **Todos os Dispositivos**. Nesse caso, todos os usuários e seus dispositivos obterão a política, mesmo se o dispositivo do usuário estiver no grupo **Todos os dispositivos**.

A exclusão apenas analisa os membros diretos do grupo. Ela não inclui os dispositivos que estão associados a um usuário. Entretanto, dispositivos que não têm um usuário não recebem a política. Isso ocorre porque esses dispositivos não têm qualquer relação com o grupo **Todos os Usuários**.

Se você incluir **Todos os Dispositivos** e excluir **Todos os Usuários**, todos os dispositivos receberão a política. Nesse cenário a intenção é excluir dessa política os dispositivos que têm um usuário associado. No entanto, isso não exclui os dispositivos pois a exclusão compara apenas os membros diretos do grupo.

## <a name="next-steps"></a>Próximas etapas

Confira [Monitorar perfis de dispositivo](device-profile-monitor.md) para conhecer as diretrizes sobre o monitoramento de perfis e os dispositivos que executam seus perfis.