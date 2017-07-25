---
title: Criar um design
description: "Este artigo ajuda você a criar um design para um design e uma implementação somente na nuvem do Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a8e38e29-f5e3-4a71-a170-d3b1a06e37c6
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fdd75bd2b96eb20e0e73b7f8f76cf1a5cc035011
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="0586d-103">Criar um design</span><span class="sxs-lookup"><span data-stu-id="0586d-103">Create a design</span></span>
<a id="create-a-design" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="0586d-104">A seção do guia deve ser usada em paralelo com outros tópicos da Seção 2.</span><span class="sxs-lookup"><span data-stu-id="0586d-104">The section of the guide should be used in parallel with other topics in Section 2.</span></span> <span data-ttu-id="0586d-105">Esse design se baseia nas informações coletadas e nas decisões tomadas ao concluir as seções anteriores deste guia.</span><span class="sxs-lookup"><span data-stu-id="0586d-105">This design is based on the information you collect and decisions you make when completing previous sections of this guide.</span></span> <span data-ttu-id="0586d-106">Nesta seção sobre design, temos como foco o Intune autônomo, que é um serviço baseado em nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0586d-106">In this design section, we focus on Intune standalone, which is a Microsoft cloud-based service.</span></span>

<span data-ttu-id="0586d-107">Embora haja requisitos mínimos de infraestrutura local, trabalhe em um plano de design para garantir que você tem a solução de gerenciamento de dispositivo móvel certa que atende a suas metas, seus objetivos e requisitos.</span><span class="sxs-lookup"><span data-stu-id="0586d-107">Although there’s minimal on-premises infrastructure requirements, work on a design plan to make sure you have the right mobile device management solution that meets your goals, objectives, and requirements.</span></span>

<span data-ttu-id="0586d-108">Além disso, é comum haver alterações de design durante as fases de implementação e teste. Portanto, lembre-se de documentar essas alterações e o motivo, conforme elas ocorrerem.</span><span class="sxs-lookup"><span data-stu-id="0586d-108">Additionally, it’s common to have design changes during the implementation and testing phases, make sure to document these changes, and the rationale behind it as they occur.</span></span> <span data-ttu-id="0586d-109">O design inclui as seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="0586d-109">The design includes the following areas:</span></span>

-   <span data-ttu-id="0586d-110">O ambiente atual</span><span class="sxs-lookup"><span data-stu-id="0586d-110">The current environment</span></span>

-   <span data-ttu-id="0586d-111">Opções de implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="0586d-111">Intune deployment options</span></span>

-   <span data-ttu-id="0586d-112">Requisitos de identidade para dependências externas</span><span class="sxs-lookup"><span data-stu-id="0586d-112">Identity requirements for external dependencies</span></span>

-   <span data-ttu-id="0586d-113">Considerações sobre plataformas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0586d-113">Device platform considerations</span></span>

-   <span data-ttu-id="0586d-114">Requisitos para entrega</span><span class="sxs-lookup"><span data-stu-id="0586d-114">Requirements to be delivered</span></span>  

<span data-ttu-id="0586d-115">Vamos examinar cada uma dessas áreas mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="0586d-115">Let’s review each of these areas in more detail.</span></span> 

## <span data-ttu-id="0586d-116">Registrar o ambiente</span><span class="sxs-lookup"><span data-stu-id="0586d-116">Record your environment</span></span>
<a id="record-your-environment" class="xliff"></a>

<span data-ttu-id="0586d-117">A primeira etapa antes de criar o design é registrar o ambiente atual.</span><span class="sxs-lookup"><span data-stu-id="0586d-117">The first step before you can create your design is to record your current environment.</span></span> <span data-ttu-id="0586d-118">O ambiente atual podem influenciar as decisões de design e deve ser documentado e referenciado ao tomar outras decisões de design do Intune.</span><span class="sxs-lookup"><span data-stu-id="0586d-118">The current environment can influence design decisions and should be documented and referenced when making other Intune design decisions.</span></span> <span data-ttu-id="0586d-119">Veja abaixo alguns exemplos de como registrar o ambiente atual:</span><span class="sxs-lookup"><span data-stu-id="0586d-119">Below are few examples of how to record the current environment:</span></span>

-   <span data-ttu-id="0586d-120">**Identidade na nuvem**</span><span class="sxs-lookup"><span data-stu-id="0586d-120">**Identity in the cloud**</span></span>

    -   <span data-ttu-id="0586d-121">Você usa o DirSync ou o Azure AD (Azure Active Directory) Connect?</span><span class="sxs-lookup"><span data-stu-id="0586d-121">Do you use DirSync or Azure Active Directory (Azure AD) Connect?</span></span>

    -   <span data-ttu-id="0586d-122">Seu ambiente é Federado?</span><span class="sxs-lookup"><span data-stu-id="0586d-122">Is your environment Federated?</span></span>

    -   <span data-ttu-id="0586d-123">A autenticação multifator está habilitada?</span><span class="sxs-lookup"><span data-stu-id="0586d-123">Is multi-factor authentication enabled?</span></span>

-   <span data-ttu-id="0586d-124">**Ambiente de email**</span><span class="sxs-lookup"><span data-stu-id="0586d-124">**Email environment**</span></span>

    -   <span data-ttu-id="0586d-125">O Exchange está sendo usado? A versão local ou na nuvem?</span><span class="sxs-lookup"><span data-stu-id="0586d-125">Is Exchange being used, is it on-premises or in the cloud?</span></span>

    -   <span data-ttu-id="0586d-126">Você está no meio de um projeto de migração do Exchange para a nuvem?</span><span class="sxs-lookup"><span data-stu-id="0586d-126">Are you in the middle of a project to migrate Exchange to the cloud?</span></span>

-   <span data-ttu-id="0586d-127">**Solução atual de MDM**</span><span class="sxs-lookup"><span data-stu-id="0586d-127">**Current MDM solution**</span></span>

    -   <span data-ttu-id="0586d-128">Você está usando outras soluções de MDM?</span><span class="sxs-lookup"><span data-stu-id="0586d-128">Are you currently using other MDM solutions?</span></span>

    -   <span data-ttu-id="0586d-129">Quais soluções de MDM estão sendo usadas para os cenários de caso de uso corporativo e BYOD?</span><span class="sxs-lookup"><span data-stu-id="0586d-129">What MDM solutions are you using for corporate and BYOD use case scenarios?</span></span>

    -   <span data-ttu-id="0586d-130">Quais funcionalidades estão sendo usadas (por exemplo, configurações de dispositivo de aplicativo, configurações de Wi-Fi, etc.)?</span><span class="sxs-lookup"><span data-stu-id="0586d-130">What capabilities are you using (e.g. app device settings, Wi-Fi configurations, etc.)?</span></span>

    -   <span data-ttu-id="0586d-131">Há suporte para quais plataformas de dispositivo?</span><span class="sxs-lookup"><span data-stu-id="0586d-131">What device platforms are supported?</span></span>

    -   <span data-ttu-id="0586d-132">Quais grupos e quantos usuários estão usando a solução de MDM?</span><span class="sxs-lookup"><span data-stu-id="0586d-132">What groups and how many users are using the MDM solution?</span></span>

-   <span data-ttu-id="0586d-133">**Solução de Certificado**</span><span class="sxs-lookup"><span data-stu-id="0586d-133">**Certificate Solution**</span></span>

    -   <span data-ttu-id="0586d-134">Você implementou uma solução de certificado?</span><span class="sxs-lookup"><span data-stu-id="0586d-134">Have you implemented a certificate solution?</span></span>

    -   <span data-ttu-id="0586d-135">Quais tipo de certificados são usados?</span><span class="sxs-lookup"><span data-stu-id="0586d-135">What type of certificates do you use?</span></span>

-   <span data-ttu-id="0586d-136">**Gerenciamento de Sistemas**</span><span class="sxs-lookup"><span data-stu-id="0586d-136">**Systems Management**</span></span>

    -   <span data-ttu-id="0586d-137">Como o ambiente de computador e servidor está sendo gerenciado?</span><span class="sxs-lookup"><span data-stu-id="0586d-137">How are you managing your PC and server environment?</span></span>

    -   <span data-ttu-id="0586d-138">O System Center Configuration Manager está sendo usado?</span><span class="sxs-lookup"><span data-stu-id="0586d-138">Is System Center Configuration Manager being used?</span></span> <span data-ttu-id="0586d-139">Você está usando uma plataforma de gerenciamento do sistema de terceiros?</span><span class="sxs-lookup"><span data-stu-id="0586d-139">Are you using a third-party system management platform?</span></span>

-   <span data-ttu-id="0586d-140">**Solução de VPN**</span><span class="sxs-lookup"><span data-stu-id="0586d-140">**VPN Solution**</span></span>

    -   <span data-ttu-id="0586d-141">Qual é sua solução de VPN?</span><span class="sxs-lookup"><span data-stu-id="0586d-141">What is your VPN solution?</span></span>

    -   <span data-ttu-id="0586d-142">Ela é usada para cenários de caso de uso corporativo e BYOD?</span><span class="sxs-lookup"><span data-stu-id="0586d-142">Is it used for both corporate and BYOD use case scenarios?</span></span>

<span data-ttu-id="0586d-143">Lembre-se de observar os projetos ou outros planos em vigor para poder fazer alterações no ambiente ao registrar o ambiente atual de MDM.</span><span class="sxs-lookup"><span data-stu-id="0586d-143">Make sure to note any projects or any other plans in place to could make changes to your environment when recording the current MDM environment.</span></span> <span data-ttu-id="0586d-144">Veja abaixo um exemplo de uma maneira de registrar o ambiente atual para ajudar a criar o design do Intune:</span><span class="sxs-lookup"><span data-stu-id="0586d-144">Below is an example of a way to record the current environment to assist when creating your Intune design:</span></span>

| <span data-ttu-id="0586d-145">**Área de solução**</span><span class="sxs-lookup"><span data-stu-id="0586d-145">**Solution area**</span></span> | <span data-ttu-id="0586d-146">**Ambiente atual**</span><span class="sxs-lookup"><span data-stu-id="0586d-146">**Current environment**</span></span> | <span data-ttu-id="0586d-147">**Comentários**</span><span class="sxs-lookup"><span data-stu-id="0586d-147">**Comments**</span></span> |
|:---:|:---:|:---:|
| <span data-ttu-id="0586d-148">**Identidade**</span><span class="sxs-lookup"><span data-stu-id="0586d-148">**Identity**</span></span> | <span data-ttu-id="0586d-149">Azure AD, Azure AD Connect, não federado, sem MFA</span><span class="sxs-lookup"><span data-stu-id="0586d-149">Azure AD, Azure AD Connect, not federated, no MFA</span></span> | <span data-ttu-id="0586d-150">Projeto em vigor para habilitar o MFA até o final do ano</span><span class="sxs-lookup"><span data-stu-id="0586d-150">Project in place to enable MFA by end of year</span></span> |                 
| <span data-ttu-id="0586d-151">**Ambiente de email**</span><span class="sxs-lookup"><span data-stu-id="0586d-151">**Email environment**</span></span> | <span data-ttu-id="0586d-152">Exchange no Local, Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0586d-152">Exchange on-premises, Exchange online</span></span> | <span data-ttu-id="0586d-153">Atualmente migrando do Exchange no Local para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0586d-153">Currently migrating from Exchange on-premises to Exchange online.</span></span> <span data-ttu-id="0586d-154">75% de caixas de correio migradas.</span><span class="sxs-lookup"><span data-stu-id="0586d-154">75% of mailboxes migrated.</span></span> <span data-ttu-id="0586d-155">Os últimos 25% serão migrados antes do início do Piloto do Intune.</span><span class="sxs-lookup"><span data-stu-id="0586d-155">Last 25% will be migrated before Intune Pilot begins.</span></span> |                
| <span data-ttu-id="0586d-156">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="0586d-156">**SharePoint**</span></span> | <span data-ttu-id="0586d-157">SharePoint local</span><span class="sxs-lookup"><span data-stu-id="0586d-157">SharePoint on-premises</span></span> | <span data-ttu-id="0586d-158">Não há planos de migração para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0586d-158">No plans to move to SharePoint online</span></span> |  
| <span data-ttu-id="0586d-159">**MDM atual**</span><span class="sxs-lookup"><span data-stu-id="0586d-159">**Current MDM**</span></span> | <span data-ttu-id="0586d-160">Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="0586d-160">Exchange ActiveSync</span></span> |  |
| <span data-ttu-id="0586d-161">**Solução de certificado**</span><span class="sxs-lookup"><span data-stu-id="0586d-161">**Certificate solution**</span></span> | <span data-ttu-id="0586d-162">Microsoft Server 2012 R2, Serviços de Certificados do AD</span><span class="sxs-lookup"><span data-stu-id="0586d-162">Microsoft Server 2012 R2, AD Certificate Services</span></span> | <span data-ttu-id="0586d-163">Usar somente o PKI para Servidores de Site</span><span class="sxs-lookup"><span data-stu-id="0586d-163">Only use PKI for Web Site Servers</span></span> |
| <span data-ttu-id="0586d-164">**Gerenciamento do Sistema**</span><span class="sxs-lookup"><span data-stu-id="0586d-164">**System Management**</span></span> | <span data-ttu-id="0586d-165">System Center Configuration Manager CB 1606</span><span class="sxs-lookup"><span data-stu-id="0586d-165">System Center Configuration Manager CB 1606</span></span> | <span data-ttu-id="0586d-166">Gostaria de investigar a solução híbrida do Intune?</span><span class="sxs-lookup"><span data-stu-id="0586d-166">Would like to investigate Intune hybrid solution</span></span> |
| <span data-ttu-id="0586d-167">**Solução de VPN**</span><span class="sxs-lookup"><span data-stu-id="0586d-167">**VPN solution**</span></span> | <span data-ttu-id="0586d-168">Cisco AnyConnect</span><span class="sxs-lookup"><span data-stu-id="0586d-168">Cisco AnyConnect</span></span> |  |

## <span data-ttu-id="0586d-169">Escolher uma opção de implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="0586d-169">Choose an Intune deployment option</span></span>
<a id="choose-an-intune-deployment-option" class="xliff"></a>

<span data-ttu-id="0586d-170">O Intune oferece duas opções de implantação: independente e híbrida.</span><span class="sxs-lookup"><span data-stu-id="0586d-170">Intune offers two deployment options: standalone and hybrid.</span></span> <span data-ttu-id="0586d-171">Decida qual delas atende aos seus requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="0586d-171">Decide which one fits your business requirements.</span></span> <span data-ttu-id="0586d-172">Independente refere-se ao serviço Intune em execução na nuvem, enquanto híbrido refere-se à integração do Intune com o System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="0586d-172">Standalone refers to Intune service running in the cloud, hybrid refers to the integration of Intune with System Center Configuration Manager.</span></span>

- <span data-ttu-id="0586d-173">Saiba mais sobre como [escolher entre o gerenciamento de dispositivo móvel independente e híbrido do Microsoft Intune com o System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)</span><span class="sxs-lookup"><span data-stu-id="0586d-173">Learn more about [choosing between Microsoft Intune standalone and hybrid mobile device management with System Center Configuration Manager](https://docs.microsoft.com/sccm/mdm/understand/choose-between-standalone-intune-and-hybrid-mobile-device-management)</span></span>

## <span data-ttu-id="0586d-174">Local do locatário do Intune</span><span class="sxs-lookup"><span data-stu-id="0586d-174">Intune tenant location</span></span>
<a id="intune-tenant-location" class="xliff"></a>

<span data-ttu-id="0586d-175">Caso sua organização tenha uma presença global, lembre-se de planejar o local em que o locatário reside ao assinar o serviço.</span><span class="sxs-lookup"><span data-stu-id="0586d-175">If your organization has global presence, make sure to plan where your tenant resides when subscribing to the service.</span></span> <span data-ttu-id="0586d-176">O país é definido durante a inscrição para uma assinatura do Intune pela primeira vez e é mapeado para as regiões do mundo listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="0586d-176">The country is defined when you sign up for an Intune subscription for the first time, and map to regions around the world which are listed below:</span></span>

-   <span data-ttu-id="0586d-177">América do Norte</span><span class="sxs-lookup"><span data-stu-id="0586d-177">North America</span></span>

-   <span data-ttu-id="0586d-178">Europa, Oriente Médio e África</span><span class="sxs-lookup"><span data-stu-id="0586d-178">Europe, Middle East, and Africa</span></span>

-   <span data-ttu-id="0586d-179">Ásia e Pacífico</span><span class="sxs-lookup"><span data-stu-id="0586d-179">Asia and Pacific</span></span>

>[!IMPORTANT]
> <span data-ttu-id="0586d-180">Não é possível alterar o local do país e do locatário posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0586d-180">It’s not possible to change the country and tenant location later.</span></span>

## <span data-ttu-id="0586d-181">Dependências externas</span><span class="sxs-lookup"><span data-stu-id="0586d-181">External dependencies</span></span>
<a id="external-dependencies" class="xliff"></a>

<span data-ttu-id="0586d-182">Dependências externas são serviços e produtos separados do Intune, mas que são um requisito do Intune ou que podem ser integradas com o Intune.</span><span class="sxs-lookup"><span data-stu-id="0586d-182">External dependencies are services and products that are separate from Intune, but are either a requirement of Intune, or might integrate with Intune.</span></span> <span data-ttu-id="0586d-183">É importante identificar os requisitos para dependências externas e como elas serão configuradas.</span><span class="sxs-lookup"><span data-stu-id="0586d-183">It’s important to identify requirements for any external dependencies and how it is to be configured.</span></span> <span data-ttu-id="0586d-184">Veja abaixo uma lista de alguns exemplos de dependências externas comuns.</span><span class="sxs-lookup"><span data-stu-id="0586d-184">Some examples of common external dependencies are listed below.</span></span>

-   <span data-ttu-id="0586d-185">Identidade</span><span class="sxs-lookup"><span data-stu-id="0586d-185">Identity</span></span>

-   <span data-ttu-id="0586d-186">Grupos de usuários e de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0586d-186">User and device groups</span></span>

-   <span data-ttu-id="0586d-187">PKI</span><span class="sxs-lookup"><span data-stu-id="0586d-187">PKI</span></span>

<span data-ttu-id="0586d-188">Vamos explorar mais detalhadamente essas dependências externas comuns abaixo</span><span class="sxs-lookup"><span data-stu-id="0586d-188">Let’s explore in more detail these common external dependencies below</span></span>

### <span data-ttu-id="0586d-189">Identidade</span><span class="sxs-lookup"><span data-stu-id="0586d-189">Identity</span></span>
<a id="identity" class="xliff"></a>

<span data-ttu-id="0586d-190">Identidade é como identificamos nossos usuários que estão abaixo de sua organização e que estão registrando um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0586d-190">Identity is how we identify the users who belong to your organization and are enrolling a device.</span></span> <span data-ttu-id="0586d-191">O Intune exige o Azure AD (Azure Active Directory) como o provedor de identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="0586d-191">Intune requires Azure Active Directory (Azure AD) as the user identity provider.</span></span> <span data-ttu-id="0586d-192">Se você já usa esse serviço, pode aproveitar sua identidade já existente na nuvem.</span><span class="sxs-lookup"><span data-stu-id="0586d-192">If you already use this service, you’ll be able to leverage your existing identity already in the cloud.</span></span> <span data-ttu-id="0586d-193">Além disso, o Azure AD Connect é a ferramenta recomendada para sincronizar as identidades de usuários locais com os serviços em nuvem da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0586d-193">In addition, Azure AD Connect is the recommended tool to synchronize your on-premises user identities with Microsoft cloud services.</span></span> <span data-ttu-id="0586d-194">Caso sua organização já esteja usando o Office 365, é importante que o Intune use o mesmo ambiente do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0586d-194">If your organization is already using Office 365, it’s important that Intune uses the same Azure Active Directory environment.</span></span>

<span data-ttu-id="0586d-195">Encontre mais informações sobre os requisitos de identidade do Intune abaixo.</span><span class="sxs-lookup"><span data-stu-id="0586d-195">You can find more information regarding Intune’s identity requirements below.</span></span>

-   <span data-ttu-id="0586d-196">Saiba mais sobre os [requisitos de identidade](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).</span><span class="sxs-lookup"><span data-stu-id="0586d-196">Learn more about [identity requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).</span></span>

-   <span data-ttu-id="0586d-197">Saiba mais sobre os [requisitos de sincronização de diretório](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).</span><span class="sxs-lookup"><span data-stu-id="0586d-197">Learn more about [directory synchronization requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).</span></span>

-   <span data-ttu-id="0586d-198">Saiba mais sobre os [requisitos de autenticação multifator](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).</span><span class="sxs-lookup"><span data-stu-id="0586d-198">Learn more about [multi-factor authentication requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).</span></span>

### <span data-ttu-id="0586d-199">Grupos de usuários e de dispositivos</span><span class="sxs-lookup"><span data-stu-id="0586d-199">User and device groups</span></span>
<a id="user-and-device-groups" class="xliff"></a>

<span data-ttu-id="0586d-200">Os grupos de usuários e de dispositivos determinam o destino de uma implantação.</span><span class="sxs-lookup"><span data-stu-id="0586d-200">User and device groups determines the target of a deployment.</span></span> <span data-ttu-id="0586d-201">Isso pode incluir uma implantação que tem políticas, aplicativos e perfis como destino.</span><span class="sxs-lookup"><span data-stu-id="0586d-201">This could include deployment targeting for policies, applications, and profiles.</span></span> <span data-ttu-id="0586d-202">O serviço de nuvem do Intune dá suporte apenas a grupos de usuários e de dispositivos. Você precisará determinar quais grupos de usuários e de dispositivos serão necessários.</span><span class="sxs-lookup"><span data-stu-id="0586d-202">Intune cloud-only supports user and device groups – you’ll need to determine what user and device groups will be required.</span></span> <span data-ttu-id="0586d-203">É recomendável criar todos os grupos no Active Directory local e sincronizá-los com o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0586d-203">It’s recommended that all groups are created in the on-premises Active Directory, then synchronized to Azure Active Directory.</span></span> <span data-ttu-id="0586d-204">Encontre mais informações sobre o planejamento e a criação de grupos de usuários e de dispositivos abaixo.</span><span class="sxs-lookup"><span data-stu-id="0586d-204">You can find more information about user and device group planning and creation below.</span></span>

-   <span data-ttu-id="0586d-205">Saiba mais sobre como [planejar os grupos de usuários e de dispositivos](/intune-classic/deploy-use/plan-your-user-and-device-groups).</span><span class="sxs-lookup"><span data-stu-id="0586d-205">Learn more about [planning your user and device groups](/intune-classic/deploy-use/plan-your-user-and-device-groups).</span></span>

-   <span data-ttu-id="0586d-206">Saiba [como criar grupos de usuários e de dispositivos](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-206">Learn [how to create user and device groups](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>

### <span data-ttu-id="0586d-207">PKI (Infraestrutura de Chave Pública)</span><span class="sxs-lookup"><span data-stu-id="0586d-207">Public Key Infrastructure (PKI)</span></span>
<a id="public-key-infrastructure-pki" class="xliff"></a>

<span data-ttu-id="0586d-208">A Infraestrutura de Chave Pública fornece certificados para dispositivos ou usuários para uma autenticação segura em um serviço.</span><span class="sxs-lookup"><span data-stu-id="0586d-208">Public Key Infrastructure supplies certificates to devices or users to securely authenticate to a service.</span></span> <span data-ttu-id="0586d-209">O Intune dá suporte a uma infraestrutura de PKI da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0586d-209">Intune supports a Microsoft PKI infrastructure.</span></span> <span data-ttu-id="0586d-210">Certificados de usuários e de dispositivos podem ser emitidos para um dispositivo móvel, a fim de atender aos requisitos da autenticação baseada em certificado.</span><span class="sxs-lookup"><span data-stu-id="0586d-210">Device and user certificates can be issued to a mobile device to satisfy certificate based authentication requirements.</span></span> <span data-ttu-id="0586d-211">Antes de implementar certificados, você precisa determinar se os certificados são necessários, se a infraestrutura de rede pode dar suporte à autenticação baseada em certificado e se os certificados são atualmente usados no ambiente existente.</span><span class="sxs-lookup"><span data-stu-id="0586d-211">Before implementing certificates, you need to determine if certificates are needed, whether the network infrastructure can support certificate based authentication, and whether certificates are currently used in the existing environment.</span></span>

<span data-ttu-id="0586d-212">Se você estiver planejando usar certificados com perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles) com suporte, pronta para criar e implantar perfis de certificado.</span><span class="sxs-lookup"><span data-stu-id="0586d-212">If you're planning to use certificates with VPN, Wi-Fi, or e-mail profiles with Intune, you need to make sure you have a supported [PKI infrastructure in place](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles), ready to create and deploy certificate profiles.</span></span>

<span data-ttu-id="0586d-213">Além disso, se certificados SCEP forem emitidos, você precisará determinar qual servidor hospedará o recurso NDES (Serviço de Registro de Dispositivo de Rede) e como ocorrerá a comunicação.</span><span class="sxs-lookup"><span data-stu-id="0586d-213">In addition, If SCEP certificates will be issued, you need to determine which server will host the Network Device Enrollment Service (NDES) feature, and how the communication will happen.</span></span>

<span data-ttu-id="0586d-214">Mais informações sobre como configurar certificados no Intune:</span><span class="sxs-lookup"><span data-stu-id="0586d-214">More information about configuring certificates in Intune:</span></span>

-   <span data-ttu-id="0586d-215">[Configurar a infraestrutura de certificado para SCEP](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep).</span><span class="sxs-lookup"><span data-stu-id="0586d-215">[How to configure the certificate infrastructure for SCEP](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep).</span></span>

-   <span data-ttu-id="0586d-216">[Configurar a infraestrutura de certificado](/intune-classic/deploy-use/configure-certificate-infrastructure-for-pfx).</span><span class="sxs-lookup"><span data-stu-id="0586d-216">[How to configure the certificate infrastructure for PFX](/intune-classic/deploy-use/configure-certificate-infrastructure-for-pfx).</span></span>

-   <span data-ttu-id="0586d-217">[Configurar perfis de certificado do Intune](/intune-classic/deploy-use/configure-intune-certificate-profiles).</span><span class="sxs-lookup"><span data-stu-id="0586d-217">[How to configure Intune certificate profiles](/intune-classic/deploy-use/configure-intune-certificate-profiles).</span></span>

-   <span data-ttu-id="0586d-218">[Como configurar políticas de acesso a recursos](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-218">[How to configure resource access policies](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).</span></span>

## <span data-ttu-id="0586d-219">Considerações sobre plataformas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0586d-219">Device Platform Considerations</span></span>
<a id="device-platform-considerations" class="xliff"></a>

<span data-ttu-id="0586d-220">É necessário examinar os dispositivos atentamente para entender como configurá-los corretamente.</span><span class="sxs-lookup"><span data-stu-id="0586d-220">You need to take a closer look at your devices to understand how them correctly.</span></span>

-   <span data-ttu-id="0586d-221">Determinar as plataformas de dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="0586d-221">Determine supported device platforms</span></span>

-   <span data-ttu-id="0586d-222">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="0586d-222">Devices</span></span>

-   <span data-ttu-id="0586d-223">Propriedade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="0586d-223">Device ownership</span></span>

-   <span data-ttu-id="0586d-224">Registro em massa</span><span class="sxs-lookup"><span data-stu-id="0586d-224">Bulk enrollment</span></span>

<span data-ttu-id="0586d-225">Vamos examinar essas áreas mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="0586d-225">Let’s review these areas in more detail.</span></span>

### <span data-ttu-id="0586d-226">Determinar as plataformas de dispositivo com suporte</span><span class="sxs-lookup"><span data-stu-id="0586d-226">Determine supported device platforms</span></span>
<a id="determine-supported-device-platforms" class="xliff"></a>

<span data-ttu-id="0586d-227">Você precisa saber quais dispositivos estarão no ambiente e verificar se eles têm suporte ou não no Intune ao criar o projeto.</span><span class="sxs-lookup"><span data-stu-id="0586d-227">You need to know what devices will be in the environment and verify whether they are supported or not by Intune when creating your design.</span></span> <span data-ttu-id="0586d-228">O Intune dá suporte às plataformas iOS, Android e Windows.</span><span class="sxs-lookup"><span data-stu-id="0586d-228">Intune supports iOS, Android, and Windows platforms.</span></span>

-   <span data-ttu-id="0586d-229">Saiba mais sobre os [Dispositivos com suporte no Intune](/intune-classic/get-started/supported-mobile-devices-and-computers).</span><span class="sxs-lookup"><span data-stu-id="0586d-229">Learn more about [Intune Supported Devices](/intune-classic/get-started/supported-mobile-devices-and-computers).</span></span>

### <span data-ttu-id="0586d-230">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="0586d-230">Devices</span></span>
<a id="devices" class="xliff"></a>

<span data-ttu-id="0586d-231">O Intune gerencia dispositivos móveis para proteger dados corporativos e permitir que os usuários finais trabalhem em mais locais.</span><span class="sxs-lookup"><span data-stu-id="0586d-231">Intune manages mobile devices to secure corporate data and allow end users to work from more locations.</span></span> <span data-ttu-id="0586d-232">O Intune dá suporte a várias plataformas de dispositivo; portanto é recomendável documentar os dispositivos e as plataformas do sistema operacional que terão suporte no design de sua organização.</span><span class="sxs-lookup"><span data-stu-id="0586d-232">Intune supports multiple device platforms, so it’s recommended to document the devices and the OS platforms that will be supported in your organization’s design.</span></span> <span data-ttu-id="0586d-233">Isso será expandido para os dispositivos e para as plataformas criadas na seção (requisitos de caso de uso).</span><span class="sxs-lookup"><span data-stu-id="0586d-233">This will expand on the devices and platforms created in section (use case requirements).</span></span>

<span data-ttu-id="0586d-234">Também recomendamos saber as versões para fazer referência à lista durante a verificação de funcionalidades do dispositivo por versão e plataforma do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0586d-234">It’s also recommended to know the versions to reference the list when checking for device capabilities by OS platform and version.</span></span> <span data-ttu-id="0586d-235">Aqui está um exemplo:</span><span class="sxs-lookup"><span data-stu-id="0586d-235">Here’s an example:</span></span>

| <span data-ttu-id="0586d-236">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-236">**Device platform**</span></span> | <span data-ttu-id="0586d-237">**Versões do sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="0586d-237">**OS Versions**</span></span> |
|:---:|:---:|
| <span data-ttu-id="0586d-238">iOS – iPhone</span><span class="sxs-lookup"><span data-stu-id="0586d-238">iOS - iPhone</span></span> | <span data-ttu-id="0586d-239">9.0+</span><span class="sxs-lookup"><span data-stu-id="0586d-239">9.0+</span></span> |                
| <span data-ttu-id="0586d-240">iOS – iPad</span><span class="sxs-lookup"><span data-stu-id="0586d-240">iOS - iPad</span></span> | <span data-ttu-id="0586d-241">8.0+</span><span class="sxs-lookup"><span data-stu-id="0586d-241">8.0+</span></span> |               
| <span data-ttu-id="0586d-242">Android – Samsung Knox Standard</span><span class="sxs-lookup"><span data-stu-id="0586d-242">Android – Samsung Knox Standard</span></span> | <span data-ttu-id="0586d-243">4.0+</span><span class="sxs-lookup"><span data-stu-id="0586d-243">4.0+</span></span> |
| <span data-ttu-id="0586d-244">Tablet Windows 10</span><span class="sxs-lookup"><span data-stu-id="0586d-244">Windows 10 tablet</span></span> | <span data-ttu-id="0586d-245">10+</span><span class="sxs-lookup"><span data-stu-id="0586d-245">10+</span></span> |

### <span data-ttu-id="0586d-246">Propriedade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="0586d-246">Device ownership</span></span>
<a id="device-ownership" class="xliff"></a>

<span data-ttu-id="0586d-247">O Intune dá suporte à propriedade corporativa e à propriedade BYOD.</span><span class="sxs-lookup"><span data-stu-id="0586d-247">Intune supports both corporate owned and BYOD ownership.</span></span> <span data-ttu-id="0586d-248">Um dispositivo será considerado de propriedade corporativa se for registrado por um gerenciador de registro do dispositivo ou pelo programa de registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0586d-248">A Device is considered corporate owned if enrolled by a device enrollment manager, or device enrollment program.</span></span> <span data-ttu-id="0586d-249">Como exemplo, um dispositivo pode ser registrado por meio do Apple DEP, marcado como corporativo e colocado em um grupo de dispositivos que recebe políticas e aplicativos corporativos de destino.</span><span class="sxs-lookup"><span data-stu-id="0586d-249">As an example, a device could be enrolled via Apple DEP, marked as corporate, and placed in a device group that receives targeted corporate policies and apps.</span></span>

<span data-ttu-id="0586d-250">Consulte a [Seção 3: Determinar os requisitos de cenários de caso de uso](planning-guide-requirements.md) para obter mais informações sobre casos de uso Corporativo e BYOD.</span><span class="sxs-lookup"><span data-stu-id="0586d-250">Refer to [Section 3: Determine use case scenario requirements](planning-guide-requirements.md) for more information about Corporate and BYOD use cases.</span></span>

### <span data-ttu-id="0586d-251">Registro em massa</span><span class="sxs-lookup"><span data-stu-id="0586d-251">Bulk enrollment</span></span>
<a id="bulk-enrollment" class="xliff"></a>

<span data-ttu-id="0586d-252">Há várias opções de registro disponíveis para registrar um dispositivo no Intune, a fim de complementar o registro por autoatendimento por meio do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="0586d-252">There are multiple enrollment options available for enrolling a device in Intune to complement the self-service enrollment through the company portal.</span></span> <span data-ttu-id="0586d-253">O registro em massa pode ser realizado de diferentes maneiras conforme a plataforma.</span><span class="sxs-lookup"><span data-stu-id="0586d-253">Bulk enrollment can be accomplished different ways depending on the platform.</span></span> <span data-ttu-id="0586d-254">Se o registro em massa for necessário, primeiro determine o método de registro em massa e incorpore-o no design.</span><span class="sxs-lookup"><span data-stu-id="0586d-254">If bulk enrollment will be required, first determine the bulk enrollment method and incorporate in to your design.</span></span> <span data-ttu-id="0586d-255">Obtenha mais informações sobre os diferentes métodos de registro em massa abaixo.</span><span class="sxs-lookup"><span data-stu-id="0586d-255">Find more information about different methods of bulk enrollment below.</span></span>

-   <span data-ttu-id="0586d-256">Saiba mais sobre o [registro em massa](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-256">Learn about more [bulk enrollment](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).</span></span>

## <span data-ttu-id="0586d-257">Requisitos de recursos</span><span class="sxs-lookup"><span data-stu-id="0586d-257">Feature requirements</span></span>
<a id="feature-requirements" class="xliff"></a>

<span data-ttu-id="0586d-258">Nesta seção, examinaremos os seguintes recursos e funcionalidades que estão alinhados aos requisitos de cenários de caso de uso:</span><span class="sxs-lookup"><span data-stu-id="0586d-258">In these sections, we’ll review the following features and capabilities that are aligned with your use case scenario requirements:</span></span>

-   <span data-ttu-id="0586d-259">Políticas de Termos e Condições</span><span class="sxs-lookup"><span data-stu-id="0586d-259">Terms and Conditions Policies</span></span>

-   <span data-ttu-id="0586d-260">Políticas de configuração</span><span class="sxs-lookup"><span data-stu-id="0586d-260">Configuration Policies</span></span>

-   <span data-ttu-id="0586d-261">Perfis de Recursos</span><span class="sxs-lookup"><span data-stu-id="0586d-261">Resource Profiles</span></span>

-   <span data-ttu-id="0586d-262">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="0586d-262">Apps</span></span>

-   <span data-ttu-id="0586d-263">Política de Conformidade</span><span class="sxs-lookup"><span data-stu-id="0586d-263">Compliance Policy</span></span>

-   <span data-ttu-id="0586d-264">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="0586d-264">Conditional Access</span></span>

<span data-ttu-id="0586d-265">Vamos examinar cada uma dessas áreas mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="0586d-265">Let’s review each of these areas in more detail.</span></span>

### <span data-ttu-id="0586d-266">Políticas de Termos e Condições</span><span class="sxs-lookup"><span data-stu-id="0586d-266">Terms and Conditions policies</span></span>
<a id="terms-and-conditions-policies" class="xliff"></a>

<span data-ttu-id="0586d-267">Termos e Condições podem ser usados para explicar as políticas ou condições que um usuário final deverá aceitar antes do registro.</span><span class="sxs-lookup"><span data-stu-id="0586d-267">Terms and Conditions can be used to explain policies or conditions that an end user must accept before enrollment.</span></span> <span data-ttu-id="0586d-268">O Intune dá suporte à capacidade de adicionar e implantar várias políticas de termos e condições em grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="0586d-268">Intune supports the ability to add and deploy multiple terms and conditions policies to user groups.</span></span> <span data-ttu-id="0586d-269">Você precisa determinar se as políticas de termos e condições são necessárias.</span><span class="sxs-lookup"><span data-stu-id="0586d-269">You need to determine if terms and condition policies are needed.</span></span> <span data-ttu-id="0586d-270">Nesse caso, quem será responsável por fornecer essas informações na organização?</span><span class="sxs-lookup"><span data-stu-id="0586d-270">If so, who will be responsible for providing this information in the organization.</span></span>

-   <span data-ttu-id="0586d-271">Saiba [como criar políticas de termos e condições](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) no Intune.</span><span class="sxs-lookup"><span data-stu-id="0586d-271">Learn [how to create term and condition policies](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune) on Intune.</span></span> <span data-ttu-id="0586d-272">Veja abaixo um exemplo de como documentar a política de termos e condições.</span><span class="sxs-lookup"><span data-stu-id="0586d-272">An example of how to document the terms and conditions policy is below.</span></span>

| <span data-ttu-id="0586d-273">**Nome de Termos e Condições**</span><span class="sxs-lookup"><span data-stu-id="0586d-273">**Terms and Conditions name**</span></span> | <span data-ttu-id="0586d-274">**Caso de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-274">**Use case**</span></span> | <span data-ttu-id="0586d-275">**Grupo de destino**</span><span class="sxs-lookup"><span data-stu-id="0586d-275">**Targeted group**</span></span> |
|:---:|:---:|:---:|
| <span data-ttu-id="0586d-276">Termos e Condições corporativos</span><span class="sxs-lookup"><span data-stu-id="0586d-276">Corporate T&C</span></span> | <span data-ttu-id="0586d-277">Corporativo</span><span class="sxs-lookup"><span data-stu-id="0586d-277">Corporate</span></span> | <span data-ttu-id="0586d-278">Usuários corporativos</span><span class="sxs-lookup"><span data-stu-id="0586d-278">Corporate users</span></span> |                 
| <span data-ttu-id="0586d-279">Termos e Condições da política BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-279">BYOD T&C</span></span> | <span data-ttu-id="0586d-280">BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-280">BYOD</span></span> | <span data-ttu-id="0586d-281">Usuários BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-281">BYOD users</span></span> |                

### <span data-ttu-id="0586d-282">Políticas de configuração</span><span class="sxs-lookup"><span data-stu-id="0586d-282">Configuration policies</span></span>
<a id="configuration-policies" class="xliff"></a>

<span data-ttu-id="0586d-283">As políticas de configuração são usadas para gerenciar as configurações e os recursos de segurança em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0586d-283">Configuration policies are used to manage security settings and features on a device.</span></span> <span data-ttu-id="0586d-284">Ao criar as políticas de configuração, consulte a seção sobre requisitos de caso de uso para determinar as configurações necessárias para os dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="0586d-284">When designing your configuration policies, refer to the use case requirements section to determine the configurations required for Intune devices.</span></span> <span data-ttu-id="0586d-285">Documente quais configurações e como elas devem ser definidas, bem como qual usuário ou quais grupos de dispositivos serão afetados.</span><span class="sxs-lookup"><span data-stu-id="0586d-285">Document which settings, and how they should be configured, also document which user, or device groups they will be targeted to.</span></span>

<span data-ttu-id="0586d-286">É necessário criar, pelo menos, uma Política de Configuração por plataforma.</span><span class="sxs-lookup"><span data-stu-id="0586d-286">You should create at least one Configuration Policy per platform.</span></span> <span data-ttu-id="0586d-287">Se necessário, é possível criar várias Políticas de Configuração por plataforma.</span><span class="sxs-lookup"><span data-stu-id="0586d-287">You can create multiple Configuration Policies per platform if needed.</span></span> <span data-ttu-id="0586d-288">Veja abaixo um exemplo de como criar quatro políticas de configuração diferentes para diferentes plataformas e cenários de caso de uso.</span><span class="sxs-lookup"><span data-stu-id="0586d-288">Below is an example of designing four different configuration policies for different platforms and use case scenarios.</span></span>

| <span data-ttu-id="0586d-289">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="0586d-289">**Policy name**</span></span> | <span data-ttu-id="0586d-290">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-290">**Device platform**</span></span> | <span data-ttu-id="0586d-291">**Configurações**</span><span class="sxs-lookup"><span data-stu-id="0586d-291">**Settings**</span></span> | <span data-ttu-id="0586d-292">**Grupo de destino**</span><span class="sxs-lookup"><span data-stu-id="0586d-292">**Target group**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-293">Corporativo – iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-293">Corporate - iOS</span></span> | <span data-ttu-id="0586d-294">iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-294">iOS</span></span> | <span data-ttu-id="0586d-295">PIN obrigatório; tamanho: 6; restringir o backup na nuvem</span><span class="sxs-lookup"><span data-stu-id="0586d-295">PIN is required, Length: 6, Restrict Cloud Backup</span></span> | <span data-ttu-id="0586d-296">Dispositivos Corporativos</span><span class="sxs-lookup"><span data-stu-id="0586d-296">Corporate Devices</span></span> |                                                           
| <span data-ttu-id="0586d-297">Corporativo – Android</span><span class="sxs-lookup"><span data-stu-id="0586d-297">Corporate - Android</span></span> | <span data-ttu-id="0586d-298">Android</span><span class="sxs-lookup"><span data-stu-id="0586d-298">Android</span></span> | <span data-ttu-id="0586d-299">PIN obrigatório; tamanho: 6; restringir o backup na nuvem</span><span class="sxs-lookup"><span data-stu-id="0586d-299">PIN is required, Length: 6, Restrict Cloud Backup</span></span> | <span data-ttu-id="0586d-300">Dispositivos Corporativos</span><span class="sxs-lookup"><span data-stu-id="0586d-300">Corporate Devices</span></span> |                                                           
| <span data-ttu-id="0586d-301">BYOD – iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-301">BYOD – iOS</span></span>  | <span data-ttu-id="0586d-302">iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-302">iOS</span></span> | <span data-ttu-id="0586d-303">PIN obrigatório; tamanho: 4</span><span class="sxs-lookup"><span data-stu-id="0586d-303">PIN is required, Length: 4</span></span> | <span data-ttu-id="0586d-304">Dispositivos BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-304">BYOD devices</span></span> |
| <span data-ttu-id="0586d-305">BYOD – Android</span><span class="sxs-lookup"><span data-stu-id="0586d-305">BYOD – Android</span></span>  | <span data-ttu-id="0586d-306">Android</span><span class="sxs-lookup"><span data-stu-id="0586d-306">Android</span></span> | <span data-ttu-id="0586d-307">PIN obrigatório; tamanho: 4</span><span class="sxs-lookup"><span data-stu-id="0586d-307">PIN is required, Length: 4</span></span> | <span data-ttu-id="0586d-308">Dispositivos BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-308">BYOD devices</span></span> |

### <span data-ttu-id="0586d-309">Perfis</span><span class="sxs-lookup"><span data-stu-id="0586d-309">Profiles</span></span>
<a id="profiles" class="xliff"></a>

<span data-ttu-id="0586d-310">Perfis são usados para ajudar o usuário final a se conectar aos dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="0586d-310">Profiles are used to help the end user connect to company data.</span></span> <span data-ttu-id="0586d-311">O Intune dá suporte a vários tipos de perfis.</span><span class="sxs-lookup"><span data-stu-id="0586d-311">Intune supports many types of profiles.</span></span> <span data-ttu-id="0586d-312">Consulte os casos de uso e os requisitos para determinar quando os [perfis](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune) serão configurados.</span><span class="sxs-lookup"><span data-stu-id="0586d-312">Refer to the use cases and requirements to determine when the [profiles](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune) will be configured.</span></span> <span data-ttu-id="0586d-313">Todos os perfis de dispositivo são categorizados por tipo de plataforma e devem ser incluídos na documentação do design.</span><span class="sxs-lookup"><span data-stu-id="0586d-313">All device profiles are categorized per platform type, and should be included in the design documentation.</span></span>

-   <span data-ttu-id="0586d-314">Perfis de certificado</span><span class="sxs-lookup"><span data-stu-id="0586d-314">Certificate profiles</span></span>

-   <span data-ttu-id="0586d-315">Perfil de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0586d-315">Wi-Fi profile</span></span>

-   <span data-ttu-id="0586d-316">Perfil da VPN</span><span class="sxs-lookup"><span data-stu-id="0586d-316">VPN profile</span></span>

-   <span data-ttu-id="0586d-317">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="0586d-317">Email profile</span></span>

<span data-ttu-id="0586d-318">Vamos examinar cada tipo de perfil mais detalhadamente.</span><span class="sxs-lookup"><span data-stu-id="0586d-318">Let’s review each type of profile in more detail.</span></span>

##### <span data-ttu-id="0586d-319">Perfis de certificado</span><span class="sxs-lookup"><span data-stu-id="0586d-319">Certificate profiles</span></span>
<a id="certificate-profiles" class="xliff"></a>

<span data-ttu-id="0586d-320">Os perfis de certificado permitem que o Intune emita um certificado para um usuário ou dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0586d-320">Certificate profiles allow Intune to issue a certificate to a user or device.</span></span> <span data-ttu-id="0586d-321">O Intune dá suporte ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="0586d-321">Intune supports the following:</span></span>

-   <span data-ttu-id="0586d-322">Protocolo SCEP</span><span class="sxs-lookup"><span data-stu-id="0586d-322">Simple Certificate Enrollment Protocol (SCEP)</span></span>

-   <span data-ttu-id="0586d-323">Certificado Raiz Confiável</span><span class="sxs-lookup"><span data-stu-id="0586d-323">Trusted Root Certificate</span></span>

-   <span data-ttu-id="0586d-324">Certificado PFX.</span><span class="sxs-lookup"><span data-stu-id="0586d-324">PFX certificate.</span></span>

<span data-ttu-id="0586d-325">É recomendável documentar qual grupo de usuários precisa de um certificado, quantos perfis de certificado serão necessários e em quais grupos de usuários eles serão implantados.</span><span class="sxs-lookup"><span data-stu-id="0586d-325">It’s recommended to document which user group needs a certificate, how many certificate profiles will be needed, and which user groups to deploy them to.</span></span>

>[!NOTE]
> <span data-ttu-id="0586d-326">Lembre-se de que o certificado raiz confiável é necessário para o certificado SCEP; portanto, garanta que todos os usuários de destino para o certificado SCEP também recebem um certificado raiz confiável.</span><span class="sxs-lookup"><span data-stu-id="0586d-326">Remember that the trusted root certificate is required for the SCEP certificate, so make sure all users targeted for the SCEP certificate also receive a trusted root certificate.</span></span> <span data-ttu-id="0586d-327">Se forem necessários certificados SCEP, projete e documente quais modelos de certificado SCEP serão necessários.</span><span class="sxs-lookup"><span data-stu-id="0586d-327">If SCEP certificates are needed, design and document what SCEP certificate templates will be needed.</span></span>

<span data-ttu-id="0586d-328">Este é um exemplo de como é possível documentar os certificados durante o design:</span><span class="sxs-lookup"><span data-stu-id="0586d-328">Here’s an example how you can document the certificates during the design:</span></span>

| <span data-ttu-id="0586d-329">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0586d-329">**Type**</span></span> | <span data-ttu-id="0586d-330">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="0586d-330">**Profile name**</span></span> | <span data-ttu-id="0586d-331">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-331">**Device platform**</span></span> | <span data-ttu-id="0586d-332">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-332">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-333">AC Raiz</span><span class="sxs-lookup"><span data-stu-id="0586d-333">Root CA</span></span> | <span data-ttu-id="0586d-334">AC Raiz Corporativa</span><span class="sxs-lookup"><span data-stu-id="0586d-334">Corporate Root CA</span></span> | <span data-ttu-id="0586d-335">Android, iOS, Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-335">Android, iOS, Windows mobile</span></span> | <span data-ttu-id="0586d-336">Corporativo, BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-336">Corporate, BYOD</span></span>  |                                                           
| <span data-ttu-id="0586d-337">SCEP</span><span class="sxs-lookup"><span data-stu-id="0586d-337">SCEP</span></span> | <span data-ttu-id="0586d-338">Certificado de Usuário</span><span class="sxs-lookup"><span data-stu-id="0586d-338">User Certificate</span></span> | <span data-ttu-id="0586d-339">Android, iOS, Windows Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-339">Android, iOS, Windows mobile</span></span> | <span data-ttu-id="0586d-340">Corporativo, BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-340">Corporate, BYOD</span></span> |                                                           

##### <span data-ttu-id="0586d-341">Perfil de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0586d-341">Wi-Fi profile</span></span>
<a id="wi-fi-profile" class="xliff"></a>

<span data-ttu-id="0586d-342">Perfis de Wi-Fi são usados para conectar automaticamente um dispositivo móvel a uma rede sem fio.</span><span class="sxs-lookup"><span data-stu-id="0586d-342">Wi-Fi Profiles are used to automatically connect a mobile device to a wireless network.</span></span> <span data-ttu-id="0586d-343">O Intune dá suporte à implantação de perfis de Wi-Fi em todas as plataformas com suporte.</span><span class="sxs-lookup"><span data-stu-id="0586d-343">Intune supports deploying Wi-Fi profiles to all supported platforms.</span></span>

-   <span data-ttu-id="0586d-344">Saiba mais sobre [como o Intune dá suporte a perfis de Wi-Fi.](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="0586d-344">Learn more about [how Intune supports Wi-Fi profiles.](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)</span></span>

<span data-ttu-id="0586d-345">Veja abaixo um exemplo de um design para um perfil de Wi-Fi:</span><span class="sxs-lookup"><span data-stu-id="0586d-345">Below is an example of a design for a Wi-Fi profile:</span></span>

| <span data-ttu-id="0586d-346">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0586d-346">**Type**</span></span> | <span data-ttu-id="0586d-347">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="0586d-347">**Profile name**</span></span> | <span data-ttu-id="0586d-348">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-348">**Device platform**</span></span> | <span data-ttu-id="0586d-349">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-349">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-350">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0586d-350">Wi-Fi</span></span> | <span data-ttu-id="0586d-351">Perfil de Wi-Fi da Ásia</span><span class="sxs-lookup"><span data-stu-id="0586d-351">Asia Wi-Fi profile</span></span> | <span data-ttu-id="0586d-352">Android</span><span class="sxs-lookup"><span data-stu-id="0586d-352">Android</span></span> | <span data-ttu-id="0586d-353">Corporativo, BYOD na região da Ásia</span><span class="sxs-lookup"><span data-stu-id="0586d-353">Corporate, BYOD Asia region</span></span>|                                                           
| <span data-ttu-id="0586d-354">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="0586d-354">Wi-Fi</span></span> | <span data-ttu-id="0586d-355">Perfil de Wi-Fi na América do Norte</span><span class="sxs-lookup"><span data-stu-id="0586d-355">North America Wi-Fi profile</span></span> | <span data-ttu-id="0586d-356">Android, iOS, Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-356">Android, iOS, Windows 10 Mobile</span></span> | <span data-ttu-id="0586d-357">Corporativo, BYOD na região da América do Norte</span><span class="sxs-lookup"><span data-stu-id="0586d-357">Corporate, BYOD North America region</span></span> |                                                           

##### <span data-ttu-id="0586d-358">Perfil da VPN</span><span class="sxs-lookup"><span data-stu-id="0586d-358">VPN profile</span></span>
<a id="vpn-profile" class="xliff"></a>

<span data-ttu-id="0586d-359">Perfis de VPN permitem que os usuários acessem a rede de locais remotos.</span><span class="sxs-lookup"><span data-stu-id="0586d-359">VPN profiles let users securely access your network from remote locations.</span></span> <span data-ttu-id="0586d-360">O Intune dá suporte a perfis de VPN de conexões de VPN móveis nativas e de fornecedores de terceiros.</span><span class="sxs-lookup"><span data-stu-id="0586d-360">Intune supports VPN profiles from native mobile VPN connections and third party vendors.</span></span>

-   <span data-ttu-id="0586d-361">Saiba mais sobre os [perfis de VPN e os fornecedores com suporte no Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-361">Learn more about [VPN profiles and vendors supported by Intune](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune).</span></span>

<span data-ttu-id="0586d-362">Veja abaixo um exemplo de como documentar o design de um perfil VPN.</span><span class="sxs-lookup"><span data-stu-id="0586d-362">Below is an example of documenting the design of a VPN profile.</span></span>

| <span data-ttu-id="0586d-363">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0586d-363">**Type**</span></span> | <span data-ttu-id="0586d-364">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="0586d-364">**Profile name**</span></span> | <span data-ttu-id="0586d-365">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-365">**Device platform**</span></span> | <span data-ttu-id="0586d-366">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-366">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-367">VPN</span><span class="sxs-lookup"><span data-stu-id="0586d-367">VPN</span></span> | <span data-ttu-id="0586d-368">Qualquer perfil de conexão VPN Cisco</span><span class="sxs-lookup"><span data-stu-id="0586d-368">VPN Cisco any connect Profile</span></span> | <span data-ttu-id="0586d-369">Android, iOS, Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-369">Android, iOS, Windows 10 Mobile</span></span> | <span data-ttu-id="0586d-370">Corporativo, BYOD na América do Norte e Alemanha</span><span class="sxs-lookup"><span data-stu-id="0586d-370">Corporate, BYOD North America and Germany</span></span>|                                                           
| <span data-ttu-id="0586d-371">VPN</span><span class="sxs-lookup"><span data-stu-id="0586d-371">VPN</span></span> | <span data-ttu-id="0586d-372">Pulse Secure</span><span class="sxs-lookup"><span data-stu-id="0586d-372">Pulse Secure</span></span> | <span data-ttu-id="0586d-373">Android</span><span class="sxs-lookup"><span data-stu-id="0586d-373">Android</span></span> | <span data-ttu-id="0586d-374">Corporativo, BYOD na região da Ásia</span><span class="sxs-lookup"><span data-stu-id="0586d-374">Corporate, BYOD Asia region</span></span> |                                                           

##### <span data-ttu-id="0586d-375">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="0586d-375">Email profile</span></span>
<a id="email-profile" class="xliff"></a>

<span data-ttu-id="0586d-376">Os perfis de email permitem que um cliente de email seja configurado automaticamente com informações de conexão e a configuração de email.</span><span class="sxs-lookup"><span data-stu-id="0586d-376">Email profiles allow an email client to be automatically setup with connection information and setup email configuration.</span></span> <span data-ttu-id="0586d-377">O Intune dá suporte a perfis de email em alguns dispositivos.</span><span class="sxs-lookup"><span data-stu-id="0586d-377">Intune supports email profiles on some devices.</span></span>

-   <span data-ttu-id="0586d-378">Saiba mais sobre os [perfis de email](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) e quais plataformas têm suporte.</span><span class="sxs-lookup"><span data-stu-id="0586d-378">Learn more about [email profiles](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) and what platforms are supported.</span></span>

<span data-ttu-id="0586d-379">Veja abaixo um exemplo de como documentar o design de perfis de email:</span><span class="sxs-lookup"><span data-stu-id="0586d-379">Below is an example of documenting the design of email profiles:</span></span>

| <span data-ttu-id="0586d-380">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0586d-380">**Type**</span></span> | <span data-ttu-id="0586d-381">**Nome do perfil**</span><span class="sxs-lookup"><span data-stu-id="0586d-381">**Profile name**</span></span> | <span data-ttu-id="0586d-382">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-382">**Device platform**</span></span> | <span data-ttu-id="0586d-383">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-383">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-384">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="0586d-384">Email profile</span></span> | <span data-ttu-id="0586d-385">Perfil de email do iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-385">iOS email profile</span></span> | <span data-ttu-id="0586d-386">iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-386">iOS</span></span> | <span data-ttu-id="0586d-387">Corporativo – BYOD para profissional da informação</span><span class="sxs-lookup"><span data-stu-id="0586d-387">Corporate – Information worker BYOD</span></span> |                                                           
| <span data-ttu-id="0586d-388">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="0586d-388">Email profile</span></span> | <span data-ttu-id="0586d-389">Perfil de email do Android Knox</span><span class="sxs-lookup"><span data-stu-id="0586d-389">Android Knox email profile</span></span> | <span data-ttu-id="0586d-390">Android Knox</span><span class="sxs-lookup"><span data-stu-id="0586d-390">Android Knox</span></span> | <span data-ttu-id="0586d-391">BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-391">BYOD</span></span> |

### <span data-ttu-id="0586d-392">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="0586d-392">Apps</span></span>
<a id="apps" class="xliff"></a>

<span data-ttu-id="0586d-393">O Intune dá suporte à entrega de aplicativos aos usuários ou dispositivos de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="0586d-393">Intune supports delivering apps to the users or devices in multiple ways.</span></span> <span data-ttu-id="0586d-394">O tipo de aplicativo entregue pode ser aplicativos do instalador de software, aplicativos de uma loja pública de aplicativos, links externos ou aplicativos iOS gerenciados.</span><span class="sxs-lookup"><span data-stu-id="0586d-394">The type of application delivered could be software installer apps, apps from a public app store, external links, or managed iOS apps.</span></span> <span data-ttu-id="0586d-395">Além das implantações de aplicativo individuais, os aplicativos adquiridos por volume podem ser gerenciados e implantados por meio de programas de compra por volume para iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="0586d-395">In addition to individual app deployments, volume-purchased apps can be managed and deployed through the volume-purchase programs for iOS and Windows.</span></span> <span data-ttu-id="0586d-396">Veja abaixo mais informações sobre como o Intune dá suporte a aplicativos e sobre os programas de compra por volume.</span><span class="sxs-lookup"><span data-stu-id="0586d-396">Below is more information about how Intune supports apps and the volume purchase programs.</span></span>

-   <span data-ttu-id="0586d-397">Saiba mais sobre os [tipos de aplicativos](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="0586d-397">Learn more about [types of apps](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

-   <span data-ttu-id="0586d-398">Saiba mais sobre o [iOS VPP (Volume Purchase Program) for Business](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-398">Learn more about [iOS Volume Purchase Program for Business (VPP)](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)).</span></span>

-   <span data-ttu-id="0586d-399">Saiba mais sobre a [Windows Store para Empresas](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-399">Learn more about [Windows Store for Business](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).</span></span>

#### <span data-ttu-id="0586d-400">Requisitos de tipo de aplicativo</span><span class="sxs-lookup"><span data-stu-id="0586d-400">App type requirements</span></span>
<a id="app-type-requirements" class="xliff"></a>

<span data-ttu-id="0586d-401">Como os aplicativos podem ser implantados em usuários e dispositivos, é recomendável decidir quais aplicativos serão gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="0586d-401">Since apps can be deployed to users and devices, it’s recommended to decide which applications will be managed by Intune.</span></span> <span data-ttu-id="0586d-402">Durante a coleta da lista, tente responder às seguintes perguntas:</span><span class="sxs-lookup"><span data-stu-id="0586d-402">While gathering the list, try to answer the following questions:</span></span>

-   <span data-ttu-id="0586d-403">Os aplicativos exigem integração com serviços de nuvem?</span><span class="sxs-lookup"><span data-stu-id="0586d-403">Do the apps require integration with cloud services?</span></span>

-   <span data-ttu-id="0586d-404">Todos os aplicativos estarão disponíveis para os usuários BYOD?</span><span class="sxs-lookup"><span data-stu-id="0586d-404">Will all apps be available to BYOD users?</span></span>

-   <span data-ttu-id="0586d-405">Quais são as opções de implantação disponíveis para esses aplicativos?</span><span class="sxs-lookup"><span data-stu-id="0586d-405">What are the deployment options available for these apps?</span></span>

-   <span data-ttu-id="0586d-406">Sua empresa precisa fornecer acesso a dados de aplicativos SaaS (software como serviço) para seus parceiros?</span><span class="sxs-lookup"><span data-stu-id="0586d-406">Does your company need to provide access to Software as a service (SaaS) apps data for their partners?</span></span>

-   <span data-ttu-id="0586d-407">Os aplicativos exigem acesso à Internet por meio dos dispositivos do usuário?</span><span class="sxs-lookup"><span data-stu-id="0586d-407">Do the apps require internet access from user’s devices?</span></span>

-   <span data-ttu-id="0586d-408">Os aplicativos estão disponíveis publicamente em uma loja de aplicativos ou são Aplicativos de Linha de Negócios personalizados?</span><span class="sxs-lookup"><span data-stu-id="0586d-408">Are the apps publicly available in an app store, or are they custom Line of Business Apps?</span></span>


>[!TIP]
> <span data-ttu-id="0586d-409">Confira os [diferentes tipos de aplicativos com suporte no Intune](/intune-classic/deploy-use/add-apps).</span><span class="sxs-lookup"><span data-stu-id="0586d-409">Check out the [different types of applications that Intune support](/intune-classic/deploy-use/add-apps).</span></span>

#### <span data-ttu-id="0586d-410">Políticas de proteção do aplicativo</span><span class="sxs-lookup"><span data-stu-id="0586d-410">App protection policies</span></span>
<a id="app-protection-policies" class="xliff"></a>

<span data-ttu-id="0586d-411">As políticas de proteção do aplicativo minimizam a perda de dados, definindo como o aplicativo gerencia os dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="0586d-411">App protection policies minimize data loss by defining how the application manages the corporate data.</span></span> <span data-ttu-id="0586d-412">O Intune dá suporte a políticas de proteção do aplicativo para qualquer aplicativo criado para funcionar com o gerenciamento de aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="0586d-412">Intune supports app protection policies for any application built to function with mobile app management.</span></span> <span data-ttu-id="0586d-413">Ao criar a política de proteção do aplicativo, é necessário determinar quais restrições você colocará aos dados corporativos em determinado aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0586d-413">When designing the app protection policy, you need to determine what restrictions you will place on corporate data in a given app.</span></span> <span data-ttu-id="0586d-414">É recomendável examinar o funcionamento das [políticas de proteção do aplicativo](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-414">It’s recommended to review how [app protection policies](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) work.</span></span> <span data-ttu-id="0586d-415">Veja abaixo um exemplo de como documentar os aplicativos existentes e qual proteção é necessária.</span><span class="sxs-lookup"><span data-stu-id="0586d-415">Below is an example of how to document the existing applications and what protection is needed.</span></span>

| <span data-ttu-id="0586d-416">**Aplicativo**</span><span class="sxs-lookup"><span data-stu-id="0586d-416">**Application**</span></span> | <span data-ttu-id="0586d-417">**Finalidade**</span><span class="sxs-lookup"><span data-stu-id="0586d-417">**Purpose**</span></span> | <span data-ttu-id="0586d-418">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="0586d-418">**Platforms**</span></span> | <span data-ttu-id="0586d-419">**Caso de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-419">**Use case**</span></span> | <span data-ttu-id="0586d-420">**Política de proteção do aplicativo**</span><span class="sxs-lookup"><span data-stu-id="0586d-420">**App protection policy**</span></span> |
|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-421">Outlook Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-421">Outlook mobile</span></span>  | <span data-ttu-id="0586d-422">Disponível</span><span class="sxs-lookup"><span data-stu-id="0586d-422">Available</span></span> | <span data-ttu-id="0586d-423">iOS</span><span class="sxs-lookup"><span data-stu-id="0586d-423">iOS</span></span> | <span data-ttu-id="0586d-424">Corporativo – Executivos</span><span class="sxs-lookup"><span data-stu-id="0586d-424">Corporate - Executives</span></span> | <span data-ttu-id="0586d-425">Sem risco de jailbreak, arquivos criptografados</span><span class="sxs-lookup"><span data-stu-id="0586d-425">Cannot be jail broken, encrypt files</span></span> |                                                         
| <span data-ttu-id="0586d-426">Word</span><span class="sxs-lookup"><span data-stu-id="0586d-426">Word</span></span> | <span data-ttu-id="0586d-427">Disponível</span><span class="sxs-lookup"><span data-stu-id="0586d-427">Available</span></span> | <span data-ttu-id="0586d-428">iOS, Android – Samsung Knox, não Knox, Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-428">iOS, Android - Samsung Knox, non-Knox, Windows 10 mobile</span></span> | <span data-ttu-id="0586d-429">Corporativo, BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-429">Corporate, BYOD</span></span> | <span data-ttu-id="0586d-430">Sem risco de jailbreak, arquivos criptografados</span><span class="sxs-lookup"><span data-stu-id="0586d-430">Cannot be jail broken, encrypt files</span></span> |                                                         

#### <span data-ttu-id="0586d-431">Políticas de conformidade</span><span class="sxs-lookup"><span data-stu-id="0586d-431">Compliance policies</span></span>
<a id="compliance-policies" class="xliff"></a>

<span data-ttu-id="0586d-432">As políticas de conformidade determinam se um dispositivo está em conformidade com requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="0586d-432">Compliance policies determine whether a device conforms to certain requirements.</span></span> <span data-ttu-id="0586d-433">O Intune usa políticas de conformidade para determinar se um dispositivo é considerado em conformidade ou não.</span><span class="sxs-lookup"><span data-stu-id="0586d-433">Intune uses compliance policies to determine if a device is considered compliant or non-compliant.</span></span> <span data-ttu-id="0586d-434">Em seguida, o status de conformidade pode ser usado para restringir o acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="0586d-434">The compliance status can then be used to restrict access to company resources.</span></span> <span data-ttu-id="0586d-435">Se o acesso condicional é necessário, é recomendável criar uma [política de conformidade do dispositivo](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-435">If conditional access is required, it is recommended to design a [device compliance policy](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).</span></span> <span data-ttu-id="0586d-436">Consulte os requisitos e casos de uso para determinar quantas políticas de conformidade do dispositivo são necessárias e quais grupos de usuários são os grupos de usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="0586d-436">Refer to requirements and use cases to determine how many device compliance policies are needed and which user groups are the target user groups.</span></span> <span data-ttu-id="0586d-437">Além disso, é necessário determinar quanto tempo um dispositivo pode ficar offline sem fazer check-in antes de ser considerado fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="0586d-437">Additionally, you need to determine how long a device can be offline without checking in before it’s considered non-compliant.</span></span>

<span data-ttu-id="0586d-438">Veja abaixo um exemplo de como criar uma política de conformidade:</span><span class="sxs-lookup"><span data-stu-id="0586d-438">Below is an example of how to design a compliance policy:</span></span>

| <span data-ttu-id="0586d-439">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="0586d-439">**Policy name**</span></span> | <span data-ttu-id="0586d-440">**Plataforma de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="0586d-440">**Device platform**</span></span> | <span data-ttu-id="0586d-441">**Configurações**</span><span class="sxs-lookup"><span data-stu-id="0586d-441">**Settings**</span></span> | <span data-ttu-id="0586d-442">**Grupo de destino**</span><span class="sxs-lookup"><span data-stu-id="0586d-442">**Target group**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-443">Política de conformidade</span><span class="sxs-lookup"><span data-stu-id="0586d-443">Compliance policy</span></span> | <span data-ttu-id="0586d-444">iOS, Android – Samsung Knox, não Knox, Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="0586d-444">iOS, Android - Samsung Knox, non-Knox, Windows 10 mobile</span></span> | <span data-ttu-id="0586d-445">PIN – obrigatório, sem risco de jailbreak</span><span class="sxs-lookup"><span data-stu-id="0586d-445">PIN - required, cannot be jail broken</span></span> | <span data-ttu-id="0586d-446">Corporativo, BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-446">Corporate, BYOD</span></span> |

#### <span data-ttu-id="0586d-447">Políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="0586d-447">Conditional access policies</span></span>
<a id="conditional-access-policies" class="xliff"></a>

<span data-ttu-id="0586d-448">O Acesso Condicional é usado para permitir que apenas os dispositivos em conformidade acessem os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="0586d-448">Conditional Access is used to allow only compliant devices to access company resources.</span></span> <span data-ttu-id="0586d-449">O Intune funciona com todo o EMS (Enterprise Mobility + Security) para controlar o acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="0586d-449">Intune works with the entire Enterprise Mobility + Security (EMS) to control access to company resources.</span></span> <span data-ttu-id="0586d-450">Você precisará determinar se o acesso condicional será necessário e o que deverá ser protegido.</span><span class="sxs-lookup"><span data-stu-id="0586d-450">You’ll need to determine if conditional access is required, and what must be secured.</span></span>

-   <span data-ttu-id="0586d-451">Saiba mais sobre o [Acesso Condicional](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="0586d-451">Learn more about [Conditional Access](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span></span>

<span data-ttu-id="0586d-452">Para o acesso online, determine quais plataformas e grupos de usuários serão o destino das políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="0586d-452">For online access, determine what platforms, and user groups will be targeted by conditional access policies.</span></span>

<span data-ttu-id="0586d-453">Além disso, você precisa determinar se é necessário instalar/configurar o conector serviço a serviço do Intune para o Exchange Online ou Exchange no Local.</span><span class="sxs-lookup"><span data-stu-id="0586d-453">Additionally, you need to determine whether you need to install/configure the Intune service-to-service connector for Exchange Online or Exchange on-premises.</span></span>

<span data-ttu-id="0586d-454">Saiba mais como instalar e configurar conectores serviço a serviço do Intune:</span><span class="sxs-lookup"><span data-stu-id="0586d-454">Learn more how to install and configure the Intune service-to-service connectors:</span></span>

-   [<span data-ttu-id="0586d-455">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0586d-455">Exchange Online</span></span>](/intune-classic/deploy-use/intune-service-to-service-exchange-connector)

-   [<span data-ttu-id="0586d-456">Exchange Local</span><span class="sxs-lookup"><span data-stu-id="0586d-456">Exchange On-premises</span></span>](/intune-classic/deploy-use/intune-on-premises-exchange-connector)

<span data-ttu-id="0586d-457">Este é um exemplo de como documentar as políticas de acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="0586d-457">Here’s an example of how to document conditional access policies:</span></span>

| <span data-ttu-id="0586d-458">**Serviço**</span><span class="sxs-lookup"><span data-stu-id="0586d-458">**Service**</span></span> | <span data-ttu-id="0586d-459">**Plataformas para Autenticação Moderna**</span><span class="sxs-lookup"><span data-stu-id="0586d-459">**Platforms for Modern Authentication**</span></span> | <span data-ttu-id="0586d-460">**Autenticação básica**</span><span class="sxs-lookup"><span data-stu-id="0586d-460">**Basic Authentication**</span></span> | <span data-ttu-id="0586d-461">**Casos de uso**</span><span class="sxs-lookup"><span data-stu-id="0586d-461">**Use cases**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="0586d-462">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0586d-462">Exchange online</span></span> | <span data-ttu-id="0586d-463">iOS, Android</span><span class="sxs-lookup"><span data-stu-id="0586d-463">iOS, Android</span></span> | <span data-ttu-id="0586d-464">Bloquear dispositivos que não estão em conformidade em plataformas com suporte no Intune</span><span class="sxs-lookup"><span data-stu-id="0586d-464">Block non-compliant devices on platforms supported by Intune</span></span> | <span data-ttu-id="0586d-465">Corporativo, BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-465">Corporate, BYOD</span></span> |
| <span data-ttu-id="0586d-466">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0586d-466">SharePoint online</span></span> | <span data-ttu-id="0586d-467">iOS, Android</span><span class="sxs-lookup"><span data-stu-id="0586d-467">iOS, Android</span></span> |  | <span data-ttu-id="0586d-468">Corporativo, BYOD</span><span class="sxs-lookup"><span data-stu-id="0586d-468">Corporate, BYOD</span></span> |

## <span data-ttu-id="0586d-469">Próxima seção</span><span class="sxs-lookup"><span data-stu-id="0586d-469">Next Section</span></span>
<a id="next-section" class="xliff"></a>

<span data-ttu-id="0586d-470">A próxima seção fornece diretrizes sobre o [processo de implementação do Intune](planning-guide-onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="0586d-470">The next section provides guidance on the [Intune implementation process](planning-guide-onboarding.md).</span></span>
