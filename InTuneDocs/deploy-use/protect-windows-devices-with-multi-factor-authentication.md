---
title: "Autenticação multifator para Windows | Microsoft Docs"
description: "O Intune integra o MFA (Multi-factor Authentication) para ajudar você a proteger seus recursos corporativos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b4f197d-bc10-4bee-91c9-19bcc8287d36
ms.reviewer: vinaybha
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e7d1760a10e63233fe7cc7f6fd57a68c5283647c
ms.openlocfilehash: cc60ffb2cd7a1d0cad141712ba7e2341954b1f02


---

# <a name="protect-windows-devices-with-multi-factor-authentication"></a>Protect Windows devices with multi-factor authentication

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune integra a MFA (autenticação multifator) para ajudar você a proteger seus recursos corporativos. A MFA requer fatores de autenticação, como autenticação de texto, além de nomes de usuário e senhas. O Intune dá suporte ao uso de MFA durante o registro de dispositivos Windows 8.1 ou posterior, Windows Phone 8.1 ou posterior ou Windows 10 Desktop ou Mobile.

>[!NOTE]
>
>A MFA pode ser necessária por usuário ou por grupo no servidor de ADFS.  


## <a name="on-premises-infrastructure-requirements-for-adfs-mfa"></a>Requisitos de infraestrutura local para MFA do ADFS
Para configurar a autenticação multifator, você precisará de:

-   Registro automático, conforme descrito em [Configurar o gerenciamento do dispositivo Windows](set-up-windows-device-management-with-microsoft-intune.md).
-   **Um domínio do Active Directory no qual o servidor ADFS foi ingressado.**

-   **Servidor ADFS (Serviços de Federação do Active Directory), configurado para MFA.** Um servidor executando o Windows Server 2012 R2 e configurado como um servidor ADFS. Para obter mais informações, consulte [Secure cloud and on-premises resources using Azure Multi-Factor Authentication Server with Windows Server 2012 R2 AD FS](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-adfs-w2k12/) (Proteger recursos locais e da nuvem usando o Servidor Azure Multi-Factor Authentication com o Windows Server 2012 R2 AD FS)

Os servidores devem atender aos requisitos de sistema em [Requisitos do sistema e informações de instalação do Windows Server 2012 R2](http://technet.microsoft.com/library/dn303418.aspx).

 


#### <a name="mfa-with-intune"></a>MFA com o Intune
Se sua organização tem uma infraestrutura de TI local que inclui um domínio do Active Directory com ADFS (Serviços de Federação do Active Directory), você pode configurar a MFA no servidor de federação e habilitá-la para registro no Intune. Com a configuração da MFA no Intune, os usuários podem se autenticar uma vez, durante o registro, e acessar recursos corporativos sem repetir o processo de MFA a cada vez.

>[!NOTE]
>
>A MFA pode ser necessária por usuário ou por grupo no servidor de ADFS.  

#### <a name="mfa-without-intune"></a>MFA sem Intune
Se você configurar a MFA no servidor de federação, mas não habilitá-la para registro no Intune, os usuários precisarão usar a MFA sempre que acessarem os recursos corporativos (e não somente no registro do dispositivo).

Você também pode usar a MFA do Azure AD (Azure Active Directory) para exigir a MFA sempre que os usuários acessarem os recursos corporativos, por usuário. A MFA do Azure AD é um serviço de nuvem que não requer nenhuma infraestrutura de TI local. Para saber como configurar a MFA do Azure AD, consulte [Introdução ao Servidor Azure Multi-Factor Authentication na nuvem](https://azure.microsoft.com/en-us/documentation/articles/multi-factor-authentication-get-started-cloud/).

## <a name="requiring-adfs-mfa-during-enrollment-of-windows-devices"></a>Exigir MFA do ADFS durante o registro de dispositivos Windows
Para obter informações sobre como habilitar a MFA no ADFS, consulte [Gerenciar riscos com autenticação multifator adicional para aplicativos confidenciais](http://technet.microsoft.com/library/dn280949.aspx).

## <a name="set-up-device-enrollment-mfa-in-intune"></a>Configurar a MFA de registro de dispositivo no Intune
>[!Important]  
>Habilite a MFA em seu ambiente de locatário ou local do AD do Azure antes de exigir a MFA para o registro de dispositivos Windows no Intune. Se você não fizer isso, os usuários que tentarem registrar seus dispositivos Windows ou tentarem ingressar seus dispositivos no Azure AD receberão uma mensagem de erro quando o registro automático durante o Ingresso no Azure AD estiver configurado.

1.  No console de administração do Intune, escolha **Administração** &gt; **Gerenciamento de dispositivo móvel** &gt; **Multi-factor Authentication**.

2.  Escolha **Configurar Multi-factor Authentication** e **Habilitar Multi-factor Authentication**.



<!--HONumber=Dec16_HO5-->


