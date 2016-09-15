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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: a5f80058e004f119acc9a918123c897b72b71314
ms.openlocfilehash: ecc6834b18d7906633bf1a029f5d63a4432c4989


---
# Escolher como registrar dispositivos móveis

As respostas para esta série de perguntas ajudarão a determinar o melhor método de registro para os dispositivos gerenciados.

## **Como você gerenciará dispositivos dedicados corporativos?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune)<br>[Assistente de Configuração do iOS >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)<br>[Marca com IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.

  - **Marcar com número IMEI** - Importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Essa é a única maneira de identificar dispositivos Windows e Android dedicados ("de usuário único") como corporativos. Os dispositivos iOS que não serão registrados no programa de registro de dispositivos da Apple ou no Apple Configurator também podem ser marcados com um número IMEI. Após declarar previamente o dispositivo para que ele seja marcado como "corporativo", você pode distribuir dispositivos aos usuários. Os usuários podem registrar seus dispositivos como dispositivos dedicados instalando o Portal da Empresa para acessar recursos da empresa como email, aplicativos e dados.

  > [!div class="button"]
  [< Voltar](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO5-->


