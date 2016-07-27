---
title: Registrar dispositivos de propriedade corporativa | Microsoft Intune
description: "Traga CODs (dispositivos corporativos) para o gerenciamento de várias maneiras, dependendo do dispositivo, como ele foi comprado e das necessidades da organização."
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 07/20/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 26ac7d52c0ad3e37e517b60d448a94849c0f4b30
ms.openlocfilehash: 6cf620a96b39540c8b7ca618936af1367971bb8f


---

# Registrar dispositivos corporativos com o Microsoft Intune
Organização ou COD (dispositivos de propriedade corporativa) podem ser colocados no gerenciamento do Intune de várias formas, dependendo do dispositivo, como ele foi adquirido e as necessidades da organização.

## Dispositivos iOS corporativos
Esses métodos de registro são bons para cenários CYOD ("Escolha seu próprio dispositivo") em que a organização adquire os dispositivos para usuários, mas deseja manter o gerenciamento do dispositivo. Se a sua organização tiver adquirido dispositivos iOS, você poderá pré-configurar o registro para que o dispositivo seja gerenciado desde a primeira vez que o usuário o ativar. O Intune dá suporte ao registro via [DEP (programa de registro de dispositivo) da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou usando a ferramenta Apple Configurator em execução em um computador Mac para registro [direto](ios-direct-enrollment-in-microsoft-intune.md) ou [Assistente de Configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Registrar dispositivos iOS corporativos](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Gerenciador de registro de dispositivos
As organizações podem usar o Intune para gerenciar grandes números de dispositivos móveis com uma única conta de usuário chamada de uma conta de gerenciador de registro do dispositivo. Depois de criar uma conta de Gerenciador de registro do dispositivo, essa conta poderá ser usada por um gerente para registrar mais de cinco dispositivos padrão permitidos por padrão para usuários normais. O registro de dispositivos com um Gerenciador de registro do dispositivo funciona somente para dispositivos que não são usados por um usuário específico. Esses dispositivos são bons para aplicativos de ponto de venda ou utilitários, por exemplo, mas ruins para usuários que precisam acessar os recursos da empresa ou email.

[Registrar dispositivos corporativos com o gerenciador de registro de dispositivo](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Registrar desktops Windows 10 corporativos

Se sua organização tiver o AADP (Azure Active Directory Premium) ou o EMS (Enterprise Management Suite), você poderá [registrar o Windows 10 para a empresa](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) e ele será marcado automaticamente como “corporativo” quando os usuários adicionarem sua conta corporativa ou de estudante.

## Identificar dispositivos como corporativos

Os dispositivos corporativos são listados como **Corporativo** em **Propriedade** em listas de dispositivos. Os dispositivos podem ser identificados como corporativos das seguintes maneiras:

 - [Registrado com o DEM (Gerenciador de Registro de Dispositivos)](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)
 - Registrado com o [DEP (Programa de Registro de Dispositivo)](ios-device-enrollment-program-in-microsoft-intune.md) da Apple ou o [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md)
 - [Pré-declarar dispositivo com números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)
 - [Registro do Azure Active Directory/Enterprise Management Suite de dispositivos Windows 10](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview)

### IMEI (Identidade de equipamentos móveis internacional)

IMEI (identidade de equipamentos móveis internacional) exclusivo são uma propriedade de dispositivo de comum para muitos fabricantes de dispositivos móveis. Os administradores do Intune podem importar números IMEI para os dispositivos da empresa. Quando o dispositivo se torna gerenciado pelo Intune, ele é marcado como um dispositivo corporativo.

[Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jul16_HO3-->


