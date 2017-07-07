---
title: Conformidade do dispositivo
titleSuffix: Intune on Azure
description: "Use este tópico para saber mais sobre a conformidade do dispositivo no Microsoft Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a747d577a28433635883ad6c4fe4c858e75902d0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="what-is-device-compliance-in-intune"></a>O que é a conformidade do dispositivo no Intune?

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As políticas de conformidade de dispositivo no Intune definem as regras e configurações às quais um dispositivo deve obedecer para ser considerado compatível pelas políticas de acesso condicional do EMS e do Intune. Você também pode usar as políticas de conformidade de dispositivo para monitorar e corrigir problemas de conformidade com dispositivos. 

Essas regras incluem o seguinte:

- Uso de senha para acessar os dispositivos
- Criptografia
- Quer o dispositivo esteja desbloqueado ou com raiz
- Versão mínima do SO obrigatória
- Versão máxima do SO permitida
- Requer que o dispositivo esteja no nível de Defesa Contra Ameaças Móveis

<!---##  Concepts
Following are some terms and concepts that are useful to understanding how to use compliance policies.

### Device compliance requirements
Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.

### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Como devo usar uma política de conformidade do dispositivo?

### <a name="using-ems-conditional-access"></a>Uso do acesso condicional do EMS
Você pode usar políticas de conformidade com o acesso condicional do EMS para permitir que somente dispositivos que estão em conformidade com uma ou mais regras de política de conformidade do dispositivo acessem o email e outros recursos corporativos.

### <a name="not-using-ems-conditional-access"></a>Não usar o acesso condicional do EMS
Você também pode usar políticas de conformidade independentemente do acesso condicional do EMS.
Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade. Por exemplo, você pode obter um relatório do número de dispositivos que não estão criptografados ou quais dispositivos estão desbloqueados ou com raiz. No entanto, quando você usa as políticas de conformidade de forma independente, não há restrições de acesso aos recursos da empresa em vigor.

Você pode implantar uma política de conformidade para usuários. Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade. Para saber quanto tempo levará para que dispositivos móveis obtenham uma política após a política ser implantada, consulte Gerenciar configurações e recursos em seus dispositivos.

##  <a name="intune-classic-admin-console-vs-intune-on-the-azure-portal"></a>Console de administração clássica do Intune vs. Intune no portal do Azure

Se você já usou o console de administração clássica do Intune, observe as seguintes diferenças para ajudar na transição para o novo fluxo de trabalho da política de conformidade do dispositivo no portal do Azure:

-   No Portal do Azure, as políticas de conformidade são criadas separadamente para cada plataforma com suporte. No console de administração do Intune, uma política de conformidade era comum a todas as plataformas com suporte.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migration-from-intune-classic-console-to-intune-on-the-azure-portal"></a>Migração do console clássico do Intune para o Intune no portal do Azure

As políticas de conformidade do dispositivo criadas no [Console clássico do Intune](https://manage.microsoft.com) não aparecerão no novo [Portal do Intune no Azure](https://portal.azure.com). No entanto, elas ainda serão destinadas aos usuários e poderão ser gerenciadas por meio do console clássico do Intune.

Se você quiser aproveitar os novos recursos relacionados à conformidade do dispositivo no Portal do Intune no Azure, será necessário criar novas políticas de conformidade do dispositivo no próprio Portal do Intune no Azure. Se você atribuir uma nova política de conformidade do dispositivo no Portal do Intune no Azure a um usuário que também recebeu uma política de conformidade do dispositivo no Portal clássico do Intune, as políticas de conformidade do dispositivo do Portal do Intune no Azure terão precedência sobre as criadas no Console clássico do Intune.

##  <a name="next-steps"></a>Próximas etapas

[Introdução às políticas de conformidade do dispositivo](device-compliance-get-started.md)


<!---### See also

Conditional access--->
