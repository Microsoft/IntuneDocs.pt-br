---
title: "<span data-ttu-id=\"d6ac5-101\">Solução de problemas de perfis de dispositivo no Microsoft Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"d6ac5-101\">Troubleshooting device profiles in Microsoft Intune</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"d6ac5-102\">Se estiver tendo dificuldades, use este tópico para ajudar a solucionar problemas com perfis de dispositivo do Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"d6ac5-102\">If you're stuck, use this topic to help you solve problems with Intune device profiles.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ed238f35927f17b20402f64586686246afabb900
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d6ac5-103">Solução de problemas de perfis de dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d6ac5-103">Troubleshooting device profiles in Microsoft Intune</span></span>
<a id="troubleshooting-device-profiles-in-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d6ac5-104">As informações neste tópico podem ser usadas para ajudar a solucionar problemas comuns relacionados a perfis de dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-104">The information in this topic can be used to help you troubleshoot common issues around Intune device profiles.</span></span>

## <span data-ttu-id="d6ac5-105">Quanto tempo leva para dispositivos móveis obterem uma política ou os aplicativos depois de terem sido atribuídos?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-105">How long does it take for mobile devices to get a policy or apps after they have been assigned?</span></span>
<a id="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned" class="xliff"></a>
<span data-ttu-id="d6ac5-106">Quando uma política ou um aplicativo é atribuído, o Intune imediatamente começa a tentar notificar o dispositivo de que ele deve fazer o check-in com o serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-106">When a policy or an app is assigned, Intune immediately begins attempting to notify the device that it should check in with the Intune service.</span></span> <span data-ttu-id="d6ac5-107">Em geral, isso leva menos de cinco minutos.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-107">This typically takes less than five minutes.</span></span>

<span data-ttu-id="d6ac5-108">Se um dispositivo não fizer o check-in para obter a política após a primeira notificação ser enviada, o Intune fará mais três tentativas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-108">If a device doesn't check in to get the policy after the first notification is sent, Intune makes three more attempts.</span></span>  <span data-ttu-id="d6ac5-109">Se o dispositivo estiver offline (por exemplo, desativado ou desconectado da rede), ele poderá não receber as notificações.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-109">If the device is offline (for example, it is turned off or not connected to a network), it might not receive the notifications.</span></span> <span data-ttu-id="d6ac5-110">Nesse caso, o dispositivo receberá a política no próximo check-in agendado com o serviço do Intune da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d6ac5-110">In this case, the device will get the policy on its next scheduled check-in with the Intune service as follows:</span></span>

- <span data-ttu-id="d6ac5-111">iOS e macOS: a cada 6 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-111">iOS and macOS: Every 6 hours.</span></span>
- <span data-ttu-id="d6ac5-112">Android: a cada 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-112">Android: Every 8 hours.</span></span>
- <span data-ttu-id="d6ac5-113">Windows Phone: a cada 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-113">Windows Phone: Every 8 hours.</span></span>
- <span data-ttu-id="d6ac5-114">Computadores Windows 8.1 e Windows 10 registrados como dispositivos: a cada 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-114">Windows 8.1 and Windows 10 PCs enrolled as devices: Every 8 hours.</span></span>

<span data-ttu-id="d6ac5-115">Se o dispositivo tiver sido registrado recentemente, a frequência de check-in será maior, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d6ac5-115">If the device has just enrolled, the check-in frequency will be more frequent, as follows:</span></span>

- <span data-ttu-id="d6ac5-116">iOS e macOS: a cada 15 minutos por 6 horas, e depois a cada 6 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-116">iOS and macOS: Every 15 minutes for 6 hours, and then every 6 hours.</span></span>
- <span data-ttu-id="d6ac5-117">Android: a cada 3 minutos por 15 minutos, então a cada 15 minutos por 2 horas e então a cada 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-117">Android: Every 3 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.</span></span>
- <span data-ttu-id="d6ac5-118">Windows Phone: a cada 5 minutos por 15 minutos, então a cada 15 minutos por 2 horas e então a cada 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-118">Windows Phone: Every 5 minutes for 15 minutes, then every 15 minutes for 2 hours, and then every 8 hours.</span></span>
- <span data-ttu-id="d6ac5-119">Computadores Windows registrados como dispositivos: a cada 3 minutos por 30 minutos e a cada 8 horas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-119">Windows PCs enrolled as devices: Every 3 minutes for 30 minutes, and then every 8 hours.</span></span>

<span data-ttu-id="d6ac5-120">Os usuários também podem iniciar o aplicativo Portal da Empresa e sincronizar o dispositivo para verificar imediatamente a política a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-120">Users can also open the Company Portal app and sync the device to immediately check for the policy anytime.</span></span>

## <span data-ttu-id="d6ac5-121">Que ações fazem com que o Intune envie imediatamente uma notificação para um dispositivo?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-121">What actions cause Intune to immediately send a notification to a device?</span></span>
<a id="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device" class="xliff"></a>
<span data-ttu-id="d6ac5-122">Os dispositivos fazem o check-in no Intune quando recebem uma notificação que os informa para fazer check-in ou durante o check-in agendado regularmente.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-122">Devices check in with Intune either when they receive a notification that tells them to check in or during their regularly scheduled check-in.</span></span>  <span data-ttu-id="d6ac5-123">Quando você seleciona um dispositivo ou usuário especificamente com uma ação como apagamento, bloqueio, redefinição de senha, atribuição de aplicativo, atribuição do perfil (Wi-Fi, VPN, email etc.) ou atribuição de política, o Intune começa imediatamente a tentar notificar o dispositivo de que ele deve fazer check-in no serviço Intune para receber essas atualizações.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-123">When you target a device or user specifically with an action such as a wipe, lock, passcode reset, app assignment, profile assignment (Wi-Fi, VPN, email, etc.), or policy assignment, Intune will immediately begin trying to notify the device that it should check in with the Intune service to receive these updates.</span></span>

<span data-ttu-id="d6ac5-124">Outras alterações, como revisar as informações de contato no portal da empresa, não causam uma notificação imediata para os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-124">Other changes, such as revising the contact information in the company portal, do not cause an immediate notification to devices.</span></span>

## <span data-ttu-id="d6ac5-125">Se várias políticas forem atribuídas ao mesmo usuário ou dispositivo, como saber quais configurações serão aplicadas?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-125">If multiple policies are assigned to the same user or device, how do I know which settings will get applied?</span></span>
<a id="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied" class="xliff"></a>
<span data-ttu-id="d6ac5-126">Quando duas ou mais políticas são atribuídas ao mesmo usuário ou dispositivo, a avaliação de qual configuração é aplicada ocorre no nível da configuração individual:</span><span class="sxs-lookup"><span data-stu-id="d6ac5-126">When two or more policies are assigned to the same user or device, the evaluation for which setting is applied happens at the individual setting level:</span></span>

-   <span data-ttu-id="d6ac5-127">Configurações de política de conformidade sempre têm precedência sobre configurações da política.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-127">Compliance policy settings always have precedence over configuration policy settings.</span></span>

-   <span data-ttu-id="d6ac5-128">A configuração de política de conformidade mais restritiva é aplicada se avaliada em relação à mesma configuração em uma política de conformidade diferente.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-128">The most restrictive compliance policy setting is applied if it is evaluated against the same setting in a different compliance policy.</span></span>

-   <span data-ttu-id="d6ac5-129">Se a definição de uma política de configuração estiver em conflito com uma configuração em uma política de configuração diferente, esse conflito será exibido no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-129">If a configuration policy setting conflicts with a setting in a different configuration policy, this conflict will be displayed in the Intune console.</span></span> <span data-ttu-id="d6ac5-130">Você deve resolver esses conflitos manualmente.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-130">You must manually resolve such conflicts.</span></span>

## <span data-ttu-id="d6ac5-131">O que acontece quando as políticas de proteção de aplicativo entram em conflito umas com as outras?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-131">What happens when app protection policies conflict with each other?</span></span> <span data-ttu-id="d6ac5-132">Qual delas será aplicada ao aplicativo?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-132">Which one will be applied to the app?</span></span>
<a id="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app" class="xliff"></a>
<span data-ttu-id="d6ac5-133">Os valores de conflito são as configurações mais restritivas disponíveis em uma política de proteção de aplicativo, exceto pelos campos de entrada de número (como as tentativas de PIN antes de redefinir).</span><span class="sxs-lookup"><span data-stu-id="d6ac5-133">Conflict values are the most restrictive settings available in an app protection policy, except for the number entry fields (like PIN attempts before reset).</span></span>  <span data-ttu-id="d6ac5-134">Os campos de entrada de número serão definidos com os mesmos valores, como se você criasse uma política de MAM no console usando a opção de configurações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-134">The number entry fields will be set the same as the values, as if you created a MAM policy in the console by using the recommended settings option.</span></span>

<span data-ttu-id="d6ac5-135">Os conflitos ocorrem quando duas configurações de perfil são iguais.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-135">Conflicts occur when two profile settings are the same.</span></span>  <span data-ttu-id="d6ac5-136">Por exemplo, você configurou duas políticas MAM idênticas, exceto pela configuração de copiar/colar.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-136">For example, you configured two MAM policies that are identical except for the copy/paste setting.</span></span>  <span data-ttu-id="d6ac5-137">Nesse cenário, a configuração de copiar/colar será definida para o valor mais restritivo, mas o restante das configurações será aplicado como configurado.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-137">In this scenario, the copy/paste setting will be set to the most restrictive value, but the rest of the settings will be applied as configured.</span></span>

<span data-ttu-id="d6ac5-138">Se uma política for atribuída ao aplicativo e entrar em vigor, e então uma segunda for atribuída, a primeira terá precedência e continuará em vigor, enquanto a segunda aparecerá como estando em conflito.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-138">If one profile is assignedd to the app and takes effect, and then a second one is assigned, the first one will take precedence and stay applied, while the second shows in conflict.</span></span> <span data-ttu-id="d6ac5-139">Se as duas forem aplicadas ao mesmo tempo, o que significa que não há perfil anterior, as duas estarão em conflito.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-139">If they are both applied at the same time, meaning that there is no preceding profile, then they will both be in conflict.</span></span> <span data-ttu-id="d6ac5-140">Quaisquer configurações conflitantes serão definidas com os valores mais restritivos.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-140">Any conflicting settings will be set to the most restrictive values.</span></span>

## <span data-ttu-id="d6ac5-141">O que acontece quando há conflito de políticas personalizadas de iOS?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-141">What happens when iOS custom policies conflict?</span></span>
<a id="what-happens-when-ios-custom-policies-conflict" class="xliff"></a>
<span data-ttu-id="d6ac5-142">O Intune não avalia o conteúdo dos arquivos de Configuração da Apple ou um perfil personalizado de URI-OMA (Open Mobile Alliance Uniform Resource Identifier).</span><span class="sxs-lookup"><span data-stu-id="d6ac5-142">Intune does not evaluate the payload of Apple Configuration files or a custom Open Mobile Alliance Uniform Resource Identifier (OMA-URI) profile.</span></span> <span data-ttu-id="d6ac5-143">Ele simplesmente serve como o mecanismo de entrega.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-143">It merely serves as the delivery mechanism.</span></span>

<span data-ttu-id="d6ac5-144">Quando você atribui um perfil personalizado, garanta que as configurações definidas não entrem em conflito com as políticas de conformidade, configuração ou outras políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-144">When you assign a custom profile, ensure that the configured settings do not conflict with compliance, configuration, or other custom policies.</span></span> <span data-ttu-id="d6ac5-145">No caso de um perfil personalizado com configurações entrar em conflitos, a ordem na qual as configurações são aplicadas é aleatória.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-145">In the case of a custom profile with settings conflicts, the order in which settings are applied is random.</span></span>

## <span data-ttu-id="d6ac5-146">O que acontece quando um perfil é excluído ou não é mais aplicável?</span><span class="sxs-lookup"><span data-stu-id="d6ac5-146">What happens when a profile is deleted or no longer applicable?</span></span>
<a id="what-happens-when-a-profile-is-deleted-or-no-longer-applicable" class="xliff"></a>
<span data-ttu-id="d6ac5-147">Quando você exclui um perfil ou remove um dispositivo de um grupo no qual um perfil foi atribuído, o perfil e as configurações são removidos do dispositivo de acordo com as listas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-147">When you delete a profile, or you remove a device from a group to which a profile was assigned, the profile and settings will be removed from the device according to the following lists.</span></span>

### <span data-ttu-id="d6ac5-148">Dispositivos registrados</span><span class="sxs-lookup"><span data-stu-id="d6ac5-148">Enrolled devices</span></span>
<a id="enrolled-devices" class="xliff"></a>

- <span data-ttu-id="d6ac5-149">Perfis de email, certificado, VPN e Wi-Fi: esses perfis são removidos de todos os dispositivos registrados com suporte.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-149">Wi-Fi, VPN, certificate, and email profiles: These profiles are removed from all supported enrolled devices.</span></span>
- <span data-ttu-id="d6ac5-150">Todos os outros tipos de perfil:</span><span class="sxs-lookup"><span data-stu-id="d6ac5-150">All other profile types:</span></span>
    - <span data-ttu-id="d6ac5-151">**Dispositivos Android e Windows**: as configurações não são removidas do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-151">**Windows and Android devices**: Settings are not removed from the device.</span></span>
    - <span data-ttu-id="d6ac5-152">**Dispositivos Windows Phone 8.1**: as configurações a seguir são removidas:</span><span class="sxs-lookup"><span data-stu-id="d6ac5-152">**Windows Phone 8.1 devices**: The following settings are removed:</span></span>
        - <span data-ttu-id="d6ac5-153">Exigir uma senha para desbloquear os dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="d6ac5-153">Require a password to unlock mobile devices</span></span>
        - <span data-ttu-id="d6ac5-154">Permitir senha simples</span><span class="sxs-lookup"><span data-stu-id="d6ac5-154">Allow simple passwords</span></span>
        - <span data-ttu-id="d6ac5-155">Comprimento mínimo da senha</span><span class="sxs-lookup"><span data-stu-id="d6ac5-155">Minimum password length</span></span>
        - <span data-ttu-id="d6ac5-156">Tipo de senha necessária</span><span class="sxs-lookup"><span data-stu-id="d6ac5-156">Required password type</span></span>
        - <span data-ttu-id="d6ac5-157">Expiração da senha (dias)</span><span class="sxs-lookup"><span data-stu-id="d6ac5-157">Password expiration (days)</span></span>
        - <span data-ttu-id="d6ac5-158">Lembrar de histórico de senha</span><span class="sxs-lookup"><span data-stu-id="d6ac5-158">Remember password history</span></span>
        - <span data-ttu-id="d6ac5-159">Número de falhas de logon repetidas permitido antes do dispositivo ser apagado</span><span class="sxs-lookup"><span data-stu-id="d6ac5-159">Number of repeated sign-in failures to allow before the device is wiped</span></span>
        - <span data-ttu-id="d6ac5-160">Minutos de inatividade antes de a senha ser necessária</span><span class="sxs-lookup"><span data-stu-id="d6ac5-160">Minutes of inactivity before password is required</span></span>
        - <span data-ttu-id="d6ac5-161">Tipo de senha necessária – o número mínimo de conjuntos de caracteres</span><span class="sxs-lookup"><span data-stu-id="d6ac5-161">Required password type – minimum number of character sets</span></span>
        - <span data-ttu-id="d6ac5-162">Permitir câmera</span><span class="sxs-lookup"><span data-stu-id="d6ac5-162">Allow camera</span></span>
        - <span data-ttu-id="d6ac5-163">Exigir criptografia no dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="d6ac5-163">Require encryption on mobile device</span></span>
        - <span data-ttu-id="d6ac5-164">Permitir armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="d6ac5-164">Allow removable storage</span></span>
        - <span data-ttu-id="d6ac5-165">Permitir navegador da web</span><span class="sxs-lookup"><span data-stu-id="d6ac5-165">Allow web browser</span></span>
        - <span data-ttu-id="d6ac5-166">Permitir loja de aplicativo</span><span class="sxs-lookup"><span data-stu-id="d6ac5-166">Allow application store</span></span>
        - <span data-ttu-id="d6ac5-167">Permitir captura de tela</span><span class="sxs-lookup"><span data-stu-id="d6ac5-167">Allow screen capture</span></span>
        - <span data-ttu-id="d6ac5-168">Permitir localização geográfica</span><span class="sxs-lookup"><span data-stu-id="d6ac5-168">Allow geolocation</span></span>
        - <span data-ttu-id="d6ac5-169">Permitir conta da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d6ac5-169">Allow Microsoft account</span></span>
        - <span data-ttu-id="d6ac5-170">Permitir copiar e colar</span><span class="sxs-lookup"><span data-stu-id="d6ac5-170">Allow copy and paste</span></span>
        - <span data-ttu-id="d6ac5-171">Permitir compartilhamento de Internet por Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ac5-171">Allow Wi-Fi tethering</span></span>
        - <span data-ttu-id="d6ac5-172">Permitir conexão automática para liberar pontos de acesso Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ac5-172">Allow automatic connection to free Wi-Fi hotspots</span></span>
        - <span data-ttu-id="d6ac5-173">Permitir relatórios de pontos de acesso Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ac5-173">Allow Wi-Fi hotspot reporting</span></span>
        - <span data-ttu-id="d6ac5-174">Permitir redefinição de fábrica</span><span class="sxs-lookup"><span data-stu-id="d6ac5-174">Allow factory reset</span></span>
        - <span data-ttu-id="d6ac5-175">Permitir Bluetooth</span><span class="sxs-lookup"><span data-stu-id="d6ac5-175">Allow Bluetooth</span></span>
        - <span data-ttu-id="d6ac5-176">Permitir NFC</span><span class="sxs-lookup"><span data-stu-id="d6ac5-176">Allow NFC</span></span>
        - <span data-ttu-id="d6ac5-177">Permitir Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="d6ac5-177">Allow Wi-Fi</span></span>

    - <span data-ttu-id="d6ac5-178">**iOS**: todas as configurações são removidas, exceto:</span><span class="sxs-lookup"><span data-stu-id="d6ac5-178">**iOS**: All settings are removed, except:</span></span>
        - <span data-ttu-id="d6ac5-179">Permitir roaming de Voz</span><span class="sxs-lookup"><span data-stu-id="d6ac5-179">Allow voice roaming</span></span>
        - <span data-ttu-id="d6ac5-180">Permitir roaming de Dados</span><span class="sxs-lookup"><span data-stu-id="d6ac5-180">Allow data roaming</span></span>
        - <span data-ttu-id="d6ac5-181">Permitir sincronização automática durante roaming</span><span class="sxs-lookup"><span data-stu-id="d6ac5-181">Allow automatic synchronization while roaming</span></span>

## <span data-ttu-id="d6ac5-182">Alterei um perfil de restrição de dispositivo, mas as alterações não entraram em vigor</span><span class="sxs-lookup"><span data-stu-id="d6ac5-182">I changed a device restriction profile, but the changes haven't taken effect</span></span>
<a id="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect" class="xliff"></a>
<span data-ttu-id="d6ac5-183">Dispositivos Windows Phone não permitem que políticas de segurança definidas por meio do MDM ou EAS sejam reduzidas em termos de segurança após terem sido configuradas.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-183">Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them.</span></span> <span data-ttu-id="d6ac5-184">Por exemplo, você define um **Número mínimo de caracteres de senha** para 8 e tenta reduzi-lo a 4.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-184">For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4.</span></span> <span data-ttu-id="d6ac5-185">O perfil mais restritivo já foi aplicado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-185">The more restrictive profile has already been applied to the device.</span></span>

<span data-ttu-id="d6ac5-186">Dependendo da plataforma do dispositivo, se você quiser alterar o perfil para um valor menos seguro, pode ser necessário redefinir as políticas de segurança.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-186">Depending on the device platform, if you want to change the profile to a less secure value you may need to reset security policies.</span></span>
<span data-ttu-id="d6ac5-187">Por exemplo, no Windows, na área de trabalho, passe o dedo da direita para a esquerda para abrir a barra **Botões** e escolha **Configurações** &gt; **Painel de Controle**.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-187">For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.</span></span>  <span data-ttu-id="d6ac5-188">Selecione o miniaplicativo **Contas de Usuário**.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-188">Select the **User Accounts** applet.</span></span>
<span data-ttu-id="d6ac5-189">No menu de navegação à esquerda, há um link **Redefinir Políticas de Segurança** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-189">In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom.</span></span> <span data-ttu-id="d6ac5-190">Escolha-o e clique no botão **Redefinir Políticas**.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-190">Choose it and then choose the **Reset Policies** button.</span></span>
<span data-ttu-id="d6ac5-191">Outros dispositivos MDM, como Android, Windows Phone 8.1 e posterior e iOS, precisarão ser desativados e registrados novamente no serviço para que você possa aplicar um perfil menos restritivo.</span><span class="sxs-lookup"><span data-stu-id="d6ac5-191">Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive profile.</span></span>

<!--- ## Status codes for MDM managed Windows devices

|Status code|Error message|What to do|
|---------------|-----------------|--------------|
|10 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Installation in progress||
|20 (APP_CI_ENFORCEMENT_IN_PROGRESS_WAITING_CONTENT)|Waiting for content||
|30 (APP_CI_ENFORCEMENT_ERROR_RETRIEVING_CONTENT)|Retrieving content|Probable Cause: Job status 30 indicates that a user download of an app failed.<br /><br />Likely causes for this may be:<br /><br />The device lost Internet connectivity while the download was in progress.<br /><br />The certificate issued to the device at the time of enrollment may have expired.<br /><br />Mitigation:<br /><br />Launch the Company Apps app from Control Panel on the device to confirm that the device certificate hasn’t expired; if it has then you will need to re-enroll the device.<br /><br />Confirm that the device is connected to the Internet and try to request the app again.|
|40 (APP_CI_ENFORCEMENT_IN_PROGRESS_CONTENT_DOWNLOADED)|Content download complete||
|50 (APP_CI_ENFORCEMENT_IN_PROGRESS_INSTALLING)|Installation in progress||
|60 (APP_CI_ENFORCEMENT_ERROR_INSTALLING)|Installation Error occurred|The app installation failed after download.<br /><br />The code signing certificate with which app was signed is not present on the device.<br /><br />A framework dependency on which the application depends is not found installed on the device.<br /><br />Ensure that the code signing certificate with which your app was signed is present on the device and confirm with the admin that such a certificate was targeted for all enterprise enrolled Windows RT devices.<br /><br />In case the installation failure is due to a missing framework dependency, the admin will have to re-publish the application again packaging the framework along with the application package.<br /><br />The application package downloaded isn’t a valid package, may have been corrupted, or may not be compatible with the OS version on the device.|
|70 (APP_CI_ENFORCEMENT_SUCCEEDED)|Installation Success||
|80 (APP_CI_ENFORCEMENT_IN_PROGRESS)|Uninstall in progress||
|90 (APP_CI_ENFORCEMENT_ERROR)|Uninstall Error occurred||
|100 (APP_CI_ENFORCEMENT_SUCCEEDED)|Uninstall Success||
|110 (APP_CI_ENFORCEMENT_ERROR)|Content hash mismatch||
|120 (APP_CI_ENFORCEMENT_ERROR)|SLK / side loading not enabled||
|130 (APP_CI_ENFORCEMENT_ERROR)|MSADP license install failed||
|No status (APP_CI_ENFORCEMENT_UNKNOWN)|n/a|The status is currently unknown.|

## Company resource access (common errors)

|Status code|Hexadecimal error code|Error message|
|---------------|--------------------------|-----------------|
|-2016281101|0x87D1FDF3|MDM CRP request not found|
|-2016281102|0x87D1FDF2|NDES URL not found|
|-2016281103|0x87D1FDF1|MDM CRP certificate info not found|
|-2016281104|0x87D1FDF0|MDM CI certificate info not found|
|-2016281105|0x87D1FDEF|Failed to evaluate the Rule|
|-2016281106|0x87D1FDEE|Not applicable because it lost in conflict resolution|
|-2016281107|0x87D1FDED|Unsupported setting discovery source|
|-2016281108|0x87D1FDEC|Referenced setting not found in CI|
|-2016281109|0x87D1FDEB|Data type conversion failed|
|-2016281110|0x87D1FDEA|Invalid parameter to CIM setting|
|-2016281111|0x87D1FDE9|Not applicable for this device|
|-2016281112|0x87D1FDE8|Remediation failed|
|-2016330905|0x87D13B67|The app state is unknown|
|-2016330906|0x87D13B66|The app is managed, but has been removed by the user|
|-2016330907|0x87D13B65|The device is redeeming the redemption code|
|-2016330908|0x87D13B64|The app install has failed|
|-2016330909|0x87D13B63|The user rejected the offer to update the app|
|-2016330910|0x87D13B62|The user rejected the offer to install the app|
|-2016330911|0x87D13B61|The user has installed the app before managed app installation could take place|
|-2016330912|0x87D13B60|The app is scheduled for installation, but needs a redemption code to complete the transaction|
|-2016341109|0x87D1138B|iOS device has returned an error|
|-2016341110|0x87D1138A|iOS device has rejected the command due to incorrect format|
|-2016341111|0x87D11389|iOS device has returned an unexpected Idle status|
|-2016341112|0x87D11388|iOS device is currently busy|

## Errors returned by iOS devices

|Status code|Hexadecimal error code|Error message|
|---------------|--------------------------|-----------------|
|-2016299111|0x87D1B799|Internal error|
|-2016299112|0x87D1B798|Internal error|
|-2016300111|0x87D1B3B1|36001:(internal error)|
|-2016300112|0x87D1B3B0|36000:Cellular already configured|
|-2016301110|0x87D1AFCA|35002:Multiple fonts in a single payload|
|-2016301111|0x87D1AFC9|35001:Failed font installation|
|-2016301112|0x87D1AFC8|35000:Invalid font data|
|-2016302109|0x87D1ABE3|34003:Kerberos principal name invalid|
|-2016302110|0x87D1ABE2|34002:Kerberos principal name missing|
|-2016302111|0x87D1ABE1|34001:Invalid URL match pattern|
|-2016302112|0x87D1ABE0|34000:Invalid app identifier match pattern|
|-2016304112|0x87D1A410|32000:Too many apps|
|-2016305111|0x87D1A029|31001:Cannot apply settings|
|-2016305112|0x87D1A028|31000:Cannot apply credential|
|-2016306111|0x87D19C41|30001:Timed out|
|-2016306112|0x87D19C40|30000:Authentication failed|
|-2016307109|0x87D1985B|29003:Bad certificate data|
|-2016307110|0x87D1985A|29002:|
|-2016307111|0x87D19859|29001:|
|-2016307112|0x87D19858|29000:Device not supervised|
|-2016308110|0x87D19472|28002:Cannot set wallpaper|
|-2016308111|0x87D19471|28001:Bad wallpaper image|
|-2016308112|0x87D19470|28000:Unknown item|
|-2016310111|0x87D18CA1|26001:File level encryption unsupported|
|-2016310112|0x87D18CA0|26000:Block level encryption unsupported|
|-2016311110|0x87D188BA|25002:Cannot remove|
|-2016311111|0x87D188B9|25001:Cannot install|
|-2016311112|0x87D188B8|25000:Bad profile|
|-2016312109|0x87D184D3|24003:Bad final profile|
|-2016312110|0x87D184D2|24002:Bad identity payload|
|-2016312111|0x87D184D1|24001:Cannot sign attribute dictionary|
|-2016312112|0x87D184D0|24000:Cannot create attribute dictionary|
|-2016313110|0x87D180EA|23002:Invalid server certificate|
|-2016313111|0x87D180E9|23001:Bad server response|
|-2016313112|0x87D180E8|23000:Bad identity|
|-2016314099|0x87D17D0D|22013:Invalid PKIOperation response|
|-2016314100|0x87D17D0C|22012:Cannot store CACertificate|
|-2016314101|0x87D17D0B|22011:Cannot generate CSR|
|-2016314102|0x87D17D0A|22010:Cannot store temporary identity|
|-2016314103|0x87D17D09|22009:Cannot create temporary identity|
|-2016314104|0x87D17D08|22008:Cannot create identity|
|-2016314105|0x87D17D07|22007:Invalid signed certificate|
|-2016314106|0x87D17D06|22006:Insufficient CACaps|
|-2016314107|0x87D17D05|22005:Network error|
|-2016314108|0x87D17D04|22004:Unsupported certificate configuration|
|-2016314109|0x87D17D03|22003:Invalid RAResponse|
|-2016314110|0x87D17D02|22002:Invalid CAResponse|
|-2016314111|0x87D17D01|22001:Cannot generate key pair|
|-2016314112|0x87D17D00|22000:Invalid key usage|
|-2016315105|0x87D1791F|21007:Cannot verify account|
|-2016315106|0x87D1791E|21006:Cannot decrypt certificate|
|-2016315107|0x87D1791D|21005:Account not unique (Email Profile already exists on device)|
|-2016315108|0x87D1791C|21004:Cannot create account|
|-2016315109|0x87D1791B|21003:No host name|
|-2016315110|0x87D1791A|21002:Cannot comply with encryption policy from server|
|-2016315111|0x87D17919|21001:Cannot comply with policy from server|
|-2016315112|0x87D17918|21000:Cannot get policy from server|
|-2016316110|0x87D17532|20002:Account not unique|
|-2016316111|0x87D17531|20001:No host name|
|-2016316112|0x87D17530|20000:Cannot create account|
|-2016317110|0x87D1714A|19002:Account not unique|
|-2016317111|0x87D17149|19001:No host name|
|-2016317112|0x87D17148|19000:Cannot create account|
|-2016318110|0x87D16D62|18002:Invalid credentials|
|-2016318111|0x87D16D61|18001:Host unreachable|
|-2016318112|0x87D16D60|18000:Unknown error|
|-2016319110|0x87D1697A|17002:Account not unique|
|-2016319111|0x87D16979|17001:No host name|
|-2016319112|0x87D16978|17000:Cannot create account|
|-2016320110|0x87D16592|16002:Account not unique|
|-2016320111|0x87D16591|16001:No host name|
|-2016320112|0x87D16590|16000:Cannot create subscription|
|-2016321109|0x87D161AB|15003:Invalid certificate|
|-2016321110|0x87D161AA|15002:Cannot lock network configuration|
|-2016321111|0x87D161A9|15001:Cannot remove VPN|
|-2016321112|0x87D161A8|15000:Cannot install VPN|
|-2016322110|0x87D15DC2|14002:Cloud configuration already exists|
|-2016322111|0x87D15DC1|14001:Device locked|
|-2016322112|0x87D15DC0|14000:Invalid field|
|-2016323107|0x87D159DD|13005:Cannot set up proxy|
|-2016323108|0x87D159DC|13004:Cannot set up EAP|
|-2016323109|0x87D159DB|13003:Cannot create WiFi configuration|
|-2016323110|0x87D159DA|13002:Password required|
|-2016323111|0x87D159D9|13001:Username required|
|-2016323112|0x87D159D8|13000:Cannot install|
|-2016324070|0x87D1561A|12042:Unknown locale code|
|-2016324071|0x87D15619|12041:Unknown language code|
|-2016324072|0x87D15618|12040:iTunes store login required|
|-2016324073|0x87D15617|12039:(unused)|
|-2016324074|0x87D15616|12038:App not managed|
|-2016324075|0x87D15615|12037:Invalid redemption code|
|-2016324076|0x87D15614|12036:Cannot remove app in current state|
|-2016324077|0x87D15613|12035:App cannot be purchased|
|-2016324078|0x87D15612|12034:URL is not HTTPS|
|-2016324079|0x87D15611|12033:Invalid manifest|
|-2016324080|0x87D15610|12032:Too many apps in manifest|
|-2016324081|0x87D1560F|12031:App installation disabled|
|-2016324082|0x87D1560E|12030:Invalid URL|
|-2016324083|0x87D1560D|12029:App not managed|
|-2016324084|0x87D1560C|12028:Not waiting for redemption|
|-2016324085|0x87D1560B|12027:Not an app|
|-2016324086|0x87D1560A|12026:App already queued|
|-2016324087|0x87D15609|12025:App already installed|
|-2016324088|0x87D15608|12024:Could not validate app manifest|
|-2016324089|0x87D15607|12023:Could not validate app iD|
|-2016324090|0x87D15606|12022:Invalid topic|
|-2016324091|0x87D15605|12021:Invalid request type|
|-2016324092|0x87D15604|12020:Unauthorized by server|
|-2016324093|0x87D15603|12019:Cannot copy escrow secret|
|-2016324094|0x87D15602|12018:Cannot copy escrow keybag data|
|-2016324095|0x87D15601|12017:Cannot create escrow keybag|
|-2016324096|0x87D15600|12016:Missing identity|
|-2016324097|0x87D155FF|12015:Cannot get push token|
|-2016324098|0x87D155FE|12014:Provisioning profile not managed|
|-2016324099|0x87D155FD|12013:Profile not managed|
|-2016324100|0x87D155FC|12012:MDM replacement mismatch|
|-2016324101|0x87D155FB|12011:Invalid MDM configuration|
|-2016324102|0x87D155FA|12010:Internal inconsistency error|
|-2016324103|0x87D155F9|12009:Invalid replacement profile|
|-2016324104|0x87D155F8|12008:Malformed request|
|-2016324105|0x87D155F7|12007:Not authorized|
|-2016324106|0x87D155F6|12006:Redirect refused|
|-2016324107|0x87D155F5|12005:Cannot find certificate|
|-2016324108|0x87D155F4|12004:Invalid push certificate|
|-2016324109|0x87D155F3|12003:Invalid challenge response|
|-2016324110|0x87D155F2|12002:Cannot check in|
|-2016324111|0x87D155F1|12001:Multiple MDM instances|
|-2016324112|0x87D155F0|12000:Invalid access rights|
|-2016325111|0x87D15209|11001:Custom APN already installed|
|-2016325112|0x87D15208|11000:Cannot install APN|
|-2016326111|0x87D14E21|10001:Invalid signer|
|-2016326112|0x87D14E20|10000:Cannot install defaults|
|-2016327106|0x87D14A3E|9006:Certificate is not an identity|
|-2016327107|0x87D14A3D|9005:Certificate is malformed|
|-2016327108|0x87D14A3C|9004:Cannot store root certificate|
|-2016327109|0x87D14A3B|9003:Cannot store WAPI data|
|-2016327110|0x87D14A3A|9002:Cannot store certificate|
|-2016327111|0x87D14A39|9001:Too many certificates in a payload|
|-2016327112|0x87D14A38|9000:Invalid password|
|-2016328112|0x87D14650|8000:Cannot install Web Clip|
|-2016329105|0x87D1426F|7007:SMTP account is misconfigured|
|-2016329106|0x87D1426E|7006:POP account is misconfigured|
|-2016329107|0x87D1426D|7005:IMAP account is misconfigured|
|-2016329108|0x87D1426C|7004:SMIME certificate is bad|
|-2016329109|0x87D1426B|7003:SMIME certificate not found|
|-2016329110|0x87D1426A|7002:Unknown error occurred during validation|
|-2016329111|0x87D14269|7001:Invalid credentials|
|-2016329112|0x87D14268|7000:Host unreachable|
|-2016330110|0x87D13E82|6002:Cannot create query|
|-2016330111|0x87D13E81|6001:Empty string|
|-2016330112|0x87D13E80|6000:Keychain system error|
|-2016331097|0x87D13AA7|5015:Cannot set grace period|
|-2016331098|0x87D13AA6|5014:Cannot set passcode|
|-2016331099|0x87D13AA5|5013:Cannot clear passcode|
|-2016331100|0x87D13AA4|5012:(unused)|
|-2016331101||5011:Wrong passcode|
|-2016331102||5010:Device locked|
|-2016331103|0x87D13AA4|5009:(unused)|
|-2016331104|0x87D13AA0|5008:Passcode too recent|
|-2016331105|0x87D13A9F|5007:Passcode expired|
|-2016331106|0x87D13AA3|5006:Passcode requires alpha characters|
|-2016331107|0x87D13A9D|5005:Passcode requires number|
|-2016331108|0x87D13A9C|5004:Passcode has ascending descending characters|
|2016331109|0x87D13A9B|5003:Passcode has repeating characters|
|-2016331110|0x87D13A9A|5002:Too few complex characters|
|-2016331111|0x87D13A99|5001:Too few unique characters|
|-2016331112|0x87D13A98|5000:Passcode too short|
|-2016332093|0x87D136C3|4019:Multiple App Lock payloads|
|-2016332094|0x87D136C2|4018:Multiple APN or Cellular payloads|
|-2016332095|0x87D136C1|4017:Multiple global HTTPProxy payloads|
|-2016332096|0x87D136C0|4016:(Internal error)|
|-2016332097|0x87D136BF|4015:Replacement profile does not contain an MDM payload|
|-2016332098|0x87D136BE|4014:No device identity available|
|-2016332099|0x87D136BD|4013:Update failed|
|-2016332100|0x87D136BC|4012:Profile is not updatable|
|-2016332101|0x87D136BB|4011:Final profile is not a configuration profile|
|-2016332102|0x87D136BA|4010:Updated profile does not have the same identifier|
|-2016332103|0x87D136B9|4009:Device locked|
|-2016332104|0x87D136B8|4008:Mismatched certificates|
|-2016332105|0x87D136B7|4007:Unrecognized file format|
|-2016332106|0x87D136B6|4006:Profile removal date is in the past|
|-2016332107|0x87D136B5|4005:Passcode does not comply|
|-2016332108|0x87D136B4|4004:User cancelled installation|
|-2016332109|0x87D136B3|4003:Profile not queued for installation|
|-2016332110|0x87D136B2|4002:Duplicate UUID|
|-2016332111|0x87D136B1|4001:Installation failure|
|-2016332112|0x87D136B0|4000:Cannot parse profile|
|2016333111|0x87D132C9|3001:Inconsistent value comparison sense (internal error)|
|-2016333112|0x87D132C8|3000:Inconsistent restriction sense (internal error)|
|-2016334108|0x87D12EE4|2004:Unsupported field value|
|-2016334109|0x87D12EE3|2003:Bad data type in field|
|-2016334110|0x87D12EE2|2002:Missing required field|
|-2016334111|0x87D12EE1|2001:Unsupported payload version|
|-2016334112|0x87D12EE0|2000:Malformed Payload|
|-2016335102|0x87D12B02|1010:Unsupported field value|
|-2016335103|0x87D12B01|1009:Profile installation failure|
|-2016335104|0x87D12B00|1008:Non-unique payload identifiers|
|-2016335105|0x87D12AFF|1007:Non-unique UUIDs|
|-2016335106|0x87D12AFE|1006:Cannot decrypt|
|-2016335107|0x87D12AFD|1005:Empty profile|
|-2016335108|0x87D12AFC|1004:Bad signature|
|-2016335109|0x87D12AFB|1003:Bad data type in field|
|-2016335110|0x87D12AFA|1002:Missing required field|
|-2016335111|0x87D12AF9|1001:Unsupported profile version|
|-2016335112|0x87D12AF8|1000:Malformed profile|

## OMA response codes

|Status code|Hexadecimal error code|Error message|
|---------------|--------------------------|-----------------|
|-2016344008|0x87D10838|(1404): Certificate access denied|
|2016344009|0x87D10837|(1403): Certificate not found|
|-2016344010|0x87D10836|DCMO(1402): The Operation failed|
|-2016344011|0x87D10835|DCMO(1401): User chose not to accept the operation when prompted|
|-2016344012|0x87D10834|DCMO(1400): Client error|
|-2016344108|0x87D107D4|DCMO(1204): Device Capability is disabled and User is allowed to re-enable it|
|-2016344109|0x87D107D3|DCMO(1203): Device Capability is disabled and User is not allowed to re-enable it|
|-2016344110|0x87D107D2|DCMO(1202): Enable operation is performed successfully but the Device Capability is currently detached|
|-2016344111|0xF3FB4D95|DCMO(1201): Enable operation is performed successfully and the Device Capability is currently attached|
|-2016344112|0x87D107D0|DCMO(1200): Operation is performed successfully|
|2016345595|0x87D10205|Syncml(517): The response to an atomic command was too large to fit in a single message.|
|-2016345596|0x87D10204|Syncml(516): Command was inside Atomic element and Atomic failed. This command was not rolled back successfully.|
|-2016345598|0x87D10202|Syncml(514): The SyncML command was not completed successfully, since the operation was already cancelled before processing the command.|
|-2016345599|0x87D10201|Syncml(513): The recipient does not support or refuses to support the specified version of the SyncML Synchronization Protocol used in the request SyncML Message.|
|-2016345600|0x87D10200|Syncml(512): An application error occurred during the synchronization session.|
|-2016345601|0x87D101FF|Syncml(511): A severe error occurred in the server while processing the request.|
|-2016345602|0x87D101FE|Syncml(510): An error occurred while processing the request. The error is related to a failure in the recipient data store.|
|-2016345603|0x87D101FD|Syncml(509): Reserved for future use.|
|2016345604|0x87D101FC|Syncml(508): An error occurred that necessitates a refresh of the current synchronization state of the client with the server.|
|-2016345605|0x87D101FB|Syncml(507): The error caused all SyncML commands within an Atomic element type to fail.|
|-2016345606|0x87D101FA|Syncml(506): An application error occurred while processing the request.|
|-2016345607|0x87D101F9|Syncml(505): The recipient does not support or refuses to support the specified version of SyncML DTD used in the request SyncML Message.|
|-2016345608|=0x87D101F8|Syncml(504): The recipient, while acting as a gateway or proxy, did not receive a timely response from the upstream recipient specified by the URI (e.g. HTTP, FTP, LDAP) or some other auxiliary recipient (e.g. DNS) it needed to access in attempting to complete the request.|
|-2016345609|0x87D101F7|Syncml(503): The recipient is currently unable to handle the request due to a temporary overloading or maintenance of the recipient.|
|-2016345610|0x87D101F6|Syncml(502): The recipient, while acting as a gateway or proxy, received an invalid response from the upstream recipient it accessed in attempting to fulfill the request.|
|-2016345611|0x87D101F5|Syncml(501): The recipient does not support the command required to fulfill the request.|
|-2016345612|0x87D101F4|Syncml(500): The recipient encountered an unexpected condition which prevented it from fulfilling the request|
|2016345684|0x87D101AC|Syncml(428): Move failed|
|-2016345685|0x87D101AB|Syncml(427): Parent cannot be deleted since it contains children.|
|-2016345686|0x87D101AA|Syncml(426): Partial item not accepted.|
|-2016345687|0x87D101A9|Syncml(425): The requested command failed because the sender does not have adequate access control permissions (ACL) on the recipient.|
|-2016345688|0x87D101A8|Syncml(424): The chunked object was received, but the size of the received object did not match the size declared within the first chunk.|
|-2016345689|0x87D101A7|Syncml(423): The requested command failed because the "Soft Deleted" item was previously "Hard Deleted" on the server.|
|-2016345690|0x87D101A6|Syncml(422): The requested command failed on the server because the CGI scripting in the LocURI was incorrectly formed.|
|-2016345691|0x87D101A5|Syncml(421): The requested command failed on the server because the specified search grammar was not known.|
|-2016345692|0x87D101A4|Syncml(420): The recipient has no more storage space for the remaining synchronization data.|
|-2016345693|0x87D101A3|Syncml(419): The client request created a conflict which was resolved by the server command winning.|
|-2016345694|0x87D101A2|Syncml(418): The requested Put or Add command failed because the target already exists.|
|2016345695|0x87D101A1|Syncml(417): The request failed at this time and the originator should retry the request later.|
|-2016345696|0x87D101A0|Syncml(416): The request failed because the specified byte size in the request was too big.|
|-2016345697|0x87D1019F|Syncml(415): Unsupported media type or format.|
|-2016345698|0x87D1019E|Syncml(414): The requested command failed because the target URI is too long for what the recipient is able or willing to process.|
|-2016345699|0x87D1019D|Syncml(413): The recipient is refusing to perform the requested command because the requested item is larger than the recipient is able or willing to process.|
|-2016345700|0x87D1019C|Syncml(412): The requested command failed on the recipient because it was incomplete or incorrectly formed.|
|-2016345701|0x87D1019B|Syncml(411): The requested command must be accompanied by byte size or length information in the Meta element type.|
|-2016345702|0x87D1019A|Syncml(410): The requested target is no longer on the recipient and no forwarding URI is known.|
|-2016345703|0x87D10199|Syncml(409): The requested failed because of an update conflict between the client and server versions of the data.|
|-2016345704|0x87D10198|Syncml(408): An expected message was not received within the required period of time.|
|-2016345705|0x87D10197|Syncml(407): The requested command failed because the originator must provide proper authentication.|
|-2016345706|0x87D10196|Syncml(406): The requested command failed because an optional feature in the request was not supported.|
|-2016345707|0x87D10195|Syncml(405): The requested command is not allowed on the target.|
|-2016345708|0x87D10194|Syncml(404): The requested target was not found.|
|-2016345709|0x87D10193|Syncml(403): The requested command failed, but the recipient understood the requested command.|
|-2016345710|0x87D10192|Syncml(402): The requested command failed because proper payment is needed.|
|-2016345711|0x87D10191|Syncml(401): The requested command failed because the requestor must provide proper authentication.|
|-2016345712|0x87D10190|Syncml(400): The requested command could not be performed because of malformed syntax in the command.|
|-2016345807|0x87D10131|Syncml(305): The requested target must be accessed through the specified proxy URI.|
|-2016345808|0x87D10130|Syncml(304):The requested SyncML command was not executed on the target.|
|-2016345809|0x87D1012F|Syncml(303): The requested target can be found at another URI.|
|-2016345810|0x87D1012E|Syncml(302): The requested target has temporarily moved to a different URI.|
|-2016345811|0x87D1012D|Syncml(301): The requested target has a new URI.|
|-2016345812|0x87D1012C|Syncml(300): The requested target is one of a number of multiple alternatives requested target.|
|-2016345896|0x87D100D8|Syncml(216): A command was inside Atomic element and Atomic failed. This command was rolled back successfully.|
|-2016345897|0x87D100D7|Syncml(215): A command was not executed, as a result of user interaction and user chose not to accept the choice.|
|-2016345898|0x87D100D6|Syncml(214): Operation cancelled. The SyncML command completed successfully, but no more commands will be processed within the session.|
|-2016345899|0x87D100D5|Syncml(213): Chunked item accepted and buffered|
|-2016345900|0x87D100D4|Syncml(212): Authentication accepted. No further authentication is needed for the remainder of the synchronization session. This response code can only be used in response to a request in which the credentials were provided.|
|-2016345901|0x87D100D3|Syncml(211): Item not deleted. The requested item was not found. It could have been previously deleted.|
|-2016345902|0x87D100D2|Syncml(210): Delete without archive. The response indicates that the requested data was successfully deleted, but that it was not archived prior to deletion because this OPTIONAL feature was not supported by the implementation.|
|-2016345903|0x87D100D1|Conflict resolved with duplicate. The response indicates that the request created an update conflict; which was resolved with a duplication of the client's data being created in the server database. The response includes both the target URI of the duplicate in the Item of the Status. In addition, in the case of a two-way synchronization, an Add command is returned with the duplicate data definition.|
|-2016345904|0x87D100D0|Conflict resolved with client's command "winning". The response indicates that there was an update conflict; which was resolved by the client command winning.|
|-2016345905|0x87D100CF|Conflict resolved with merge. The response indicates that the request created a conflict; which was resolved with a merge of the client and server instances of the data. The response includes both the Target and Source URLs in the Item of the Status. In addition, a Replace command is returned with the merged data.|
|-2016345906|0x87D100CE|The response indicates that only part of the command was completed. If the remainder of the command can be completed later, then when completed another appropriate completion request status code SHOULD be created.|
|-2016345907|0x87D100CD|The source SHOULD update their content. The originator of the request is being told that their content SHOULD be synchronized to get an up to date version.|
|-2016345908|0x87D100CC|The request was successfully completed but no data is being returned. The response code is also returned in response to a Get when the target has no content.|
|-2016345909|0x87D100CB|Non-authoritative response. The request is being responded to by an entity other than the one targeted. The response is only to be returned when the request would have been resulted in a 200 response code from the authoritative target.|
|-2016345910|0x87D100CA|Accepted for processing. The request to either run a remote execution of an application or to alert a user or application was successfully performed.|
|-2016345911|0x87D100C9|The requested item was added.|
|-2016345912|0x87D100C8|The SyncML command completed successfully.|
|-2016346011|0x87D10065|The specified SyncML command is being carried out, but has not yet completed.| 
--->

### <span data-ttu-id="d6ac5-192">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d6ac5-192">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="d6ac5-193">Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](get-support.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="d6ac5-193">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](get-support.md).</span></span>