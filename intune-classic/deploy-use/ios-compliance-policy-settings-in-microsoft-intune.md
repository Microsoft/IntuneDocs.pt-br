---
title: "Configuração da política de conformidade em dispositivos iOS"
description: "Este tópico descreve as regras e configurações que você pode definir em uma política de conformidade para dispositivos iOS."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d3248747740dafe858a581ed19a02ba87c4b761
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="15ab3-103">Configurações de política de conformidade para dispositivos iOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="15ab3-103">Compliance policy settings for iOS devices in Microsoft Intune</span></span>
<a id="compliance-policy-settings-for-ios-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="15ab3-104">As configurações de política descritas neste tópico se aplicam a dispositivos que executam o iOS 8.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="15ab3-104">The policy settings described in this topic apply to devices running iOS 8.0 and later.</span></span>

<span data-ttu-id="15ab3-105">Se você estiver procurando informações sobre outras plataformas, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="15ab3-105">If you are looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
- [<span data-ttu-id="15ab3-106">Configurações da política de conformidade para dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="15ab3-106">Compliance policy settings for Android devices</span></span>](android-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="15ab3-107">Configurações da política de conformidade para o Android for work</span><span class="sxs-lookup"><span data-stu-id="15ab3-107">Compliance policy settings for Android for work</span></span>](afw-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="15ab3-108">Configurações de política de conformidade para dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="15ab3-108">Compliance policy settings for Windows devices</span></span>](windows-compliance-policy-settings-in-microsoft-intune.md)

## <span data-ttu-id="15ab3-109">Configurações de segurança do sistema</span><span class="sxs-lookup"><span data-stu-id="15ab3-109">System security settings</span></span>
<a id="system-security-settings" class="xliff"></a>
### <span data-ttu-id="15ab3-110">Senha</span><span class="sxs-lookup"><span data-stu-id="15ab3-110">Password</span></span>
<a id="password" class="xliff"></a>
- <span data-ttu-id="15ab3-111">**Exigir senha para desbloquear dispositivos móveis**: defina esta opção como **Sim** para exigir que o usuário insira uma senha antes que possa acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15ab3-111">**Require a password to unlock mobile devices**: Set this to **Yes** to require the user to enter a password before they can access their device.</span></span> <span data-ttu-id="15ab3-112">Dispositivos iOS que usam uma senha são criptografados.</span><span class="sxs-lookup"><span data-stu-id="15ab3-112">iOS devices that use a password are encrypted.</span></span>

- <span data-ttu-id="15ab3-113">**Permitir senhas simples**: defina como **Sim** para permitir que o usuário crie uma senha simples, como **1234** ou **1111**.</span><span class="sxs-lookup"><span data-stu-id="15ab3-113">**Allow simple passwords**: Set this to **Yes** to let the user create a simple password like **1234** or **1111**.</span></span>

-  <span data-ttu-id="15ab3-114">**Comprimento mínimo da senha**: especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.</span><span class="sxs-lookup"><span data-stu-id="15ab3-114">**Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.</span></span>

- <span data-ttu-id="15ab3-115">**Tipo de senha necessária:** especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.</span><span class="sxs-lookup"><span data-stu-id="15ab3-115">**Required password type**: Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>

- <span data-ttu-id="15ab3-116">**Número mínimo de conjuntos de caracteres:** se você definir **Tipo de senha necessária** como **Alfanumérica**, use essa configuração para especificar o número mínimo de conjuntos de caracteres que a senha deve conter.</span><span class="sxs-lookup"><span data-stu-id="15ab3-116">**Minimum number of character sets**: If you set **Required password type** to **Alphanumeric**, use this setting to specify the minimum number of character sets that the password must have.</span></span> <span data-ttu-id="15ab3-117">Os quatro conjuntos de caracteres são:</span><span class="sxs-lookup"><span data-stu-id="15ab3-117">The four character sets are:</span></span>
  -   <span data-ttu-id="15ab3-118">Letras minúsculas</span><span class="sxs-lookup"><span data-stu-id="15ab3-118">Lowercase letters</span></span>
  -   <span data-ttu-id="15ab3-119">Letras maiúsculas</span><span class="sxs-lookup"><span data-stu-id="15ab3-119">Uppercase letters</span></span>
  -   <span data-ttu-id="15ab3-120">Símbolos</span><span class="sxs-lookup"><span data-stu-id="15ab3-120">Symbols</span></span>
  -   <span data-ttu-id="15ab3-121">Números</span><span class="sxs-lookup"><span data-stu-id="15ab3-121">Numbers</span></span>

  <span data-ttu-id="15ab3-122">Definir um número mais alto exige que o usuário crie uma senha mais complexa.</span><span class="sxs-lookup"><span data-stu-id="15ab3-122">Setting a higher number will require the user to create a password that is more complex.</span></span>

  <span data-ttu-id="15ab3-123">Para dispositivos iOS, essa configuração se refere ao número de caracteres especiais (por exemplo, **!**, **#**, **&amp;**) que devem ser incluídos na senha.</span><span class="sxs-lookup"><span data-stu-id="15ab3-123">For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.</span></span>

- <span data-ttu-id="15ab3-124">**Minutos de inatividade antes que a senha seja exigida**: especifique o tempo ocioso antes que o usuário precise digitar novamente sua senha.</span><span class="sxs-lookup"><span data-stu-id="15ab3-124">**Minutes of inactivity before password is required**:  Specify the idle time before the user must reenter their password.</span></span>

- <span data-ttu-id="15ab3-125">**Expiração da senha (dias)**: selecione o número de dias antes que a senha do usuário expire e seja preciso criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="15ab3-125">**Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="15ab3-126">**Lembrar histórico de senha:** use essa configuração em conjunto com **Evitar reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="15ab3-126">**Remember password history**: Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="15ab3-127">**Evitar a reutilização de senhas anteriores**: se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.</span><span class="sxs-lookup"><span data-stu-id="15ab3-127">**Prevent reuse of previous passwords**: If you selected **Remember password history**, specify the number of previously used passwords that cannot be reused.</span></span>

- <span data-ttu-id="15ab3-128">**Exigir uma senha quando o dispositivo volta do estado ocioso**: use essa configuração em conjunto com **Minutos de inatividade antes que a senha seja exigida**.</span><span class="sxs-lookup"><span data-stu-id="15ab3-128">**Require a password when the device returns from an idle state**: Use this setting together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="15ab3-129">O usuário é solicitado a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.</span><span class="sxs-lookup"><span data-stu-id="15ab3-129">The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <span data-ttu-id="15ab3-130">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="15ab3-130">Email profile</span></span>
<a id="email-profile" class="xliff"></a>
- <span data-ttu-id="15ab3-131">**A conta de email deve ser gerenciada pelo Intune** : quando essa opção é definida como **Sim**, o dispositivo deve usar o perfil de email implantado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15ab3-131">**Email account must be managed by Intune**: When this option is set to **Yes**, the device must use the email profile deployed to the device.</span></span> <span data-ttu-id="15ab3-132">O dispositivo é considerado incompatível nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="15ab3-132">The device is considered noncompliant in the following situations:</span></span>
  - <span data-ttu-id="15ab3-133">O perfil de email é implantado em um grupo de usuários diferente do grupo de usuários que é destino da política de conformidade.</span><span class="sxs-lookup"><span data-stu-id="15ab3-133">The email profile is deployed to a user group other than the user group that the compliance policy targets.</span></span>
  - <span data-ttu-id="15ab3-134">O usuário já configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15ab3-134">The user has already set up an email account on the device that matches the Intune email profile deployed to the device.</span></span> <span data-ttu-id="15ab3-135">Intune não pode substituir o perfil de usuário provisionado e, portanto, não é capaz de gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="15ab3-135">Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.</span></span> <span data-ttu-id="15ab3-136">Para garantir a conformidade, o usuário deve remover as configurações de email existentes.</span><span class="sxs-lookup"><span data-stu-id="15ab3-136">To ensure compliance, the user must remove the existing email settings.</span></span> <span data-ttu-id="15ab3-137">Depois, o Intune pode instalar o perfil de email gerenciado.</span><span class="sxs-lookup"><span data-stu-id="15ab3-137">Then, Intune can install the managed email profile.</span></span>

- <span data-ttu-id="15ab3-138">**Selecione o perfil de email que deve ser gerenciado pelo Intune**: se a configuração **A conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para especificar o perfil de email do Intune.</span><span class="sxs-lookup"><span data-stu-id="15ab3-138">**Select the email profile that must be managed by Intune**: If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile.</span></span> <span data-ttu-id="15ab3-139">O perfil de email deve estar presente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15ab3-139">The email profile must be present on the device.</span></span>

     <span data-ttu-id="15ab3-140">Para obter detalhes sobre os perfis de email, consulte [Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="15ab3-140">For details about email profiles, see [Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).</span></span>

## <span data-ttu-id="15ab3-141">Configurações de integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="15ab3-141">Device health settings</span></span>
<a id="device-health-settings" class="xliff"></a>

- <span data-ttu-id="15ab3-142">**O dispositivo não pode estar com jailbreak ou com raiz**: se você habilitar essa configuração, os dispositivos com jailbreak não serão compatíveis.</span><span class="sxs-lookup"><span data-stu-id="15ab3-142">**Device must not be jailbroken or rooted**: If you enable this setting, jailbroken devices will not be compliant.</span></span>

##  <span data-ttu-id="15ab3-143">Propriedades do dispositivo</span><span class="sxs-lookup"><span data-stu-id="15ab3-143">Device properties</span></span>
<a id="device-properties" class="xliff"></a>
- <span data-ttu-id="15ab3-144">**SO mínimo exigido**: quando um dispositivo não atender ao requisito mínimo de versão do SO, ele será relatado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="15ab3-144">**Minimum OS required**: When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span>
<span data-ttu-id="15ab3-145">É exibido um link com informações sobre como atualizar.</span><span class="sxs-lookup"><span data-stu-id="15ab3-145">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="15ab3-146">O usuário pode optar por atualizar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="15ab3-146">The user can choose to upgrade their device.</span></span> <span data-ttu-id="15ab3-147">Depois disso, ele pode acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="15ab3-147">After that, they can access company resources.</span></span>

- <span data-ttu-id="15ab3-148">**Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e o usuário será solicitado a entrar em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="15ab3-148">**Maximum OS version allowed**: When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin.</span></span> <span data-ttu-id="15ab3-149">Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="15ab3-149">Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>
