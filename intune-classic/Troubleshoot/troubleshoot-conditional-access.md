---
title: Solucionar problemas de acesso condicional
description: "O que fazer quando os usuários não obtêm acesso aos recursos por meio de acesso condicional do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 433fc32c-ca9c-4bad-9616-852c72faf996
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 04b1785c0b75d4668879488e5221d8b8c2794834
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="b559f-103">Solucionar problemas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="b559f-103">Troubleshoot conditional access</span></span>
=======
# Solucionar problemas de acesso condicional
>>>>>>> live
<a id="troubleshoot-conditional-access" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b559f-104">Normalmente, um usuário está tentando acessar o email ou o SharePoint e recebe uma solicitação para registrar.</span><span class="sxs-lookup"><span data-stu-id="b559f-104">Typically, a user is trying to access email or SharePoint and receives a prompt to enroll.</span></span> <span data-ttu-id="b559f-105">Essa solicitação levará o usuário para o portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b559f-105">That prompt will lead the user to the company portal.</span></span>

<span data-ttu-id="b559f-106">Este tópico descreve o que fazer quando os usuários não obtêm acesso aos recursos por meio de acesso condicional do Intune.</span><span class="sxs-lookup"><span data-stu-id="b559f-106">This topic describes what to do when your users fail to get access to resources through Intune conditional access.</span></span>


<<<<<<< HEAD
## <span data-ttu-id="b559f-107">Os conceitos básicos para o sucesso no acesso condicional</span><span class="sxs-lookup"><span data-stu-id="b559f-107">The basics for success in conditional access</span></span>
=======
## Os conceitos básicos para o sucesso no acesso condicional
>>>>>>> live
<a id="the-basics-for-success-in-conditional-access" class="xliff"></a>

<span data-ttu-id="b559f-108">Para que o acesso condicional funcione, são necessárias as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="b559f-108">In order to conditional access to work, you need the following conditions:</span></span>

-   <span data-ttu-id="b559f-109">O dispositivo deve ser gerenciado pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="b559f-109">The device must be managed by Intune</span></span>
-   <span data-ttu-id="b559f-110">O dispositivo deve estar registrado no AAD (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="b559f-110">The device must be registered with Azure Active Directory (AAD) .</span></span> <span data-ttu-id="b559f-111">Em circunstâncias normais, esse registro ocorre automaticamente durante o registro do Intune.</span><span class="sxs-lookup"><span data-stu-id="b559f-111">Under normal circumcstances this registration takes place automatically during Intune enrollment</span></span>
-   <span data-ttu-id="b559f-112">O dispositivo deve ser compatível com suas políticas de conformidade do Intune, tanto para o dispositivo quanto para o usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b559f-112">The device must be compliant with your Intune compliance policies, for the device, and for the user of the device.</span></span>  <span data-ttu-id="b559f-113">Se não houver nenhuma política de conformidade, o registro do Intune será suficiente.</span><span class="sxs-lookup"><span data-stu-id="b559f-113">If there are no compliance policies, Intune enrollment is sufficient.</span></span>
-   <span data-ttu-id="b559f-114">O Exchange ActiveSync deverá ser ativado no dispositivo se o usuário estiver recuperando mensagens por meio do cliente de email nativo do dispositivo em vez de por meio do Outlook.</span><span class="sxs-lookup"><span data-stu-id="b559f-114">Exchange ActiveSync must be activated on the device if the user is retrieving mail through the device's native mail client rather than through Outlook.</span></span>     <span data-ttu-id="b559f-115">Isso ocorre automaticamente para dispositivos iOS, Windows Phone e Android/KNOX Standard.</span><span class="sxs-lookup"><span data-stu-id="b559f-115">This happens automatically for iOS, Windows Phone and Android/KNOX Standard devices.</span></span>
-   <span data-ttu-id="b559f-116">O Intune Exchange Connector deve estar configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="b559f-116">Your Intune Exchange Connector should be properly configured.</span></span> <span data-ttu-id="b559f-117">Consulte [Troubleshooting the Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) (Solução de problemas do Exchange Connector no Microsoft Intune) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b559f-117">See [Troubleshooting the Exchange Connector in Microsoft Intune](troubleshoot-exchange-connector.md) for more information.</span></span>

<span data-ttu-id="b559f-118">Essas condições podem ser exibidas para cada dispositivo no Portal de gerenciamento do Azure e no relatório de inventário de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b559f-118">These conditions can be viewed for each device in the Azure Management Portal and in the device inventory report.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="b559f-119">Problemas de registro</span><span class="sxs-lookup"><span data-stu-id="b559f-119">Enrollment issues</span></span>
=======
## Problemas de registro
>>>>>>> live
<a id="enrollment-issues" class="xliff"></a>

 -  <span data-ttu-id="b559f-120">O dispositivo não está registrado, portanto o registro resolverá o problema.</span><span class="sxs-lookup"><span data-stu-id="b559f-120">The device isn't enrolled, so enrollment will resolve the issue.</span></span>
 -  <span data-ttu-id="b559f-121">O usuário registrou o dispositivo, mas houve falha no ingresso no local de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b559f-121">The user enrolled the device, but the workplace join failed.</span></span> <span data-ttu-id="b559f-122">O usuário deve atualizar o registro por meio do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="b559f-122">The user should update the enrollment from the company portal.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="b559f-123">Problemas de conformidade</span><span class="sxs-lookup"><span data-stu-id="b559f-123">Compliance issues</span></span>
=======
## Problemas de conformidade
>>>>>>> live
<a id="compliance-issues" class="xliff"></a>

 -  <span data-ttu-id="b559f-124">O dispositivo não é compatível com a política do Intune.</span><span class="sxs-lookup"><span data-stu-id="b559f-124">The device is not compliant with Intune policy.</span></span> <span data-ttu-id="b559f-125">Problemas comuns são requisitos de senha e criptografia.</span><span class="sxs-lookup"><span data-stu-id="b559f-125">Common issues are encryption and password requirements.</span></span> <span data-ttu-id="b559f-126">O usuário será redirecionado para o portal da empresa, em que ele pode configurar seu dispositivo para que seja compatível.</span><span class="sxs-lookup"><span data-stu-id="b559f-126">The user will be redirected to the company portal, where they can configure their device to be compliant.</span></span>
 -  <span data-ttu-id="b559f-127">Pode levar algum tempo para que as informações de conformidade sejam registradas para um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b559f-127">It may take some time for compliance information to be registered for a device.</span></span> <span data-ttu-id="b559f-128">Aguarde alguns minutos e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="b559f-128">Wait a few minutes and try again.</span></span>
 -  <span data-ttu-id="b559f-129">Para dispositivos iOS:</span><span class="sxs-lookup"><span data-stu-id="b559f-129">For iOS devices:</span></span>
     -   <span data-ttu-id="b559f-130">Um perfil de email existente criado pelo usuário bloqueia a implantação de um perfil criado pelo administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="b559f-130">An existing email profile created by the user will block the deployment of an Intune admin-created profile.</span></span> <span data-ttu-id="b559f-131">Isso é um problema comum, pois usuários do iOS normalmente vão criar um perfil de email e, depois, se registrar.</span><span class="sxs-lookup"><span data-stu-id="b559f-131">This is a common problem as iOS users will typically create an email profile, then enroll.</span></span> <span data-ttu-id="b559f-132">O portal da empresa informará ao usuário que ele não é compatível devido ao seu perfil de email configurado manualmente e solicitará que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="b559f-132">The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed.</span></span> <span data-ttu-id="b559f-133">Para evitar o problema, instrua os usuários a registrar sem instalar um perfil de email e permitir que o Intune implante o perfil.</span><span class="sxs-lookup"><span data-stu-id="b559f-133">To prevent the problem instruct your users to enroll without installing an email profile and to allow Intune to deploy the profile.</span></span>
     -   <span data-ttu-id="b559f-134">Um dispositivo iOS pode ficar parado em um estado de verificação de conformidade, impedindo que o usuário inicie outro check-in.</span><span class="sxs-lookup"><span data-stu-id="b559f-134">An iOS device may get stuck in a checking-compliance state, preventing the user from initiating another check-in.</span></span> <span data-ttu-id="b559f-135">Reiniciar o portal da empresa pode corrigir isso, e o estado da conformidade refletirá o estado do dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="b559f-135">Restarting the company portal may fix this, and the compliance state will reflect the device state in Intune.</span></span> <span data-ttu-id="b559f-136">Depois que todos os dados forem coletados de uma sincronização de dispositivo, a verificação de conformidade será rápida, levando em média menos da metade de uma segundo.</span><span class="sxs-lookup"><span data-stu-id="b559f-136">After all of the data is collected from a device sync the compliance check is, fast, less than half a second on average.</span></span>

        <span data-ttu-id="b559f-137">Normalmente, o motivo para os dispositivos permanecerem nesse estado é porque eles estão com problemas de conexão com o serviço ou a sincronização está levando muito tempo.</span><span class="sxs-lookup"><span data-stu-id="b559f-137">Typically, the reason devices stay in this state is because they are having trouble connecting to the service or the sync is taking a long time.</span></span>  <span data-ttu-id="b559f-138">Se o problema persistir em diferentes configurações de rede (celular, Wi-Fi, VPN), após várias reinicializações do dispositivo e após a verificação de que o SSP está atualizado no dispositivo, entre em contato com o Suporte da Microsoft conforme descrito em [Como obter suporte para o Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="b559f-138">If the problem persists on different network configurations (cellular, Wi-Fi, VPN), through device restarts, and after verifying that the SSP is up-to-date on the device, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

 - <span data-ttu-id="b559f-139">Para dispositivos Android:</span><span class="sxs-lookup"><span data-stu-id="b559f-139">For Android devices:</span></span>
    - <span data-ttu-id="b559f-140">Certos dispositivos Android parecem ser criptografados, mas o aplicativo de Portal da Empresa reconhece esses dispositivos como não criptografados.</span><span class="sxs-lookup"><span data-stu-id="b559f-140">Certain Android devices may seem to be encrypted, but the Company Portal app recognizes these devices as not encrypted.</span></span> 
    
        -   <span data-ttu-id="b559f-141">Os dispositivos nesse estado exigem que o usuário defina uma senha de inicialização segura.</span><span class="sxs-lookup"><span data-stu-id="b559f-141">Devices that are in this state require the user to set a secure start-up passcode.</span></span> <span data-ttu-id="b559f-142">O usuário verá uma notificação do dispositivo no aplicativo Portal da Empresa solicitando uma senha de inicialização para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b559f-142">The user will see a device notification from the Company Portal app asking to set a start-up passcode for the device.</span></span> <span data-ttu-id="b559f-143">Depois de tocar na notificação do dispositivo e confirmar o PIN existente ou a senha, escolha a opção **Exigir PIN para iniciar o dispositivo** na tela **Proteger inicialização**.</span><span class="sxs-lookup"><span data-stu-id="b559f-143">After tapping the device notification and confirming the existing PIN or password, choose the **Require PIN to start device** option on the **Secure start-up** screen.</span></span> <span data-ttu-id="b559f-144">Em seguida, toque no botão **Verificar Conformidade** do dispositivo no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="b559f-144">Then, tap the **Check Compliance** button for the device from the Company Portal app.</span></span> <span data-ttu-id="b559f-145">Agora o dispositivo deve ser detectado como criptografado.</span><span class="sxs-lookup"><span data-stu-id="b559f-145">The device should now be detected as encrypted.</span></span>
    
        -   <span data-ttu-id="b559f-146">Alguns fabricantes de dispositivos criptografam seus dispositivos usando um PIN padrão em vez do PIN secreto definido pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="b559f-146">Some device manufacturers encrypt their devices using a default PIN instead of the secret PIN set by the user.</span></span> <span data-ttu-id="b559f-147">O Intune reconhece a criptografia usando o PIN padrão como inseguro, pois esse método de criptografia pode colocar os dados no dispositivo em risco, podendo ser acessados por usuários mal-intencionados com acesso físico ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b559f-147">Intune recognizes encryption using the default PIN as insecure because this method of encryption can put the data on the device at risk from malicious users with physical access to the device.</span></span> <span data-ttu-id="b559f-148">Se esse for o problema, considere o uso de [políticas de proteção do aplicativo](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).</span><span class="sxs-lookup"><span data-stu-id="b559f-148">If this is the issue, consider using [app protection policies](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).</span></span>

<<<<<<< HEAD
## <span data-ttu-id="b559f-149">Problemas de política</span><span class="sxs-lookup"><span data-stu-id="b559f-149">Policy issues</span></span>
=======
## Problemas de política
>>>>>>> live
<a id="policy-issues" class="xliff"></a>

<span data-ttu-id="b559f-150">Quando você cria uma política de conformidade e a vincula a uma política de email, ambas as políticas precisam ser implantadas para o mesmo usuário. Portanto, tenha cuidado ao planejar quais políticas são implantadas em quais grupos.</span><span class="sxs-lookup"><span data-stu-id="b559f-150">When you create a compliance policy and link it to an email policy, both policies have to be deployed to the same user, so be careful when planning which policies are deployed to which groups.</span></span> <span data-ttu-id="b559f-151">Os usuários que têm apenas uma política aplicada têm uma probabilidade de descobrir que seus dispositivos não são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="b559f-151">Users that have only one policy applied are likely to find that their devices are not compliant.</span></span>


<<<<<<< HEAD
## <span data-ttu-id="b559f-152">Problemas com o Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="b559f-152">Exchange ActiveSync issues</span></span>
<a id="exchange-activesync-issues" class="xliff"></a>

### <span data-ttu-id="b559f-153">Um dispositivo Android compatível recebe aviso de quarentena</span><span class="sxs-lookup"><span data-stu-id="b559f-153">Compliant Android device gets quarantine notice</span></span>
<a id="compliant-android-device-gets-quarantine-notice" class="xliff"></a>
- <span data-ttu-id="b559f-154">Um dispositivo Android registrado e compatível ainda pode receber um aviso de quarentena ao tentar acessar recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="b559f-154">An Android device that is enrolled and compliant may still get a quarantine notice when trying to access corporate resources.</span></span> <span data-ttu-id="b559f-155">Antes de escolher o link que diz **Começar**, o usuário deve verificar se o portal da empresa não estava aberto quando ele tentou acessar os recursos.</span><span class="sxs-lookup"><span data-stu-id="b559f-155">Before choosing the link that says **Begin**, the user should ensure that the company portal was not open when they tried to access the resources.</span></span> <span data-ttu-id="b559f-156">Os usuários devem fechar o portal da empresa, tente novamente para acessar os recursos e, em seguida, escolher o link **Começar**.</span><span class="sxs-lookup"><span data-stu-id="b559f-156">The users should close the company portal, try again to access the resources, and then choose the **Begin** link.</span></span>

### <span data-ttu-id="b559f-157">Um dispositivo desativado continua tendo acesso.</span><span class="sxs-lookup"><span data-stu-id="b559f-157">Retired device continues to have access.</span></span>
<a id="retired-device-continues-to-have-access" class="xliff"></a>
- <span data-ttu-id="b559f-158">Durante a utilização do Exchange Online, um dispositivo desativado pode continuar tendo acesso por várias horas após a desativação.</span><span class="sxs-lookup"><span data-stu-id="b559f-158">When using Exchange Online, a retired device may continue to have access for several hours after retirement.</span></span> <span data-ttu-id="b559f-159">Isso ocorre porque o Exchange armazena em cache os direitos de acesso por 6 horas.</span><span class="sxs-lookup"><span data-stu-id="b559f-159">This is because Exchange caches access rights for 6 hours.</span></span> <span data-ttu-id="b559f-160">Considere outros meios de proteção de dados em dispositivos desativados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="b559f-160">Consider other means of protecting data on retired devices in this scenario.</span></span>

### <span data-ttu-id="b559f-161">O dispositivo é compatível e registrado com o AAD, mas ainda é bloqueado</span><span class="sxs-lookup"><span data-stu-id="b559f-161">Device is compliant and registered with AAD but still blocked</span></span>
<a id="device-is-compliant-and-registered-with-aad-but-still-blocked" class="xliff"></a>
- <span data-ttu-id="b559f-162">Às vezes, o provisionamento da EASID (ID do Exchange ActiveSync) para o AAD é atrasado.</span><span class="sxs-lookup"><span data-stu-id="b559f-162">Sometimes, provision of the Exchange ActiveSync ID (EASID)  to AAD is delayed.</span></span> <span data-ttu-id="b559f-163">Uma causa comum desse problema é a limitação, então, aguarde alguns minutos e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="b559f-163">A common cause of this issue is throttling, so wait a few minutes and try again.</span></span>

### <span data-ttu-id="b559f-164">Dispositivo bloqueado</span><span class="sxs-lookup"><span data-stu-id="b559f-164">Device blocked</span></span>
=======
## Problemas com o Exchange ActiveSync
<a id="exchange-activesync-issues" class="xliff"></a>

### Um dispositivo Android compatível recebe aviso de quarentena
<a id="compliant-android-device-gets-quarantine-notice" class="xliff"></a>
- Um dispositivo Android registrado e compatível ainda pode receber um aviso de quarentena ao tentar acessar recursos corporativos. Antes de escolher o link que diz **Começar**, o usuário deve verificar se o portal da empresa não estava aberto quando ele tentou acessar os recursos. Os usuários devem fechar o portal da empresa, tente novamente para acessar os recursos e, em seguida, escolher o link **Começar**.

### Um dispositivo desativado continua tendo acesso.
<a id="retired-device-continues-to-have-access" class="xliff"></a>
- Durante a utilização do Exchange Online, um dispositivo desativado pode continuar tendo acesso por várias horas após a desativação. Isso ocorre porque o Exchange armazena em cache os direitos de acesso por 6 horas. Considere outros meios de proteção de dados em dispositivos desativados neste cenário.

### O dispositivo é compatível e registrado com o AAD, mas ainda é bloqueado
<a id="device-is-compliant-and-registered-with-aad-but-still-blocked" class="xliff"></a>
- Às vezes, o provisionamento da EASID (ID do Exchange ActiveSync) para o AAD é atrasado. Uma causa comum desse problema é a limitação, então, aguarde alguns minutos e tente novamente.

### Dispositivo bloqueado
>>>>>>> live
<a id="device-blocked" class="xliff"></a>

<span data-ttu-id="b559f-165">Um dispositivo pode ser bloqueado do Acesso condicional sem receber um email de ativação.</span><span class="sxs-lookup"><span data-stu-id="b559f-165">A device may be blocked from Conditional Access without receiving an activation email.</span></span>

- <span data-ttu-id="b559f-166">Há uma regra padrão do Exchange que coloca os dispositivos em quarentena ou os bloqueia?</span><span class="sxs-lookup"><span data-stu-id="b559f-166">Is there a default Exchange rule which quarantines or blocks devices?</span></span> <span data-ttu-id="b559f-167">Se uma regra padrão bloquear ou colocar os dispositivos em quarentena, os dispositivos não poderão receber o email de ativação do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b559f-167">If a default rule blocks or quarantines devices, devices will not be able to receive the activation email from the Exchange Connector.</span></span> <span data-ttu-id="b559f-168">Isso ocorre por design.</span><span class="sxs-lookup"><span data-stu-id="b559f-168">This is by design.</span></span>
- <span data-ttu-id="b559f-169">A conta de notificação está configurada corretamente conforme descrito na configuração básica?</span><span class="sxs-lookup"><span data-stu-id="b559f-169">Is the notification account properly configured as described in Basic configuration?</span></span>
- <span data-ttu-id="b559f-170">O dispositivo está presente no console de administração do Intune como um dispositivo do Exchange ActiveSync?</span><span class="sxs-lookup"><span data-stu-id="b559f-170">Is the device present in the Intune admin console as an Exchange ActiveSync device?</span></span> <span data-ttu-id="b559f-171">Se não, é provável que a descoberta do dispositivo esteja falhando, provavelmente devido a um problema de sincronização do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b559f-171">If not, it's likely that device discovery is failing, probably because of an Exchange Connector sync issue.</span></span> <span data-ttu-id="b559f-172">Consulte O dispositivo do Exchange ActiveSync não é descoberto no Exchange.</span><span class="sxs-lookup"><span data-stu-id="b559f-172">See Exchange ActiveSync device not discovered from Exchange.</span></span>
- <span data-ttu-id="b559f-173">Verifique os logs do Exchange Connector quanto à atividade EnviarEmail e verifique se há erros.</span><span class="sxs-lookup"><span data-stu-id="b559f-173">Check the Exchange Connector logs for sendemail activity and check for errors.</span></span> <span data-ttu-id="b559f-174">Um exemplo de comando a ser procurado é EnviarEmail da conta de notificação para EmailUsuário.</span><span class="sxs-lookup"><span data-stu-id="b559f-174">An example of the command to search for is SendEmail from notification account to useremail.</span></span>
- <span data-ttu-id="b559f-175">Antes de bloquear o dispositivo, o Exchange Connector envia o email de ativação.</span><span class="sxs-lookup"><span data-stu-id="b559f-175">Before the Exchange Connector blocks the device, it sends the activation email.</span></span> <span data-ttu-id="b559f-176">Se o dispositivo estiver offline, ele poderá não receber o email de ativação.</span><span class="sxs-lookup"><span data-stu-id="b559f-176">If the device is offline, it may not receive the activation email.</span></span> <span data-ttu-id="b559f-177">Verifique se o cliente de email do dispositivo tem recuperação de email usando Push em vez de Pull, pois isso também pode fazer com que o usuário perca o email.</span><span class="sxs-lookup"><span data-stu-id="b559f-177">Check if the device email client has email retrieval using Push instead of Poll as this could also cause the user to miss the email.</span></span> <span data-ttu-id="b559f-178">Mude para Pull e veja se o dispositivo recebe o email.</span><span class="sxs-lookup"><span data-stu-id="b559f-178">Switch to Poll and see if the device receives the email.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="b559f-179">Um dispositivo incompatível não é bloqueado</span><span class="sxs-lookup"><span data-stu-id="b559f-179">Non-compliant device not blocked</span></span>
=======
## Um dispositivo incompatível não é bloqueado
>>>>>>> live
<a id="non-compliant-device-not-blocked" class="xliff"></a>

<span data-ttu-id="b559f-180">Se você encontrar um dispositivo que não é compatível, mas continua tendo acesso, execute as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="b559f-180">If you encounter a device that is not compliant but continues to have access, take the following steps.</span></span>

- <span data-ttu-id="b559f-181">Analise os grupos de Destino e Exclusão.</span><span class="sxs-lookup"><span data-stu-id="b559f-181">Review your Target and Exclusion groups.</span></span> <span data-ttu-id="b559f-182">Se um usuário não estiver no grupo de destino correto ou estiver no grupo de exclusão, ele não será bloqueado.</span><span class="sxs-lookup"><span data-stu-id="b559f-182">If a user isn't in the right target group or is in the exclusion group, they won’t be blocked.</span></span> <span data-ttu-id="b559f-183">Somente os dispositivos de usuários em um grupo de Destino são verificados quanto à conformidade.</span><span class="sxs-lookup"><span data-stu-id="b559f-183">Only devices of users in a Target group are checked for compliance.</span></span>
- <span data-ttu-id="b559f-184">Certifique-se de que o dispositivo esteja sendo descoberto.</span><span class="sxs-lookup"><span data-stu-id="b559f-184">Ensure the device is being discovered.</span></span> <span data-ttu-id="b559f-185">O Exchange Connector está apontando para uma CAS do Exchange 2010 enquanto o usuário está em um servidor Exchange 2013?</span><span class="sxs-lookup"><span data-stu-id="b559f-185">Is the Exchange Connector pointing to an Exchange 2010 CAS while the user is on an Exchange 2013 server?</span></span> <span data-ttu-id="b559f-186">Nesse caso, se a regra padrão do Exchange for Permitir, mesmo se o usuário estiver no grupo de Destino, o Intune não poderá estar ciente da conexão do dispositivo com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="b559f-186">In this case, if the default Exchange rule is Allow, even if the user is in the Target group, Intune can't be aware of the device's connection to Exchange.</span></span>
- <span data-ttu-id="b559f-187">Verifique a existência/estado de acesso do dispositivo no Exchange:</span><span class="sxs-lookup"><span data-stu-id="b559f-187">Check Device Existence/Access State in Exchange:</span></span>
    - <span data-ttu-id="b559f-188">Use este cmdlet do PowerShell para obter uma lista de todos os dispositivos móveis para uma caixa de correio: "Get-ActiveSyncDeviceStatistics -mailbox mbx".</span><span class="sxs-lookup"><span data-stu-id="b559f-188">Use this PowerShell cmdlet to get a list of all mobile devices for a mailbox: "Get-ActiveSyncDeviceStatistics -mailbox mbx'.</span></span> <span data-ttu-id="b559f-189">Caso o dispositivo não esteja listado, ele não está acessando o Exchange.</span><span class="sxs-lookup"><span data-stu-id="b559f-189">If the device isn’t listed then it isn’t accessing Exchange.</span></span>
    - <span data-ttu-id="b559f-190">Se o dispositivo estiver listado, use cmdlet Get-CASmailbox -identity:’upn’ | fl para obter informações detalhadas sobre seu estado de acesso e fornecer essas informações ao Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b559f-190">If the device is listed, use the Get-CASmailbox -identity:’upn’ | fl cmdlet to get detailed information about its access state, and provide that information to Microsoft Support.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="b559f-191">Antes de abrir um tíquete de suporte</span><span class="sxs-lookup"><span data-stu-id="b559f-191">Before you open a support ticket</span></span>
<a id="before-you-open-a-support-ticket" class="xliff"></a>
<span data-ttu-id="b559f-192">Caso esses procedimentos de solução de problemas não resolvam o problema, há informações que o Suporte da Microsoft pode solicitar, como logs de caixa de correio do OWA ou logs do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b559f-192">If these troubleshooting procedures don't resolve your issue, there is information that you may be asked to provide to Microsoft Support, such as OWA mailbox logs or Exchange Connector logs.</span></span>

### <span data-ttu-id="b559f-193">Coletando logs de caixa de correio do OWA</span><span class="sxs-lookup"><span data-stu-id="b559f-193">Collecting OWA mailbox logs</span></span>
=======
## Antes de abrir um tíquete de suporte
<a id="before-you-open-a-support-ticket" class="xliff"></a>
Caso esses procedimentos de solução de problemas não resolvam o problema, há informações que o Suporte da Microsoft pode solicitar, como logs de caixa de correio do OWA ou logs do Exchange Connector.

### Coletando logs de caixa de correio do OWA
>>>>>>> live
<a id="collecting-owa-mailbox-logs" class="xliff"></a>

1. <span data-ttu-id="b559f-194">Faça logon por meio do OWA e escolha o símbolo de configurações (engrenagem) ao lado de seu nome no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="b559f-194">Log on through OWA and choose the settings (gear) symbol next to your name in the upper right corner.</span></span>
2. <span data-ttu-id="b559f-195">Escolha **Opções**</span><span class="sxs-lookup"><span data-stu-id="b559f-195">Choose **Options**</span></span>
3. <span data-ttu-id="b559f-196">Escolha **Telefone** (talvez seja **Dispositivos Móveis**) na coluna à esquerda.</span><span class="sxs-lookup"><span data-stu-id="b559f-196">Choose **Phone** (may say **Mobile Devices**) in the  column on the left side.</span></span>
4. <span data-ttu-id="b559f-197">No menu superior, escolha **Dispositivos Móveis**.</span><span class="sxs-lookup"><span data-stu-id="b559f-197">From the top menu, choose **Mobile Devices**.</span></span>
5. <span data-ttu-id="b559f-198">Escolha seu dispositivo na lista e, em seguida, escolha **Iniciar Registro**.</span><span class="sxs-lookup"><span data-stu-id="b559f-198">Choose your device from the list and then choose **Start Logging**.</span></span>
6. <span data-ttu-id="b559f-199">Quando solicitado, escolha **Sim** na caixa de diálogo pop-up.</span><span class="sxs-lookup"><span data-stu-id="b559f-199">When prompted, choose **Yes** on the pop-up dialog.</span></span>
7. <span data-ttu-id="b559f-200">Execute a ação que causou o problema, para que você possa reproduzi-lo.</span><span class="sxs-lookup"><span data-stu-id="b559f-200">Perform the action that caused the issue, so that you can reproduce it.</span></span>
8. <span data-ttu-id="b559f-201">Aguarde por 1 a 2 minutos e volte para a lista telefônica no OWA.</span><span class="sxs-lookup"><span data-stu-id="b559f-201">Wait 1-2 minutes then go back to the phone list in OWA.</span></span> <span data-ttu-id="b559f-202">Verifique se o seu telefone está selecionado na lista e, no menu superior, escolha **Recuperar Log**.</span><span class="sxs-lookup"><span data-stu-id="b559f-202">Make sure your phone is selected in the list, and then from the top menu choose **Retrieve Log**.</span></span>
9. <span data-ttu-id="b559f-203">Você deve ter recebido um email de si mesmo com um anexo.</span><span class="sxs-lookup"><span data-stu-id="b559f-203">You should receive an email from yourself with an attachment.</span></span> <span data-ttu-id="b559f-204">Quando você abrir um tíquete de suporte, forneça o conteúdo do email ao Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b559f-204">When you open a support ticket, provide the contents of the email to Microsoft Support.</span></span>

<<<<<<< HEAD
### <span data-ttu-id="b559f-205">Logs do Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="b559f-205">Exchange Connector logs</span></span>
<a id="exchange-connector-logs" class="xliff"></a>

#### <span data-ttu-id="b559f-206">Informações gerais sobre logs</span><span class="sxs-lookup"><span data-stu-id="b559f-206">General log information</span></span>
<a id="general-log-information" class="xliff"></a>
<span data-ttu-id="b559f-207">Para exibir logs do Exchange Connector, use a [Ferramenta do Visualizador de Rastreamento do Servidor] (ferramenta do visualizador de rastreamento do servidor (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx').</span><span class="sxs-lookup"><span data-stu-id="b559f-207">To view Exchange Connector logs use the [Server Trace Viewer Tool](server trace viewer tool (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx').</span></span> <span data-ttu-id="b559f-208">Essa ferramenta requer que você baixe o SDK do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="b559f-208">This tool requires that you download the Windows Server SDK.</span></span>
=======
### Logs do Exchange Connector
<a id="exchange-connector-logs" class="xliff"></a>

#### Informações gerais sobre logs
<a id="general-log-information" class="xliff"></a>
Para exibir logs do Exchange Connector, use a [Ferramenta do Visualizador de Rastreamento do Servidor] (ferramenta do visualizador de rastreamento do servidor (https://msdn.microsoft.com/library/ms732023(v=vs.110).aspx'). Essa ferramenta requer que você baixe o SDK do Windows Server.
>>>>>>> live

>[!NOTE]
><span data-ttu-id="b559f-209">Os logs estão localizados em C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs.</span><span class="sxs-lookup"><span data-stu-id="b559f-209">The logs are located in C:\ProgramData\Microsoft\Windows Intune Exchange Connector\Logs.</span></span> <span data-ttu-id="b559f-210">Os logs estão contidos em uma série de 30 arquivos de log que começa com *Connector0.log* e para em *Connector29.log*.</span><span class="sxs-lookup"><span data-stu-id="b559f-210">The logs are contained in a series of 30 log files starting with *Connector0.log* and stopping at *Connector29.log*.</span></span> <span data-ttu-id="b559f-211">Os logs se sobrepõem uns aos outros após 10 MB de dados serem acumulados em um log.</span><span class="sxs-lookup"><span data-stu-id="b559f-211">Logs rollover from one to another after 10MB of data has accumulated in a log.</span></span> <span data-ttu-id="b559f-212">Depois de chegarem a Connector29, os logs recomeçam em Connector0, substituindo os arquivos de log anteriores.</span><span class="sxs-lookup"><span data-stu-id="b559f-212">Once the logs get to Connector29, they will start over at Connector0 again, overwriting previous log files.</span></span>

<<<<<<< HEAD
#### <span data-ttu-id="b559f-213">Localização de logs de sincronização</span><span class="sxs-lookup"><span data-stu-id="b559f-213">Locating sync logs</span></span>
=======
#### Localização de logs de sincronização
>>>>>>> live
<a id="locating-sync-logs" class="xliff"></a>

-    <span data-ttu-id="b559f-214">Localize uma sincronização completa nos logs pesquisando **full sync**.</span><span class="sxs-lookup"><span data-stu-id="b559f-214">Locate a full sync in the logs by searching for **full sync**.</span></span> <span data-ttu-id="b559f-215">O início de uma sincronização completa será marcado por este texto:</span><span class="sxs-lookup"><span data-stu-id="b559f-215">The beginning of a full sync will be marked by this text:</span></span>

    <span data-ttu-id="b559f-216">“Handling command: Getting the mobile device list without a time filter (full sync) for <number> users”</span><span class="sxs-lookup"><span data-stu-id="b559f-216">'Handling command: Getting the mobile device list without a time filter (full sync) for <number> users\`</span></span>

    <span data-ttu-id="b559f-217">O final do log de uma sincronização completa será semelhante a:</span><span class="sxs-lookup"><span data-stu-id="b559f-217">The end of the log for a full sync looks like this:</span></span>

    <span data-ttu-id="b559f-218">Getting the mobile device list without a time filter (full sync) for 4 users completed successfully.</span><span class="sxs-lookup"><span data-stu-id="b559f-218">Getting the mobile device list without a time filter (full sync) for 4 users completed successfully.</span></span> <span data-ttu-id="b559f-219">Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','</span><span class="sxs-lookup"><span data-stu-id="b559f-219">Details: Inventory command result - Devices synced: 0 Commmand ID: commandIDGUID' Exchange health: 'Server health 'Name: 'PowerShellExchangeServer: <Name=mymailservername>' Status: Connected','</span></span>

-   <span data-ttu-id="b559f-220">Localize uma sincronização rápida (delta) nos logs pesquisando **quick sync**.</span><span class="sxs-lookup"><span data-stu-id="b559f-220">Locate a quick (delta) sync in the logs by searching for **quick sync**.</span></span>

<<<<<<< HEAD
##### <span data-ttu-id="b559f-221">Exceções no comando Get next</span><span class="sxs-lookup"><span data-stu-id="b559f-221">Exceptions in Get next command</span></span>
<a id="exceptions-in-get-next-command" class="xliff"></a>
<span data-ttu-id="b559f-222">Verifique os logs do Exchange Connector quanto a exceções no comando **Get next** e forneça-as ao Suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b559f-222">Check the Exchange Connector logs for exceptions in **Get next command**, and provide these to Microsoft Support.</span></span>

#### <span data-ttu-id="b559f-223">Log detalhado</span><span class="sxs-lookup"><span data-stu-id="b559f-223">Verbose logging</span></span>
=======
##### Exceções no comando Get next
<a id="exceptions-in-get-next-command" class="xliff"></a>
Verifique os logs do Exchange Connector quanto a exceções no comando **Get next** e forneça-as ao Suporte da Microsoft.

#### Log detalhado
>>>>>>> live
<a id="verbose-logging" class="xliff"></a>

<span data-ttu-id="b559f-224">Para habilitar o log detalhado:</span><span class="sxs-lookup"><span data-stu-id="b559f-224">To enable verbose logging:</span></span>

1.  <span data-ttu-id="b559f-225">Abra o arquivo de configuração de rastreamento do Exchange Connector.</span><span class="sxs-lookup"><span data-stu-id="b559f-225">Open the Exchange Connector tracing configuration file.</span></span> <span data-ttu-id="b559f-226">O arquivo está localizado em: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.</span><span class="sxs-lookup"><span data-stu-id="b559f-226">The file is located at: %ProgramData%\Microsoft\Windows Intune Exchange Connector\TracingConfiguration.xml.</span></span>
2.  <span data-ttu-id="b559f-227">Localize TraceSourceLine com a seguinte chave: OnPremisesExchangeConnectorService</span><span class="sxs-lookup"><span data-stu-id="b559f-227">Locate the TraceSourceLine with the following key: OnPremisesExchangeConnectorService</span></span>
3.  <span data-ttu-id="b559f-228">Alterar o valor do nó **SourceLevel** de **Warning ActivityTracing** (o padrão) para **Verbose ActivityTracing**, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="b559f-228">Change the **SourceLevel** node value from **Warning ActivityTracing** (the default) to **Verbose ActivityTracing**, as shown below.</span></span>

<<<<<<< HEAD
    <span data-ttu-id="b559f-229"><TraceSourceLine> <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key> <Value xsi:type="TraceSource"> <SourceLevel>All</SourceLevel> <Listeners> <Listener> <ListenerType>CircularTraceListener</ListenerType> <SourceLevel>Verbose ActivityTracing</SourceLevel> <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes> <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName> <FileQuota>30</FileQuota> </Listener> </Listeners> </Value>
    </TraceSourceLine></span><span class="sxs-lookup"><span data-stu-id="b559f-229"><TraceSourceLine> <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key> <Value xsi:type="TraceSource"> <SourceLevel>All</SourceLevel> <Listeners> <Listener> <ListenerType>CircularTraceListener</ListenerType> <SourceLevel>Verbose ActivityTracing</SourceLevel> <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes> <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName> <FileQuota>30</FileQuota> </Listener> </Listeners> </Value>
    </TraceSourceLine></span></span>



### <span data-ttu-id="b559f-230">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b559f-230">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="b559f-231">Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="b559f-231">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
=======
    <TraceSourceLine> <Key xsi:type="xsd:string">OnPremisesExchangeConnectorService</Key> <Value xsi:type="TraceSource"> <SourceLevel>All</SourceLevel> <Listeners> <Listener> <ListenerType>CircularTraceListener</ListenerType> <SourceLevel>Verbose ActivityTracing</SourceLevel> <FileSizeQuotaInBytes>10000000</FileSizeQuotaInBytes> <FileName>Microsoft\Windows Intune Exchange Connector\Logs\Connector.svclog</FileName> <FileQuota>30</FileQuota> </Listener> </Listeners> </Value>
    </TraceSourceLine>



### Próximas etapas
<a id="next-steps" class="xliff"></a>
Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).
>>>>>>> live
