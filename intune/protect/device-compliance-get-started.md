---
title: Políticas de conformidade do dispositivo no Microsoft Intune – Azure | Microsoft Docs
description: Introdução ao uso de políticas de conformidade do dispositivo, visão geral de status e níveis de gravidade, como usar o status "Em período de carência", como trabalhar com Acesso Condicional, como lidar com dispositivos sem uma política atribuída e as diferenças de conformidade entre o portal do Azure e o portal clássico do Microsoft Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/21/2019
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
ms.openlocfilehash: 967bf9937c71ff3ca7277f43fd969291eb5af6de
ms.sourcegitcommit: c2e62f1ebdf75599c8e544287123c602f0f15f2b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72749180"
---
# <a name="set-rules-on-devices-to-allow-access-to-resources-in-your-organization-using-intune"></a>Definir regras em dispositivos para permitir o acesso aos recursos em sua organização usando o Intune

Muitas soluções de MDM (gerenciamento de dispositivo móvel) ajudam a proteger dados organizacionais exigindo que os usuários e dispositivos atendam a alguns requisitos. No Intune, esse recurso é chamado de "políticas de conformidade". As políticas de conformidade definem as regras e configurações que os usuários e dispositivos devem cumprir para serem compatíveis. Quando são combinadas com o Acesso Condicional, os administradores podem bloquear usuários e dispositivos que não atendem às regras.

Por exemplo, um administrador do Intune pode exigir:

- que os usuários finais usem uma senha para acessar dados organizacionais em dispositivos móveis
- que o dispositivo não esteja desbloqueado por jailbreak ou por rooting
- uma versão mínima ou máxima do sistema operacional no dispositivo
- o dispositivo esteja em um nível igual ou inferior ao nível da ameaça

Você também pode usar esse recurso para monitorar o status de conformidade dos dispositivos em sua organização.

> [!IMPORTANT]
> O Intune segue o agendamento de check-in do dispositivo para todas as avaliações de conformidade no dispositivo. Os [ciclos de atualização de política e perfil](../configuration/device-profile-troubleshoot.md#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned) listam os tempos de atualização estimados.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

- When the device is first determined to be noncompliant, an email with noncompliant notification is sent to the user.

- 3 days after initial noncompliance state, a follow up reminder is sent to the user.

- 5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

- 7 days after initial noncompliance state, access to company resources is blocked. This requires that you have Conditional Access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement Conditional Access policies in addition to compliance policies in order for access to company resources to be blocked.--->

## <a name="device-compliance-policies-work-with-azure-ad"></a>As políticas de conformidade do dispositivo funcionam com o Azure AD

O Microsoft Intune usa o [Acesso Condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) do Azure Active Directory (abre outro site do docs) para ajudar a aplicar a conformidade. Quando um dispositivo é registrado no Intune, o processo de registro do Azure AD é iniciado e atualiza as informações do dispositivo no Azure AD. Uma informação essencial é o status de conformidade do dispositivo. Esse status de conformidade é usado pelas políticas de Acesso Condicional para bloquear ou permitir o acesso a email e outros recursos da organização.

- [O que é gerenciamento de dispositivo no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction) é um excelente recurso para saber por que e como os dispositivos são registrados no Azure AD.

- [Acesso Condicional](conditional-access.md) e [maneiras comuns de usar o Acesso Condicional](conditional-access-intune-common-ways-use.md) descrevem esse recurso com relação ao Microsoft Intune.

## <a name="ways-to-use-device-compliance-policies"></a>Maneiras de usar as políticas de conformidade do dispositivo

### <a name="with-conditional-access"></a>Com Acesso Condicional

Para dispositivos que estão em conformidade com as regras da política, você pode conceder a eles acesso ao email e outros recursos da organização. Se os dispositivos não estiverem em conformidade com as regras de política, eles não terão acesso aos recursos da organização. Isso é Acesso Condicional.

### <a name="without-conditional-access"></a>Sem Acesso Condicional

Você pode também usar políticas de conformidade do dispositivo sem qualquer Acesso Condicional. Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade. Por exemplo, você pode obter um relatório do número de dispositivos que não estão criptografados ou de quais dispositivos estão desbloqueados por jailbreak ou por rooting. Quando você usa políticas de conformidade sem Acesso Condicional, não há restrições de acesso aos recursos da empresa.

## <a name="ways-to-deploy-device-compliance-policies"></a>Maneiras de implantar políticas de conformidade do dispositivo

Você pode implantar a política de conformidade para usuários em grupos de usuários ou dispositivos em grupos de dispositivo. Quando uma política de conformidade é implantada para um usuário, a conformidade de todos os dispositivos do usuário é verificada. No Windows 10 versão 1803 e dispositivos mais recentes, recomendamos implantar em grupos de dispositivos *se* o usuário principal não registrou o dispositivo. Usar grupos de dispositivos neste cenário ajuda os relatórios de conformidade.

O Intune também inclui um conjunto de configurações de política de conformidade interna. As políticas internas a seguir são avaliadas em todos os dispositivos registrados no Intune:

- **Marcar dispositivos sem política de conformidade atribuída como**: Essa propriedade tem dois valores:

  - **Em conformidade** (*padrão*): recurso de segurança desativado
  - **Em não conformidade**: o recurso de segurança está ativado.

  Quando um dispositivo não tem uma política de conformidade atribuída, é considerado como dispositivo compatível por padrão. Se você usa Acesso Condicional com políticas de conformidade, recomendamos alterar a configuração padrão para **Em não conformidade**. Se um usuário final não estiver em conformidade por não ter uma política atribuída, o [Portal da Empresa](../apps/company-portal-app.md) mostrará `No compliance policies have been assigned`.

- **Detecção avançada de jailbreak**: Quando habilitada, essa configuração faz com que dispositivos iOS realizem check-in com o Intune com mais frequência. Habilitar essa propriedade usa serviços de localização do dispositivo e afeta o uso da bateria. Os dados de local do usuário não são armazenados pelo Intune.

  Habilitar essa configuração exige que os dispositivos:
  - Habilite os serviços de localização no nível do sistema operacional.
  - Permitam que o Portal da Empresa use serviços de localização.
  - Avaliem e relatem o status de jailbreak ao Intune pelo menos uma vez a cada 72 horas. Caso contrário, o dispositivo será marcado como não estando em conformidade. A avaliação é disparada com a abertura do aplicativo do Portal da Empresa ou a movimentação física do dispositivo para 500 metros de distância ou mais. Se o dispositivo não se mover 500 metros em 72 horas, o usuário precisará abrir o aplicativo Portal da Empresa para executar uma avaliação avançada de desbloqueio.

- **Período de validade do status de conformidade (dias)** : Insira o período que os dispositivos relatam o status de todas as políticas de conformidade recebidas. Dispositivos que não retornam o status dentro desse período são tratados como não estando em conformidade. O valor padrão é de 30 dias.

Você pode usar essas políticas internas para monitorar essas configurações. O Intune também [atualiza ou verifica se há atualizações](create-compliance-policy.md#refresh-cycle-times) em intervalos diferentes, dependendo da plataforma do dispositivo. [Perguntas, problemas e resoluções comuns com perfis e políticas de dispositivo no Microsoft Intune](../configuration/device-profile-troubleshoot.md) é um bom recurso.

Relatórios de conformidade são uma ótima maneira de verificar o status dos dispositivos. [Monitorar políticas de conformidade](compliance-policy-monitor.md) inclui algumas orientações.

## <a name="non-compliance-and-conditional-access-on-the-different-platforms"></a>Falta de conformidade e Acesso Condicional em diferentes plataformas

A tabela a seguir descreve como as configurações em não conformidade são gerenciadas quando uma política de conformidade é usada com uma política de Acesso Condicional.

---------------------------

|**Configuração de política**| **Plataforma** |
| --- | ----|
| **Configuração de senha ou PIN** | - **Android 4.0 e posterior**: Em Quarentena<br>- **Samsung Knox Standard 4.0 e posterior**: Em Quarentena<br>- **Android Enterprise**: Em Quarentena  <br>  <br>- **iOS 8.0 e posterior**: Corrigida<br>- **macOS 10.11 e posterior**: Corrigida  <br>  <br>- **Windows 8.1 e posterior**: Corrigida<br>- **Windows Phone 8.1 e posterior**: Corrigida|
| **Criptografia de dispositivo** | - **Android 4.0 e posterior**: Em Quarentena<br>- **Samsung Knox Standard 4.0 e posterior**: Em Quarentena<br>- **Android Enterprise**: Em Quarentena<br><br>- **iOS 8.0 e posterior**: Corrigida (pela definição do PIN)<br>- **macOS 10.11 e posterior**: Corrigida (pela definição do PIN)<br><br>- **Windows 8.1 e posterior**: Não Aplicável<br>- **Windows Phone 8.1 e posterior**: Corrigida |
| **Dispositivo desbloqueado ou com raiz** | - **Android 4.0 e posterior**: Em Quarentena (não é uma configuração)<br>- **Samsung Knox Standard 4.0 e posterior**: Em Quarentena (não é uma configuração)<br>- **Android Enterprise**: Em Quarentena (não é uma configuração)<br><br>- **iOS 8.0 e posterior**: Em Quarentena (não é uma configuração)<br>- **macOS 10.11 e posterior**: Não Aplicável<br><br>- **Windows 8.1 e posterior**: Não Aplicável<br>- **Windows Phone 8.1 e posterior**: Não Aplicável |
| **Perfil de email** | - **Android 4.0 e posterior**: Não Aplicável<br>- **Samsung Knox Standard 4.0 e posterior**: Não Aplicável<br>- **Android Enterprise**: Não Aplicável<br><br>- **iOS 8.0 e posterior**: Em Quarentena<br>- **macOS 10.11 e posterior**: Em Quarentena<br><br>- **Windows 8.1 e posterior**: Não Aplicável<br>- **Windows Phone 8.1 e posterior**: Não Aplicável |
| **Versão mínima do SO** | - **Android 4.0 e posterior**: Em Quarentena<br>- **Samsung Knox Standard 4.0 e posterior**: Em Quarentena<br>- **Android Enterprise**: Em Quarentena<br><br>- **iOS 8.0 e posterior**: Em Quarentena<br>- **macOS 10.11 e posterior**: Em Quarentena<br><br>- **Windows 8.1 e posterior**: Em Quarentena<br>- **Windows Phone 8.1 e posterior**: Em Quarentena |
| **Versão máxima do SO** | - **Android 4.0 e posterior**: Em Quarentena<br>- **Samsung Knox Standard 4.0 e posterior**: Em Quarentena<br>- **Android Enterprise**: Em Quarentena<br><br>- **iOS 8.0 e posterior**: Em Quarentena<br>- **macOS 10.11 e posterior**: Em Quarentena<br><br>- **Windows 8.1 e posterior**: Em Quarentena<br>- **Windows Phone 8.1 e posterior**: Em Quarentena |
| **Atestado de integridade do Windows** | - **Android 4.0 e posterior**: Não Aplicável<br>- **Samsung Knox Standard 4.0 e posterior**: Não Aplicável<br>- **Android Enterprise**: Não Aplicável<br><br>- **iOS 8.0 e posterior**: Não Aplicável<br>- **macOS 10.11 e posterior**: Não Aplicável<br><br>- **Windows 10 e Windows 10 Mobile**: Em Quarentena<br>- **Windows 8.1 e posterior**: Em Quarentena<br>- **Windows Phone 8.1 e posterior**: Não Aplicável |

---------------------------

**Corrigido**: o sistema operacional do dispositivo impõe a conformidade. Por exemplo, o usuário é forçado a definir um PIN.

**Em quarentena**: o sistema operacional do dispositivo não impõe a conformidade. Por exemplo, dispositivos com Android e Android Enterprise não forçam o usuário a criptografar o dispositivo. Quando o dispositivo não está em conformidade, ocorrem as seguintes ações:

- Quando uma política de Acesso Condicional se aplica ao usuário, o dispositivo é bloqueado.
- O aplicativo Portal da Empresa notifica o usuário sobre qualquer problema de conformidade.

## <a name="azure-classic-portal-vs-azure-portal"></a>Portal Clássico do Azure vs. Portal do Azure

A principal diferença ao usar políticas de conformidade do dispositivo no Portal do Azure:

- No Portal do Azure, as políticas de conformidade são criadas separadamente para cada plataforma compatível
- No Portal Clássico do Azure, uma política de conformidade do dispositivo é comum a todas as plataformas compatíveis

<!--- - In the Azure portal, you have the ability to specify actions and notifications that are initiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

- In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

Políticas de conformidade do dispositivo criadas no [portal clássico](https://manage.microsoft.com) não aparecem no [Portal do Azure](https://portal.azure.com). No entanto, elas ainda serão destinadas aos usuários e poderão ser gerenciadas usando o portal clássico.

Para usar os recursos relacionados à conformidade do dispositivo no Portal do Azure, você deve criar novas políticas de conformidade de dispositivo no Portal do Azure. Se você atribuir uma política de conformidade do dispositivo no Portal do Azure a um usuário que já tenha uma política de conformidade do dispositivo atribuída pelo portal clássico, as políticas de conformidade do dispositivo do Portal do Azure terão precedência em relação às criadas no portal clássico.

## <a name="next-steps"></a>Próximas etapas

- [Criar uma política](create-compliance-policy.md) e exibir os pré-requisitos.
- Confira as configurações de conformidade para as diferentes plataformas de dispositivos:

  - [Android](compliance-policy-create-android.md)
  - [Android Enterprise](compliance-policy-create-android-for-work.md)
  - [iOS](compliance-policy-create-ios.md)
  - [macOS](compliance-policy-create-mac-os.md)
  - [Windows Holographic for Business](compliance-policy-create-windows.md#windows-holographic-for-business)
  - [Windows Phone 8.1](compliance-policy-create-windows-8-1.md)
  - [Windows 8.1 e posterior](compliance-policy-create-windows-8-1.md)
  - [Windows 10 e posterior](compliance-policy-create-windows.md)

- [Referência para entidades de política](../reports-ref-policy.md) contém informações sobre as entidades de política do Intune Data Warehouse.
