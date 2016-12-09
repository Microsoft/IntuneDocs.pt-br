---
title: Proteger dispositivos | Microsoft Intune
description: "Conheça algumas das maneiras que o Intune pode ajudar a que proteger seus dispositivos contra acesso não autorizado e outras ameaças."
keywords: 
author: Robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 09/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6adfb7375f9747f64e7037164f48918789bd7ee0
ms.openlocfilehash: 235db7eb1036bfccd074fd83b4b59e75529a5e34


---

# <a name="protect-devices-with-microsoft-intune"></a>Proteger dispositivos com o Microsoft Intune

O Microsoft Intune oferece um conjunto completo de recursos para ajudá-lo a proteger dispositivos gerenciados e os dados armazenados nesses dispositivos. Leia este tópico para conhecer as noções básicas sobre esses recursos e saber como obter mais informações.

## <a name="general-ways-to-protect-all-devices"></a>Maneiras gerais para proteger todos os dispositivos

### <a name="device-configuration"></a>Configuração do dispositivo
As [políticas de configuração](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) do Intune o ajudam a proteger e configurar dispositivos controlando uma infinidade de recursos e configurações. Por exemplo:
- Você pode restringir o uso de recursos de hardware no dispositivo, como a câmera ou o Bluetooth.
- Você pode configurar aplicativos compatíveis e incompatíveis. Você será alertado se um aplicativo não compatível for instalado (e algumas plataformas podem realmente bloquear a instalação).

### <a name="reset-passcodes-when-users-are-locked-out-of-their-devices"></a>Redefinir senhas quando os usuários estão bloqueados de seus dispositivos
Como a primeira etapa na proteção dos dados da empresa em dispositivos móveis é exigir uma senha para usar o dispositivo, às vezes, você precisa [redefinir uma senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou ajudar um funcionário a fazê-lo, removendo a senha ou configurando uma senha temporária remotamente. Você também poderá [bloquear um dispositivo remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) se ele for perdido ou roubado.

### <a name="retire-devices-and-remove-data"></a>Desativar dispositivos e remover dados
Quando um dispositivo precisa ser [removido do gerenciamento do Intune](retire-devices-from-microsoft-intune-management.md) (por exemplo, um usuário sai ou o dispositivo é perdido ou roubado), é provável que você queira remover dados do dispositivo. O Intune fornece diversos métodos para garantir que os dados da empresa permaneçam seguros.

### <a name="require-devices-to-be-compliant"></a>Exigir que is dispositivos sejam compatíveis
O Intune tem [políticas de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) que permitem avaliar (e, em alguns casos, corrigir) dispositivos que não são compatíveis com as regras que você especifica. Por exemplo, você pode relatar dispositivos iOS que são desbloqueados, se os dispositivos são criptografados ou se dispositivos Windows 10 são relatados como íntegros pelo Serviço de Atestado de Integridade.

### <a name="protect-apps-and-the-data-they-use"></a>Proteger aplicativos e os dados que eles usam
O Intune oferece vários recursos para ajudá-lo a proteger seus dados e aplicativos. Por exemplo, políticas de MAM (gerenciamento de aplicativos móveis) podem impedir que seja feito backup dos dados de um aplicativo protegido, restringir as opções de copiar e colar em outros aplicativos, exigir um PIN para acessar um aplicativo e muito mais. Para obter mais detalhes sobre como proteger aplicativos, veja [Proteger aplicativos e dados com o Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md)

## <a name="further-capabilities-for-windows-devices"></a>Recursos adicionais para dispositivos Windows

### <a name="add-an-additional-layer-of-protection-to-windows-devices"></a>Adicionar uma camada adicional de proteção para dispositivos Windows
A [MFA (autenticação multifator)](protect-windows-devices-with-multi-factor-authentication.md) é uma maneira mais segura de autenticar os usuários de dispositivos Windows e Windows Phone na rede.  Com o MFA, os usuários precisam confirmar sua identidade além do nome de usuário e a senha, por meio de uma chamada telefônica ou mensagem de texto.

### <a name="control-windows-hello-for-business-settings-on-windows-devices"></a>Controlar configurações do Windows Hello para Empresas em dispositivos Windows
O Intune permite integrar-se ao [Windows Hello for Business](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (conhecido anteriormente como Microsoft Passport), que é um método de entrada alternativo para o Windows 10 e posterior que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual.

## <a name="further-capabilities-for-ios-devices"></a>Recursos adicionais para dispositivos iOS

### <a name="bypass-activation-lock-on-ios-devices"></a>Bypass do Bloqueio de Ativação em dispositivos iOS
O Bloqueio de Ativação é um recurso que ajuda a proteger os dispositivos dos usuários exigindo que a ID da Apple e a senha sejam inseridas antes do usuário poder apagar ou reativar o dispositivo. No entanto, isso pode causar problemas, por exemplo, se o usuário deixar a empresa sem remover o bloqueio. [Ignorar o Bloqueio de Ativação do iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) pode ajudar, removendo o bloqueio de dispositivos iOS supervisionado e permitindo que ele seja realocado ou apagado.



## <a name="protect-windows-pcs-managed-with-the-intune-client"></a>Proteger computadores Windows gerenciados com o cliente Intune
O Intune continua a dar suporte às políticas de segurança para computadores Windows que não são registrados, mas que são gerenciados com o software cliente do computador Intune. Para descobrir como essas políticas podem ajudar a proteger seus computadores Windows, consulte [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Usar políticas para ajudar a proteger os computadores Windows que executam o software cliente do Intune).



<!--HONumber=Dec16_HO2-->


