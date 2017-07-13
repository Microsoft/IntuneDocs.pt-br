---
title: Habilitar o acesso aos recursos da empresa
description: "Os perfis de Wi-Fi, VPN e email funcionam em conjunto para ajudar seus usuários a obter acesso aos arquivos e recursos necessários."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 18091d5dea0ff4b4519082973255a21e5cbc311e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="de0d1-103">Habilitar o acesso aos recursos da empresa com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="de0d1-103">Enable access to company resources with Microsoft Intune</span></span>
<a id="enable-access-to-company-resources-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="de0d1-104">Os perfis de Wi-Fi, VPN e email do Microsoft Intune funcionam em conjunto para ajudar os usuários a obter acesso aos arquivos e recursos necessários para realizar seu trabalho, independentemente de onde estiverem.</span><span class="sxs-lookup"><span data-stu-id="de0d1-104">Microsoft Intune Wi-Fi, VPN, and email profiles work together to help your users gain access to the files and resources that they need to do their work wherever they are.</span></span> <span data-ttu-id="de0d1-105">Perfis de certificado ajudam a proteger o acesso.</span><span class="sxs-lookup"><span data-stu-id="de0d1-105">Certificate profiles help secure that access.</span></span>

## <span data-ttu-id="de0d1-106">[Perfis de Wi-Fi](wi-fi-connections-in-microsoft-intune.md) e plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="de0d1-106">[Wi-Fi profiles](wi-fi-connections-in-microsoft-intune.md) and supported platforms</span></span>
<a id="wi-fi-profileswi-fi-connections-in-microsoft-intunemd-and-supported-platforms" class="xliff"></a>

<span data-ttu-id="de0d1-107">Implante configurações de rede sem fio aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="de0d1-107">Deploy wireless network settings to your users.</span></span> <span data-ttu-id="de0d1-108">Essas configurações facilitam para os usuários se conectar à rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="de0d1-108">These settings make it easy for your users to connect to the corporate network.</span></span>
#### <span data-ttu-id="de0d1-109">Plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="de0d1-109">Supported platforms</span></span>
<a id="supported-platforms" class="xliff"></a>

|<span data-ttu-id="de0d1-110">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-110">Windows 8.1 and later</span></span>|<span data-ttu-id="de0d1-111">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-111">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="de0d1-112">iOS</span><span class="sxs-lookup"><span data-stu-id="de0d1-112">iOS</span></span>|<span data-ttu-id="de0d1-113">Android</span><span class="sxs-lookup"><span data-stu-id="de0d1-113">Android</span></span>|<span data-ttu-id="de0d1-114">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="de0d1-114">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="de0d1-115">Sim (Você pode importar um perfil de Wi-Fi do Windows.)</span><span class="sxs-lookup"><span data-stu-id="de0d1-115">Yes (You can import a Windows Wi-Fi profile.)</span></span>|<span data-ttu-id="de0d1-116">Sim (Você pode configurar OMA-URI.)</span><span class="sxs-lookup"><span data-stu-id="de0d1-116">Yes (You can configure OMA-URI.)</span></span> |<span data-ttu-id="de0d1-117">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-117">Yes</span></span>|<span data-ttu-id="de0d1-118">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-118">Yes</span></span>|<span data-ttu-id="de0d1-119">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-119">Yes</span></span>|

## <span data-ttu-id="de0d1-120">[Perfis de VPN](vpn-connections-in-microsoft-intune.md) e plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="de0d1-120">[VPN profiles](vpn-connections-in-microsoft-intune.md) and supported platforms</span></span>
<a id="vpn-profilesvpn-connections-in-microsoft-intunemd-and-supported-platforms" class="xliff"></a>
<span data-ttu-id="de0d1-121">Implante configurações de VPN (rede virtual privada) para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="de0d1-121">Deploy virtual private network (VPN) settings to your users.</span></span> <span data-ttu-id="de0d1-122">Essas configurações facilitam para os usuários se conectar aos recursos na rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="de0d1-122">These settings make it easy for users to connect to resources on the corporate network.</span></span>

|<span data-ttu-id="de0d1-123">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-123">Windows 8.1 and later</span></span>|<span data-ttu-id="de0d1-124">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-124">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="de0d1-125">iOS</span><span class="sxs-lookup"><span data-stu-id="de0d1-125">iOS</span></span>|<span data-ttu-id="de0d1-126">Android</span><span class="sxs-lookup"><span data-stu-id="de0d1-126">Android</span></span>|<span data-ttu-id="de0d1-127">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="de0d1-127">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="de0d1-128">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-128">Yes</span></span>|<span data-ttu-id="de0d1-129">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-129">Yes</span></span>|<span data-ttu-id="de0d1-130">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-130">Yes</span></span>|<span data-ttu-id="de0d1-131">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-131">Yes</span></span>|<span data-ttu-id="de0d1-132">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-132">Yes</span></span>|

## <span data-ttu-id="de0d1-133">[Perfis de email](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) e plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="de0d1-133">[Email profiles](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) and supported platforms</span></span>
<a id="email-profilesconfigure-access-to-corporate-email-using-email-profiles-with-microsoft-intunemd-and-supported-platforms" class="xliff"></a>
<span data-ttu-id="de0d1-134">Crie, implante e monitore configurações de email nativas em dispositivos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="de0d1-134">Create, deploy, and monitor native email client settings on devices in your organization.</span></span>

|<span data-ttu-id="de0d1-135">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-135">Windows 8.1 and later</span></span>|<span data-ttu-id="de0d1-136">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-136">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="de0d1-137">iOS</span><span class="sxs-lookup"><span data-stu-id="de0d1-137">iOS</span></span>|<span data-ttu-id="de0d1-138">Android</span><span class="sxs-lookup"><span data-stu-id="de0d1-138">Android</span></span>|<span data-ttu-id="de0d1-139">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="de0d1-139">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="de0d1-140">Não</span><span class="sxs-lookup"><span data-stu-id="de0d1-140">No</span></span>|<span data-ttu-id="de0d1-141">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-141">Yes</span></span>|<span data-ttu-id="de0d1-142">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-142">Yes</span></span>|<span data-ttu-id="de0d1-143">Não</span><span class="sxs-lookup"><span data-stu-id="de0d1-143">No</span></span>|<span data-ttu-id="de0d1-144">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-144">Yes</span></span>|
> [!NOTE]
> <span data-ttu-id="de0d1-145">[Esta postagem de blog de equipe do Intune](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) fornece informações sobre como configurar um perfil de Wi-Fi do Windows Phone 8.1 usando o OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="de0d1-145">[This Intune team blog post](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) gives information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.</span></span>

## <span data-ttu-id="de0d1-146">[Perfis de certificado](secure-resource-access-with-certificate-profiles.md) e plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="de0d1-146">[Certificate profiles](secure-resource-access-with-certificate-profiles.md) and supported platforms</span></span>
<a id="certificate-profilessecure-resource-access-with-certificate-profilesmd-and-supported-platforms" class="xliff"></a>
<span data-ttu-id="de0d1-147">Ajude a proteger o acesso aos recursos de empresa, incluindo conexões VPN e redes sem fio.</span><span class="sxs-lookup"><span data-stu-id="de0d1-147">Help secure access to company resources including wireless networks and VPN connections.</span></span>

|<span data-ttu-id="de0d1-148">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-148">Windows 8.1 and later</span></span>|<span data-ttu-id="de0d1-149">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="de0d1-149">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="de0d1-150">iOS</span><span class="sxs-lookup"><span data-stu-id="de0d1-150">iOS</span></span>|<span data-ttu-id="de0d1-151">Android</span><span class="sxs-lookup"><span data-stu-id="de0d1-151">Android</span></span>|<span data-ttu-id="de0d1-152">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="de0d1-152">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="de0d1-153">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-153">Yes</span></span>|<span data-ttu-id="de0d1-154">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-154">Yes</span></span>|<span data-ttu-id="de0d1-155">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-155">Yes</span></span>|<span data-ttu-id="de0d1-156">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-156">Yes</span></span>|<span data-ttu-id="de0d1-157">Sim</span><span class="sxs-lookup"><span data-stu-id="de0d1-157">Yes</span></span>|
