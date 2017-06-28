---
title: "Escolher como registrar dispositivos móveis"
description: "Decidir como registrar dispositivos móveis no Intune respondendo algumas perguntas simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.translationtype: Human Translation
ms.sourcegitcommit: df3c42d8b52d1a01ddab82727e707639d5f77c16
ms.openlocfilehash: 8fe7b2bb58655374d3e92391cd0a37aeda3062d4
ms.contentlocale: pt-br
ms.lasthandoff: 06/08/2017


---
# <a name="choose-how-to-enroll-mobile-devices"></a>Escolher como registrar dispositivos móveis

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

As respostas para esta série de perguntas ajudarão a determinar o melhor método de registro para os dispositivos gerenciados.

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a>**Como você gerenciará dispositivos dedicados corporativos?**

  > [!div class="button"]
[iOS DEP >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
[Assistente de Configuração do iOS >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
[Marcar com IMEI >](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:

  - **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.

  - **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.

  - **Marcar com número IMEI** - Importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Essa é a única maneira de identificar dispositivos Windows e Android dedicados ("de usuário único") como corporativos. Os dispositivos iOS que não serão registrados no programa de registro de dispositivos da Apple ou no Apple Configurator também podem ser marcados com um número IMEI. Após declarar previamente o dispositivo para que ele seja marcado como "corporativo", você pode distribuir dispositivos aos usuários. Os usuários podem registrar seus dispositivos como dispositivos dedicados instalando o Portal da Empresa para acessar recursos da empresa como email, aplicativos e dados.

> [!div class="button"]
[< Voltar](choose-how-to-enroll-devices3.md)

