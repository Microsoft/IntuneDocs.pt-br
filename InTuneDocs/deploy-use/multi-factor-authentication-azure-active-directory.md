---
title: "Autenticação multifator usando o Azure AD | Microsoft Docs"
description: "Como exigir a autenticação multifator no Azure AD para registro de dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
translationtype: Human Translation
ms.sourcegitcommit: 85462d6cb5e3dc6ce8e94fe8fd1bc1c1c2b6e4f3
ms.openlocfilehash: 6e20eca60886781ae884107a224245639c5f107c


---

# <a name="multi-factor-authentication-for-microsoft-intune"></a>Autenticação multifator para o Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Intune integra a MFA (autenticação multifator do Azure AD) para registro de dispositivos para ajudá-lo a proteger seus recursos corporativos. A MFA requer fatores de autenticação, como autenticação de texto, além de nomes de usuário e senhas. Há suporte para dispositivos iOS, Android, Windows 8.1 ou posterior ou Windows Phone 8.1 ou posterior.

> [!NOTE]
>
> Esta é a nova experiência do MFA no Intune. A experiência mais antiga, da qual os clientes estão sendo migrados, é descrita em [Protect Windows devices with multi-factor authentication](protect-windows-devices-with-multi-factor-authentication.md) (Proteger dispositivos Windows com a autenticação multifator).
>
> Em versões mais antigas do Configuration Manager (anteriores à versão 1610), você ainda verá a configuração de MFA no console de administração do Configuration Manager. Não tente configurar a MFA no console de administração do Configuration Manager, pois ela não funcionará. Configure a MFA conforme descrito neste tópico.

### <a name="configuring-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Configurar o Intune para exigir a autenticação multifator no registro do dispositivo
Para exigir a MFA no registro do dispositivo, siga estas etapas:

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



<!--HONumber=Dec16_HO3-->


