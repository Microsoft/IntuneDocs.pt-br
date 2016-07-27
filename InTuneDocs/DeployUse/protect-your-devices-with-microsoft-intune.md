---
title: Proteger dispositivos | Microsoft Intune
description: "Conheça algumas das maneiras que o Intune pode ajudar a que proteger seus dispositivos contra acesso não autorizado e outras ameaças."
keywords: 
author: Robstackmsft
manager: arob98
ms.date: 07/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 53201c36e7a210c1c62d3ed3183093ed8e63dc53


---

# Proteger dispositivos com o Microsoft Intune
Depois de seus dispositivos serem gerenciados pelo Intune, é recomendável garantir que eles estejam protegidos contra acesso não autorizado e outras ameaças. Aqui estão alguns dos recursos do Intune que ajudam a atingir esses objetivos.

> [!TIP]
> Este tópico não contém todas as maneiras em que o Intune pode ajudar a proteger seus dispositivos. Por exemplo, você pode usar as políticas do Intune para definir muitas configurações de segurança para seus dispositivos como configurar senhas, configurações de criptografia e funcionalidades de hardware como o Bluetooth e a câmera do dispositivo. Consulte [Manage settings and features on your devices with Microsoft Intune (Gerenciar configurações e funcionalidades em seus dispositivos com o Microsoft Intune)](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) para saber mais sobre essas configurações.

## Redefinir senhas quando os usuários estão bloqueados de seus dispositivos
Como a primeira etapa na proteção dos dados da empresa em dispositivos móveis é exigir uma senha para usar o dispositivo, às vezes, você precisa [redefinir uma senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou ajudar um funcionário a fazê-lo, removendo a senha ou configurando uma senha temporária remotamente. Você também poderá [bloquear um dispositivo remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) se ele for perdido ou roubado.

## Adicionar uma camada adicional de proteção para dispositivos Windows
A [MFA (autenticação multifator)](protect-windows-devices-with-multi-factor-authentication.md) é uma maneira mais segura de autenticar os usuários de dispositivos Windows e Windows Phone na rede.  Com a MFA, os usuários precisam confirmar sua identidade além do nome de usuário e a senha, por meio de uma chamada telefônica ou mensagem de texto.

## Controlar as configurações do Microsoft Passport em dispositivos Windows
O Intune permite integrar-se ao [Microsoft Passport for Work](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md), que é um método de entrada alternativo para o Windows 10 e posterior que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual.

## Bypass do Bloqueio de Ativação em dispositivos iOS
O Bloqueio de Ativação é um recurso que ajuda a proteger os dispositivos dos usuários exigindo que a ID da Apple e a senha sejam inseridas antes do usuário poder apagar ou reativar o dispositivo. No entanto, isso pode causar problemas, por exemplo, se o usuário deixar a empresa sem remover o bloqueio. [Ignorar o Bloqueio de Ativação do iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) pode ajudar, removendo o bloqueio de dispositivos iOS supervisionado e permitindo que ele seja realocado ou apagado.

## Proteger computadores Windows gerenciados com o cliente Intune
O Intune continua a dar suporte às políticas de segurança para computadores Windows que não são registrados, mas que são gerenciados com o software cliente do computador Intune. Para descobrir como essas políticas podem ajudar a proteger seus computadores Windows, consulte [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Usar políticas para ajudar a proteger os computadores Windows que executam o software cliente do Intune).



<!--HONumber=Jul16_HO3-->


