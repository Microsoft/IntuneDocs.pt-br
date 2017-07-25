---
title: "O que acontece quando você cancela o registro do dispositivo Windows? | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 3de9589c46250727b1994381c24c68e6e2b90da2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d6e93-103">O que acontece quando você cancela o registro do dispositivo Windows no Intune?</span><span class="sxs-lookup"><span data-stu-id="d6e93-103">What happens if you unenroll your Windows device from Intune?</span></span>
<a id="what-happens-if-you-unenroll-your-windows-device-from-intune" class="xliff"></a>

<span data-ttu-id="d6e93-104">Use os links no lado direito desta página, em **Neste artigo**, para localizar informações sobre o tipo de dispositivo que você está usando.</span><span class="sxs-lookup"><span data-stu-id="d6e93-104">Use the links at the right side of this page, under **In this article**, to find information about the type of device you're using.</span></span>


## <span data-ttu-id="d6e93-105">Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista</span><span class="sxs-lookup"><span data-stu-id="d6e93-105">Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista</span></span>
<a id="windows-10-windows-81-windows-8-windows-7-windows-vista" class="xliff"></a>

-   <span data-ttu-id="d6e93-106">O dispositivo não aparece mais no Portal da Empresa e você não pode mais instalar aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="d6e93-106">Your device doesn't appear in the Company Portal anymore, and you can’t install apps from the Company Portal anymore.</span></span>

-   <span data-ttu-id="d6e93-107">Se você tiver instalado o software cliente do Intune, ele será removido do computador.</span><span class="sxs-lookup"><span data-stu-id="d6e93-107">If you installed the Intune client software, it’s removed from your computer.</span></span>

-   <span data-ttu-id="d6e93-108">O software Intune Endpoint Protection será removido do computador.</span><span class="sxs-lookup"><span data-stu-id="d6e93-108">The Intune Endpoint Protection software is removed from your computer.</span></span> <span data-ttu-id="d6e93-109">Se o computador tiver outro software de proteção contra vírus instalado que esteja desabilitado, esse software poderá ser habilitado novamente depois que o Intune Endpoint Protection for removido.</span><span class="sxs-lookup"><span data-stu-id="d6e93-109">If your computer has other virus protection software installed and it is disabled, that software can be re-enabled after Intune Endpoint Protection is removed.</span></span> <span data-ttu-id="d6e93-110">Verifique o computador depois de removê-lo do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="d6e93-110">Check your computer after removing it from the Company Portal.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d6e93-111">Se outro software de proteção contra vírus não for habilitado novamente ou não estiver instalado, o seu computador poderá ficar vulnerável a vírus e malware.</span><span class="sxs-lookup"><span data-stu-id="d6e93-111">If the other virus protection software is not re-enabled or no other virus protection software is installed, your computer may be vulnerable to viruses and malware.</span></span>

-   <span data-ttu-id="d6e93-112">Configurações que foram alteradas no seu dispositivo quando ele foi adicionado (por exemplo, a desabilitação da câmera) não se aplicam mais.</span><span class="sxs-lookup"><span data-stu-id="d6e93-112">Any settings that were changed on your device when you added it (for example, disabling the camera) no longer apply.</span></span>

-   <span data-ttu-id="d6e93-113">O computador não recebe mais as atualizações automáticas de software ou de software antivírus do serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="d6e93-113">Your computer no longer receives automatic software updates or antivirus software updates from the Intune service.</span></span> <span data-ttu-id="d6e93-114">No entanto, dependendo de como estiver configurado, seu computador ainda pode receber atualizações do Windows Server Update Services, Windows Update ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="d6e93-114">But, depending on how it is set up, your computer might still receive updates from the Windows Server Update Services, Windows Update, or Microsoft Update.</span></span>

<span data-ttu-id="d6e93-115">Além disso, para Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="d6e93-115">In addition, for Windows 8.1:</span></span>

-   <span data-ttu-id="d6e93-116">Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-116">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="d6e93-117">Alguns aplicativos de email, como o Windows Mail, não podem mais acessar os emails da empresa armazenados no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-117">Some email apps, like Windows Mail, can’t access company email that is stored on your device anymore.</span></span>

-   <span data-ttu-id="d6e93-118">Talvez você não consiga se conectar à sua rede da empresa usando o Wi-Fi ou uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="d6e93-118">You might not be able to connect to your company network by using Wi-Fi or a virtual private network.</span></span>

-   <span data-ttu-id="d6e93-119">Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-119">You might not have access to some company resources, like file shares or internal websites, on your device anymore.</span></span>

## <span data-ttu-id="d6e93-120">Windows 10 Mobile e Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="d6e93-120">Windows 10 mobile and Windows Phone 8.1</span></span>
<a id="windows-10-mobile-and-windows-phone-81" class="xliff"></a>

-   <span data-ttu-id="d6e93-121">O aplicativo de Portal da Empresa é desinstalado do seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-121">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="d6e93-122">isso significa que o dispositivo não aparece mais no Portal da Empresa e você não pode instalar aplicativos do site do Portal da Empresa ou do aplicativo de Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="d6e93-122">This means that your device doesn’t appear in the Company Portal anymore, and you can't install apps from the Company Portal app or the Company Portal website.</span></span>

-   <span data-ttu-id="d6e93-123">Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-123">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="d6e93-124">Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.</span><span class="sxs-lookup"><span data-stu-id="d6e93-124">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d6e93-125">As únicas exceções a isso são as políticas de criptografia, que ainda se aplicam.</span><span class="sxs-lookup"><span data-stu-id="d6e93-125">The only exception to this is encryption policies, which still apply.</span></span> <span data-ttu-id="d6e93-126">Se a política da sua empresa exigiu que você criptografasse seu Windows Phone, a única maneira de descriptografar o telefone será redefini-lo usando o menu **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d6e93-126">If your company policy required you to encrypt your Windows Phone, the only way to unencrypt your phone is to reset it by using the **Settings** menu.</span></span>

## <span data-ttu-id="d6e93-127">Windows RT executando o Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d6e93-127">Windows RT running Windows 8.1</span></span>
<a id="windows-rt-running-windows-81" class="xliff"></a>

-   <span data-ttu-id="d6e93-128">O aplicativo de Portal da Empresa é desinstalado do seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-128">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="d6e93-129">Isso significa que o dispositivo não aparece mais no Portal da Empresa e você não pode instalar aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="d6e93-129">This means that your device doesn’t appear in the Company Portal anymore, and you can’t install apps from the Company Portal.</span></span>

-   <span data-ttu-id="d6e93-130">Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-130">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="d6e93-131">Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.</span><span class="sxs-lookup"><span data-stu-id="d6e93-131">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

-   <span data-ttu-id="d6e93-132">Talvez você não consiga mais se conectar à sua rede da empresa usando o Wi-Fi ou uma rede virtual privada.</span><span class="sxs-lookup"><span data-stu-id="d6e93-132">You might not be able to connect to your company network by using Wi-Fi or a virtual private network anymore.</span></span>

-   <span data-ttu-id="d6e93-133">Talvez você não tenha mais acesso a alguns recursos da empresa, como compartilhamentos de arquivos ou sites internos, no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-133">You might not have access to some company resources, like file shares or internal websites, on your device anymore.</span></span>

-   <span data-ttu-id="d6e93-134">Alguns aplicativos de email, como o Windows Mail, não podem mais acessar os emails da empresa armazenados no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-134">Some email apps, like Windows Mail, can’t access company email that is stored on your device anymore.</span></span>

<span data-ttu-id="d6e93-135">Quando você remover seu dispositivo Windows RT, acontecerá o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d6e93-135">When you remove your Windows RT device, the following happens:</span></span>

-   <span data-ttu-id="d6e93-136">O aplicativo de Portal da Empresa é desinstalado do seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-136">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="d6e93-137">Isso significa que o dispositivo não aparece mais no Portal da Empresa e você não pode instalar aplicativos do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="d6e93-137">This means that your device doesn’t appear in the Company Portal anymore, and you can't install apps from the Company Portal.</span></span>

-   <span data-ttu-id="d6e93-138">Você não poderá mais usar os aplicativos e os dados da empresa no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6e93-138">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="d6e93-139">Qualquer configuração que tiver sido alterada em seu dispositivo quando você o adicionou (por exemplo, desabilitar a câmera ou exigir uma senha com determinado tamanho) não se aplicará mais.</span><span class="sxs-lookup"><span data-stu-id="d6e93-139">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

<span data-ttu-id="d6e93-140">Se tiver dúvidas, entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="d6e93-140">If you have questions, contact your IT admin.</span></span> <span data-ttu-id="d6e93-141">Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d6e93-141">For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
