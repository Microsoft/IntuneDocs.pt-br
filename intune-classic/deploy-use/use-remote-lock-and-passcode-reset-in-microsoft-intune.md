---
title: "Redefinição de senha e bloqueio remoto"
description: "O Intune fornece funcionalidades de bloqueio remoto e redefinição de senha."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ms.reviewer: chrisgre
ms.custom: intune-classic
ms.openlocfilehash: f43c2fb3c2aaff43aaef8cb033185c8c517d83a0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6b1d5-103">Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="6b1d5-103">Help protect your devices with remote lock and passcode reset</span></span>
<a id="help-protect-your-devices-with-remote-lock-and-passcode-reset" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6b1d5-104">O Microsoft Intune fornece funcionalidades de bloqueio remoto e redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-104">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span>

## <span data-ttu-id="6b1d5-105">Bloquear um dispositivo remotamente</span><span class="sxs-lookup"><span data-stu-id="6b1d5-105">Lock a device remotely</span></span>
<a id="lock-a-device-remotely" class="xliff"></a>
<span data-ttu-id="6b1d5-106">Se um usuário perder um dispositivo, você poderá bloquear o dispositivo remotamente.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-106">If a user loses a device, you can lock the device remotely.</span></span> <span data-ttu-id="6b1d5-107">O dispositivo já deve ter um PIN ou senha configurada antes de usar o bloqueio remoto.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-107">The device must already have a PIN or passcode set on it before you can use remote lock.</span></span>

<span data-ttu-id="6b1d5-108">A tabela abaixo lista como o bloqueio remoto funciona em diferentes plataformas móveis.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-108">The following table lists how remote lock works on different mobile platforms.</span></span>

|<span data-ttu-id="6b1d5-109">Plataforma</span><span class="sxs-lookup"><span data-stu-id="6b1d5-109">Platform</span></span>|<span data-ttu-id="6b1d5-110">Bloqueio remoto</span><span class="sxs-lookup"><span data-stu-id="6b1d5-110">Remote lock</span></span>|
|------------|---------------|
|<span data-ttu-id="6b1d5-111">macOS</span><span class="sxs-lookup"><span data-stu-id="6b1d5-111">macOS</span></span>|<span data-ttu-id="6b1d5-112">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-112">Not supported</span></span>|
|<span data-ttu-id="6b1d5-113">iOS</span><span class="sxs-lookup"><span data-stu-id="6b1d5-113">iOS</span></span>|<span data-ttu-id="6b1d5-114">Com suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-114">Supported</span></span>|
|<span data-ttu-id="6b1d5-115">Android</span><span class="sxs-lookup"><span data-stu-id="6b1d5-115">Android</span></span>|<span data-ttu-id="6b1d5-116">Com suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-116">Supported</span></span>|
|<span data-ttu-id="6b1d5-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="6b1d5-117">Android for Work</span></span>|<span data-ttu-id="6b1d5-118">Com suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-118">Supported</span></span>|
|<span data-ttu-id="6b1d5-119">Windows 10 (mobile)</span><span class="sxs-lookup"><span data-stu-id="6b1d5-119">Windows 10 (mobile)</span></span>|<span data-ttu-id="6b1d5-120">Com suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-120">Supported</span></span>|
|<span data-ttu-id="6b1d5-121">Windows 10 (desktop)</span><span class="sxs-lookup"><span data-stu-id="6b1d5-121">Windows 10 (desktop)</span></span>|<span data-ttu-id="6b1d5-122">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-122">Not supported</span></span>|
|<span data-ttu-id="6b1d5-123">Windows Phone 8 e Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="6b1d5-123">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="6b1d5-124">Com suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-124">Supported</span></span>|
|<span data-ttu-id="6b1d5-125">Windows RT 8.1 e Windows RT</span><span class="sxs-lookup"><span data-stu-id="6b1d5-125">Windows RT 8.1 and Windows RT</span></span>|<span data-ttu-id="6b1d5-126">Suportado se o usuário atual do dispositivo for o mesmo usuário que registrou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-126">Supported if the current user of the device is the same user who enrolled the device.</span></span>|
|<span data-ttu-id="6b1d5-127">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6b1d5-127">Windows 8.1</span></span>|<span data-ttu-id="6b1d5-128">Suportado se o usuário atual do dispositivo for o mesmo usuário que registrou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-128">Supported if the current user of the device is the same user who enrolled the device.</span></span>|

<span data-ttu-id="6b1d5-129">Não há suporte para o bloqueio remoto para computadores com Windows registrados com o cliente de software do Intune.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-129">Remote lock is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <span data-ttu-id="6b1d5-130">Para bloquear um dispositivo móvel remotamente usando o console do Intune</span><span class="sxs-lookup"><span data-stu-id="6b1d5-130">Lock a mobile device remotely through the Intune console</span></span>
<a id="lock-a-mobile-device-remotely-through-the-intune-console" class="xliff"></a>

1.  <span data-ttu-id="6b1d5-131">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-131">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="6b1d5-132">Clique em **Todos os Dispositivos Gerenciados Diretamente** para exibir os dispositivos registrados no Intune ou **Todos os Dispositivos de Gerenciados pelo Exchange ActiveSync**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-132">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6b1d5-133">Você também pode navegar para um dispositivo por usuário.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-133">You can also navigate to a device by user.</span></span> <span data-ttu-id="6b1d5-134">Escolha **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-134">Choose **All Users**.</span></span> <span data-ttu-id="6b1d5-135">Na página de propriedades do usuário, escolha **Dispositivos** e selecione o nome do dispositivo móvel que deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-135">On the user's properties page, choose **Devices**, and then choose the name of the mobile device you want to lock.</span></span>

3.  <span data-ttu-id="6b1d5-136">Na lista, clique no dispositivo ou nos dispositivos que deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-136">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="6b1d5-137">Na barra de tarefas, escolha **Tarefas Remotas** e selecione **Bloqueio Remoto**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-137">On the taskbar, choose **Remote Tasks** and select **Remote Lock**.</span></span>

## <span data-ttu-id="6b1d5-138">Redefinir a senha em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="6b1d5-138">Reset the passcode on a device</span></span>
<a id="reset-the-passcode-on-a-device" class="xliff"></a>
<span data-ttu-id="6b1d5-139">Se um usuário esquecer a senha, você poderá ajudá-lo removendo a senha de um dispositivo ou impondo uma nova senha temporária em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-139">If a user forgets a passcode, you can help by removing the passcode from a device or by forcing a new temporary passcode on a device.</span></span> <span data-ttu-id="6b1d5-140">A tabela a seguir lista como a redefinição de senha funciona em diferentes plataformas remotas.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-140">The following table lists how passcode reset works on different mobile platforms.</span></span>

|<span data-ttu-id="6b1d5-141">Plataforma</span><span class="sxs-lookup"><span data-stu-id="6b1d5-141">Platform</span></span>|<span data-ttu-id="6b1d5-142">Redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="6b1d5-142">Passcode reset</span></span>|
|------------|------------------|
|<span data-ttu-id="6b1d5-143">macOS</span><span class="sxs-lookup"><span data-stu-id="6b1d5-143">macOS</span></span>|<span data-ttu-id="6b1d5-144">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-144">Not supported</span></span>|
|<span data-ttu-id="6b1d5-145">iOS</span><span class="sxs-lookup"><span data-stu-id="6b1d5-145">iOS</span></span>|<span data-ttu-id="6b1d5-146">Suportado para limpar a senha de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-146">Supported for clearing the passcode from a device.</span></span> <span data-ttu-id="6b1d5-147">Não cria uma nova senha temporária.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-147">Does not create a new temporary passcode.</span></span>|
|<span data-ttu-id="6b1d5-148">Android</span><span class="sxs-lookup"><span data-stu-id="6b1d5-148">Android</span></span>|<span data-ttu-id="6b1d5-149">Suporte em versões anteriores ao Android 7.0.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-149">Supported on versions earlier than Android 7.0.</span></span> <span data-ttu-id="6b1d5-150">Cria uma senha temporária.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-150">Creates a temporary passcode.</span></span>|
|<span data-ttu-id="6b1d5-151">Android for Work</span><span class="sxs-lookup"><span data-stu-id="6b1d5-151">Android for Work</span></span>|<span data-ttu-id="6b1d5-152">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-152">Not supported</span></span>|
|<span data-ttu-id="6b1d5-153">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="6b1d5-153">Windows 10 mobile</span></span>|<span data-ttu-id="6b1d5-154">Suporte para dispositivos móveis com a versão do Windows 10 para Criadores e posteriores ingressados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-154">Supported for Windows 10 Creator version and later mobile devices that are Azure AD joined.</span></span>|
|<span data-ttu-id="6b1d5-155">Windows Phone 8 e Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="6b1d5-155">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="6b1d5-156">Com suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-156">Supported</span></span>|
|<span data-ttu-id="6b1d5-157">Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="6b1d5-157">Windows RT 8.1</span></span>|<span data-ttu-id="6b1d5-158">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-158">Not Supported</span></span>|
|<span data-ttu-id="6b1d5-159">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6b1d5-159">Windows 8.1</span></span>|<span data-ttu-id="6b1d5-160">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-160">Not Supported</span></span>|
|<span data-ttu-id="6b1d5-161">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="6b1d5-161">Windows 10 desktop</span></span>|<span data-ttu-id="6b1d5-162">Sem suporte</span><span class="sxs-lookup"><span data-stu-id="6b1d5-162">Not Supported</span></span>|

<span data-ttu-id="6b1d5-163">Não há suporte para a redefinição de senha para computadores com Windows registrados com o cliente de software do Intune.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-163">Passcode reset is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <span data-ttu-id="6b1d5-164">Redefinir uma senha</span><span class="sxs-lookup"><span data-stu-id="6b1d5-164">Reset a passcode</span></span>
<a id="reset-a-passcode" class="xliff"></a>

1.  <span data-ttu-id="6b1d5-165">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos Móveis**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-165">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="6b1d5-166">Clique em **Todos os Dispositivos Gerenciados Diretamente** para exibir os dispositivos registrados no Intune ou **Todos os Dispositivos de Gerenciados pelo Exchange ActiveSync**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-166">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="6b1d5-167">Você também pode navegar para um dispositivo por usuário.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-167">You can also navigate to a device by user.</span></span> <span data-ttu-id="6b1d5-168">Clique em **Todos os Usuários**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-168">Click **All Users**.</span></span> <span data-ttu-id="6b1d5-169">Na página de propriedades do usuário, clique em **Dispositivos** e clique no nome do dispositivo móvel que deseja apagar.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-169">On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.</span></span>

3.  <span data-ttu-id="6b1d5-170">Na lista, clique no dispositivo ou nos dispositivos que deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-170">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="6b1d5-171">Na barra de tarefas, escolha **Tarefas Remotas** e selecione **Redefinição de Senha**.</span><span class="sxs-lookup"><span data-stu-id="6b1d5-171">On the taskbar, choose **Remote Tasks** and select **Passcode Reset**.</span></span>


### <span data-ttu-id="6b1d5-172">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6b1d5-172">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="6b1d5-173">Desativar dispositivos](retire-devices-from-microsoft-intune-management.md) e [Apagamento seletivo do Windows para o gerenciamento de dados de dispositivos</span><span class="sxs-lookup"><span data-stu-id="6b1d5-173">Retire devices](retire-devices-from-microsoft-intune-management.md) and [Windows Selective Wipe for Device Data Management</span></span>](http://technet.microsoft.com/library/dn486874.aspx)
