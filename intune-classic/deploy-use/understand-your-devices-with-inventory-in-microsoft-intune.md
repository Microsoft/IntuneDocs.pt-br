---
title: "Compreenda seus dispositivos com um inventário"
description: "Use o Intune para exibir informações sobre o hardware dos dispositivos que você gerencia."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2d2acab722c0a1f0c5757f6bbe75687cd8416485
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7b5c7-103">Compreenda seus dispositivos com um inventário no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7b5c7-103">Understand your devices with inventory in Microsoft Intune</span></span>
<a id="understand-your-devices-with-inventory-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="7b5c7-104">O Microsoft Intune permite que você exiba o inventário de dispositivos e computadores Windows registrados que executam o software cliente do Intune.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-104">Microsoft Intune lets you view the inventory of enrolled devices and Windows PCs that run the Intune client software.</span></span>
<span data-ttu-id="7b5c7-105">O Intune normalmente coleta o inventário de dispositivos gerenciados a cada sete dias.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-105">Intune typically collects inventory from managed devices every 7 days.</span></span> <span data-ttu-id="7b5c7-106">Por isso, pode haver um atraso antes que os relatórios mostrem os resultados das alterações recentes nos dispositivos; por exemplo, uma alteração no nome do dispositivo ou o espaço de armazenamento livre.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-106">Because of this, there might be a delay before reports show the results of any recent changes to devices, for example, a change to the device name, or free storage space.</span></span>

## <span data-ttu-id="7b5c7-107">O que é coletado dos dispositivos registrados?</span><span class="sxs-lookup"><span data-stu-id="7b5c7-107">What's collected from enrolled devices?</span></span>
<a id="whats-collected-from-enrolled-devices" class="xliff"></a>
<span data-ttu-id="7b5c7-108">Para exibir o inventário coletado por dispositivos móveis, execute os [Relatórios de inventário de dispositivos móveis](understand-microsoft-intune-operations-by-using-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-108">To view the inventory that's collected by mobile devices, run the [Mobile Device Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md).</span></span> <span data-ttu-id="7b5c7-109">O Intune coleta o seguinte inventário dos dispositivos registrados:</span><span class="sxs-lookup"><span data-stu-id="7b5c7-109">Intune collects the following inventory from enrolled devices:</span></span>

|<span data-ttu-id="7b5c7-110">Propriedade</span><span class="sxs-lookup"><span data-stu-id="7b5c7-110">Property</span></span>|<span data-ttu-id="7b5c7-111">Coletado por</span><span class="sxs-lookup"><span data-stu-id="7b5c7-111">Collected by</span></span>|
|------------|-----------------------|
|<span data-ttu-id="7b5c7-112">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-112">**Name**</span></span>|<span data-ttu-id="7b5c7-113">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-113">All devices</span></span>|
|<span data-ttu-id="7b5c7-114">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-114">**Operating System**</span></span>|<span data-ttu-id="7b5c7-115">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-115">All devices</span></span>|
|<span data-ttu-id="7b5c7-116">**Fabricante**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-116">**Manufacturer**</span></span>|<span data-ttu-id="7b5c7-117">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-117">All devices</span></span>|
|<span data-ttu-id="7b5c7-118">**Modelo**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-118">**Model**</span></span>|<span data-ttu-id="7b5c7-119">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-119">All devices</span></span>|
|<span data-ttu-id="7b5c7-120">**Canal de gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-120">**Management Channel**</span></span>|<span data-ttu-id="7b5c7-121">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-121">All devices</span></span>|
|<span data-ttu-id="7b5c7-122">**Registrado no AAD**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-122">**AAD Registered**</span></span>|<span data-ttu-id="7b5c7-123">Todos os dispositivos, exceto o Mac OS X</span><span class="sxs-lookup"><span data-stu-id="7b5c7-123">All devices except Mac OS X</span></span>|
|<span data-ttu-id="7b5c7-124">**Compatível**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-124">**Compliant**</span></span>|<span data-ttu-id="7b5c7-125">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-125">All devices</span></span>|
|<span data-ttu-id="7b5c7-126">**EAS ativado**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-126">**EAS Activated**</span></span>|<span data-ttu-id="7b5c7-127">Todos os dispositivos, exceto o Mac OS X</span><span class="sxs-lookup"><span data-stu-id="7b5c7-127">All devices except Mac OS X</span></span>|
|<span data-ttu-id="7b5c7-128">**ID de ativação de EAS**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-128">**EAS Activation ID**</span></span>|<span data-ttu-id="7b5c7-129">Todos os dispositivos, exceto o Mac OS X</span><span class="sxs-lookup"><span data-stu-id="7b5c7-129">All devices except Mac OS X</span></span>|
|<span data-ttu-id="7b5c7-130">**Tempo de ativação de EAS**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-130">**EAS Activation Time**</span></span>|<span data-ttu-id="7b5c7-131">Todos os dispositivos, exceto o Mac OS X</span><span class="sxs-lookup"><span data-stu-id="7b5c7-131">All devices except Mac OS X</span></span>|
|<span data-ttu-id="7b5c7-132">**Estado de gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-132">**Management State**</span></span>|<span data-ttu-id="7b5c7-133">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-133">All devices</span></span>|
|<span data-ttu-id="7b5c7-134">**Endereço de email**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-134">**Email Address**</span></span>|<span data-ttu-id="7b5c7-135">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-135">All devices</span></span>|
|<span data-ttu-id="7b5c7-136">**ID do Exchange ActiveSync**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-136">**Exchange ActiveSync ID**</span></span>|<span data-ttu-id="7b5c7-137">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-137">All devices</span></span>|
|<span data-ttu-id="7b5c7-138">**Com jailbreak ou com raiz**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-138">**Jailbroken or Rooted**</span></span>|<span data-ttu-id="7b5c7-139">Somente os dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b5c7-139">iOS and Android devices only</span></span>|
|<span data-ttu-id="7b5c7-140">**ID exclusiva do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-140">**Unique Device ID**</span></span>|<span data-ttu-id="7b5c7-141">Todos os dispositivos, exceto o Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="7b5c7-141">All devices except Exchange ActiveSync</span></span>|
|<span data-ttu-id="7b5c7-142">**Número de série**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-142">**Serial number**</span></span>|<span data-ttu-id="7b5c7-143">Dispositivos iOS, Mac OS X, Android, Windows 8.1 e Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="7b5c7-143">iOS, Mac OS X, Android, Windows 8.1, and Windows 10 desktop devices</span></span>|
|<span data-ttu-id="7b5c7-144">**Espaço de armazenamento total**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-144">**Total Storage Space**</span></span>|<span data-ttu-id="7b5c7-145">Dispositivos iOS, Mac OS X, Windows 8.1 e Windows 10 Desktop e Mobile</span><span class="sxs-lookup"><span data-stu-id="7b5c7-145">iOS, Mac OS X, Windows 8.1, and Windows 10 desktop and Mobile devices</span></span>|
|<span data-ttu-id="7b5c7-146">**Espaço de armazenamento livre**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-146">**Free Storage Space**</span></span>|<span data-ttu-id="7b5c7-147">Dispositivos iOS, Mac OS X, Windows 8.1 e Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="7b5c7-147">iOS, Mac OS X, Windows 8.1, and Windows 10 desktop devices</span></span>|
|<span data-ttu-id="7b5c7-148">**Número de telefone**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-148">**Phone Number**</span></span><br><span data-ttu-id="7b5c7-149">Os telefones categorizados como Empresariais são identificados com o número de telefone completo (por exemplo, quando você executa um relatório de inventário de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-149">Phones that are categorized as corporate are identified with their full phone number (for example, when you run a mobile device inventory report).</span></span> <span data-ttu-id="7b5c7-150">Os números de telefone BYOD são mascarados com &#42;, e apenas os quatro últimos dígitos são exibidos.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-150">BYOD phone numbers are masked with &#42;, and only the last four digits are displayed.</span></span>|<span data-ttu-id="7b5c7-151">Dispositivos iOS, Android e Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7b5c7-151">iOS, Android, and Windows Phone devices</span></span>|
|<span data-ttu-id="7b5c7-152">**IMEI**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-152">**IMEI**</span></span>|<span data-ttu-id="7b5c7-153">Dispositivos Exchange ActiveSync, iOS, Android e Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7b5c7-153">Exchange ActiveSync, iOS, Android, and Windows Phone devices</span></span>|
|<span data-ttu-id="7b5c7-154">**MEID**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-154">**MEID**</span></span><br><span data-ttu-id="7b5c7-155">Identificador de Equipamentos Móveis</span><span class="sxs-lookup"><span data-stu-id="7b5c7-155">Mobile Equipment Identifier</span></span>|<span data-ttu-id="7b5c7-156">Somente os dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="7b5c7-156">iOS devices only</span></span>|
|<span data-ttu-id="7b5c7-157">**Wi-Fi MAC**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-157">**Wi-Fi MAC**</span></span>|<span data-ttu-id="7b5c7-158">Todos os dispositivos, exceto o Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="7b5c7-158">All devices except Exchange ActiveSync</span></span>|
|<span data-ttu-id="7b5c7-159">**Carrier do assinante**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-159">**Subscriber Carrier**</span></span>|<span data-ttu-id="7b5c7-160">Somente os dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b5c7-160">iOS and Android devices only</span></span>|
|<span data-ttu-id="7b5c7-161">**Tecnologia celular**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-161">**Cellular Technology**</span></span>|<span data-ttu-id="7b5c7-162">Somente os dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="7b5c7-162">iOS and Android devices only</span></span>|
|<span data-ttu-id="7b5c7-163">**Supervisionado**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-163">**Supervised**</span></span>|<span data-ttu-id="7b5c7-164">Somente os dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="7b5c7-164">iOS devices only</span></span>|
|<span data-ttu-id="7b5c7-165">**Estado de Bloqueio de Ativação**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-165">**Activation Lock State**</span></span>|<span data-ttu-id="7b5c7-166">Somente os dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="7b5c7-166">iOS devices only</span></span>|
|<span data-ttu-id="7b5c7-167">**Data registrada**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-167">**Enrolled Date**</span></span>|<span data-ttu-id="7b5c7-168">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-168">All devices</span></span>|
|<span data-ttu-id="7b5c7-169">**Última atualização**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-169">**Last Updated**</span></span>|<span data-ttu-id="7b5c7-170">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-170">All devices</span></span>|
|<span data-ttu-id="7b5c7-171">**Ethernet MAC**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-171">**Ethernet MAC**</span></span>|<span data-ttu-id="7b5c7-172">Somente os dispositivos Mac OS X</span><span class="sxs-lookup"><span data-stu-id="7b5c7-172">Mac OS X devices only</span></span>|
|<span data-ttu-id="7b5c7-173">**Bloqueio de Ativação habilitado**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-173">**Activation Lock Enabled**</span></span>|<span data-ttu-id="7b5c7-174">Somente os dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="7b5c7-174">iOS devices only</span></span>|
|<span data-ttu-id="7b5c7-175">**Criptografia habilitada**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-175">**Encryption Enabled**</span></span>|<span data-ttu-id="7b5c7-176">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="7b5c7-176">All devices</span></span>|

## <span data-ttu-id="7b5c7-177">O que é coletado de computadores Windows?</span><span class="sxs-lookup"><span data-stu-id="7b5c7-177">What's collected from Windows PCs?</span></span>
<a id="whats-collected-from-windows-pcs" class="xliff"></a>
> [!IMPORTANT]
> <span data-ttu-id="7b5c7-178">Esta seção se aplica somente aos computadores Windows que executam o software cliente do computador Windows com o Intune.</span><span class="sxs-lookup"><span data-stu-id="7b5c7-178">This section applies only to Windows PCs that run the Intune Windows PC client software.</span></span>

<span data-ttu-id="7b5c7-179">Para exibir o inventário coletado por computadores Windows, execute os [Relatórios de inventário de computador](understand-microsoft-intune-operations-by-using-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7b5c7-179">To view the inventory that's collected by Windows PCs, run the [Computer Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md).</span></span> <span data-ttu-id="7b5c7-180">O Intune coleta o seguinte inventário dos computadores Windows:</span><span class="sxs-lookup"><span data-stu-id="7b5c7-180">Intune collects the following inventory from Windows PCs:</span></span>

-   <span data-ttu-id="7b5c7-181">**Nome**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-181">**Name**</span></span>

-   <span data-ttu-id="7b5c7-182">**Tipo de chassi**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-182">**Chassis Type**</span></span>

-   <span data-ttu-id="7b5c7-183">**Fabricante**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-183">**Manufacturer**</span></span>

-   <span data-ttu-id="7b5c7-184">**Modelo**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-184">**Model**</span></span>

-   <span data-ttu-id="7b5c7-185">**Sistema operacional**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-185">**Operating System**</span></span>

-   <span data-ttu-id="7b5c7-186">**Versão do TPM**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-186">**TPM Version**</span></span>

-   <span data-ttu-id="7b5c7-187">**Espaço total em disco**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-187">**Total Disk Space**</span></span>

-   <span data-ttu-id="7b5c7-188">**Espaço em disco utilizado**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-188">**Used Disk Space**</span></span>

-   <span data-ttu-id="7b5c7-189">**Espaço livre em disco**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-189">**Free Disk Space**</span></span>

-   <span data-ttu-id="7b5c7-190">**Nome de disco do SO**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-190">**OS Disk Name**</span></span>

-   <span data-ttu-id="7b5c7-191">**Espaço em disco do SO**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-191">**OS Disk Space**</span></span>

-   <span data-ttu-id="7b5c7-192">**Espaço livre em disco do SO**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-192">**OS Disk Free Space**</span></span>

-   <span data-ttu-id="7b5c7-193">**Memória física**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-193">**Physical Memory**</span></span>

-   <span data-ttu-id="7b5c7-194">**Nome do processador**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-194">**Processor Name**</span></span>

-   <span data-ttu-id="7b5c7-195">**Arquitetura do processador**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-195">**Processor Architecture**</span></span>

-   <span data-ttu-id="7b5c7-196">**Velocidade da CPU**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-196">**CPU Speed**</span></span>

-   <span data-ttu-id="7b5c7-197">**Endereço IP**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-197">**IP Address**</span></span>

-   <span data-ttu-id="7b5c7-198">**Número de série**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-198">**Serial number**</span></span>

-   <span data-ttu-id="7b5c7-199">**Último usuário a fazer logon**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-199">**Last User to Log On**</span></span>

-   <span data-ttu-id="7b5c7-200">**Usuário atribuído**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-200">**Assigned User**</span></span>

-   <span data-ttu-id="7b5c7-201">**Última atualização**</span><span class="sxs-lookup"><span data-stu-id="7b5c7-201">**Last Updated**</span></span>

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
