---
title: "Introdução ao Intune no portal do Azure"
titleSuffix: Intune on Azure
description: "Conheça os conceitos básicos do Intune no portal do Azure e como ele pode ajudar você a gerenciar seus dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 06/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7549f3277c23c3951090502f2babfe7c47b0a201
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="44c51-103">Introdução ao Microsoft Intune no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="44c51-103">Introduction to Microsoft Intune in the Azure portal</span></span>
<a id="introduction-to-microsoft-intune-in-the-azure-portal" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="44c51-104">O Microsoft Intune agora está no portal do Azure, o que significa que a funcionalidade e os fluxos de trabalho conhecidos agora são diferentes.</span><span class="sxs-lookup"><span data-stu-id="44c51-104">Microsoft Intune is now in the Azure portal meaning that the workflows and functionality you are used to are now different.</span></span>
<span data-ttu-id="44c51-105">O novo portal oferece uma funcionalidade nova e atualizada no portal do Azure, em que você pode gerenciar os dispositivos móveis, computadores e aplicativos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="44c51-105">The new portal offers you new and updated functionality in the Azure portal where you can manage your organization's mobile devices, PCs, and apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44c51-106">**Ainda não consegue ver o novo portal?**</span><span class="sxs-lookup"><span data-stu-id="44c51-106">**Don’t see the new portal yet?**</span></span><br>
> <span data-ttu-id="44c51-107">Os locatários existentes estão sendo migrados para a nova experiência.</span><span class="sxs-lookup"><span data-stu-id="44c51-107">Existing tenants are being migrated to the new experience.</span></span> <span data-ttu-id="44c51-108">Uma notificação é mostrada no Centro de Mensagens do Office antes da migração do locatário.</span><span class="sxs-lookup"><span data-stu-id="44c51-108">A notification is shown in the Office Message Center before your tenant migrates.</span></span>
>
> <span data-ttu-id="44c51-109">As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que os fluxos de trabalho do Registro da Apple estejam disponíveis no Azure.</span><span class="sxs-lookup"><span data-stu-id="44c51-109">Intune accounts created before January 2017 require a one-time migration before Apple Enrollment workflows are available in Azure.</span></span> <span data-ttu-id="44c51-110">O agendamento para a migração ainda não foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="44c51-110">The schedule for migration has not been announced yet.</span></span> <span data-ttu-id="44c51-111">Caso sua conta existente não possa acessar o portal do Azure, recomendamos criar uma conta de avaliação.</span><span class="sxs-lookup"><span data-stu-id="44c51-111">If your existing account cannot access the Azure portal, we recommend creating a trial account.</span></span>
>
> <span data-ttu-id="44c51-112">Examine a lista de possíveis bloqueadores (em inglês) em https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/</span><span class="sxs-lookup"><span data-stu-id="44c51-112">Review the list of potential blockers https://blogs.technet.microsoft.com/intunesupport/2017/05/17/intune-migration-blockers-for-grouping-targeting/</span></span>


<span data-ttu-id="44c51-113">Encontre informações sobre o novo portal nesta biblioteca, que está sempre sendo atualizada.</span><span class="sxs-lookup"><span data-stu-id="44c51-113">You can find information about the new portal in this library, and it is continually updated.</span></span> <span data-ttu-id="44c51-114">Caso tenha sugestões que gostaria de ver, deixe seus comentários nos comentários do tópico.</span><span class="sxs-lookup"><span data-stu-id="44c51-114">If you have suggestions you'd like to see, leave feedback in the topic comments.</span></span> <span data-ttu-id="44c51-115">Adoraríamos ouvir sua opinião.</span><span class="sxs-lookup"><span data-stu-id="44c51-115">We'd love to hear from you.</span></span>

<span data-ttu-id="44c51-116">Destaques da nova experiência incluem:</span><span class="sxs-lookup"><span data-stu-id="44c51-116">Highlights of the new experience include:</span></span>

- <span data-ttu-id="44c51-117">Um console integrado para todos os seus componentes de EMS (Enterprise Mobility + Security)</span><span class="sxs-lookup"><span data-stu-id="44c51-117">An integrated console for all your Enterprise Mobility + Security (EMS) components</span></span>
- <span data-ttu-id="44c51-118">Um console baseado em HTML criado nos padrões da Web</span><span class="sxs-lookup"><span data-stu-id="44c51-118">An HTML-based console built on web standards</span></span>
- <span data-ttu-id="44c51-119">Suporte à API do Microsoft Graph para automatizar diversas ações</span><span class="sxs-lookup"><span data-stu-id="44c51-119">Microsoft Graph API support to automate many actions</span></span>
- <span data-ttu-id="44c51-120">Grupos do Azure Active Directory (AD) para fornecer compatibilidade entre todos os aplicativos do Azure</span><span class="sxs-lookup"><span data-stu-id="44c51-120">Azure Active Directory (AD) groups to provide compatibility across all your Azure applications</span></span>
- <span data-ttu-id="44c51-121">Suporte para a maioria dos navegadores da Web modernos</span><span class="sxs-lookup"><span data-stu-id="44c51-121">Support for most modern web browsers</span></span>

<span data-ttu-id="44c51-122">Se você estiver buscando documentação para o console clássico do Intune, consulte a [Biblioteca de documentação do Intune](https://docs.microsoft.com/intune-classic/).</span><span class="sxs-lookup"><span data-stu-id="44c51-122">If you are looking for documentation for the classic Intune console, see [the Intune documentation library](https://docs.microsoft.com/intune-classic/).</span></span>

## <span data-ttu-id="44c51-123">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="44c51-123">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="44c51-124">Para usar o Intune no Portal do Azure, você deve ter uma conta de administrador e locatário Intune.</span><span class="sxs-lookup"><span data-stu-id="44c51-124">To use Intune in the Azure portal, you must have an Intune admin and tenant account.</span></span> <span data-ttu-id="44c51-125">[Inscreva-se em uma conta](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) se você ainda não tiver uma.</span><span class="sxs-lookup"><span data-stu-id="44c51-125">[Sign up for an account](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) if you don't already have one.</span></span>

## <span data-ttu-id="44c51-126">Navegadores da Web com suporte no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="44c51-126">Supported web browsers for the Azure portal</span></span>
<a id="supported-web-browsers-for-the-azure-portal" class="xliff"></a>

<span data-ttu-id="44c51-127">O Portal do Azure é executado na maioria dos computadores, Macs e tablets.</span><span class="sxs-lookup"><span data-stu-id="44c51-127">The Azure portal runs on most modern PCs, Macs, and tablets.</span></span> <span data-ttu-id="44c51-128">Não há suporte para telefones celulares.</span><span class="sxs-lookup"><span data-stu-id="44c51-128">Mobile phones are not supported.</span></span>
<span data-ttu-id="44c51-129">No momento, há suporte para os seguintes navegadores:</span><span class="sxs-lookup"><span data-stu-id="44c51-129">Currently, the following browsers are supported:</span></span>

- <span data-ttu-id="44c51-130">Microsoft Edge (última versão)</span><span class="sxs-lookup"><span data-stu-id="44c51-130">Microsoft Edge (latest version)</span></span>
- <span data-ttu-id="44c51-131">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="44c51-131">Microsoft Internet Explorer 11</span></span>
- <span data-ttu-id="44c51-132">Safari (última versão, somente Mac)</span><span class="sxs-lookup"><span data-stu-id="44c51-132">Safari (latest version, Mac only)</span></span>
- <span data-ttu-id="44c51-133">Chrome (última versão)</span><span class="sxs-lookup"><span data-stu-id="44c51-133">Chrome (latest version)</span></span>
- <span data-ttu-id="44c51-134">Firefox (última versão)</span><span class="sxs-lookup"><span data-stu-id="44c51-134">Firefox (latest version)</span></span>

<span data-ttu-id="44c51-135">Visite o [portal do Azure](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) para obter as informações mais recentes sobre os navegadores com suporte.</span><span class="sxs-lookup"><span data-stu-id="44c51-135">Check the [Azure portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) for the latest information about supported browsers.</span></span>

## <span data-ttu-id="44c51-136">O que há nesta biblioteca?</span><span class="sxs-lookup"><span data-stu-id="44c51-136">What's in this library?</span></span>
<a id="whats-in-this-library" class="xliff"></a>

<span data-ttu-id="44c51-137">A documentação reflete o layout do portal do Intune para tornar mais fácil encontrar as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="44c51-137">The documentation reflects the layout of the Intune portal to make it easier to find the information you need.</span></span>

![Cargas de trabalho do Portal do Azure](./media/azure-portal-workloads.png)

### <span data-ttu-id="44c51-139">Introdução</span><span class="sxs-lookup"><span data-stu-id="44c51-139">Introduction and get started</span></span>
<a id="introduction-and-get-started" class="xliff"></a>
<span data-ttu-id="44c51-140">Esta seção contém [informações de introdução](introduction-intune.md) que ajudam você a começar a usar o Intune.</span><span class="sxs-lookup"><span data-stu-id="44c51-140">This section contains [introductory information](introduction-intune.md) that helps you get started using Intune.</span></span>
### <span data-ttu-id="44c51-141">Plano e design</span><span class="sxs-lookup"><span data-stu-id="44c51-141">Plan and design</span></span>
<a id="plan-and-design" class="xliff"></a>
<span data-ttu-id="44c51-142">Informações para ajudá-lo a [planejar e projetar](/intune-classic/plan-design/introduction) seu ambiente do Intune.</span><span class="sxs-lookup"><span data-stu-id="44c51-142">Information to help you [plan and design](/intune-classic/plan-design/introduction) your Intune environment.</span></span>
### <span data-ttu-id="44c51-143">Registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="44c51-143">Device enrollment</span></span>
<a id="device-enrollment" class="xliff"></a>
<span data-ttu-id="44c51-144">[Como fazer o Intune gerenciar seus dispositivos](device-enrollment.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-144">[How to get your devices managed by Intune](device-enrollment.md).</span></span>
### <span data-ttu-id="44c51-145">Conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="44c51-145">Device compliance</span></span>
<a id="device-compliance" class="xliff"></a>
<span data-ttu-id="44c51-146">[Defina um nível de conformidade para seus dispositivos e, depois, relate os dispositivos que não estão em conformidade](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-146">[Define a compliance level for your devices, then report any devices that are not compliant](device-compliance.md).</span></span>
### <span data-ttu-id="44c51-147">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="44c51-147">Device configuration</span></span>
<a id="device-configuration" class="xliff"></a>
<span data-ttu-id="44c51-148">[Entenda os perfis que você pode usar para definir as configurações e recursos nos dispositivos gerenciados](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-148">[Understand the profiles you can use to configure settings and features on devices you manage](device-profiles.md).</span></span>
### <span data-ttu-id="44c51-149">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="44c51-149">Devices</span></span>
<a id="devices" class="xliff"></a>
<span data-ttu-id="44c51-150">[Familiarize-se com os dispositivos gerenciados com relatórios e inventários](device-management.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-150">[Get to know the devices you manage with inventory and reports](device-management.md).</span></span>
### <span data-ttu-id="44c51-151">Aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="44c51-151">Mobile apps</span></span>
<a id="mobile-apps" class="xliff"></a>
<span data-ttu-id="44c51-152">[Como publicar, gerenciar, configurar e proteger os aplicativos](app-management.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-152">[How to publish, manage, configure, and protect apps](app-management.md).</span></span>
### <span data-ttu-id="44c51-153">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="44c51-153">Conditional access</span></span>
<a id="conditional-access" class="xliff"></a>
<span data-ttu-id="44c51-154">[Restrinja o acesso aos serviços do Exchange com base nas condições que você especificar](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-154">[Restrict access to Exchange services depending on conditions you specify](conditional-access.md).</span></span>
### <span data-ttu-id="44c51-155">Acesso local</span><span class="sxs-lookup"><span data-stu-id="44c51-155">On-premises access</span></span>
<a id="on-premises-access" class="xliff"></a>
[<span data-ttu-id="44c51-156">Configurar o acesso ao Exchange ActiveSync e ao Exchange local</span><span class="sxs-lookup"><span data-stu-id="44c51-156">Configure access to Exchange ActiveSync, and Exchange on-premises</span></span>](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <span data-ttu-id="44c51-157">Usuários</span><span class="sxs-lookup"><span data-stu-id="44c51-157">Users</span></span>
<a id="users" class="xliff"></a>
<span data-ttu-id="44c51-158">[Saiba mais sobre os usuários de dispositivos que você gerencia e classifique os recursos em grupos](user-management.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-158">[Learn about the users of devices you manage and sort resources into groups](user-management.md).</span></span>
### <span data-ttu-id="44c51-159">Grupos</span><span class="sxs-lookup"><span data-stu-id="44c51-159">Groups</span></span>
<a id="groups" class="xliff"></a>
[<span data-ttu-id="44c51-160">Saiba mais sobre como você pode usar grupos do Azure Active Directory com o Intune</span><span class="sxs-lookup"><span data-stu-id="44c51-160">Learn about how you can use Azure Active Directory groups with Intune</span></span>](groups-get-started.md)
### <span data-ttu-id="44c51-161">Funções do Intune</span><span class="sxs-lookup"><span data-stu-id="44c51-161">Intune roles</span></span>
<a id="intune-roles" class="xliff"></a>
<span data-ttu-id="44c51-162">[Controle quem pode executar várias ações do Intune e a quem essas ações se aplicam](role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-162">[Control who can perform various Intune actions, and who those actions apply to](role-based-access-control.md).</span></span> <span data-ttu-id="44c51-163">Você pode usar as funções internas que abordam alguns cenários comuns do Intune ou pode criar suas próprias funções.</span><span class="sxs-lookup"><span data-stu-id="44c51-163">You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.</span></span>
### <span data-ttu-id="44c51-164">Atualizações de software</span><span class="sxs-lookup"><span data-stu-id="44c51-164">Software updates</span></span>
<a id="software-updates" class="xliff"></a>
<span data-ttu-id="44c51-165">[Saiba mais sobre como configurar atualizações de software para dispositivos com Windows 10](windows-update-for-business-configure.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-165">[Learn about how to configure software updates for Windows 10 devices](windows-update-for-business-configure.md).</span></span>



## <span data-ttu-id="44c51-166">Quais são as novidades?</span><span class="sxs-lookup"><span data-stu-id="44c51-166">What's new?</span></span>
<a id="whats-new" class="xliff"></a>

<span data-ttu-id="44c51-167">[Conheça as novidades do Intune](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="44c51-167">[Find out what's new in Intune](whats-new.md).</span></span>
