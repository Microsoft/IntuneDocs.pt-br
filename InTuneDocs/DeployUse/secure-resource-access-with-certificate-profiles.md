---
title: Habilitar o acesso aos recursos da empresa usando perfis de certificado |Microsoft Intune
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 79617dd41e51402a73759da792f581028095a2f5
ms.openlocfilehash: 1d2e6676714daba76a9b54553b4ad1af23a0f880


---

# Proteger o acesso a recursos com perfis de certificado no Microsoft Intune
Quando você habilita o acesso aos recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você tem a opção de proteção de acesso com um certificado instalado em cada dispositivo do usuário. Assim é como funciona:

1. Verifique se você tem a infraestrutura de certificado correta em vigor, conforme descrito em [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md) ou [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md).

2. Instale um certificado raiz (ou o certificado de autoridade de certificação intermediário) em cada dispositivo para que o dispositivo reconheça a legitimidade de sua autoridade de certificação. Você pode fazer isso criando e implantando um **Perfil de Certificado Confiável**. Quando você implanta esse perfil, os dispositivos que você gerencia com o Intune solicitarão e receberão o certificado raiz. Você precisa criar um perfil separado para cada plataforma. O **Perfil de Certificado Confiável** está disponível para estas plataformas:
 -  iOS 7.1 e posterior
 -  Mac OS X 10.9 e posterior
 -  Android 4.0 e posterior
 -  Windows 8.1 e posterior
 -  Windows Phone 8.1 e posterior

3. Faça com que cada dispositivo solicite um certificado a ser usado para autenticação de email, VPN e acesso de Wi-Fi, conforme descrito em [Configurar perfis de certificado do Intune](configure-intune-certificate-profiles.md). Você pode criar e implantar um **Perfil de Certificado PKCS #12 (.PFX)** ou um **Perfil de Certificado SCEP** para dispositivos nestas plataformas:

-  Android 4.0 e posterior
-  iOS 7.1 e posterior
-  Windows 10 (Desktop e Mobile) e posterior

Use o **Perfil de Certificado SCEP**:
-   Mac OS X 10.9 e posterior
-   Windows Phone 8.1 e posterior

Você precisa criar um perfil separado para cada plataforma. Ao criar o perfil, você associa-o ao **perfil de Certificado Raiz Confiável** que já foi criado.

> [!NOTE]           
> -    Se você não tiver uma autoridade de certificação corporativa, você precisará criar uma.
>- Se você decidir, com base em suas plataformas de dispositivo, usar o perfil de SCEP (Protocolo de Registro de Certificado Simplificado), você também precisará configurar um NDES (Serviço de Registro de Dispositivo de Rede).
>-  Se você planeja usar o protocolo SCEP ou perfis .PFX, você precisa baixar e configurar o Conector de Certificado do Microsoft Intune.
> A configuração de tudo isso é descrita no tópico [Configurar a infraestrutura de certificado](configure-certificate-infrastructure.md).

### Próximas etapas
- [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md)
- [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md)
- [Configurar perfis de certificado do Intune](configure-intune-certificate-profiles.md)



<!--HONumber=Jul16_HO1-->


