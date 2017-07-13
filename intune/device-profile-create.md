---
title: "Criar perfis de configuração de dispositivo do Intune"
titleSuffix: Intune on Azure
description: "Saiba como criar perfis de configuração de dispositivo do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6df6813667241d3ad5f8768585f2e1a34f0fe6e3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="290c4-103">Como criar perfis de configuração do dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="290c4-103">How to create device configuration profiles in Microsoft Intune</span></span>
<a id="how-to-create-device-configuration-profiles-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. <span data-ttu-id="290c4-104">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="290c4-104">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="290c4-105">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="290c4-105">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="290c4-106">Na folha **Intune**, escolha **Configurar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="290c4-106">On the **Intune** blade, choose **Configure devices**.</span></span>
2. <span data-ttu-id="290c4-107">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="290c4-107">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="290c4-108">Na folha que mostra a lista de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="290c4-108">On the blade showing the list of profiles, choose **Create Profile**.</span></span>
3. <span data-ttu-id="290c4-109">Na folha **Criar Perfil**, especifique os seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="290c4-109">On the **Create Profile** blade, specify the following items:</span></span>
    - <span data-ttu-id="290c4-110">**Nome** – Insira um nome descritivo para o novo perfil.</span><span class="sxs-lookup"><span data-stu-id="290c4-110">**Name** - Enter a descriptive name for the new profile.</span></span>
    - <span data-ttu-id="290c4-111">**Descrição** – Insira uma descrição opcional para o perfil.</span><span class="sxs-lookup"><span data-stu-id="290c4-111">**Description** -  Enter an optional description for the profile.</span></span>
    - <span data-ttu-id="290c4-112">**Plataforma** – Selecione o tipo de plataforma para o perfil que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="290c4-112">**Platform** -  Select the platform type for the profile you want to create.</span></span>
    - <span data-ttu-id="290c4-113">**Tipo de perfil** – Selecione o tipo de perfil que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="290c4-113">**Profile type** - Select the type of profile you want to create.</span></span> <span data-ttu-id="290c4-114">A lista de tipos disponíveis varia dependendo da plataforma escolhida.</span><span class="sxs-lookup"><span data-stu-id="290c4-114">The list of available types differs depending on the platform you chose.</span></span>
    - <span data-ttu-id="290c4-115">**Configurações** – Consulte os seguintes tópicos para obter informações sobre as configurações para cada tipo de perfil:</span><span class="sxs-lookup"><span data-stu-id="290c4-115">**Settings** - See the following topics for information about the settings for each profile type:</span></span>
        -  [<span data-ttu-id="290c4-116">Configurações de recurso do dispositivo</span><span class="sxs-lookup"><span data-stu-id="290c4-116">Device feature settings</span></span>](device-features-configure.md)
        -  [<span data-ttu-id="290c4-117">Configurações de restrição de dispositivo</span><span class="sxs-lookup"><span data-stu-id="290c4-117">Device restriction settings</span></span>](device-restrictions-configure.md)
        -  [<span data-ttu-id="290c4-118">Configurações de email</span><span class="sxs-lookup"><span data-stu-id="290c4-118">Email settings</span></span>](email-settings-configure.md)
        -  [<span data-ttu-id="290c4-119">Configurações de VPN</span><span class="sxs-lookup"><span data-stu-id="290c4-119">VPN settings</span></span>](vpn-settings-configure.md)
        -  [<span data-ttu-id="290c4-120">Configurações de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="290c4-120">Wi-Fi settings</span></span>](wi-fi-settings-configure.md)
        -  [<span data-ttu-id="290c4-121">Configurações de atualização da edição do Windows 10</span><span class="sxs-lookup"><span data-stu-id="290c4-121">Windows 10 edition upgrade settings</span></span>](edition-upgrade-configure-windows-10.md)
        -  [<span data-ttu-id="290c4-122">Configurações do certificado</span><span class="sxs-lookup"><span data-stu-id="290c4-122">Certificate settings</span></span>](certificates-configure.md)
        -  [<span data-ttu-id="290c4-123">Definir a Proteção de Informações do Windows</span><span class="sxs-lookup"><span data-stu-id="290c4-123">Windows Information Protection settings</span></span>](windows-information-protection-configure.md)
        -  [<span data-ttu-id="290c4-124">Configurações de educação</span><span class="sxs-lookup"><span data-stu-id="290c4-124">Education settings</span></span>](education-settings-configure.md)
        -  [<span data-ttu-id="290c4-125">Configurações personalizadas</span><span class="sxs-lookup"><span data-stu-id="290c4-125">Custom settings</span></span>](custom-settings-configure.md)

    ![Criar perfil de dispositivo](./media/create-device-profile.png)
4. <span data-ttu-id="290c4-127">Depois de terminar de definir as configurações, na folha **Criar Perfil**, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="290c4-127">Once you are done configuring settings, on the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="290c4-128">O perfil é criado e exibido na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="290c4-128">The profile is created and appears on the profiles list blade.</span></span>
<span data-ttu-id="290c4-129">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="290c4-129">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>


### <span data-ttu-id="290c4-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="290c4-130">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="290c4-131">Para obter informações sobre como atribuir perfis de dispositivo, consulte [Como atribuir perfis de dispositivos com o Microsoft Intune](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="290c4-131">For information about how to assign device profiles, see [How to assign device profiles with Microsoft Intune](device-profile-assign.md).</span></span>
