---
title: "Processo de integração do Intune"
description: "Este artigo ajuda você com todos os detalhes que precisam ser considerados ao integrar a solução somente na nuvem do Intune em seu ambiente."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ade7caf544d71c062c0fa251d7a113facb700a36
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="04664-103">Implementação do Intune</span><span class="sxs-lookup"><span data-stu-id="04664-103">Intune implementation</span></span>
<a id="intune-implementation" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="04664-104">Durante a fase de integração, você implementará o Intune no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="04664-104">During the onboarding phase, you’ll implement Intune into your production environment.</span></span> <span data-ttu-id="04664-105">O processo de implementação consistirá em configurar o Intune e as dependências externas (se necessário) de acordo com os [requisitos de caso de uso](planning-guide-requirements.md) examinados nas seções anteriores deste guia.</span><span class="sxs-lookup"><span data-stu-id="04664-105">The implementation process will consist of setting up and configuring Intune and external dependencies (if required), based on your [use case requirements](planning-guide-requirements.md) that were reviewed in previous sections of this guide.</span></span>

<span data-ttu-id="04664-106">A seção a seguir fornece uma visão geral do processo de implementação do Intune que inclui requisitos e tarefas de alto nível.</span><span class="sxs-lookup"><span data-stu-id="04664-106">The following section provides an overview of the Intune implementation process that includes requirements and high-level tasks.</span></span>

>[!TIP]
> <span data-ttu-id="04664-107">Confira [Recursos adicionais](planning-guide-resources.md) para obter mais informações sobre o processo de implementação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-107">Check [Additional resources](planning-guide-resources.md) for more information about the Intune implementation process.</span></span>

## <span data-ttu-id="04664-108">Requisitos do Intune</span><span class="sxs-lookup"><span data-stu-id="04664-108">Intune requirements</span></span>
<a id="intune-requirements" class="xliff"></a>

<span data-ttu-id="04664-109">Os principais requisitos independentes do Intune são fornecidos abaixo:</span><span class="sxs-lookup"><span data-stu-id="04664-109">The main Intune standalone requirements are provided below:</span></span>

-   <span data-ttu-id="04664-110">Assinatura do EMS/Intune</span><span class="sxs-lookup"><span data-stu-id="04664-110">EMS/Intune subscription</span></span>

-   <span data-ttu-id="04664-111">Assinatura do Office 365 (para aplicativos do Office e aplicativos gerenciados por política de MAM)</span><span class="sxs-lookup"><span data-stu-id="04664-111">Office 365 subscription (for Office apps and MAM policy managed apps)</span></span>

-   <span data-ttu-id="04664-112">Certificado Apple APNs (para habilitar o gerenciamento de plataforma de dispositivo iOS)</span><span class="sxs-lookup"><span data-stu-id="04664-112">Apple APNs Certificate (to enable iOS device platform management)</span></span>

-   <span data-ttu-id="04664-113">Azure AD Connect (para sincronização de diretório)</span><span class="sxs-lookup"><span data-stu-id="04664-113">Azure AD Connect (for directory synchronization)</span></span>

-   <span data-ttu-id="04664-114">Conector Local do Intune para Exchange (para a AC do Exchange no Local, se necessário)</span><span class="sxs-lookup"><span data-stu-id="04664-114">Intune On-Premises Connector for Exchange (for CA for Exchange On-Premises, if needed)</span></span>

-   <span data-ttu-id="04664-115">Intune Certificate Connector (para a implantação de certificado SCEP, se necessário)</span><span class="sxs-lookup"><span data-stu-id="04664-115">Intune Certificate Connector (for SCEP certificate deployment, if needed)</span></span>

>[!TIP]
> <span data-ttu-id="04664-116">Encontre mais informações sobre os requisitos independentes do Intune [aqui](/intune/supported-devices-browsers).</span><span class="sxs-lookup"><span data-stu-id="04664-116">You can find more information about Intune standalone requirements [here](/intune/supported-devices-browsers).</span></span>

## <span data-ttu-id="04664-117">Processo de implementação do Intune</span><span class="sxs-lookup"><span data-stu-id="04664-117">Intune implementation process</span></span>
<a id="intune-implementation-process" class="xliff"></a>

### <span data-ttu-id="04664-118">Visão geral das tarefas de implementação</span><span class="sxs-lookup"><span data-stu-id="04664-118">Overview of implementation tasks</span></span>
<a id="overview-of-implementation-tasks" class="xliff"></a>

<span data-ttu-id="04664-119">Esta é uma visão geral de cada tarefa durante a implementação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-119">Here's an overview of each task when implementing Intune.</span></span>

#### <span data-ttu-id="04664-120">Tarefa 1: Adicionar a assinatura do Intune</span><span class="sxs-lookup"><span data-stu-id="04664-120">Task 1: Add Intune subscription</span></span>
<a id="task-1-add-intune-subscription" class="xliff"></a>

<span data-ttu-id="04664-121">Conforme identificado na seção anterior sobre requisitos, é necessária uma assinatura do EMS ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-121">As identified in the previous requirements section, an EMS or Intune subscription is required.</span></span> <span data-ttu-id="04664-122">Caso sua organização não tenha uma assinatura do EMS nem do Intune, contate a Microsoft ou a Equipe de Contas da Microsoft sobre seu interesse em comprar o EMS (Enterprise Mobility + Security) ou o Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-122">If your organization does not have an EMS or Intune subscription, please contact Microsoft or your Microsoft Account Team regarding your interest in purchasing Enterprise Mobility + Security (EMS) or Intune.</span></span>

-   <span data-ttu-id="04664-123">Saiba mais sobre [como comprar o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span><span class="sxs-lookup"><span data-stu-id="04664-123">Learn more about [how to buy Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span></span>

#### <span data-ttu-id="04664-124">Tarefa 2: Adicionar uma assinatura do Office 365</span><span class="sxs-lookup"><span data-stu-id="04664-124">Task 2: Add Office 365 subscription</span></span>
<a id="task-2-add-office-365-subscription" class="xliff"></a>

<span data-ttu-id="04664-125">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="04664-125">This step is optional.</span></span> <span data-ttu-id="04664-126">Conforme identificado na seção anterior sobre requisitos, é necessária uma assinatura do Office 365 se você planeja usar o Exchange Online e gerenciar aplicativos móveis do Office com uma política de MAM.</span><span class="sxs-lookup"><span data-stu-id="04664-126">As identified in the previous requirements section, an Office 365 subscription is required if you plan to use Exchange Online and manage Office mobile apps with MAM policy.</span></span> <span data-ttu-id="04664-127">Caso sua organização não tenha uma assinatura do Office 365, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o Office 365.</span><span class="sxs-lookup"><span data-stu-id="04664-127">If your organization does not have an Office 365 subscription, please contact Microsoft or your Microsoft account team regarding your interest in purchasing Office 365.</span></span>

-   <span data-ttu-id="04664-128">Saiba mais sobre [como comprar o Office 365](https://products.office.com/business/compare-office-365-for-business-plans).</span><span class="sxs-lookup"><span data-stu-id="04664-128">Learn more about [how to buy Office 365](https://products.office.com/business/compare-office-365-for-business-plans).</span></span>

#### <span data-ttu-id="04664-129">Tarefa 3: Adicionar grupos de usuários no Azure AD</span><span class="sxs-lookup"><span data-stu-id="04664-129">Task 3: Add users groups in Azure AD</span></span>
<a id="task-3-add-users-groups-in-azure-ad" class="xliff"></a>

<span data-ttu-id="04664-130">Talvez seja necessário adicionar usuários ou grupos de segurança no AD ou AAD de acordo com seus requisitos e cenários de caso de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-130">You may need to add users or security groups in AD or AAD based on your Intune deployment use case scenarios and requirements.</span></span> <span data-ttu-id="04664-131">Você deve examinar os usuários e grupos de segurança atuais no Active Directory ou Azure Active Directory e determinar se eles atendem totalmente às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="04664-131">You should review your current users and security groups in Active Directory or Azure Active Directory and determine if they fully meet your needs.</span></span> <span data-ttu-id="04664-132">Novos usuários e grupos de segurança geralmente são adicionados no Active Directory e sincronizados no Azure Active Directory por meio do Azure AD Directory Connect.</span><span class="sxs-lookup"><span data-stu-id="04664-132">New users and security groups are most commonly added in Active Directory and synchronized into Azure Active Directory via Azure AD Directory Connect.</span></span>

-   <span data-ttu-id="04664-133">Saiba mais sobre [como adicionar usuários/grupos no Intune](users-permissions-add.md).</span><span class="sxs-lookup"><span data-stu-id="04664-133">Learn more about [how to add users/groups in Intune](users-permissions-add.md).</span></span>

#### <span data-ttu-id="04664-134">Tarefa 4: Atribuir licenças de usuário do Intune e Office 365</span><span class="sxs-lookup"><span data-stu-id="04664-134">Task 4: Assign Intune and Office 365 user licenses</span></span>
<a id="task-4-assign-intune-and-office-365-user-licenses" class="xliff"></a>

<span data-ttu-id="04664-135">Todos os usuários que serão alvo da distribuição do EMS/Intune e Office 365 precisarão ter uma licença atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="04664-135">All users that will be targeted for EMS/Intune and Office 365 rollout will need to have a license assigned to them.</span></span> <span data-ttu-id="04664-136">A atribuição de licença do EMS/Intune e Office 365 pode ser feita no Portal do Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="04664-136">EMS/Intune and Office 365 license assignment can be done in the Office 365 Admin Center Portal.</span></span>

-   <span data-ttu-id="04664-137">Saiba mais sobre [como atribuir licenças do Intune](licenses-assign.md).</span><span class="sxs-lookup"><span data-stu-id="04664-137">Learn more about [how to assign Intune licenses](licenses-assign.md).</span></span>

#### <span data-ttu-id="04664-138">Tarefa 5: Definir a autoridade de gerenciamento de dispositivo móvel para o Intune</span><span class="sxs-lookup"><span data-stu-id="04664-138">Task 5: Set Mobile Device Management Authority to Intune</span></span>
<a id="task-5-set-mobile-device-management-authority-to-intune" class="xliff"></a>

<span data-ttu-id="04664-139">Antes de iniciar a instalação, a configuração, o gerenciamento e o registro de dispositivos usando o Intune, é necessário definir a Autoridade de Gerenciamento de Dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-139">Before you can begin to set up, configure, manage and enroll devices using Intune, you must set the Device Management Authority to Intune.</span></span> <span data-ttu-id="04664-140">A configuração da tarefa da Autoridade de Gerenciamento de Dispositivo é concluída no Portal de Administração do Intune, no espaço de trabalho Administrador.</span><span class="sxs-lookup"><span data-stu-id="04664-140">Setting the Device Management Authority task is completed in the Intune Admin Portal, Admin workspace.</span></span>

-   <span data-ttu-id="04664-141">Saiba mais sobre [como definir a Autoridade de Gerenciamento de Dispositivo](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).</span><span class="sxs-lookup"><span data-stu-id="04664-141">Learn more about [how to set the Device Management Authority](/intune-classic/deploy-use/prerequisites-for-enrollment#step-2-set-mdm-authority).</span></span>

#### <span data-ttu-id="04664-142">Tarefa 6: Habilitar plataformas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="04664-142">Task 6: Enable device platforms</span></span>
<a id="task-6-enable-device-platforms" class="xliff"></a>

<span data-ttu-id="04664-143">Por padrão, no console de administração do Intune, a maioria das plataformas de dispositivo é habilitada, exceto dispositivos Apple (iOS e Mac).</span><span class="sxs-lookup"><span data-stu-id="04664-143">By default, in the Intune admin console, most device platforms are enabled, except for Apple devices (iOS and Mac).</span></span> <span data-ttu-id="04664-144">Antes que os dispositivos iOS possam ser registrados e gerenciados no Intune, a plataforma de dispositivo deve ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="04664-144">Before iOS devices can be enrolled and managed in Intune, the device platform must be enabled.</span></span> <span data-ttu-id="04664-145">A habilitação da plataforma de dispositivo iOS consiste em um processo de três etapas: criar e baixar o certificado APNs e carregar o certificado APNs no Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-145">Enabling the iOS device platform consists of a three-step process: create and download the APNs certificate and upload the APNs certificate into Intune.</span></span>

-   <span data-ttu-id="04664-146">Saiba mais sobre [como funciona a configuração do gerenciamento de dispositivos iOS e Mac.](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="04664-146">Learn more about [how the iOS and Mac device management setup works.](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)</span></span>

#### <span data-ttu-id="04664-147">Tarefa 7: Adicionar e implantar políticas de termos e condições</span><span class="sxs-lookup"><span data-stu-id="04664-147">Task 7: Add and deploy terms and conditions policies</span></span>
<a id="task-7-add-and-deploy-terms-and-conditions-policies" class="xliff"></a>

<span data-ttu-id="04664-148">O Microsoft Intune dá suporte à adição e implantação de políticas de termos e condições.</span><span class="sxs-lookup"><span data-stu-id="04664-148">Microsoft Intune supports adding and deploying terms and conditions policies.</span></span> <span data-ttu-id="04664-149">A adição e implantação de políticas de termos e condições são concluídas no Portal de Administração do Intune, no espaço de trabalho Política.</span><span class="sxs-lookup"><span data-stu-id="04664-149">Adding and deploying terms and conditions policies are completed in the Intune Admin Portal, Policy workspace.</span></span> <span data-ttu-id="04664-150">Adicione políticas de termos e condições conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-150">Add terms and conditions policies as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="04664-151">Saiba mais sobre [como adicionar e implantar políticas de termos e condições](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="04664-151">Learn more about [how to add and deploy terms and condition policies](/intune-classic/deploy-use/terms-and-condition-policy-settings-in-microsoft-intune).</span></span>

#### <span data-ttu-id="04664-152">Tarefa 8: Adicionar e implantar políticas de configuração</span><span class="sxs-lookup"><span data-stu-id="04664-152">Task 8: Add and deploy configuration policies</span></span>
<a id="task-8-add-and-deploy-configuration-policies" class="xliff"></a>

<span data-ttu-id="04664-153">O Microsoft Intune dá suporte à adição e à implantação de dois tipos de políticas de Configuração: Geral e Personalizada.</span><span class="sxs-lookup"><span data-stu-id="04664-153">Microsoft Intune supports adding and deploying two types of Configuration policies, General and Custom.</span></span> <span data-ttu-id="04664-154">A adição e implantação de políticas de Configuração são concluídas no Portal de Administração do Intune, no espaço de trabalho Política.</span><span class="sxs-lookup"><span data-stu-id="04664-154">Adding and deploying Configuration policies are completed in the Intune Admin Portal, Policy workspace.</span></span> <span data-ttu-id="04664-155">Adicione políticas de Configuração conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-155">Add the Configuration policies as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="04664-156">Saiba mais sobre [como adicionar e implantar políticas de configuração](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span><span class="sxs-lookup"><span data-stu-id="04664-156">Learn more about [how to add and deploy configuration policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span></span>

#### <span data-ttu-id="04664-157">Tarefa 9: Adicionar e implantar perfis de recursos</span><span class="sxs-lookup"><span data-stu-id="04664-157">Task 9: Add and deploy resource profiles</span></span>
<a id="task-9-add-and-deploy-resource-profiles" class="xliff"></a>

<span data-ttu-id="04664-158">O Microsoft Intune dá suporte a perfis de Email, Wi-Fi e VPN.</span><span class="sxs-lookup"><span data-stu-id="04664-158">Microsoft Intune supports Email, Wi-Fi and VPN profiles.</span></span> <span data-ttu-id="04664-159">A adição e implantação de perfis são concluídas no Portal de Administração do Intune, no espaço de trabalho Política.</span><span class="sxs-lookup"><span data-stu-id="04664-159">Adding and deploying profiles are completed in the Intune Admin Portal, Policy workspace.</span></span> <span data-ttu-id="04664-160">Adicione perfis de Email/Wi-Fi/VPN conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-160">Add Email/Wi-Fi/VPN profiles as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="04664-161">Saiba mais sobre como [habilitar o acesso a recursos da empresa com o Intune](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="04664-161">Learn more about [enable access to company resources with Intune](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune).</span></span>

#### <span data-ttu-id="04664-162">Tarefa 10: Adicionar e implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="04664-162">Task 10: Add and deploy apps</span></span>
<a id="task-10-add-and-deploy-apps" class="xliff"></a>

<span data-ttu-id="04664-163">O Microsoft Intune dá suporte à implantação de aplicativos Web, LOB e de Repositório Público.</span><span class="sxs-lookup"><span data-stu-id="04664-163">Microsoft Intune supports the deployment of Web, LOB and Public Store Apps.</span></span> <span data-ttu-id="04664-164">Além disso, há suporte para o gerenciamento de aplicativos que integraram o SDK do Intune pela associação deles a políticas de MAM.</span><span class="sxs-lookup"><span data-stu-id="04664-164">In addition, managing apps that have integrated the Intune SDK by associated them with MAM policies is supported.</span></span> <span data-ttu-id="04664-165">A adição e implantação de aplicativos são concluídas no Portal de Administração do Intune, no espaço de trabalho Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="04664-165">Adding and deploying apps are completed in the Intune Admin Portal, App workspace.</span></span> <span data-ttu-id="04664-166">A adição de políticas de MAM é concluída no Portal de Administração do Intune, no espaço de trabalho Política.</span><span class="sxs-lookup"><span data-stu-id="04664-166">Adding MAM policies are completed in the Intune Admin Portal, Policy workspace.</span></span> <span data-ttu-id="04664-167">Adicione aplicativos conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-167">Add apps as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="04664-168">Saiba mais sobre como [adicionar e implantar aplicativos](/intune-classic/deploy-use/deploy-apps).</span><span class="sxs-lookup"><span data-stu-id="04664-168">Learn more about [add and deploy applications](/intune-classic/deploy-use/deploy-apps).</span></span>

#### <span data-ttu-id="04664-169">Tarefa 11: Adicionar e implantar políticas de conformidade</span><span class="sxs-lookup"><span data-stu-id="04664-169">Task 11: Add and deploy compliance policies</span></span>
<a id="task-11-add-and-deploy-compliance-policies" class="xliff"></a>

<span data-ttu-id="04664-170">O Microsoft Intune dá suporte a políticas de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="04664-170">Microsoft Intune supports Compliance policies.</span></span> <span data-ttu-id="04664-171">A adição e implantação de políticas de Conformidade são concluídas no Portal de Administração do Intune, no espaço de trabalho Política.</span><span class="sxs-lookup"><span data-stu-id="04664-171">Adding and deploying Compliance policies are completed in the Intune Admin Portal, Policy workspace.</span></span> <span data-ttu-id="04664-172">Adicione políticas de Conformidade conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-172">Add Compliance policies as appropriate and deploy to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="04664-173">Saiba mais sobre as [políticas de conformidade](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="04664-173">Learn more about [compliance policies](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).</span></span>

#### <span data-ttu-id="04664-174">Tarefa 12: Habilitar Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="04664-174">Task 12: Enable Conditional Access Policies</span></span>
<a id="task-12-enable-conditional-access-policies" class="xliff"></a>

<span data-ttu-id="04664-175">O Microsoft Intune dá suporte ao Acesso Condicional para Exchange Online e no Local, SharePoint Online, Skype for Business Online e Dynamics CRM Online.</span><span class="sxs-lookup"><span data-stu-id="04664-175">Microsoft Intune supports Conditional Access for Exchange Online and On-premises, SharePoint Online, Skype for Business Online and Dynamics CRM Online.</span></span> <span data-ttu-id="04664-176">Habilite políticas de Acesso Condicional no Portal de Administração do Intune, no espaço de trabalho Política.</span><span class="sxs-lookup"><span data-stu-id="04664-176">You enable Conditional Access policies in the Intune Admin Portal, Policy workspace.</span></span> <span data-ttu-id="04664-177">Habilite e configure o Acesso Condicional conforme apropriado, de acordo com seus [requisitos e casos de uso de implantação do Intune](planning-guide-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04664-177">Enable and configure Conditional Access as appropriate based on your [Intune deployment use cases and requirements](planning-guide-requirements.md).</span></span>

-   <span data-ttu-id="04664-178">Saiba mais sobre o [acesso condicional](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="04664-178">Learn more about [conditional access](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span></span>

#### <span data-ttu-id="04664-179">Tarefa 13: Registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="04664-179">Task 13: Enroll devices</span></span>
<a id="task-13-enroll-devices" class="xliff"></a>

<span data-ttu-id="04664-180">O Intune dá suporte às plataformas de dispositivo iOS, Mac OS, Android, Windows Desktop e Windows Mobile.</span><span class="sxs-lookup"><span data-stu-id="04664-180">Intune supports iOS, Mac OS, Android, Windows desktop and Windows mobile device platforms.</span></span> <span data-ttu-id="04664-181">Registre as plataformas de dispositivo móvel conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-181">Enroll mobile device platforms as appropriate, based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="04664-182">Saiba mais sobre [como registrar dispositivos](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="04664-182">Learn more about [how to enroll devices](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune).</span></span>

>[!TIP]
> <span data-ttu-id="04664-183">Confira este [módulo de sessão sobre o Intune da Microsoft Virtual Academy](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) para obter mais informações sobre o processo de implementação do Intune.</span><span class="sxs-lookup"><span data-stu-id="04664-183">Check out this [Microsoft Virtual Academy Intune session module](https://mva.microsoft.com/training-courses/deploying-microsoft-enterprise-mobility-suite-16408?l=PPWNoZxvD_1404778676) for more information on the Intune implementation process.</span></span>

## <span data-ttu-id="04664-184">Próxima seção</span><span class="sxs-lookup"><span data-stu-id="04664-184">Next Section</span></span>
<a id="next-section" class="xliff"></a>

<span data-ttu-id="04664-185">A próxima seção fornece diretrizes sobre como [testar e validar sua implantação do Intune](planning-guide-test-validation.md).</span><span class="sxs-lookup"><span data-stu-id="04664-185">The next section provides guidance on [testing and validating your Intune deployment](planning-guide-test-validation.md).</span></span>
