---
title: Políticas de conformidade do dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Introdução ao uso de políticas de conformidade do dispositivo, visão geral dos níveis de status e gravidade, uso do status InGracePeriod, trabalhar com Acesso Condicional, manuseio de dispositivos sem uma política atribuída e diferenças de conformidade no Portal do Azure e no portal clássico no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8b3a99744f830da3c88473e79bce78c97875d73
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71722625"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Criar uma política de conformidade no Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

As políticas de conformidade do dispositivo são um recurso importante ao usar o Intune para proteger recursos da sua organização. No Intune, você pode criar regras e configurações que dispositivos precisam cumprir para serem considerados em conformidade, como uma verão mínima do sistema operacional. Se o dispositivo não está em conformidade, é possível bloquear o acesso aos dados e recursos usando o [Acesso Condicional](conditional-access.md).

Você também pode executar ações para casos de não conformidade, como enviar um email de notificação ao usuário. Para ver uma visão geral do que fazem as políticas de conformidade e como elas são usadas, confira a [Introdução à conformidade do dispositivo](device-compliance-get-started.md).

Este artigo:

- Lista os pré-requisitos e as etapas para criar uma política de conformidade.
- Mostra como atribuir a política aos grupos de usuários e dispositivos.
- Descreve os recursos adicionais, incluindo as marcas de escopo para "filtrar" suas políticas e as etapas que você pode executar em dispositivos que não são compatíveis.
- Lista os tempos de ciclo de atualização de check-in quando os dispositivos recebem as atualizações da política.

## <a name="before-you-begin"></a>Antes de começar

Para usar as políticas de conformidade do dispositivo, não deixe de:

- Usar as seguintes assinaturas:

  - Intune
  - Ao usar o Acesso Condicional, você precisa da edição Premium do Azure Active Directory (AD). A opção [Preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/) exibe o que é oferecido nas diferentes edições. A conformidade do Intune não exige o Azure AD.

- Usar uma plataforma compatível:

  - Android
  - Android Enterprise
  - iOS
  - macOS (versão prévia)
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Inscrever dispositivos no Intune (obrigatório para ver o status de conformidade)

- Inscrever dispositivos para um usuário, ou inscrever sem um usuário primário. Não há suporte para dispositivos registrados para vários usuários.

## <a name="create-the-policy"></a>Criar a política

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Selecione **Conformidade do dispositivo**. Você tem as seguintes opções:

    - **Visão geral**: Mostra um resumo e a quantidade de dispositivos que estão em conformidade, não avaliados e assim por diante. Também lista as políticas e configurações individuais em suas políticas. [Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md) oferece informações úteis.
    - **Gerenciar**: Crie políticas de dispositivo, envie [notificações](quickstart-send-notification.md) para dispositivos que não estão em conformidade e habilite o [isolamento de rede](use-network-locations.md).
    - **Monitorar**: Verifique o status de conformidade de seus dispositivos e o nível de configuração e política. [Monitorar as políticas de conformidade do dispositivo do Intune](compliance-policy-monitor.md) é um recurso útil. Além disso, visualize os logs e verifique o status do agente de ameaça de seus dispositivos.
    - **Configuração**: Use as [políticas de conformidade internas](device-compliance-get-started.md#ways-to-deploy-device-compliance-policies), habilite a [ATP (Proteção Avançada contra Ameaças) do Microsoft Defender](advanced-threat-protection.md), adicione um [conector de defesa contra ameaças móveis](mobile-threat-defense.md) e use o [Jamf](conditional-access-integrate-jamf.md).

3. Selecione **Políticas** > **Criar Política**. Insira as seguintes propriedades:

    - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política seria **Marcar dispositivos do iOS com jailbreak como fora de conformidade**.
    - **Descrição**: Insira uma descrição para a política. Essa configuração é opcional, mas recomendada.
    - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:  

       - **Android**
       - **Android Enterprise**
       - **iOS**
       - **macOS**
       - **Windows Phone 8.1**
       - **Windows 8.1 e posterior**
       - **Windows 10 e posterior**

    - **Configurações**: Os artigos a seguir listam e descrevem as configurações de cada plataforma:

        - [Android](compliance-policy-create-android.md)
        - [Android Enterprise](compliance-policy-create-android-for-work.md)
        - [iOS](compliance-policy-create-ios.md)
        - [macOS](compliance-policy-create-mac-os.md)
        - [Windows Phone 8.1, Windows 8.1 e posteriores](compliance-policy-create-windows-8-1.md)
        - [Windows 10 e posterior](compliance-policy-create-windows.md)

4. Quando terminar, selecione **OK** > **Criar** para salvar as alterações. A política é criada e exibida na lista. Em seguida, atribua a política a grupos.

## <a name="assign-user-groups"></a>Atribuir grupos de usuários

Depois que uma política é criada, a próxima etapa é atribuir a política aos grupos:

1. Escolha uma política que você criou. As políticas existentes estão em **Conformidade do dispositivo** > **Políticas**.
2. Escolha a política > **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).
3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Escolha os grupos de usuários aos quais deseja aplicar essa política > escolha **Salvar** para implantar a política para os usuários.

Você aplicou a política aos usuários. Os dispositivos usados pelos usuários afetados pela política são avaliados quanto à conformidade.

### <a name="evaluate-how-many-users-are-targeted"></a>Avaliar quantos usuários são afetados

Ao atribuir a política, também é possível **Avaliar** quantos usuários são afetados. Esse recurso calcula os usuários, não os dispositivos.

1. No Intune, escolha **Conformidade do Dispositivo** > **Políticas**.
2. Escolha a política > **Atribuições** > **Avaliar**. Uma mensagem é exibida mostrando quantos usuários essa política afeta.

Se o botão **Avaliar** estiver desabilitado, verifique se a política foi atribuída a um ou mais grupos.

## <a name="actions-for-noncompliance"></a>Ações de não conformidade

Para dispositivos que não atendem às suas políticas de conformidade, é possível adicionar uma sequência de ações a serem aplicadas automaticamente. Você pode alterar a agenda quando o dispositivo está marcado como não em conformidade, como após um dia. Você também pode configurar uma segunda ação que envia um email para o usuário quando o dispositivo não está em conformidade.

[Adicionar ações a dispositivos que não estão em conformidade](actions-for-noncompliance.md) apresenta mais informações, incluindo como criar um email de notificação para seus usuários.

Por exemplo, você está usando o recurso Locais e adiciona uma localização em uma política de conformidade. A ação padrão para não conformidade se aplica quando você seleciona pelo menos uma localização. Se o dispositivo não estiver conectado a locais selecionados, imediatamente será considerado que ele não está em conformidade. Você pode dar aos usuários um período de cortesia, como um dia.

## <a name="scope-tags"></a>Marcas de escopo

As marcas de escopo são uma ótima maneira de atribuir e filtrar políticas para grupos específicos, como Vendas, RH, todos os funcionários de determinado local geográfico e assim por diante. Após adicionar as configurações, você também pode adicionar uma marca de escopo às políticas de conformidade. [Usar marcas de escopo para filtrar políticas](../fundamentals/scope-tags.md) é um recurso útil.

## <a name="refresh-cycle-times"></a>Tempos de ciclo de atualização

O Intune usa ciclos de atualização diferentes para verificar se há atualizações de políticas de conformidade. Se o dispositivo for recém-registrado, a frequência de execução do check-in será maior. Os [ciclos de atualização de política e perfil](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) listam os tempos de atualização estimados.

A qualquer momento, os usuários podem abrir o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente as atualizações de políticas.

### <a name="assign-an-ingraceperiod-status"></a>Atribuir um status de InGracePeriod

O status InGracePeriod para uma política de conformidade é um valor. Esse valor é determinado pela combinação do período de cortesia do dispositivo e status real de um dispositivo para essa política de conformidade.

Especificamente, se um dispositivo tem um status NonCompliant para uma política de conformidade atribuída, e:

- Não há um período de cortesia atribuído ao dispositivo, de modo que o valor atribuído à política de conformidade é NonCompliant
- O dispositivo tem um período de cortesia que expirou, de modo que o valor atribuído à política de conformidade é NonCompliant
- O dispositivo tem um período de cortesia no futuro, de modo que o valor atribuído à política de conformidade é InGracePeriod

A tabela a seguir resume estes pontos:

|Status de conformidade real|Valor do período de carência atribuído|Status de conformidade efetiva|
|---------|---------|---------|
|NonCompliant |Nenhum período de carência atribuído |NonCompliant |
|NonCompliant |Data no passado|NonCompliant|
|NonCompliant |Data no futuro|InGracePeriod|

Para obter mais informações sobre como monitorar políticas de conformidade de dispositivo, consulte [Monitorar políticas de conformidade de dispositivo do Intune](compliance-policy-monitor.md).

### <a name="assign-a-resulting-compliance-policy-status"></a>Atribuir um status de política de conformidade resultante

Se um dispositivo tiver várias políticas de conformidade e diferentes status de conformidade para duas ou mais das políticas de conformidade atribuídas, um único status de conformidade resultante será atribuído. Essa atribuição é baseada em um nível de gravidade conceitual atribuído a cada status de conformidade. Cada status de conformidade tem o seguinte nível de gravidade:

|Status  |Gravidade  |
|---------|---------|
|Unknown     |1|
|NotApplicable     |2|
|Em Conformidade|3|
|InGracePeriod|4|
|NonCompliant|5|
|Erro do|6|

Quando um dispositivo tem várias políticas de conformidade, o mais alto nível de gravidade de todas as políticas é atribuído a esse dispositivo.

Por exemplo, um dispositivo tem três políticas de conformidade atribuídas a ele: um status Unknown (Desconhecido, gravidade = 1), um status Compliant (Em Conformidade, gravidade = 3) e um status InGracePeriod (Período de tolerância, gravidade = 4). O status InGracePeriod tem o nível mais alto de gravidade. Portanto, todas as três políticas têm o status de conformidade InGracePeriod.

## <a name="next-steps"></a>Próximas etapas

[Monitorar suas políticas](compliance-policy-monitor.md).