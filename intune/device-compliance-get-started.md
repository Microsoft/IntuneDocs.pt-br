---
title: "Políticas de conformidade do dispositivo no Intune"
titleSuffix: Azure portal
description: "Use este tópico para saber mais sobre a conformidade do dispositivo no Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f4a9f70762c3d30a49a686bcf1cfa9de4851b6c
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2018
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Introdução às políticas de conformidade do dispositivo no Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>O que é a conformidade do dispositivo no Intune?

As políticas de conformidade do dispositivo no Intune definem as regras e as configurações às quais um dispositivo deve satisfazer para ser considerado em conformidade pelo Intune.

Essas regras incluem o seguinte:

- Uso de senha para acessar os dispositivos

- Criptografia

- Quer o dispositivo esteja desbloqueado ou com raiz

- Versão mínima do SO obrigatória

- Versão máxima do SO permitida

- Requer que o dispositivo esteja no nível de Defesa Contra Ameaças Móveis

Você também pode usar políticas de conformidade do dispositivo para monitorar o status de conformidade dos seus dispositivos.

### <a name="device-compliance-requirements"></a>Requisitos de conformidade do dispositivo

Requisitos de conformidade são essencialmente regras como exigir um PIN do dispositivo ou especificar o que é necessário ou não para uma política de conformidade de criptografia.

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

##  <a name="pre-requisites"></a>Pré-requisitos

Você precisa ter as seguintes assinaturas para usar as políticas de conformidade do dispositivo com o Intune:

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Plataformas com Suporte:

-   Android

-   iOS

-   macOS (versão prévia)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Os dispositivos devem ser registrados no Intune para relatar os status de conformidade.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>Como as políticas de conformidade do dispositivo no Intune funcionam com o Azure AD

Quando um dispositivo é registrado no Intune, ocorre o processo de registro no Azure AD, que atualiza os atributos do dispositivo com mais informações no Azure AD. Uma das principais informações do dispositivo é o status de conformidade do dispositivo, que é usado pelas políticas de acesso condicional para bloquear ou permitir o acesso ao email e a outros recursos corporativos.

- Saiba mais sobre [processo de registro do Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Maneiras de usar as políticas de conformidade do dispositivo

### <a name="with-conditional-access"></a>Com acesso condicional
Você pode usar uma política de conformidade com acesso condicional para permitir que somente dispositivos em conformidade com uma ou mais regras de política de conformidade do dispositivo acessem o email e outros recursos corporativos.

### <a name="without-conditional-access"></a>Sem acesso condicional
Você também pode usar as políticas de conformidade do dispositivo independentemente do acesso condicional. Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade. Por exemplo, você pode obter um relatório do número de dispositivos que não estão criptografados ou quais dispositivos estão desbloqueados ou com raiz. No entanto, quando você usa as políticas de conformidade de forma independente, não há restrições de acesso aos recursos da empresa em vigor.

Você pode implantar uma política de conformidade para usuários. Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade. Para saber quanto tempo leva para que dispositivos móveis obtenham uma política depois que ela é implantada, consulte [Solução de problemas de perfis de dispositivo no Microsoft Intune](device-profile-troubleshoot.md#how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned).

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Usando políticas de conformidade do dispositivo no portal clássico do Intune versus Portal do Azure

Observe as principais diferenças para ajudar você na transição para o novo fluxo de trabalho da política de conformidade do dispositivo no Portal do Azure.

- No Portal do Azure, as políticas de conformidade são criadas separadamente para cada plataforma com suporte.
- No portal clássico do Intune, uma política de conformidade do dispositivo era comum a todas as plataformas com suporte.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Migrar as políticas de conformidade do dispositivo do portal clássico do Intune para o Portal do Azure

As políticas de conformidade do dispositivo criadas no [portal clássico do Intune](https://manage.microsoft.com) não aparecerão no novo [Portal do Azure no Intune](https://portal.azure.com). No entanto, elas ainda serão destinadas aos usuários e poderão ser gerenciadas por meio do portal clássico do Intune.

Se desejar aproveitar os novos recursos relacionados à conformidade do dispositivo no Portal do Azure, você precisará criar novas políticas de conformidade do dispositivo no próprio Portal do Azure. Se você atribuir uma nova política de conformidade do dispositivo no Portal do Azure a um usuário ao qual uma política de conformidade do dispositivo também foi atribuída no portal clássico do Intune, as políticas de conformidade do dispositivo do Portal do Azure no Intune terão precedência em relação às criadas no portal clássico do Intune.

##  <a name="next-steps"></a>Próximas etapas

Crie uma política de conformidade do dispositivo para as seguintes plataformas:

- [Android](compliance-policy-create-android.md)
- [Android for Work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
