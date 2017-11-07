---
title: Escolha como registrar dispositivos Windows no Intune
titlesuffix: Azure portal
description: Saiba como configurar o registro de dispositivos Windows no Microsoft Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 307f4b8d5ba27ce8136569e0c58711f9b1364d93
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Registrar dispositivos iOS no Intune

O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads e de iPhones para permitir acesso ao email e aos aplicativos da empresa aos usuários.

Como administrador do Intune, você pode habilitar o registro para dispositivos iOS. Você pode permitir que os usuários registrem seus dispositivos pessoais, conhecido como o registro BYOD (traga seu próprio dispositivo). Você também pode habilitar o registro de dispositivos de propriedade da empresa.

## <a name="prerequisites-for-ios-enrollment"></a>Pré-requisitos para registro de iOS
Antes de habilitar dispositivos iOS, conclua as seguintes etapas:
- [Configure o Intune](setup-steps.md) – essas etapas configuram sua infraestrutura do Intune. Em especial, o registro de dispositivo exige que você [defina a autoridade MDM](mdm-authority-set.md).
- [Obtenha um Apple MDM Push Certificate](apple-mdm-push-certificate-get.md) –A Apple exige um certificado para habilitar o gerenciamento de dispositivos iOS e macOS.

## <a name="user-owned-ios-devices-byod"></a>BYOD (Dispositivos iOS de propriedade do usuário)

É possível permitir que os usuários registrem seus dispositivos pessoais para o gerenciamento do Intune, conhecidos como "traga seu próprio dispositivo" ou BYOD. Depois de concluir os pré-requisitos e receber licenças de usuários, eles poderão baixar o aplicativo Portal da Empresa do iOS na App Store e seguir as instruções de registro no aplicativo.

## <a name="company-owned-ios-devices"></a>Dispositivos iOS de propriedade da empresa
Para organizações que adquirem dispositivos para seus usuários, o Intune dá suporte aos seguintes métodos de registro de dispositivos iOS de propriedade da empresa:

- DEP (Programa de registro de dispositivos) da Apple
- Apple School Manager
- Registro do Assistente de Configuração do Apple Configurator
- Registro direto do Apple Configurator

Também é possível registrar dispositivos iOS de propriedade da empresa com uma conta do [gerenciador de registros de dispositivos](device-enrollment-manager-enroll.md).

## <a name="device-enrollment-program"></a>Programa de Registro do Dispositivo
As organizações podem comprar dispositivos iOS por meio do DEP (Programa de registro de dispositivos) da Apple. O DEP permite implantar um perfil de registro “over the air” para trazer dispositivos ao gerenciamento. Saiba mais sobre o [Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
O Apple School Manager é um programa de compra e de registro de dispositivo para escolas. Como o DEP, você pode implantar um perfil para registrar dispositivos no gerenciamento. Saiba mais sobre o [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Você pode registrar dispositivos iOS com o Apple Configurator em execução em um computador Mac. Para preparar os dispositivos, conecte-os via USB e instale um perfil de registro. Você pode registrar dispositivos com o Apple Configurator de duas maneiras:
- Registro do Assistente de Configuração – restaura o dispositivo para as configurações de fábrica, prepara-o para executar o Assistente de Configuração e instala as políticas da empresa para o novo usuário do dispositivo.
- Registro direto – não redefine o dispositivo para as configurações de fábrica e registra o dispositivo com uma política predefinida. Esse método é destinado a dispositivos sem afinidade de usuário.

Saiba mais sobre o [registro do Apple Configurator](apple-configurator-setup-assistant-enroll-ios.md).
