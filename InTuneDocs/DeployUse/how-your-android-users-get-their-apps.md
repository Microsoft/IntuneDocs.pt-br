---
title: "Como os usuários Android podem obter aplicativos | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33d1684-b1b5-44f7-9aac-c6d5186a5d7c
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d3bcf89636f9da8fd8bfa5cc52391742a9ce9f92
ms.openlocfilehash: 25571ce1b214c927f3dc2ea3968d00970621e474


---


# Como os usuários Android podem obter aplicativos
Use estas informações para entender como e onde os usuários finais obtêm os aplicativos que você distribui por meio do Microsoft Intune. 

**Aplicativos necessários** - Aplicativos que são exigidos pelo administrador e instalados no dispositivo com envolvimento mínimo do usuário, dependendo da plataforma.
 
- **Dispositivos Samsung Knox**: se você implantar um aplicativo necessário em dispositivos Samsung Knox, ele será instalado de modo automático e silencioso em seu dispositivo.
- **Nativo (dispositivos não Samsung Knox)**: se você implantar um aplicativo necessário em dispositivos não Samsung Knox, ele não será instalado de modo automático nos dispositivos dos usuários. Em vez disso, os usuários serão solicitados a instalar o aplicativo. Depois de aceitar as solicitações, o aplicativo é baixado e usuários recebem uma notificação indicando que eles precisam instalá-lo. 

**Aplicativos necessários** - Aplicativos fornecidos na lista do aplicativo do Portal da Empresa e que o usuário pode optar por instalar.

**Aplicativos gerenciados** - Aplicativos que podem ser gerenciados pelas políticas e que foram "encapsulados" pelo Intune ou foram compilados com o SDK (Software Development Kit) de MAM (Mobile Application Management) do Intune. Esses aplicativos podem ser gerenciados pelo Intune e é possível aplicar políticas de aplicativo a eles.

**Aplicativos não gerenciados** - Aplicativos que podem ser gerenciados por meio de políticas e que não foram encapsulados pelo Intune ou que não incorporam o SDK de MAM do Intune. Políticas de aplicativo que não podem ser aplicadas a esses aplicativos.

###Consulte também
[Adicionar aplicativos com o Microsoft Intune](/intune/deploy-use/add-apps)
[Como os usuários iOS podem obter aplicativos](how-your-ios-users-get-their-apps.md)
[Como os usuários Windows podem obter aplicativos](how-your-windows-users-get-their-apps.md)


<!--HONumber=Jul16_HO1-->


