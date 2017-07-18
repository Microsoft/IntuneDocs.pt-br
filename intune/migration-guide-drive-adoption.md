---
title: "<span data-ttu-id=\"266a1-101\">Gerar adoção de usuário final com acesso condicional</span><span class=\"sxs-lookup\"><span data-stu-id=\"266a1-101\">Drive end-user adoption with conditional access</span></span>"
description: "<span data-ttu-id=\"266a1-102\">Este artigo fornece informações sobre como usar o acesso condicional para gerar o registro no Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"266a1-102\">This article provides insights on how to use conditional access to drive Intune enrollment.</span></span>"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7a9c3bef955239ad653a9ca45c55c533be36c5ce
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a><span data-ttu-id="266a1-103">Gerar adoção de usuário final com acesso condicional</span><span class="sxs-lookup"><span data-stu-id="266a1-103">Drive end-user adoption with conditional access</span></span>

<span data-ttu-id="266a1-104">A habilitação de recursos de acesso condicional com o Intune, tal como o bloqueio de email para dispositivos não registrados, pode ajudar a gerar registro e conformidade, mas isso não é obrigatório para o sucesso da migração.</span><span class="sxs-lookup"><span data-stu-id="266a1-104">Enabling conditional access features with Intune, such as blocking email for unenrolled devices, can help drive enrollment and compliance but they are not required for a migration to be successful.</span></span> <span data-ttu-id="266a1-105">Seus objetivos para a adoção da migração e os requisitos de segurança devem determinar o sucesso.</span><span class="sxs-lookup"><span data-stu-id="266a1-105">Your migration adoption goals and security requirements should dictate the success.</span></span>

## <a name="migration-campaign-with-conditional-access"></a><span data-ttu-id="266a1-106">Campanha de migração com acesso condicional</span><span class="sxs-lookup"><span data-stu-id="266a1-106">Migration campaign with conditional access</span></span>

<span data-ttu-id="266a1-107">Está é uma abordagem típica para aprimorar uma campanha de migração com acesso condicional:</span><span class="sxs-lookup"><span data-stu-id="266a1-107">Here is a typical approach to enhancing a migration campaign with conditional access:</span></span>

1.  <span data-ttu-id="266a1-108">Defina as regras de acesso condicional que serão aplicadas a todos os usuários, mas exclua especificamente os usuários que precisam migrar do provedor de MDM antigo.</span><span class="sxs-lookup"><span data-stu-id="266a1-108">Set conditional access rules to be enforced for all users but specifically exclude the users who need to migrate from the old MDM provider.</span></span> <span data-ttu-id="266a1-109">Você pode criar um grupo de usuários do Azure AD com todos os usuários com acesso condicional excluído.</span><span class="sxs-lookup"><span data-stu-id="266a1-109">You can create an Azure AD user group with all conditional access excluded users.</span></span>

2.  <span data-ttu-id="266a1-110">À medida que os usuários migrarem, remova-os do grupo de exclusão de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="266a1-110">As users migrate, remove them from the conditional access exclusion group.</span></span>

3.  <span data-ttu-id="266a1-111">Após a conclusão da migração, configure todas as políticas de acesso condicional para bloquear por padrão, a menos que o Intune permita o acesso.</span><span class="sxs-lookup"><span data-stu-id="266a1-111">After migration completes, configure all conditional access policies to block by default unless Intune allows access.</span></span>

### <a name="advantages"></a><span data-ttu-id="266a1-112">Vantagens</span><span class="sxs-lookup"><span data-stu-id="266a1-112">Advantages</span></span>

-   <span data-ttu-id="266a1-113">Fornece controle de acesso para novas contas de usuário ou para contas de usuário que não eram gerenciadas pela solução anterior.</span><span class="sxs-lookup"><span data-stu-id="266a1-113">Provides access control for new user accounts or user account who were not managed by the previous solution.</span></span>

-   <span data-ttu-id="266a1-114">Fornece um período de carência para migração aos usuários da solução anterior.</span><span class="sxs-lookup"><span data-stu-id="266a1-114">Provides grace period for users of previous solution to migration.</span></span>

-   <span data-ttu-id="266a1-115">Minimiza a perda de produtividade</span><span class="sxs-lookup"><span data-stu-id="266a1-115">Minimizes loss of productivity</span></span>

### <a name="disadvantages"></a><span data-ttu-id="266a1-116">Desvantagens</span><span class="sxs-lookup"><span data-stu-id="266a1-116">Disadvantages</span></span>

-   <span data-ttu-id="266a1-117">Os usuários da solução anterior poderiam acessar recursos usando dispositivos não gerenciados até que o acesso condicional fosse habilitado para eles.</span><span class="sxs-lookup"><span data-stu-id="266a1-117">Users of previous solution could potentially access resources using unmanaged devices until conditional access is enabled for those users.</span></span>


<span data-ttu-id="266a1-118">Essa é uma abordagem entre várias.</span><span class="sxs-lookup"><span data-stu-id="266a1-118">This is one approach among many.</span></span> <span data-ttu-id="266a1-119">Você pode escolher um processo mais simples que adia todo o acesso condicional até que cada fase tenha sido instruída para o registro, ou um processo mais rígido que garante o acesso condicional desde o começo e exige conformidade total para todos os acessos.</span><span class="sxs-lookup"><span data-stu-id="266a1-119">You may choose a simpler process that defers all conditional access until after every phase has been instructed to enroll, or a stricter process that enforces conditional access from the very beginning and requires full compliance for all access.</span></span>

-   <span data-ttu-id="266a1-120">Saiba mais sobre o [acesso condicional](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="266a1-120">Learn more about [conditional access](conditional-access.md).</span></span>

## <a name="task-list-for-conditional-access"></a><span data-ttu-id="266a1-121">Lista de tarefas para acesso condicional</span><span class="sxs-lookup"><span data-stu-id="266a1-121">Task list for conditional access</span></span>

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a><span data-ttu-id="266a1-122">Tarefa 1: Decidir como você pretende implementar o acesso condicional</span><span class="sxs-lookup"><span data-stu-id="266a1-122">Task 1: Decide how you are going to implement conditional access</span></span>

<span data-ttu-id="266a1-123">[Maneiras comuns de usar o acesso condicional](conditional-access-intune-common-ways-use.md).</span><span class="sxs-lookup"><span data-stu-id="266a1-123">[Common ways to use conditional access](conditional-access-intune-common-ways-use.md).</span></span>

### <a name="task-2-set-up-intune-conditional-access"></a><span data-ttu-id="266a1-124">Tarefa 2: Configurar o acesso condicional do Intune</span><span class="sxs-lookup"><span data-stu-id="266a1-124">Task 2: Set up Intune conditional access</span></span>

<span data-ttu-id="266a1-125">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="266a1-125">Choose one of the following options:</span></span>

-   [<span data-ttu-id="266a1-126">Configurar o acesso condicional no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="266a1-126">Configure conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [<span data-ttu-id="266a1-127">Instalar o Exchange Connector local com o Intune</span><span class="sxs-lookup"><span data-stu-id="266a1-127">Install on-premises Exchange connector with Intune</span></span>](exchange-connector-install.md)

-   [<span data-ttu-id="266a1-128">Configurar políticas de acesso condicional baseado no aplicativo para o Exchange Online</span><span class="sxs-lookup"><span data-stu-id="266a1-128">Set up app-based conditional access policies for Exchange Online</span></span>](app-based-conditional-access-intune-create.md)

-   [<span data-ttu-id="266a1-129">Configurar políticas de acesso condicional baseado no aplicativo para o SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="266a1-129">Set up app-based conditional access policies for SharePoint Online</span></span>](app-based-conditional-access-intune-create.md)

-   [<span data-ttu-id="266a1-130">Bloquear aplicativos que não usam autenticação moderna (ADAL)</span><span class="sxs-lookup"><span data-stu-id="266a1-130">Block apps that do not use modern authentication (ADAL)</span></span>](app-modern-authentication-block.md)

## <a name="next-steps"></a><span data-ttu-id="266a1-131">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="266a1-131">Next steps</span></span>

<span data-ttu-id="266a1-132">Saiba mais sobre o [ciclo de migração típico](migration-guide-cycle.md).</span><span class="sxs-lookup"><span data-stu-id="266a1-132">Learn about the [typical migration cycle](migration-guide-cycle.md).</span></span>
