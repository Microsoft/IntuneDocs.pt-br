---
title: "Conformidade do dispositivo | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: use este tópico para saber mais sobre a conformidade do dispositivo no Microsoft Intune"
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
translationtype: Human Translation
ms.sourcegitcommit: 7693d49e2f0fa6e4aa40b6bb71433a7eaab8dd15
ms.openlocfilehash: a4254503e4e6b86079f862966dee2727934f1ee6


---

# <a name="what-is-device-compliance-in-intune-azure-preview"></a>O que é a conformidade de dispositivo na versão prévia do Intune Azure?


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Para ajudar a proteger dados da empresa, você precisa garantir que os dispositivos usados para acessar dados e aplicativos da empresa estejam em conformidade com determinadas regras. Essas regras podem incluir o uso de um PIN para acessar os dispositivos e criptografar dados armazenados em dispositivos. Chamamos um conjunto dessas regras de **política de conformidade**.

##  <a name="how-should-i-use-a-device-compliance-policy"></a>Como devo usar uma política de conformidade do dispositivo?
Você pode usar políticas de conformidade com políticas de acesso condicional para permitir que somente dispositivos que estão em conformidade com as regras de política de conformidade acessem o email e outros serviços.

Você também pode usar uma política de conformidade independentemente do acesso condicional.
Quando você usa as políticas de conformidade de forma independente, os dispositivos de destino são avaliados e relatados com o status de conformidade. Por exemplo, você pode querer obter um relatório do número de dispositivos que não estão criptografados ou quais dispositivos estão com jailbreak ou com raiz. No entanto, quando você usa as políticas de conformidade de forma independente, não há restrições de acesso aos recursos da empresa em vigor.

Você pode implantar uma política de conformidade para usuários. Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade. Para saber quanto tempo levará para que dispositivos móveis obtenham uma política após a política ser implantada, consulte Gerenciar configurações e recursos em seus dispositivos.

##  <a name="concepts"></a>Conceitos
Veja a seguir alguns termos e conceitos que são úteis para entender como usar políticas de conformidade.

### <a name="compliance-requirements"></a>Requisitos de conformidade
Requisitos de conformidade são essencialmente regras como exigir um PIN do dispositivo ou especificar o que é necessário ou não para uma política de conformidade de criptografia.

<!---### Actions for noncompliance

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

##  <a name="differences-between-the-classic-intune-admin-console-and-intune-in-the-azure-portal"></a>Diferenças entre o console de administração do Intune clássico e o Intune no Portal do Azure


Se você já usou o console de administração do Intune clássico anteriormente, observe as seguintes diferenças para ajudar na transição para o novo fluxo de trabalho de conformidade do dispositivo no Portal do Azure:


-   No Portal do Azure, as políticas de conformidade são criadas separadamente para cada plataforma com suporte. No console de administração do Intune, uma política de conformidade era comum a todas as plataformas com suporte.


<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="next-steps"></a>Próximas etapas

[Introdução às políticas de conformidade](get-started-with-device-compliance.md)


<!---### See also

Conditional access--->



<!--HONumber=Feb17_HO1-->


