---
title: "Usar políticas para simplificar o gerenciamento de computador Windows"
description: "Descreve as políticas de gerenciamento de computador Windows e as configurações para o Microsoft Intune Center."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e14b5c56356812fdc3ea775cddde0f668b344177
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="92887-103">Usar políticas para simplificar o gerenciamento de computador Windows</span><span class="sxs-lookup"><span data-stu-id="92887-103">Use policies to simplify Windows PC management</span></span>
<a id="use-policies-to-simplify-windows-pc-management" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="92887-104">Para gerenciar áreas de trabalho do Windows como computadores executando o cliente de software do Intune nelas, é possível usar apenas as políticas que estão sob as políticas **Gerenciamento do Computador** no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="92887-104">To manage Windows desktops as PCs, by running the Intune software client on them, you can use only the policies that are under **Computer Management** policies in the Intune admin console.</span></span> <span data-ttu-id="92887-105">Todas as outras políticas listadas no console do administrador destinam-se somente a dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="92887-105">All of the other policies listed in the admin console are for mobile devices only.</span></span> <span data-ttu-id="92887-106">Usando as políticas **Gerenciamento do Computador**, é possível definir as configurações no Microsoft Intune Center, controlar as atualizações em computadores e configurar o Firewall do Windows para computadores.</span><span class="sxs-lookup"><span data-stu-id="92887-106">Using the **Computer Management** policies, you can configure the settings in the Microsoft Intune Center, control updates to PCs, and configure Windows Firewall for PCs.</span></span>

![Modelo de políticas para computadores Windows](../media/pc_policy_template.png)

### <span data-ttu-id="92887-108">Gerenciar o Microsoft Intune Center</span><span class="sxs-lookup"><span data-stu-id="92887-108">Manage the Microsoft Intune Center</span></span>
<a id="manage-the-microsoft-intune-center" class="xliff"></a>
<span data-ttu-id="92887-109">Os usuários veem o cliente de software do Intune como o **Microsoft Intune Center**.</span><span class="sxs-lookup"><span data-stu-id="92887-109">Users see the Intune software client as the **Microsoft Intune Center**.</span></span> <span data-ttu-id="92887-110">O Microsoft Intune Center permite que os usuários:</span><span class="sxs-lookup"><span data-stu-id="92887-110">The Microsoft Intune Center lets users:</span></span>

-   <span data-ttu-id="92887-111">Obtenham aplicativos a partir do portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="92887-111">Get applications from the company portal.</span></span>

-   <span data-ttu-id="92887-112">Procurem atualizações.</span><span class="sxs-lookup"><span data-stu-id="92887-112">Check for updates.</span></span>

-   <span data-ttu-id="92887-113">Gerencie o Endpoint Protection do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="92887-113">Manage Microsoft Intune Endpoint Protection.</span></span>

-  <span data-ttu-id="92887-114">Solicitem assistência remota.</span><span class="sxs-lookup"><span data-stu-id="92887-114">Request remote assistance.</span></span>

<span data-ttu-id="92887-115">O Microsoft Intune Center é instalado em todos os computadores gerenciados.</span><span class="sxs-lookup"><span data-stu-id="92887-115">The Microsoft Intune Center is installed on all managed computers.</span></span> <span data-ttu-id="92887-116">Você pode definir as seguintes configurações em uma política do Intune e elas são exibidas para os usuários no Microsoft Intune Center:</span><span class="sxs-lookup"><span data-stu-id="92887-116">You can configure the following settings in an Intune policy, and these are displayed to users in the Microsoft Intune Center:</span></span>

|<span data-ttu-id="92887-117">Configuração de política</span><span class="sxs-lookup"><span data-stu-id="92887-117">Policy setting</span></span>|<span data-ttu-id="92887-118">Detalhes</span><span class="sxs-lookup"><span data-stu-id="92887-118">Details</span></span>|
|------------------|--------------------|
|<span data-ttu-id="92887-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="92887-119">**Name**</span></span>|<span data-ttu-id="92887-120">O nome do administrador que gerencia o computador.</span><span class="sxs-lookup"><span data-stu-id="92887-120">The name of the administrator who manages the computer.</span></span><br /><span data-ttu-id="92887-121">Comprimento máximo: 40 caracteres</span><span class="sxs-lookup"><span data-stu-id="92887-121">Maximum length: 40 characters</span></span>|
|<span data-ttu-id="92887-122">**Número do telefone**</span><span class="sxs-lookup"><span data-stu-id="92887-122">**Phone number**</span></span>|<span data-ttu-id="92887-123">O número do telefone do administrador que gerencia o computador.</span><span class="sxs-lookup"><span data-stu-id="92887-123">The telephone number of the administrator who manages the computer.</span></span><br /><span data-ttu-id="92887-124">Comprimento máximo: 20 caracteres</span><span class="sxs-lookup"><span data-stu-id="92887-124">Maximum length: 20 characters</span></span>|
|<span data-ttu-id="92887-125">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="92887-125">**Email address**</span></span>|<span data-ttu-id="92887-126">O endereço de email do administrador que gerencia o computador.</span><span class="sxs-lookup"><span data-stu-id="92887-126">The email address of the administrator who manages the computer.</span></span><br /><span data-ttu-id="92887-127">Comprimento máximo: 40 caracteres</span><span class="sxs-lookup"><span data-stu-id="92887-127">Maximum length: 40 characters</span></span>|
|<span data-ttu-id="92887-128">**Nome do site**</span><span class="sxs-lookup"><span data-stu-id="92887-128">**Web site name**</span></span>|<span data-ttu-id="92887-129">O nome do site de suporte para os usuários.</span><span class="sxs-lookup"><span data-stu-id="92887-129">The name of your support website for users.</span></span><br /><span data-ttu-id="92887-130">>Comprimento máximo: 40 caracteres</span><span class="sxs-lookup"><span data-stu-id="92887-130">>Maximum length: 40 characters</span></span>|
|<span data-ttu-id="92887-131">**URL do site**</span><span class="sxs-lookup"><span data-stu-id="92887-131">**Web site URL**</span></span>|<span data-ttu-id="92887-132">A URL do site de suporte.</span><span class="sxs-lookup"><span data-stu-id="92887-132">The URL of your support website.</span></span><br /><span data-ttu-id="92887-133">Comprimento máximo: 150 caracteres</span><span class="sxs-lookup"><span data-stu-id="92887-133">Maximum length: 150 characters</span></span>|
|<span data-ttu-id="92887-134">**Observações**</span><span class="sxs-lookup"><span data-stu-id="92887-134">**Notes**</span></span>|<span data-ttu-id="92887-135">Uma observação que é exibida para os usuários.</span><span class="sxs-lookup"><span data-stu-id="92887-135">A note that is displayed to users.</span></span><br /><span data-ttu-id="92887-136">Comprimento máximo: 120 caracteres</span><span class="sxs-lookup"><span data-stu-id="92887-136">Maximum length: 120 characters</span></span>|

<span data-ttu-id="92887-137">Consulte os seguintes recursos para obter informações sobre as políticas e configurações que você pode definir para computadores Windows:</span><span class="sxs-lookup"><span data-stu-id="92887-137">See the following resources for information about policies and settings that you can configure for Windows PCs:</span></span>

- <span data-ttu-id="92887-138">[Manter computadores Windows atualizados com as atualizações de software no Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) – essas políticas fazem os computadores gerenciados procurar e baixar atualizações de software da Microsoft e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="92887-138">[Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) - These policies make managed computers check for, and download software updates from, Microsoft and from third parties.</span></span> <span data-ttu-id="92887-139">Essas atualizações não incluem atualizações de SO (por exemplo, atualizar do Windows 7 para o Windows 10 ou atualizar de uma versão do Windows 10 para uma versão posterior).</span><span class="sxs-lookup"><span data-stu-id="92887-139">These updates do not include OS upgrades (e.g., upgrading from Windows 7 to Windows 10, or upgrades from one Windows 10 version to a later version).</span></span>

- <span data-ttu-id="92887-140">[Ajudar a proteger computadores Windows com o Endpoint Protection para Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) – essas configurações incluem agendas de verificação e ações a serem tomadas quando um malware for detectado.</span><span class="sxs-lookup"><span data-stu-id="92887-140">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) - These settings include scan schedules and actions to take when malware is detected.</span></span>

- <span data-ttu-id="92887-141">[Ajudar a proteger computadores Windows usando políticas de Firewall do Windows no Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) – essas políticas simplificam a administração de configurações do Firewall do Windows nos computadores gerenciados.</span><span class="sxs-lookup"><span data-stu-id="92887-141">[Help protect Windows PCs using Windows Firewall policies in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) - These policies simplify the administration of Windows Firewall settings on managed computers.</span></span>


### <span data-ttu-id="92887-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="92887-142">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="92887-143">Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="92887-143">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
