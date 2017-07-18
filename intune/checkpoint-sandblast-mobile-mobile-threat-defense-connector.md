---
title: Conector do Check Point SandBlast Mobile com o Intune
titleSuffix: Intune on Azure
description: "Integração do Check Point SandBlast com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e722411e7eea11a604cdd2c6f7f818053d0ffbb0
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="e9bea-103">Conector da Defesa contra Ameaças Móveis do Check Point SandBlast com o Intune</span><span class="sxs-lookup"><span data-stu-id="e9bea-103">Check Point SandBlast Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="e9bea-104">É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Check Point SandBlast Mobile, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="e9bea-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Check Point SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="e9bea-105">O risco é avaliado com base na telemetria coletada dos dispositivos executando o aplicativo Check Point SandBlast Mobile.</span><span class="sxs-lookup"><span data-stu-id="e9bea-105">Risk is assessed based on telemetry collected from devices running the Check Point SandBlast Mobile app.</span></span>

<span data-ttu-id="e9bea-106">Você pode configurar políticas de acesso condicional com base na avaliação de risco do Check Point SandBlast Mobile habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos sem conformidade com recursos corporativos com base em ameaças detectadas.</span><span class="sxs-lookup"><span data-stu-id="e9bea-106">You can configure conditional access policies based on Check Point SandBlast Mobile risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a><span data-ttu-id="e9bea-107">Como o Intune e o Check Point SandBlast Mobile ajudam a proteger os recursos da empresa?</span><span class="sxs-lookup"><span data-stu-id="e9bea-107">How do Intune and Check Point SandBlast Mobile help protect your company resources?</span></span>

<span data-ttu-id="e9bea-108">O aplicativo móvel do Check Point SandBlast Mobile para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível e envia os dados de telemetria ao serviço de nuvem do Check Point SandBlast para avaliar o risco causado por ameaças móveis ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9bea-108">Check Point Sandblast Mobile app for Android and iOS captures file system, network stack, device and application telemetry where available, then sends the telemetry data to the Check Point SandBlast cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="e9bea-109">A política de conformidade do dispositivo do Intune inclui uma regra para Defesa contra Ameaças Móveis do Check Point SandBlast, que tem base na avaliação de risco do Check Point SandBlast.</span><span class="sxs-lookup"><span data-stu-id="e9bea-109">The Intune device compliance policy includes a rule for Check Point SandBlast Mobile Threat Defense, which is based on the Check Point SandBlast risk assessment.</span></span> <span data-ttu-id="e9bea-110">Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.</span><span class="sxs-lookup"><span data-stu-id="e9bea-110">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span> <span data-ttu-id="e9bea-111">Se o dispositivo for considerado fora de conformidade, o acesso dos usuários a recursos corporativos como o Exchange Online e o SharePoint Online será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="e9bea-111">If the device is found non-compliant, users are blocked access to corporate resources like Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="e9bea-112">Os usuários também recebem diretrizes do aplicativo móvel do Check Point SandBlast para resolver o problema e recuperar o acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="e9bea-112">Users also receive guidance from the Check Point SandBlast mobile app installed in their devices to resolve the issue and regain access to corporate resources.</span></span>

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

[Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

[Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

[Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)

[Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)
