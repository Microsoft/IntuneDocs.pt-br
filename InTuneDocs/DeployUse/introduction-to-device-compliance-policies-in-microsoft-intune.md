---
title: "Políticas de conformidade do dispositivo | Microsoft Intune"
description: "Este tópico explica os conceitos necessários para entender o que são políticas de conformidade do dispositivo e como elas funcionam."
keywords: 
author: karthikaraman
manager: jeffgilb
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0775107a-6662-41c8-9404-be14bbb599f3
ms.reviewer: chrisgre
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c72c8e1a764af73ba4d421ca6637ee91ab7bca0a
ms.openlocfilehash: f34ff402ae1012a471219647e94bc1f5225a6f07


---

# Políticas de conformidade do dispositivo no Microsoft Intune
## O que é uma política de conformidade?
Para proteger os dados da empresa, você precisa certificar-se de que os dispositivos usados para acessar os aplicativos e os dados da empresa estão em conformidade com determinadas regras, como usar um PIN para acessar o dispositivo e a criptografia de dados armazenados no dispositivo. Um conjunto de tais regras é referido como uma política de conformidade.

## Como devo usar as políticas de conformidade?
Você pode usar políticas de conformidade com políticas de acesso condicional permitir somente o acesso a dispositivos que estão em conformidade com as regras de política de conformidade para acessar email ou outros serviços. Leia o artigo [Restringir o acesso ao email e serviços O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) para compreender como as duas políticas podem ser usadas juntas.

Você também pode usar políticas de conformidade independentemente do acesso condicional. Quando usadas de forma independente, os dispositivos de destino são avaliados e informados com o status de conformidade. Por exemplo, você talvez deseje um relatório sobre o número de dispositivos que não estão criptografados ou quais dispositivos estão com jailbreak ou com raiz. No entanto, quando usados de forma independente, não há restrições de acesso aos recursos da empresa em vigor.

Você pode implantar políticas de conformidade para usuários. Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade.

A tabela a seguir lista os tipos de dispositivos suportados pelas políticas de conformidade e como configurações não compatíveis são gerenciadas quando a política é usada com uma política de acesso condicional.

--------------

|Configuração de política| Windows 8.1 e posterior| Windows Phone 8.1 e posterior| iOS 6.0 e posterior|Android 4.0 e posterior<br/>Samsung KNOX padrão 4.0 e posterior|
|-----|----|----|----|
|**Configuração de senha ou PIN** |Corrigida|Corrigida|Corrigida|Em Quarentena|
|**Criptografia de dispositivo**|N/D|Corrigida|Corrigida (pela definição do PIN)|Em Quarentena|
|**Dispositivo desbloqueado ou modificado**|N/D|N/D|Em Quarentena (não é uma configuração)|Em Quarentena (não é uma configuração)|
|**Perfil de email**|N/D|N/D|Em Quarentena|N/D|
|**Versão mínima do SO**|Em Quarentena|Em Quarentena|Em Quarentena|Em Quarentena|
|**Versão máxima do SO**|Em Quarentena| Em Quarentena| Em Quarentena| Em Quarentena|
|**Atestado de integridade do Windows**|O Windows 10 e o Windows 10 Mobile são colocados em quarentena.<br /><br />A configuração não é aplicável ao Windows 8.1|N/D|N/D|N/D|
--------------
**Corrigida** = a conformidade é imposta pelo sistema operacional do dispositivo (por exemplo, o usuário será forçado a definir um PIN).  Nunca há um caso em que a configuração esteja incompatível.

**Em Quarentena** = o sistema operacional do dispositivo não impõe conformidade (por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo). Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:

-   O dispositivo será bloqueado se o usuário for afetado pela política de acesso condicional.

-   O portal da empresa notificará o usuário sobre quaisquer problemas de conformidade.

## Próximas etapas
[Criar uma política de conformidade do dispositivo](create-a-device-compliance-policy-in-microsoft-intune.md)

[Implantar e monitorar uma política de conformidade do dispositivo](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md)

### Consulte também
[Restringir o acesso ao email e aos serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


