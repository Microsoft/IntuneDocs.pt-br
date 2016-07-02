---
title: Registrar dispositivos de propriedade corporativa | Microsoft Intune
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 69cf07aa0747448e0ef3384b5b5132e0e76aed45
ms.openlocfilehash: e07053b9b26afacc03e45f2cb104eda6088a1e05


---

# Registrar dispositivos corporativos com o Microsoft Intune
Organização ou COD (dispositivos de propriedade corporativa) podem ser colocados no gerenciamento do Intune de várias formas, dependendo do dispositivo, como ele foi adquirido e as necessidades da organização.

## Dispositivos iOS corporativos
Esses métodos de registro são bons para cenários CYOD ("Escolha seu próprio dispositivo") em que a organização adquire os dispositivos para usuários, mas deseja manter o gerenciamento do dispositivo. Se a sua organização tiver adquirido dispositivos iOS, você poderá pré-configurar o registro para que o dispositivo seja gerenciado desde a primeira vez que o usuário o ativar. O Intune dá suporte ao registro via [DEP (programa de registro de dispositivo) da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou usando a ferramenta Apple Configurator em execução em um computador Mac para registro [direto](ios-direct-enrollment-in-microsoft-intune.md) ou [Assistente de Configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Registrar dispositivos iOS corporativos](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Gerenciador de registro de dispositivos
As organizações podem usar o Intune para gerenciar grandes números de dispositivos móveis com uma única conta de usuário chamada de uma conta de gerenciador de registro do dispositivo. Depois de criar uma conta de Gerenciador de registro do dispositivo, essa conta poderá ser usada por um gerente para registrar mais de cinco dispositivos padrão permitidos por padrão para usuários normais. O registro de dispositivos com um Gerenciador de registro do dispositivo funciona somente para dispositivos que não são usados por um usuário específico. Esses dispositivos são bons para aplicativos de ponto de venda ou utilitários, por exemplo, mas ruins para usuários que precisam acessar os recursos da empresa ou email.

[Registrar dispositivos corporativos com o gerenciador de registro de dispositivo](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## IMEI (Identidade de equipamentos móveis internacional)
IMEI (identidade de equipamentos móveis internacional) exclusivo são uma propriedade de dispositivo de comum para muitos fabricantes de dispositivos móveis. Os administradores do Intune podem importar números IMEI para os dispositivos da empresa. Quando o dispositivo se torna gerenciado pelo Intune, ele pode ser marcado como um dispositivo corporativo e receber a política apropriada.

[Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md)



<!--HONumber=Jun16_HO5-->


