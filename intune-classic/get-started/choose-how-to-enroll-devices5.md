---
title: "Escolher como registrar dispositivos móveis"
description: "Decidir como registrar dispositivos móveis no Intune respondendo algumas perguntas simples"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: e978a9df5d0c0e2e94f484c5e683a970f66dc945
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2f31d-103">Escolher como registrar dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="2f31d-103">Choose how to enroll mobile devices</span></span>
<a id="choose-how-to-enroll-mobile-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2f31d-104">As respostas para esta série de perguntas ajudarão a determinar o melhor método de registro para os dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="2f31d-104">Your answers to this series of questions will help determine the best enrollment method for the devices you manage.</span></span>

## <span data-ttu-id="2f31d-105">**Como você gerenciará dispositivos iOS compartilhados?**</span><span class="sxs-lookup"><span data-stu-id="2f31d-105">**How will you manage shared iOS devices?**</span></span>
<a id="how-will-you-manage-shared-ios-devices" class="xliff"></a>

> [!div class="button"]
<span data-ttu-id="2f31d-106">[Registro no DEP para iOS >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]</span><span class="sxs-lookup"><span data-stu-id="2f31d-106">[iOS DEP Enrollment >](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
[!div class="button"]</span></span>
> <span data-ttu-id="2f31d-107">[Registro direto para iOS >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
[!div class="button"]</span><span class="sxs-lookup"><span data-stu-id="2f31d-107">[iOS Direct enrollment >](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
[!div class="button"]</span></span>
[<span data-ttu-id="2f31d-108">Registro no DEM ></span><span class="sxs-lookup"><span data-stu-id="2f31d-108">DEM enrollment ></span></span>](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - <span data-ttu-id="2f31d-109">**DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="2f31d-109">**Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile.</span></span> <span data-ttu-id="2f31d-110">Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com ele.</span><span class="sxs-lookup"><span data-stu-id="2f31d-110">When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP.</span></span>

  - <span data-ttu-id="2f31d-111">**Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="2f31d-111">**Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC.</span></span> <span data-ttu-id="2f31d-112">Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f31d-112">You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device.</span></span> <span data-ttu-id="2f31d-113">Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="2f31d-113">If you can factory reset devices to enroll them use Setup Assistant enrollment.</span></span> <span data-ttu-id="2f31d-114">Se você não quiser redefinir os dispositivos para os padrões de fábrica, use o Registro direto.</span><span class="sxs-lookup"><span data-stu-id="2f31d-114">If you don't want to factory reset devices, use Direct enrollment.</span></span>

  - <span data-ttu-id="2f31d-115">**Gerenciador de Registro de Dispositivo** - O gerenciador de registro de dispositivo (DEM) do Intune permite que um gerente ou administrador registre vários dispositivos móveis com uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="2f31d-115">**Device Enrollment Manager** - Intune's device enrollment manager (DEM) allows a manager or administrator to enroll many mobile devices with a single user account.</span></span> <span data-ttu-id="2f31d-116">Esses dispositivos não podem ter afinidade de usuário (ou seja, usuários dedicados) e devem ser registrados instalando e entrando no aplicativo do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="2f31d-116">These devices cannot have user affinity (i.e. dedicated users) and must enroll by installing and signing in to the Company Portal app.</span></span>

> [!div class="button"]
[<span data-ttu-id="2f31d-117">< Voltar</span><span class="sxs-lookup"><span data-stu-id="2f31d-117">< Back</span></span>](choose-how-to-enroll-devices3.md)
