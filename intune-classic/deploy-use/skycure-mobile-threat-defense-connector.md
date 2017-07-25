---
title: "Conector da defesa contra ameaças móveis do Skycure"
description: "Proteja o acesso aos recursos da empresa com base no risco do dispositivo, da rede e do aplicativo usando o conector de Defesa contra Ameaças Móveis do Skycure e o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7a004e6c-604a-448c-bfb8-cfda63749f5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d0b401babf356e44479229c3bea27c956926a6f9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="eacfe-103">Conector de Defesa contra Ameaças Móveis do Skycure</span><span class="sxs-lookup"><span data-stu-id="eacfe-103">Skycure Mobile Threat Defense connector</span></span>
<a id="skycure-mobile-threat-defense-connector" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="eacfe-104">É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="eacfe-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="eacfe-105">O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:</span><span class="sxs-lookup"><span data-stu-id="eacfe-105">Risk is assessed based on telemetry collected from devices running Skycure, including:</span></span>

-   <span data-ttu-id="eacfe-106">Defesa física</span><span class="sxs-lookup"><span data-stu-id="eacfe-106">Physical defense</span></span>

-   <span data-ttu-id="eacfe-107">Defesa de rede</span><span class="sxs-lookup"><span data-stu-id="eacfe-107">Network defense</span></span>

-   <span data-ttu-id="eacfe-108">Defesa do aplicativo</span><span class="sxs-lookup"><span data-stu-id="eacfe-108">Application defense</span></span>

-   <span data-ttu-id="eacfe-109">Defesa de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="eacfe-109">Vulnerabilities defense</span></span>

<span data-ttu-id="eacfe-110">Você pode configurar políticas de acesso condicional com base na avaliação de risco do Skycure habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos com base em ameaças detectadas.</span><span class="sxs-lookup"><span data-stu-id="eacfe-110">You can configure conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <span data-ttu-id="eacfe-111">Como o Intune e o Skycure ajudam a proteger os recursos da empresa?</span><span class="sxs-lookup"><span data-stu-id="eacfe-111">How do Intune and Skycure help protect your company resources?</span></span>
<a id="how-do-intune-and-skycure-help-protect-your-company-resources" class="xliff"></a>

<span data-ttu-id="eacfe-112">O aplicativo móvel do Skycure para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Skycure para avaliar o risco do dispositivo a ameaças móveis.</span><span class="sxs-lookup"><span data-stu-id="eacfe-112">Skycure mobile app for Android or iOS captures file system, network stack, device and application telemetry where available, then sends it to the Skycure cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="eacfe-113">A política de conformidade do dispositivo do Intune inclui uma regra para defesa contra ameaças móveis do Skycure, que tem base na avaliação de risco do Skycure.</span><span class="sxs-lookup"><span data-stu-id="eacfe-113">The Intune device compliance policy includes a rule for Skycure mobile threat defense, which is based on the Skycure risk assessment.</span></span> <span data-ttu-id="eacfe-114">Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.</span><span class="sxs-lookup"><span data-stu-id="eacfe-114">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="eacfe-115">Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online serão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="eacfe-115">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online are blocked.</span></span> <span data-ttu-id="eacfe-116">Os usuários com dispositivos bloqueados recebem orientação do aplicativo móvel do Skycure para resolver o problema e recuperar o acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="eacfe-116">Users on blocked devices receive guidance from the Skycure mobile app to resolve the issue and regain access to corporate resources.</span></span>

<span data-ttu-id="eacfe-117">O Intune dá suporte a dois modos de integração com o Skycure:</span><span class="sxs-lookup"><span data-stu-id="eacfe-117">Intune supports two modes of integration with Skycure:</span></span>

-   <span data-ttu-id="eacfe-118">**Configuração básica**, que é um modo somente leitura que permite a visibilidade do Skycure para dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="eacfe-118">**Basic setup** which is a read only mode that allows Skycure visibility for devices in Intune.</span></span>

-   <span data-ttu-id="eacfe-119">**Integração total**, que permite ao Skycure relatar detalhes dos incidentes de risco e segurança do dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="eacfe-119">**Full integration** which allows Skycure to report device risk and security incident details to Intune.</span></span>

## <span data-ttu-id="eacfe-120">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="eacfe-120">Sample scenarios</span></span>
<a id="sample-scenarios" class="xliff"></a>

<span data-ttu-id="eacfe-121">Confira alguns cenários comuns:</span><span class="sxs-lookup"><span data-stu-id="eacfe-121">Here are some common scenarios:</span></span>

### <span data-ttu-id="eacfe-122">Controlar o acesso com base em ameaças de aplicativos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="eacfe-122">Control access based on threats from malicious apps</span></span>
<a id="control-access-based-on-threats-from-malicious-apps" class="xliff"></a>

<span data-ttu-id="eacfe-123">Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:</span><span class="sxs-lookup"><span data-stu-id="eacfe-123">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="eacfe-124">Conectar-se ao email corporativo</span><span class="sxs-lookup"><span data-stu-id="eacfe-124">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="eacfe-125">Sincronizar arquivos corporativos com o aplicativo OneDrive for Work</span><span class="sxs-lookup"><span data-stu-id="eacfe-125">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="eacfe-126">Acessar aplicativos da empresa</span><span class="sxs-lookup"><span data-stu-id="eacfe-126">Accessing company apps</span></span>

<span data-ttu-id="eacfe-127">**Bloquear quando aplicativos mal-intencionados forem detectados:**</span><span class="sxs-lookup"><span data-stu-id="eacfe-127">**Block when malicious apps are detected:**</span></span>

![Aplicativos mal-intencionados detectados](../media/mtp/skycure-arch-1.png)

<span data-ttu-id="eacfe-129">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="eacfe-129">**Access granted on remediation:**</span></span>

![Acesso concedido a aplicativos mal-intencionados detectado](../media/mtp/skycure-arch-2.png)

### <span data-ttu-id="eacfe-131">Controlar o acesso com base em ameaças à rede</span><span class="sxs-lookup"><span data-stu-id="eacfe-131">Control access based on threat to network</span></span>
<a id="control-access-based-on-threat-to-network" class="xliff"></a>

<span data-ttu-id="eacfe-132">Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eacfe-132">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="eacfe-133">**Bloquear o acesso à rede por meio de Wi-Fi:**</span><span class="sxs-lookup"><span data-stu-id="eacfe-133">**Block network access through Wi-Fi:**</span></span>

![Bloquear o acesso à rede por meio de Wi-Fi](../media/mtp/skycure-arch-3.png)

<span data-ttu-id="eacfe-135">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="eacfe-135">**Access granted on remediation:**</span></span>

![Acesso concedido após a correção](../media/mtp/skycure-arch-4.png)

### <span data-ttu-id="eacfe-137">Controlar o acesso ao SharePoint Online com base em ameaças à rede</span><span class="sxs-lookup"><span data-stu-id="eacfe-137">Control access to SharePoint Online based on threat to network</span></span>
<a id="control-access-to-sharepoint-online-based-on-threat-to-network" class="xliff"></a>

<span data-ttu-id="eacfe-138">Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="eacfe-138">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="eacfe-139">**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**</span><span class="sxs-lookup"><span data-stu-id="eacfe-139">**Block SharePoint Online when network threats are detected:**</span></span>

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](../media/mtp/skycure-arch-5.png)

<span data-ttu-id="eacfe-141">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="eacfe-141">**Access granted on remediation:**</span></span>

![Acesso concedido após correção para exemplo do Sharepoint](../media/mtp/skycure-arch-6.png)

## <span data-ttu-id="eacfe-143">Plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="eacfe-143">Supported platforms</span></span>
<a id="supported-platforms" class="xliff"></a>

-   <span data-ttu-id="eacfe-144">**Android 4.1 e posterior**</span><span class="sxs-lookup"><span data-stu-id="eacfe-144">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="eacfe-145">**iOS 8 e posterior**</span><span class="sxs-lookup"><span data-stu-id="eacfe-145">**iOS 8 and later**</span></span>

## <span data-ttu-id="eacfe-146">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="eacfe-146">Pre-requisites</span></span>
<a id="pre-requisites" class="xliff"></a>

-   <span data-ttu-id="eacfe-147">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="eacfe-147">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="eacfe-148">Assinatura do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="eacfe-148">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="eacfe-149">Assinatura da Defesa contra Ameaças Móveis do Skycure</span><span class="sxs-lookup"><span data-stu-id="eacfe-149">Skycure Mobile Threat Defense subscription</span></span>

<span data-ttu-id="eacfe-150">Para saber mais, veja o [site do Skycure](https://www.skycure.com/skycure-microsoft-integration/).</span><span class="sxs-lookup"><span data-stu-id="eacfe-150">For more information, check [Skycure website](https://www.skycure.com/skycure-microsoft-integration/).</span></span>

## <span data-ttu-id="eacfe-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="eacfe-151">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="eacfe-152">Estas são as etapas que precisam ser concluídas para integrar o Intune ao Skycure:</span><span class="sxs-lookup"><span data-stu-id="eacfe-152">Here are the steps you need to complete to integrate Intune with Skycure:</span></span>

1.  [<span data-ttu-id="eacfe-153">Configurar o Skycure para usar o SS (Logon Único) do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eacfe-153">Configure Skycure to use Azure Active Directory Single Sign On (SS)</span></span>](/intune-classic/deploy-use/configure-skycure-to-use-azure-active-directory-single-sign-on)

2.  [<span data-ttu-id="eacfe-154">Baixar a política de configuração de aplicativo iOS do Skycure</span><span class="sxs-lookup"><span data-stu-id="eacfe-154">Download Skycure iOS app configuration policy</span></span>](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)

3.  [<span data-ttu-id="eacfe-155">Adicionar os aplicativos Skycure, o Microsoft Authenticator e a política de configuração do iOS</span><span class="sxs-lookup"><span data-stu-id="eacfe-155">Add Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](/intune-classic/deploy-use/add-skycure-apps-microsoft-authenticator-and-ios-app-configuration-policy)

4.  [<span data-ttu-id="eacfe-156">Implantar os aplicativos Skycure, o aplicativo Microsoft Authenticator e a política de configuração do iOS</span><span class="sxs-lookup"><span data-stu-id="eacfe-156">Deploy Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)

5.  [<span data-ttu-id="eacfe-157">Configurar a integração do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="eacfe-157">Set up Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

6.  [<span data-ttu-id="eacfe-158">Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune</span><span class="sxs-lookup"><span data-stu-id="eacfe-158">Enable Skycure Mobile Threat Defense in Intune</span></span>](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

7.  [<span data-ttu-id="eacfe-159">Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure no Intune</span><span class="sxs-lookup"><span data-stu-id="eacfe-159">Create Skycure Mobile Threat Defense compliance policy in Intune</span></span>](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
