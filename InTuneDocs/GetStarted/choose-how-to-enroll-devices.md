---
title: "Escolher como registrar dispositivos móveis | Microsoft Intune"
description: "Decidir como registrar dispositivos móveis no Intune respondendo algumas perguntas simples"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: c671610b9c56d8b92d126d9902cce9c8c689ed63
ms.openlocfilehash: aac4eee56ec7326b2ce466d19b580aa5f1388aea


---

# Escolher como registrar dispositivos móveis

As respostas para as perguntas a seguir ajudam a determinar o melhor método de registro para os dispositivos gerenciados.

## **Os funcionários trazem seus próprios dispositivos ou os dispositivos são fornecidos pela sua organização?**

  - **Dispositivos de usuários** – registro de "BYOD" (Traga seu próprio dispositivo)
  - **Dispositivos da empresa** – registro de COD

> [!div class="button"]
[Registro de BYOD >](#what-byod-devices-can-your-users-enroll)   [Registro de COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## **Quais dispositivos de BYOD seus usuários podem registrar?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS e Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows Mobile 10 e Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Computadores Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## **Seus dispositivos da empresa são compartilhados ou têm usuários dedicados?**

> [!div class="button"]
[Compartilhado >](#what-operating-system-are-your-shared-devices-running)   [Dedicado >](#how-will-you-manage-dedicated-ios-devices)


## **Que sistema operacional seus dispositivos compartilhados estão executando?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## **Como você gerenciará seus dispositivos iOS compartilhados?**

  > [!div class="button"]
  [Registro do iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Registro do iOS Direct >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [Registro de DEM >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração. Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.

  - **Gerenciador de Registro de Dispositivo** - O gerenciador de registro de dispositivo (DEM) do Intune permite que um gerente ou administrador registre vários dispositivos móveis com uma única conta de usuário. Esses dispositivos não podem ter afinidade de usuário (ou seja, usuários dedicados) e devem ser registrados instalando e entrando no aplicativo do Portal da Empresa.

## **Como você gerenciará seus dispositivos iOS dedicados?**

  > [!div class="button"]
  [Marcar com IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistente de configuração do iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marcar com IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.

  - **Marcar com número IMEI** - Importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Os usuários podem registrar seus dispositivos como um dispositivos pessoal instalando o Portal da Empresa para acessar os recursos da empresa como email, aplicativos e dados.



<!--HONumber=Aug16_HO1-->


