---
title: "Mensagens do Portal da Empresa que os usuários podem ver no Android"
description: "Descreve as mensagens do aplicativo Portal da Empresa que os usuários finais do Intune podem ver."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.openlocfilehash: ae0bd848413fc82f68f2ce6e6ac55fe92b9cb989
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b124b-103">Ajudar usuários finais a compreender as mensagens do aplicativo do Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="b124b-103">Help end users understand Company Portal app messages</span></span>
<a id="help-end-users-understand-company-portal-app-messages" class="xliff"></a>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> <span data-ttu-id="b124b-104">As informações a seguir aplicam-se somente aos dispositivos com Android 6.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="b124b-104">The following information applies only on devices with Android 6.0+.</span></span>

<span data-ttu-id="b124b-105">Em pontos diferentes no processo de registro, os usuários finais verão duas mensagens diferentes que podem ser motivo de preocupação.</span><span class="sxs-lookup"><span data-stu-id="b124b-105">At different points in the enrollment process, end users will see two different messages that could be cause for concern.</span></span>

- <span data-ttu-id="b124b-106">__Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?__</span><span class="sxs-lookup"><span data-stu-id="b124b-106">__Allow Company Portal to make and manage phone calls?__</span></span>
- <span data-ttu-id="b124b-107">__Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?__</span><span class="sxs-lookup"><span data-stu-id="b124b-107">__Allow Company Portal to access photos, media, and files on your device?__</span></span>

## <span data-ttu-id="b124b-108">Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?</span><span class="sxs-lookup"><span data-stu-id="b124b-108">Allow Company Portal to make and manage phone calls?</span></span>
<a id="allow-company-portal-to-make-and-manage-phone-calls" class="xliff"></a>

### <span data-ttu-id="b124b-109">Onde ele aparece</span><span class="sxs-lookup"><span data-stu-id="b124b-109">Where it appears</span></span>
<a id="where-it-appears" class="xliff"></a>
<span data-ttu-id="b124b-110">A mensagem **Permitir que o Portal da Empresa faça e gerencie chamadas telefônicas?** é exibida quando os usuários tocam em **Registrar** no aplicativo do Portal da Empresa enquanto estão registrando o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b124b-110">The message **Allow Company Portal to make and manage phone calls?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.</span></span>

### <span data-ttu-id="b124b-111">O que significa</span><span class="sxs-lookup"><span data-stu-id="b124b-111">What it means</span></span>
<a id="what-it-means" class="xliff"></a>
<span data-ttu-id="b124b-112">Ao aceitar este aviso, os usuários permitirão que o IMEI e o número de telefone de seus dispositivos sejam enviados ao serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b124b-112">By accepting this prompt, users allow their device's phone and IMEI numbers to be sent to the Intune service.</span></span> <span data-ttu-id="b124b-113">Eles aparecerão no console do administrador na página __Hardware__.</span><span class="sxs-lookup"><span data-stu-id="b124b-113">These will appear on the admin console on the __Hardware__ page.</span></span>

> [!NOTE]
> <span data-ttu-id="b124b-114">**O aplicativo de Portal da Empresa nunca faz ou gerencia chamadas telefônicas!**</span><span class="sxs-lookup"><span data-stu-id="b124b-114">**The Company Portal app never makes or manages phone calls!**</span></span> <span data-ttu-id="b124b-115">O texto da mensagem é controlado pelo Google e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="b124b-115">The message text is controlled by Google and cannot be changed.</span></span>

<span data-ttu-id="b124b-116">Para ver a página **Hardware**, vá para **Grupos** > **Todos os dispositivos móveis** > **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="b124b-116">To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Devices**.</span></span> <span data-ttu-id="b124b-117">Selecione o dispositivo do usuário e vá para **Exibir Propriedades** > **Hardware**.</span><span class="sxs-lookup"><span data-stu-id="b124b-117">Select the user's device, and go to **View Properties** > **Hardware**.</span></span>

### <span data-ttu-id="b124b-118">O que acontece se os usuários negarem o acesso</span><span class="sxs-lookup"><span data-stu-id="b124b-118">What happens if users deny access</span></span>
<a id="what-happens-if-users-deny-access" class="xliff"></a>
<span data-ttu-id="b124b-119">Se os usuários negarem acesso, eles poderão continuar a usar o aplicativo de Portal da Empresa e registrar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b124b-119">If users deny access, they can continue to use the Company Portal app and enroll their device.</span></span> <span data-ttu-id="b124b-120">No entanto, o IMEI e o número de telefone do dispositivo estarão em branco na página __Hardware__ no console do administrador.</span><span class="sxs-lookup"><span data-stu-id="b124b-120">However, the device phone number and IMEI number will be blank on the __Hardware__ page in the admin console.</span></span> <span data-ttu-id="b124b-121">Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para interromper o prompt.</span><span class="sxs-lookup"><span data-stu-id="b124b-121">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.</span></span>

<span data-ttu-id="b124b-122">Se os usuários permitem, mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entrarem no aplicativo do Portal da Empresa após o registro.</span><span class="sxs-lookup"><span data-stu-id="b124b-122">If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</span></span>

<span data-ttu-id="b124b-123">Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.</span><span class="sxs-lookup"><span data-stu-id="b124b-123">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.</span></span>

### <span data-ttu-id="b124b-124">Como explicar isso aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="b124b-124">How to explain this to your users</span></span>
<a id="how-to-explain-this-to-your-users" class="xliff"></a>
<span data-ttu-id="b124b-125">Peça para os usuários [registrarem seu dispositivo Android no Intune](/intune-user-help/enroll-your-device-in-intune-android) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b124b-125">Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.</span></span>

## <span data-ttu-id="b124b-126">Permitir que o Portal da Empresa acesse seus contatos?</span><span class="sxs-lookup"><span data-stu-id="b124b-126">Allow Company Portal to access your contacts?</span></span>
<a id="allow-company-portal-to-access-your-contacts" class="xliff"></a>

### <span data-ttu-id="b124b-127">Onde ele aparece</span><span class="sxs-lookup"><span data-stu-id="b124b-127">Where it appears</span></span>
<a id="where-it-appears" class="xliff"></a>
<span data-ttu-id="b124b-128">A mensagem **Permitir que o Portal da Empresa acesse seus contatos?** é exibida quando os usuários tocam em **Registrar** no aplicativo do Portal da Empresa enquanto estão registrando o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b124b-128">The message **Allow Company Portal to access your contacts?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.</span></span>

### <span data-ttu-id="b124b-129">O que significa</span><span class="sxs-lookup"><span data-stu-id="b124b-129">What it means</span></span>
<a id="what-it-means" class="xliff"></a>
<span data-ttu-id="b124b-130">Ao aceitar este prompt, os usuários permitem que o Intune crie sua conta de trabalho e gerencie a identidade do Azure Active Directory que está registrada para o usuário no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b124b-130">By accepting this prompt, users allow Intune to create their work account and manage the Azure Active Directory identity that is registered for the user on that device.</span></span>

> [!NOTE]
> <span data-ttu-id="b124b-131">**A Microsoft nunca acessa seus contatos!**</span><span class="sxs-lookup"><span data-stu-id="b124b-131">**Microsoft never accesses your contacts!**</span></span> <span data-ttu-id="b124b-132">O texto da mensagem é controlado pelo Google e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="b124b-132">The message text is controlled by Google and cannot be changed.</span></span>

### <span data-ttu-id="b124b-133">O que acontece se os usuários negarem o acesso</span><span class="sxs-lookup"><span data-stu-id="b124b-133">What happens if users deny access</span></span>
<a id="what-happens-if-users-deny-access" class="xliff"></a>
<span data-ttu-id="b124b-134">Se os usuários negarem o acesso, seu dispositivo não será registrado no Intune e não poderá ser gerenciado.</span><span class="sxs-lookup"><span data-stu-id="b124b-134">If users deny access, their device will not be enrolled in Intune and cannot be managed.</span></span> <span data-ttu-id="b124b-135">Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para interromper o prompt.</span><span class="sxs-lookup"><span data-stu-id="b124b-135">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.</span></span>

<span data-ttu-id="b124b-136">Se os usuários permitem, mas posteriormente negam o acesso, a mensagem é exibida na próxima vez que os usuários entrarem no aplicativo do Portal da Empresa após o registro.</span><span class="sxs-lookup"><span data-stu-id="b124b-136">If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</span></span>

<span data-ttu-id="b124b-137">Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Telefone** e ativar a permissão.</span><span class="sxs-lookup"><span data-stu-id="b124b-137">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.</span></span>

### <span data-ttu-id="b124b-138">Como explicar isso aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="b124b-138">How to explain this to your users</span></span>
<a id="how-to-explain-this-to-your-users" class="xliff"></a>
<span data-ttu-id="b124b-139">Peça para os usuários [registrarem seu dispositivo Android no Intune](/intune-user-help/enroll-your-device-in-intune-android) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b124b-139">Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.</span></span>

## <span data-ttu-id="b124b-140">Permitir que o Portal da empresa acesse fotos, mídia e arquivos em seu dispositivo?</span><span class="sxs-lookup"><span data-stu-id="b124b-140">Allow Company Portal to access photos, media, and files on your device?</span></span>
<a id="allow-company-portal-to-access-photos-media-and-files-on-your-device" class="xliff"></a>

### <span data-ttu-id="b124b-141">Onde ele aparece</span><span class="sxs-lookup"><span data-stu-id="b124b-141">Where it appears</span></span>
<a id="where-it-appears" class="xliff"></a>
<span data-ttu-id="b124b-142">A mensagem **Permitir que o Portal da Empresa acesse fotos, mídia e arquivos em seu dispositivo?** é exibida quando os usuários tocam em **Enviar dados** para enviar logs ao administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="b124b-142">The message **Allow Company Portal to access photos, media, and files on your device?** appears when users tap **Send Data** to send logs to their IT admin.</span></span>

### <span data-ttu-id="b124b-143">O que significa</span><span class="sxs-lookup"><span data-stu-id="b124b-143">What it means</span></span>
<a id="what-it-means" class="xliff"></a>
<span data-ttu-id="b124b-144">Ao aceitar este prompt, os usuários permitem que seu dispositivo grave logs de dados no cartão SD do dispositivo e que habilite esses logs a serem movidos usando um cabo USB.</span><span class="sxs-lookup"><span data-stu-id="b124b-144">By accepting this prompt, users allow their device to write data logs to the device's SD card and enable those logs to be moved using a USB cable.</span></span>   

> [!NOTE]
> <span data-ttu-id="b124b-145">**O aplicativo do Portal da Empresa nunca acessa fotos, mídia e arquivos dos usuários!**</span><span class="sxs-lookup"><span data-stu-id="b124b-145">**The Company Portal app never accesses users' photos, media, and files!**</span></span> <span data-ttu-id="b124b-146">O texto da mensagem é controlado pelo Google e não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="b124b-146">The message text is controlled by Google and cannot be changed.</span></span>

### <span data-ttu-id="b124b-147">O que acontece se os usuários negarem o acesso</span><span class="sxs-lookup"><span data-stu-id="b124b-147">What happens if users deny access</span></span>
<a id="what-happens-if-users-deny-access" class="xliff"></a>
<span data-ttu-id="b124b-148">Se os usuários negarem o acesso, eles ainda podem enviar logs de dados por email, mas os logs não serão copiados para o cartão SD do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b124b-148">If users deny access, they can still send data logs via email, but the logs won't be copied to the device's SD card.</span></span>

<span data-ttu-id="b124b-149">Na segunda vez que os usuários entrarem no aplicativo Portal da Empresa após negarem acesso, a mensagem exibe uma caixa de seleção **Nunca Perguntar Novamente** que os usuários podem selecionar para que a mensagem nunca seja exibida novamente.</span><span class="sxs-lookup"><span data-stu-id="b124b-149">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</span></span> <span data-ttu-id="b124b-150">Se os usuários permitirem, mas posteriormente negarem o acesso, a mensagem será exibida na próxima vez que os usuários tentarem enviar logs.</span><span class="sxs-lookup"><span data-stu-id="b124b-150">If users allow, but then later deny access, the message appears the next time users try to send logs.</span></span> <span data-ttu-id="b124b-151">Se os usuários decidirem posteriormente permitir o acesso, eles poderão acessar **Configurações** > **Aplicativos** > **Portal da Empresa** > **Permissões** > **Armazenamento** e ativar a permissão.</span><span class="sxs-lookup"><span data-stu-id="b124b-151">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.</span></span>


### <span data-ttu-id="b124b-152">Como explicar isso aos seus usuários</span><span class="sxs-lookup"><span data-stu-id="b124b-152">How to explain this to your users</span></span>
<a id="how-to-explain-this-to-your-users" class="xliff"></a>
<span data-ttu-id="b124b-153">Peça aos usuários para [enviarem logs para o administrador de TI por email](/intune-user-help/send-logs-to-your-it-admin-by-email-android).</span><span class="sxs-lookup"><span data-stu-id="b124b-153">Send your users to [Send logs to your IT admin by email](/intune-user-help/send-logs-to-your-it-admin-by-email-android).</span></span> <span data-ttu-id="b124b-154">Você também pode pedir que eles [enviem logs para o administrador de TI por cabo](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) se quiser permitir que eles comparem os dois métodos.</span><span class="sxs-lookup"><span data-stu-id="b124b-154">You can also send them to [Send logs to your IT admin by cable](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) if you want to let them compare the two methods.</span></span>


### <span data-ttu-id="b124b-155">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b124b-155">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="b124b-156">O que dizer a seus usuários finais sobre como usar o Intune</span><span class="sxs-lookup"><span data-stu-id="b124b-156">What to tell your end users about using Intune</span></span>](/intune-classic/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)
