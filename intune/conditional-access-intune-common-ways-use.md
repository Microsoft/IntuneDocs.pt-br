---
title: Acesso condicional com o Intune
titleSuffix: Intune on Azure
description: Maneiras comuns de usar o acesso condicional com o Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ba1f12d762a6288fc2e7a3bfdae637f8ae13a94
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3b3f4-103">Maneiras comuns de usar o acesso condicional com o Intune</span><span class="sxs-lookup"><span data-stu-id="3b3f4-103">Common ways to use conditional access with Intune</span></span>
<a id="common-ways-to-use-conditional-access-with-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="3b3f4-104">Você precisa configurar a política de conformidade do dispositivo móvel do Intune e as funcionalidades de MAM (gerenciamento de aplicativo móvel) do Intune para impor a conformidade do acesso condicional em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-104">You need to configure Intune mobile device compliance policy, and the Intune mobile application management (MAM) capabilities to drive conditional access compliance at your organization.</span></span> <span data-ttu-id="3b3f4-105">Vamos falar sobre as maneiras comuns de usar o acesso condicional com o Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-105">Let’s talk about the common ways to use conditional access with Intune.</span></span>

## <span data-ttu-id="3b3f4-106">Acesso condicional baseado no dispositivo</span><span class="sxs-lookup"><span data-stu-id="3b3f4-106">Device-based conditional access</span></span>
<a id="device-based-conditional-access" class="xliff"></a>

<span data-ttu-id="3b3f4-107">O Intune e o Azure Active Directory trabalham juntos para garantir que somente dispositivos gerenciados e em conformidade têm permissão para acessar o email, os serviços do Office 365, aplicativos SaaS (Software como serviço) e [aplicativos locais](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-107">Intune and Azure Active Directory work together to make sure only managed and compliant devices are allowed access to email, Office 365 services, Software as a service (SaaS) apps, and [on-premises apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).</span></span> <span data-ttu-id="3b3f4-108">Além disso, você pode definir uma política no Azure Active Directory para permitir que somente os computadores que ingressaram no domínio ou os dispositivos móveis que foram registrados no Intune acessem os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-108">Additionally, you can set a policy in Azure Active Directory to only enable computers that are domain-joined, or mobile devices that are enrolled in Intune to access Office 365 services.</span></span>

<span data-ttu-id="3b3f4-109">O Intune fornece funcionalidades de política de conformidade do dispositivo que avaliam o status de conformidade dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-109">Intune provides device compliance policy capabilities that evaluate the compliance status of the devices.</span></span> <span data-ttu-id="3b3f4-110">O status da conformidade é relatado ao Azure Active Directory, que usa isso para impor a política de acesso condicional criada no Azure Active Directory quando o usuário tenta acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-110">The compliance status is reported to Azure Active Directory that uses it to enforce the conditional access policy created in Azure Active Directory when the user tries to access company resources.</span></span>

<span data-ttu-id="3b3f4-111">Começando no [novo portal do Azure](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), as políticas de acesso condicional baseado no dispositivo para o Exchange Online e outros produtos do Office 365 são configuradas por meio do portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-111">Starting at the [new Azure portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), device-based conditional access policies for Exchange online and other Office 365 products are configured through the Azure portal.</span></span>

-   <span data-ttu-id="3b3f4-112">Saiba mais sobre o [acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-112">Learn more about [conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span></span>

-   <span data-ttu-id="3b3f4-113">Saiba mais sobre [o que é a conformidade do dispositivo do Intune](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-113">Learn more about [what is Intune device compliance](device-compliance.md).</span></span>

-   <span data-ttu-id="3b3f4-114">Saiba mais sobre a [proteção de email, o Office 365 e outros serviços usando o acesso condicional com o Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-114">Learn more about [protecting e-mail, Office 365, and other services using conditional access with Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span></span>

### <span data-ttu-id="3b3f4-115">Acesso condicional para o Exchange Local</span><span class="sxs-lookup"><span data-stu-id="3b3f4-115">Conditional access for Exchange on-premises</span></span>
<a id="conditional-access-for-exchange-on-premises" class="xliff"></a>

<span data-ttu-id="3b3f4-116">O acesso condicional pode ser usado para permitir ou bloquear o acesso ao **Exchange Local** com base no estado do registro e nas políticas de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-116">Conditional access can be used to allow or block access to **Exchange on-premises** based on the device compliance policies and enrollment state.</span></span> <span data-ttu-id="3b3f4-117">Quando o acesso condicional é usado em combinação com uma política de conformidade do dispositivo, somente os dispositivos em conformidade podem acessar o Exchange Local.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-117">When conditional access is used in combination with a device compliance policy, only compliant devices are allowed access to Exchange on-premises.</span></span>

<span data-ttu-id="3b3f4-118">Defina configurações avançadas no acesso condicional para um controle mais granular, como:</span><span class="sxs-lookup"><span data-stu-id="3b3f4-118">You can configure advanced settings in conditional access for more granular control such as:</span></span>

-   <span data-ttu-id="3b3f4-119">Permitir ou bloquear algumas plataformas.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-119">Allow or block certain platforms.</span></span>

-   <span data-ttu-id="3b3f4-120">Bloquear imediatamente dispositivos que não são gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-120">Immediately block devices that are not managed by Intune.</span></span>

<span data-ttu-id="3b3f4-121">Qualquer dispositivo usado para acessar o Exchange Local é verificado quanto à conformidade quando as políticas de conformidade do dispositivo e de acesso condicional são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-121">Any device used to access Exchange on-premises is checked for compliance when device compliance and conditional access policies are applied.</span></span>

<span data-ttu-id="3b3f4-122">Quando os dispositivos não atendem às condições definidas, o usuário final é guiado pelo processo de registro do dispositivo para corrigir o problema que impede o dispositivo de estar em conformidade.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-122">When devices do not meet the conditions set, the end user is guided through the process of enrolling the device to fix the issue that is making the device non-compliant.</span></span>

#### <span data-ttu-id="3b3f4-123">Como funciona o acesso condicional no Exchange Local</span><span class="sxs-lookup"><span data-stu-id="3b3f4-123">How conditional access for Exchange on-premises works</span></span>
<a id="how-conditional-access-for-exchange-on-premises-works" class="xliff"></a>

<span data-ttu-id="3b3f4-124">O Intune Exchange Connector mantém todos os registros do EAS (Exchange Active Sync) que existem no servidor Exchange, de forma que o Intune possa usar esses registros do EAS e mapeá-los para registros de dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-124">The Intune Exchange connector pulls in all the Exchange Active Sync (EAS) records that exist at the Exchange server so Intune can take these EAS records and map them to Intune device records.</span></span> <span data-ttu-id="3b3f4-125">Esses registros são dispositivos registrados e reconhecidos pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-125">These records are devices enrolled and recognized by Intune.</span></span> <span data-ttu-id="3b3f4-126">Esse processo permite ou bloqueia o acesso a email.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-126">This process allows or blocks e-mail access.</span></span>

<span data-ttu-id="3b3f4-127">Se o registro do EAS for novo e o Intune não o reconhecer, o Intune emitirá um comando let que bloqueia o acesso a email.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-127">If the EAS record is brand new, and Intune is not aware of it, Intune issues a command-let that blocks access to e-mail.</span></span> <span data-ttu-id="3b3f4-128">Estes são mais detalhes sobre como esse processo funciona:</span><span class="sxs-lookup"><span data-stu-id="3b3f4-128">Here are more details on how this process works:</span></span>

![Fluxograma do Exchange Local com AC](./media/ca-intune-common-ways-1.png)

1.  <span data-ttu-id="3b3f4-130">O usuário tenta acessar o email corporativo, que está hospedado no Exchange Local 2010 SP1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-130">User tries to access corporate e-mail, which is hosted on Exchange on-premises 2010 SP1 or later.</span></span>

2.  <span data-ttu-id="3b3f4-131">Se o dispositivo não for gerenciado pelo Intune, ele terá o acesso a email bloqueado.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-131">If the device is not managed by Intune, it will be blocked access to e-mail.</span></span> <span data-ttu-id="3b3f4-132">O Intune envia uma notificação de bloqueio para o cliente do EAS.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-132">Intune sends block notification to the EAS client.</span></span>

3.  <span data-ttu-id="3b3f4-133">O EAS recebe a notificação de bloqueio, move o dispositivo para a quarentena e envia o email de quarentena com etapas de correção que contêm links para que os usuários possam registrar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-133">EAS receives block notification, moves the device to quarantine, and sends the quarantine e-mail with remediation steps that contain links so the users can enroll their devices.</span></span>

4.  <span data-ttu-id="3b3f4-134">Ocorre o processo de Ingresso no local de trabalho, que é a primeira etapa para que o dispositivo seja gerenciado pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-134">The Workplace join process happens, which is the first step to have the device managed by Intune.</span></span>

5.  <span data-ttu-id="3b3f4-135">O dispositivo é registrado no Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-135">The device gets enrolled into Intune.</span></span>

6.  <span data-ttu-id="3b3f4-136">O Intune mapeia o registro do EAS para um registro de dispositivo e salva o estado de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-136">Intune maps the EAS record to a device record, and saves the device compliance state.</span></span>

7.  <span data-ttu-id="3b3f4-137">A ID do cliente do EAS é registrada pelo processo de Registro de Dispositivo do Azure AD, que cria uma relação entre o registro de dispositivo do Intune e a ID do cliente do EAS.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-137">The EAS client ID gets registered by the Azure AD Device Registration process, which creates a relationship between the Intune device record, and the EAS client ID.</span></span>

8.  <span data-ttu-id="3b3f4-138">O Registro de Dispositivo do Azure AD salva as informações de estado do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-138">The Azure AD Device Registration saves the device state information.</span></span>

9.  <span data-ttu-id="3b3f4-139">Se o usuário atender às políticas de acesso condicional, o Intune emitirá um comando let por meio do Intune Exchange Connector que permite a sincronização da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-139">If the user meets the conditional access policies, Intune issues a command-let through the Intune Exchange connector that allows the mailbox to sync.</span></span>

10. <span data-ttu-id="3b3f4-140">O servidor Exchange envia a notificação ao cliente do EAS, de forma que o usuário possa acessar o email.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-140">Exchange server sends the notification to EAS client so the user can access e-mail.</span></span>

#### <span data-ttu-id="3b3f4-141">O que é a função do Intune?</span><span class="sxs-lookup"><span data-stu-id="3b3f4-141">What’s the Intune role?</span></span>
<a id="whats-the-intune-role" class="xliff"></a>

<span data-ttu-id="3b3f4-142">O Intune avalia e gerencia o estado do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-142">Intune evaluates and manage the device state.</span></span>

#### <span data-ttu-id="3b3f4-143">O que é a função de servidor Exchange?</span><span class="sxs-lookup"><span data-stu-id="3b3f4-143">What’s the Exchange server role?</span></span>
<a id="whats-the-exchange-server-role" class="xliff"></a>

<span data-ttu-id="3b3f4-144">O servidor Exchange fornece a API e a infraestrutura para mover os dispositivos para sua quarentena.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-144">Exchange server provides API and infrastructure to move devices to its quarantine.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="3b3f4-145">Lembre-se de que o usuário que está usando o dispositivo deve ter um perfil de conformidade atribuído a ele para que o dispositivo seja avaliado quanto à conformidade.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-145">Keep in mind that the user who’s using the device must have a compliance profile assigned to them so the device to be evaluated for compliance.</span></span> <span data-ttu-id="3b3f4-146">Se nenhuma política de conformidade for implantada para o usuário, o dispositivo será tratado como em conformidade e nenhuma restrição de acesso será aplicada.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-146">If no compliance policy is deployed to the user, the device is treated as compliant and no access restrictions are applied.</span></span>

### <span data-ttu-id="3b3f4-147">Acesso condicional baseado em controle de acesso à rede</span><span class="sxs-lookup"><span data-stu-id="3b3f4-147">Conditional access based on network access control</span></span>
<a id="conditional-access-based-on-network-access-control" class="xliff"></a>

<span data-ttu-id="3b3f4-148">O Intune integrado com parceiros, como Cisco ISE, Aruba Clear Pass e Citrix NetScaler, para fornecer controles de acesso baseados no registro do Intune e no estado de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-148">Intune integrated with partners like Cisco ISE, Aruba Clear Pass, and Citrix NetScaler to provide access controls based on the Intune enrollment and the device compliance state.</span></span>

<span data-ttu-id="3b3f4-149">Os usuários podem ter o acesso permitido ou negado ao tentar acessar os recursos corporativos de Wi-Fi ou VPN, dependendo se o dispositivo é gerenciado e está em conformidade com as políticas de conformidade do dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-149">Users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources based on whether the device is managed and compliant with Intune device compliance policies.</span></span>

-   <span data-ttu-id="3b3f4-150">Saiba mais sobre a [integração de NAC com o Intune](network-access-control-integrate.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-150">Learn more about the [NAC integration with Intune](network-access-control-integrate.md).</span></span>

### <span data-ttu-id="3b3f4-151">Acesso condicional baseado nos riscos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3b3f4-151">Conditional access based on device risk</span></span>
<a id="conditional-access-based-on-device-risk" class="xliff"></a>

<span data-ttu-id="3b3f4-152">O Intune em parceria com fornecedores de Defesa contra Ameaças Móveis, que fornece uma solução de segurança para detectar malwares, cavalos de Troia e outras ameaças em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-152">Intune partnered with Mobile Threat Defense vendors that provides a security solution to detect malwares, Trojans, and other threats on mobile devices.</span></span>

#### <span data-ttu-id="3b3f4-153">Como funciona a integração entre o Intune e a defesa contra ameaças móveis</span><span class="sxs-lookup"><span data-stu-id="3b3f4-153">How the Intune and mobile threat defense integration works</span></span>
<a id="how-the-intune-and-mobile-threat-defense-integration-works" class="xliff"></a>

<span data-ttu-id="3b3f4-154">Quando os dispositivos móveis têm o agente de defesa contra ameaças móveis instalado, o agente pode enviar mensagens sobre o estado de conformidade novamente para o Intune, relatando se uma ameaça foi encontrada no próprio dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-154">When mobile devices have the mobile threat defense agent installed, the agent can send compliance state messages back to Intune reporting if a threat has been found in the mobile device itself.</span></span>

<span data-ttu-id="3b3f4-155">A integração entre o Intune e a defesa contra ameaças móveis desempenha um fator importante nas decisões sobre o acesso condicional baseadas nos riscos do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-155">The Intune and mobile threat defense integration plays a factor at the conditional access decisions based on device risk.</span></span>

-   <span data-ttu-id="3b3f4-156">Saiba mais sobre a [defesa contra ameaças móveis do Intune](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-156">Learn more about [Intune mobile threat defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).</span></span>

### <span data-ttu-id="3b3f4-157">Acesso condicional para computadores Windows</span><span class="sxs-lookup"><span data-stu-id="3b3f4-157">Conditional access for Windows PCs</span></span>
<a id="conditional-access-for-windows-pcs" class="xliff"></a>

<span data-ttu-id="3b3f4-158">O acesso condicional para computadores fornece funcionalidades semelhantes disponíveis para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-158">Conditional access for PCs provide similar capabilities available for mobile devices.</span></span> <span data-ttu-id="3b3f4-159">Vamos falar sobre as maneiras pelas quais você pode usar o acesso condicional ao gerenciar computadores com o Intune.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-159">Let’s talk about the ways you can use conditional access when managing PCs with Intune.</span></span>

#### <span data-ttu-id="3b3f4-160">De propriedade corporativa</span><span class="sxs-lookup"><span data-stu-id="3b3f4-160">Corporate-owned</span></span>
<a id="corporate-owned" class="xliff"></a>

-   <span data-ttu-id="3b3f4-161">**Ingressado no domínio do AD local:** essa tem sido a opção mais comum de implantação de acesso condicional para organizações, que estão razoavelmente confiantes com o fato de que já estão gerenciando seus computadores por meio de políticas de grupo do AD e/ou com o System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-161">**On premises AD domain joined:** This has been the most common conditional access deployment option for organizations, whose are reasonable comfortable with the fact they’re already managing their PCs through AD group policies and/or with System Center Configuration Manager.</span></span>

-   <span data-ttu-id="3b3f4-162">**Ingressado no domínio do Azure AD e gerenciamento do Intune:** esse cenário é normalmente voltado para cenários CYOD (Escolha seu próprio dispositivo) e cenários de laptops móveis em que esses dispositivos raramente são conectados à rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-162">**Azure AD domain joined and Intune management:** This scenario is typically geared to Choose Your Own Device (CYOD), and roaming laptop scenarios where these devices are rarely connected to corporate-network.</span></span> <span data-ttu-id="3b3f4-163">O dispositivo é ingressado no Azure AD e registrado no Intune, o que remove qualquer dependência do AD local e dos controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-163">The device joins to the Azure AD and gets enrolled to Intune, which removes any dependency on on-premises AD, and domain controllers.</span></span> <span data-ttu-id="3b3f4-164">Isso pode ser usado como um critério de acesso condicional ao acessar recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-164">This can be used as a conditional access criteria when accessing corporate resources.</span></span>

-   <span data-ttu-id="3b3f4-165">**Ingressado no domínio do AD e o System Center Configuration Manager:** no branch atual, o System Center Configuration Manager fornece funcionalidades de acesso condicional que podem avaliar critérios específicos de conformidade, além de ser um computador ingressado no domínio:</span><span class="sxs-lookup"><span data-stu-id="3b3f4-165">**AD domain joined and System Center Configuration Manager:** As of current branch, System Center Configuration Manager provides conditional access capabilities that can evaluate specific compliance criteria, in addition to be a domain-joined PC:</span></span>

    -   <span data-ttu-id="3b3f4-166">O computador está criptografado?</span><span class="sxs-lookup"><span data-stu-id="3b3f4-166">Is the PC encrypted?</span></span>

    -   <span data-ttu-id="3b3f4-167">Algum malware está instalado?</span><span class="sxs-lookup"><span data-stu-id="3b3f4-167">Is Malware installed?</span></span> <span data-ttu-id="3b3f4-168">Ele está atualizado?</span><span class="sxs-lookup"><span data-stu-id="3b3f4-168">Is it up-to-date?</span></span>

    -   <span data-ttu-id="3b3f4-169">O dispositivo está desbloqueado ou com raiz?</span><span class="sxs-lookup"><span data-stu-id="3b3f4-169">Is the device jailbroken or rooted?</span></span>

#### <span data-ttu-id="3b3f4-170">BYOD (Traga seu próprio dispositivo)</span><span class="sxs-lookup"><span data-stu-id="3b3f4-170">Bring your own device (BYOD)</span></span>
<a id="bring-your-own-device-byod" class="xliff"></a>

-   <span data-ttu-id="3b3f4-171">**Ingresso no local de trabalho e gerenciamento do Intune:** com essa opção, o usuário pode ingressar seus dispositivos pessoais para acessar recursos e serviços corporativos.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-171">**Workplace join and Intune management:** Here the user can join their personal devices to access corporate resources and services.</span></span> <span data-ttu-id="3b3f4-172">Use o Ingresso no local de trabalho e registre dispositivos no Intune para receber políticas no dispositivo, que também é outra opção para avaliar os critérios de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-172">You can use Workplace join and enroll devices into Intune to receive device-level policies, which is also another option to evaluate conditional access criteria.</span></span>

## <span data-ttu-id="3b3f4-173">Acesso condicional baseado no aplicativo</span><span class="sxs-lookup"><span data-stu-id="3b3f4-173">App-based conditional access</span></span>
<a id="app-based-conditional-access" class="xliff"></a>

<span data-ttu-id="3b3f4-174">O Intune e o Azure Active Directory funcionam em conjunto para garantir que somente aplicativos gerenciados podem acessar o email corporativo ou outros serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3b3f4-174">Intune and Azure Active Directory work together to make sure only managed apps can access corporate e-mail or other Office 365 services.</span></span>

-   <span data-ttu-id="3b3f4-175">Saiba mais sobre o [acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-175">Learn more about [app-based conditional access with Intune](app-based-conditional-access-intune.md).</span></span>

## <span data-ttu-id="3b3f4-176">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3b3f4-176">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="3b3f4-177">Como configurar o acesso condicional no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3b3f4-177">How to configure conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

<span data-ttu-id="3b3f4-178">[Como instalar o Exchange Connector local com o Intune](https://docs.microsoft.com/intune/exchange-connector-install).</span><span class="sxs-lookup"><span data-stu-id="3b3f4-178">[How to install on-premises Exchange connector with Intune](https://docs.microsoft.com/intune/exchange-connector-install).</span></span>

[<span data-ttu-id="3b3f4-179">Como criar uma política de acesso condicional para o Exchange Local</span><span class="sxs-lookup"><span data-stu-id="3b3f4-179">How to create a conditional access policy for Exchange on-premises</span></span>](conditional-access-exchange-create.md)
