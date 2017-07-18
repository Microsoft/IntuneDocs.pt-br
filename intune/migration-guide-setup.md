---
title: "<span data-ttu-id=\"3eb8d-101\">Configuração básica do Intune</span><span class=\"sxs-lookup\"><span data-stu-id=\"3eb8d-101\">Intune basic setup</span></span>"
description: "<span data-ttu-id=\"3eb8d-102\">Este artigo fornece as etapas necessárias para configurar o Microsoft Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"3eb8d-102\">This article provides the necessary steps to set up Microsoft Intune.</span></span>"
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
ms.openlocfilehash: 9ea12f3707b830f0e3426526a7ae91d176d6e809
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="basic-setup"></a><span data-ttu-id="3eb8d-103">Configuração básica</span><span class="sxs-lookup"><span data-stu-id="3eb8d-103">Basic setup</span></span>

<span data-ttu-id="3eb8d-104">Depois de avaliar seu ambiente, é hora de configurar o Intune.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-104">After you assess your environment, it’s time to set up Intune.</span></span>

## <a name="external-dependencies-for-an-intune-deployment"></a><span data-ttu-id="3eb8d-105">Dependências externas para uma implantação do Intune</span><span class="sxs-lookup"><span data-stu-id="3eb8d-105">External dependencies for an Intune deployment</span></span>

### <a name="identity"></a><span data-ttu-id="3eb8d-106">Identidade</span><span class="sxs-lookup"><span data-stu-id="3eb8d-106">Identity</span></span>

<span data-ttu-id="3eb8d-107">O Intune exige o AAD (Azure Active Directory) como o provedor de identidade e agrupamento de usuário.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-107">Intune requires Azure Active Directory (AAD) as the identity and user grouping provider.</span></span> <span data-ttu-id="3eb8d-108">Saiba mais sobre:</span><span class="sxs-lookup"><span data-stu-id="3eb8d-108">Learn more about:</span></span>

-  [<span data-ttu-id="3eb8d-109">Requisitos de identidade</span><span class="sxs-lookup"><span data-stu-id="3eb8d-109">Identity requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [<span data-ttu-id="3eb8d-110">Requisitos de sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="3eb8d-110">Directory synchronization requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [<span data-ttu-id="3eb8d-111">Requisitos de MFA (autenticação multifator)</span><span class="sxs-lookup"><span data-stu-id="3eb8d-111">Multi-factor authentication (MFA) requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   [<span data-ttu-id="3eb8d-112">Planejar seus grupos de dispositivos e de usuários</span><span class="sxs-lookup"><span data-stu-id="3eb8d-112">Planning your user and device groups</span></span>](users-add.md)

-   [<span data-ttu-id="3eb8d-113">Como criar grupos de dispositivos e de usuários</span><span class="sxs-lookup"><span data-stu-id="3eb8d-113">How to create user and device groups</span></span>](groups-get-started.md)

<span data-ttu-id="3eb8d-114">Se sua organização já estiver usando o Office 365, o Intune deverá usar o mesmo ambiente do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-114">If your organization is already using Office 365, Intune must use the same Azure Active Directory environment.</span></span>

### <a name="pki-optional"></a><span data-ttu-id="3eb8d-115">PKI (opcional)</span><span class="sxs-lookup"><span data-stu-id="3eb8d-115">PKI (optional)</span></span>

<span data-ttu-id="3eb8d-116">Se você estiver planejando usar a autenticação com base em certificados para perfis de VPN, Wi-Fi ou email com o Intune, verifique se você tem uma [infraestrutura de PKI em vigor](certificates-configure.md) com suporte, pronta para criar e implantar perfis de certificado.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-116">If you're planning to use certificate-based authentication for VPN, Wi-Fi, or e-mail profiles with Intune, you’ll need to make sure that you have a supported [PKI infrastructure in place](certificates-configure.md), ready to create and deploy certificate profiles.</span></span> <span data-ttu-id="3eb8d-117">Saiba mais sobre como configurar certificados no Intune:</span><span class="sxs-lookup"><span data-stu-id="3eb8d-117">Learn more about configuring certificates in Intune:</span></span>

-   [<span data-ttu-id="3eb8d-118">Como configurar a infraestrutura de certificado para SCEP</span><span class="sxs-lookup"><span data-stu-id="3eb8d-118">How to configure the certificate infrastructure for SCEP</span></span>](/intune/certificates-scep-configure)

-   <span data-ttu-id="3eb8d-119">[Configurar a infraestrutura de certificado](/intune/certficates-pfx-configure).</span><span class="sxs-lookup"><span data-stu-id="3eb8d-119">[How to configure the certificate infrastructure for PFX](/intune/certficates-pfx-configure).</span></span>


## <a name="task-list-for-an-intune-setup"></a><span data-ttu-id="3eb8d-120">Lista de tarefas para uma configuração do Intune</span><span class="sxs-lookup"><span data-stu-id="3eb8d-120">Task list for an Intune setup</span></span>

### <a name="task-1-intune-subscription"></a><span data-ttu-id="3eb8d-121">Tarefa 1: Assinatura do Intune</span><span class="sxs-lookup"><span data-stu-id="3eb8d-121">Task 1: Intune subscription</span></span>

<span data-ttu-id="3eb8d-122">Antes de migrar para o Intune, primeiro você precisa de uma assinatura do Intune.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-122">Before you can migrate to Intune, you first need an Intune subscription.</span></span>

-   <span data-ttu-id="3eb8d-123">Visite [esta página](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), que fornece instruções sobre como:</span><span class="sxs-lookup"><span data-stu-id="3eb8d-123">You can visit [this page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), which gives you instructions on how to:</span></span>

    -   <span data-ttu-id="3eb8d-124">Criar uma nova assinatura do Intune vinculada a um novo locatário do AAD.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-124">Create a new Intune subscription linked to a new AAD tenant.</span></span>

    -   <span data-ttu-id="3eb8d-125">Vincular a assinatura do Intune entrando em um locatário do AAD existente.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-125">Link the Intune subscription by signing into an existing AAD tenant.</span></span>

### <a name="task-2-assign-intune-user-licenses"></a><span data-ttu-id="3eb8d-126">Etapa 2: Atribuir licenças de usuário do Intune</span><span class="sxs-lookup"><span data-stu-id="3eb8d-126">Task 2: Assign Intune user licenses</span></span>

-   <span data-ttu-id="3eb8d-127">Saiba [como atribuir licenças de usuário do Intune](licenses-assign.md).</span><span class="sxs-lookup"><span data-stu-id="3eb8d-127">Learn [how to assign Intune user licenses](licenses-assign.md).</span></span>

-   <span data-ttu-id="3eb8d-128">Se você tiver criado um novo locatário do Azure Active Directory, saiba [como criar novos usuários ou sincronizar usuários de seu AD (Active Directory) local.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="3eb8d-128">If you have created a new Azure Active Directory tenant, learn [how to create new users or sync user from your on-premises Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span></span>

### <a name="task-3-set-your-mdm-authority-to-intune"></a><span data-ttu-id="3eb8d-129">Tarefa 3: Definir sua autoridade de MDM para o Intune</span><span class="sxs-lookup"><span data-stu-id="3eb8d-129">Task 3: Set your MDM authority to Intune</span></span>

<span data-ttu-id="3eb8d-130">O Intune pode ser gerenciado por meio do portal do Azure ou do console do Branch Atual do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-130">Intune can be managed through the Azure portal or the Configuration Manager Current Branch console.</span></span> <span data-ttu-id="3eb8d-131">A menos que você precise integrar o Intune a uma implantação do Branch Atual do Configuration Manager, recomendamos que você gerencie o Intune do [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="3eb8d-131">Unless you need to integrate Intune with a Configuration Manager Current Branch deployment, we recommend that you manage Intune from the [Azure portal](https://portal.azure.com).</span></span>

<span data-ttu-id="3eb8d-132">Defina sua autoridade de MDM como **Intune** para habilitar o Portal do Azure no Intune.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-132">Set your MDM authority to **Intune** to enable the Intune Azure portal.</span></span> <span data-ttu-id="3eb8d-133">O uso de uma autoridade de MDM diferente permite que o Intune transfira o gerenciamento do MDM para consoles de gerenciamento alternativos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-133">Using a different MDM authority allows Intune to transfer MDM management to alternate Microsoft management consoles.</span></span> <span data-ttu-id="3eb8d-134">Esses casos são incomuns.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-134">These cases are uncommon.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3eb8d-135">Se você estiver transferindo seu gerenciamento de dispositivos móvel para o Intune pela primeira vez, defina a autoridade de MDM como Intune.</span><span class="sxs-lookup"><span data-stu-id="3eb8d-135">If you are transferring your mobile device management to Intune for the first time, you should set the MDM authority to Intune.</span></span>

<span data-ttu-id="3eb8d-136">Saiba [como definir a autoridade de gerenciamento móvel](mdm-authority-set.md).</span><span class="sxs-lookup"><span data-stu-id="3eb8d-136">Learn [how to set the mobile management authority](mdm-authority-set.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="3eb8d-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3eb8d-137">Next step</span></span>

<span data-ttu-id="3eb8d-138">Configure [políticas de gerenciamento de dispositivos e aplicativos](migration-guide-configure-policies.md).</span><span class="sxs-lookup"><span data-stu-id="3eb8d-138">Configure [device and app management policies](migration-guide-configure-policies.md).</span></span>
