---
title: "Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10"
description: "Provedor de instalação do gerenciamento de aplicativos móveis (MAM) no Azure AD"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5f159ead358807872b5099bb9c670f372eed401e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7d631-103">Prepare-se para configurar as políticas de proteção do aplicativo para Windows 10</span><span class="sxs-lookup"><span data-stu-id="7d631-103">Get ready to configure app protection policies for Windows 10</span></span>
<a id="get-ready-to-configure-app-protection-policies-for-windows-10" class="xliff"></a>

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="7d631-104">Antes de criar uma política de proteção de aplicativo do Windows 10, você precisará habilitar o gerenciamento de aplicativos móveis (MAM) para o Windows 10 configurando o provedor de MAM no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="7d631-104">Before creating a Windows 10 app protection policy using, you need to enable mobile application management (MAM) for Windows 10 by setting up the MAM provider in Azure AD.</span></span> <span data-ttu-id="7d631-105">Essa configuração permite definir o estado do registro ao criar uma nova política do WIP (Proteção de Informações do Windows) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="7d631-105">This configuration allows you to define the enrollment state when creating a new Windows Information Protection (WIP) policy with Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="7d631-106">O estado do registro pode ser MAM ou MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="7d631-106">The enrollment state can be either MAM or mobile device management (MDM).</span></span>

## <span data-ttu-id="7d631-107">Para configurar o provedor de MAM</span><span class="sxs-lookup"><span data-stu-id="7d631-107">To configure the MAM provider</span></span>
<a id="to-configure-the-mam-provider" class="xliff"></a>

1.  <span data-ttu-id="7d631-108">Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="7d631-108">Go to the [Azure portal](https://portal.azure.com/) and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="7d631-109">No menu à esquerda, escolha **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7d631-109">From the left menu, choose **Azure Active Directory**.</span></span>

    ![Configuração do provedor do MAM](../media/AppManagement/mam-provider-sc-1.png)

3.  <span data-ttu-id="7d631-111">A folha **Azure AD** é aberta, escolha **Mobilidade (MDM e MAM)**, em seguida, clique em **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="7d631-111">**Azure AD** blade opens, choose **Mobility (MDM and MAM)**, then click **Microsoft Intune**.</span></span>

    ![Mobilidade MDM e MAM](../media/AppManagement/mam-provider-sc-2.png)

4.  <span data-ttu-id="7d631-113">A folha de configuração é aberta, escolha **Restaurar as URLs padrão do MAM** primeiro, em seguida, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7d631-113">The configure blade opens, choose **Restore default MAM URLs** first, then configure the following:</span></span>

    <span data-ttu-id="7d631-114">a.</span><span class="sxs-lookup"><span data-stu-id="7d631-114">a.</span></span>  <span data-ttu-id="7d631-115">Escopo do usuário de MAM: você pode usar o MAM para proteger dados corporativos em um grupo específico de usuários que usam dispositivos com Windows 10 ou todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="7d631-115">MAM user scope: You can use MAM to protect corporate data on specific group of users that use Windows 10 devices or all users.</span></span>

    <span data-ttu-id="7d631-116">b.</span><span class="sxs-lookup"><span data-stu-id="7d631-116">b.</span></span>  <span data-ttu-id="7d631-117">URL de termos de uso do MAM: a URL do ponto de extremidade dos termos de uso do serviço MAM.</span><span class="sxs-lookup"><span data-stu-id="7d631-117">MAM terms of use URL: The URL of the terms of use endpoint of the MAM service.</span></span> <span data-ttu-id="7d631-118">Isso é usado para exibir os termos do serviço MAM para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="7d631-118">This is used to display the term of MAM service to end-users.</span></span>

    <span data-ttu-id="7d631-119">c.</span><span class="sxs-lookup"><span data-stu-id="7d631-119">c.</span></span>  <span data-ttu-id="7d631-120">URL de descoberta de MAM: essa é a URL que os dispositivos buscam quando precisam aplicar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7d631-120">MAM discovery URL: This the URL devices seek when they need to apply app protection policies.</span></span>

    <span data-ttu-id="7d631-121">d.</span><span class="sxs-lookup"><span data-stu-id="7d631-121">d.</span></span>  <span data-ttu-id="7d631-122">URL de conformidade do MAM:</span><span class="sxs-lookup"><span data-stu-id="7d631-122">MAM compliance URL:</span></span>

5.  <span data-ttu-id="7d631-123">Quando você tiver definido essas configurações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7d631-123">Once you configure these settings, choose **Save**.</span></span>

## <span data-ttu-id="7d631-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7d631-124">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="7d631-125">Criar uma política de proteção de aplicativo WIP</span><span class="sxs-lookup"><span data-stu-id="7d631-125">Create a WIP app protection policy</span></span>](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)
