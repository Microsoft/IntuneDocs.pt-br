---
title: Registrar dispositivos macOS no Intune
titleSuffix: Intune on Azure
description: Saiba como registrar dispositivos macOS no Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e1e87705380167a01753f9fe82e6a42ca8fa5787
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3f373-103">Registrar dispositivos macOS no Intune</span><span class="sxs-lookup"><span data-stu-id="3f373-103">Enroll macOS devices in Intune</span></span>
<a id="enroll-macos-devices-in-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="3f373-104">O Intune permite que você gerencie dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="3f373-104">Intune enables you to manage macOS devices.</span></span> <span data-ttu-id="3f373-105">Para habilitar o gerenciamento de dispositivos, os usuários devem registrar seus dispositivos acessando o [site do Portal da Empresa](http://portal.manage.microsoft.com) e seguir as instruções.</span><span class="sxs-lookup"><span data-stu-id="3f373-105">To enable device management, your users must enroll their devices by going to the [Company Portal website](http://portal.manage.microsoft.com), and following the prompts.</span></span> <span data-ttu-id="3f373-106">Quando os dispositivos macOS estiverem sob gerenciamento, você pode [criar configurações personalizadas para dispositivos macOS](custom-settings-macos.md).</span><span class="sxs-lookup"><span data-stu-id="3f373-106">Once macOS devices are under management, you can [create custom settings for macOS devices](custom-settings-macos.md).</span></span> <span data-ttu-id="3f373-107">Mais recursos serão disponibilizados em breve.</span><span class="sxs-lookup"><span data-stu-id="3f373-107">More capabilities are coming soon.</span></span>

## <span data-ttu-id="3f373-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3f373-108">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

<span data-ttu-id="3f373-109">Atenda os seguintes pré-requisitos antes de configurar o registro do dispositivo macOS:</span><span class="sxs-lookup"><span data-stu-id="3f373-109">Complete the following prerequisites before setting up macOS device enrollment:</span></span>

- [<span data-ttu-id="3f373-110">Configurar domínios</span><span class="sxs-lookup"><span data-stu-id="3f373-110">Configure domains</span></span>](custom-domain-name-configure.md)
- [<span data-ttu-id="3f373-111">Definir a Autoridade MDM</span><span class="sxs-lookup"><span data-stu-id="3f373-111">Set the MDM Authority</span></span>](mdm-authority-set.md)
- [<span data-ttu-id="3f373-112">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="3f373-112">Create groups</span></span>](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [<span data-ttu-id="3f373-113">Configurar o Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="3f373-113">Configure the Company Portal</span></span>](company-portal-app.md)
- <span data-ttu-id="3f373-114">Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span><span class="sxs-lookup"><span data-stu-id="3f373-114">Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span></span>
- [<span data-ttu-id="3f373-115">Obtenha um certificado push de MDM da Apple</span><span class="sxs-lookup"><span data-stu-id="3f373-115">Get an Apple MDM push certificate</span></span>](apple-mdm-push-certificate-get.md)

## <span data-ttu-id="3f373-116">Configurar registro do macOS</span><span class="sxs-lookup"><span data-stu-id="3f373-116">Set up macOS enrollment</span></span>
<a id="set-up-macos-enrollment" class="xliff"></a>

<span data-ttu-id="3f373-117">Por padrão, o Intune já está configurado para permitir o registro de dispositivos macOS.</span><span class="sxs-lookup"><span data-stu-id="3f373-117">By default, Intune already allows enrollment of macOS devices.</span></span>

<span data-ttu-id="3f373-118">Para bloquear o registro de dispositivos macOS, consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md).</span><span class="sxs-lookup"><span data-stu-id="3f373-118">To block macOS devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).</span></span>

## <span data-ttu-id="3f373-119">Informe aos usuários como registrar seus dispositivos para acessar os recursos da empresa</span><span class="sxs-lookup"><span data-stu-id="3f373-119">Tell your users how to enroll their devices to access company resources</span></span>
<a id="tell-your-users-how-to-enroll-their-devices-to-access-company-resources" class="xliff"></a>

<span data-ttu-id="3f373-120">Você precisará pedir aos usuários finais que acessem o [site do Portal da Empresa](http://portal.manage.microsoft.com) e sigam os prompts para registrar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="3f373-120">You'll need to tell your end users to go to the [Company Portal website](http://portal.manage.microsoft.com), and follow the prompts to enroll their devices.</span></span> <span data-ttu-id="3f373-121">Você também pode enviar a eles um link com as etapas do registro online: [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span><span class="sxs-lookup"><span data-stu-id="3f373-121">You can also send them a link to online enrollment steps: [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span></span>

<span data-ttu-id="3f373-122">Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="3f373-122">For information about other end-user tasks, see these articles:</span></span>

- [<span data-ttu-id="3f373-123">Recursos sobre a experiência do usuário final com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3f373-123">Resources about the end-user experience with Microsoft Intune</span></span>](end-user-educate.md)
- [<span data-ttu-id="3f373-124">Usando um dispositivo iOS ou macOS com o Intune</span><span class="sxs-lookup"><span data-stu-id="3f373-124">Using your iOS or macOS device with Intune</span></span>](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
