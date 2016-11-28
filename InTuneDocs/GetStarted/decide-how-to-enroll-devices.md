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
ms.assetid: 178df739-d3b9-43cb-8440-c5c110b1276b
ms.reviewer: dagerrit
translationtype: Human Translation
ms.sourcegitcommit: 3a00f9cdfb137306a28b33f9d1acdb6bc108670f
ms.openlocfilehash: 02aed5f84340f7d64681e27f1e4312f7f927a6c1


---

# <a name="choose-how-to-enroll-mobile-devices"></a>Escolher como registrar dispositivos móveis

Registro de dispositivo móvel é o processo que traz smartphones, tablets e computadores para gerenciamento pelo Microsoft Intune. Como administrador, você precisa determinar a melhor maneira de registrar dispositivos com base no seguinte:

 -  Propriedade (pessoal versus propriedade da empresa)
 -  Uso (compartilhado versus pessoal)
 -  Plataforma (iOS, Android, Windows Phone, computador Windows ou computador Mac)

As respostas para as perguntas a seguir ajudam a determinar o melhor método de registro para os dispositivos gerenciados.

## <a name="do-employees-bring-their-own-devices-or-are-devices-provided-by-your-organization"></a>**Os funcionários trazem seus próprios dispositivos ou os dispositivos são fornecidos pela sua organização?**

  - **Dispositivos de usuários** – registro "BYOD" (Traga seu próprio dispositivo): os usuários podem instalar o aplicativo de Portal da Empresa do Intune em seu dispositivo e registrá-lo, obtendo acesso a recursos da empresa como email, aplicativos da empresa, dados da empresa e suporte.  

  - **Dispositivos da empresa**: COD (dispositivos da empresa) podem ser registrados de diversas maneiras, dependendo das necessidades da organização e dos tipos de dispositivos gerenciados.

> [!div class="button"]
[Registro de BYOD >](#what-byod-devices-can-your-users-enroll)   [Registro de COD >](#are-your-company-owned-devices-shared-or-do-they-have-dedicated-users)

## <a name="what-byod-devices-can-your-users-enroll"></a>**Quais dispositivos de BYOD seus usuários podem registrar?**

> [!div class="button"]
[Android](/intune/deploy-use/set-up-android-management-with-microsoft-intune) [iOS e Mac](/intune/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune) [Windows Mobile 10 e Windows Phone](/intune/deploy-use/set-up-windows-phone-management-with-microsoft-intune) [Computadores Windows](/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune)

## <a name="are-your-company-owned-devices-shared-or-do-they-have-dedicated-users"></a>**Seus dispositivos da empresa são compartilhados ou têm usuários dedicados?**

- **Dispositivos da empresa compartilhados**: esses dispositivos não tem um único usuário e geralmente não estão configurados para acessar email. Os exemplos incluem dispositivos de quiosque ou dispositivos orientados a tarefas que os usuários extraem de um pool, conforme necessário e depois retornam. Os métodos de registro recomendados dependem da plataforma dos dispositivos.

- **Usuários dedicados** - Dispositivos da empresa que são concedidos a usuários individuais precisam ser controlados como ativos da empresa, permitindo ainda aos usuários acessar email e dados como dispositivos pessoais. Os métodos de registro recomendados dependem da plataforma dos dispositivos.

> [!div class="button"]
[Compartilhado >](#what-operating-system-are-your-shared-devices-running)   [Dedicado >](#how-will-you-manage-dedicated-ios-devices)


## <a name="what-operating-system-are-your-shared-devices-running"></a>**Que sistema operacional seus dispositivos compartilhados estão executando?**

  > [!div class="button"]
  [Windows >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [Android >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune) [iOS >](#how-will-you-manage-shared-ios-devices)

## <a name="how-will-you-manage-shared-ios-devices"></a>**Como você gerenciará dispositivos iOS compartilhados?**

- **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele

- **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração. Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.

- **Gerenciador de Registro de Dispositivo** - O gerenciador de registro de dispositivo (DEM) do Intune permite que um gerente ou administrador registre vários dispositivos móveis com uma única conta de usuário. Esses dispositivos não podem ter afinidade de usuário (ou seja, usuários dedicados) e devem ser registrados instalando e entrando no aplicativo do Portal da Empresa.

  > [!div class="button"]
  [Registro do iOS DEP >](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Registro direto do iOS >](/intune/deploy-use/ios-direct-enrollment-in-microsoft-intune) [Registro de DEM >](/intune/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune).

## <a name="how-will-you-manage-dedicated-ios-devices"></a>**Como você gerenciará dispositivos iOS dedicados?**

Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:

- **DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro. Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.

- **Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac. Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo. Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.

- **Marcar com número IMEI** - Importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune. Os usuários podem registrar seus dispositivos como um dispositivos pessoal instalando o Portal da Empresa para acessar os recursos da empresa como email, aplicativos e dados.

  > [!div class="button"]
  [Marcar com IMEI >](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers) [iOS DEP](/intune/deploy-use/ios-device-enrollment-program-in-microsoft-intune) [Assistente de configuração do iOS](/intune/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune) [Marcar com IMEI](/intune/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)



<!--HONumber=Nov16_HO3-->


