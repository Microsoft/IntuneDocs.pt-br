---
title: Atribuir perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Use o Portal do Azure para atribuir perfis de dispositivo e políticas a usuários e a dispositivos. Saiba como excluir grupos de uma atribuição de perfil no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: altsou
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae8bc7d5797a2ba6404331166e9d955bbb2fadf9
ms.sourcegitcommit: 78cebd3571fed72a3a99e9d33770ef3d932ae8ca
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74059593"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Atribuir perfis de usuário e dispositivo no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Você cria um perfil e ele inclui todas as configurações inseridas. A próxima etapa é implantar ou "atribuir" o perfil aos grupos de usuário ou de dispositivos do Azure Active Directory (Azure AD). Quando atribuído, os usuários e os dispositivos recebem seu perfil e as configurações inseridas são aplicadas.

Este artigo mostra como atribuir um perfil e inclui algumas informações sobre como usar marcas de escopo em seus perfis.

> [!NOTE]  
> Quando uma política é removida ou não está mais atribuída a um dispositivo, a configuração pode manter o valor existente. A configuração não é revertida para um valor padrão. Para alterar a configuração para um valor diferente, crie uma nova política e a atribua.

## <a name="before-you-begin"></a>Antes de começar

Verifique se você tem a função apropriada para atribuir políticas. Para obter mais informações, confira [RBAC (controle de acesso baseado em função) com o Microsoft Intune](../fundamentals/role-based-access-control.md).

## <a name="assign-a-device-profile"></a>Atribuir um perfil de dispositivo

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Selecione **Dispositivos** > **Perfis de configuração**. Todos os perfis são listados.
3. Escolha o perfil que você deseja atribuir > **Atribuições**.
4. Escolha se deseja **Incluir** ou **Excluir** grupos e, em seguida, escolha os grupos. Ao selecionar os grupos, você está escolhendo um grupo do Azure AD. Para escolher vários grupos, mantenha a tecla **Ctrl** pressionada e escolha os grupos.

    ![Captura de tela de opções para incluir ou excluir grupos de uma atribuição de perfil](./media/device-profile-assign/group-include-exclude.png)

5. **Salve** suas alterações.

### <a name="evaluate-how-many-users-are-targeted"></a>Avaliar quantos usuários são afetados

Ao atribuir o perfil, também é possível **Avaliar** quantos usuários são afetados. Esse recurso calcula os usuários, não os dispositivos.

1. No centro de administração, selecione **Dispositivos** > **Configuração**.
2. Escolha um perfil > **Atribuições** > **Avaliar**. Uma mensagem mostra quantos usuários esse perfil afeta.

Se o botão **Avaliar** estiver desabilitado, verifique se o perfil foi atribuído a um ou mais grupos.

## <a name="use-scope-tags-or-applicability-rules"></a>Usar marcas de escopo ou regras de aplicabilidade

Ao criar ou atualizar um perfil, também é possível adicionar marcas de escopo e regras de aplicabilidade a ele.

As **marcas de escopo** são uma ótima maneira de atribuir e filtrar políticas para grupos específicos, como Recursos humanos ou Todos os funcionários de determinado local geográfico. Saiba mais em [Usar o RBAC e marcas de escopo na TI distribuída](../fundamentals/scope-tags.md).

Em dispositivos com Windows 10, você pode adicionar **regras de aplicabilidade** para que o perfil se aplique apenas a uma versão específica do sistema operacional ou a uma edição específica do Windows. Saiba mais nas [regras de aplicabilidade](device-profile-create.md#applicability-rules).

## <a name="exclude-groups-from-a-profile-assignment"></a>Excluir grupos de uma atribuição de perfil

Os perfis de configuração de dispositivo do Intune permitem que você inclua e exclua grupos da atribuição de política.

Como prática recomendada, crie e atribua políticas especificamente para seus grupos de usuários. Além disso, crie e atribua políticas diferentes especificamente para seus grupos de dispositivos. Para obter mais informações dos grupos, confira [Adicionar grupos para organizar usuários e dispositivos](../fundamentals/groups-add.md).

Ao atribuir suas políticas, use a tabela abaixo para incluir e excluir grupos. Uma marca de seleção significa que há suporte para a atribuição:

![as opções com suporte incluem ou excluem grupos de uma atribuição de perfil](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>O que você deve saber

- A exclusão tem precedência sobre a inclusão nos seguintes cenários do mesmo tipo de grupo:

  - Incluir grupos de usuários e excluir grupos de usuários
  - Incluir grupos de dispositivos e excluir grupo de dispositivos

  Por exemplo, você pode atribuir um perfil de dispositivo ao grupo de usuários **Todos os usuários corporativos**, mas excluir os membros do grupo de usuários **Equipe de gerenciamento sênior**. Como ambos os grupos são grupos de usuários, **Todos os usuários corporativos**, exceto a **Equipe de gerenciamento sênior**, recebe a política.

- O Intune não avalia as relações de grupo de usuário para dispositivo. Se você atribuir políticas a grupos mistos, os resultados poderão não ser o que você deseja ou espera.

  Por exemplo, você atribui um perfil de dispositivo ao grupo de usuários **todos os usuários**, mas exclui um grupo de dispositivos **Todos os dispositivos pessoais**. Nessa atribuição de política de grupo mista, **Todos os usuários** recebe a política. A exclusão não é aplicada.

  Como resultado, não é recomendável atribuir políticas a grupos mistos.

## <a name="next-steps"></a>Próximas etapas

Confira [Monitorar perfis de dispositivo](device-profile-monitor.md) para conhecer as diretrizes sobre o monitoramento de perfis e os dispositivos que executam seus perfis.
