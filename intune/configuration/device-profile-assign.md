---
title: Atribuir perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Use o Portal do Azure para atribuir perfis de dispositivo e políticas a usuários e a dispositivos. Saiba como excluir grupos de uma atribuição de perfil no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: db1f0944a6725d1f361ea20c972d8ffa8f5d9035
ms.sourcegitcommit: a50a1ca123ecc2c5ac129f112f73838748f56476
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72237206"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Atribuir perfis de usuário e dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Você cria um perfil e ele inclui todas as configurações inseridas. A próxima etapa é implantar ou "atribuir" o perfil aos grupos de usuário ou de dispositivos do Azure Active Directory (Azure AD). Quando atribuído, os usuários e os dispositivos recebem seu perfil e as configurações inseridas são aplicadas.

Este artigo mostra como atribuir um perfil e inclui algumas informações sobre como usar marcas de escopo em seus perfis.

> [!NOTE]  
> Quando uma política é removida ou não está mais atribuída a um dispositivo, a configuração pode manter o valor existente. A configuração não é revertida para um valor padrão. Para alterar a configuração para um valor diferente, crie uma nova política e a atribua.

## <a name="assign-a-device-profile"></a>Atribuir um perfil de dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Configuração do dispositivo** > **Perfis**. Todos os perfis são listados.
3. Escolha o perfil que você deseja atribuir > **Atribuições**.
4. Escolha se deseja **Incluir** ou **Excluir** grupos e, em seguida, escolha os grupos. Ao selecionar os grupos, você está escolhendo um grupo do Azure AD. Para escolher vários grupos, mantenha a tecla **Ctrl** pressionada e escolha os grupos.

    ![Captura de tela de opções para incluir ou excluir grupos de uma atribuição de perfil](./media/device-profile-assign/group-include-exclude.png)

5. **Salve** suas alterações.

### <a name="evaluate-how-many-users-are-targeted"></a>Avaliar quantos usuários são afetados

Ao atribuir o perfil, também é possível **Avaliar** quantos usuários são afetados. Esse recurso calcula os usuários, não os dispositivos.

1. No Intune, escolha **Configuração do Dispositivo** > **Perfis**.
2. Escolha um perfil > **Atribuições** > **Avaliar**. Uma mensagem mostra quantos usuários esse perfil afeta.

Se o botão **Avaliar** estiver desabilitado, verifique se o perfil foi atribuído a um ou mais grupos.

## <a name="use-scope-tags-or-applicability-rules"></a>Usar marcas de escopo ou regras de aplicabilidade

Ao criar ou atualizar um perfil, também é possível adicionar marcas de escopo e regras de aplicabilidade a ele.

As **marcas de escopo** são uma ótima maneira de atribuir e filtrar políticas para grupos específicos, como Recursos humanos ou Todos os funcionários de determinado local geográfico. Saiba mais em [Usar o RBAC e marcas de escopo na TI distribuída](../fundamentals/scope-tags.md).

Em dispositivos com Windows 10, você pode adicionar **regras de aplicabilidade** para que o perfil se aplique apenas a uma versão específica do sistema operacional ou a uma edição específica do Windows. Saiba mais nas [regras de aplicabilidade](device-profile-create.md#applicability-rules).

## <a name="exclude-groups-from-a-profile-assignment"></a>Excluir grupos de uma atribuição de perfil

Os perfis de configuração de dispositivo do Intune permitem que você exclua grupos da atribuição de política.

O Intune não analisa as relações de grupo de usuário para dispositivo. Incluir grupos de usuários e excluir grupos de dispositivos pode não atingir os resultados esperados. Em cenários de grupo de usuários para grupo de usuários e grupo de dispositivos para grupo de dispositivos, a exclusão tem precedência sobre a inclusão.

Por exemplo, você pode atribuir um perfil de dispositivo ao grupo de usuários **Todos os usuários corporativos**, mas excluir os membros do grupo de usuários **Equipe de gerenciamento sênior**. Como ambos os grupos são grupos de usuários, todos os membros da **Equipe de gerenciamento sênior** são excluídos da política, mesmo que sejam membros do grupo de inclusão **Todos os usuários corporativos**.

A inclusão tem precedência sobre a exclusão na utilização de grupos mistos, como grupo de usuários para grupo de dispositivos, ou grupo de dispositivos para grupo de usuários.

Por exemplo, digamos que você queira atribuir um perfil de dispositivo a todos os usuários da organização, exceto os dispositivos de quiosque. você inclui o grupo **Todos os Usuários**, mas exclui o grupo **Todos os Dispositivos**. Nesse caso, todos os usuários e seus dispositivos obterão a política, mesmo se o dispositivo do usuário estiver no grupo **Todos os dispositivos**.

A exclusão apenas analisa os membros diretos do grupo. Ela não inclui os dispositivos que estão associados a um usuário. Entretanto, os dispositivos que não têm um usuário não recebem a política. Isso ocorre porque esses dispositivos sem usuários não têm qualquer relação com o grupo **Todos os usuários**.

Se você incluir **Todos os Dispositivos** e excluir **Todos os Usuários**, todos os dispositivos receberão a política. Nesse cenário a intenção é excluir dessa política os dispositivos que têm um usuário associado. No entanto, isso não exclui os dispositivos pois a exclusão compara apenas os membros diretos do grupo.

## <a name="next-steps"></a>Próximas etapas

Confira [Monitorar perfis de dispositivo](device-profile-monitor.md) para conhecer as diretrizes sobre o monitoramento de perfis e os dispositivos que executam seus perfis.
