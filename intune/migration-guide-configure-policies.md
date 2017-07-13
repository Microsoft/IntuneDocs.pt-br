---
title: "Configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativo durante uma migração do Intune"
description: "A finalidade deste artigo é mostrar as etapas necessárias para configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativo durante uma migração do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5e848dda6643a28141a8f5f1d0bdc01f2bd9d390
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c22bb-103">Configurar políticas de conformidade do dispositivo e de gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="c22bb-103">Configure device compliance and app management policies</span></span>
<a id="configure-device-compliance-and-app-management-policies" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="c22bb-104">O principal objetivo ao migrar para o Intune é registrar todos os dispositivos e torná-l-os compatíveis com suas políticas.</span><span class="sxs-lookup"><span data-stu-id="c22bb-104">The main goal when migrating to Intune is to have all devices enrolled, and compliant with its policies.</span></span> <span data-ttu-id="c22bb-105">As políticas de dispositivo não só ajudam você a gerenciar dispositivos de usuário corporativos, mas também dispositivos pessoais (BYOD) e compartilhados, como quiosques, máquinas de ponto de venda, tablets compartilhados por vários alunos em uma sala de aula ou dispositivos sem usuários (somente iOS).</span><span class="sxs-lookup"><span data-stu-id="c22bb-105">Device policies not only help you to manage corporate-owned single-user devices, but also personal (BYOD), and shared devices such as, kiosks, point-of-sales machines, tablets shared by multiple students in a classroom, or user-less devices (iOS only).</span></span>

<span data-ttu-id="c22bb-106">Cada plataforma de dispositivo pode oferecer configurações diferentes, mas as políticas de dispositivo do Intune trabalham com cada uma delas para fornecer os seguintes recursos de gerenciamento de dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="c22bb-106">Each device platform may offer different settings, but Intune device policies work with each device platform by providing the following mobile device management capabilities:</span></span>

-   <span data-ttu-id="c22bb-107">Controle do número de dispositivos que cada usuário registra.</span><span class="sxs-lookup"><span data-stu-id="c22bb-107">Regulate numbers of devices each user enrolls.</span></span>

-   <span data-ttu-id="c22bb-108">Gerenciamento das configurações de dispositivos (por exemplo, criptografia no nível de dispositivo, comprimento da senha, uso de câmera).</span><span class="sxs-lookup"><span data-stu-id="c22bb-108">Manage devices settings (e.g. device-level encryption, password length, camera usage).</span></span>

-   <span data-ttu-id="c22bb-109">Entrega de aplicativos, perfis de email, perfis de VPN etc.</span><span class="sxs-lookup"><span data-stu-id="c22bb-109">Deliver apps, email profiles, VPN profiles, etc.</span></span>

-   <span data-ttu-id="c22bb-110">Avaliação de critérios no nível do dispositivo para as políticas de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="c22bb-110">Evaluate device-level criteria for security compliance policies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c22bb-111">As políticas de gerenciamento de dispositivo não são atribuídas diretamente aos dispositivos ou usuários individuais, em vez disso, são atribuídas a grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="c22bb-111">Device management policies are not assigned directly to individual devices or users, but instead are assigned to user groups.</span></span> <span data-ttu-id="c22bb-112">As políticas podem ser aplicadas diretamente a um grupo de usuários e, portanto, para o dispositivo de usuário, ou podem ser aplicadas a um grupo de dispositivos e, portanto, aos membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="c22bb-112">The policies may be directly applied to a user group, and thereby to the user device, or the policies may be applied to a device group, and thereby to group members.</span></span>

## <span data-ttu-id="c22bb-113">Lista de tarefas para políticas de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="c22bb-113">Task list for device compliance policies</span></span>
<a id="task-list-for-device-compliance-policies" class="xliff"></a>

### <span data-ttu-id="c22bb-114">Tarefa 1: Adicionar grupos de dispositivos (opcional)</span><span class="sxs-lookup"><span data-stu-id="c22bb-114">Task 1: Add device groups (optional)</span></span>
<a id="task-1-add-device-groups-optional" class="xliff"></a>

<span data-ttu-id="c22bb-115">Você poderá criar grupos de dispositivos quando precisar realizar várias tarefas administrativas com base na identidade do dispositivo, em vez de na identidade do usuário.</span><span class="sxs-lookup"><span data-stu-id="c22bb-115">You can create device groups, when you need to perform a variety of administrative tasks based on device identity, instead of user identity.</span></span>

<span data-ttu-id="c22bb-116">Os grupos de dispositivos são úteis para o gerenciamento de dispositivos sem usuários dedicados, como dispositivos de quiosque ou dispositivos compartilhados por colegas de turno ou atribuídos a um local específico.</span><span class="sxs-lookup"><span data-stu-id="c22bb-116">Device groups are useful for managing devices without dedicated users, such as kiosk devices, or devices shared by shift workers or assigned to a specific location.</span></span>

<span data-ttu-id="c22bb-117">Ao configurar grupos de dispositivos antes do registro do dispositivo, você pode aproveitar as categorias dos dispositivos para agrupar automaticamente os dispositivos no registro a fim de receber automaticamente as políticas de dispositivo do grupo.</span><span class="sxs-lookup"><span data-stu-id="c22bb-117">By configuring device groups ahead of device enrollment, you can leverage device categories to auto-group devices upon enrollment to receive their group’s device policies automatically.</span></span> <span data-ttu-id="c22bb-118">[Introdução aos grupos](/intune/groups-get-started).</span><span class="sxs-lookup"><span data-stu-id="c22bb-118">[Get started with groups](/intune/groups-get-started).</span></span>

### <span data-ttu-id="c22bb-119">Tarefa 2: Usar perfis de acesso aos recursos (Wi-Fi, VPN e certificados de email)</span><span class="sxs-lookup"><span data-stu-id="c22bb-119">Task 2: Use resource access profiles (Wi-Fi, VPN, and email certificates)</span></span>
<a id="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates" class="xliff"></a>

<span data-ttu-id="c22bb-120">Os perfis de acesso aos recursos provisionam certificados e configurações de acesso a dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="c22bb-120">Resource access profiles provision certificates and access configurations to enrolled devices.</span></span>

<span data-ttu-id="c22bb-121">Conforme abordado anteriormente na seção Avaliar os requisitos de MDM, se você estiver usando a autenticação baseada em certificado, [configure certificados](/intune/certificates-configure).</span><span class="sxs-lookup"><span data-stu-id="c22bb-121">As previously discussed in the Assess MDM requirements section, if you are using certificate-based authentication, [configure certificates](/intune/certificates-configure).</span></span>

### <span data-ttu-id="c22bb-122">Tarefa 3: Criar e implantar perfis de configuração de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c22bb-122">Task 3: Create and deploy device configuration profiles</span></span>
<a id="task-3-create-and-deploy-device-configuration-profiles" class="xliff"></a>

<span data-ttu-id="c22bb-123">Você precisa criar um perfil de configuração de dispositivo para impor as configurações no nível do dispositivo, por exemplo: desabilitar a câmera, loja de aplicativos, configurar o modo de aplicativo único, tela inicial etc.</span><span class="sxs-lookup"><span data-stu-id="c22bb-123">You need to create a device configuration profile to enforce device-level settings, for example: disable camera, app-store, configure single-app mode, home screen, etc.</span></span>

- <span data-ttu-id="c22bb-124">Saiba mais sobre [perfis de dispositivo](/intune/device-profiles).</span><span class="sxs-lookup"><span data-stu-id="c22bb-124">Learn about [device profiles](/intune/device-profiles).</span></span>

####  <span data-ttu-id="c22bb-125">Importação direta de perfis de configuração do iOS (opcional)</span><span class="sxs-lookup"><span data-stu-id="c22bb-125">Direct import of iOS configuration profiles (optional)</span></span>
<a id="direct-import-of-ios-configuration-profiles-optional" class="xliff"></a>

-   <span data-ttu-id="c22bb-126">**Perfis do Apple Configurator iOS (iOS 7.1 e posterior):** se a solução de MDM existente usar perfis do Apple Configurator (arquivos .mobileconfig), o Intune poderá importá-las diretamente como políticas de configuração do cliente.</span><span class="sxs-lookup"><span data-stu-id="c22bb-126">**Apple Configurator iOS Profiles (iOS 7.1 and later):** If your existing MDM solution uses Apple Configurator profiles (.mobileconfig files), Intune can directly import them as custom configuration policies.</span></span>

-   <span data-ttu-id="c22bb-127">**Políticas de configuração de aplicativos móveis do iOS:** se a solução de MDM existente usar políticas de configuração de aplicativos móveis do iOS, o Intune poderá importá-las diretamente desde que atendam ao formato XML especificado pela Apple para listas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="c22bb-127">**iOS Mobile Application Configuration policies:** If your existing MDM solution uses iOS Mobile Application Configuration policies, Intune can directly import them as long as they meet the XML format specified by Apple for property lists.</span></span>

- <span data-ttu-id="c22bb-128">Saiba como adicionar uma política personalizada para [iOS](/intune/custom-settings-ios)</span><span class="sxs-lookup"><span data-stu-id="c22bb-128">Learn how to add a custom policy for [iOS](/intune/custom-settings-ios)</span></span>

### <span data-ttu-id="c22bb-129">Tarefa 4: Criar e implantar uma política de conformidade do dispositivo (opcional)</span><span class="sxs-lookup"><span data-stu-id="c22bb-129">Task 4: Create and deploy device compliance policies (optional)</span></span>
<a id="task-4-create-and-deploy-device-compliance-policies-optional" class="xliff"></a>

<span data-ttu-id="c22bb-130">As políticas de conformidade do dispositivo avaliam as configurações orientadas a segurança e fornecem relatórios que mostram se os dispositivos são compatíveis com os padrões corporativos ou não.</span><span class="sxs-lookup"><span data-stu-id="c22bb-130">Device compliance policies evaluate security oriented settings, and provides reporting which shows whether the devices are compliant with corporate standards or not.</span></span> <span data-ttu-id="c22bb-131">As políticas de conformidade do dispositivo avaliam fatores de segurança orientados a segurança, como:</span><span class="sxs-lookup"><span data-stu-id="c22bb-131">Device compliance policies evaluate security oriented factors such as:</span></span>

-   <span data-ttu-id="c22bb-132">Tamanho do PIN</span><span class="sxs-lookup"><span data-stu-id="c22bb-132">PIN length</span></span>

-   <span data-ttu-id="c22bb-133">Status desbloqueado</span><span class="sxs-lookup"><span data-stu-id="c22bb-133">Jail-broken status</span></span>

-   <span data-ttu-id="c22bb-134">Versão do SO</span><span class="sxs-lookup"><span data-stu-id="c22bb-134">OS Version</span></span>

<span data-ttu-id="c22bb-135">Confira os recursos adicionais para configurações de conformidade do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c22bb-135">See additional resources for device compliance settings:</span></span>

-   <span data-ttu-id="c22bb-136">Saiba mais sobre [políticas de conformidade do dispositivo](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="c22bb-136">Learn about [device compliance policies](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune).</span></span>

-   <span data-ttu-id="c22bb-137">Saiba [como criar uma política de conformidade do dispositivo](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="c22bb-137">Learn [how to create a device compliance policy](/intune-classic/deploy-use/create-a-device-compliance-policy-in-microsoft-intune).</span></span>

### <span data-ttu-id="c22bb-138">Tarefa 5: Publicar e implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="c22bb-138">Task 5: Publish and deploy Apps</span></span>
<a id="task-5-publish-and-deploy-apps" class="xliff"></a>

<span data-ttu-id="c22bb-139">Com o Intune MDM, você pode provisionar aplicativos exigindo a instalação automática deles, ou disponibilizá-los no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="c22bb-139">When using Intune MDM, you can provision apps by either requiring their automatic installation, or making them available in the Company Portal.</span></span>

-   <span data-ttu-id="c22bb-140">Saiba [como adicionar aplicativos](/intune-classic/deploy-use/add-apps).</span><span class="sxs-lookup"><span data-stu-id="c22bb-140">Learn [how to add apps](/intune-classic/deploy-use/add-apps).</span></span>

-   <span data-ttu-id="c22bb-141">Saiba [como implantar aplicativos](/intune-classic/deploy-use/deploy-apps).</span><span class="sxs-lookup"><span data-stu-id="c22bb-141">Learn [how to deploy apps](/intune-classic/deploy-use/deploy-apps).</span></span>

### <span data-ttu-id="c22bb-142">Tarefa 6: Habilitar o registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c22bb-142">Task 6: Enable device enrollment</span></span>
<a id="task-6-enable-device-enrollment" class="xliff"></a>

<span data-ttu-id="c22bb-143">O registro estabelece o gerenciamento pelo provisionamento de controle no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c22bb-143">Enrollment establishes management by provisioning control on the device.</span></span> <span data-ttu-id="c22bb-144">Saiba [como se preparar para registrar dispositivos corporativos e pessoais](/intune/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="c22bb-144">Learn [how to get ready to enroll corporate-owned and user personal's devices](/intune/device-enrollment).</span></span>

## <span data-ttu-id="c22bb-145">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c22bb-145">Next steps</span></span>
<a id="next-steps" class="xliff"></a> 

[<span data-ttu-id="c22bb-146">Configurar Políticas de Proteção de Aplicativo (opcional)</span><span class="sxs-lookup"><span data-stu-id="c22bb-146">Configure App Protection Policies (optional)</span></span>](migration-guide-app-protection-policies.md)
