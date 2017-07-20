---
title: Conector do Skycure com o Intune
titleSuffix: Intune on Azure
description: "Integração do conector do Skycure com o Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2a7c15cf695fd88ba5961611c78ecc28a29238af
ms.sourcegitcommit: 3b21f20108e2bf1cf47c141b36a7bdae609c4ec3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a><span data-ttu-id="875aa-103">Conector de Defesa contra Ameaças Móveis do Skycure</span><span class="sxs-lookup"><span data-stu-id="875aa-103">Skycure Mobile Threat Defense connector</span></span>

<span data-ttu-id="875aa-104">É possível controlar o acesso de dispositivos móveis a recursos corporativos usando o acesso condicional com base na avaliação de risco realizada pelo Skycure, uma solução de defesa contra ameaças móveis integrada ao Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="875aa-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="875aa-105">O risco é avaliado com base na telemetria coletada dos dispositivos com o Skycure em execução, incluindo:</span><span class="sxs-lookup"><span data-stu-id="875aa-105">Risk is assessed based on telemetry collected from devices running Skycure, including:</span></span>

-   <span data-ttu-id="875aa-106">Defesa física</span><span class="sxs-lookup"><span data-stu-id="875aa-106">Physical defense</span></span>

-   <span data-ttu-id="875aa-107">Defesa de rede</span><span class="sxs-lookup"><span data-stu-id="875aa-107">Network defense</span></span>

-   <span data-ttu-id="875aa-108">Defesa do aplicativo</span><span class="sxs-lookup"><span data-stu-id="875aa-108">Application defense</span></span>

-   <span data-ttu-id="875aa-109">Defesa de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="875aa-109">Vulnerabilities defense</span></span>

<span data-ttu-id="875aa-110">Você pode configurar políticas de acesso condicional com base na avaliação de risco do Skycure habilitada por meio de políticas de conformidade do dispositivo do Intune, que podem ser usadas para permitir ou bloquear o acesso de dispositivos incompatíveis a recursos corporativos com base em ameaças detectadas.</span><span class="sxs-lookup"><span data-stu-id="875aa-110">You can configure conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a><span data-ttu-id="875aa-111">Como o Intune e o Skycure ajudam a proteger os recursos da empresa?</span><span class="sxs-lookup"><span data-stu-id="875aa-111">How do Intune and Skycure help protect your company resources?</span></span>

<span data-ttu-id="875aa-112">O aplicativo móvel do Skycure para Android e iOS captura o sistema de arquivos, a pilha de rede e a telemetria do dispositivo e dos aplicativos, quando disponível, e envia-os ao serviço de nuvem do Skycure para avaliar o risco do dispositivo a ameaças móveis.</span><span class="sxs-lookup"><span data-stu-id="875aa-112">Skycure mobile app for Android or iOS captures file system, network stack, device and application telemetry where available, then sends it to the Skycure cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="875aa-113">A política de conformidade do dispositivo do Intune inclui uma regra para a Defesa contra Ameaças Móveis do Skycure, que se baseia na avaliação de risco do Skycure.</span><span class="sxs-lookup"><span data-stu-id="875aa-113">The Intune device compliance policy includes a rule for Skycure Mobile Threat Defense, which is based on the Skycure risk assessment.</span></span> <span data-ttu-id="875aa-114">Quando essa regra é habilitada, o Intune avalia a conformidade do dispositivo com a política habilitada.</span><span class="sxs-lookup"><span data-stu-id="875aa-114">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="875aa-115">Se o dispositivo for considerado fora de conformidade, o acesso a recursos como o Exchange Online e o SharePoint Online serão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="875aa-115">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online are blocked.</span></span> <span data-ttu-id="875aa-116">Os usuários com dispositivos bloqueados recebem orientação do aplicativo móvel do Skycure para resolver o problema e recuperar o acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="875aa-116">Users on blocked devices receive guidance from the Skycure mobile app to resolve the issue and regain access to corporate resources.</span></span>

<span data-ttu-id="875aa-117">O Intune dá suporte a dois modos de integração com o Skycure:</span><span class="sxs-lookup"><span data-stu-id="875aa-117">Intune supports two modes of integration with Skycure:</span></span>

-   <span data-ttu-id="875aa-118">**Configuração básica**, que é um modo somente leitura que permite a visibilidade do Skycure para dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="875aa-118">**Basic setup** which is a read only mode that allows Skycure visibility for devices in Intune.</span></span>

-   <span data-ttu-id="875aa-119">**Integração total**, que permite ao Skycure relatar detalhes dos incidentes de risco e segurança do dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="875aa-119">**Full integration** which allows Skycure to report device risk and security incident details to Intune.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="875aa-120">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="875aa-120">Sample scenarios</span></span>

<span data-ttu-id="875aa-121">Confira alguns cenários comuns:</span><span class="sxs-lookup"><span data-stu-id="875aa-121">Here are some common scenarios:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="875aa-122">Controlar o acesso com base em ameaças de aplicativos mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="875aa-122">Control access based on threats from malicious apps</span></span>

<span data-ttu-id="875aa-123">Quando aplicativos mal-intencionados, como malwares, são detectados nos dispositivos, é possível bloquear os dispositivos até que a ameaça seja resolvida:</span><span class="sxs-lookup"><span data-stu-id="875aa-123">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="875aa-124">Conectar-se ao email corporativo</span><span class="sxs-lookup"><span data-stu-id="875aa-124">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="875aa-125">Sincronizar arquivos corporativos com o aplicativo OneDrive for Work</span><span class="sxs-lookup"><span data-stu-id="875aa-125">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="875aa-126">Acessar aplicativos da empresa</span><span class="sxs-lookup"><span data-stu-id="875aa-126">Accessing company apps</span></span>

<span data-ttu-id="875aa-127">**Bloquear quando aplicativos mal-intencionados forem detectados:**</span><span class="sxs-lookup"><span data-stu-id="875aa-127">**Block when malicious apps are detected:**</span></span>

![Aplicativos mal-intencionados detectados](./media/skycure-arch-1.png)

<span data-ttu-id="875aa-129">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="875aa-129">**Access granted on remediation:**</span></span>

![Acesso concedido a aplicativos mal-intencionados detectado](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="875aa-131">Controlar o acesso com base em ameaças à rede</span><span class="sxs-lookup"><span data-stu-id="875aa-131">Control access based on threat to network</span></span>

<span data-ttu-id="875aa-132">Detecta ameaças como **Man-in-the-middle** na rede e protege o acesso a redes Wi-Fi com base no risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="875aa-132">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="875aa-133">**Bloquear o acesso à rede por meio de Wi-Fi:**</span><span class="sxs-lookup"><span data-stu-id="875aa-133">**Block network access through Wi-Fi:**</span></span>

![Bloquear o acesso à rede por meio de Wi-Fi](./media/skycure-arch-3.png)

<span data-ttu-id="875aa-135">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="875aa-135">**Access granted on remediation:**</span></span>

![Acesso concedido após a correção](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="875aa-137">Controlar o acesso ao SharePoint Online com base em ameaças à rede</span><span class="sxs-lookup"><span data-stu-id="875aa-137">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="875aa-138">Detectar ameaças como **Man-in-the-middle** na rede e impede a sincronização de arquivos corporativos com base no risco ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="875aa-138">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="875aa-139">**Bloquear o SharePoint Online quando ameaças à rede forem detectadas:**</span><span class="sxs-lookup"><span data-stu-id="875aa-139">**Block SharePoint Online when network threats are detected:**</span></span>

![Bloquear o SharePoint Online quando ameaças à rede forem detectadas](./media/skycure-arch-5.png)

<span data-ttu-id="875aa-141">**Acesso concedido após a correção:**</span><span class="sxs-lookup"><span data-stu-id="875aa-141">**Access granted on remediation:**</span></span>

![Acesso concedido após correção para exemplo do Sharepoint](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a><span data-ttu-id="875aa-143">Plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="875aa-143">Supported platforms</span></span>

-   <span data-ttu-id="875aa-144">**Android 4.1 e posterior**</span><span class="sxs-lookup"><span data-stu-id="875aa-144">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="875aa-145">**iOS 8 e posterior**</span><span class="sxs-lookup"><span data-stu-id="875aa-145">**iOS 8 and later**</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="875aa-146">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="875aa-146">Pre-requisites</span></span>

-   <span data-ttu-id="875aa-147">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="875aa-147">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="875aa-148">Assinatura do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="875aa-148">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="875aa-149">Assinatura da Defesa contra Ameaças Móveis do Skycure</span><span class="sxs-lookup"><span data-stu-id="875aa-149">Skycure Mobile Threat Defense subscription</span></span>

<span data-ttu-id="875aa-150">Para saber mais, veja o [site do Skycure](https://www.skycure.com/skycure-microsoft-integration/).</span><span class="sxs-lookup"><span data-stu-id="875aa-150">For more information, check [Skycure website](https://www.skycure.com/skycure-microsoft-integration/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="875aa-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="875aa-151">Next steps</span></span>

<span data-ttu-id="875aa-152">Estas são as etapas que precisam ser concluídas para integrar o Intune ao Skycure:</span><span class="sxs-lookup"><span data-stu-id="875aa-152">Here are the steps you need to complete to integrate Intune with Skycure:</span></span>

1.  [<span data-ttu-id="875aa-153">Adicionar e atribuir os aplicativos Skycure, o Microsoft Authenticator e a política de configuração do iOS</span><span class="sxs-lookup"><span data-stu-id="875aa-153">Add and assign Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)

2.  [<span data-ttu-id="875aa-154">Configurar a integração do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="875aa-154">Set up Skycure integration with Intune</span></span>](skycure-mtd-connector-integration.md)

3.  [<span data-ttu-id="875aa-155">Habilitar o conector MTD do Skycure no Intune</span><span class="sxs-lookup"><span data-stu-id="875aa-155">Enable Skycure MTD connector in Intune</span></span>](mtd-connector-enable.md)

4.  [<span data-ttu-id="875aa-156">Criar uma política de conformidade do dispositivo do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="875aa-156">Create Skycure device compliance policy with Intune</span></span>](mtd-device-compliance-policy-create.md)
