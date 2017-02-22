---
title: "Registrar dispositivos macOS no Intune| Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: saiba como registrar dispositivos macOS na versão prévia do Intune Azure."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 1/3/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ba2affcdbcdfcd690d671c7b20f9d1e14a74f764
ms.openlocfilehash: 171175689adca027181f3da4d05222117de97e13


---

# <a name="enroll-macos-devices-in-intune-azure-preview"></a>Registrar dispositivos macOS na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Como administrador do Intune, você pode gerenciar dispositivos macOS. Por padrão, o Portal do Azure permite que os usuários registrem seus dispositivos macOS. Você só precisa dizer aos seus usuários para acessarem o [site do Portal da Empresa](http://portal.manage.microsoft.com) e registrar seu dispositivo macOS. 

## <a name="prerequisites"></a>Pré-requisitos

Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:

- [Configurar domínios](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-2)
- [Definir a Autoridade MDM](set-mdm-authority.md)
- [Criar grupos](https://docs.microsoft.com/intune/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [Configurar o Portal da Empresa](/intune-azure/manage-apps/company-portal-app.md)
- Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Obtenha um certificado push de MDM da Apple](get-an-apple-mdm-push-certificate.md)

## <a name="set-up-macos-enrollment"></a>Configurar registro do macOS

Por padrão, Intune já está configurado para permitir o registro de dispositivos macOS. 

Para ver a configuração para permitir ou bloquear o registro de dispositivos macOS, acesse a folha do Intune no Portal do Azure e escolha **Registro** > **Restrições de Registro**. 

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa

Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune/enduser/enroll-your-device-in-intune-macos). O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.

Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:

- [Recursos sobre a experiência do usuário final com o Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
- [Usando um dispositivo iOS ou macOS com o Intune](https://docs.microsoft.com/intune/enduser/using-your-ios-or-mac-os-x-device-with-intune)


<!--HONumber=Feb17_HO1-->


