---
title: "<span data-ttu-id=\"98d9a-101\">Processo de integração do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"98d9a-101\">Intune onboarding process</span></span>"
description: "<span data-ttu-id=\"98d9a-102\">Este artigo ajuda você com todos os detalhes que precisam ser considerados ao integrar a solução somente na nuvem do Intune em seu ambiente.</span><span class=\"sxs-lookup\"><span data-stu-id=\"98d9a-102\">This article helps you with all details that need to be considered when on-boarding Intune cloud-only solution into your environment.</span></span>"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 71558786cc7f058cee31e9bbe3960ed75a76891b
ms.sourcegitcommit: ce363409d1206e4a3d669709863ccc9eb22b7d5f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2017
---
<<<<<<< HEAD
# <a name="implement-your-intune-plan"></a><span data-ttu-id="98d9a-103">Implementar seu plano do Intune</span><span class="sxs-lookup"><span data-stu-id="98d9a-103">Implement your Intune plan</span></span>

<span data-ttu-id="98d9a-104">Durante a fase de integração, você implantará o Intune no ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="98d9a-104">During the onboarding phase, you deploy Intune into your production environment.</span></span> <span data-ttu-id="98d9a-105">O processo de implementação consiste em configurar o Intune e as dependências externas (se necessário) de acordo com os [requisitos de caso de uso](planning-guide-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-105">The implementation process consists of setting up and configuring Intune and external dependencies (if required) based on your [use-case requirements](planning-guide-requirements.md).</span></span>

<span data-ttu-id="98d9a-106">A seção a seguir fornece uma visão geral do processo de implementação do Intune que inclui requisitos e tarefas de alto nível.</span><span class="sxs-lookup"><span data-stu-id="98d9a-106">The following section provides an overview of the Intune implementation process that includes requirements and high-level tasks.</span></span>
=======
# <a name="implement-your-intune-plan"></a>Implementar seu plano do Intune

Durante a fase de integração, você implantará o Intune no ambiente de produção. O processo de implementação consiste em configurar o Intune e as dependências externas (se necessário) de acordo com os [requisitos de caso de uso](planning-guide-requirements.md).
>>>>>>> live

## <a name="intune-requirements"></a><span data-ttu-id="98d9a-107">Requisitos do Intune</span><span class="sxs-lookup"><span data-stu-id="98d9a-107">Intune requirements</span></span>

<<<<<<< HEAD
<span data-ttu-id="98d9a-108">Os principais requisitos independentes do Intune são:</span><span class="sxs-lookup"><span data-stu-id="98d9a-108">The main Intune standalone requirements are:</span></span>

-   <span data-ttu-id="98d9a-109">EMS (Enterprise Mobility + Security)/assinatura do Intune</span><span class="sxs-lookup"><span data-stu-id="98d9a-109">Enterprise Mobility + Security (EMS)/Intune subscription</span></span>

-   <span data-ttu-id="98d9a-110">Assinatura do Office 365 (para aplicativos do Office e aplicativos gerenciados por política de MAM)</span><span class="sxs-lookup"><span data-stu-id="98d9a-110">Office 365 subscription (for Office apps and MAM policy managed apps)</span></span>

-   <span data-ttu-id="98d9a-111">Certificado Apple APNs (para habilitar o gerenciamento de plataforma de dispositivo iOS)</span><span class="sxs-lookup"><span data-stu-id="98d9a-111">Apple APNs Certificate (to enable iOS device platform management)</span></span>
=======
## <a name="intune-requirements"></a>Requisitos do Intune

Os principais requisitos independentes do Intune são:

-   EMS (Enterprise Mobility + Security)/assinatura do Intune
>>>>>>> live

-   <span data-ttu-id="98d9a-112">Azure AD Connect (para sincronização de diretório)</span><span class="sxs-lookup"><span data-stu-id="98d9a-112">Azure AD Connect (for directory synchronization)</span></span>

-   <span data-ttu-id="98d9a-113">On-Premises Connector do Intune para Exchange (para a acesso condicional para o Exchange Local, se necessário)</span><span class="sxs-lookup"><span data-stu-id="98d9a-113">Intune On-Premises Connector for Exchange (for conditional access for Exchange On-Premises, if needed)</span></span>

-   <span data-ttu-id="98d9a-114">Intune Certificate Connector (para a implantação de certificado SCEP, se necessário)</span><span class="sxs-lookup"><span data-stu-id="98d9a-114">Intune Certificate Connector (for SCEP certificate deployment, if needed)</span></span>

<<<<<<< HEAD
>[!TIP]
> <span data-ttu-id="98d9a-115">Consulte a lista de [dispositivos com suporte](supported-devices-browsers.md) para obter uma lista de dispositivos que você pode gerenciar com o Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-115">See the list of [supported devices](supported-devices-browsers.md) for a complete list of devices you can manage with Intune.</span></span>
=======
-   On-Premises Connector do Intune para Exchange (para a acesso condicional para o Exchange Local, se necessário)
>>>>>>> live

## <a name="intune-implementation-process"></a><span data-ttu-id="98d9a-116">Processo de implementação do Intune</span><span class="sxs-lookup"><span data-stu-id="98d9a-116">Intune implementation process</span></span>

<<<<<<< HEAD
<span data-ttu-id="98d9a-117">Nós identificamos 13 tarefas discretas para implementar uma implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-117">We've identified 13 discrete tasks for implementing an Intune deployment.</span></span> <span data-ttu-id="98d9a-118">Dependendo dos requisitos de negócios, da infraestrutura existente e da estratégia de gerenciamento de dispositivo, algumas dessas tarefas talvez já tenham sido concluídas.</span><span class="sxs-lookup"><span data-stu-id="98d9a-118">Depending on your business requirements, existing infrastructure, and device management strategy, some of these tasks may already be finished.</span></span> <span data-ttu-id="98d9a-119">Outras podem não se aplicar ao seu plano.</span><span class="sxs-lookup"><span data-stu-id="98d9a-119">Others may not apply to your plan.</span></span>
=======
>[!TIP]
> Consulte a lista de [dispositivos com suporte](supported-devices-browsers.md) para obter uma lista de dispositivos que você pode gerenciar com o Intune.
>>>>>>> live

### <a name="task-1-get-an-intune-subscription"></a><span data-ttu-id="98d9a-120">Tarefa 1: obter uma assinatura do Intune</span><span class="sxs-lookup"><span data-stu-id="98d9a-120">Task 1: Get an Intune subscription</span></span>

<<<<<<< HEAD
<span data-ttu-id="98d9a-121">Conforme indicado na seção de requisitos do Intune acima, você precisa de uma assinatura do EMS ou do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-121">As indicated in the Intune requirements section above, you need an EMS or Intune subscription.</span></span> <span data-ttu-id="98d9a-122">Caso sua organização não tenha uma, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o EMS (Enterprise Mobility + Security) ou o Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-122">If your organization does not have one, contact Microsoft or your Microsoft account team regarding your interest in purchasing Enterprise Mobility + Security (EMS) or Intune.</span></span>

-   <span data-ttu-id="98d9a-123">Saiba mais sobre [como comprar o Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span><span class="sxs-lookup"><span data-stu-id="98d9a-123">Learn more about [how to buy Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span></span>

### <a name="task-2-add-office-365-subscription"></a><span data-ttu-id="98d9a-124">Tarefa 2: Adicionar uma assinatura do Office 365</span><span class="sxs-lookup"><span data-stu-id="98d9a-124">Task 2: Add Office 365 subscription</span></span>

<span data-ttu-id="98d9a-125">Essa etapa é opcional.</span><span class="sxs-lookup"><span data-stu-id="98d9a-125">This step is optional.</span></span> <span data-ttu-id="98d9a-126">Você precisa de uma assinatura do Office 365 se você planeja usar o Exchange Online e gerenciar aplicativos móveis do Office com as políticas de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="98d9a-126">You need an Office 365 subscription if you plan to use Exchange Online and manage Office mobile apps with app protection policies.</span></span> <span data-ttu-id="98d9a-127">Caso sua organização não tenha uma assinatura do Office 365, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d9a-127">If your organization does not have an Office 365 subscription, contact Microsoft or your Microsoft account team regarding your interest in purchasing Office 365.</span></span>
=======
Nós identificamos 13 tarefas discretas para implementar uma implantação do Intune. Dependendo dos requisitos de negócios, da infraestrutura existente e da estratégia de gerenciamento de dispositivo, algumas dessas tarefas talvez já tenham sido concluídas. Outras podem não se aplicar ao seu plano.

### <a name="task-1-get-an-intune-subscription"></a>Tarefa 1: obter uma assinatura do Intune

Conforme indicado na seção de requisitos do Intune acima, você precisa de uma assinatura do EMS ou do Intune. Caso sua organização não tenha uma, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o EMS (Enterprise Mobility + Security) ou o Intune.
>>>>>>> live

-   <span data-ttu-id="98d9a-128">Saiba mais sobre [como comprar o Office 365](https://products.office.com/business/compare-office-365-for-business-plans).</span><span class="sxs-lookup"><span data-stu-id="98d9a-128">Learn more about [how to buy Office 365](https://products.office.com/business/compare-office-365-for-business-plans).</span></span>

<<<<<<< HEAD
### <a name="task-3-add-users-groups-in-azure-ad"></a><span data-ttu-id="98d9a-129">Tarefa 3: Adicionar grupos de usuários no Azure AD</span><span class="sxs-lookup"><span data-stu-id="98d9a-129">Task 3: Add users groups in Azure AD</span></span>

<span data-ttu-id="98d9a-130">Talvez seja necessário adicionar usuários ou grupos de segurança no Active Directory ou Azure Active Directory de acordo com seus requisitos e cenários de caso de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-130">You may need to add users or security groups in Active Directory or Azure Active Directory based on your Intune deployment use-case scenarios and requirements.</span></span> <span data-ttu-id="98d9a-131">Examine os usuários e grupos de segurança atuais no Active Directory ou Azure Active Directory e determine se eles atendem totalmente às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="98d9a-131">Review your current users and security groups in Active Directory or Azure Active Directory and determine if they fully meet your needs.</span></span> <span data-ttu-id="98d9a-132">Ao adicionar novos usuários e grupos de segurança, recomendamos adicioná-los no Active Directory e sincronizar com o Azure Active Directory usando o Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="98d9a-132">When adding new users and security groups, we recommend adding them in Active Directory and synchronizing with Azure Active Directory using Azure AD Connect.</span></span>
=======
### <a name="task-2-add-office-365-subscription"></a>Tarefa 2: Adicionar uma assinatura do Office 365

Essa etapa é opcional. Você precisa de uma assinatura do Office 365 se você planeja usar o Exchange Online e gerenciar aplicativos móveis do Office com as políticas de proteção do aplicativo. Caso sua organização não tenha uma assinatura do Office 365, contate a Microsoft ou a equipe de contas da Microsoft sobre seu interesse em comprar o Office 365.
>>>>>>> live


<<<<<<< HEAD
-   <span data-ttu-id="98d9a-133">Saiba mais sobre [como adicionar usuários/grupos no Intune](users-permissions-add.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-133">Learn more about [how to add users/groups in Intune](users-permissions-add.md).</span></span>
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a><span data-ttu-id="98d9a-134">Tarefa 4: Atribuir licenças de usuário do Intune e Office 365</span><span class="sxs-lookup"><span data-stu-id="98d9a-134">Task 4: Assign Intune and Office 365 user licenses</span></span>
=======
### <a name="task-3-add-users-groups-in-azure-ad"></a>Tarefa 3: Adicionar grupos de usuários no Azure AD

Talvez seja necessário adicionar usuários ou grupos de segurança no Active Directory ou Azure Active Directory de acordo com seus requisitos e cenários de caso de uso de implantação do Intune. Examine os usuários e grupos de segurança atuais no Active Directory ou Azure Active Directory e determine se eles atendem totalmente às suas necessidades. Ao adicionar novos usuários e grupos de segurança, recomendamos adicioná-los no Active Directory e sincronizar com o Azure Active Directory usando o Azure AD Connect.


-   Saiba mais sobre [como adicionar usuários/grupos no Intune](users-permissions-add.md).
<!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a>Tarefa 4: Atribuir licenças de usuário do Intune e Office 365
>>>>>>> live

<span data-ttu-id="98d9a-135">Todos os usuários que serão alvo da distribuição do EMS/Intune e Office 365 precisarão ter uma licença atribuída a eles.</span><span class="sxs-lookup"><span data-stu-id="98d9a-135">All users you target for EMS/Intune and Office 365 rollout need to have a license assigned to them.</span></span> <span data-ttu-id="98d9a-136">A atribuição de licença do EMS/Intune e Office 365 pode ser feita no Portal do Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="98d9a-136">You can assign EMS/Intune and Office 365 licenses in the Office 365 Admin Center Portal.</span></span>

-   <span data-ttu-id="98d9a-137">Saiba mais sobre [como atribuir licenças do Intune](licenses-assign.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-137">Learn more about [how to assign Intune licenses](licenses-assign.md).</span></span>

<<<<<<< HEAD
### <a name="task-5-set-mobile-device-management-authority-to-intune"></a><span data-ttu-id="98d9a-138">Tarefa 5: definir a autoridade de gerenciamento de dispositivo móvel para o Intune</span><span class="sxs-lookup"><span data-stu-id="98d9a-138">Task 5: Set mobile device management authority to Intune</span></span>

<span data-ttu-id="98d9a-139">Antes de iniciar a instalação, a configuração, o gerenciamento e o registro de dispositivos usando o Intune, é necessário definir a autoridade de gerenciamento de dispositivo para o Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-139">Before you can begin to set up, configure, manage and enroll devices using Intune, you must set the device management authority to Intune.</span></span>

-   <span data-ttu-id="98d9a-140">Saiba mais sobre [como definir a autoridade de gerenciamento de dispositivo](mdm-authority-set.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-140">Learn more about [how to set the device management authority](mdm-authority-set.md).</span></span>

### <a name="task-6-enable-device-platforms"></a><span data-ttu-id="98d9a-141">Tarefa 6: Habilitar plataformas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="98d9a-141">Task 6: Enable device platforms</span></span>

<span data-ttu-id="98d9a-142">Por padrão, a maioria das plataformas de dispositivo é habilitada, exceto dispositivos Apple (iOS e Mac).</span><span class="sxs-lookup"><span data-stu-id="98d9a-142">By default, most device platforms are enabled except for Apple devices (iOS and Mac).</span></span> <span data-ttu-id="98d9a-143">Antes que os dispositivos iOS possam ser registrados e gerenciados no Intune, a plataforma de dispositivo deve ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="98d9a-143">Before iOS devices can be enrolled and managed in Intune, the device platform must be enabled.</span></span> <span data-ttu-id="98d9a-144">Para fazer isso, você precisa criar um MDM Push Certificate e adicioná-lo ao Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-144">To do so, you need to create an MDM Push certificate, and add it to Intune.</span></span>

-   <span data-ttu-id="98d9a-145">Saiba mais sobre [como habilitar dispositivos da Apple para registro](apple-mdm-push-certificate-get.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-145">Learn more about [how to enable Apple devices for enrollment](apple-mdm-push-certificate-get.md).</span></span>

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a><span data-ttu-id="98d9a-146">Tarefa 7: Adicionar e implantar políticas de termos e condições</span><span class="sxs-lookup"><span data-stu-id="98d9a-146">Task 7: Add and deploy terms and conditions policies</span></span>

<span data-ttu-id="98d9a-147">O Intune dá suporte a políticas de termos e condições.</span><span class="sxs-lookup"><span data-stu-id="98d9a-147">Intune supports terms and conditions policies.</span></span> <span data-ttu-id="98d9a-148">Adicione políticas de termos e condições conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-148">Add terms and conditions policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="98d9a-149">Saiba mais sobre [como adicionar e implantar políticas de termos e condições](terms-and-conditions-create.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-149">Learn more about [how to add and deploy terms and condition policies](terms-and-conditions-create.md).</span></span>

### <a name="task-8-add-and-deploy-configuration-policies"></a><span data-ttu-id="98d9a-150">Tarefa 8: Adicionar e implantar políticas de configuração</span><span class="sxs-lookup"><span data-stu-id="98d9a-150">Task 8: Add and deploy configuration policies</span></span>

<span data-ttu-id="98d9a-151">O Intune dá suporte a dois tipos de políticas de configuração, geral e personalizada.</span><span class="sxs-lookup"><span data-stu-id="98d9a-151">Intune supports two types of configuration policies, general and custom.</span></span> <span data-ttu-id="98d9a-152">Adicione políticas de configuração conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-152">Add the configuration policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="98d9a-153">Saiba mais sobre [como adicionar e implantar políticas de configuração](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-153">Learn more about [how to add and deploy configuration policies](device-profiles.md).</span></span>

### <a name="task-9-add-and-deploy-resource-profiles"></a><span data-ttu-id="98d9a-154">Tarefa 9: Adicionar e implantar perfis de recursos</span><span class="sxs-lookup"><span data-stu-id="98d9a-154">Task 9: Add and deploy resource profiles</span></span>

<span data-ttu-id="98d9a-155">O Intune dá suporte a perfis de Email, de Wi-Fi e de VPN.</span><span class="sxs-lookup"><span data-stu-id="98d9a-155">Intune supports email, Wi-Fi, and VPN profiles.</span></span> <span data-ttu-id="98d9a-156">Adicione esses perfis conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-156">Add these profiles as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="98d9a-157">Saiba mais sobre [como habilitar o acesso a recursos da empresa com o Intune](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-157">Learn more about [how to enable access to company resources with Intune](device-profiles.md).</span></span>

### <a name="task-10-add-and-deploy-apps"></a><span data-ttu-id="98d9a-158">Tarefa 10: Adicionar e implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="98d9a-158">Task 10: Add and deploy apps</span></span>

<span data-ttu-id="98d9a-159">O Intune dá suporte à implantação de aplicativos Web, LOB e de repositório público.</span><span class="sxs-lookup"><span data-stu-id="98d9a-159">Intune supports the deployment of web, line-of-business, and public Store apps.</span></span> <span data-ttu-id="98d9a-160">Você também pode gerenciar aplicativos que integraram o SDK do Intune, associando-os a políticas de MAM.</span><span class="sxs-lookup"><span data-stu-id="98d9a-160">You can also manage apps that have integrated the Intune SDK by associating them with MAM policies.</span></span> <span data-ttu-id="98d9a-161">Adicione aplicativos conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-161">Add apps as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="98d9a-162">Saiba mais sobre [adição e implantação de aplicativos](app-management.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-162">Learn more about [adding and deploying apps](app-management.md).</span></span>

### <a name="task-11-add-and-deploy-compliance-policies"></a><span data-ttu-id="98d9a-163">Tarefa 11: Adicionar e implantar políticas de conformidade</span><span class="sxs-lookup"><span data-stu-id="98d9a-163">Task 11: Add and deploy compliance policies</span></span>

<span data-ttu-id="98d9a-164">O Intune dá suporte a políticas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="98d9a-164">Intune supports compliance policies.</span></span> <span data-ttu-id="98d9a-165">Adicione políticas de conformidade conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-165">Add compliance policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="98d9a-166">Saiba mais sobre as [políticas de conformidade](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-166">Learn more about [compliance policies](device-compliance.md).</span></span>

### <a name="task-12-enable-conditional-access-policies"></a><span data-ttu-id="98d9a-167">Tarefa 12: habilitar políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="98d9a-167">Task 12: Enable conditional access policies</span></span>

<span data-ttu-id="98d9a-168">O Intune dá suporte ao acesso condicional para Exchange Online, Exchange Local, SharePoint Online, Skype for Business Online e Dynamics CRM Online.</span><span class="sxs-lookup"><span data-stu-id="98d9a-168">Intune supports conditional access for Exchange Online, Exchange on-premises, SharePoint Online, Skype for Business Online, and Dynamics CRM Online.</span></span> <span data-ttu-id="98d9a-169">Habilite e configure o acesso condicional conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-169">Enable and configure conditional access as appropriate based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="98d9a-170">Saiba mais sobre o [acesso condicional](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-170">Learn more about [conditional access](conditional-access.md).</span></span>

### <a name="task-13-enroll-devices"></a><span data-ttu-id="98d9a-171">Tarefa 13: Registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="98d9a-171">Task 13: Enroll devices</span></span>
=======
### <a name="task-5-set-mobile-device-management-authority-to-intune"></a>Tarefa 5: definir a autoridade de gerenciamento de dispositivo móvel para o Intune

Antes de iniciar a instalação, a configuração, o gerenciamento e o registro de dispositivos usando o Intune, é necessário definir a autoridade de gerenciamento de dispositivo para o Intune.

-   Saiba mais sobre [como definir a autoridade de gerenciamento de dispositivo](mdm-authority-set.md).

### <a name="task-6-enable-device-platforms"></a>Tarefa 6: Habilitar plataformas de dispositivo

Por padrão, a maioria das plataformas de dispositivo é habilitada, exceto dispositivos Apple (iOS e Mac). Antes que os dispositivos iOS possam ser registrados e gerenciados no Intune, a plataforma de dispositivo deve ser habilitada. Para fazer isso, você precisa criar um MDM Push Certificate e adicioná-lo ao Intune.

-   Saiba mais sobre [como habilitar dispositivos da Apple para registro](apple-mdm-push-certificate-get.md).

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a>Tarefa 7: Adicionar e implantar políticas de termos e condições

O Intune dá suporte a políticas de termos e condições. Adicione políticas de termos e condições conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como adicionar e implantar políticas de termos e condições](terms-and-conditions-create.md).

### <a name="task-8-add-and-deploy-configuration-policies"></a>Tarefa 8: Adicionar e implantar políticas de configuração

O Intune dá suporte a dois tipos de políticas de configuração, geral e personalizada. Adicione políticas de configuração conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como adicionar e implantar políticas de configuração](device-profiles.md).

### <a name="task-9-add-and-deploy-resource-profiles"></a>Tarefa 9: Adicionar e implantar perfis de recursos

O Intune dá suporte a perfis de Email, de Wi-Fi e de VPN. Adicione esses perfis conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [como habilitar o acesso a recursos da empresa com o Intune](device-profiles.md).

### <a name="task-10-add-and-deploy-apps"></a>Tarefa 10: Adicionar e implantar aplicativos

O Intune dá suporte à implantação de aplicativos Web, LOB e de repositório público. Você também pode gerenciar aplicativos que integraram o SDK do Intune, associando-os a políticas de MAM. Adicione aplicativos conforme apropriado e implante-os em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre [adição e implantação de aplicativos](app-management.md).

### <a name="task-11-add-and-deploy-compliance-policies"></a>Tarefa 11: Adicionar e implantar políticas de conformidade

O Intune dá suporte a políticas de conformidade. Adicione políticas de conformidade conforme apropriado e implante-as em grupos de destino de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre as [políticas de conformidade](device-compliance.md).

### <a name="task-12-enable-conditional-access-policies"></a>Tarefa 12: habilitar políticas de acesso condicional

O Intune dá suporte ao acesso condicional para Exchange Online, Exchange Local, SharePoint Online, Skype for Business Online e Dynamics CRM Online. Habilite e configure o acesso condicional conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.

-   Saiba mais sobre o [acesso condicional](conditional-access.md).

### <a name="task-13-enroll-devices"></a>Tarefa 13: Registrar dispositivos
>>>>>>> live

<span data-ttu-id="98d9a-172">O Intune dá suporte às plataformas de dispositivo iOS, Mac OS, Android, Windows Desktop e Windows Mobile.</span><span class="sxs-lookup"><span data-stu-id="98d9a-172">Intune supports iOS, Mac OS, Android, Windows desktop, and Windows mobile device platforms.</span></span> <span data-ttu-id="98d9a-173">Registre as plataformas de dispositivo móvel conforme apropriado, de acordo com seus requisitos e casos de uso de implantação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-173">Enroll mobile device platforms as appropriate based on your Intune deployment use cases and requirements.</span></span>

<<<<<<< HEAD
-   <span data-ttu-id="98d9a-174">Saiba mais sobre [como registrar dispositivos](device-enrollment.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-174">Learn more about [how to enroll devices](device-enrollment.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="98d9a-175">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="98d9a-175">Next steps</span></span>

<span data-ttu-id="98d9a-176">Confira este [módulo de sessão sobre o Intune da Microsoft Virtual Academy](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) para obter mais informações sobre o processo de implementação do Intune.</span><span class="sxs-lookup"><span data-stu-id="98d9a-176">Check out this [Microsoft Virtual Academy Intune session module](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) for more information on the Intune implementation process.</span></span>


<span data-ttu-id="98d9a-177">Veja diretrizes de como [testar e validar sua implantação do Intune](planning-guide-test-validation.md).</span><span class="sxs-lookup"><span data-stu-id="98d9a-177">See guidance on [testing and validating your Intune deployment](planning-guide-test-validation.md).</span></span>
=======
-   Saiba mais sobre [como registrar dispositivos](device-enrollment.md).


## <a name="next-steps"></a>Próximas etapas

Confira este [módulo de sessão sobre o Intune da Microsoft Virtual Academy](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) para obter mais informações sobre o processo de implementação do Intune.


Veja diretrizes de como [testar e validar sua implantação do Intune](planning-guide-test-validation.md).
>>>>>>> live
