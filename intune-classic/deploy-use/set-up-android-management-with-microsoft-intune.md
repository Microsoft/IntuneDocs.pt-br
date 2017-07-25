---
title: Configurar o gerenciamento de Android
description: "Habilitar o MDM (gerenciamento de dispositivo móvel) para dispositivos Android e KNOX Standard com o Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 927259d2f3b3078c9fdb0f1ba3bb22a69b555ab6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ab97d-103">Configurar o gerenciamento de dispositivo Android</span><span class="sxs-lookup"><span data-stu-id="ab97d-103">Set up Android device management</span></span>
<a id="set-up-android-device-management" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ab97d-104">Como administrador do Intune, você pode habilitar o gerenciamento de dispositivos Android, incluindo dispositivos Samsung Knox Standard, por meio do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ab97d-104">As an Intune administrator, you can enable management of Android devices, including Samsung Knox Standard devices, from the Company Portal.</span></span> <span data-ttu-id="ab97d-105">Os usuários podem registrar seus dispositivos usando o aplicativo de Portal da Empresa disponível no Google Play.</span><span class="sxs-lookup"><span data-stu-id="ab97d-105">Users can then enroll their devices using the Company Portal app that is available from Google Play.</span></span>

<span data-ttu-id="ab97d-106">Por padrão, os dispositivos Android têm permissão para se registrarem no Intune.</span><span class="sxs-lookup"><span data-stu-id="ab97d-106">By default, Android devices are allowed to enroll in Intune.</span></span> <span data-ttu-id="ab97d-107">Para bloquear o registro de dispositivos Android, entre no [Portal de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="ab97d-107">To block Android devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span> <span data-ttu-id="ab97d-108">Escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Regras de Registro** e desmarque a caixa de seleção **Permitir Dispositivos Android**.</span><span class="sxs-lookup"><span data-stu-id="ab97d-108">Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the **Allow Android devices** check box.</span></span>

1.  <span data-ttu-id="ab97d-109">**Configurar Intune**</span><span class="sxs-lookup"><span data-stu-id="ab97d-109">**Set up Intune**</span></span><br>
    <span data-ttu-id="ab97d-110">Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](prerequisites-for-enrollment.md#step-2-set-mdm-authority) como **Microsoft Intune** e configure o MDM.</span><span class="sxs-lookup"><span data-stu-id="ab97d-110">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.</span></span>

2.  <span data-ttu-id="ab97d-111">**Registro do Android habilitado**</span><span class="sxs-lookup"><span data-stu-id="ab97d-111">**Android enrollment enabled**</span></span><br>
    <span data-ttu-id="ab97d-112">Nenhuma configuração adicional no console do Intune é necessária para habilitar o registro de dispositivo móvel Android.</span><span class="sxs-lookup"><span data-stu-id="ab97d-112">No additional configurations in the Intune console are needed to enable Android mobile device enrollment.</span></span>

3.  <span data-ttu-id="ab97d-113">**Informe aos usuários como registrar seus dispositivos para obter acesso aos recursos da empresa.**</span><span class="sxs-lookup"><span data-stu-id="ab97d-113">**Tell your users how to enroll their devices to get access to company resources.**</span></span>

    <span data-ttu-id="ab97d-114">Para obter instruções de registro de usuário final, consulte [Registrar seu dispositivo com Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span><span class="sxs-lookup"><span data-stu-id="ab97d-114">For end-user enrollment instructions, see [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span></span> <span data-ttu-id="ab97d-115">O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ab97d-115">The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.</span></span>

    <span data-ttu-id="ab97d-116">Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="ab97d-116">For information about other end-user tasks, see these articles:</span></span>
  - [<span data-ttu-id="ab97d-117">Recursos sobre a experiência do usuário final com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab97d-117">Resources about the end-user experience with Microsoft Intune</span></span>](/intune/end-user-educate)
  - [<span data-ttu-id="ab97d-118">Diretrizes do usuário final para dispositivos com Android</span><span class="sxs-lookup"><span data-stu-id="ab97d-118">End user guidance for Android devices</span></span>](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

<span data-ttu-id="ab97d-119">Devido à ausência da Google Play Store na China, os dispositivos Android devem obter o Portal da Empresa nos marketplaces de aplicativos chineses.</span><span class="sxs-lookup"><span data-stu-id="ab97d-119">Due to the absence of Google Play Store in China, Android devices must obtain the Company Portal from Chinese app marketplaces.</span></span> <span data-ttu-id="ab97d-120">O aplicativo do Portal da Empresa para Android estará disponível para download nas seguintes lojas:</span><span class="sxs-lookup"><span data-stu-id="ab97d-120">The Company Portal app for Android will be available for download on the following stores:</span></span>
* [<span data-ttu-id="ab97d-121">Baidu</span><span class="sxs-lookup"><span data-stu-id="ab97d-121">Baidu</span></span>](https://go.microsoft.com/fwlink/?linkid=836946)
* [<span data-ttu-id="ab97d-122">Huawei</span><span class="sxs-lookup"><span data-stu-id="ab97d-122">Huawei</span></span>](https://go.microsoft.com/fwlink/?linkid=836948)
* [<span data-ttu-id="ab97d-123">Tencent</span><span class="sxs-lookup"><span data-stu-id="ab97d-123">Tencent</span></span>](https://go.microsoft.com/fwlink/?linkid=836949)
* [<span data-ttu-id="ab97d-124">Wandoujia</span><span class="sxs-lookup"><span data-stu-id="ab97d-124">Wandoujia</span></span>](https://go.microsoft.com/fwlink/?linkid=836950)
* [<span data-ttu-id="ab97d-125">Xiaomi</span><span class="sxs-lookup"><span data-stu-id="ab97d-125">Xiaomi</span></span>](https://go.microsoft.com/fwlink/?linkid=836947)

<span data-ttu-id="ab97d-126">O aplicativo de Portal da Empresa para Android usa o Google Play Services para se comunicar com o serviço Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ab97d-126">The Company Portal app for Android uses Google Play Services to communicate with the Microsoft Intune service.</span></span> <span data-ttu-id="ab97d-127">Como o Google Play Services ainda não está disponível na China, a execução de qualquer uma das seguintes tarefas pode levar até 8 horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="ab97d-127">Since Google Play Services are not yet available in China, performing any of the following tasks can take up to 8 hours to complete.</span></span> 

|<span data-ttu-id="ab97d-128">Console de Administração do Intune</span><span class="sxs-lookup"><span data-stu-id="ab97d-128">Intune Admin Console</span></span>| <span data-ttu-id="ab97d-129">Aplicativo do Portal da Empresa do Intune para Android</span><span class="sxs-lookup"><span data-stu-id="ab97d-129">Intune Company Portal app for Android</span></span> |<span data-ttu-id="ab97d-130">Site do Portal da Empresa do Intune</span><span class="sxs-lookup"><span data-stu-id="ab97d-130">Intune Company Portal Website</span></span>|   
|---|---|---|
|<span data-ttu-id="ab97d-131">Apagamento completo</span><span class="sxs-lookup"><span data-stu-id="ab97d-131">Full wipe</span></span>| <span data-ttu-id="ab97d-132">Remover um dispositivo remoto</span><span class="sxs-lookup"><span data-stu-id="ab97d-132">Remove a remote device</span></span>| <span data-ttu-id="ab97d-133">Remover dispositivo (local e remoto)</span><span class="sxs-lookup"><span data-stu-id="ab97d-133">Remove device (local and remote)</span></span>|
|<span data-ttu-id="ab97d-134">Apagamento seletivo</span><span class="sxs-lookup"><span data-stu-id="ab97d-134">Selective wipe</span></span>| <span data-ttu-id="ab97d-135">Redefinir dispositivo</span><span class="sxs-lookup"><span data-stu-id="ab97d-135">Reset device</span></span>| <span data-ttu-id="ab97d-136">Redefinir o dispositivo</span><span class="sxs-lookup"><span data-stu-id="ab97d-136">Reset device</span></span>|
|<span data-ttu-id="ab97d-137">Implantações de aplicativo novo ou atualizado</span><span class="sxs-lookup"><span data-stu-id="ab97d-137">New or updated app deployments</span></span>| <span data-ttu-id="ab97d-138">Instalar aplicativos de linha de negócios disponíveis</span><span class="sxs-lookup"><span data-stu-id="ab97d-138">Install available line-of-business apps</span></span>| <span data-ttu-id="ab97d-139">Redefinição de senha de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ab97d-139">Device passcode reset</span></span>|
|<span data-ttu-id="ab97d-140">Bloqueio remoto</span><span class="sxs-lookup"><span data-stu-id="ab97d-140">Remote lock</span></span>|||
|<span data-ttu-id="ab97d-141">Redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="ab97d-141">Passcode reset</span></span>|||

### <span data-ttu-id="ab97d-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ab97d-142">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="ab97d-143">Pré-requisitos para registrar dispositivos no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab97d-143">Prerequisites to enrolling devices in Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
