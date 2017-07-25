---
title: Perfis de certificado para acesso a recursos
description: "Proteja o acesso ao email, Wi-Fi e VPN com um certificado instalado em cada dispositivo do usuário."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5570c13b9ca1782b12ad7ca718d18c98bda7bbfa
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="5aa3b-103">Proteger o acesso a recursos com perfis de certificado no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5aa3b-103">Secure resource access with certificate profiles in Microsoft Intune</span></span>
<a id="secure-resource-access-with-certificate-profiles-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5aa3b-104">Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode proteger o acesso usando um certificado instalado em cada dispositivo de usuário.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-104">When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can secure the access by using a certificate that is installed on each user device.</span></span> <span data-ttu-id="5aa3b-105">Assim é como funciona:</span><span class="sxs-lookup"><span data-stu-id="5aa3b-105">Here's how it works:</span></span>

1. <span data-ttu-id="5aa3b-106">Verifique se você tem a infraestrutura de certificado correta, conforme descrito em [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md) e [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md).</span><span class="sxs-lookup"><span data-stu-id="5aa3b-106">Make sure you have the right certificate infrastructure in place, as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) and [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md).</span></span>

2. <span data-ttu-id="5aa3b-107">Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-107">Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA.</span></span> <span data-ttu-id="5aa3b-108">Para fazer isso, crie e implante um **Perfil de Certificado Confiável**.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-108">To do this, create and deploy a **Trusted Certificate Profile**.</span></span> <span data-ttu-id="5aa3b-109">Quando você implanta esse perfil, os dispositivos que você gerencia com o Intune solicitarão e receberão o certificado raiz.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-109">When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate.</span></span> <span data-ttu-id="5aa3b-110">Você precisa criar um perfil separado para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-110">You have to create a separate profile for each platform.</span></span> <span data-ttu-id="5aa3b-111">O **Perfil de Certificado Confiável** está disponível para estas plataformas:</span><span class="sxs-lookup"><span data-stu-id="5aa3b-111">The **Trusted Certificate Profile** is available for these platforms:</span></span>
 -  <span data-ttu-id="5aa3b-112">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-112">iOS 8.0 and later</span></span>
 -  <span data-ttu-id="5aa3b-113">Mac OS X 10.9 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-113">Mac OS X 10.9 and later</span></span>
 -  <span data-ttu-id="5aa3b-114">Android 4.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-114">Android 4.0 and later</span></span>
 -  <span data-ttu-id="5aa3b-115">Android for Work</span><span class="sxs-lookup"><span data-stu-id="5aa3b-115">Android for Work</span></span>
 -  <span data-ttu-id="5aa3b-116">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-116">Windows 8.1 and later</span></span>
 -  <span data-ttu-id="5aa3b-117">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-117">Windows Phone 8.1 and later</span></span>

3. <span data-ttu-id="5aa3b-118">Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email, conforme descrito em [Configurar perfis de certificado do Intune](configure-intune-certificate-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5aa3b-118">Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access, as described in [Configure Intune certificate profiles](configure-intune-certificate-profiles.md).</span></span> <span data-ttu-id="5aa3b-119">Você pode criar e implantar um **Perfil de Certificado PKCS #12 (.PFX)** *ou* um **Perfil de Certificado SCEP** para dispositivos em execução nestas plataformas:</span><span class="sxs-lookup"><span data-stu-id="5aa3b-119">You can create and deploy a **PKCS #12 (.PFX) Certificate Profile** *or* a **SCEP Certificate Profile** for devices running these platforms:</span></span>

  -  <span data-ttu-id="5aa3b-120">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-120">iOS 8.0 and later</span></span>
  -  <span data-ttu-id="5aa3b-121">Android 4.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-121">Android 4.0 and later</span></span>
  -  <span data-ttu-id="5aa3b-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="5aa3b-122">Android for Work</span></span>
  -  <span data-ttu-id="5aa3b-123">Windows 10 (Desktop e Mobile) e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-123">Windows 10 (desktop and mobile) and later</span></span>

  <span data-ttu-id="5aa3b-124">Use um **Perfil de Certificado SCEP** para dispositivos executados nestas plataformas:</span><span class="sxs-lookup"><span data-stu-id="5aa3b-124">Use a **SCEP Certificate Profile** for devices running these platforms:</span></span>
    -   <span data-ttu-id="5aa3b-125">Mac OS X 10.9 e posterior</span><span class="sxs-lookup"><span data-stu-id="5aa3b-125">Mac OS X 10.9 and later</span></span>
    -   <span data-ttu-id="5aa3b-126">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="5aa3b-126">Windows Phone 8.1</span></span>

<span data-ttu-id="5aa3b-127">Você deve criar um perfil separado para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-127">You must create a separate profile for each platform.</span></span> <span data-ttu-id="5aa3b-128">Ao criar o perfil, você o associa ao **Perfil de Certificado Raiz Confiável** que já criou.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-128">When you create the profile, associate it with the **Trusted Root Certificate Profile** that you've already created.</span></span>

> [!NOTE]           
> - <span data-ttu-id="5aa3b-129">Se não tiver uma Autoridade de Certificação Corporativa, você precisará criar uma.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-129">If you don't have an Enterprise Certification Authority, you must create one.</span></span>
>- <span data-ttu-id="5aa3b-130">Com base em suas plataformas de dispositivo, se decidir usar o perfil de SCEP (Protocolo de Registro de Certificado Simplificado), você também precisará configurar um NDES (Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="5aa3b-130">If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.</span></span>
>-  <span data-ttu-id="5aa3b-131">Se planeja usar perfis SCEP ou .PFX, você precisa baixar e configurar o Conector de Certificado do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5aa3b-131">Whether you plan to use SCEP or .PFX profiles, you must download and configure the Microsoft Intune Certificate Connector.</span></span>
>-  <span data-ttu-id="5aa3b-132">Saiba como configurar todos os serviços necessários em [Configurar a infraestrutura de certificado para SCEP](configure-certificate-infrastructure-for-scep.md) ou [Configurar a infraestrutura de certificado para PFX](configure-certificate-infrastructure-for-pfx.md).</span><span class="sxs-lookup"><span data-stu-id="5aa3b-132">Learn how to configure all of the required services in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md).</span></span>

### <span data-ttu-id="5aa3b-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="5aa3b-133">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
- [<span data-ttu-id="5aa3b-134">Configurar a infraestrutura de certificado para SCEP</span><span class="sxs-lookup"><span data-stu-id="5aa3b-134">Configure certificate infrastructure for SCEP</span></span>](configure-certificate-infrastructure-for-scep.md)
- [<span data-ttu-id="5aa3b-135">Configurar a infraestrutura de certificado para PFX</span><span class="sxs-lookup"><span data-stu-id="5aa3b-135">Configure certificate infrastructure for PFX</span></span>](configure-certificate-infrastructure-for-pfx.md)
- [<span data-ttu-id="5aa3b-136">Configurar perfis de certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="5aa3b-136">Configure Intune certificate profiles</span></span>](configure-intune-certificate-profiles.md)
