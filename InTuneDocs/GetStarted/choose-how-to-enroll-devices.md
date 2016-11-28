---
title: "Escolher como registrar dispositivos móveis | Microsoft Intune"
description: "Decidir como registrar dispositivos móveis no Intune respondendo algumas perguntas simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cac62b64-3f8b-47ae-aa66-970c7ba15466
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: f15c9748b1c55ec46ddd0056445bf434fa323c59


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Escolher como registrar dispositivos móveis

As respostas para as perguntas a seguir ajudam a determinar o melhor método de registro para os dispositivos gerenciados.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Os funcionários trazem seus próprios dispositivos ou os dispositivos são fornecidos pela sua organização?**

  - **Dispositivos de usuários** – registro de "BYOD" (Traga seu próprio dispositivo)
  - **Dispositivos da empresa** – registro de COD

> [!div class="button"]
[Registro de BYOD >](#what-byod-devices-can-your-users-enroll)   
> [!div class="button"]
[Registro de COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Quais dispositivos de BYOD seus usuários podem registrar?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS e Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows Mobile 10 e Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Computadores Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Seus dispositivos da empresa são compartilhados ou têm usuários dedicados?**

> [!div class="button"]
[Compartilhado >](#what-operating-system-are-your-shared-devices-running)   [Dedicado >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Que sistema operacional seus dispositivos compartilhados estão executando?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Como você gerenciará dispositivos iOS compartilhados?**

  > [!div class="button"]
  [Registro do iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Registro do iOS Direct >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)  [Registro de DEM >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **DEP (Programa de Registro do Dispositivo) da Apple** – dispositivos iOS adquiridos ou gerenciados com o DEP podem ser associados a um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica para registrá-los, use a opção de registro do Assistente de Configuração. Se você não quiser redefinir os dispositivos para os padrões de fábrica, use a opção de registro Direto.

  - **Gerenciador de Registro de Dispositivo (Intune)** – o DEM (gerenciador de registro de dispositivo) do Intune permite que um gerente ou administrador registre vários dispositivos móveis com uma única conta de usuário. Esses dispositivos não podem ter usuários dedicados (afinidade do usuário) e devem ser registrados instalando e entrando no aplicativo de Portal da Empresa.

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Como você gerenciará dispositivos iOS dedicados?**

  > [!div class="button"]
   [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistente de Configuração do iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marcação com IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:

  - **DEP (Programa de Registro do Dispositivo) da Apple** – dispositivos iOS adquiridos ou gerenciados com o DEP podem ser associados a um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica para registrá-los, use a opção de registro do Assistente de Configuração.

  - **Marcar com número IMEI** – importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Os usuários podem registrar seus dispositivos como um dispositivos pessoal instalando o Portal da Empresa para acessar os recursos da empresa como email, aplicativos e dados.



<!--HONumber=Nov16_HO3-->


