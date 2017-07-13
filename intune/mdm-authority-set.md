---
title: "Defina a autoridade de gerenciamento de dispositivo móvel"
titleSuffix: Intune on Azure
description: "Saiba como definir a autoridade de gerenciamento de dispositivo móvel no Intune. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 449c45e0edcc0d0a33352ba154ad68fa6c4725c0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="a6d8b-104">Defina a autoridade de gerenciamento de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="a6d8b-104">Set the mobile device management authority</span></span>
<a id="set-the-mobile-device-management-authority" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a6d8b-105">A configuração de autoridade de gerenciamento de dispositivo móvel (MDM) determina como você gerenciar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-105">The mobile device management (MDM) authority setting determines how you manage your devices.</span></span> <span data-ttu-id="a6d8b-106">Como administrador de TI, você deverá definir uma autoridade MDM antes que os usuários possam registrar dispositivos para gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-106">As an IT admin, you must set an MDM authority before users can enroll devices for management.</span></span>

<span data-ttu-id="a6d8b-107">As configurações possíveis são:</span><span class="sxs-lookup"><span data-stu-id="a6d8b-107">Possible configurations are:</span></span>

- <span data-ttu-id="a6d8b-108">**Intune Autônomo** – Gerenciamento apenas na nuvem, que você pode definir usando o Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-108">**Intune Standalone** - cloud-only management, which you configure by using the Azure portal.</span></span> <span data-ttu-id="a6d8b-109">Inclui o conjunto completo de recursos que o Intune oferece.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-109">Includes the full set of capabilities that Intune offers.</span></span> <span data-ttu-id="a6d8b-110">[Definir a autoridade MDM no console do Intune](#mdm-authority-set-to-intune).</span><span class="sxs-lookup"><span data-stu-id="a6d8b-110">[Set the MDM authority in the Intune console](#mdm-authority-set-to-intune).</span></span>

- <span data-ttu-id="a6d8b-111">**Intune Híbrido** – Integração da solução de nuvem Intune com o System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-111">**Intune Hybrid** - integration of the Intune cloud solution with System Center Configuration Manager.</span></span> <span data-ttu-id="a6d8b-112">Você configura o Intune usando o console do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-112">You configure Intune by using the Configuration Manager console.</span></span> <span data-ttu-id="a6d8b-113">[Definir a autoridade do MDM no Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).</span><span class="sxs-lookup"><span data-stu-id="a6d8b-113">[Set the MDM authority in Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).</span></span>

- <span data-ttu-id="a6d8b-114">**Gerenciamento de dispositivo móvel para o Office 365** – Integração do Office 365 com a solução de nuvem do Intune.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-114">**Mobile Device Management for Office 365** - integration of Office 365 with the Intune cloud solution.</span></span> <span data-ttu-id="a6d8b-115">Configure o Intune do seu Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-115">You configure Intune from your Office 365 Admin Center.</span></span> <span data-ttu-id="a6d8b-116">Inclui um subconjunto dos recursos que estão disponíveis com o Intune Autônomo.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-116">Includes a subset of the capabilities that are available with Intune Standalone.</span></span> <span data-ttu-id="a6d8b-117">Defina a autoridade MDM no Centro de administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-117">Set the MDM authority in Office 365 Admin Center.</span></span>

>[!IMPORTANT]    
<span data-ttu-id="a6d8b-118">No Configuration Manager versão 1610 ou posterior e no Microsoft Intune versão 1705, você altera a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-118">In Configuration Manager version 1610 or later and Microsoft Intune version 1705, you change the MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices.</span></span> <span data-ttu-id="a6d8b-119">Para obter detalhes, consulte [O que fazer se você escolher a configuração incorreta de autoridade de MDM](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span><span class="sxs-lookup"><span data-stu-id="a6d8b-119">For details, see [What to do if you choose the wrong MDM authority setting](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span></span>

## <span data-ttu-id="a6d8b-120">Definir a autoridade de MDM como o Intune</span><span class="sxs-lookup"><span data-stu-id="a6d8b-120">Set MDM authority to Intune</span></span>
<a id="set-mdm-authority-to-intune" class="xliff"></a>

1. <span data-ttu-id="a6d8b-121">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-121">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
  <span data-ttu-id="a6d8b-122">![Captura de tela da carga de trabalho de solução de problema do Intune com o link Selecionar Usuário](media/set-mdm-auth.png)</span><span class="sxs-lookup"><span data-stu-id="a6d8b-122">![Screenshot of the Intune Troubleshoot workload with Select User link](media/set-mdm-auth.png)</span></span>
2. <span data-ttu-id="a6d8b-123">Na folha Intune, escolha **Registro de dispositivo** e escolha **Visão Geral**.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-123">On the Intune blade, choose **Device enrollment**, and then choose **Overview**.</span></span>

3. <span data-ttu-id="a6d8b-124">na folha **Começar a gerenciar dispositivos**, escolha **Definir autoridade MDM Intune**.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-124">On the **Start managing devices** blade, choose **Set MDM Authority to Intune**.</span></span> <span data-ttu-id="a6d8b-125">Uma mensagem indica que você configurou com êxito sua autoridade MDM Intune.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-125">A message indicates that you have successfully set your MDM authority to Intune.</span></span>

## <span data-ttu-id="a6d8b-126">Limpeza de dispositivo móvel após a expiração do certificado MDM</span><span class="sxs-lookup"><span data-stu-id="a6d8b-126">Mobile device cleanup after MDM certificate expiration</span></span>
<a id="mobile-device-cleanup-after-mdm-certificate-expiration" class="xliff"></a>

<span data-ttu-id="a6d8b-127">O certificado do MDM é renovado automaticamente quando os dispositivos móveis estão se comunicando com o serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-127">The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service.</span></span> <span data-ttu-id="a6d8b-128">Se os dispositivos móveis forem apagados ou se eles não conseguirem se comunicar com o serviço Intune por um certo período, o certificado do MDM não será renovado.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-128">If mobile devices are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate will not get renewed.</span></span> <span data-ttu-id="a6d8b-129">O dispositivo é removido do Portal do Azure 180 dias após a expiração do certificado do MDM.</span><span class="sxs-lookup"><span data-stu-id="a6d8b-129">The device is removed from the Azure portal 180 days after the MDM certificate expires.</span></span>
