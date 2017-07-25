---
title: "Ignorar o Bloqueio de Ativação do iOS com o Intune"
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para ignorar o Bloqueio de Ativação do iOS para acessar dispositivos bloqueados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0b92949efca2e4dac5836755e2f32b0527d4762d
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="fadf5-103">Ignorar o Bloqueio de Ativação em dispositivos iOS supervisionados com o Intune</span><span class="sxs-lookup"><span data-stu-id="fadf5-103">Bypass Activation Lock on supervised iOS devices with Intune</span></span>
<a id="bypass-activation-lock-on-supervised-ios-devices-with-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="fadf5-104">O Microsoft Intune pode ajudar a gerenciar o Bloqueio de Ativação do iOS, um recurso do aplicativo Buscar meu iPhone para dispositivos iOS 8.0 e posteriores.</span><span class="sxs-lookup"><span data-stu-id="fadf5-104">Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices.</span></span> <span data-ttu-id="fadf5-105">O Bloqueio de Ativação é habilitado automaticamente quando um usuário abre o aplicativo Buscar meu iPhone em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-105">Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device.</span></span> <span data-ttu-id="fadf5-106">Depois que ele for habilitado, a ID da Apple e a senha do usuário deverão ser inseridas antes que qualquer pessoa possa:</span><span class="sxs-lookup"><span data-stu-id="fadf5-106">After it is enabled, the user's Apple ID and password must be entered before anyone can:</span></span>

- <span data-ttu-id="fadf5-107">Desligar o Buscar meu iPhone</span><span class="sxs-lookup"><span data-stu-id="fadf5-107">Turn off Find My iPhone</span></span>
- <span data-ttu-id="fadf5-108">Apagar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="fadf5-108">Erase the device</span></span>
- <span data-ttu-id="fadf5-109">Reativar o dispositivo</span><span class="sxs-lookup"><span data-stu-id="fadf5-109">Reactivate the device</span></span>

## <span data-ttu-id="fadf5-110">Como o Bloqueio de Ativação afeta você</span><span class="sxs-lookup"><span data-stu-id="fadf5-110">How Activation Lock affects you</span></span>
<a id="how-activation-lock-affects-you" class="xliff"></a>

<span data-ttu-id="fadf5-111">Embora o Bloqueio de Ativação ajude a proteger dispositivos iOS e aumente a probabilidade de recuperação de um dispositivo perdido ou roubado, como administrador de TI, essa funcionalidade pode apresentar vários desafios.</span><span class="sxs-lookup"><span data-stu-id="fadf5-111">While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges.</span></span> <span data-ttu-id="fadf5-112">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="fadf5-112">For example:</span></span>

- <span data-ttu-id="fadf5-113">Um usuário configura o Bloqueio de Ativação em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-113">A user sets up Activation Lock on a device.</span></span> <span data-ttu-id="fadf5-114">O usuário sai da empresa e retorna o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-114">The user then leaves the company and returns the device.</span></span> <span data-ttu-id="fadf5-115">Sem a ID da Apple e a senha do usuário, não é possível reativar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-115">Without the user's Apple ID and password, there is no way to reactivate the device.</span></span>
- <span data-ttu-id="fadf5-116">Você precisa de um relatório de todos os dispositivos que têm o Bloqueio de Ativação habilitado.</span><span class="sxs-lookup"><span data-stu-id="fadf5-116">You need a report of all devices that have Activation Lock enabled.</span></span>
- <span data-ttu-id="fadf5-117">Você deseja transferir alguns dispositivos para um outro departamento durante uma atualização do dispositivo na sua organização.</span><span class="sxs-lookup"><span data-stu-id="fadf5-117">You want to reassign some devices to a different department during a device refresh in your organization.</span></span> <span data-ttu-id="fadf5-118">Só é possível reatribuir dispositivos que não têm o Bloqueio de Ativação habilitado.</span><span class="sxs-lookup"><span data-stu-id="fadf5-118">You can only reassign devices that do not have Activation Lock enabled.</span></span>

<span data-ttu-id="fadf5-119">Para ajudar a resolver esses problemas, a Apple introduziu bypass de Bloqueio de Ativação no iOS 7.1.</span><span class="sxs-lookup"><span data-stu-id="fadf5-119">To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1.</span></span> <span data-ttu-id="fadf5-120">Isso permite remover o Bloqueio de Ativação de dispositivos supervisionados sem a ID Apple e a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="fadf5-120">This lets you remove the Activation Lock from supervised devices without the user's Apple ID and password.</span></span> <span data-ttu-id="fadf5-121">Dispositivos supervisionados podem gerar um código de bypass de Bloqueio de Ativação específico do dispositivo, que é armazenado no servidor de ativação da Apple.</span><span class="sxs-lookup"><span data-stu-id="fadf5-121">Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.</span></span>

>[!TIP]
><span data-ttu-id="fadf5-122">O modo supervisionado para dispositivos iOS permite que você use o Apple Configurator para bloquear um dispositivo e limitar a funcionalidade para fins comerciais específicos.</span><span class="sxs-lookup"><span data-stu-id="fadf5-122">Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes.</span></span> <span data-ttu-id="fadf5-123">O modo supervisionado geralmente é somente para dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="fadf5-123">Supervised mode is generally only for corporate-owned devices.</span></span>

<span data-ttu-id="fadf5-124">Leia mais sobre o Bloqueio de Ativação no [site da Apple](https://support.apple.com/HT201365).</span><span class="sxs-lookup"><span data-stu-id="fadf5-124">You can read more about Activation Lock on [Apple's web site](https://support.apple.com/HT201365).</span></span>

## <span data-ttu-id="fadf5-125">Como o Intune ajuda você a gerenciar o Bloqueio de Ativação</span><span class="sxs-lookup"><span data-stu-id="fadf5-125">How Intune helps you manage Activation Lock</span></span>
<a id="how-intune-helps-you-manage-activation-lock" class="xliff"></a>
<span data-ttu-id="fadf5-126">O Intune pode solicitar o status do Bloqueio de Ativação de dispositivos supervisionados que executam o iOS 8.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="fadf5-126">Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later.</span></span> <span data-ttu-id="fadf5-127">Somente para dispositivos supervisionados, o Intune pode recuperar o código de bypass de Bloqueio de Ativação e emiti-lo diretamente para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-127">For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device.</span></span> <span data-ttu-id="fadf5-128">Se o dispositivo tiver sido apagado, será possível acessar diretamente o dispositivo usando um nome de usuário em branco e o código como a senha.</span><span class="sxs-lookup"><span data-stu-id="fadf5-128">If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.</span></span>

<span data-ttu-id="fadf5-129">**Os benefícios para o negócio são:**</span><span class="sxs-lookup"><span data-stu-id="fadf5-129">**The business benefits of this are:**</span></span>

- <span data-ttu-id="fadf5-130">O usuário obtém os benefícios de segurança do aplicativo Buscar meu iPhone.</span><span class="sxs-lookup"><span data-stu-id="fadf5-130">The user gets the security benefits of the Find My iPhone app.</span></span>
- <span data-ttu-id="fadf5-131">É possível permitir que usuários façam seu trabalho e saibam que, quando um dispositivo precisar ser realocado, será possível desativá-lo ou desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-131">You can enable users to do their work and know that when a device needs to be re-purposed, you can retire or unlock it.</span></span>

## <span data-ttu-id="fadf5-132">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="fadf5-132">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="fadf5-133">Antes de ignorar o bloqueio de ativação em dispositivos, deverá habilitá-lo primeiro.</span><span class="sxs-lookup"><span data-stu-id="fadf5-133">Before you can bypass Activation Lock on devices, you must enable it first.</span></span> <span data-ttu-id="fadf5-134">Para fazer isto:</span><span class="sxs-lookup"><span data-stu-id="fadf5-134">To do this:</span></span>

1. <span data-ttu-id="fadf5-135">Configure um perfil de restrição de dispositivo do Intune para o iOS usando as informações em [Como definir as configurações de restrição de dispositivo](/intune-azure/configure-devices/how-to-configure-device-restrictions).</span><span class="sxs-lookup"><span data-stu-id="fadf5-135">Configure an Intune device restriction profile for iOS using the information in [How to configure device restriction settings](/intune-azure/configure-devices/how-to-configure-device-restrictions).</span></span>
2. <span data-ttu-id="fadf5-136">Habilite a configuração do modo de **Quiosque** **Bloqueio de Ativação**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-136">Enable the **Kiosk** mode setting **Activation Lock**.</span></span>
3. <span data-ttu-id="fadf5-137">Salve o perfil e, depois, atribua-o aos dispositivos nos quais você deseja gerenciar o bypass do Bloqueio de Ativação.</span><span class="sxs-lookup"><span data-stu-id="fadf5-137">Save the profile, and then assign it to the devices on which you want to manage Activation Lock bypass.</span></span>


## <span data-ttu-id="fadf5-138">Como usar o bypass do Bloqueio de Ativação</span><span class="sxs-lookup"><span data-stu-id="fadf5-138">How to use Activation Lock bypass</span></span>
<a id="how-to-use-activation-lock-bypass" class="xliff"></a>

>[!IMPORTANT]
><span data-ttu-id="fadf5-139">Depois de efetuar bypass do Bloqueio de Ativação em um dispositivo, um novo Bloqueio de Ativação será aplicado automaticamente se o aplicativo Buscar meu iPhone for aberto.</span><span class="sxs-lookup"><span data-stu-id="fadf5-139">After you bypass the Activation Lock on a device, a new Activation Lock is automatically applied if the Find My iPhone app is opened.</span></span> <span data-ttu-id="fadf5-140">Por isso, **é necessário estar em posse física do dispositivo antes de seguir este procedimento**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-140">Because of this, **you should be in physical possession of the device before you follow this procedure**.</span></span>

<span data-ttu-id="fadf5-141">A ação remota de dispositivo **Ignorar Bloqueio de Ativação** do Intune remove o bloqueio de ativação de um dispositivo iOS sem a ID da Apple e a senha do usuário.</span><span class="sxs-lookup"><span data-stu-id="fadf5-141">The Intune **Bypass Activation Lock** remote device action removes the activation lock from an iOS device without the user’s Apple ID and password.</span></span> <span data-ttu-id="fadf5-142">Depois de fazer o bypass do bloqueio de ativação, o dispositivo ativa-o novamente quando inicia o aplicativo o Localizar Meu iPhone.</span><span class="sxs-lookup"><span data-stu-id="fadf5-142">Once you bypass the activation lock, the device turns on activation lock again when the Find My iPhone app launches.</span></span> <span data-ttu-id="fadf5-143">Faça bypass do bloqueio de ativação apenas se você tiver acesso físico ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fadf5-143">Only bypass the activation lock if you have physical access to the device.</span></span>

1. <span data-ttu-id="fadf5-144">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="fadf5-144">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="fadf5-145">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-145">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="fadf5-146">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-146">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="fadf5-147">Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-147">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="fadf5-148">Na lista de dispositivos gerenciados, escolha um dispositivo iOS supervisionado e, em seguida, escolha a ação remota de dispositivo **Ignorar Bloqueio de Ativação**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-148">From the list of devices you manage, choose a supervised iOS device, and then choose the **Bypass Activation Lock** device remote action.</span></span>

<span data-ttu-id="fadf5-149">Examine o status da solicitação de desbloqueio na página de detalhes do dispositivo na carga de trabalho **Gerenciar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="fadf5-149">You can examine the status of the unlock request on the details page for the device in the **Manage devices** workload.</span></span>
