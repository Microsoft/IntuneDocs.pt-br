---
title: "Autenticação multifator para registro de dispositivo do Intune | Microsoft Docs"
description: "Como exigir a autenticação multifator no Azure AD para registro de dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 7768013a1cc764b6dfbf4b7d22be4f5cf95f50bf
ms.openlocfilehash: dba070ef76de8015b347e760b424a5e28ce6ddec
ms.lasthandoff: 02/18/2017


---

# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Autenticação multifator para registros de dispositivo do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune integra a MFA (autenticação multifator do Azure AD) para registro de dispositivos para ajudá-lo a proteger seus recursos corporativos.

A MFA funciona solicitando dois ou mais dos métodos de verificação a seguir: 

- Algo que você conhece (normalmente uma senha ou PIN).
- Algo que você tem (um dispositivo de confiança que não é facilmente duplicado, como um telefone).
- Algo que você é (biometria).

MFA tem suporte para dispositivos iOS, Android, Windows 8.1 ou posterior ou Windows Phone 8.1 ou posterior.

> [!NOTE]
> Em versões mais antigas do Configuration Manager (anteriores à versão 1610), você ainda verá a configuração de MFA no console de administração do Configuration Manager. Não tente configurar a MFA no console de administração do Configuration Manager, pois ela não funcionará. Configure a MFA conforme descrito neste tópico.

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Configurar o Intune para exigir a autenticação multifator no registro do dispositivo
Para exigir MFA quando um dispositivo é registrado, siga estas etapas:

1. Entre no [Portal do Microsoft Azure](https://manage.windowsazure.com) com suas credenciais de administrador.
2. Escolha seu locatário.
2. Escolha a guia **Aplicativos**. Você verá uma lista de serviços para os quais pode configurar recursos de segurança do Azure AD.
3. Escolha **Registro do Microsoft Intune**.
4. Escolha **Configurar**. 
5. Em **autenticação multifator e regras de acesso com base em localização**, você pode:
    
    -  Habilitar as regras de acesso
    -  Escolher se deseja aplicar as regras a todos os usuários ou a grupos de segurança específicos do Azure AD.
    -  Exigir a autenticação multifator para o registro de todos os dispositivos.
    -  Exigir a autenticação multifator para o registro quando o dispositivo não estiver no trabalho.
    -  Escolha **Bloquear o acesso a recursos corporativos** para impedir o registro de um dispositivo quando ele não estiver conectado à rede corporativa. 
4. Você também pode clicar no link para **definir/editar seu local de rede de trabalho**, a fim de configurar os requisitos de conectividade de rede para o registro do dispositivo.

> [!IMPORTANT]
> 
> Não configure **Regras de acesso com base em dispositivo** para o Registro do Microsoft Intune.

