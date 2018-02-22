---
title: Conector do Check Point SandBlast Mobile com o Intune
titlesuffix: Azure portal
description: "Integração do Check Point SandBlast com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: dougeby
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 09a8914be00b7af039257fe0759967b7f5a90c5e
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2018
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a>Conector da Defesa contra Ameaças Móveis do Check Point SandBlast com o Intune

É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Check Point SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune. O risco é avaliado com base na telemetria coletada dos dispositivos executando o aplicativo Check Point SandBlast Mobile.

Você pode configurar políticas de acesso condicional com base na avaliação de risco do Check Point SandBlast Mobile, habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos não compatíveis aos recursos corporativos com base em ameaças detectadas.

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a>Como o Intune e o Check Point SandBlast Mobile ajudam a proteger os recursos da empresa?

O aplicativo móvel do Check Point SandBlast Mobile para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível e envia os dados de telemetria ao serviço de nuvem do Check Point SandBlast para avaliar o risco causado por ameaças móveis ao dispositivo.

A política de conformidade do dispositivo do Intune inclui uma regra para Defesa contra Ameaças Móveis do Check Point SandBlast, que tem base na avaliação de risco do Check Point SandBlast. Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada. Se o dispositivo for considerado não compatível, o acesso dos usuários aos recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado. Os usuários também recebem diretrizes do aplicativo móvel do Check Point SandBlast para resolver o problema e recuperar o acesso aos recursos corporativos.

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Check Point MTD block when malicious apps are detected](./media/checkpoint-MTD-2.PNG)

**Access granted on remediation:**

![Check Point MTD access granted](./media/checkpoint-MTD-3.PNG)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Check Point MTD block network access through Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Access granted on remediation:**

![Check Point MTD Wi-Fi access granted](./media/checkpoint-MTD-5.PNG)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Check Point MTD block SharePoint Online access](./media/checkpoint-MTD-6.PNG)

**Access granted on remediation:**

![Check Point MTD SharePoint Online access granted](./media/checkpoint-MTD-7.PNG)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
    -   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

- [Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)

- [Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)
