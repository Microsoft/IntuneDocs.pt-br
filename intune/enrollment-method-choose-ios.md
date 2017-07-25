---
title: Escolha como registrar dispositivos iOS no Intune
titleSuffix: Intune on Azure
description: Saiba como configurar o registro de dispositivos iOS no Microsoft Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 092f582cf30210858bd8cdd3879edfa873523ccb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="ddfb0-103">Escolha como registrar dispositivos iOS e macOS</span><span class="sxs-lookup"><span data-stu-id="ddfb0-103">Choose how to enroll iOS and macOS devices</span></span>
<a id="choose-how-to-enroll-ios-and-macos-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ddfb0-104">Este tópico descreve os métodos que um administrador de TI pode usar para habilitar o registro de dispositivo iOS no Intune.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-104">This topic describes the methods an IT admin can use to enable iOS device enrollment in Intune.</span></span>

<span data-ttu-id="ddfb0-105">Use as seguintes informações para decidir qual método usar para registro de dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-105">Use the following information to decide which method to use for enrolling iOS devices.</span></span> <span data-ttu-id="ddfb0-106">Todos os métodos a seguir, exceto BYOD, são para registro de dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-106">All of the following methods, except BYOD, are for enrolling corporate-owned devices.</span></span>

<span data-ttu-id="ddfb0-107">**Pré-requisito:** um[certificado do Apple Push Notification Service](apple-mdm-push-certificate-get.md) é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-107">**Prerequisite:** An [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md) is required.</span></span>

## <span data-ttu-id="ddfb0-108">BYOD (Dispositivos iOS de propriedade do usuário)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-108">User-owned iOS devices (BYOD)</span></span>
<a id="user-owned-ios-devices-byod" class="xliff"></a>

<span data-ttu-id="ddfb0-109">Se os usuários desejarem registrar seus dispositivos pessoais BYOD (traga seu próprio dispositivo), eles poderão baixar o aplicativo do Portal da Empresa para iOS na Loja de Aplicativos e seguir as instruções de registro no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-109">If users want to enroll their personal, BYOD (bring your own device) devices, they can download the Company Portal app for iOS from the App Store, and follow the enrollment instructions in the app.</span></span> <span data-ttu-id="ddfb0-110">Depois de registrado, os usuários podem se conectar à rede da empresa, ingressar no domínio ou no Azure Active Directory e obter acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-110">Once enrolled, users can connect to the company network, join the domain or Azure Active Directory, and get access to corporate resources.</span></span> <span data-ttu-id="ddfb0-111">Para habilitar o cenário BYOD, o único requisito é ter um [certificado Apple Push Notification Service](apple-mdm-push-certificate-get.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-111">To enable BYOD, the only requirement is an [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md).</span></span> <span data-ttu-id="ddfb0-112">Você também pode bloquear o registro de dispositivos iOS pessoais.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-112">You can also block enrollment of personally owned iOS devices.</span></span> <span data-ttu-id="ddfb0-113">Consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md) para obter instruções.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-113">See [Set device type restrictions](enrollment-restrictions-set.md) for instructions.</span></span>
=======
# Escolha como registrar dispositivos iOS e macOS
<a id="choose-how-to-enroll-ios-and-macos-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Este tópico descreve os métodos que um administrador de TI pode usar para habilitar o registro de dispositivo iOS no Intune.
>>>>>>> live

## <span data-ttu-id="ddfb0-114">Dispositivos macOS de propriedade do usuário (BYOD)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-114">User-owned macOS devices (BYOD)</span></span>
<a id="user-owned-macos-devices-byod" class="xliff"></a>

<span data-ttu-id="ddfb0-115">Você pode habilitar o registro de dispositivo macOS.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-115">You can enable macOS device enrollment.</span></span> <span data-ttu-id="ddfb0-116">Para habilitar o registro do macOS, o único requisito é ter um [certificado Apple Push Notification Service](apple-mdm-push-certificate-get.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-116">To enable macOS enrollment, the only requirement is an [Apple Push Notification service  certificate](apple-mdm-push-certificate-get.md).</span></span> <span data-ttu-id="ddfb0-117">Para obter mais informações, consulte [Registrar dispositivos macOS](./macos-enroll.md)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-117">For more information, see [Enroll macOS devices](./macos-enroll.md)</span></span>

<<<<<<< HEAD
## <span data-ttu-id="ddfb0-118">Programa de registro com a Apple</span><span class="sxs-lookup"><span data-stu-id="ddfb0-118">Enrollment program with Apple</span></span>
<a id="enrollment-program-with-apple" class="xliff"></a>
<span data-ttu-id="ddfb0-119">A Apple oferece programas de compra de dispositivo que incluem o registro de dispositivo e a infraestrutura de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-119">Apple offers device purchasing programs that include device enrollment and management infrastructure.</span></span> <span data-ttu-id="ddfb0-120">O dispositivo comprado por meio de um desses programas pode ser registrado em massa em um registro “sem fio” com a atribuição de números de série do dispositivo ao gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-120">Devices purchased through one of these programs can be bulk-enrolled "over the air" by assigning device serial numbers for Intune management.</span></span>

- <span data-ttu-id="ddfb0-121">**DEP (Programa de registro de dispositivos)** – programa de registro de dispositivos da Apple para organizações e empresas.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-121">**Device Enrollment Program (DEM)** - Apple's device enrollment program for organizations and enterprises.</span></span> <span data-ttu-id="ddfb0-122">Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-122">For more information, see [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md).</span></span>
- <span data-ttu-id="ddfb0-123">**Apple School Manager** – programa de registro de dispositivos da Apple para escolas.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-123">**Apple School Manager** - Apple's device enrollment program for schools.</span></span> <span data-ttu-id="ddfb0-124">Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-124">For more information, see [Enable iOS device enrollment with Apple School Manager](apple-school-manager-set-up-ios.md)</span></span>

## <span data-ttu-id="ddfb0-125">Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="ddfb0-125">Apple Configurator</span></span>
<a id="apple-configurator" class="xliff"></a>

<span data-ttu-id="ddfb0-126">Você pode registrar dispositivos iOS exportando um perfil de Registro Corporativo e, em seguida, conectando esses dispositivos móveis a um Mac que esteja executando o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-126">You can enroll iOS devices by exporting a Corporate Enrollment profile and then connecting those mobile devices to a Mac that is running Apple Configurator.</span></span> <span data-ttu-id="ddfb0-127">O Apple Configurator dá suporte a duas formas de registro:</span><span class="sxs-lookup"><span data-stu-id="ddfb0-127">Apple Configurator supports two forms of enrollment:</span></span>

- <span data-ttu-id="ddfb0-128">**Registro no Assistente de Configuração**: redefine o dispositivo para as configurações de fábrica e o prepara para a configuração do novo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-128">**Setup Assistant enrollment**: Resets the device to factory settings and prepares it for setup by the device's new user.</span></span> <span data-ttu-id="ddfb0-129">Esse método requer que o administrador conecte o dispositivo iOS a um computador Mac via USB executando o Apple Configurator para pré-configurar o registro.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-129">This method requires the admin to connect the iOS device through USB to a Mac computer running Apple Configurator to preconfigure the enrollment.</span></span> <span data-ttu-id="ddfb0-130">Em seguida, os dispositivos são entregues aos usuários, que executam o Assistente de Configuração na primeira inicialização do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-130">Devices are then delivered to their users, who run the Setup Assistant when the devices first starts.</span></span> <span data-ttu-id="ddfb0-131">Esse processo configura o dispositivo dos usuários com suas credenciais corporativas ou de estudante e conclui o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-131">This process configures the device with users' work or school credentials and completes the enrollment process.</span></span> <span data-ttu-id="ddfb0-132">Para obter mais informações, confira [Registrar dispositivos iOS usando o Apple Configurator e o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-132">For more information, see [Enroll iOS devices with Apple Configurator and Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md).</span></span>
=======
## BYOD (Dispositivos iOS de propriedade do usuário)
<a id="user-owned-ios-devices-byod" class="xliff"></a>

Se os usuários desejarem registrar seus dispositivos pessoais BYOD (traga seu próprio dispositivo), eles poderão baixar o aplicativo do Portal da Empresa para iOS na Loja de Aplicativos e seguir as instruções de registro no aplicativo. Depois de registrado, os usuários podem se conectar à rede da empresa, ingressar no domínio ou no Azure Active Directory e obter acesso aos recursos corporativos. Para habilitar o cenário BYOD, o único requisito é ter um [certificado Apple Push Notification Service](apple-mdm-push-certificate-get.md). Você também pode bloquear o registro de dispositivos iOS pessoais. Consulte [Definir restrições de tipo de dispositivo](enrollment-restrictions-set.md) para obter instruções.

## Dispositivos macOS de propriedade do usuário (BYOD)
<a id="user-owned-macos-devices-byod" class="xliff"></a>

Você pode habilitar o registro de dispositivo macOS. Para habilitar o registro do macOS, o único requisito é ter um [certificado Apple Push Notification Service](apple-mdm-push-certificate-get.md). Para obter mais informações, consulte [Registrar dispositivos macOS](./macos-enroll.md)

## Programa de registro com a Apple
<a id="enrollment-program-with-apple" class="xliff"></a>
A Apple oferece programas de compra de dispositivo que incluem o registro de dispositivo e a infraestrutura de gerenciamento. O dispositivo comprado por meio de um desses programas pode ser registrado em massa em um registro “sem fio” com a atribuição de números de série do dispositivo ao gerenciamento do Intune.

- **DEP (Programa de registro de dispositivos)** – programa de registro de dispositivos da Apple para organizações e empresas. Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).
- **Apple School Manager** – programa de registro de dispositivos da Apple para escolas. Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md)

## Apple Configurator
<a id="apple-configurator" class="xliff"></a>

Você pode registrar dispositivos iOS exportando um perfil de Registro Corporativo e, em seguida, conectando esses dispositivos móveis a um Mac que esteja executando o Apple Configurator. O Apple Configurator dá suporte a duas formas de registro:

- **Registro no Assistente de Configuração**: redefine o dispositivo para as configurações de fábrica e o prepara para a configuração do novo usuário do dispositivo. Esse método requer que o administrador conecte o dispositivo iOS a um computador Mac via USB executando o Apple Configurator para pré-configurar o registro. Em seguida, os dispositivos são entregues aos usuários, que executam o Assistente de Configuração na primeira inicialização do dispositivo. Esse processo configura o dispositivo dos usuários com suas credenciais corporativas ou de estudante e conclui o processo de registro. Para obter mais informações, confira [Registrar dispositivos iOS usando o Apple Configurator e o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md).
>>>>>>> live

- <span data-ttu-id="ddfb0-133">**Registro direto**: cria um arquivo compatível com Apple Configurator para uso durante a preparação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-133">**Direct enrollment**: Creates an Apple Configurator–compliant file for use during device preparation.</span></span> <span data-ttu-id="ddfb0-134">O dispositivo registrado não é redefinido para os padrões de fábrica nem fica associado a nenhum usuário.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-134">The enrolled device isn’t factory reset, and it has no user affiliation.</span></span> <span data-ttu-id="ddfb0-135">Para registrar dispositivos, o administrador precisa conectar o dispositivo iOS por meio de USB em um computador Mac executando o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-135">To enroll devices, the admin is required to connect the iOS device through USB to a Mac computer running Apple Configurator.</span></span> <span data-ttu-id="ddfb0-136">Para saber mais, confira [Registrar dispositivos iOS usando o Apple Configurator Device Enrollment](apple-configurator-direct-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-136">For more information, see [Enroll iOS devices using Apple Configurator Direct Enrollment](apple-configurator-direct-enroll-ios.md).</span></span>

<<<<<<< HEAD
## <span data-ttu-id="ddfb0-137">Usar o DEP (Device Enrollment Program)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-137">Use the Device Enrollment Program (DEP)</span></span>
<a id="use-the-device-enrollment-program-dep" class="xliff"></a>

<span data-ttu-id="ddfb0-138">O DEP implanta um perfil de registro "over the air" em dispositivos que são adquiridos por meio do DEP.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-138">DEP deploys an enrollment profile “over the air” to devices that are purchased through DEP.</span></span> <span data-ttu-id="ddfb0-139">Quando o usuário executa o Assistente de Configuração no dispositivo na primeira inicialização, o dispositivo é registrado no Intune.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-139">When a user runs Setup Assistant on the device when it first starts, the device is enrolled in Intune.</span></span> <span data-ttu-id="ddfb0-140">Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-140">For more information, see [Enroll iOS devices using Device Enrollment Program](device-enrollment-program-enroll-ios.md).</span></span>

## <span data-ttu-id="ddfb0-141">Usar o DEM (Gerenciador de Registro de Dispositivos)</span><span class="sxs-lookup"><span data-stu-id="ddfb0-141">Use the device enrollment manager (DEM)</span></span>
<a id="use-the-device-enrollment-manager-dem" class="xliff"></a>
<span data-ttu-id="ddfb0-142">O gerenciador de registros de dispositivo é uma conta de usuário genérica que pode registrar e gerenciar até 1.000 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-142">Device enrollment manager is a generic user account that can enroll and manage up to 1,000 devices without.</span></span> <span data-ttu-id="ddfb0-143">Os dispositivos gerenciados pelo DEM não podem ter afinidade de usuário e, portanto, o dispositivo nunca tem um proprietário.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-143">DEM-managed devices cannot have user affinity, so the device never has an owner.</span></span> <span data-ttu-id="ddfb0-144">Conceda permissões DEM a um usuário do Intune para proporciona essas funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-144">You give DEM permissions to an Intune user to give them these capabilities.</span></span> <span data-ttu-id="ddfb0-145">Cada dispositivo que o usuário DEM registra usa uma licença do Intune.</span><span class="sxs-lookup"><span data-stu-id="ddfb0-145">Each device that the DEM user enrolls uses an Intune license.</span></span> <span data-ttu-id="ddfb0-146">Para obter mais informações, consulte [Registrar dispositivos usando o Gerenciador de registro de dispositivo](device-enrollment-manager-enroll.md).</span><span class="sxs-lookup"><span data-stu-id="ddfb0-146">For more information, see [Enroll devices using device enrollment manager](device-enrollment-manager-enroll.md).</span></span>
=======
## Usar o DEP (Device Enrollment Program)
<a id="use-the-device-enrollment-program-dep" class="xliff"></a>

O DEP implanta um perfil de registro "over the air" em dispositivos que são adquiridos por meio do DEP. Quando o usuário executa o Assistente de Configuração no dispositivo na primeira inicialização, o dispositivo é registrado no Intune. Para obter mais informações, consulte [Registrar dispositivos iOS usando o Programa de registro de dispositivos](device-enrollment-program-enroll-ios.md).

## Usar o DEM (Gerenciador de Registro de Dispositivos)
<a id="use-the-device-enrollment-manager-dem" class="xliff"></a>
O gerenciador de registros de dispositivo é uma conta de usuário genérica que pode registrar e gerenciar até 1.000 dispositivos. Os dispositivos gerenciados pelo DEM não podem ter afinidade de usuário e, portanto, o dispositivo nunca tem um proprietário. Conceda permissões DEM a um usuário do Intune para proporciona essas funcionalidades. Cada dispositivo que o usuário DEM registra usa uma licença do Intune. Para obter mais informações, consulte [Registrar dispositivos usando o Gerenciador de registro de dispositivo](device-enrollment-manager-enroll.md).
>>>>>>> live
