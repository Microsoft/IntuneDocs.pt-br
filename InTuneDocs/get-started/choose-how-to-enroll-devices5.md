---
title: "Escolher como registrar dispositivos móveis | Microsoft Intune"
description: "Decidir como registrar dispositivos móveis no Intune respondendo algumas perguntas simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: 5581e80612286471b29d35f193fba5146f9ca90f


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Escolher como registrar dispositivos móveis

As respostas para esta série de perguntas ajudarão a determinar o melhor método de registro para os dispositivos gerenciados.


## <a name="how-will-you-manage-shared-ios-devices"></a>**Como você gerenciará dispositivos iOS compartilhados?**

  > [!div class="button"]
  [Registro no DEP para iOS >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
  > [!div class="button"]
  [Registro direto para iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune)
  > [!div class="button"]
  [Registro no DEM >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração. Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.

  - **Gerenciador de Registro de Dispositivo** - O gerenciador de registro de dispositivo (DEM) do Intune permite que um gerente ou administrador registre vários dispositivos móveis com uma única conta de usuário. Esses dispositivos não podem ter afinidade de usuário (ou seja, usuários dedicados) e devem ser registrados instalando e entrando no aplicativo do Portal da Empresa.

  > [!div class="button"]
  [< Voltar](choose-how-to-enroll-devices3.md)



<!--HONumber=Nov16_HO3-->

