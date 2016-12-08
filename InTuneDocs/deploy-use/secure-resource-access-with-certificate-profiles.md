---
title: Perfis de certificado para o acesso a recursos | Microsoft Intune
description: "Proteja o acesso ao email, Wi-Fi e VPN com um certificado instalado em cada dispositivo do usuário."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/23/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 35d08100b4332cc63667a401143c17972225a908
ms.openlocfilehash: b64260fd44e5c3fd0fb80e0dab4d75bd5c4eb305


---

# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a>Proteger o acesso a recursos com perfis de certificado no Microsoft Intune
Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode proteger o acesso usando um certificado instalado em cada dispositivo de usuário. Assim é como funciona:

1. Verifique se você tem a infraestrutura de certificado correta, conforme descrito em [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md) e [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md).

2. Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação. Para fazer isso, crie e implante um **Perfil de Certificado Confiável**. Quando você implanta esse perfil, os dispositivos que você gerencia com o Intune solicitarão e receberão o certificado raiz. Você precisa criar um perfil separado para cada plataforma. O **Perfil de Certificado Confiável** está disponível para estas plataformas:
 -  iOS 8.0 e posterior
 -  Mac OS X 10.9 e posterior
 -  Android 4.0 e posterior
 -  Android for Work
 -  Windows 8.1 e posterior
 -  Windows Phone 8.1 e posterior

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

3. Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email, conforme descrito em [Configurar perfis de certificado do Intune](configure-intune-certificate-profiles.md). Você pode criar e implantar um **Perfil de Certificado PKCS #12 (.PFX)** *ou* um **Perfil de Certificado SCEP** para dispositivos em execução nestas plataformas:

  -  iOS 8.0 e posterior
  -  Android 4.0 e posterior
  -  Android for Work
  -  Windows 10 (Desktop e Mobile) e posterior

  Use um **Perfil de Certificado SCEP** para dispositivos executados nestas plataformas:
    -   Mac OS X 10.9 e posterior
    -   Windows Phone 8.1 

Você deve criar um perfil separado para cada plataforma. Ao criar o perfil, você o associa ao **Perfil de Certificado Raiz Confiável** que já criou.

> [!NOTE]           
> - Se não tiver uma Autoridade de Certificação Corporativa, você precisará criar uma.
>- Com base em suas plataformas de dispositivo, se decidir usar o perfil de SCEP (Protocolo de Registro de Certificado Simplificado), você também precisará configurar um NDES (Serviço de Registro de Dispositivo de Rede).
>-  Se planeja usar perfis SCEP ou .PFX, você precisa baixar e configurar o Conector de Certificado do Microsoft Intune.
>-  Saiba como configurar todos os serviços necessários em [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md) ou [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md).

### <a name="next-steps"></a>Próximas etapas
- [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md)
- [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md)
- [Configurar perfis de certificado do Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Nov16_HO4-->


