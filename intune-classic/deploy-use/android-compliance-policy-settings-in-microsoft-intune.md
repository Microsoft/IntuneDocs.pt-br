---
title: "Configurações da política de conformidade para o Android"
description: "Este tópico descreve as configurações de política de conformidade de dispositivo Android."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cc698998491fa56769376c013fb76ac75b5627bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="709f6-103">Configurações de política de conformidade para dispositivos Android no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="709f6-103">Compliance policy settings for Android devices in Microsoft Intune</span></span>
<a id="compliance-policy-settings-for-android-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="709f6-104">As configurações de política descritas neste tópico se aplicam a dispositivos que executam o Android 4.0 e posterior ou o Samsung KNOX 4.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="709f6-104">The policy settings described in this topic apply to devices that are running Android 4.0 and later or Samsung KNOX 4.0 and later.</span></span>

<span data-ttu-id="709f6-105">Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="709f6-105">If you're looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
- [<span data-ttu-id="709f6-106">Configurações da política de conformidade para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="709f6-106">Compliance policy settings for iOS devices</span></span>](ios-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="709f6-107">Configurações de política de conformidade para dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="709f6-107">Compliance policy settings for Windows devices</span></span>](windows-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="709f6-108">Configurações da política de conformidade para dispositivos Android para Trabalho</span><span class="sxs-lookup"><span data-stu-id="709f6-108">Compliance policy settings for Android for Work devices</span></span>](afw-compliance-policy-settings-in-microsoft-intune.md)

## <span data-ttu-id="709f6-109">Configurações de segurança do sistema</span><span class="sxs-lookup"><span data-stu-id="709f6-109">System security settings</span></span>
<a id="system-security-settings" class="xliff"></a>
### <span data-ttu-id="709f6-110">Senha</span><span class="sxs-lookup"><span data-stu-id="709f6-110">Password</span></span>
<a id="password" class="xliff"></a>
- <span data-ttu-id="709f6-111">**Exigir uma senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que os usuários insiram uma senha antes que possam acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="709f6-111">**Require a password to unlock mobile devices**: Set this to **Yes** to require users to enter a password before they can access their device.</span></span>

-  <span data-ttu-id="709f6-112">**Comprimento mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.</span><span class="sxs-lookup"><span data-stu-id="709f6-112">**Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.</span></span>

- <span data-ttu-id="709f6-113">**Qualidade da senha**: essa configuração detecta se os requisitos de senha especificados por você estão configurados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="709f6-113">**Password quality**: This setting detects if the password requirements that you specify are set up on the device.</span></span> <span data-ttu-id="709f6-114">Habilite essa configuração para exigir que os usuários atendam certos requisitos de senha para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="709f6-114">Enable this setting to require that users meet certain password requirements for Android devices.</span></span> <span data-ttu-id="709f6-115">Escolha:</span><span class="sxs-lookup"><span data-stu-id="709f6-115">Choose from:</span></span>

  -   <span data-ttu-id="709f6-116">**Biométrico de segurança baixa**</span><span class="sxs-lookup"><span data-stu-id="709f6-116">**Low security biometric**</span></span>
  -   <span data-ttu-id="709f6-117">**Necessária**</span><span class="sxs-lookup"><span data-stu-id="709f6-117">**Required**</span></span>
  -   <span data-ttu-id="709f6-118">**Pelo menos, numérico**</span><span class="sxs-lookup"><span data-stu-id="709f6-118">**At least numeric**</span></span>
  -   <span data-ttu-id="709f6-119">**Pelo menos, alfabético**</span><span class="sxs-lookup"><span data-stu-id="709f6-119">**At least alphabetic**</span></span>
  -   <span data-ttu-id="709f6-120">**Pelo menos, alfanumérico**</span><span class="sxs-lookup"><span data-stu-id="709f6-120">**At least alphanumeric**</span></span>
  -   <span data-ttu-id="709f6-121">**Alfanumérico com símbolos**</span><span class="sxs-lookup"><span data-stu-id="709f6-121">**Alphanumeric with symbols**</span></span>

- <span data-ttu-id="709f6-122">**Minutos de inatividade antes que a senha seja exigida:** especifica o tempo ocioso antes que o usuário precise digitar novamente sua senha.</span><span class="sxs-lookup"><span data-stu-id="709f6-122">**Minutes of inactivity before password is required:**  Specify the idle time before the user must re-enter their password.</span></span>

- <span data-ttu-id="709f6-123">**Expiração da senha (dias)**: selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="709f6-123">**Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="709f6-124">**Lembrar o histórico da senha**: use essa configuração em conjunto com **Evitar a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="709f6-124">**Remember password history**: Use this setting together with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="709f6-125">**Evitar a reutilização de senhas anteriores:** especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas (se **Lembrar o histórico de senha** estiver selecionado).</span><span class="sxs-lookup"><span data-stu-id="709f6-125">**Prevent reuse of previous passwords:** Specify the number of previously used passwords that cannot be re-used (if **Remember password history** is selected).</span></span>

- <span data-ttu-id="709f6-126">**Exigir uma senha quando o dispositivo retorna do estado ocioso:** use em conjunto com a configuração **Minutos de inatividade antes da senha ser necessária**.</span><span class="sxs-lookup"><span data-stu-id="709f6-126">**Require a password when the device returns from an idle state:** Use together with the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="709f6-127">Os usuários serão solicitados a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.</span><span class="sxs-lookup"><span data-stu-id="709f6-127">Users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <span data-ttu-id="709f6-128">Criptografia</span><span class="sxs-lookup"><span data-stu-id="709f6-128">Encryption</span></span>
<a id="encryption" class="xliff"></a>
- <span data-ttu-id="709f6-129">**Exigir criptografia no dispositivo móvel**: defina esta opção como **Sim** para exigir que os dispositivos sejam criptografados para poderem conectarem-se aos recursos.</span><span class="sxs-lookup"><span data-stu-id="709f6-129">**Require encryption on mobile device:** Set this to **Yes** to require devices to be encrypted to be able connect to resources.</span></span> <span data-ttu-id="709f6-130">Os dispositivos serão criptografados quando você definir a configuração **Exigir uma senha para desbloquear dispositivos móveis**.</span><span class="sxs-lookup"><span data-stu-id="709f6-130">Devices are encrypted when you configure the setting **Require a password to unlock mobile devices**.</span></span>

## <span data-ttu-id="709f6-131">Configurações de segurança e integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="709f6-131">Device health and security settings</span></span>
<a id="device-health-and-security-settings" class="xliff"></a>

- <span data-ttu-id="709f6-132">**O dispositivo não pode estar com jailbreak ou com raiz**: se você habilitar essa configuração, os dispositivos com jailbreak serão avaliados como não compatíveis.</span><span class="sxs-lookup"><span data-stu-id="709f6-132">**Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices are evaluated as noncompliant.</span></span>
- <span data-ttu-id="709f6-133">**Exigir que dispositivos impeçam a instalação de aplicativos de fontes desconhecidas (Android 4.0 ou posterior)**: para bloquear dispositivos que têm a opção **Segurança > Fontes desconhecidas** habilitado no dispositivo, habilite essa configuração e defina-a como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="709f6-133">**Require that devices prevent installation of apps from unknown sources (Android 4.0 or later)**: To block devices that have **Security > Unknown sources** enabled on the device, enable this setting and set it to **Yes**.</span></span>  

>[!IMPORTANT]
><span data-ttu-id="709f6-134">Aplicativos de sideload requerem que a configuração **Fontes desconhecidas** esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="709f6-134">Side-loading applications requires that the  **Unknown sources** setting is enabled.</span></span> <span data-ttu-id="709f6-135">Aplique esta política de conformidade somente se você não estiver fazendo o sideload de aplicativos Android nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="709f6-135">Enforce this compliance policy only if you are not side-loading Android apps on devices.</span></span>

- <span data-ttu-id="709f6-136">**Exigir que a depuração de USB esteja desabilitada (Android 4.2 ou posterior)**: especifique se a opção de detecção de depuração de USB no dispositivo está habilitada.</span><span class="sxs-lookup"><span data-stu-id="709f6-136">**Require that USB debugging is  disabled (Android 4.2 or later)**: Specify whether to detect if the USB debugging option on the device is enabled.</span></span>
- <span data-ttu-id="709f6-137">**Exigir que os dispositivos tenham habilitado “Examinar dispositivo contra ameaças à segurança” (Android 4.4 4.2)**: especifique se o recurso **Verificar aplicativos** está habilitado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="709f6-137">**Require devices have enabled Scan device for security threats (Android 4.2-4.4)**: Specify that the **Verify apps** feature is enabled on the device.</span></span>
- <span data-ttu-id="709f6-138">**Nível mínimo do patch de segurança do Android (Android 6.0 ou posterior)**: especifique o nível mínimo de patch de Android.</span><span class="sxs-lookup"><span data-stu-id="709f6-138">**Minimum Android security patch level (Android 6.0 or later)**: Specify the minimum Android patch level.</span></span>  <span data-ttu-id="709f6-139">Dispositivos com níveis de patch mais antigos são incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="709f6-139">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="709f6-140">A data deve ser especificada neste formato: AAAA-MM-DD.</span><span class="sxs-lookup"><span data-stu-id="709f6-140">The date must be specified in this format: YYYY-MM-DD.</span></span>
- <span data-ttu-id="709f6-141">**Requer proteção contra ameaças de dispositivo a ser habilitado**: use esta configuração para fazer a avaliação de risco da solução Consulta MTP como uma condição para conformidade.</span><span class="sxs-lookup"><span data-stu-id="709f6-141">**Require device threat protection to be enabled**: Use this setting to take the risk assessment from the Lookout MTP solution as a condition for compliance.</span></span> <span data-ttu-id="709f6-142">Selecione o nível máximo de ameaça permitido, que é um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="709f6-142">Select the maximum allowed threat level, which is one of the following:</span></span>

  - <span data-ttu-id="709f6-143">**Nenhum (Seguro)**: este é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="709f6-143">**None (secured)** This is the most secure.</span></span> <span data-ttu-id="709f6-144">Isso significa que o dispositivo não pode ter nenhuma ameaça.</span><span class="sxs-lookup"><span data-stu-id="709f6-144">This means that the device cannot have any threats.</span></span> <span data-ttu-id="709f6-145">Se for detectado que o dispositivo tem qualquer ameaça, ele será avaliado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="709f6-145">If the device is detected as having any threats, it is evaluated as noncompliant.</span></span>
  - <span data-ttu-id="709f6-146">**Baixo**: o dispositivo será avaliado como compatível se apenas ameaças de nível baixo estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="709f6-146">**Low:** The device is evaluated as compliant if only low-level threats are present.</span></span> <span data-ttu-id="709f6-147">Qualquer coisa acima disso coloca o dispositivo no estado de não compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="709f6-147">Anything higher puts the device in noncompliant status.</span></span>
  - <span data-ttu-id="709f6-148">**Médio**: o dispositivo será avaliado como compatível se as ameaças presentes nele forem de nível baixo ou médio.</span><span class="sxs-lookup"><span data-stu-id="709f6-148">**Medium:** The device is evaluated as compliant if the threats that are present on the device are low- or medium-level.</span></span> <span data-ttu-id="709f6-149">Se forem detectadas ameaças no dispositivo, será determinado que ele é não compatível.</span><span class="sxs-lookup"><span data-stu-id="709f6-149">If high-level threats are detected on the device, it is determined to be noncompliant.</span></span>
  - <span data-ttu-id="709f6-150">**Alto**: esta é a opção menos segura.</span><span class="sxs-lookup"><span data-stu-id="709f6-150">**High:** This is the least secure.</span></span> <span data-ttu-id="709f6-151">Basicamente, ela permite todos os níveis de ameaça, o que talvez só seja útil se você usar esta solução apenas para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="709f6-151">Essentially this allows all threat levels, which is perhaps only useful if you using this solution only for reporting purposes.</span></span>

  <span data-ttu-id="709f6-152">Para obter mais detalhes, consulte [Criar política de conformidade de dispositivo do Lookout](create-lookout-device-compliance-policy.md).</span><span class="sxs-lookup"><span data-stu-id="709f6-152">For more details, see [Create Lookout device compliance policy](create-lookout-device-compliance-policy.md).</span></span>

## <span data-ttu-id="709f6-153">Configurações de propriedade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="709f6-153">Device property settings</span></span>
<a id="device-property-settings" class="xliff"></a>

- <span data-ttu-id="709f6-154">**Sistema operacional mínimo exigido**: quando um dispositivo não atender ao requisito mínimo da versão do sistema operacional, ele será relatado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="709f6-154">**Minimum OS required:** When  a device doesn't meet the minimum OS version requirement, it is reported as noncompliant.</span></span>
  <span data-ttu-id="709f6-155">É exibido um link com informações sobre como atualizar.</span><span class="sxs-lookup"><span data-stu-id="709f6-155">A link with information about how to upgrade is displayed.</span></span> <span data-ttu-id="709f6-156">O usuário pode optar por atualizar seus dispositivos após o que será possível acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="709f6-156">The user can choose to upgrade their device, after which they can access company resources.</span></span>

- <span data-ttu-id="709f6-157">**Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="709f6-157">**Maximum OS version allowed:** When a device is using an OS version that's later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin.</span></span> <span data-ttu-id="709f6-158">Até que a regra seja alterada para permitir a versão do SO, este dispositivo não poderá ser usado para acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="709f6-158">Until the rule changes to allow the OS version, this device cannot be used to access company resources.</span></span>
