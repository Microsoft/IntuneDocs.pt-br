---
title: Desativar dispositivos
description: "O Intune dá suporte ao apagamento seletivo e ao apagamento completo para remover o dispositivo do gerenciamento do Intune removendo suas políticas e o portal da empresa."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dbec400-5d8a-47be-b892-7745811d9de2
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 493b5bfce7ab9b78f5f7c48d0d18524d1b191f1f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ffc91-103">Desativar dispositivos do gerenciamento do Intune</span><span class="sxs-lookup"><span data-stu-id="ffc91-103">Retire devices from Intune management</span></span>
<a id="retire-devices-from-intune-management" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ffc91-104">Quer os dispositivos sejam pessoais ou corporativos, chega o momento em que um dispositivo gerenciado precisa ser removido do gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="ffc91-104">Whether devices are corporate-owned or personally owned, eventually a managed device needs to be removed from Intune management.</span></span>

<span data-ttu-id="ffc91-105">Os dispositivos nunca serão removidos do Intune sem a intervenção do usuário, mesmo se eles não tiverem sido conectados ao serviço Intune por um período.</span><span class="sxs-lookup"><span data-stu-id="ffc91-105">Devices are never removed from Intune without your intervention, even if the devices haven't connected to the Intune service for a period of time.</span></span>

<span data-ttu-id="ffc91-106">Você pode ter que desativar um dispositivo por diversos motivos:</span><span class="sxs-lookup"><span data-stu-id="ffc91-106">You might need to retire a device for a variety of reasons:</span></span>

-   <span data-ttu-id="ffc91-107">O usuário deixa uma empresa de maneira planejada (partida "gerenciada")</span><span class="sxs-lookup"><span data-stu-id="ffc91-107">User leaves a company in a planned way (“managed” departure)</span></span>
-   <span data-ttu-id="ffc91-108">O usuário parte abruptamente (é demitido, pede demissão etc.).</span><span class="sxs-lookup"><span data-stu-id="ffc91-108">User leaves abruptly (gets fired, quits, etc.).</span></span>
-   <span data-ttu-id="ffc91-109">Perda de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ffc91-109">Loss of device</span></span>
-   <span data-ttu-id="ffc91-110">Realocação de um dispositivo (mudança para outro usuário, reutilização para uma finalidade diferente etc.)</span><span class="sxs-lookup"><span data-stu-id="ffc91-110">Repurpose of a device (move to another user, reuse for a different purpose, etc.)</span></span>

<span data-ttu-id="ffc91-111">Você pode executar um apagamento seletivo ou completo em um dispositivo gerenciado como um dispositivo móvel ou bloquear um dispositivo e redefinir a senha.</span><span class="sxs-lookup"><span data-stu-id="ffc91-111">You can do either a selective wipe or a full wipe on a device that's managed as a mobile device, or you can lock a device and reset its password.</span></span> <span data-ttu-id="ffc91-112">Apagando o dispositivo, você libera a assinatura do usuário para adicionar um dispositivo diferente.</span><span class="sxs-lookup"><span data-stu-id="ffc91-112">By wiping the device, you free up the user's subscription to add a different device.</span></span> <span data-ttu-id="ffc91-113">Você também pode desativar computadores gerenciados com o software cliente do Intune.</span><span class="sxs-lookup"><span data-stu-id="ffc91-113">You can also retire PCs that are managed with the Intune client software.</span></span>

## <span data-ttu-id="ffc91-114">Apagar dados e aplicativos dos dispositivos</span><span class="sxs-lookup"><span data-stu-id="ffc91-114">Wipe data and apps from devices</span></span>
<a id="wipe-data-and-apps-from-devices" class="xliff"></a>
<span data-ttu-id="ffc91-115">O apagamento seletivo e o apagamento completo removem o dispositivo do gerenciamento do Intune, removendo sua política e o portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="ffc91-115">Both a selective wipe and a full wipe remove the device from Intune management by removing its policy and the company portal.</span></span> <span data-ttu-id="ffc91-116">Como resultado, o dispositivo não tem mais as credenciais necessárias para entrar em recursos da empresa como o Microsoft SharePoint, email ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffc91-116">As a result, the device no longer has the necessary credentials to sign in to company resources like Microsoft SharePoint, email, or Office 365.</span></span>

<span data-ttu-id="ffc91-117">O [apagamento seletivo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) é a ação preferencial para funcionários que tiverem registrado seus próprios dispositivos no Intune, porque ela não afeta as informações pessoais no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ffc91-117">[Selective wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe) is the preferred action for employees who have enrolled their own devices in Intune because it does not affect personal information on the device.</span></span> <span data-ttu-id="ffc91-118">Somente dados corporativos são removidos.</span><span class="sxs-lookup"><span data-stu-id="ffc91-118">Only corporate data is removed.</span></span>

<span data-ttu-id="ffc91-119">Para dispositivos que precisam ser realocados, também é possível usar um [apagamento completo](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), que redefine o dispositivo para as configurações padrão de fábrica.</span><span class="sxs-lookup"><span data-stu-id="ffc91-119">For devices that need to be repurposed, you can also use a [full wipe](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe), which resets the device to factory default settings.</span></span>

### <span data-ttu-id="ffc91-120">Removendo licenças de usuário e dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="ffc91-120">Removing user licenses and managed devices</span></span>
<a id="removing-user-licenses-and-managed-devices" class="xliff"></a>
<span data-ttu-id="ffc91-121">Quando você remover uma licença de usuário, os dispositivos registrados do usuário não serão mais registrados.</span><span class="sxs-lookup"><span data-stu-id="ffc91-121">When you remove a user license, that user's enrolled devices cease to be enrolled.</span></span> <span data-ttu-id="ffc91-122">Como prática recomendada, você deve usar o apagamento seletivo para remover os dados da empresa de dispositivos gerenciados antes de remover a licença do Intune para um usuário.</span><span class="sxs-lookup"><span data-stu-id="ffc91-122">As a best practice, you should use selective wipe to remove company data from managed devices before removing the Intune license for a user.</span></span> <span data-ttu-id="ffc91-123">Quando você remover a licença de usuário, o dispositivo não pode ser alvo de ações remotas.</span><span class="sxs-lookup"><span data-stu-id="ffc91-123">Once you remove the user license, the device cannot be targeted for remote actions.</span></span>

## <span data-ttu-id="ffc91-124">Para excluir dispositivos no portal do Active Directory do Azure</span><span class="sxs-lookup"><span data-stu-id="ffc91-124">To delete devices in the Azure Active Directory portal</span></span>
<a id="to-delete-devices-in-the-azure-active-directory-portal" class="xliff"></a>

1.  <span data-ttu-id="ffc91-125">Entre com suas credenciais da organização em [http://aka.ms/accessaad](http://aka.ms/accessaad) ou [https://portal.office.com](https://portal.office.com) e escolha **Centros de Administração** &gt; **Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="ffc91-125">Sign in with your organization credentials to [http://aka.ms/accessaad](http://aka.ms/accessaad) or [https://portal.office.com](https://portal.office.com), and then choose **Admin centers** &gt; **Azure AD**.</span></span>

2.  <span data-ttu-id="ffc91-126">Se não tiver uma, crie uma assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="ffc91-126">Create an Azure subscription if you don’t have one.</span></span> <span data-ttu-id="ffc91-127">Isso não deve exigir um cartão de crédito ou pagamento se você tiver uma conta paga.</span><span class="sxs-lookup"><span data-stu-id="ffc91-127">This should not require a credit card or payment if you have a paid account.</span></span> <span data-ttu-id="ffc91-128">Escolha o link de assinatura **Registrar seu Azure Active Directory gratuito**.</span><span class="sxs-lookup"><span data-stu-id="ffc91-128">Choose the **Register your free Azure Active Directory** subscription link.</span></span>

4.  <span data-ttu-id="ffc91-129">Escolha **Active Directory** e escolha sua organização.</span><span class="sxs-lookup"><span data-stu-id="ffc91-129">Choose **Active Directory**, and then choose your organization.</span></span>

5.  <span data-ttu-id="ffc91-130">Escolha a guia **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="ffc91-130">Choose the **Users** tab.</span></span>

6.  <span data-ttu-id="ffc91-131">Selecione o usuário cujos dispositivos deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="ffc91-131">Choose the user whose devices you want to delete.</span></span>

7.  <span data-ttu-id="ffc91-132">Escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="ffc91-132">Choose **Devices**.</span></span>

8.  <span data-ttu-id="ffc91-133">Escolha os dispositivos, conforme apropriado e escolha **Excluir dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ffc91-133">Choose the devices as appropriate, and then choose **Delete device**.</span></span> <span data-ttu-id="ffc91-134">O dispositivo será excluído na próxima vez que for sincronizado com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ffc91-134">The device will be deleted the next time it syncs with Active Directory.</span></span> <span data-ttu-id="ffc91-135">Normalmente, isso ocorre em até quatro horas.</span><span class="sxs-lookup"><span data-stu-id="ffc91-135">This typically happens within four hours.</span></span> <span data-ttu-id="ffc91-136">Após a sincronização, o dispositivo é removido do gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ffc91-136">After syncing, the device is removed from management.</span></span> <span data-ttu-id="ffc91-137">Isso remove um dispositivo do limite de dispositivos deste usuário.</span><span class="sxs-lookup"><span data-stu-id="ffc91-137">This removes one device from the device limit for this user.</span></span>

## <span data-ttu-id="ffc91-138">Desativar computadores gerenciados</span><span class="sxs-lookup"><span data-stu-id="ffc91-138">Retire managed computers</span></span>
<a id="retire-managed-computers" class="xliff"></a>
<span data-ttu-id="ffc91-139">Computadores gerenciados com o software cliente do Intune podem ser removidos do gerenciamento por meio do console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="ffc91-139">Computers that Intune client software manages can be removed from management in the Intune admin console.</span></span> <span data-ttu-id="ffc91-140">Esse processo também desinstala o software cliente e exclui a política do Intune do computador.</span><span class="sxs-lookup"><span data-stu-id="ffc91-140">This also uninstalls the client software and deletes the Intune policy from the computer.</span></span> <span data-ttu-id="ffc91-141">Veja informações sobre [como desativar computadores gerenciados com o software cliente do Intune](retire-a-windows-pc-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="ffc91-141">See information about [retiring computers managed with the Intune client software](retire-a-windows-pc-with-microsoft-intune.md).</span></span>

## <span data-ttu-id="ffc91-142">Bloquear o acesso a um dispositivo</span><span class="sxs-lookup"><span data-stu-id="ffc91-142">Block access a device</span></span>
<a id="block-access-a-device" class="xliff"></a>
<span data-ttu-id="ffc91-143">Se um dispositivo for perdido ou quando for necessário desativar um dispositivo devido à saída de um funcionário da empresa sem a devolução de um hardware de propriedade da empresa, também será possível [redefinir a senha e bloquear remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ffc91-143">If a device is lost or when you must retire a device because an employee left your company without returning a company-owned hardware, you can also [passcode reset and remotely lock](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) the device.</span></span> <span data-ttu-id="ffc91-144">Isso impede que as informações da empresa sejam indevidamente utilizadas, embora você possa precisar dar baixa no dispositivo como perda.</span><span class="sxs-lookup"><span data-stu-id="ffc91-144">This keeps company information from being misused, although you might have to write the device off as a loss.</span></span>

<span data-ttu-id="ffc91-145">Você também deseja revogar a licença da conta de usuário Intune do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ffc91-145">You also want to revoke the license from the employee's Intune user account.</span></span> <span data-ttu-id="ffc91-146">Isso libera a licença, permitindo atribuí-la a uma nova conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ffc91-146">This frees up the license, and you can assign it to a new user account.</span></span>

## <span data-ttu-id="ffc91-147">Desativar o hardware</span><span class="sxs-lookup"><span data-stu-id="ffc91-147">Retire hardware</span></span>
<a id="retire-hardware" class="xliff"></a>
<span data-ttu-id="ffc91-148">Às vezes, é o próprio dispositivo que chegou ao fim da vida útil.</span><span class="sxs-lookup"><span data-stu-id="ffc91-148">Sometimes, it’s the device itself that has reached its end of life.</span></span> <span data-ttu-id="ffc91-149">Nesses casos, [redefini-lo para as configurações de fábrica](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) com um apagamento completo remove todos os dados e o dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="ffc91-149">In such cases, [resetting it to factory settings](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md) with a full wipe removes all data and removes the device from Intune.</span></span> <span data-ttu-id="ffc91-150">Em seguida, você pode se desfazer do hardware de acordo com a política da empresa.</span><span class="sxs-lookup"><span data-stu-id="ffc91-150">Then, you can get rid of the hardware according to your company’s policy.</span></span>

### <span data-ttu-id="ffc91-151">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ffc91-151">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="ffc91-152">Ajudar a proteger os dados com apagamento completo ou seletivo</span><span class="sxs-lookup"><span data-stu-id="ffc91-152">Help protect your data with full or selective wipe</span></span>](use-remote-wipe-to-help-protect-data-using-microsoft-intune.md)
