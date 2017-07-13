---
title: "<span data-ttu-id=\"60576-101\">Como criar uma política de conformidade para o iOS</span><span class=\"sxs-lookup\"><span data-stu-id=\"60576-101\">How to create a compliance policy for iOS</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"60576-102\">Saiba como criar uma política de conformidade para dispositivos iOS.</span><span class=\"sxs-lookup\"><span data-stu-id=\"60576-102\">Learn how to create a compliance policy for iOS devices.\"</span></span>"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9337586ad5daa909f38aba2b25fc159b44f55e65
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="60576-103">Como criar uma política de conformidade do dispositivo para dispositivos iOS no Intune</span><span class="sxs-lookup"><span data-stu-id="60576-103">How to create a device compliance policy for iOS devices in Intune</span></span>
<a id="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="60576-104">As políticas de conformidade são criadas para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="60576-104">Compliance policies are created for each platform.</span></span>  <span data-ttu-id="60576-105">Você pode criar uma política de conformidade no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="60576-105">You can create a compliance policy in the Azure portal.</span></span> <span data-ttu-id="60576-106">Para saber mais sobre o que é a política de conformidade, consulte o tópico [O que é conformidade do dispositivo](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="60576-106">To learn more about what compliance policy is see [what is a device compliance](device-compliance.md) topic.</span></span> <span data-ttu-id="60576-107">Para saber mais sobre os pré-requisitos que você precisa cumprir antes de criar uma política de conformidade, consulte o tópico [Introdução à conformidade do dispositivo](device-compliance-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="60576-107">To learn about the prerequisites that you need to address before creating a compliance policy see [Get started with device compliance](device-compliance-get-started.md) topic.</span></span>

<span data-ttu-id="60576-108">A tabela abaixo descreve como as configurações não compatíveis são gerenciadas quando uma política de conformidade é usada com uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="60576-108">The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

-------------------------------


| <span data-ttu-id="60576-109">**Configuração de política**</span><span class="sxs-lookup"><span data-stu-id="60576-109">**Policy setting**</span></span> | <span data-ttu-id="60576-110">**iOS 8.0 e posterior**</span><span class="sxs-lookup"><span data-stu-id="60576-110">**iOS 8.0 and later**</span></span> |
| --- | --- |
| <span data-ttu-id="60576-111">**Configuração de senha ou PIN**</span><span class="sxs-lookup"><span data-stu-id="60576-111">**PIN or password configuration**</span></span> | <span data-ttu-id="60576-112">Corrigida</span><span class="sxs-lookup"><span data-stu-id="60576-112">Remediated</span></span> |   
| <span data-ttu-id="60576-113">**Criptografia de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="60576-113">**Device encryption**</span></span> | <span data-ttu-id="60576-114">Corrigida (pela definição do PIN)</span><span class="sxs-lookup"><span data-stu-id="60576-114">Remediated (by setting PIN)</span></span> |
| <span data-ttu-id="60576-115">**Dispositivo desbloqueado ou com raiz**</span><span class="sxs-lookup"><span data-stu-id="60576-115">**Jailbroken or rooted device**</span></span> | <span data-ttu-id="60576-116">Em Quarentena (não é uma configuração)</span><span class="sxs-lookup"><span data-stu-id="60576-116">Quarantined (not a setting)</span></span>
| <span data-ttu-id="60576-117">**Perfil de email**</span><span class="sxs-lookup"><span data-stu-id="60576-117">**Email profile**</span></span> | <span data-ttu-id="60576-118">Em Quarentena</span><span class="sxs-lookup"><span data-stu-id="60576-118">Quarantined</span></span> |
|<span data-ttu-id="60576-119">**Versão mínima do SO**</span><span class="sxs-lookup"><span data-stu-id="60576-119">**Minimum OS version**</span></span> | <span data-ttu-id="60576-120">Em Quarentena</span><span class="sxs-lookup"><span data-stu-id="60576-120">Quarantined</span></span> |
| <span data-ttu-id="60576-121">**Versão máxima do SO**</span><span class="sxs-lookup"><span data-stu-id="60576-121">**Maximum OS version**</span></span> | <span data-ttu-id="60576-122">Em Quarentena</span><span class="sxs-lookup"><span data-stu-id="60576-122">Quarantined</span></span> |  
| <span data-ttu-id="60576-123">**Atestado de integridade do Windows**</span><span class="sxs-lookup"><span data-stu-id="60576-123">**Windows health attestation**</span></span> | <span data-ttu-id="60576-124">Não aplicável</span><span class="sxs-lookup"><span data-stu-id="60576-124">Not applicable</span></span> |  
----------------------------


<span data-ttu-id="60576-125">**Remediado** = o sistema operacional do dispositivo impõe a conformidade.</span><span class="sxs-lookup"><span data-stu-id="60576-125">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="60576-126">(Por exemplo, o usuário é forçado a definir um PIN.)</span><span class="sxs-lookup"><span data-stu-id="60576-126">(For example, the user is forced to set a PIN.)</span></span>

<span data-ttu-id="60576-127">**Em quarentena** = o sistema operacional do dispositivo não impõe a conformidade.</span><span class="sxs-lookup"><span data-stu-id="60576-127">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="60576-128">(Por exemplo, dispositivos Android não forçam o usuário a criptografar o dispositivo.) Quando os dispositivos não são compatíveis, ocorrem as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="60576-128">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:</span></span>

- <span data-ttu-id="60576-129">O dispositivo será bloqueado se uma política de acesso condicional se aplicar ao usuário.</span><span class="sxs-lookup"><span data-stu-id="60576-129">The device is blocked if a conditional access policy applies to the user.</span></span>
- <span data-ttu-id="60576-130">O portal da empresa notificará o usuário sobre qualquer problema de conformidade.</span><span class="sxs-lookup"><span data-stu-id="60576-130">The company portal notifies the user about any compliance problems.</span></span>

## <span data-ttu-id="60576-131">Criar uma política de conformidade no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="60576-131">Create a compliance policy in the Azure portal</span></span>
<a id="create-a-compliance-policy-in-the-azure-portal" class="xliff"></a>

1. <span data-ttu-id="60576-132">Na folha **Intune**, escolha **Definir conformidade do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="60576-132">From the **Intune** blade, choose **Set Device compliance**.</span></span> <span data-ttu-id="60576-133">Em **Gerenciar**, escolha **Todas as políticas de conformidade de dispositivo** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="60576-133">Under **Manage**, choose **All device compliance policies** and choose **Create**.</span></span>
2. <span data-ttu-id="60576-134">Digite um nome, descrição e escolha a plataforma à qual você deseja que essa política se aplique.</span><span class="sxs-lookup"><span data-stu-id="60576-134">Type a name, description and choose the platform that you want this policy to apply to.</span></span>
3. <span data-ttu-id="60576-135">Escolha **Requisitos de conformidade** para especificar as configurações de **Segurança**, **Integridade do dispositivo** e **Propriedade do dispositivo** aqui. Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="60576-135">Choose **Compliance requirements** to specify the **Security**, **Device health**, and **Device property** settings here, When you are done, choose **Ok**.</span></span>

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <span data-ttu-id="60576-136">Atribuir grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="60576-136">Assign user groups</span></span>
<a id="assign-user-groups" class="xliff"></a>

<span data-ttu-id="60576-137">Para atribuir uma política de conformidade aos usuários, escolha uma política que você configurou.</span><span class="sxs-lookup"><span data-stu-id="60576-137">To assign a compliance policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="60576-138">As políticas existentes podem ser encontradas na folha **Conformidade – Políticas**.</span><span class="sxs-lookup"><span data-stu-id="60576-138">Existing policies can be found in the **Compliance –policies** blade.</span></span>

1. <span data-ttu-id="60576-139">Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="60576-139">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="60576-140">Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.</span><span class="sxs-lookup"><span data-stu-id="60576-140">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>
2. <span data-ttu-id="60576-141">Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="60576-141">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>  <span data-ttu-id="60576-142">Escolher **Selecionar** implanta a política para os usuários.</span><span class="sxs-lookup"><span data-stu-id="60576-142">Choosing **Select**  deploys the policy to users.</span></span>

<span data-ttu-id="60576-143">Você aplicou a política para os usuários.</span><span class="sxs-lookup"><span data-stu-id="60576-143">You have applied the policy to users.</span></span>  <span data-ttu-id="60576-144">A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.</span><span class="sxs-lookup"><span data-stu-id="60576-144">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>

<!---## Compliance policy settings--->

## <span data-ttu-id="60576-145">Configurações de segurança do sistema</span><span class="sxs-lookup"><span data-stu-id="60576-145">System security settings</span></span>
<a id="system-security-settings" class="xliff"></a>

### <span data-ttu-id="60576-146">Senha</span><span class="sxs-lookup"><span data-stu-id="60576-146">Password</span></span>
<a id="password" class="xliff"></a>

- <span data-ttu-id="60576-147">**Exigir uma senha para desbloquear dispositivos móveis**: defina essa opção como **Sim** para exigir que o usuário insira uma senha antes de acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60576-147">**Require a password to unlock mobile devices** : Set this to **Yes** to require the user to enter a password before they can access their device.</span></span> <span data-ttu-id="60576-148">Dispositivos iOS que usam uma senha são criptografados.</span><span class="sxs-lookup"><span data-stu-id="60576-148">iOS devices that use a password are encrypted.</span></span>
- <span data-ttu-id="60576-149">**Permitir senhas simples**: defina como **Sim** para permitir que o usuário crie uma senha simples, como **1234** ou **1111**.</span><span class="sxs-lookup"><span data-stu-id="60576-149">**Allow simple passwords** : Set this to **Yes** to let the user create a simple password like **1234** or **1111**.</span></span>
- <span data-ttu-id="60576-150">**Tamanho mínimo da senha:** especifique o número mínimo de dígitos ou caracteres que a senha do usuário deve ter.</span><span class="sxs-lookup"><span data-stu-id="60576-150">**Minimum password length** : Specify the minimum number of digits or characters that the password must have.</span></span>
- <span data-ttu-id="60576-151">**Tipo de senha necessária**: especifique se o usuário deve criar uma senha **Alfanumérica** ou **Numérica**.</span><span class="sxs-lookup"><span data-stu-id="60576-151">**Required password type** : Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>
- <span data-ttu-id="60576-152">**Número mínimo de conjuntos de caracteres:** se você definir **Tipo de senha necessária** como **Alfanumérica**, use essa configuração para especificar o número mínimo de conjuntos de caracteres que a senha deve conter.</span><span class="sxs-lookup"><span data-stu-id="60576-152">**Minimum number of character sets** : If you set **Required password type** to **Alphanumeric** , use this setting to specify the minimum number of character sets that the password must have.</span></span> <span data-ttu-id="60576-153">Os quatro conjuntos de caracteres são:</span><span class="sxs-lookup"><span data-stu-id="60576-153">The four character sets are:</span></span>
  - <span data-ttu-id="60576-154">Letras minúsculas</span><span class="sxs-lookup"><span data-stu-id="60576-154">Lowercase letters</span></span>
  - <span data-ttu-id="60576-155">Letras maiúsculas</span><span class="sxs-lookup"><span data-stu-id="60576-155">Uppercase letters</span></span>
  - <span data-ttu-id="60576-156">Símbolos</span><span class="sxs-lookup"><span data-stu-id="60576-156">Symbols</span></span>
  - <span data-ttu-id="60576-157">Números</span><span class="sxs-lookup"><span data-stu-id="60576-157">Numbers</span></span>

<span data-ttu-id="60576-158">Definir um número mais alto exige que o usuário crie uma senha mais complexa.</span><span class="sxs-lookup"><span data-stu-id="60576-158">Setting a higher number will require the user to create a password that is more complex.</span></span>

<span data-ttu-id="60576-159">Para dispositivos iOS, essa configuração se refere ao número de caracteres especiais (por exemplo, **!**</span><span class="sxs-lookup"><span data-stu-id="60576-159">For iOS devices, this setting refers to the number of special characters (for example, **!**</span></span> <span data-ttu-id="60576-160">, **#**, **&amp;**) que devem ser incluídos na senha.</span><span class="sxs-lookup"><span data-stu-id="60576-160">, **#** , **&amp;** ) that must be included in the password.</span></span>

- <span data-ttu-id="60576-161">**Minutos de inatividade antes que a senha seja exigida**: especifique o tempo ocioso antes que o usuário precise digitar novamente a senha.</span><span class="sxs-lookup"><span data-stu-id="60576-161">**Minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.</span></span>
- <span data-ttu-id="60576-162">**Expiração da senha (dias)**: selecione o número de dias antes que a senha expire e seja preciso criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="60576-162">**Password expiration (days)**: Select the number of days before the password expires and they must create a new one.</span></span>
- <span data-ttu-id="60576-163">**Lembrar o histórico da senha**: use essa configuração em conjunto com **Impedir a reutilização de senhas anteriores** para impedir que o usuário crie senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="60576-163">**Remember password history** : Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>
- <span data-ttu-id="60576-164">**Impedir a reutilização de senhas anteriores**: se a opção **Lembrar o histórico de senha** estiver selecionada, especifique o número de senhas usadas anteriormente que não poderão ser reutilizadas.</span><span class="sxs-lookup"><span data-stu-id="60576-164">**Prevent reuse of previous passwords** : If you selected **Remember password history** , specify the number of previously used passwords that cannot be reused.</span></span>
- <span data-ttu-id="60576-165">**Exigir uma senha quando o dispositivo volta do estado ocioso**: use essa configuração em conjunto com **Minutos de inatividade antes que a senha seja exigida**.</span><span class="sxs-lookup"><span data-stu-id="60576-165">**Require a password when the device returns from an idle state** : Use this setting together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="60576-166">O usuário é solicitado a inserir uma senha para acessar um dispositivo que está inativo durante o tempo especificado na configuração **Minutos de inatividade antes da senha ser necessária**.</span><span class="sxs-lookup"><span data-stu-id="60576-166">The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <span data-ttu-id="60576-167">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="60576-167">Email profile</span></span>
<a id="email-profile" class="xliff"></a>

- <span data-ttu-id="60576-168">**A conta de email deve ser gerenciada pelo Intune**: quando essa opção é definida como **Sim**, o dispositivo deve usar o perfil de email implantado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60576-168">**Email account must be managed by Intune** : When this option is set to **Yes** , the device must use the email profile deployed to the device.</span></span> <span data-ttu-id="60576-169">O dispositivo é considerado incompatível nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="60576-169">The device is considered noncompliant in the following situations:</span></span>
  - <span data-ttu-id="60576-170">O perfil de email é implantado em um grupo de usuários diferente do grupo de usuários que é destino da política de conformidade.</span><span class="sxs-lookup"><span data-stu-id="60576-170">The email profile is deployed to a user group other than the user group that the compliance policy targets.</span></span>
  - <span data-ttu-id="60576-171">O usuário já configurou uma conta de email no dispositivo que corresponde ao perfil de email do Intune implantado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60576-171">The user has already set up an email account on the device that matches the Intune email profile deployed to the device.</span></span> <span data-ttu-id="60576-172">Intune não pode substituir o perfil de usuário provisionado e, portanto, não é capaz de gerenciá-lo.</span><span class="sxs-lookup"><span data-stu-id="60576-172">Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.</span></span> <span data-ttu-id="60576-173">Para garantir a conformidade, o usuário deve remover as configurações de email existentes.</span><span class="sxs-lookup"><span data-stu-id="60576-173">To ensure compliance, the user must remove the existing email settings.</span></span> <span data-ttu-id="60576-174">Depois, o Intune pode instalar o perfil de email gerenciado.</span><span class="sxs-lookup"><span data-stu-id="60576-174">Then, Intune can install the managed email profile.</span></span>
- <span data-ttu-id="60576-175">**Selecione o perfil de email que deve ser gerenciado pelo Intune**: se a configuração **A conta de email deve ser gerenciada pelo Intune** for selecionada, escolha **Selecionar** para especificar o perfil de email do Intune.</span><span class="sxs-lookup"><span data-stu-id="60576-175">**Select the email profile that must be managed by Intune** : If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile.</span></span> <span data-ttu-id="60576-176">O perfil de email deve estar presente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60576-176">The email profile must be present on the device.</span></span>

<span data-ttu-id="60576-177">Para obter detalhes sobre o perfil de email, consulte [Configurar o acesso ao email corporativo usando perfis de email com o Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="60576-177">For details about email profile, see [Configure access to corporate email using email profiles with Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).</span></span>

## <span data-ttu-id="60576-178">Configurações de integridade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="60576-178">Device health settings</span></span>
<a id="device-health-settings" class="xliff"></a>

- <span data-ttu-id="60576-179">**O dispositivo não pode estar com jailbreak ou com raiz**: se você habilitar essa configuração, os dispositivos com jailbreak não serão compatíveis.</span><span class="sxs-lookup"><span data-stu-id="60576-179">**Device must not be jailbroken or rooted** : If you enable this setting, jailbroken devices will not be compliant.</span></span>

## <span data-ttu-id="60576-180">Propriedades do dispositivo</span><span class="sxs-lookup"><span data-stu-id="60576-180">Device properties</span></span>
<a id="device-properties" class="xliff"></a>

- <span data-ttu-id="60576-181">**Sistema operacional mínimo exigido**: quando um dispositivo não atende ao requisito mínimo de versão do sistema operacional, ele será relatado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="60576-181">**Minimum OS required** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span> <span data-ttu-id="60576-182">É exibido um link com informações sobre como atualizar.</span><span class="sxs-lookup"><span data-stu-id="60576-182">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="60576-183">O usuário pode optar por atualizar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="60576-183">The user can choose to upgrade their device.</span></span> <span data-ttu-id="60576-184">Depois disso, ele pode acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="60576-184">After that, they can access company resources.</span></span>
- <span data-ttu-id="60576-185">**Versão do sistema operacional máxima permitida**: quando um dispositivo estiver usando uma versão de sistema operacional posterior àquela especificada na regra, o acesso aos recursos da empresa será bloqueado e será solicitado que o usuário entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="60576-185">**Maximum OS version allowed** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin.</span></span> <span data-ttu-id="60576-186">Até que haja uma alteração na regra para permitir a versão do SO, este dispositivo não pode ser usado para acessar recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="60576-186">Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
