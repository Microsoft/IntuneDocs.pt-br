---
title: "Gerenciar o Bloqueio de Ativação do iOS em dispositivos"
description: "O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 7.1 e posterior."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3695e4c047edd9b788768db36184460f0e27d3bc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="9bfae-103">Ajude a proteger dispositivos iOS com bypass de Bloqueio de Ativação para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9bfae-103">Help protect iOS devices with Activation Lock bypass for Microsoft Intune</span></span>
<a id="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="9bfae-104">O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 8.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="9bfae-104">Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices.</span></span> <span data-ttu-id="9bfae-105">O Bloqueio de Ativação é habilitado automaticamente quando um usuário abre o aplicativo Buscar meu iPhone em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-105">Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device.</span></span> <span data-ttu-id="9bfae-106">Depois que ele for habilitado, a ID da Apple e a senha do usuário deverão ser inseridas antes que qualquer pessoa possa:</span><span class="sxs-lookup"><span data-stu-id="9bfae-106">After it is enabled, the user's Apple ID and password must be entered before anyone can:</span></span> 

-   <span data-ttu-id="9bfae-107">Desligar o Buscar meu iPhone</span><span class="sxs-lookup"><span data-stu-id="9bfae-107">Turn off Find My iPhone</span></span>

-   <span data-ttu-id="9bfae-108">Apagar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9bfae-108">Erase the device</span></span>

-   <span data-ttu-id="9bfae-109">Reativar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="9bfae-109">Reactivate the device</span></span>

## <span data-ttu-id="9bfae-110">Como o Bloqueio de Ativação afeta você</span><span class="sxs-lookup"><span data-stu-id="9bfae-110">How Activation Lock affects you</span></span>
<a id="how-activation-lock-affects-you" class="xliff"></a>
<span data-ttu-id="9bfae-111">Embora o Bloqueio de Ativação ajude a proteger dispositivos iOS e aumente a probabilidade de recuperação de um dispositivo perdido ou roubado, como administrador de TI, essa funcionalidade pode apresentar vários desafios.</span><span class="sxs-lookup"><span data-stu-id="9bfae-111">While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges.</span></span> <span data-ttu-id="9bfae-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="9bfae-112">For example:</span></span>

-   <span data-ttu-id="9bfae-113">Um usuário configura o Bloqueio de Ativação em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-113">A user sets up Activation Lock on a device.</span></span> <span data-ttu-id="9bfae-114">O usuário sai da empresa e retorna o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-114">The user then leaves the company and returns the device.</span></span> <span data-ttu-id="9bfae-115">Sem a ID da Apple e a senha do usuário, não é possível reativar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-115">Without the user's Apple ID and password, there is no way to reactivate the device.</span></span>

-   <span data-ttu-id="9bfae-116">Você precisa de um relatório de todos os dispositivos que têm o Bloqueio de Ativação habilitado.</span><span class="sxs-lookup"><span data-stu-id="9bfae-116">You need a report of all devices that have Activation Lock enabled.</span></span>

-   <span data-ttu-id="9bfae-117">Você deseja transferir alguns dispositivos para um outro departamento durante uma atualização do dispositivo na sua organização.</span><span class="sxs-lookup"><span data-stu-id="9bfae-117">You want to reassign some devices to a different department during a device refresh in your organization.</span></span> <span data-ttu-id="9bfae-118">Só é possível reatribuir dispositivos que não têm o Bloqueio de Ativação habilitado.</span><span class="sxs-lookup"><span data-stu-id="9bfae-118">You can only reassign devices that do not have Activation Lock enabled.</span></span>

<span data-ttu-id="9bfae-119">Para ajudar a resolver esses problemas, a Apple introduziu bypass de Bloqueio de Ativação no iOS 7.1.</span><span class="sxs-lookup"><span data-stu-id="9bfae-119">To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1.</span></span> <span data-ttu-id="9bfae-120">Isso permite remover o Bloqueio de Ativação de dispositivos supervisionados sem a ID Apple e a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="9bfae-120">This lets you remove the Activation Lock from supervised devices without the user's Apple ID and password.</span></span> <span data-ttu-id="9bfae-121">Dispositivos supervisionados podem gerar um código de bypass de Bloqueio de Ativação específico do dispositivo, que é armazenado no servidor de ativação da Apple.</span><span class="sxs-lookup"><span data-stu-id="9bfae-121">Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.</span></span>

> [!TIP]
> <span data-ttu-id="9bfae-122">O modo supervisionado para dispositivos iOS permite que você use o Apple Configurator para bloquear um dispositivo e limitar a funcionalidade para fins comerciais específicos.</span><span class="sxs-lookup"><span data-stu-id="9bfae-122">Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes.</span></span> <span data-ttu-id="9bfae-123">O modo supervisionado geralmente é somente para dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="9bfae-123">Supervised mode is generally only for corporate-owned devices.</span></span>

<span data-ttu-id="9bfae-124">Você pode ler mais sobre o Bloqueio de Ativação [aqui](https://support.apple.com/en-us/HT201365).</span><span class="sxs-lookup"><span data-stu-id="9bfae-124">You can read more about Activation Lock [here](https://support.apple.com/en-us/HT201365).</span></span>

## <span data-ttu-id="9bfae-125">Como o Intune ajuda você a gerenciar o Bloqueio de Ativação</span><span class="sxs-lookup"><span data-stu-id="9bfae-125">How Intune helps you manage Activation Lock</span></span>
<a id="how-intune-helps-you-manage-activation-lock" class="xliff"></a>
<span data-ttu-id="9bfae-126">O Intune pode solicitar o status do Bloqueio de Ativação de dispositivos supervisionados que executam o iOS 8.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="9bfae-126">Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later.</span></span> <span data-ttu-id="9bfae-127">Somente para dispositivos supervisionados, o Intune pode recuperar o código de bypass de Bloqueio de Ativação e emiti-lo diretamente para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-127">For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device.</span></span> <span data-ttu-id="9bfae-128">Se o dispositivo tiver sido apagado, será possível acessar diretamente o dispositivo usando um nome de usuário em branco e o código como a senha.</span><span class="sxs-lookup"><span data-stu-id="9bfae-128">If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.</span></span>

<span data-ttu-id="9bfae-129">**Os benefícios para o negócio são**:</span><span class="sxs-lookup"><span data-stu-id="9bfae-129">**The business benefits of this are**:</span></span>

-   <span data-ttu-id="9bfae-130">O usuário obtém os benefícios de segurança do aplicativo Buscar meu iPhone.</span><span class="sxs-lookup"><span data-stu-id="9bfae-130">The user gets the security benefits of the Find My iPhone app.</span></span>

-   <span data-ttu-id="9bfae-131">É possível permitir que usuários façam seu trabalho e saibam que, quando um dispositivo precisar ser realocado, será possível desativá-lo ou desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-131">You can enable users to do their work and know that when a device needs to be re-purposed, you can retire or unlock it.</span></span>

## <span data-ttu-id="9bfae-132">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9bfae-132">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="9bfae-133">Antes de ignorar o bloqueio de ativação em dispositivos, deverá habilitá-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="9bfae-133">Before you can bypass Activation Lock on devices, you must enable it first.</span></span> <span data-ttu-id="9bfae-134">Para fazer isto:</span><span class="sxs-lookup"><span data-stu-id="9bfae-134">To do this:</span></span>

1. <span data-ttu-id="9bfae-135">Use as informações no tópico [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="9bfae-135">Use the information in the topic [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).</span></span>
2. <span data-ttu-id="9bfae-136">Na seção **Registro** da página de configurações, defina os parâmetros de **Permitir Bloqueio de Ativação quando o dispositivo estiver no modo supervisionado** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="9bfae-136">In the **Enrollment** section, of the settings page, configure the setting **Allow Activation Lock when the device is in supervised mode** to **Yes**.</span></span>
3. <span data-ttu-id="9bfae-137">Salve a política e implante-a nos dispositivos nos quais você deseja gerenciar o bypass do bloqueio de ativação.</span><span class="sxs-lookup"><span data-stu-id="9bfae-137">Save the policy, and deploy it to the devices on which you want to manage Activation Lock bypass.</span></span>

## <span data-ttu-id="9bfae-138">Como usar o bypass de Bloqueio de Ativação do console do administrador do Intune</span><span class="sxs-lookup"><span data-stu-id="9bfae-138">How to use Activation Lock bypass from the Intune admin console</span></span>
<a id="how-to-use-activation-lock-bypass-from-the-intune-admin-console" class="xliff"></a>
> [!IMPORTANT]
> <span data-ttu-id="9bfae-139">Depois de efetuar bypass do Bloqueio de Ativação em um dispositivo, um novo Bloqueio de Ativação será aplicado automaticamente se o aplicativo Buscar meu iPhone for aberto.</span><span class="sxs-lookup"><span data-stu-id="9bfae-139">After you bypass the Activation Lock on a device, a new Activation Lock is automatically applied if the Find My iPhone app is opened.</span></span> <span data-ttu-id="9bfae-140">Por isso, **é necessário estar em posse física do dispositivo antes de seguir este procedimento**.</span><span class="sxs-lookup"><span data-stu-id="9bfae-140">Because of this, **you should be in physical possession of the device before you follow this procedure**.</span></span>

1.  <span data-ttu-id="9bfae-141">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos de Propriedade Corporativa**.</span><span class="sxs-lookup"><span data-stu-id="9bfae-141">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices**.</span></span>

2.  <span data-ttu-id="9bfae-142">Selecione o dispositivo cujo Bloqueio de Ativação você deseja efetuar bypass.</span><span class="sxs-lookup"><span data-stu-id="9bfae-142">Select the device whose Activation Lock you want to bypass.</span></span> <span data-ttu-id="9bfae-143">Escolha **Bypass do Bloqueio de Ativação**.</span><span class="sxs-lookup"><span data-stu-id="9bfae-143">Choose **Activation Lock Bypass**.</span></span>

3.  <span data-ttu-id="9bfae-144">Leia a mensagem de aviso.</span><span class="sxs-lookup"><span data-stu-id="9bfae-144">Read the warning message.</span></span> <span data-ttu-id="9bfae-145">Escolha **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="9bfae-145">Choose **Yes** to proceed.</span></span>

<span data-ttu-id="9bfae-146">Você pode examinar o status da solicitação de desbloqueio na página de detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-146">You can examine the status of the unlock request on the details page for the device.</span></span>

## <span data-ttu-id="9bfae-147">Como ver quais dispositivos estão usando o Bloqueio de Ativação</span><span class="sxs-lookup"><span data-stu-id="9bfae-147">How to see which devices are using Activation Lock</span></span>
<a id="how-to-see-which-devices-are-using-activation-lock" class="xliff"></a>
<span data-ttu-id="9bfae-148">Você pode ver quais dispositivos estão usando o Bloqueio de Ativação de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="9bfae-148">You can see which devices are using Activation Lock in two ways:</span></span>

-   <span data-ttu-id="9bfae-149">Execute **Relatórios de Inventário de Dispositivo Móvel**.</span><span class="sxs-lookup"><span data-stu-id="9bfae-149">Run the **Mobile Device Inventory Reports**.</span></span> <span data-ttu-id="9bfae-150">Este relatório exibe as colunas **Status do Bloqueio de Ativação** e **Supervisionado** para indicar o estado de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9bfae-150">This report displays the **Activation Lock Status** and **Supervised** columns to indicate the state of devices.</span></span> <span data-ttu-id="9bfae-151">Os valores de **Supervisionado** são **Sim** ou **Não**, e os valores do **Status do Bloqueio de Ativação** são:</span><span class="sxs-lookup"><span data-stu-id="9bfae-151">The values for **Supervised** are **Yes** or **No**, and the values for **Activation Lock Status** are:</span></span>

    -   <span data-ttu-id="9bfae-152">Habilitado com o código de bypass</span><span class="sxs-lookup"><span data-stu-id="9bfae-152">Enabled with bypass code</span></span>

    -   <span data-ttu-id="9bfae-153">Habilitado sem o código de bypass (dispositivo não supervisionado)</span><span class="sxs-lookup"><span data-stu-id="9bfae-153">Enabled without bypass code (device is not supervised)</span></span>

    -   <span data-ttu-id="9bfae-154">Habilitado sem o código de bypass (dispositivo não pode ser alcançado)</span><span class="sxs-lookup"><span data-stu-id="9bfae-154">Enabled without bypass code (device cannot be reached)</span></span>

    -   <span data-ttu-id="9bfae-155">Não habilitado</span><span class="sxs-lookup"><span data-stu-id="9bfae-155">Not enabled</span></span>

    <span data-ttu-id="9bfae-156">A caixa **Status do Bloqueio de Ativação** fica em branco para dispositivos que não executam o iOS 8.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="9bfae-156">The **Activation Lock Status** box is blank for devices that do not run iOS 8.0 or later.</span></span>

-   <span data-ttu-id="9bfae-157">Selecione um dispositivo em uma exibição de grupos para ver o status de Bloqueio de Ativação no painel de detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9bfae-157">Select a device in a groups view to see the Activation Lock status in the device details pane.</span></span>

    <span data-ttu-id="9bfae-158">Se selecionar um dispositivo no nó **Todos os Dispositivos Corporativos** e o Bloqueio de Ativação estiver habilitado para o dispositivo, você também poderá ver o código de bypass.</span><span class="sxs-lookup"><span data-stu-id="9bfae-158">If you select a device in the **All Corporate-owned Devices** node and Activation Lock is enabled for the device, you can also see the bypass code.</span></span> <span data-ttu-id="9bfae-159">Esse código pode ser usado para emitir manualmente um bypass de Bloqueio de Ativação.</span><span class="sxs-lookup"><span data-stu-id="9bfae-159">This code can be used to manually issue an Activation Lock bypass.</span></span>

    > [!IMPORTANT]
    ><span data-ttu-id="9bfae-160">O Intune faz o inventário dos dispositivos para o Bloqueio de Ativação a cada sete dias.</span><span class="sxs-lookup"><span data-stu-id="9bfae-160">Intune takes inventory from devices for Activation Lock every seven days.</span></span> <span data-ttu-id="9bfae-161">Por causa disso, os dispositivos podem não ser exibidos imediatamente com seu status de Bloqueio de Ativação no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="9bfae-161">Because of this, devices might not immediately be displayed with their Activation Lock status in the Intune console.</span></span>


### <span data-ttu-id="9bfae-162">Consulte também</span><span class="sxs-lookup"><span data-stu-id="9bfae-162">See also</span></span>
<a id="see-also" class="xliff"></a>
<span data-ttu-id="9bfae-163">[Desativar dispositivos](retire-devices-from-microsoft-intune-management.md)
[Ajude a proteger os dispositivos com bloqueio remoto e redefinição de senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="9bfae-163">[Retire devices](retire-devices-from-microsoft-intune-management.md)
[Help protect your devices with remote lock and passcode reset](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)</span></span>
