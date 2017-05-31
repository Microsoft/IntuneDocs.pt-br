---
title: Registrar dispositivos macOS no Intune
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como registrar dispositivos macOS na versão prévia do Intune Azure."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: c10a28a51e9f6bed99a657cd940b00f3114e4588
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Registrar dispositivos macOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

O Intune permite que você gerencie dispositivos macOS. Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos acessando o [site do Portal da Empresa](http://portal.manage.microsoft.com) e seguir as instruções. Quando os dispositivos macOS estiverem sob gerenciamento, você pode [criar configurações personalizadas para dispositivos macOS](custom settings-macos.md). Mais recursos serão disponibilizados em breve.

## <a name="prerequisites"></a>Pré-requisitos

Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:

- [Configurar domínios](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Definir a Autoridade MDM](mdm-authority-set.md)
- [Criar grupos](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](company-portal-app.md)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>Configurar registro do macOS

Por padrão, o Intune já está configurado para permitir o registro de dispositivos macOS.

Para bloquear o registro de dispositivos macOS, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md#set-device-type-restrictions).

Para definir o número máximo de dispositivos que um usuário pode registrar, consulte [Definir restrições de limite de dispositivos](enrollment-restrictions-set.md#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Você precisará pedir aos usuários finais que acessem o [site do Portal da Empresa](http://portal.manage.microsoft.com) e sigam os prompts para registrar seus dispositivos. Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Usando um dispositivo iOS ou macOS com o Intune](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)

