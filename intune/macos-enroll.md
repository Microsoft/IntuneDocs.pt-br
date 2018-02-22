---
title: Registrar dispositivos macOS no Intune
titlesuffix: Azure portal
description: Saiba como registrar dispositivos macOS no Intune.
keywords: 
author: ErikjeMS
ms.author: erikje
nmanager: dougeby
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f896ebd51f989c0e441043d320247946cdb8997b
ms.sourcegitcommit: 9bd6278d129fa29f184b2d850138f8f65f3674ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2018
---
# <a name="enroll-macos-devices-in-intune"></a>Registrar dispositivos macOS no Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O Intune permite que você gerencie dispositivos macOS. Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos acessando o [site do Portal da Empresa](http://portal.manage.microsoft.com) e seguir as instruções. Quando os dispositivos macOS estiverem sob gerenciamento, você pode [criar configurações personalizadas para dispositivos macOS](custom-settings-macos.md). Mais recursos serão disponibilizados em breve.

## <a name="prerequisites"></a>Pré-requisitos

Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:

- [Configurar domínios](custom-domain-name-configure.md)
- [Definir a Autoridade MDM](mdm-authority-set.md)
- [Criar grupos](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](company-portal-app.md)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a>Configurar registro do macOS

Por padrão, o Intune já está configurado para permitir o registro de dispositivos macOS.

Para bloquear o registro de dispositivos macOS, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Peça aos usuários finais que acessem o [site do Portal da Empresa](http://portal.manage.microsoft.com) e sigam os prompts para registrar seus dispositivos. Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](end-user-educate.md)
- [Como usar seu dispositivo macOS com o Intune](/intune-user-help/using-your-macos-device-with-intune)
