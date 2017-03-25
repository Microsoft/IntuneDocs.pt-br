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
translationtype: Human Translation
ms.sourcegitcommit: e76d66768ac58df25313e102b7f60d2bc7bbc59b
ms.openlocfilehash: 3ef80446889e40464aed39fc83d9777dbfcc4d11
ms.lasthandoff: 03/22/2017


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Registrar dispositivos macOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O Intune permite que você gerencie dispositivos macOS. Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos acessando o [site do Portal da Empresa](http://portal.manage.microsoft.com) e seguir as instruções. Quando os dispositivos macOS estiverem sob gerenciamento, você pode [criar configurações personalizadas para dispositivos macOS](https://docs.microsoft.com/intune-azure/configure-devices/custom-for-macos). Mais recursos serão disponibilizados em breve.

## <a name="prerequisites"></a>Pré-requisitos

Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:

- [Configurar domínios](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Definir a Autoridade MDM](set-mdm-authority.md)
- [Criar grupos](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](/intune-azure/manage-apps/company-portal-app.md)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Configurar registro do macOS

Por padrão, o Intune já está configurado para permitir o registro de dispositivos macOS.

Para bloquear o registro de dispositivos macOS, consulte [Definir restrições de tipo de dispositivo](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions).

Para definir o número máximo de dispositivos que um usuário pode registrar, consulte [Definir restrições de limite de dispositivos](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-limit-restrictions).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Você precisará pedir aos usuários finais que acessem o [site do Portal da Empresa](http://portal.manage.microsoft.com) e sigam os prompts para registrar seus dispositivos. Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/how-to-educate-your-end-users-about-microsoft-intune)
- [Usando um dispositivo iOS ou macOS com o Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)

