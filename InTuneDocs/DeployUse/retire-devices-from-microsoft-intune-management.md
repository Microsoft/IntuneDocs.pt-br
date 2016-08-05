---
title: Desativar dispositivos | Microsoft Intune
description: "O Intune dá suporte ao apagamento seletivo e ao apagamento completo para remover o dispositivo do gerenciamento do Intune removendo suas políticas e o portal da empresa."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e9cbf5858cc4e860b540f421b6d463b8e7a429cf
ms.openlocfilehash: 42b723f99c34f03060140e5f280b87287d108ae1


---

# Desativar dispositivos do gerenciamento do Intune

Quer os dispositivos sejam pessoais ou corporativos, chega o momento em que um dispositivo gerenciado precisa ser desativado no gerenciamento do Intune. A desativação de dispositivo é relativamente simples, basta você executar um apagamento seletivo ou completo.
## Apagar dados e aplicativos dos dispositivos
Tanto o apagamento seletivo quanto o apagamento completo removem o dispositivo do gerenciamento do Intune removendo sua política e o portal da empresa, o que significa que o dispositivo deixa de ter as credenciais necessárias para fazer logon em recursos da empresa, como o Microsoft SharePoint, o email ou o Office 365.

O [apagamento seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) é a ação preferencial para funcionários que tiverem registrado seus próprios dispositivos no Intune, porque ela não afeta as informações pessoais no dispositivo. Somente dados corporativos são removidos.

Para dispositivos corporativos, você também pode usar um [apagamento completo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), que redefine o dispositivo para as configurações de fábrica.

## Revogar o acesso à rede da empresa
No caso em que você estiver desativando um dispositivo porque um funcionário deixou a empresa e não devolveu equipamentos de propriedade da empresa, você também pode [bloquear remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) o dispositivo. Isso impede que as informações da empresa e do hardware sejam mal utilizadas, embora você possa perder o dispositivo.

Você também deseja revogar a licença da conta de usuário Intune do funcionário. Isso libera a licença e você pode atribuí-la para uma nova conta de usuário.

## Desativar o hardware
Às vezes, é o próprio dispositivo que chegou ao fim da vida útil. Nesses casos, [redefini-lo para as configurações de fábrica](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) com um apagamento completo remove todos os dados e o dispositivo do Intune. Em seguida, você pode se desfazer do hardware de acordo com a política da empresa.

### Consulte também
[Ajudar a proteger os dados com apagamento completo ou seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)



<!--HONumber=Jul16_HO4-->


