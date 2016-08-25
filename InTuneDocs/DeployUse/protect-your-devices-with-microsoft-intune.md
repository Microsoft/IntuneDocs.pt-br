---
title: Proteger dispositivos | Microsoft Intune
description: "Conheça algumas das maneiras que o Intune pode ajudar a que proteger seus dispositivos contra acesso não autorizado e outras ameaças."
keywords: 
author: Robstackmsft
manager: angrobe
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c999a852b68762002ac94269e27ecbf46c8f9999
ms.openlocfilehash: 3318590eaedc6f0e96fb463dc016d5786eeb38fb


---

# Proteger dispositivos com o Microsoft Intune
Depois que seus dispositivos forem gerenciados pelo Intune, é recomendável garantir sua proteção contra o acesso não autorizado e outras ameaças. Aqui estão alguns dos recursos do Intune que ajudam a atingir esses objetivos.

> [!TIP]
> Este tópico não contém todas as maneiras pelas quais o Intune pode ajudar a proteger seus dispositivos. Por exemplo, você pode usar as políticas do Intune para definir várias configurações de segurança para seus dispositivos, como configurações de senhas e criptografia, além de recursos de hardware, como Bluetooth e a câmera do dispositivo. Consulte [Manage settings and features on your devices with Microsoft Intune (Gerenciar configurações e funcionalidades em seus dispositivos com o Microsoft Intune)](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) para saber mais sobre essas configurações.

## Redefinir senhas quando os usuários estão bloqueados de seus dispositivos
A primeira etapa na proteção de dados da empresa em dispositivos móveis é exigir uma senha para uso do dispositivo. Às vezes, você precisa [redefinir uma senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou ajudar um funcionário a fazê-lo, removendo a senha ou definindo uma senha temporária remotamente. Você também poderá [bloquear um dispositivo remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) se ele for perdido ou roubado.

## Adicionar uma camada adicional de proteção para dispositivos Windows
A [MFA (autenticação multifator)](protect-windows-devices-with-multi-factor-authentication.md) é uma maneira mais segura de autenticar os usuários de dispositivos Windows e Windows Phone na rede. Com o MFA, os usuários precisam confirmar sua identidade além do nome de usuário e a senha, por meio de uma chamada telefônica ou mensagem de texto.

## Controlar as configurações do Microsoft Passport em dispositivos Windows
O Intune se integra ao [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md). que é um método de entrada alternativo no Windows 10 e posterior. O Microsoft Passport for Work usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual.

## Bypass do Bloqueio de Ativação em dispositivos iOS
O Bloqueio de Ativação é um recurso que ajuda a proteger os dispositivos dos usuários, exigindo que a ID da Apple e a senha sejam inseridas antes que o usuário possa apagar ou reativar o dispositivo. No entanto, isso pode causar problemas, por exemplo, se o usuário deixar a empresa sem remover o bloqueio. [O bypass do Bloqueio de Ativação do iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) pode ajudar, removendo o bloqueio de dispositivos iOS supervisionados, para que eles possam ser realocados ou apagados.

## Proteger computadores Windows gerenciados com o cliente Intune
O Intune continua dando suporte às políticas de segurança para computadores Windows que não são registrados, mas que são gerenciados com o software cliente do computador do Intune. Para descobrir como essas políticas podem ajudar a proteger seus computadores Windows, consulte [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Usar políticas para ajudar a proteger os computadores Windows que executam o software cliente do Intune).



<!--HONumber=Aug16_HO2-->


