---
title: "Configurações de política do Exchange ActiveSync"
description: "Use a política do Exchange ActiveSync do Intune para definir as configurações que permitem controlar recursos e funcionalidades em dispositivos gerenciados pelo Exchange ActiveSync."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6bbb0cd7ca87a3c6cc352cbdd6dd2b61a9c5e36c
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7ac7c-103">Configurações de política do Exchange ActiveSync no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7ac7c-103">Exchange ActiveSync policy settings in Microsoft Intune</span></span>
<a id="exchange-activesync-policy-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="7ac7c-104">Use a política do **Exchange ActiveSync** do Microsoft Intune para definir configurações que controlam diversos recursos e funcionalidades em dispositivos que são gerenciados pelo Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-104">Use the Microsoft Intune **Exchange ActiveSync** policy to configure settings that control a range of features and functionality on devices that are managed by Exchange ActiveSync.</span></span>


## <span data-ttu-id="7ac7c-105">Configurações de senha</span><span class="sxs-lookup"><span data-stu-id="7ac7c-105">Password settings</span></span>
<a id="password-settings" class="xliff"></a>

|<span data-ttu-id="7ac7c-106">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="7ac7c-106">Setting name</span></span>|<span data-ttu-id="7ac7c-107">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7ac7c-107">Details</span></span>
|----------------|---|
|<span data-ttu-id="7ac7c-108">**Exigir uma senha para desbloquear os dispositivos móveis**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-108">**Require a password to unlock mobile devices**</span></span>|<span data-ttu-id="7ac7c-109">Especifica se os dispositivos devem ser bloqueados usando uma senha.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-109">Specifies whether devices must be locked by using a password.</span></span><br><span data-ttu-id="7ac7c-110">(não aplicável a dispositivos que executam o Windows RT).</span><span class="sxs-lookup"><span data-stu-id="7ac7c-110">(not applicable to devices running Windows RT).</span></span>|
|<span data-ttu-id="7ac7c-111">**Tipo de senha necessária**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-111">**Required password type**</span></span>|<span data-ttu-id="7ac7c-112">Especifica o tipo de senha necessária, por exemplo, apenas numérica ou alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-112">Specifies the type of password that will be required, such as numeric only or alphanumeric.</span></span>|
|<span data-ttu-id="7ac7c-113">**Comprimento mínimo da senha**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-113">**Minimum password length**</span></span>|<span data-ttu-id="7ac7c-114">Especifica o número mínimo de caracteres necessários na senha do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-114">Specifies the minimum number of required characters in the device password.</span></span>|
|<span data-ttu-id="7ac7c-115">**Permitir senha simples**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-115">**Allow simple passwords**</span></span>|<span data-ttu-id="7ac7c-116">Especifica se você pode usar senhas simples, que incluem '0000' e '1234'.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-116">Specifies whether you can use simple passwords, which include ‘0000’ and ‘1234’.</span></span>|
|<span data-ttu-id="7ac7c-117">**Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-117">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="7ac7c-118">Especifica o número de vezes em que o usuário pode inserir uma senha incorreta antes de apagar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-118">Specifies the number of times that a user can enter an incorrect password before the device is wiped.</span></span>|
|<span data-ttu-id="7ac7c-119">**Expiração da senha (dias)**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-119">**Password expiration (days)**</span></span>|<span data-ttu-id="7ac7c-120">Especifica o número de dias após os quais a senha do dispositivo deve ser alterada.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-120">Specifies the number of days after which the device password must be changed.</span></span>
|<span data-ttu-id="7ac7c-121">**Lembrar histórico de senha**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-121">**Remember password history**</span></span>|<span data-ttu-id="7ac7c-122">Especifica se deve ser permitido o uso de senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-122">Specifies whether to not allow the use of previously used passwords.</span></span>|
|<span data-ttu-id="7ac7c-123">**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-123">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="7ac7c-124">Especifica o número de senhas usadas anteriormente que não podem ser utilizadas novamente.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-124">Specifies the number of previously used passwords that can't be used again.</span></span>|
|<span data-ttu-id="7ac7c-125">**Minutos de inatividade antes de a senha ser necessária**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-125">**Minutes of inactivity before password is required**</span></span>|<span data-ttu-id="7ac7c-126">Especifica a quantidade de tempo que um dispositivo deve permanecer ocioso antes que a tela seja bloqueada.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-126">Specifies the amount of time that a device must be idle before the screen is locked.</span></span>

## <span data-ttu-id="7ac7c-127">Configurações de criptografia</span><span class="sxs-lookup"><span data-stu-id="7ac7c-127">Encryption settings</span></span>
<a id="encryption-settings" class="xliff"></a>

|<span data-ttu-id="7ac7c-128">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="7ac7c-128">Setting name</span></span>|<span data-ttu-id="7ac7c-129">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7ac7c-129">Details</span></span>|
|----------------|---|
|<span data-ttu-id="7ac7c-130">**Exigir criptografia no dispositivo móvel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="7ac7c-130">**Require encryption on mobile device**<sup>1</sup></span></span>|<span data-ttu-id="7ac7c-131">Requer que os dados em um dispositivo sejam criptografados quando tiverem suporte.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-131">Requires the data on a device to be encrypted when supported.</span></span><br><br><span data-ttu-id="7ac7c-132">Para dispositivos Windows Phone 8, defina como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-132">For Windows Phone 8 devices, you must set this to **Yes**.</span></span><br /><br /><span data-ttu-id="7ac7c-133">Para habilitar a criptografia em dispositivos iOS, habilite a configuração **Exigir uma senha para desbloquear dispositivos móveis**.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-133">To enable encryption on iOS devices, enable the **Require a password to unlock mobile devices** setting.</span></span>|
|<span data-ttu-id="7ac7c-134">**Exigir criptografia em cartões de armazenamento**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-134">**Require encryption on storage cards**</span></span>|<span data-ttu-id="7ac7c-135">Exige que os dados armazenados externamente, como em um cartão SD, sejam criptografados (em dispositivos com suporte).</span><span class="sxs-lookup"><span data-stu-id="7ac7c-135">Requires data that is stored on external storage such as an SD card to be encrypted (on supported devices).</span></span>
<span data-ttu-id="7ac7c-136"><sup>1</sup> Mais informações sobre dispositivos que executam o Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="7ac7c-136"><sup>1</sup> Additional information for devices that run Windows 8.1</span></span>

-   <span data-ttu-id="7ac7c-137">Se deseja impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](https://support.microsoft.com/kb/3013816) em cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-137">If you want to enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/kb/3013816) on each device.</span></span>

-   <span data-ttu-id="7ac7c-138">Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-138">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>

-   <span data-ttu-id="7ac7c-139">Se desejar que a criptografia funcione para Windows 8.1, o dispositivo deve atender aos requisitos de certificação de hardware [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-139">If you want encryption to work for Windows 8.1 devices, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.</span></span>

-   <span data-ttu-id="7ac7c-140">Se você impuser a criptografia em um dispositivo Windows 8.1, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-140">If you enforce encryption on a Windows 8.1 device, the recovery key is only accessible from the user's Microsoft account, which is accessed from the user's OneDrive account.</span></span> <span data-ttu-id="7ac7c-141">Não é possível recuperar essa chave em nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-141">You cannot recover this key on behalf of a user.</span></span>

## <span data-ttu-id="7ac7c-142">Configurações de email</span><span class="sxs-lookup"><span data-stu-id="7ac7c-142">Email settings</span></span>
<a id="email-settings" class="xliff"></a>

|<span data-ttu-id="7ac7c-143">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="7ac7c-143">Setting name</span></span>|<span data-ttu-id="7ac7c-144">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7ac7c-144">Details</span></span>
|----------------|---|
|<span data-ttu-id="7ac7c-145">**Permitir que os usuários baixem anexos de email**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-145">**Allow users to download email attachments**</span></span>|<span data-ttu-id="7ac7c-146">Especifica se anexos de email podem ser baixados no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-146">Specifies whether email attachments can be downloaded to the device.</span></span>|
|<span data-ttu-id="7ac7c-147">**Período de sincronização de email**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-147">**Email synchronization period**</span></span>|<span data-ttu-id="7ac7c-148">Especifica o número de dias de email recebido que serão sincronizados com o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-148">Specifies the number of days of received email that will be synchronized to the device.</span></span>
|<span data-ttu-id="7ac7c-149">**Permitir que dispositivos móveis que não dão suporte completo às configurações do Exchange ActiveSync sejam sincronizados com o Exchange**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-149">**Allow mobile devices that don’t fully support Exchange ActiveSync settings to synchronize with Exchange**</span></span>|<span data-ttu-id="7ac7c-150">Especifica se o acesso do Exchange deve ser permitido em dispositivos que não oferecem suporte a uma ou mais configurações do Exchange ActiveSync.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-150">Specifies whether to allow Exchange access on devices that don't support one or more Exchange ActiveSync settings.</span></span>

## <span data-ttu-id="7ac7c-151">Configurações do navegador</span><span class="sxs-lookup"><span data-stu-id="7ac7c-151">Browser settings</span></span>
<a id="browser-settings" class="xliff"></a>

|<span data-ttu-id="7ac7c-152">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="7ac7c-152">Setting name</span></span>|<span data-ttu-id="7ac7c-153">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7ac7c-153">Details</span></span>
|----------------|---|
|<span data-ttu-id="7ac7c-154">**Permitir o navegador da Web**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-154">**Allow web browser**</span></span>|<span data-ttu-id="7ac7c-155">Especifica se o navegador da Web no dispositivo pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-155">Specifies whether the web browser on the device can be used.</span></span><br><span data-ttu-id="7ac7c-156">(Não disponível para Windows RT ou Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="7ac7c-156">(Not available for Windows RT or Windows Phone).</span></span>

## <span data-ttu-id="7ac7c-157">Configurações de hardware</span><span class="sxs-lookup"><span data-stu-id="7ac7c-157">Hardware settings</span></span>
<a id="hardware-settings" class="xliff"></a>

|<span data-ttu-id="7ac7c-158">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="7ac7c-158">Setting name</span></span>|<span data-ttu-id="7ac7c-159">Detalhes</span><span class="sxs-lookup"><span data-stu-id="7ac7c-159">Details</span></span>
|----------------|---|
|<span data-ttu-id="7ac7c-160">**Permitir câmera**</span><span class="sxs-lookup"><span data-stu-id="7ac7c-160">**Allow camera**</span></span>|<span data-ttu-id="7ac7c-161">Especifica se a câmera no dispositivo pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="7ac7c-161">Specifies whether the camera on the device can be used.</span></span><br><span data-ttu-id="7ac7c-162">(Não disponível para Windows RT ou Windows Phone).</span><span class="sxs-lookup"><span data-stu-id="7ac7c-162">(Not available for Windows RT or Windows Phone).</span></span>



### <span data-ttu-id="7ac7c-163">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7ac7c-163">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="7ac7c-164">Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7ac7c-164">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
