---
title: Como monitorar a conformidade do dispositivo
titleSuffix: Intune on Azure
description: Saiba como monitorar a conformidade do dispositivo.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f18bfa7fb045dbad4ab785c2c8e1bc13fc439db
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1d5b6-103">Como monitorar a conformidade do dispositivo no Intune</span><span class="sxs-lookup"><span data-stu-id="1d5b6-103">How to monitor device compliance in Intune</span></span>
<a id="how-to-monitor-device-compliance-in-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1d5b6-104">Você pode exibir o resumo do status dos seus **perfis de conformidade** na folha **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-104">You can view the summary of the status of your **compliance profiles** in the **Overview** blade.</span></span>
<span data-ttu-id="1d5b6-105">Você pode clicar em interativamente nos gráficos para analisar os detalhes.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-105">You can interactively click through the charts to drill down into the details.</span></span> <span data-ttu-id="1d5b6-106">Se você tiver vários perfis de conformidade configurados, também será possível exibir o status de cada política indo até a folha de política e escolhendo **Relatórios** na seção **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-106">If you have multiple compliance profiles configured, you can also view the status for each policy by going to the policy blade and choosing **Reports** in the **Manage** section.</span></span>  <span data-ttu-id="1d5b6-107">Os detalhes dos relatórios disponíveis são listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-107">The details of the reports available are listed below.</span></span>

##  <span data-ttu-id="1d5b6-108">Conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="1d5b6-108">Device compliance</span></span>
<a id="device-compliance" class="xliff"></a>

<span data-ttu-id="1d5b6-109">A exibição resumida do relatório de conformidade do dispositivo começa mostrando as informações agregadas sobre o número de dispositivos que estão se comunicando como um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1d5b6-109">The summarized view of the device compliance report shows starts with showing you the aggregated information about the number of devices that are reporting as one of the following:</span></span>

- <span data-ttu-id="1d5b6-110">**Em conformidade**: o dispositivo foi avaliado quanto à conformidade recentemente e foi considerado em conformidade com as configurações do perfil de conformidade especificado.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-110">**Compliant**: Device has been evaluated for compliance recently and has been determined as compliant with the compliance profile settings you specified.</span></span>
- <span data-ttu-id="1d5b6-111">**Fora de conformidade**: o dispositivo foi avaliado e determinado como fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-111">**Noncompliant**: The device has been evaluated and determined as noncompliant.</span></span>  <span data-ttu-id="1d5b6-112">Se havia um período de cortesia especificado no perfil, ele expirou e deixou o dispositivo fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-112">If there was a grace period specified in the profile, the grace period has expired putting the device in a noncompliant status.</span></span>
- <span data-ttu-id="1d5b6-113">**Período de cortesia**: o dispositivo foi avaliado e determinado como fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-113">**Grace period**: Device has been evaluated and determined as noncompliant.</span></span> <span data-ttu-id="1d5b6-114">No entanto, o período de cortesia ainda se aplica antes de o dispositivo ser efetivamente marcado como fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-114">However, the grace period still applies before the device is actually marked as noncompliant.</span></span>

<span data-ttu-id="1d5b6-115">Você pode fazer uma busca detalhada em cada seção para ver mais detalhes sobre os usuários e dispositivos individuais.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-115">You can drill down on each section to see more details on the individual devices and users.</span></span>

## <span data-ttu-id="1d5b6-116">Conformidade da configuração</span><span class="sxs-lookup"><span data-stu-id="1d5b6-116">Setting compliance</span></span>
<a id="setting-compliance" class="xliff"></a>

<span data-ttu-id="1d5b6-117">O relatório de conformidade de configuração fornece detalhes sobre cada configuração de conformidade, como:</span><span class="sxs-lookup"><span data-stu-id="1d5b6-117">The setting compliance report provides the details for each compliance settings such as:</span></span>

- <span data-ttu-id="1d5b6-118">Número de dispositivos que não estão em conformidade com a configuração.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-118">Number of devices that are noncompliant with the setting.</span></span>
- <span data-ttu-id="1d5b6-119">A plataforma à qual a configuração é aplicada.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-119">The platform that the setting is applied to.</span></span>

<span data-ttu-id="1d5b6-120">Você pode fazer uma busca detalhada em cada configuração para obter mais informações sobre os perfis nos quais essas configurações tem sido habilitadas e o valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="1d5b6-120">You can drill down on each of the setting to see more information about the profiles on which these settings have been enabled, and the value of the setting.</span></span>
