---
title: "Conector da defesa contra ameaças móveis do Lookout"
description: "Proteja o acesso aos recursos da empresa com base no risco do dispositivo, rede e aplicativo com o conector de Defesa Contra Ameaças Móveis do Lookout e com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6ed808e3dd1db1bf58d4c0caa8cddccbc49c05f7
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c088d-103">Conector de Defesa Contra Ameaças Móveis do Lookout com o Intune</span><span class="sxs-lookup"><span data-stu-id="c088d-103">Lookout Mobile Threat Defense connector with Intune</span></span>
<a id="lookout-mobile-threat-defense-connector-with-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c088d-104">É possível controlar o acesso de dispositivos móveis a recursos corporativos com base na avaliação de risco realizada pelo Lookout, uma solução de Defesa contra Ameaças Móveis integrada ao Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="c088d-104">You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a Mobile Threat Defense solution integrated with Microsoft Intune.</span></span> <span data-ttu-id="c088d-105">O risco é avaliado com base na telemetria coletada dos dispositivos pelo serviço Lookout, incluindo:</span><span class="sxs-lookup"><span data-stu-id="c088d-105">Risk is assessed based on telemetry collected from devices by the Lookout service including:</span></span>
- <span data-ttu-id="c088d-106">Vulnerabilidades do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="c088d-106">Operating system vulnerabilities</span></span>
- <span data-ttu-id="c088d-107">Aplicativos mal-intencionados instalados</span><span class="sxs-lookup"><span data-stu-id="c088d-107">Malicious apps installed</span></span>
- <span data-ttu-id="c088d-108">Perfis de rede mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="c088d-108">Malicious network profiles</span></span>

<span data-ttu-id="c088d-109">É possível configurar políticas de acesso condicional com base na avaliação de risco do Lookout habilitada por meio das políticas de conformidade do Intune.</span><span class="sxs-lookup"><span data-stu-id="c088d-109">You can  configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies.</span></span> <span data-ttu-id="c088d-110">As configurações possibilitam permitir ou bloquear dispositivos fora de conformidade de acordo com as ameaças detectadas.</span><span class="sxs-lookup"><span data-stu-id="c088d-110">Settings let you allow or block non-compliant devices based on detected threats.</span></span>

## <span data-ttu-id="c088d-111">Como a Defesa contra Ameaças Móveis do Lookout e do Intune ajudam a proteger recursos da empresa?</span><span class="sxs-lookup"><span data-stu-id="c088d-111">How do Intune and Lookout Mobile Threat Defense help protect company resources?</span></span>
<a id="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources" class="xliff"></a>
<span data-ttu-id="c088d-112">O aplicativo móvel do Lookout, **Lookout for Work**, é instalado e executado em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="c088d-112">Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices.</span></span> <span data-ttu-id="c088d-113">Esse aplicativo captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Lookout para avaliar o risco do dispositivo a ameaças móveis.</span><span class="sxs-lookup"><span data-stu-id="c088d-113">This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats.</span></span> <span data-ttu-id="c088d-114">É possível alterar as classificações de nível de risco das ameaças no console do Lookout para atender às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="c088d-114">You can change risk level classifications for threats in the Lookout console to suit your requirements.</span></span>  

<span data-ttu-id="c088d-115">A política de conformidade no Intune inclui uma regra para a Defesa contra Ameaças Móveis do Lookout de acordo com a avaliação de risco do Lookout.</span><span class="sxs-lookup"><span data-stu-id="c088d-115">The compliance policy in Intune includes a rule for Lookout Mobile Threat Defense based on Lookout risk assessment.</span></span> <span data-ttu-id="c088d-116">Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.</span><span class="sxs-lookup"><span data-stu-id="c088d-116">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="c088d-117">Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online poderá ser bloqueado.</span><span class="sxs-lookup"><span data-stu-id="c088d-117">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online can blocked.</span></span> <span data-ttu-id="c088d-118">Os usuários nos dispositivos bloqueados recebem etapas para resolver o problema e obter o acesso novamente.</span><span class="sxs-lookup"><span data-stu-id="c088d-118">Users on blocked devices receive a steps to resolve the issue and regain access.</span></span> <span data-ttu-id="c088d-119">As diretrizes são iniciadas por meio do aplicativo Lookout for Work.</span><span class="sxs-lookup"><span data-stu-id="c088d-119">Guidance is launched from the Lookout for work app.</span></span>

## <span data-ttu-id="c088d-120">Plataformas com suporte:</span><span class="sxs-lookup"><span data-stu-id="c088d-120">Supported platforms:</span></span>
<a id="supported-platforms" class="xliff"></a>
<span data-ttu-id="c088d-121">Há suporte para as seguintes plataformas no Lookout quando registradas no Intune:</span><span class="sxs-lookup"><span data-stu-id="c088d-121">The following platforms are supported for Lookout when enrolled in Intune:</span></span>
* <span data-ttu-id="c088d-122">**Android 4.1 e posterior**</span><span class="sxs-lookup"><span data-stu-id="c088d-122">**Android 4.1 and later**</span></span>
* <span data-ttu-id="c088d-123">**iOS 8 e posterior** Para obter mais informações sobre o suporte a plataformas e idiomas, visite o [site do Lookout](https://personal.support.lookout.com/hc/articles/114094140253).</span><span class="sxs-lookup"><span data-stu-id="c088d-123">**iOS 8 and later** For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/articles/114094140253).</span></span>

## <span data-ttu-id="c088d-124">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="c088d-124">Prerequisites:</span></span>
<a id="prerequisites" class="xliff"></a>
* <span data-ttu-id="c088d-125">Assinatura do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c088d-125">Microsoft Intune subscription</span></span>
* <span data-ttu-id="c088d-126">Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="c088d-126">Azure Active Directory</span></span>
* <span data-ttu-id="c088d-127">Assinatura corporativa do Lookout Mobile Endpoint Security</span><span class="sxs-lookup"><span data-stu-id="c088d-127">Lookout Mobile Endpoint Security enterprise subscription</span></span>  

<span data-ttu-id="c088d-128">Para obter mais informações, consulte [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="c088d-128">For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)</span></span>

## <span data-ttu-id="c088d-129">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="c088d-129">Sample scenarios</span></span>
<a id="sample-scenarios" class="xliff"></a>
<span data-ttu-id="c088d-130">A seguir, temos alguns cenários comuns:</span><span class="sxs-lookup"><span data-stu-id="c088d-130">Following are some common scenarios:</span></span>

### <span data-ttu-id="c088d-131">Controlar o acesso com base em ameaças de aplicativos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="c088d-131">Control access based on threats from malicious apps</span></span>
<a id="control-access-based-on-threats-from-malicious-apps" class="xliff"></a>
<span data-ttu-id="c088d-132">Quando aplicativos mal-intencionados, como malware, são detectados nos dispositivos, é possível impedir que os dispositivos façam o seguinte até que a ameaça seja resolvida:</span><span class="sxs-lookup"><span data-stu-id="c088d-132">When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:</span></span>
* <span data-ttu-id="c088d-133">Conectar-se ao email corporativo</span><span class="sxs-lookup"><span data-stu-id="c088d-133">Connecting to corporate e-mail</span></span>
* <span data-ttu-id="c088d-134">Sincronizar arquivos corporativos com o aplicativo OneDrive for Work</span><span class="sxs-lookup"><span data-stu-id="c088d-134">Syncing corporate files with the OneDrive for Work app</span></span>
* <span data-ttu-id="c088d-135">Acessar aplicativos da empresa</span><span class="sxs-lookup"><span data-stu-id="c088d-135">Accessing company apps</span></span>

<span data-ttu-id="c088d-136">**Bloquear quando aplicativos mal-intencionados forem detectados:**
![diagrama que mostra a política de acesso condicional bloqueando o acesso quando for determinado que o dispositivo não está em conformidade devido à presença de aplicativos mal-intencionados no dispositivo](../media/mtp/malicious-apps-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="c088d-136">**Block when malicious apps are detected:**
![diagram showing conditional access policy blocking access when device is determined to be non-compliant due to malicious apps on the device](../media/mtp/malicious-apps-blocked.png)</span></span>

<span data-ttu-id="c088d-137">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="c088d-137">**Access granted on remediation:**</span></span>

![diagrama mostrando a política de acesso condicional concedendo acesso quando é determinado que o dispositivo é compatível após a correção](../media/mtp/malicious-apps-unblocked.png)

### <span data-ttu-id="c088d-139">Controlar o acesso com base em ameaças à rede</span><span class="sxs-lookup"><span data-stu-id="c088d-139">Control access based on threat to network</span></span>
<a id="control-access-based-on-threat-to-network" class="xliff"></a>
<span data-ttu-id="c088d-140">Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle e protege o acesso a redes Wi-Fi com base no risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c088d-140">Detect threats to your network such as Man-in-the-middle attacks and protect access to WiFi networks based on the device risk.</span></span>

<span data-ttu-id="c088d-141">**Bloquear o acesso à rede por meio de WiFi:**
![diagrama que mostra o acesso condicional bloqueando o acesso WiFi com base nas ameaças à rede](../media/mtp/network-wifi-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="c088d-141">**Block network access through WiFi:**
![diagram showing conditional access blocking WiFi access based on network threats](../media/mtp/network-wifi-blocked.png)</span></span>

<span data-ttu-id="c088d-142">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="c088d-142">**Access granted on remediation:**</span></span>

![diagrama mostrando o acesso condicional permitindo o acesso após a correção da ameaça](../media/mtp/network-wifi-unblocked.png)
### <span data-ttu-id="c088d-144">Controlar o acesso ao SharePoint Online com base em ameaças à rede</span><span class="sxs-lookup"><span data-stu-id="c088d-144">Control access to SharePoint Online based on threat to network</span></span>
<a id="control-access-to-sharepoint-online-based-on-threat-to-network" class="xliff"></a>

<span data-ttu-id="c088d-145">Detecta ameaças à sua rede, como ataques do tipo man-in-the-middle, e impede a sincronização de arquivos corporativos com base no risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c088d-145">Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="c088d-146">**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**</span><span class="sxs-lookup"><span data-stu-id="c088d-146">**Block SharePoint Online when network threats are detected:**</span></span>

![Diagrama mostrando o acesso condicional bloqueando o acesso do dispositivo ao SharePoint Online com base na detecção de ameaças](../media/mtp/network-spo-blocked.png)


<span data-ttu-id="c088d-148">**Concessão do acesso após a correção:**</span><span class="sxs-lookup"><span data-stu-id="c088d-148">**Access granted on remediation:**</span></span>

![Diagrama que mostra o acesso condicional permitindo o acesso após a correção da ameaça à rede](../media/mtp/network-spo-unblocked.png)

## <span data-ttu-id="c088d-150">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c088d-150">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="c088d-151">Veja as principais etapas que você precisa realizar para implementar esta solução:</span><span class="sxs-lookup"><span data-stu-id="c088d-151">Here are the main steps you must do to implement this solution:</span></span>
1.  [<span data-ttu-id="c088d-152">Configurar sua assinatura do Lookout</span><span class="sxs-lookup"><span data-stu-id="c088d-152">Set up your Lookout subscription</span></span>](setup-your-lookout-mtd-subscription.md)
2.  [<span data-ttu-id="c088d-153">Habilitar a Defesa contra Ameaças Móveis do Lookout no Intune</span><span class="sxs-lookup"><span data-stu-id="c088d-153">Enable Lookout Mobile Threat Defense in Intune</span></span>](enable-lookout-mtd-connection.md)
3.  [<span data-ttu-id="c088d-154">Configurar e implantar o aplicativo Defesa contra Ameaças Móveis do Lookout</span><span class="sxs-lookup"><span data-stu-id="c088d-154">Configure and deploy Lookout Mobile Threat Defense app</span></span>](configure-deploy-lookout-for-work-app.md)
4.  [<span data-ttu-id="c088d-155">Configurar política de conformidade de dispositivo do Lookout</span><span class="sxs-lookup"><span data-stu-id="c088d-155">Configure Lookout device compliance policy</span></span>](create-lookout-device-compliance-policy.md)
5.  [<span data-ttu-id="c088d-156">Solucionar problemas de integração da Defesa contra Ameaças Móveis do Lookout</span><span class="sxs-lookup"><span data-stu-id="c088d-156">Troubleshoot Lookout Mobile Threat Defense integration</span></span>](/intune-classic/troubleshoot/device-threat-protection-troubleshooting)
