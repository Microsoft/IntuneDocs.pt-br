---
title: Autenticação multifator para o registro de dispositivo do Intune
description: Como exigir a autenticação multifator no Azure AD para registro de dispositivos.
keywords: ''
author: dougeby
ms.author: angrobe
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: ''
ms.service: ''
ms.technology: ''
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: e8572834aed14ee08b3ba3c74bc7504193397ef5
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2018
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
