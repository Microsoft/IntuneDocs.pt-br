---
title: Políticas de conformidade do dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Requisitos para usar políticas de conformidade do dispositivo, visão geral dos níveis de status e a gravidade, usando o status de InGracePeriod, trabalhando com acesso condicional, lidando com dispositivos sem uma política atribuída e as diferenças de conformidade no Portal do Azure e no portal clássico no Microsoft Intune
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 806df8077045a4ad81cb7e221bd053059461a2fd
ms.sourcegitcommit: 6f2f2fa70f4e47fa5ad2f3c536ba7116e1bd1d05
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55199397"
---
# <a name="get-started-with-device-compliance-policies-in-intune"></a>Introdução às políticas de conformidade do dispositivo no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Muitas soluções de MDM (gerenciamento de dispositivo móvel) ajudam a proteger dados organizacionais exigindo que os usuários e dispositivos atendam a alguns requisitos. No Intune, esse recurso é chamado de "políticas de conformidade". As políticas de conformidade definem as regras e configurações que os usuários e dispositivos devem cumprir para serem compatíveis. Quando são combinadas com o acesso condicional, os administradores podem bloquear usuários e dispositivos que não atendem às regras. Por exemplo, um administrador do Intune pode exigir:

- que os usuários finais usem uma senha para acessar dados organizacionais em dispositivos móveis

- que o dispositivo não esteja desbloqueado por jailbreak ou por rooting

- uma versão mínima ou máxima do sistema operacional no dispositivo

- o dispositivo esteja em um nível igual ou inferior ao nível da ameaça

Você também pode usar políticas de conformidade do dispositivo para monitorar o status de conformidade em seus dispositivos.

> [!IMPORTANT]
> O Intune segue o agendamento de check-in do dispositivo para todas as avaliações de conformidade no dispositivo. [Saiba mais sobre o agendamento de check-in do dispositivo](https://docs.microsoft.com/intune/device-profile-troubleshoot#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="prerequisites"></a>Pré-requisitos

Para usar as políticas de conformidade do dispositivo, não deixe de:

- Usar as seguintes assinaturas:

  - Intune
  - Azure AD (Active Directory) Premium

- Usar uma plataforma compatível:

  - Android
  - iOS
  - macOS (versão prévia)
  - Windows 8.1
  - Windows Phone 8.1
  - Windows 10

- Inscrever dispositivos no Intune para ver o status de conformidade

- Inscrever dispositivos para um usuário, ou inscrever sem um usuário primário. Não há suporte para dispositivos registrados para vários usuários.

## <a name="how-device-compliance-policies-work-with-azure-ad"></a>Como as políticas de conformidade do dispositivo funcionam com o Azure AD

Quando um dispositivo é registrado no Intune, o processo de registro do Azure AD é iniciado e atualiza os atributos do dispositivo no Azure AD. Uma informação essencial é o status de conformidade do dispositivo. Esse status de conformidade é usado pelas políticas de acesso condicional para bloquear ou permitir o acesso a email e outros recursos corporativos.

[Processo de registro do Azure AD](https://docs.microsoft.com/azure/active-directory/device-management-introduction) fornece mais informações.

## <a name="refresh-cycle-times"></a>Tempos de ciclo de atualização

Durante a verificação de conformidade, o Intune usa o mesmo ciclo de atualização como perfis de configuração. Em geral, os tempos são:

- iOS: A cada seis horas
- macOS: A cada seis horas
- Android: A cada oito horas
- Computadores com Windows 10 inscritos como dispositivos: A cada oito horas
- Windows Phone: A cada oito horas
- Windows 8.1: A cada oito horas

Uma verificação de conformidade ocorre com mais frequência imediatamente após o registro de um dispositivo.

### <a name="assign-an-ingraceperiod-status"></a>Atribuir um status de InGracePeriod

O status InGracePeriod para uma política de conformidade é um valor. Esse valor é determinado pela combinação do período de cortesia do dispositivo e status real de um dispositivo para essa política de conformidade.

Especificamente, se um dispositivo tem um status NonCompliant para uma política de conformidade atribuída, e:

- o dispositivo não tem nenhum período de cortesia atribuído, então o valor atribuído à política de conformidade é NonCompliant
- o dispositivo tem um período de cortesia que expirou, então o valor atribuído à política de conformidade é NonCompliant
- o dispositivo tem nenhum período de cortesia no futuro, então o valor atribuído à política de conformidade é InGracePeriod

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
|Compatível|3|
|InGracePeriod|4|
|NonCompliant|5|
|Erro do|6|

Quando um dispositivo tem várias políticas de conformidade, o mais alto nível de gravidade de todas as políticas é atribuído a esse dispositivo.

Por exemplo, digamos que um dispositivo tenha três políticas de conformidade atribuídas a ele: um status Desconhecido (gravidade = 1), um status Em Conformidade (gravidade = 3) e um status InGracePeriod (gravidade = 4). O status de InGracePeriod tem o mais alto nível de gravidade, portanto todas as três políticas têm o status de conformidade de InGracePeriod.

## <a name="ways-to-use-device-compliance-policies"></a>Maneiras de usar as políticas de conformidade do dispositivo

#### <a name="with-conditional-access"></a>Com acesso condicional
Para dispositivos que estão em conformidade com as regras da política, você pode conceder a eles acesso ao email e outros recursos corporativos. Se os dispositivos não estiverem em conformidade com as regras de política, eles não terão acesso aos recursos corporativos. Isso é acesso condicional.

#### <a name="without-conditional-access"></a>Sem acesso condicional
Você também pode usar políticas de conformidade do dispositivo sem qualquer acesso condicional. Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade. Por exemplo, você pode obter um relatório do número de dispositivos que não estão criptografados ou de quais dispositivos estão desbloqueados por jailbreak ou por rooting. Quando você usa políticas de conformidade sem acesso condicional, não há restrições de acesso aos recursos da empresa.

## <a name="ways-to-deploy-device-compliance-policies"></a>Maneiras de implantar políticas de conformidade do dispositivo
Você pode implantar a política de conformidade para usuários em grupos de usuários ou dispositivos em grupos de dispositivo. Quando uma política de conformidade é implantada para um usuário, a conformidade de todos os dispositivos do usuário é verificada. No Windows 10 versão 1803 e dispositivos mais recentes, recomendamos implantar em grupos de dispositivos *se* o usuário principal não registrou o dispositivo. Usar grupos de dispositivos neste cenário ajuda os relatórios de conformidade.

Um conjunto de configurações de política de conformidade interno (**Intune** > **Conformidade do dispositivo**) é avaliado em todos os dispositivos registrados no Intune. Entre elas estão:

- **Marcar dispositivos sem política de conformidade atribuída como**: Essa propriedade tem dois valores:

  - **Em conformidade**: o recurso de segurança está desativado
  - **Não em conformidade** (padrão): recurso de segurança ligado

  Se um dispositivo não tiver uma política de conformidade atribuída, ele será considerado como não estando em conformidade. Por padrão, os dispositivos são marcados como **Não está em conformidade**. Se você usa acesso condicional, recomendamos alterar a configuração para **Não em conformidade**. Se um usuário final não estiver em conformidade porque uma política não está atribuída, o Portal da Empresa mostrará `No compliance policies have been assigned`.

- **Detecção avançada de jailbreak**: Quando habilitada, essa configuração faz com que dispositivos iOS realizem check-in com o Intune com mais frequência. Habilitar essa propriedade usa serviços de localização do dispositivo e afeta o uso da bateria. Os dados de local do usuário não são armazenados pelo Intune.

  Habilitar essa configuração exige que os dispositivos:
  - Habilitem serviços de localização no nível do sistema operacional
  - Permitam que o Portal da Empresa use serviços de localização
  - Avaliem e relatem o status de jailbreak ao Intune pelo menos uma vez a cada 72 horas. Caso contrário, o dispositivo será marcado como não estando em conformidade. A avaliação é disparada com a abertura do aplicativo do Portal da Empresa ou a movimentação física do dispositivo para 500 metros de distância ou mais. Se o dispositivo não se mover 500 metros em 72 horas, o usuário precisará abrir o aplicativo Portal da Empresa para executar uma avaliação avançada de desbloqueio.

- **Período de validade do status de conformidade (dias)**: Insira o período que os dispositivos relatam o status de todas as políticas de conformidade recebidas. Dispositivos que não retornam o status dentro desse período são tratados como não estando em conformidade. O valor padrão é de 30 dias.

Todos os dispositivos têm uma **Política de Conformidade do Dispositivo Interna** (portal do Azure > Conformidade do dispositivo > Conformidade de política). Use essa política interna para monitorar essas configurações.

Para saber o tempo que leva para dispositivos móveis obterem uma política depois de a política ser implantada, consulte [Solução de problemas de perfis de dispositivo](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

Relatórios de conformidade são uma ótima maneira de verificar o status dos dispositivos. Consulte [Monitorar políticas de conformidade](compliance-policy-monitor.md) para obter as diretrizes.

### <a name="actions-for-noncompliance"></a>Ações de não conformidade
Você pode configurar uma sequência ordenada pelo tempo de ações que se aplicam a dispositivos que não atendem aos critérios da política de conformidade. Essas ações para não conformidade podem ser automatizadas, conforme descrito em [Automatizar ações para não conformidade](actions-for-noncompliance.md).

## <a name="azure-classic-portal-vs-azure-portal"></a>Portal Clássico do Azure vs. Portal do Azure

A principal diferença ao usar políticas de conformidade do dispositivo no Portal do Azure:

- No Portal do Azure, as políticas de conformidade são criadas separadamente para cada plataforma compatível
- No Portal Clássico do Azure, uma política de conformidade do dispositivo é comum a todas as plataformas compatíveis

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

## <a name="device-compliance-policies-in-the-classic-portal-and-azure-portal"></a>Políticas de conformidade do dispositivo no portal clássico e no Portal do Azure

Políticas de conformidade do dispositivo criadas no [portal clássico](https://manage.microsoft.com) não aparecem no [Portal do Azure](https://portal.azure.com). No entanto, elas ainda serão destinadas aos usuários e poderão ser gerenciadas usando o portal clássico.

Para usar os recursos relacionados à conformidade do dispositivo no Portal do Azure, você deve criar novas políticas de conformidade de dispositivo no Portal do Azure. Se você atribuir uma política de conformidade do dispositivo no Portal do Azure a um usuário que já tenha uma política de conformidade do dispositivo atribuída pelo portal clássico, as políticas de conformidade do dispositivo do Portal do Azure terão precedência em relação às criadas no portal clássico.

## <a name="next-steps"></a>Próximas etapas

- Crie uma política de conformidade do dispositivo para as seguintes plataformas:

  - [Android](compliance-policy-create-android.md)
  - [Perfil de trabalho Android](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows](compliance-policy-create-windows.md)

- Para obter informações sobre as entidades de política do Intune Data Warehouse, consulte [Referência para entidades de política](reports-ref-policy.md).
