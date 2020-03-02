---
title: Criar políticas de conformidade do dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Criar políticas de conformidade do dispositivo, visão geral do status e dos níveis de gravidade, usar o status de InGracePeriod, trabalhar com Acesso Condicional, lidar com dispositivos sem uma política atribuída e as diferenças de conformidade no Portal do Azure e no portal clássico no Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: samyada
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 68fcdb66591ec0e566aa702b3ca4d6c5c5448859
ms.sourcegitcommit: c780e9988341a20f94fdeb8672bd13e0b302da93
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77514006"
---
# <a name="create-a-compliance-policy-in-microsoft-intune"></a>Criar uma política de conformidade no Microsoft Intune

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

  - Administrador do dispositivo Android
  - Android Enterprise
  - iOS
  - macOS
  - Windows 10
  - Windows 8.1
  - Windows Phone 8.1

- Inscrever dispositivos no Intune (obrigatório para ver o status de conformidade)

- Inscrever dispositivos para um usuário, ou inscrever sem um usuário primário. Não há suporte para dispositivos registrados para vários usuários.

## <a name="create-the-policy"></a>Criar a política

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Selecione **Dispositivos** > **Políticas de conformidade** > **Criar Política**.

3. Especifique as seguintes propriedades:

   - **Nome**: Insira um nome descritivo para a política. Nomeie suas políticas para que você possa identificá-las facilmente mais tarde. Por exemplo, um bom nome de política seria **Marcar dispositivos do iOS/iPadOS com jailbreak como fora de conformidade**.

   - **Descrição**: Insira uma descrição para a política. Essa configuração é opcional, mas recomendada.

   - **Plataforma**: Escolha a plataforma dos dispositivos. Suas opções:
     - **Administrador do dispositivo Android**
     - **Android Enterprise**
     - **iOS/iPadOS**
     - **macOS**
     - **Windows Phone 8.1**
     - **Windows 8.1 e posterior**
     - **Windows 10 e posterior**

     Para o *Android Enterprise*, você precisa selecionar um **Tipo de perfil**:
     - **Proprietário do dispositivo**
     - **Perfil de trabalho**

   - **Configurações**: Os artigos a seguir listam e descrevem as configurações de cada plataforma:
     - [Administrador do dispositivo Android](compliance-policy-create-android.md)
     - [Android Enterprise](compliance-policy-create-android-for-work.md)
     - [iOS/iPadOS](compliance-policy-create-ios.md)
     - [macOS](compliance-policy-create-mac-os.md)
     - [Windows Phone 8.1, Windows 8.1 e posteriores](compliance-policy-create-windows-8-1.md)
     - [Windows 10 e posterior](compliance-policy-create-windows.md)  

   - **Locais** *(administrador do dispositivo Android)* : Em sua política, você pode forçar conformidade pela localização do dispositivo. Escolha entre os locais existentes. Ainda não tem um local? [Usar locais (limite de rede)](use-network-locations.md) no Intune fornece alguma orientação.  

   - **Ações para não compatibilidade**: Para dispositivos que não atendem às suas políticas de conformidade, é possível adicionar uma sequência de ações a serem aplicadas automaticamente. Você pode alterar a agenda quando o dispositivo está marcado como não em conformidade, como após um dia. Você também pode configurar uma segunda ação que envia um email para o usuário quando o dispositivo não está em conformidade.

     [Adicionar ações a dispositivos que não estão em conformidade](actions-for-noncompliance.md) apresenta mais informações, incluindo como criar um email de notificação para seus usuários.

     Por exemplo, você está usando o recurso Locais e adiciona uma localização em uma política de conformidade. A ação padrão para não conformidade se aplica quando você seleciona pelo menos uma localização. Se o dispositivo não estiver conectado a locais selecionados, imediatamente será considerado que ele não está em conformidade. Você pode dar aos usuários um período de cortesia, como um dia.

   - **Escopo (Marcas)** : Marcas de escopo são uma ótima maneira de filtrar políticas para grupos específicos, como `US-NC IT Team` ou `JohnGlenn_ITDepartment`. Após adicionar as configurações, você também pode adicionar uma marca de escopo às políticas de conformidade. [Usar marcas de escopo para filtrar políticas](../fundamentals/scope-tags.md) é um recurso útil.

4. Quando terminar, selecione **OK** > **Criar** para salvar as alterações. A política é criada e exibida na lista. Em seguida, atribua a política a grupos.

## <a name="assign-the-policy"></a>Atribuir a política

Depois que uma política é criada, a próxima etapa é atribuir a política aos grupos:

1. Escolha uma política que você criou. As políticas existentes estão em **Dispositivos** > **Políticas de conformidade** > **Políticas**.

2. Selecione a *política* > **Atribuições**. Você pode incluir ou excluir grupos de segurança do Azure Active Directory (AD).

3. Escolha **Grupos selecionados** para ver os grupos de segurança do Azure AD. Escolha os grupos aos quais deseja aplicar essa política > Escolha **Salvar** para implantar a política.

Os usuários ou dispositivos direcionados pela sua política são avaliados em relação à conformidade durante o check-in com o Intune.

### <a name="evaluate-how-many-users-are-targeted"></a>Avaliar quantos usuários são afetados

Ao atribuir a política, também é possível **Avaliar** quantos usuários são afetados. Esse recurso calcula os usuários, não os dispositivos.

1. No Intune, selecione **Dispositivos** > **Políticas de conformidade** > **Políticas**.

2. Selecione uma *política* > **Atribuições** > **Avaliar**. Uma mensagem é exibida mostrando quantos usuários essa política afeta.

Se o botão **Avaliar** estiver desabilitado, verifique se a política foi atribuída a um ou mais grupos.

<!-- ## Actions for noncompliance

For devices that don't meet your compliance policies, you can add a sequence of actions to apply automatically. You can change the schedule when the device is marked non-compliant, such as after one day. You can also configure a second action that sends an email to the user when the device isn't compliant.

[Add actions for noncompliant devices](actions-for-noncompliance.md) provides more information, including creating a notification email to your users.

For example, you're using the Locations feature, and add a location in a compliance policy. The default action for noncompliance applies when you select at least one location. If the device isn't connected to the selected locations, it's immediately considered not compliant. You can give your users a grace period, such as one day.

## Scope tags

Scope tags are a great way to assign and filter policies to specific groups, such as Sales, HR, All US-NC employees, and so on. After you add the settings, you can also add a scope tag to your compliance policies. [Use scope tags to filter policies](../fundamentals/scope-tags.md) is a good resource.
-->

## <a name="refresh-cycle-times"></a>Tempos de ciclo de atualização

O Intune usa ciclos de atualização diferentes para verificar se há atualizações de políticas de conformidade. Se o dispositivo for recém-registrado, a frequência de execução do check-in será maior. Os [ciclos de atualização de política e perfil](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) descrevem os tempos de atualização estimados.

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

|Status  |Severidade  |
|---------|---------|
|Unknown     |1|
|NotApplicable     |2|
|compatível|3|
|InGracePeriod|4|
|NonCompliant|5|
|Erro do|6|

Quando um dispositivo tem várias políticas de conformidade, o mais alto nível de gravidade de todas as políticas é atribuído a esse dispositivo.

Por exemplo, um dispositivo tem três políticas de conformidade atribuídas a ele: um status Unknown (Desconhecido, gravidade = 1), um status Compliant (Em Conformidade, gravidade = 3) e um status InGracePeriod (Período de tolerância, gravidade = 4). O status InGracePeriod tem o nível mais alto de gravidade. Portanto, todas as três políticas têm o status de conformidade InGracePeriod.

## <a name="next-steps"></a>Próximas etapas

[Monitorar suas políticas](compliance-policy-monitor.md).
