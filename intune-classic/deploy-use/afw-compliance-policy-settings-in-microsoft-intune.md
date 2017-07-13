---
title: "Configurações de conformidade do Android for Work"
description: "Este tópico descreve as configurações de política de conformidade para dispositivos Android compatíveis com o Android for Work."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 79be4993c9b23294d1f49743f863588f9d0cb9b5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="23bb9-103">Configurações de política de conformidade para dispositivos Android for Work no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="23bb9-103">Compliance policy settings for Android for Work devices in Microsoft Intune</span></span>
<a id="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="23bb9-104">As configurações de política descritas neste tópico se aplicam a dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="23bb9-104">The policy settings described in this topic apply to Android for Work devices.</span></span>

<span data-ttu-id="23bb9-105">Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="23bb9-105">If you are looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
- [<span data-ttu-id="23bb9-106">Configurações de política de conformidade para Android</span><span class="sxs-lookup"><span data-stu-id="23bb9-106">Compliance policy setting for Android</span></span>](android-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="23bb9-107">Configurações de política de conformidade para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="23bb9-107">Compliance policy settings for iOS devices</span></span>](ios-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="23bb9-108">Configurações de política de conformidade para dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="23bb9-108">Compliance policy settings for Windows devices</span></span>](windows-compliance-policy-settings-in-microsoft-intune.md)

## <span data-ttu-id="23bb9-109">Configurações de segurança do sistema</span><span class="sxs-lookup"><span data-stu-id="23bb9-109">System security settings</span></span>
<a id="system-security-settings" class="xliff"></a>
### <span data-ttu-id="23bb9-110">Senha</span><span class="sxs-lookup"><span data-stu-id="23bb9-110">Password</span></span>
<a id="password" class="xliff"></a>
- <span data-ttu-id="23bb9-111">**Exigir uma senha para desbloquear dispositivos móveis:** defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que eles possam acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23bb9-111">**Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.</span></span>

-  <span data-ttu-id="23bb9-112">**Comprimento mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve conter.</span><span class="sxs-lookup"><span data-stu-id="23bb9-112">**Minimum password length:** Specify the minimum number of digits or characters that the user’s password must contain.</span></span>

- <span data-ttu-id="23bb9-113">**Qualidade da senha:** essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="23bb9-113">**Password quality:** This setting detects if the password requirements you specify is configured on the device.</span></span> <span data-ttu-id="23bb9-114">Habilite essa configuração para exigir que os usuários configurem certos requisitos de senha para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="23bb9-114">Enable this setting to require that users configure certain password requirements for Android devices.</span></span> <span data-ttu-id="23bb9-115">Escolha:</span><span class="sxs-lookup"><span data-stu-id="23bb9-115">Choose from:</span></span>
  -   <span data-ttu-id="23bb9-116">**Biométrico de segurança baixa**</span><span class="sxs-lookup"><span data-stu-id="23bb9-116">**Low security biometric**</span></span>
  - <span data-ttu-id="23bb9-117">**Necessária**</span><span class="sxs-lookup"><span data-stu-id="23bb9-117">**Required**</span></span>
  -   <span data-ttu-id="23bb9-118">**Pelo menos, numérico**</span><span class="sxs-lookup"><span data-stu-id="23bb9-118">**At least numeric**</span></span>
  -   <span data-ttu-id="23bb9-119">**Pelo menos, alfabético**</span><span class="sxs-lookup"><span data-stu-id="23bb9-119">**At least alphabetic**</span></span>
  -   <span data-ttu-id="23bb9-120">**Pelo menos, alfanumérico**</span><span class="sxs-lookup"><span data-stu-id="23bb9-120">**At least alphanumeric**</span></span>
  -   <span data-ttu-id="23bb9-121">**Alfanumérico com símbolos**</span><span class="sxs-lookup"><span data-stu-id="23bb9-121">**Alphanumeric with symbols**</span></span>

- <span data-ttu-id="23bb9-122">**Minutos de inatividade antes da senha ser necessária:** especifica o tempo ocioso antes que o usuário precise digitar novamente a senha.</span><span class="sxs-lookup"><span data-stu-id="23bb9-122">**Minutes of inactivity before password is required:**  Specifies the idle time before the user must re-enter their password.</span></span>

- <span data-ttu-id="23bb9-123">**Expiração da senha (dias):** selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="23bb9-123">**Password expiration (days):** Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="23bb9-124">**Lembrar o histórico da senha:** use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="23bb9-124">**Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="23bb9-125">**Evitar a reutilização de senhas anteriores:** se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.</span><span class="sxs-lookup"><span data-stu-id="23bb9-125">**Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.</span></span>

- <span data-ttu-id="23bb9-126">**Exigir uma senha quando o dispositivo retorna do estado ocioso:** essa configuração deve ser usada junto com a configuração **Minutos de inatividade antes da senha ser necessária**.</span><span class="sxs-lookup"><span data-stu-id="23bb9-126">**Require a password when the device returns from an idle state:** This setting should be used together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="23bb9-127">Os usuários finais serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.</span><span class="sxs-lookup"><span data-stu-id="23bb9-127">The end-users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <span data-ttu-id="23bb9-128">Criptografia</span><span class="sxs-lookup"><span data-stu-id="23bb9-128">Encryption</span></span>
<a id="encryption" class="xliff"></a>
- <span data-ttu-id="23bb9-129">**Exigir criptografia no dispositivo móvel:** não é necessário definir essa configuração, pois os dispositivos Android for Work impõem a criptografia.</span><span class="sxs-lookup"><span data-stu-id="23bb9-129">**Require encryption on mobile device:** You don't have to configure this setting since Android for Work devices enforce encryption.</span></span>

## <span data-ttu-id="23bb9-130">Configurações de segurança e integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="23bb9-130">Device health and security settings</span></span>
<a id="device-health-and-security-settings" class="xliff"></a>

- <span data-ttu-id="23bb9-131">**O dispositivo não pode estar com jailbreak ou com raiz:** se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.</span><span class="sxs-lookup"><span data-stu-id="23bb9-131">**Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices will be evaluated as noncompliant.</span></span>
- <span data-ttu-id="23bb9-132">**Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas:** não é necessário definir essa configuração, pois dispositivos Android for Work sempre restringem a instalação de fontes desconhecidas.</span><span class="sxs-lookup"><span data-stu-id="23bb9-132">**Require that devices prevent installation of apps from unknown sources:** You do not have to configure this setting as Android for Work devices always restrict installation from unknown sources.</span></span> <span data-ttu-id="23bb9-133">.</span><span class="sxs-lookup"><span data-stu-id="23bb9-133">.</span></span>  

- <span data-ttu-id="23bb9-134">**Exigir que a depuração de USB esteja desabilitada**: não é necessário definir essas configurações, pois a depuração USB já está desabilitada em dispositivos Android for Work.</span><span class="sxs-lookup"><span data-stu-id="23bb9-134">**Require that USB debugging is  disabled**: You do not have to configure this settings as USB debugging is already disabled on Android for Work devices.</span></span>

- <span data-ttu-id="23bb9-135">**Nível mínimo do patch de segurança do Android**: use essa configuração para especificar o nível mínimo do patch do Android.</span><span class="sxs-lookup"><span data-stu-id="23bb9-135">**Minimum Android security patch level**: Use this setting to specify the minimum Android patch level.</span></span>  <span data-ttu-id="23bb9-136">Dispositivos com níveis de patch mais antigos são incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="23bb9-136">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="23bb9-137">A data deve ser especificada no formato: AAAA-MM-DD.</span><span class="sxs-lookup"><span data-stu-id="23bb9-137">The date must be specified the format: YYYY-MM-DD.</span></span>
- <span data-ttu-id="23bb9-138">**Exigir que a proteção contra ameaças ao dispositivo esteja habilitada**: use essa configuração para executar a avaliação de risco da solução de proteção contra ameaças ao dispositivo como uma condição para a conformidade.</span><span class="sxs-lookup"><span data-stu-id="23bb9-138">**Require device threat protection to be enabled**: Use this setting to take the risk assessment from the device threat protection solution as a condition for compliance.</span></span> <span data-ttu-id="23bb9-139">Selecione o nível máximo de ameaça permitido, que é um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="23bb9-139">Select the maximum allowed threat level, which is one of the following:</span></span>

  - <span data-ttu-id="23bb9-140">**Nenhum (Seguro)**: este é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="23bb9-140">**None (secured)** This is the most secure.</span></span> <span data-ttu-id="23bb9-141">Isso significa que o dispositivo não pode ter nenhuma ameaça.</span><span class="sxs-lookup"><span data-stu-id="23bb9-141">This means that the device cannot have any threats.</span></span> <span data-ttu-id="23bb9-142">Se for detectado que o dispositivo tem qualquer nível de ameaça, ele será avaliado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="23bb9-142">If the device is detected as having any level of threats, it will be evaluated as non-compliant.</span></span>
  - <span data-ttu-id="23bb9-143">**Baixo**: o dispositivo será avaliado como compatível se apenas ameaças de nível baixo estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="23bb9-143">**Low:** Device is evaluated as compliant if only low level threats are present.</span></span> <span data-ttu-id="23bb9-144">Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.</span><span class="sxs-lookup"><span data-stu-id="23bb9-144">Anything higher puts the device in a non-compliant status.</span></span>
  - <span data-ttu-id="23bb9-145">**Médio**: o dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio.</span><span class="sxs-lookup"><span data-stu-id="23bb9-145">**Medium:** Device is evaluated as compliant if the threats that are present on the device are low or medium level.</span></span> <span data-ttu-id="23bb9-146">Se for detectado que o dispositivo tem ameaças de nível alto, será determinado que ele é não compatível.</span><span class="sxs-lookup"><span data-stu-id="23bb9-146">If the device is detected to have high level threats, it is determined as non-compliant.</span></span>
  - <span data-ttu-id="23bb9-147">**Alto**: esta é a opção menos segura.</span><span class="sxs-lookup"><span data-stu-id="23bb9-147">**High:** This is the least secure.</span></span> <span data-ttu-id="23bb9-148">Basicamente, ela permite todos os níveis de ameaça e talvez só seja útil se você usa esta solução apenas para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="23bb9-148">Essentially, this allows all threat levels, and perhaps only useful if you using this solution only for reporting purposes.</span></span>

  <span data-ttu-id="23bb9-149">Para obter mais detalhes, consulte [Create device compliance policy](create-lookout-device-compliance-policy.md) (Criar política de conformidade do dispositivo).</span><span class="sxs-lookup"><span data-stu-id="23bb9-149">For more details, see [Create device compliance policy](create-lookout-device-compliance-policy.md).</span></span>

## <span data-ttu-id="23bb9-150">Configurações de propriedade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="23bb9-150">Device property settings</span></span>
<a id="device-property-settings" class="xliff"></a>
- <span data-ttu-id="23bb9-151">**Sistema operacional mínimo exigido:** se um dispositivo não atender ao requisito mínimo de versão do SO (sistema operacional), ele será relatado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="23bb9-151">**Minimum OS required:** When a device does not meet the minimum operating system (OS) version requirement, it is reported as noncompliant.</span></span>
  <span data-ttu-id="23bb9-152">É exibido um link com informações sobre como atualizar.</span><span class="sxs-lookup"><span data-stu-id="23bb9-152">A link with information on how to upgrade is displayed.</span></span> <span data-ttu-id="23bb9-153">O usuário final pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="23bb9-153">The end-user can choose to upgrade their device after which they can access company resources.</span></span>

- <span data-ttu-id="23bb9-154">**Versão máxima permitida do sistema operacional:** quando um dispositivo estiver usando uma versão do SO (sistema operacional) posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário deverá entrar em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="23bb9-154">**Maximum OS version allowed:** When a device is using an operating system (OS) version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin.</span></span> <span data-ttu-id="23bb9-155">Até que haja uma alteração na regra para permitir a versão do sistema operacional em questão, o dispositivo não poderá ser usado para acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="23bb9-155">Until there is a change in the rule to allow the operating system version, this device cannot be used to access company resources.</span></span>
