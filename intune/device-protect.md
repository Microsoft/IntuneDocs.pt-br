---
title: Proteger dispositivos com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Conheça algumas das maneiras que o Intune pode ajudar a que proteger seus dispositivos contra acesso não autorizado e outras ameaças.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ce2c5e51c7a902e7b132f78a216b9067690011b8
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61511178"
---
# <a name="protect-devices-with-microsoft-intune"></a>Proteger dispositivos com o Microsoft Intune

O Microsoft Intune ajuda a proteger os dispositivos gerenciados e os dados armazenados neles.

## <a name="device-configuration"></a>Configuração do dispositivo
As [políticas de configuração](device-profiles.md) do Intune ajudam a proteger e configurar dispositivos controlando uma infinidade de recursos e configurações. Por exemplo:
- Você pode restringir o uso de recursos de hardware no dispositivo, como a câmera ou o Bluetooth.
- Você pode configurar aplicativos compatíveis e incompatíveis. Você será alertado se um aplicativo sem conformidade for instalado (e algumas plataformas podem até bloquear a instalação).

## <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Redefinir senhas quando os usuários estão bloqueados de seus dispositivos
Como a primeira etapa na proteção dos dados da empresa em dispositivos móveis é exigir uma senha para usar o dispositivo, às vezes, você precisa [redefinir uma senha](device-passcode-reset.md) ou ajudar um funcionário a fazê-lo, removendo a senha ou configurando uma senha temporária remotamente. Você também poderá [bloquear um dispositivo remotamente](device-remote-lock.md) se ele for perdido ou roubado.

## <a name="retire-devices-and-remove-data"></a>Desativar dispositivos e remover dados
Quando um dispositivo precisar ser [removido do gerenciamento do Intune](devices-wipe.md) (por exemplo, quando um usuário sai ou quando o dispositivo é perdido ou roubado), é provável que você vá querer remover os dados dele. O Intune fornece diversos métodos para garantir que os dados da empresa permaneçam seguros.

## <a name="require-devices-to-be-compliant"></a>Exigir que is dispositivos sejam compatíveis
O Intune tem [políticas de conformidade do dispositivo](device-compliance-get-started.md) que permitem avaliar (e, em alguns casos, corrigir) dispositivos que não estejam em conformidade com as regras que você especifica. Por exemplo, você pode obter relatórios sobre:
- dispositivos iOS com jailbreak
- dispositivos criptografados ou não criptografados
- a integridade dos dispositivos com Windows 10 (conforme determinado pelo Serviço de Atestado de Integridade).

## <a name="protect-apps-and-the-data-they-use"></a>Proteger aplicativos e os dados que eles usam
O Intune oferece vários recursos para ajudá-lo a proteger seus dados e aplicativos. Por exemplo, as políticas MAM (gerenciamento do aplicativo móvel) podem:
- impedir que haja backup dos dados em um aplicativo protegido
- restringir os recursos de copiar e colar em outros aplicativos
- exigir um PIN para acessar um aplicativo Saiba mais em [Proteger aplicativos e dados com o Microsoft Intune](app-protection-policy.md)

## <a name="add-an-additional-layer-of-protection-to-devices"></a>Adicionar uma camada adicional de proteção aos dispositivos
O [MFA (autenticação multifator)](multi-factor-authentication.md) é uma maneira mais segura de autenticar os usuários de dispositivos na rede.  Com o MFA, os usuários precisam confirmar sua identidade além do nome de usuário e a senha, por meio de uma chamada telefônica ou mensagem de texto.

## <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Controlar configurações do Windows Hello para Empresas em dispositivos Windows
O Intune permite integrar-se ao [Windows Hello for Business](windows-hello.md), que é um método de entrada alternativo para o Windows 10 e posterior que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual.

## <a name="bypass-activation-lock-on-ios-devices"></a>Bypass do Bloqueio de Ativação em dispositivos iOS
O Bloqueio de Ativação é um recurso que ajuda a proteger os dispositivos dos usuários. O recurso exige que os usuários insiram seu ID e senha da Apple antes que qualquer pessoa possa apagar ou reativar o dispositivo. No entanto, este recurso pode causar problemas, por exemplo, se o usuário deixar a empresa sem remover o bloqueio. [Ignorar o Bloqueio de Ativação do iOS]( device-activation-lock-bypass.md) pode ajudar, removendo o bloqueio de dispositivos iOS supervisionado e permitindo que ele seja realocado ou apagado.

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre a [defesa contra ameaças móveis](mobile-threat-defense.md)


