---
title: "Configuração básica do Intune"
description: "A finalidade deste artigo é fornecer as etapas necessárias para configurar o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c3129b2a8d93e91493455da5f3e5fd1a59dd77bb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c9f1a-103">Configuração básica</span><span class="sxs-lookup"><span data-stu-id="c9f1a-103">Basic setup</span></span>
<a id="basic-setup" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="c9f1a-104">Depois de avaliar seu ambiente, é hora de configurar o Intune.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-104">After you assess your environment, it’s time to setup Intune.</span></span>

## <span data-ttu-id="c9f1a-105">Dependências externas para uma implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="c9f1a-105">External dependencies for an Intune deployment</span></span>
<a id="external-dependencies-for-an-intune-deployment" class="xliff"></a>

### <span data-ttu-id="c9f1a-106">Identidade</span><span class="sxs-lookup"><span data-stu-id="c9f1a-106">Identity</span></span>
<a id="identity" class="xliff"></a>

<span data-ttu-id="c9f1a-107">O Intune exige o AAD (Azure Active Directory) como o provedor de identidade e agrupamento de usuário.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-107">Intune requires Azure Active Directory (AAD) as the identity and user grouping provider.</span></span>

-   <span data-ttu-id="c9f1a-108">Saiba mais sobre os [requisitos de identidade](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-108">Learn more about [identity requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview).</span></span>

-   <span data-ttu-id="c9f1a-109">Saiba mais sobre os [requisitos de sincronização de diretório](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-109">Learn more about [directory synchronization requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements).</span></span>

-   <span data-ttu-id="c9f1a-110">Saiba mais sobre os [requisitos de autenticação multifator](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-110">Learn more about [multi-factor authentication requirements](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements).</span></span>

-   <span data-ttu-id="c9f1a-111">Saiba mais sobre como [planejar os grupos de usuários e de dispositivos](/intune/users-permissions-add).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-111">Learn more about [planning your user and device groups](/intune/users-permissions-add).</span></span>

-   <span data-ttu-id="c9f1a-112">Saiba [como criar grupos de usuários e de dispositivos](/intune/groups-get-started).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-112">Learn [how to create user and device groups](/intune/groups-get-started).</span></span>

<span data-ttu-id="c9f1a-113">Caso sua organização já esteja usando o Office 365, é importante que o Intune use o mesmo ambiente do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-113">If your organization is already using Office 365, it’s important that Intune uses the same Azure Active Directory environment.</span></span>

### <span data-ttu-id="c9f1a-114">PKI (opcional)</span><span class="sxs-lookup"><span data-stu-id="c9f1a-114">PKI (optional)</span></span>
<a id="pki-optional" class="xliff"></a>

<span data-ttu-id="c9f1a-115">Se você estiver planejando usar a autenticação com base em certificados para perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](/intune/certificates-configure) com suporte, pronta para criar e implantar perfis de certificado.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-115">If you're planning to use certificate-based authentication for VPN, Wi-Fi, or e-mail profiles with Intune, you’ll need to make sure that you have a supported [PKI infrastructure in place](/intune/certificates-configure), ready to create and deploy certificate profiles.</span></span>

<span data-ttu-id="c9f1a-116">Confira abaixo mais informações sobre como configurar certificados no Intune.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-116">More information about configuring certificates in Intune is below.</span></span>

-   <span data-ttu-id="c9f1a-117">[Configurar a infraestrutura de certificado para SCEP](/intune/certificates-scep-configure).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-117">[How to configure the certificate infrastructure for SCEP](/intune/certificates-scep-configure).</span></span>

-   <span data-ttu-id="c9f1a-118">[Configurar a infraestrutura de certificado](/intune/certficates-pfx-configure).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-118">[How to configure the certificate infrastructure for PFX](/intune/certficates-pfx-configure).</span></span>


## <span data-ttu-id="c9f1a-119">Lista de tarefas para uma configuração do Intune</span><span class="sxs-lookup"><span data-stu-id="c9f1a-119">Task list for an Intune Setup</span></span>
<a id="task-list-for-an-intune-setup" class="xliff"></a>

### <span data-ttu-id="c9f1a-120">Tarefa 1: Assinatura do Intune</span><span class="sxs-lookup"><span data-stu-id="c9f1a-120">Task 1: Intune subscription</span></span>
<a id="task-1-intune-subscription" class="xliff"></a>

<span data-ttu-id="c9f1a-121">Antes de migrar para o Intune, primeiro você precisa de uma assinatura do Intune.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-121">Before you can migrate to Intune, you first need an Intune subscription.</span></span>

-   <span data-ttu-id="c9f1a-122">Visite [esta página](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), que fornece instruções sobre como:</span><span class="sxs-lookup"><span data-stu-id="c9f1a-122">You can visit [this page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), which gives you instructions on how to:</span></span>

    -   <span data-ttu-id="c9f1a-123">Criar uma nova assinatura do Intune vinculada a um novo locatário do AAD.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-123">Create a new Intune subscription linked to a new AAD tenant.</span></span>

    -   <span data-ttu-id="c9f1a-124">Vincular a assinatura do Intune entrando em um locatário do AAD existente.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-124">Link the Intune subscription by signing into an existing AAD tenant.</span></span>

### <span data-ttu-id="c9f1a-125">Etapa 2: Atribuir licenças de usuário do Intune</span><span class="sxs-lookup"><span data-stu-id="c9f1a-125">Task 2: Assign Intune user licenses</span></span>
<a id="task-2-assign-intune-user-licenses" class="xliff"></a>

-   <span data-ttu-id="c9f1a-126">Saiba [como atribuir licenças de usuário do Intune](licenses-assign.md).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-126">Learn [how to assign Intune user licenses](licenses-assign.md).</span></span>

-   <span data-ttu-id="c9f1a-127">Se você tiver criado um novo locatário do Azure Active Directory, saiba [como criar novos usuários ou sincronizar usuários de seu AD (Active Directory) local.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="c9f1a-127">If you have created a new Azure Active Directory tenant, learn [how to create new users or sync user from your on-premises Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span></span>

### <span data-ttu-id="c9f1a-128">Tarefa 3: Definir sua autoridade de MDM para o Intune</span><span class="sxs-lookup"><span data-stu-id="c9f1a-128">Task 3: Set your MDM authority to Intune</span></span>
<a id="task-3-set-your-mdm-authority-to-intune" class="xliff"></a>

<span data-ttu-id="c9f1a-129">O Intune pode ser gerenciado por meio do portal do Azure ou do console do Branch Atual do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-129">Intune can be managed through the Azure portal or the Configuration Manager Current Branch console.</span></span> <span data-ttu-id="c9f1a-130">A menos que você precise integrar o Intune a uma implantação do Branch Atual do Configuration Manager, recomendamos o gerenciamento do Intune no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-130">Unless you need to integrate Intune with a Configuration Manager Current Branch deployment, it is recommended to manage Intune from the [Azure Portal](https://portal.azure.com).</span></span>

<span data-ttu-id="c9f1a-131">Defina sua autoridade de MDM como **Intune** para habilitar o Portal do Azure no Intune.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-131">Set your MDM authority to **Intune** to enable the Intune Azure Portal.</span></span> <span data-ttu-id="c9f1a-132">O uso de uma autoridade de MDM diferente permite que o Intune transfira o gerenciamento do MDM para consoles de gerenciamento alternativos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-132">Using a different MDM authority allows Intune to transfer MDM management to alternate Microsoft management consoles.</span></span> <span data-ttu-id="c9f1a-133">Esses casos são incomuns.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-133">These cases are uncommon.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9f1a-134">Se você estiver transferindo seu gerenciamento de dispositivos móvel para o Intune pela primeira vez, defina a autoridade de MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="c9f1a-134">If you are transferring your mobile device management to Intune for the first time, you should set the MDM authority to Intune.</span></span>

-   <span data-ttu-id="c9f1a-135">Saiba [como definir a autoridade de gerenciamento móvel](/intune/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="c9f1a-135">Learn [how to set the mobile management authority](/intune/mdm-authority-set).</span></span>

## <span data-ttu-id="c9f1a-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c9f1a-136">Next step</span></span>
<a id="next-step" class="xliff"></a>

[<span data-ttu-id="c9f1a-137">Configurar políticas de gerenciamento de dispositivos e aplicativos</span><span class="sxs-lookup"><span data-stu-id="c9f1a-137">Configure device and app management policies</span></span>](migration-guide-configure-policies.md)
