---
title: Atribuir perfis de dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Use o Centro de administração do Gerenciador de Ponto de Extremidade da Microsoft para atribuir perfis de dispositivo e políticas a usuários e dispositivos. Saiba como excluir grupos de uma atribuição de perfil no Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2020
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
ms.openlocfilehash: 5b61c333f41054194b44c7517e508fe1ef6d28d4
ms.sourcegitcommit: b0d683917af83170f85022b270270d8ced8e301c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76812382"
---
# <a name="assign-user-and-device-profiles-in-microsoft-intune"></a>Atribuir perfis de usuário e dispositivo no Microsoft Intune

Você cria um perfil e ele inclui todas as configurações inseridas. A próxima etapa é implantar ou "atribuir" o perfil aos grupos de usuário ou de dispositivos do Azure Active Directory (Azure AD). Quando atribuído, os usuários e os dispositivos recebem seu perfil e as configurações inseridas são aplicadas.

Este artigo mostra como atribuir um perfil e inclui algumas informações sobre como usar marcas de escopo em seus perfis.

> [!NOTE]  
> Quando um perfil é removido ou não está mais atribuído a um dispositivo, podem ocorrer coisas diferentes, dependendo das configurações no perfil. As configurações são baseadas em CSPs, e cada CSP pode lidar com a remoção de perfil de forma diferente. Por exemplo, uma configuração pode manter o valor existente e não ser revertida para o valor padrão. O comportamento é controlado por cada CSP no sistema operacional. Para obter uma lista de CSPs do Windows, confira [referência do CSP (provedor de serviços de configuração)](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).
>
> Para alterar uma configuração para um valor diferente, crie um novo perfil, defina a configuração para **Não configurado** e atribua o perfil. Depois de aplicado ao dispositivo, os usuários devem ter controle para alterar as configurações para seus valores preferidos.
>
> Ao definir essas configurações, sugerimos a implantação em um grupo piloto. Para obter mais conselhos de distribuição do Intune, confira [Criar um plano de distribuição](../fundamentals/planning-guide-rollout-plan.md).

## <a name="before-you-begin"></a>Antes de começar

Verifique se você tem a função apropriada para atribuir perfis. Para obter mais informações, confira [RBAC (controle de acesso baseado em função) com o Microsoft Intune](../fundamentals/role-based-access-control.md).

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

As **marcas de escopo** são uma ótima maneira de filtrar perfis para grupos específicos, como `US-NC IT Team` ou `JohnGlenn_ITDepartment`. Saiba mais em [Usar o RBAC e marcas de escopo na TI distribuída](../fundamentals/scope-tags.md).

Em dispositivos com Windows 10, você pode adicionar **regras de aplicabilidade** para que o perfil se aplique apenas a uma versão específica do sistema operacional ou a uma edição específica do Windows. Saiba mais nas [regras de aplicabilidade](device-profile-create.md#applicability-rules).

## <a name="user-groups-vs-device-groups"></a>Grupos de usuários X grupos de dispositivos

Muitos usuários perguntam quando devem usar grupos de usuários e quando devem usar grupos de dispositivos. A resposta depende da sua meta. Confira algumas diretrizes para começar.

### <a name="device-groups"></a>Grupos de dispositivos

Se você quiser aplicar as configurações em um dispositivo, independentemente de quem está conectado, atribua seus perfis a um grupo de dispositivos. As configurações aplicadas aos grupos de dispositivos sempre acompanham o dispositivo, não o usuário.

Por exemplo:

- Os grupos de dispositivos são úteis para gerenciar dispositivos sem um usuário dedicado. Por exemplo, você tem dispositivos que imprimem tíquetes, verificam inventários, são compartilhados por operadores de turno, são atribuídos a um depósito específico e assim por diante. Coloque esses dispositivos em um grupo de dispositivos e atribua seus perfis a esse grupo de dispositivos.

- Crie um [perfil do Intune para a DFCI (Interface de Configuração de Firmware do Dispositivo)](device-firmware-configuration-interface-windows.md) que atualiza as configurações no BIOS. Por exemplo, você configura esse perfil para desabilitar a câmera do dispositivo ou bloquear as opções de inicialização para impedir que os usuários inicializem outro sistema operacional. Esse perfil é um bom cenário para atribuir a um grupo de dispositivos.

- Em alguns dispositivos Windows específicos, você sempre deseja controlar algumas configurações do Microsoft Edge, independentemente de quem usa o dispositivo. Por exemplo, você deseja bloquear todos os downloads, limitar todos os cookies para a sessão de navegação atual e excluir o histórico de navegação. Nesse cenário, coloque esses dispositivos Windows específicos em um grupo de dispositivos. Em seguida, crie um [Modelo administrativo no Intune](administrative-templates-windows.md), adicione essas configurações de dispositivo e atribua esse perfil ao grupo de dispositivos.

Para resumir, use grupos de dispositivos quando você não se importa com quem está conectado no dispositivo ou se alguém está conectado. Você quer que essas configurações sempre estejam no dispositivo.

### <a name="user-groups"></a>Grupos de usuários

As configurações de perfis aplicadas a grupos de usuários sempre acompanham o usuário quando ele entra em seus vários dispositivos. É normal que os usuários tenham muitos dispositivos, como um Surface Pro para trabalhar e um dispositivo iOS pessoal. E é normal que a pessoa acesse email e outros recursos da organização nesses dispositivos.

Por exemplo:

- Você deseja colocar um ícone de Suporte técnico para todos os usuários em todos os dispositivos deles. Nesse cenário, coloque esses usuários em um grupo de usuários e atribua o perfil do ícone de Suporte técnico a esse grupo de usuários.
- Um usuário recebe um novo dispositivo de propriedade da organização. O usuário entra no dispositivo com a conta de domínio dele. O dispositivo é registrado automaticamente no Azure AD e é gerenciado automaticamente pelo Intune. Esse perfil é um bom cenário para atribuir a um grupo de usuários.
- Sempre que um usuário entra em um dispositivo, você deseja controlar recursos em aplicativos, como OneDrive ou Office. Nesse cenário, atribua as configurações de perfil do OneDrive ou do Office a um grupo de usuários.

  Por exemplo, você deseja bloquear controles ActiveX não confiáveis em aplicativos do Office. Você pode criar um [Modelo administrativo no Intune](administrative-templates-windows.md), definir essas configurações e atribuir esse perfil ao grupo de dispositivos.

Para resumir, use grupos de usuários quando desejar que suas configurações e regras sempre acompanhem o usuário em qualquer dispositivo que ele usar.

## <a name="exclude-groups-from-a-profile-assignment"></a>Excluir grupos de uma atribuição de perfil

Os perfis de configuração de dispositivo do Intune permitem que você inclua e exclua grupos da atribuição de perfis.

Como prática recomendada, crie e atribua perfis especificamente para os seus grupos de usuários. Além disso, crie e atribua perfis diferentes especificamente para os seus grupos de dispositivos. Para obter mais informações dos grupos, confira [Adicionar grupos para organizar usuários e dispositivos](../fundamentals/groups-add.md).

Ao atribuir perfis, use a tabela abaixo para incluir e excluir grupos. Uma marca de seleção significa que há suporte para a atribuição:

![as opções com suporte incluem ou excluem grupos de uma atribuição de perfil](./media/device-profile-assign/include-exclude-user-device-groups.png)

### <a name="what-you-should-know"></a>O que você deve saber

- A exclusão tem precedência sobre a inclusão nos seguintes cenários do mesmo tipo de grupo:

  - Incluir grupos de usuários e excluir grupos de usuários
  - Incluir grupos de dispositivos e excluir grupo de dispositivos

  Por exemplo, você pode atribuir um perfil de dispositivo ao grupo de usuários **Todos os usuários corporativos**, mas excluir os membros do grupo de usuários **Equipe de gerenciamento sênior**. Como ambos os grupos são grupos de usuários, **Todos os usuários corporativos**, exceto a **Equipe de gerenciamento sênior**, recebe o perfil.

- O Intune não avalia as relações de grupo de usuário para dispositivo. Se você atribuir perfis a grupos mistos, os resultados poderão não ser o que você deseja ou espera.

  Por exemplo, você atribui um perfil de dispositivo ao grupo de usuários **todos os usuários**, mas exclui um grupo de dispositivos **Todos os dispositivos pessoais**. Nessa atribuição de perfil de grupo misto, a opção **Todos os usuários** recebe a política. A exclusão não é aplicada.

  Como resultado, não é recomendável atribuir perfis a grupos mistos.

## <a name="next-steps"></a>Próximas etapas

Confira [Monitorar perfis de dispositivo](device-profile-monitor.md) para conhecer as diretrizes sobre o monitoramento de perfis e os dispositivos que executam seus perfis.
