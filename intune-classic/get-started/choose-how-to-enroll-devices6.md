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
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 8fe7b2bb58655374d3e92391cd0a37aeda3062d4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1b25b-103">Escolher como registrar dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="1b25b-103">Choose how to enroll mobile devices</span></span>
<a id="choose-how-to-enroll-mobile-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1b25b-104">As respostas para esta série de perguntas ajudarão a determinar o melhor método de registro para os dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="1b25b-104">Your answers to this series of questions will help determine the best enrollment method for the devices you manage.</span></span>

## <span data-ttu-id="1b25b-105">**Como você gerenciará dispositivos dedicados corporativos?**</span><span class="sxs-lookup"><span data-stu-id="1b25b-105">**How will you manage dedicated, corporate-owned devices?**</span></span>
<a id="how-will-you-manage-dedicated-corporate-owned-devices" class="xliff"></a>

  > [!div class="button"]
[<span data-ttu-id="1b25b-106">iOS DEP ></span><span class="sxs-lookup"><span data-stu-id="1b25b-106">iOS DEP ></span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
<span data-ttu-id="1b25b-107">[Assistente de Configuração do iOS >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]</span><span class="sxs-lookup"><span data-stu-id="1b25b-107">[iOS Setup Assistant >](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
[!div class="button"]</span></span>
[<span data-ttu-id="1b25b-108">Marcar com IMEI ></span><span class="sxs-lookup"><span data-stu-id="1b25b-108">Tag with IMEI ></span></span>](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  <span data-ttu-id="1b25b-109">Você pode registrar dispositivos da empresa com usuários dedicados das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="1b25b-109">You can enroll corporate-owned devices with dedicated users in the following ways:</span></span>

  - <span data-ttu-id="1b25b-110">**DEP (Programa de Registro do Dispositivo) da Apple**: dispositivos iOS podem ser comprados ou gerenciados com o DEP com um perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="1b25b-110">**Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile.</span></span> <span data-ttu-id="1b25b-111">Quando os usuários ligam seus dispositivos pela primeira vez, o dispositivo baixa o perfil de DEP e registra-se com o Intune.</span><span class="sxs-lookup"><span data-stu-id="1b25b-111">When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.</span></span>

  - <span data-ttu-id="1b25b-112">**Apple Configurator em um Mac**: o Apple Configurator é um aplicativo da Apple que é executado em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="1b25b-112">**Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC.</span></span> <span data-ttu-id="1b25b-113">Você pode conectar dispositivos iOS ao Mac com um cabo USB para instalar um perfil de registro no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1b25b-113">You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device.</span></span> <span data-ttu-id="1b25b-114">Se você puder redefinir os dispositivos para os padrões de fábrica, use o Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="1b25b-114">If you can factory reset devices to enroll them use Setup Assistant enrollment.</span></span>

  - <span data-ttu-id="1b25b-115">**Marcar com número IMEI** - Importando os números do IMEI (identidade internacional de equipamentos móveis) dos dispositivos da empresa, você poderá marcá-los como dispositivos da empresa no Intune.</span><span class="sxs-lookup"><span data-stu-id="1b25b-115">**Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune.</span></span> <span data-ttu-id="1b25b-116">Essa é a única maneira de identificar dispositivos Windows e Android dedicados ("de usuário único") como corporativos.</span><span class="sxs-lookup"><span data-stu-id="1b25b-116">This is the only way to identify dedicated ("single-user") Windows and Android devices as corporate-owned.</span></span> <span data-ttu-id="1b25b-117">Os dispositivos iOS que não serão registrados no programa de registro de dispositivos da Apple ou no Apple Configurator também podem ser marcados com um número IMEI.</span><span class="sxs-lookup"><span data-stu-id="1b25b-117">iOS devices that won't be enrolled with Apple's device enrollment program or Apple Configurator can also be tagged with an IMEI number.</span></span> <span data-ttu-id="1b25b-118">Após declarar previamente o dispositivo para que ele seja marcado como "corporativo", você pode distribuir dispositivos aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1b25b-118">After predeclaring the device so it will be tagged as "corporate", you can distribute devices to users.</span></span> <span data-ttu-id="1b25b-119">Os usuários podem registrar seus dispositivos como dispositivos dedicados instalando o Portal da Empresa para acessar recursos da empresa como email, aplicativos e dados.</span><span class="sxs-lookup"><span data-stu-id="1b25b-119">Users can then enroll their devices as a dedicated devices by installing the Company Portal to access company resources such as email, apps, and data.</span></span>

> [!div class="button"]
[<span data-ttu-id="1b25b-120">< Voltar</span><span class="sxs-lookup"><span data-stu-id="1b25b-120">< Back</span></span>](choose-how-to-enroll-devices3.md)
