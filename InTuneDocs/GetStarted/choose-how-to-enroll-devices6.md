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
ms.sourcegitcommit: f65bdbc7aa708b37a766275494e080436d9a5485
ms.openlocfilehash: 3e5c9ed2ba374172ea27b61a34f0746f582f0ebc


---
# Escolher como registrar dispositivos móveis

As respostas para esta série de perguntas ajudarão a determinar o melhor método de registro para os dispositivos gerenciados.

## **Como você gerenciará seus dispositivos iOS dedicados?**

  > [!div class="button"]
[iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistente de Configuração do iOS >](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marcação com IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.

  - **Marcar com número IMEI** - Importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Os usuários podem registrar seus dispositivos como um dispositivos pessoal instalando o Portal da Empresa para acessar os recursos da empresa como email, aplicativos e dados.

  > [!div class="button"]
  [< Voltar](choose-how-to-enroll-devices3.md)



<!--HONumber=Aug16_HO3-->


