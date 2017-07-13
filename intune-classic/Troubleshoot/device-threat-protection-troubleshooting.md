---
title: "Solucionar problemas de integração do Lookout"
description: "Este tópico descreve a solução de problemas que costumam ocorrer com a integração do Lookout"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cd3c2809161aa438eb7aef91a65d68cb0f657607
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="880b7-103">Solucionar problemas de integração do Lookout com o Intune</span><span class="sxs-lookup"><span data-stu-id="880b7-103">Troubleshoot Lookout Integration with Intune</span></span>
<a id="troubleshoot-lookout-integration-with-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="880b7-104">Este tópico descreve alguns problemas comuns que podem ocorrer durante a configuração da Consulta MTP (proteção contra ameaças móveis).</span><span class="sxs-lookup"><span data-stu-id="880b7-104">This topic describes some common issues you may encounter with your Lookout mobile threat protection (MTP) setup.</span></span>

<span data-ttu-id="880b7-105">**Erros de logon**</span><span class="sxs-lookup"><span data-stu-id="880b7-105">**Login errors**</span></span>

## <span data-ttu-id="880b7-106">Erros 403</span><span class="sxs-lookup"><span data-stu-id="880b7-106">403 errors</span></span>
<a id="403-errors" class="xliff"></a>
<span data-ttu-id="880b7-107">Ao fazer logon no [console do Lookout MTP](https://aad.lookout.com), você recebe um erro 403: **Você não tem autorização para acessar o serviço.** Isso pode acontecer quando o nome de usuário especificado não é membro do grupo do Azure AD (Active Directory) configurado para acessar o Lookout MTP.</span><span class="sxs-lookup"><span data-stu-id="880b7-107">When you log in to the [Lookout MTP console](https://aad.lookout.com) you see a 403 error:  **you are not authorized to access the service**  This can happen when the specified username is not a member of the Azure Active Directory (AD) group configured to access Lookout MTP.</span></span>

<span data-ttu-id="880b7-108">O Lookout MTP permite que apenas usuários de um grupo do Azure AD configurado acessem o serviço.</span><span class="sxs-lookup"><span data-stu-id="880b7-108">Lookout MTP only allows users from a configured Azure AD group to access the service.</span></span> <span data-ttu-id="880b7-109">Para determinar qual grupo está configurado com acesso ao Lookout MTP, contate o suporte do Lookout:</span><span class="sxs-lookup"><span data-stu-id="880b7-109">To determine which group is configured with access to Lookout MTP, contact Lookout Support:</span></span>

* <span data-ttu-id="880b7-110">Email: enterprisesupport@lookout.com</span><span class="sxs-lookup"><span data-stu-id="880b7-110">Email: enterprisesupport@lookout.com</span></span>
* <span data-ttu-id="880b7-111">Faça logon no [Console do MTP](http://aad.lookout.com) e navegue até o módulo **Suporte**.</span><span class="sxs-lookup"><span data-stu-id="880b7-111">Login to the  [MTP  Console](http://aad.lookout.com), and navigate to the **Support** module.</span></span>
* <span data-ttu-id="880b7-112">Acesse: https://enterprise.support.lookout.com/hc/requests e faça uma solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="880b7-112">Go to: https://enterprise.support.lookout.com/hc/requests and make a support request.</span></span>

## <span data-ttu-id="880b7-113">Não é possível entrar</span><span class="sxs-lookup"><span data-stu-id="880b7-113">Unable to sign in</span></span>
<a id="unable-to-sign-in" class="xliff"></a>
<span data-ttu-id="880b7-114">Você vê o erro a seguir quando o usuário administrador global do Azure AD não aceitou a configuração inicial do Lookout.</span><span class="sxs-lookup"><span data-stu-id="880b7-114">You see the following error when the Azure AD global admin user has not accepted the initial Lookout setup.</span></span>

![captura de tela da tela de logon do Lookout mostrando erro ao entrar](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

<span data-ttu-id="880b7-116">Para resolver esse problema, o usuário administrador global deve entrar em https://aad.lookout.com/les?action=consent e aceitar a solicitação para iniciar a instalação.</span><span class="sxs-lookup"><span data-stu-id="880b7-116">To resolve this issue, the global admin user must login to  https://aad.lookout.com/les?action=consent and accept the prompt to initiate the set up.</span></span> <span data-ttu-id="880b7-117">Informações mais detalhadas podem ser encontradas no tópico [Set up your subscription with Lookout MTP](../deploy-use/setup-your-lookout-mtd-subscription.md) (Configurar sua assinatura com a Consulta MTP)</span><span class="sxs-lookup"><span data-stu-id="880b7-117">More detailed information can be found in  [Set up your subscription with Lookout MTP](../deploy-use/setup-your-lookout-mtd-subscription.md) topic</span></span>

<span data-ttu-id="880b7-118">**Problemas de status do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="880b7-118">**Device status issues**</span></span>

## <span data-ttu-id="880b7-119">Dispositivo ausente na lista de dispositivos do Lookout</span><span class="sxs-lookup"><span data-stu-id="880b7-119">Device missing from Lookout device list</span></span>
<a id="device-missing-from-lookout-device-list" class="xliff"></a>

<span data-ttu-id="880b7-120">Isso pode acontecer em um dos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="880b7-120">This could happen in either of the following scenarios:</span></span>
* <span data-ttu-id="880b7-121">O usuário do dispositivo não está no **Grupo de Registro** especificado no **Console do Lookout MTP**.</span><span class="sxs-lookup"><span data-stu-id="880b7-121">The device user is not in the **Enrollment Group** specified in the **Lookout MTP Console**.</span></span>  <span data-ttu-id="880b7-122">No [console do Lookout](http://aad.lookout.com), acesse **Sistema** > **Intune Connector** > **Gerenciamento de Registro**.</span><span class="sxs-lookup"><span data-stu-id="880b7-122">In the [Lookout console](http://aad.lookout.com), go **System** > **Intune Connector** > **Enrollment Management**.</span></span>  <span data-ttu-id="880b7-123">Examine os grupos do Azure AD configurados para o registro e verifique se o usuário do dispositivo faz parte de um dos grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="880b7-123">Review the Azure AD groups configured for enrollment and verify that the device user is part of one of the Azure AD groups.</span></span>  <span data-ttu-id="880b7-124">Depois que um usuário é adicionado ao grupo de registro, pode levar até o intervalo de sondagem configurado, 5 minutos por padrão, para que o dispositivo seja exibido no módulo **Dispositivos** do console do Lookout MTP.</span><span class="sxs-lookup"><span data-stu-id="880b7-124">Once a user is added to the enrollment group, it can take up to the configured polling interval, 5 minutes by default, for the device to appear in the **Devices** module of the Lookout MTP console.</span></span>
* <span data-ttu-id="880b7-125">Se o dispositivo não tiver suporte da Consulta MTP.</span><span class="sxs-lookup"><span data-stu-id="880b7-125">If the device is unsupported by Lookout MTP.</span></span>  <span data-ttu-id="880b7-126">Os dispositivos que não têm suporte aparecerão na seção **Dispositivos Gerenciados** das configurações do conector no Console da Consulta MTP.</span><span class="sxs-lookup"><span data-stu-id="880b7-126">Devices that are unsupported will appear in the **Managed Devices** section of the connector settings on the Lookout MTP Console.</span></span>

### <span data-ttu-id="880b7-127">Dispositivo relatado como **pendente**</span><span class="sxs-lookup"><span data-stu-id="880b7-127">Device reported as **pending**</span></span>
<a id="device-reported-as-pending" class="xliff"></a>

<span data-ttu-id="880b7-128">Um dispositivo é mostrado como **Pendente** se o usuário final não abriu o aplicativo Lookout for Work nem tocou no botão **Ativar**.</span><span class="sxs-lookup"><span data-stu-id="880b7-128">A device is shown as  **Pending** if the end user has not opened the Lookout for work app and tapped the  **Activate** button.</span></span> <span data-ttu-id="880b7-129">Para obter mais detalhes sobre a ativação do dispositivo com o aplicativo Lookout for Work, consulte [Você é solicitado a instalar o Lookout for Work](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) ou [Você é solicitado a instalar o Lookout for Work em seu dispositivo iOS](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios)</span><span class="sxs-lookup"><span data-stu-id="880b7-129">For more details on the device activation with Lookout for work app, see [You are prompted to install Lookout for Work on your Android device](http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android) or [You are prompted to install Lookout for Work on your iOS device](https://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-ios)</span></span>

## <span data-ttu-id="880b7-130">Dispositivo ativo, mas sem ID de dispositivo</span><span class="sxs-lookup"><span data-stu-id="880b7-130">Device whos active, but has no device ID</span></span>
<a id="device-whos-active-but-has-no-device-id" class="xliff"></a>
<span data-ttu-id="880b7-131">No console do Lookout MTP, se um dispositivo ativo não tiver nenhuma ID de dispositivo, o usuário do dispositivo não estará no grupo de registro.</span><span class="sxs-lookup"><span data-stu-id="880b7-131">In the Lookout MTP console, if an active device has no device ID then the device user is not in the enrollment group.</span></span> <span data-ttu-id="880b7-132">Um dispositivo poderá entrar nesse estado se o usuário do dispositivo tiver sido removido do grupo de registro ou se o grupo de registro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="880b7-132">A device can get into this state is if the device user has been removed from the enrollment group or the enrollment group has been removed.</span></span>

<span data-ttu-id="880b7-133">No [console do Lookout](http://aad.lookout.com), acesse **Sistema** > **Intune Connector** > **Registro** e examine as configurações.</span><span class="sxs-lookup"><span data-stu-id="880b7-133">In the [Lookout console](http://aad.lookout.com), go **System** > **Intune Connector** > **Enrollment** and review the settings.</span></span>  <span data-ttu-id="880b7-134">Examine os grupos do Azure AD e verifique se o usuário do dispositivo faz parte de um dos grupos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="880b7-134">Review the Azure AD groups and verify that the device useris part of one of the Azure AD groups.</span></span>

<span data-ttu-id="880b7-135">Enquanto o dispositivo estiver nesse estado, o Lookout continuará notificando o usuário das ameaças detectadas, mas não enviará nenhuma informação sobre a ameaça ao Intune.</span><span class="sxs-lookup"><span data-stu-id="880b7-135">While a device is in this state, Lookout will continue to notify the user of any threats detected, but will not send any threat information to Intune.</span></span>

## <span data-ttu-id="880b7-136">Dispositivo relatado como **desconectado**</span><span class="sxs-lookup"><span data-stu-id="880b7-136">Device reported as **disconnected**</span></span>
<a id="device-reported-as-disconnected" class="xliff"></a>

<span data-ttu-id="880b7-137">**Desconectado** significa que o dispositivo não foi sincronizado com o Lookout MTP no intervalo configurado, 30 dias por padrão, com um mínimo de 7 dias.</span><span class="sxs-lookup"><span data-stu-id="880b7-137">**Disconnected** means the device hasn't synced with Lookout MTP in the configured interval, 30 days by default with a minimum of 7 days.</span></span> <span data-ttu-id="880b7-138">O aplicativo Portal da Empresa ou Lookout for Work está ausente do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="880b7-138">Either the Company Portal app or the Lookout for Work app is missing from the device.</span></span> <span data-ttu-id="880b7-139">Reinstalar os aplicativos deve solucionar esse problema.</span><span class="sxs-lookup"><span data-stu-id="880b7-139">Reinstalling the apps should resolve this issue.</span></span> <span data-ttu-id="880b7-140">Quando o usuário abre o Lookout for Work e ativa o aplicativo, o dispositivo é ressincronizado com a Consulta MTP e o Intune.</span><span class="sxs-lookup"><span data-stu-id="880b7-140">When the user opens Lookout for Work and activates the app, the device resyncs with Lookout MTP and Intune.</span></span>

### <span data-ttu-id="880b7-141">Forçando uma sincronização de dispositivo</span><span class="sxs-lookup"><span data-stu-id="880b7-141">Forcing a device sync</span></span>
<a id="forcing-a-device-sync" class="xliff"></a>
<span data-ttu-id="880b7-142">Do módulo **Dispositivos** do console da Consulta MTP, o administrador pode selecionar o dispositivo e optar por excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="880b7-142">From the **Devices** module of the Lookout MTP console, the administrator can select the device and choose to delete it.</span></span>   <span data-ttu-id="880b7-143">Na próxima vez em que o proprietário do dispositivo abrir o aplicativo do Lookout for Work e tocar em **Ativar**, o estado do dispositivo fará uma ressincronização completa.</span><span class="sxs-lookup"><span data-stu-id="880b7-143">The next time the device owner opens the Lookout for Work app and taps **Activate**, the device state will do a full resync.</span></span>

## <span data-ttu-id="880b7-144">O dispositivo tem um novo usuário</span><span class="sxs-lookup"><span data-stu-id="880b7-144">Device has a new user</span></span>
<a id="device-has-a-new-user" class="xliff"></a>
<span data-ttu-id="880b7-145">É necessário apagar o dispositivo e solicitar que o novo usuário se registre.</span><span class="sxs-lookup"><span data-stu-id="880b7-145">You should wipe the device and ask the new user to enroll.</span></span>  <span data-ttu-id="880b7-146">Do [Console do administrador do Intune](https://manage.microsoft.com), selecione o dispositivo, clique com botão direito do mouse e escolha **Desativar/Apagar** para remover o dispositivo do gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="880b7-146">From the [Intune administrator console](https://manage.microsoft.com), select the device, right click, and choose **Retire/Wipe** to remove the device from management.</span></span> <span data-ttu-id="880b7-147">Depois de desativar o dispositivo, você poderá excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="880b7-147">After retiring the device you can delete it.</span></span>

![captura de tela do módulo do dispositivo no console de administração do Intune com a opção desativar/apagar exibida](../media/mtp/mtp-retire-device-intune-console.png)

<span data-ttu-id="880b7-149">Também é possível acessar o módulo **Dispositivos** do [console do Lookout](http://aad.lookout.com) e escolher **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="880b7-149">You can also go to the **Devices** module of the [Lookout console](http://aad.lookout.com) and choose **Delete**.</span></span>

<span data-ttu-id="880b7-150">Se o novo usuário estiver em um grupo de registro do Lookout MTP, o dispositivo será exibido depois que o Azure AD associar o dispositivo ao novo usuário.</span><span class="sxs-lookup"><span data-stu-id="880b7-150">If the new user is in an  Lookout MTP enrollment group, the device will appear once Azure AD associates the device with the new user.</span></span>

## <span data-ttu-id="880b7-151">Fluxos de trabalho de correção de conformidade</span><span class="sxs-lookup"><span data-stu-id="880b7-151">Compliance remediation workflows</span></span>
<a id="compliance-remediation-workflows" class="xliff"></a>
- [<span data-ttu-id="880b7-152">Você é solicitado a instalar o Lookout for Work em seu dispositivo Android</span><span class="sxs-lookup"><span data-stu-id="880b7-152">You are prompted to install Lookout for Work on your Android device</span></span>]( http://docs.microsoft.com/intune-user-help/you-are-prompted-to-install-lookout-for-work-android)
- [<span data-ttu-id="880b7-153">Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo Android</span><span class="sxs-lookup"><span data-stu-id="880b7-153">You need to resolve a threat that Lookout for Work found on your Android device</span></span>](http://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [<span data-ttu-id="880b7-154">Você precisa resolver uma ameaça que o Lookout for Work encontrou em seu dispositivo iOS</span><span class="sxs-lookup"><span data-stu-id="880b7-154">You need to resolve a threat that Lookout for Work found on your iOS device</span></span>](https://docs.microsoft.com/intune-user-help/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <span data-ttu-id="880b7-155">Consulte também</span><span class="sxs-lookup"><span data-stu-id="880b7-155">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="880b7-156">Configurar sua assinatura com a Consulta MTP</span><span class="sxs-lookup"><span data-stu-id="880b7-156">Set up you subscription with Lookout MTP</span></span>](/intune-classic/deploy-use/set-up-your-subscription-with-lookout-mtp)
