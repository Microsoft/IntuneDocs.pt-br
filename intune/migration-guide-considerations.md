---
title: "Considerações especiais sobre a migração"
description: "A finalidade deste artigo é tecer considerações especiais sobre a migração antes de os clientes iniciarem uma campanha de migração."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc39ffd3a4f11a4c2b32f75dc5befcd8ce42f43e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="89523-103">Considerações especiais sobre a migração</span><span class="sxs-lookup"><span data-stu-id="89523-103">Special migration considerations</span></span>
<a id="special-migration-considerations" class="xliff"></a>

[!INCLUDE[note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="89523-104">Algumas considerações especiais de migração podem ser aplicáveis dependendo do seu ambiente de provedor de MDM atual.</span><span class="sxs-lookup"><span data-stu-id="89523-104">There are special migration considerations which may be applicable depending on your existing MDM provider environment.</span></span>

## <span data-ttu-id="89523-105">Redefinição de fábrica para o programa DEP (Programa de Registro de Dispositivo) da Apple</span><span class="sxs-lookup"><span data-stu-id="89523-105">Factory reset for Apple’s Device Enrollment Program (DEP)</span></span>
<a id="factory-reset-for-apples-device-enrollment-program-dep" class="xliff"></a>

<span data-ttu-id="89523-106">O programa DEP (Programa de Registro de Dispositivo) da Apple define configurações de dispositivos que não podem ser removidas pelo usuário final.</span><span class="sxs-lookup"><span data-stu-id="89523-106">The Apple Device Enrollment Program (DEP) sets device configurations that cannot be removed by the end user.</span></span> <span data-ttu-id="89523-107">Para manter os recursos de gerenciamento avançados do DEP, o dispositivo deve retornar ao estado inicial (novo) por meio da redefinição de fábrica a fim de ser registrado no Intune.</span><span class="sxs-lookup"><span data-stu-id="89523-107">To retain the advanced management features of DEP, the device must be returned to the out-of-box (new) state via factory reset to enroll to Intune.</span></span>

<span data-ttu-id="89523-108">Para continuar usando o DEP para gerenciar os dispositivos no Intune, [configure o registro de dispositivo iOS com o Programa de registro de dispositivos](/intune/device-enrollment-program-enroll-ios).</span><span class="sxs-lookup"><span data-stu-id="89523-108">To continue using DEP to manage the devices in Intune, [set up iOS device enrollment with Device Enrollment Program](/intune/device-enrollment-program-enroll-ios).</span></span>


## <span data-ttu-id="89523-109">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="89523-109">Next steps</span></span>
<a id="next-steps" class="xliff"></a> 

[<span data-ttu-id="89523-110">Fase 2: Campanha de migração</span><span class="sxs-lookup"><span data-stu-id="89523-110">Phase 2: Migration campaign</span></span>](migration-guide-campaign.md)
