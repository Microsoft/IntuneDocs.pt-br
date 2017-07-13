---
title: Gerenciar dispositivos corporativos
description: "Registre dispositivos corporativos de diversas formas, com base no tipo de dispositivo, em como ele foi comprado e nas necessidades da organização."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8dae789ad1996543ddf9b92d031ac995beff6a46
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c83a7-103">Registrar dispositivos corporativos usando o Intune</span><span class="sxs-lookup"><span data-stu-id="c83a7-103">Enroll corporate-owned devices by using Intune</span></span>
<a id="enroll-corporate-owned-devices-by-using-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c83a7-104">Registre dispositivos corporativos ou da organização para registrá-los com o Intune de diversas formas, dependendo do tipo do dispositivo, de como ele foi adquirido e das necessidades da organização.</span><span class="sxs-lookup"><span data-stu-id="c83a7-104">You can enroll organization-owned or corporate-owned devices to manage with Intune in a variety of ways, depending on the type of device, how the device was purchased, and the needs of the organization.</span></span> <span data-ttu-id="c83a7-105">Você também pode instalar o aplicativo de Portal da Empresa para registrar e gerenciar dispositivos corporativos, como em cenários de BYOD ("traga seu próprio dispositivo").</span><span class="sxs-lookup"><span data-stu-id="c83a7-105">You also can install the Company Portal app to enroll and manage corporate-owned devices, like in a "bring your own device" (BYOD) scenario.</span></span>

<span data-ttu-id="c83a7-106">Por padrão, dispositivos para todas as plataformas têm permissão para se registrarem no Intune.</span><span class="sxs-lookup"><span data-stu-id="c83a7-106">By default, devices for all platforms are allowed to enroll in Intune.</span></span> <span data-ttu-id="c83a7-107">Para bloquear o registro de dispositivos, entre no [Portal de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="c83a7-107">To block devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span> <span data-ttu-id="c83a7-108">Escolha **Admin** > **Gerenciamento de Dispositivo Móvel** > **Regras de Registro** e desmarque as caixas de seleção aplicáveis para as plataformas que deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="c83a7-108">Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the applicable check boxes for the platforms that you want to block.</span></span>

## <span data-ttu-id="c83a7-109">Registrar dispositivos iOS corporativos</span><span class="sxs-lookup"><span data-stu-id="c83a7-109">Enroll corporate-owned iOS devices</span></span>
<a id="enroll-corporate-owned-ios-devices" class="xliff"></a>

<span data-ttu-id="c83a7-110">O métodos de registro de dispositivos corporativos são uma boa opção para cenários de CYOD "escolha seu próprio dispositivo".</span><span class="sxs-lookup"><span data-stu-id="c83a7-110">Corporate-owned device enrollment methods are a good choice for "choose your own device" (CYOD) scenarios.</span></span> <span data-ttu-id="c83a7-111">Em um ambiente de CYOD, a organização paga para um dispositivo que o usuário seleciona e a organização gerencia o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c83a7-111">In a CYOD environment, the organization pays for a device that the user selects, and the organization manages the device.</span></span>

<span data-ttu-id="c83a7-112">Se o usuário tiver dispositivos iOS entre os quais escolher, você pode pré-configurar registro para que o dispositivo seja gerenciado com o Intune desde a primeira vez em que o usuário o ativar.</span><span class="sxs-lookup"><span data-stu-id="c83a7-112">If you offer users iOS devices to choose from, you can preconfigure enrollment so that the device is managed with Intune from the first time the user turns it on.</span></span> <span data-ttu-id="c83a7-113">O Intune dá suporte ao registro por meio do [DEP (programa de registro de dispositivo) da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou usando a ferramenta Apple Configurator em um computador Mac para registro [direto](ios-direct-enrollment-in-microsoft-intune.md) ou com o [Assistente de Configuração](ios-setup-assistant-enrollment-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c83a7-113">Intune supports enrollment via the [Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md), or by using the Apple Configurator tool on a Mac computer for [direct](ios-direct-enrollment-in-microsoft-intune.md) or [Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) enrollment.</span></span>

<span data-ttu-id="c83a7-114">Saiba como [registrar dispositivos iOS corporativos](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c83a7-114">Learn how to [enroll corporate-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

## <span data-ttu-id="c83a7-115">Criar uma conta de gerenciador de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c83a7-115">Create a device enrollment manager account</span></span>
<a id="create-a-device-enrollment-manager-account" class="xliff"></a>

<span data-ttu-id="c83a7-116">Você pode criar uma conta de DEM (gerenciador de registro de dispositivo) de usuário único no Intune para gerenciar um grande número de dispositivos móveis na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c83a7-116">You can create a single-user device enrollment manager (DEM) account in Intune to manage a large number of mobile devices for your organization.</span></span> <span data-ttu-id="c83a7-117">Depois de criar uma conta de DEM, o gerente da conta designada pode registrar mais do que os 15 dispositivos que um usuário padrão pode registrar.</span><span class="sxs-lookup"><span data-stu-id="c83a7-117">After you create a DEM account, a designated account manager can enroll more than the 15 devices that a standard user can enroll.</span></span>

<span data-ttu-id="c83a7-118">Você pode usar uma conta de DEM para registrar apenas dispositivos que não são usados por um usuário único específico.</span><span class="sxs-lookup"><span data-stu-id="c83a7-118">You can use a DEM account to enroll only devices that aren't used by a single, specific user.</span></span> <span data-ttu-id="c83a7-119">Esses tipos de dispositivos são bons para aplicativos de ponto de venda ou utilitários, por exemplo, mas não para usuários que precisam acessar os recursos da empresa ou o email.</span><span class="sxs-lookup"><span data-stu-id="c83a7-119">Those types of devices are good for point-of-sale or utility apps, for example, but not for users who need to access email or company resources.</span></span>

<span data-ttu-id="c83a7-120">Saiba como [registrar dispositivos corporativos usando uma conta de DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c83a7-120">Learn how to [enroll corporate-owned devices by using a DEM account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).</span></span>

## <span data-ttu-id="c83a7-121">Registrar dispositivos Windows 10 Enterprise corporativos</span><span class="sxs-lookup"><span data-stu-id="c83a7-121">Enroll corporate-owned Windows 10 Enterprise devices</span></span>
<a id="enroll-corporate-owned-windows-10-enterprise-devices" class="xliff"></a>

<span data-ttu-id="c83a7-122">Caso utilize o Azure Active Directory Premium ou a Microsoft Enterprise Mobility Suite em sua organização, você pode [registrar dispositivos Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview).</span><span class="sxs-lookup"><span data-stu-id="c83a7-122">If you use Azure Active Directory Premium or Microsoft Enterprise Mobility Suite in your organization, you can [enroll Windows 10 Enterprise devices](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview).</span></span> <span data-ttu-id="c83a7-123">Quando um usuário adiciona uma conta corporativa ou de estudante a um dispositivo, o dispositivo é marcado automaticamente como "corporativo".</span><span class="sxs-lookup"><span data-stu-id="c83a7-123">When a user adds a work or school account on a device, the device is automatically tagged as "corporate-owned."</span></span>

## <span data-ttu-id="c83a7-124">Importar números IMEI</span><span class="sxs-lookup"><span data-stu-id="c83a7-124">Import IMEI numbers</span></span>
<a id="import-imei-numbers" class="xliff"></a>

<span data-ttu-id="c83a7-125">Muitos fabricantes de dispositivos móveis usam um número exclusivo chamado IMEI (identidade de equipamentos móveis internacional) em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c83a7-125">Many mobile device manufacturers use a unique number called an International Mobile Equipment Identity (IMEI) on their devices.</span></span> <span data-ttu-id="c83a7-126">Você pode importar números IMEI para dispositivos de propriedade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c83a7-126">You can import IMEI numbers for devices that your organization owns.</span></span> <span data-ttu-id="c83a7-127">Quando o dispositivo passa a ser gerenciado pelo Intune, ele é marcado como um dispositivo corporativo.</span><span class="sxs-lookup"><span data-stu-id="c83a7-127">When the device becomes managed by Intune, it's tagged as a corporate-owned device.</span></span>

<span data-ttu-id="c83a7-128">Saiba como [marcar dispositivos corporativos usando números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c83a7-128">Learn how to [tag corporate-owned devices by using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md).</span></span>

## <span data-ttu-id="c83a7-129">Identificar uma dispositivo como corporativo</span><span class="sxs-lookup"><span data-stu-id="c83a7-129">Identify a device as corporate-owned</span></span>
<a id="identify-a-device-as-corporate-owned" class="xliff"></a>

<span data-ttu-id="c83a7-130">O Intune reconhece um dispositivo como "corporativo" quando qualquer uma das seguintes condições forem verdadeiras:</span><span class="sxs-lookup"><span data-stu-id="c83a7-130">Intune recognizes a device as "corporate" when any of the following conditions are true:</span></span>

 - <span data-ttu-id="c83a7-131">O dispositivo foi [registrado usando uma conta de DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (todas as plataformas).</span><span class="sxs-lookup"><span data-stu-id="c83a7-131">The device was [enrolled by using a DEM account](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) (all platforms).</span></span>
 - <span data-ttu-id="c83a7-132">O dispositivo foi registrado usando o [DEP da Apple](ios-device-enrollment-program-in-microsoft-intune.md) ou o [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (somente iOS).</span><span class="sxs-lookup"><span data-stu-id="c83a7-132">The device was enrolled by using the [Apple DEP](ios-device-enrollment-program-in-microsoft-intune.md) or [Apple Configurator](ios-setup-assistant-enrollment-in-microsoft-intune.md) (iOS only).</span></span>
 - <span data-ttu-id="c83a7-133">O fabricante do dispositivo [declarou o dispositivo previamente usando números IMEI](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (todas as plataformas com números IMEI).</span><span class="sxs-lookup"><span data-stu-id="c83a7-133">The device manufacturer [predeclared the device by using IMEI numbers](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers.md) (all platforms with IMEI numbers).</span></span>
 - <span data-ttu-id="c83a7-134">O dispositivo está registrado no [Azure Active Directory ou no Enterprise Mobility Suite como um dispositivo Windows 10 Enterprise](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (somente Windows 10).</span><span class="sxs-lookup"><span data-stu-id="c83a7-134">The device is registered in [Azure Active Directory or Enterprise Mobility Suite as a Windows 10 Enterprise device](https://docs.microsoft.com/active-directory/active-directory-azureadjoin-windows10-devices-overview) (Windows 10 only).</span></span>

<span data-ttu-id="c83a7-135">Quando um dispositivo é marcado como corporativo, você verá **Corporativo** na coluna **Propriedade** para esse registro de dispositivo no console do administrador.</span><span class="sxs-lookup"><span data-stu-id="c83a7-135">When a device is tagged as corporate, you see **Corporate** in the **Ownership** column for that device record in the administrator console.</span></span> 
