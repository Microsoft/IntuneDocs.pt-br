---
title: "O que são perfis de dispositivo no Microsoft Intune?"
titleSuffix: Intune on Azure
description: Saiba mais sobre os perfis de dispositivo do Intune e como eles podem ajudar a gerenciar e proteger os dispositivos em sua empresa.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5288bfc3aebbd119b49ef5261944840fd863afa5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="73cc2-103">O que são perfis de dispositivo do Microsoft Intune?</span><span class="sxs-lookup"><span data-stu-id="73cc2-103">What are Microsoft Intune device profiles?</span></span>
<a id="what-are-microsoft-intune-device-profiles" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="73cc2-104">Use o a carga de trabalho **Configuração de dispositivo** do Microsoft Intune para gerenciar as configurações e recursos em todos os dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="73cc2-104">Use the Microsoft Intune **Device configuration** workload to manage settings and features on all of the devices you manage.</span></span> <span data-ttu-id="73cc2-105">Na maioria das vezes, você usará essa carga de trabalho para criar perfis de dispositivo, que permitem gerenciar e controlar um intervalo inteiro de diferentes recursos e funcionalidades nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73cc2-105">You mostly use this workload to create device profiles, which let you manage and control a whole range of different features and functionality on devices.</span></span>

<span data-ttu-id="73cc2-106">Quando você abrir essa carga de trabalho, verá as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="73cc2-106">When you open this workload, you see the following options:</span></span>

- <span data-ttu-id="73cc2-107">**Visão geral** – Essa página fornece status e relatórios que ajudarão a monitorar as configurações de dispositivo que você atribuiu a usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73cc2-107">**Overview** - This page gives you status and reports that help you monitor device configurations that you have assigned to users and devices.</span></span>
- <span data-ttu-id="73cc2-108">**Gerenciar Perfis** – Esta é a seção que você acessará para criar perfis de configuração de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73cc2-108">**Manage Profiles** - This section is where you go to create device configuration profiles.</span></span> <span data-ttu-id="73cc2-109">você pode encontrar uma lista de todos os tipos de perfil que você pode criar posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="73cc2-109">You can find a list all the profile types you can create later in this topic.</span></span>
- <span data-ttu-id="73cc2-110">**Configurar a autoridade de certificação** – Este fluxo de trabalho guia você pelas as etapas necessárias para configurar perfis de certificados do Intune.</span><span class="sxs-lookup"><span data-stu-id="73cc2-110">**Setup Certificate Authority** - This workflow walks you though the steps required to configure Intune certificate profiles.</span></span>

## <span data-ttu-id="73cc2-111">Introdução</span><span class="sxs-lookup"><span data-stu-id="73cc2-111">Getting started</span></span>
<a id="getting-started" class="xliff"></a>

<span data-ttu-id="73cc2-112">O fluxo de trabalho para a criação de perfis de dispositivo é semelhante para todos os perfis.</span><span class="sxs-lookup"><span data-stu-id="73cc2-112">The workflow for creating device profiles is similar for all profiles.</span></span> <span data-ttu-id="73cc2-113">Leia [Como criar perfis de configuração de dispositivo do Microsoft Intune](device-profile-create.md) para obter informações.</span><span class="sxs-lookup"><span data-stu-id="73cc2-113">Read [How to create Microsoft Intune device configuration profiles](device-profile-create.md) for information.</span></span> <span data-ttu-id="73cc2-114">Depois, continue lendo para obter informações específicas sobre a criação de configurações para cada tipo de perfil.</span><span class="sxs-lookup"><span data-stu-id="73cc2-114">Then read on for specific information about creating settings for each profile type.</span></span>

<span data-ttu-id="73cc2-115">É possível gerenciar os seguintes recursos em seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="73cc2-115">You can manage the following capabilities on your devices:</span></span>

## <span data-ttu-id="73cc2-116">Recursos de dispositivo</span><span class="sxs-lookup"><span data-stu-id="73cc2-116">Device features</span></span>
<a id="device-features" class="xliff"></a>

<span data-ttu-id="73cc2-117">Os recursos de dispositivo permitem que você controle os recursos em dispositivos iOS e macOS, como AirPrint, notificações e configurações compartilhadas do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73cc2-117">Device features let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.</span></span>
<span data-ttu-id="73cc2-118">Para saber mais, veja [Como definir as configurações de recursos do dispositivo](device-features-configure.md) Oferece suporte a: iOS e macOS.</span><span class="sxs-lookup"><span data-stu-id="73cc2-118">For more information, see [How to configure device feature settings](device-features-configure.md) Supports: iOS and macOS.</span></span>

## <span data-ttu-id="73cc2-119">Restrições de dispositivo</span><span class="sxs-lookup"><span data-stu-id="73cc2-119">Device restrictions</span></span>
<a id="device-restrictions" class="xliff"></a>
<span data-ttu-id="73cc2-120">Restrições de dispositivo permitem controlar muitas configurações em dispositivos gerenciados, incluindo configurações de segurança, hardware e compartilhamento de dados.</span><span class="sxs-lookup"><span data-stu-id="73cc2-120">Device restrictions let you control many settings on devices you manage across categories including security, hardware, and data sharing settings.</span></span> <span data-ttu-id="73cc2-121">Por exemplo, você pode criar um perfil de restrição de dispositivo que impede que os usuários de dispositivos iOS acessem a câmera do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73cc2-121">For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.</span></span>
<span data-ttu-id="73cc2-122">Para obter mais informações, consulte [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md) Há suporte para: Android, iOS, macOS, Windows 10 e Windows 10 Team.</span><span class="sxs-lookup"><span data-stu-id="73cc2-122">For more information, see [How to configure device restriction settings](device-restrictions-configure.md) Supports: Android, iOS, macOS, Windows 10, and Windows 10 Team.</span></span>

## <span data-ttu-id="73cc2-123">Email</span><span class="sxs-lookup"><span data-stu-id="73cc2-123">Email</span></span>
<a id="email" class="xliff"></a>
<span data-ttu-id="73cc2-124">Os perfis de email ajudam a criar, atribuir e monitorar configurações de email do Exchange ActiveSync nos dispositivos que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="73cc2-124">Email profiles let you create, assign, and monitor Exchange ActiveSync email settings on devices you manage.</span></span> <span data-ttu-id="73cc2-125">Os perfis de email ajudam a garante a consistência, reduzem chamadas de suporte e permitem que os usuários finais tenham acesso ao email da empresa em seus dispositivos pessoais sem qualquer configuração necessária da parte deles.</span><span class="sxs-lookup"><span data-stu-id="73cc2-125">Email profiles help ensure consistency, reduce support calls, and let end-users access company email on their personal devices without any required setup on their part.</span></span>
<span data-ttu-id="73cc2-126">Para obter mais informações, consulte [Como definir as configurações de email](email-settings-configure.md) Há suporte para: Android, iOS, Windows Phone 8.1 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-126">For more information, see [How to configure email settings](email-settings-configure.md) Supports: Android, iOS, Windows Phone 8.1, and Windows 10.</span></span>

## <span data-ttu-id="73cc2-127">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="73cc2-127">Wi-Fi</span></span>
<a id="wi-fi" class="xliff"></a>
<span data-ttu-id="73cc2-128">Use os perfis de Wi-Fi para atribuir configurações de rede sem fio para usuários e dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="73cc2-128">Use Wi-Fi profiles to assign wireless network settings to users and devices in your organization.</span></span> <span data-ttu-id="73cc2-129">Quando você atribuir um perfil de Wi-Fi, os usuários terão acesso ao Wi-Fi de sua empresa sem precisar configurá-lo por conta própria.</span><span class="sxs-lookup"><span data-stu-id="73cc2-129">When you assign a Wi-Fi profile, your users get access to your corporate Wi-Fi without having to configure it themselves.</span></span>
<span data-ttu-id="73cc2-130">Para obter mais informações, consulte [Como definir configurações de Wi-Fi](wi-fi-settings-configure.md) Há suporte para: Android, iOS, macOS e Windows 8.1 (somente importação).</span><span class="sxs-lookup"><span data-stu-id="73cc2-130">For more information, see [How to configure Wi-Fi settings](wi-fi-settings-configure.md) Supports: Android, iOS, macOS, and Windows 8.1 (import only).</span></span>

## <span data-ttu-id="73cc2-131">VPN</span><span class="sxs-lookup"><span data-stu-id="73cc2-131">VPN</span></span>
<a id="vpn" class="xliff"></a>
<span data-ttu-id="73cc2-132">Redes virtuais privadas (VPN) oferecem aos usuários acesso remoto seguro à rede da empresa.</span><span class="sxs-lookup"><span data-stu-id="73cc2-132">Virtual private networks (VPNs) give your users secure remote access to your company network.</span></span> <span data-ttu-id="73cc2-133">Dispositivos usam um perfil de conexão VPN para iniciar uma conexão com o servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="73cc2-133">Devices use a VPN connection profile to initiate a connection with the VPN server.</span></span> <span data-ttu-id="73cc2-134">Atribua perfis VPN aos usuários e dispositivos na sua organização para que eles possam se conectar à rede de forma fácil e segura.</span><span class="sxs-lookup"><span data-stu-id="73cc2-134">Assign VPN profiles to users and devices in your organization, so they can easily and securely connect to the network.</span></span>
<span data-ttu-id="73cc2-135">Para obter mais informações, consulte [Como definir as configurações de VPN](vpn-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="73cc2-135">For more information, see [How to configure VPN settings](vpn-settings-configure.md).</span></span>
<span data-ttu-id="73cc2-136">Há suporte para: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-136">Supports: Android, iOS, macOS, Windows Phone 8.1, Windows 8.1, and Windows 10.</span></span>

## <span data-ttu-id="73cc2-137">Educação</span><span class="sxs-lookup"><span data-stu-id="73cc2-137">Education</span></span>
<a id="education" class="xliff"></a>
<span data-ttu-id="73cc2-138">Permite configurar opções o aplicativo Windows Take a Test.</span><span class="sxs-lookup"><span data-stu-id="73cc2-138">Lets you configure options for the Windows Take a Test app.</span></span> <span data-ttu-id="73cc2-139">Quando você configura essas opções, nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.</span><span class="sxs-lookup"><span data-stu-id="73cc2-139">When you configure these options, no other apps can run on the device until the test is complete.</span></span>
<span data-ttu-id="73cc2-140">Para saber mais, veja [Como definir as configurações de educação](education-settings-configure.md)</span><span class="sxs-lookup"><span data-stu-id="73cc2-140">For more information, see [How to configure education settings](education-settings-configure.md)</span></span>

## <span data-ttu-id="73cc2-141">Certificados</span><span class="sxs-lookup"><span data-stu-id="73cc2-141">Certificates</span></span>
<a id="certificates" class="xliff"></a>
<span data-ttu-id="73cc2-142">Esse tipo de perfil permite que você configure certificados SCEP e PKCS confiáveis que podem ser atribuídos aos dispositivos e usados para autenticar o Wi-Fi, VPN e perfis de email.</span><span class="sxs-lookup"><span data-stu-id="73cc2-142">This profile type lets you configure trusted, SCEP, and PKCS certificates that can be assigned to devices and used to authenticate Wi-Fi, VPN, and email profiles.</span></span>
<span data-ttu-id="73cc2-143">Para obter mais informações, consulte [Como configurar certificados](certificates-configure.md) Há suporte para: Android, iOS, Windows Phone 8.1, Windows 8.1 e Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-143">For more information, see [How to configure certificates](certificates-configure.md) Supports: Android, iOS, Windows Phone 8.1, Windows 8.1, and Windows 10.</span></span>

## <span data-ttu-id="73cc2-144">Atualização de edição</span><span class="sxs-lookup"><span data-stu-id="73cc2-144">Edition upgrade</span></span>
<a id="edition-upgrade" class="xliff"></a>
<span data-ttu-id="73cc2-145">Este tipo de perfil permite atualizar automaticamente dos dispositivos que executam algumas versões do Windows 10 para uma edição mais recente.</span><span class="sxs-lookup"><span data-stu-id="73cc2-145">This profile type lets you automatically upgrade devices that run some versions of Windows 10 to a newer edition.</span></span>
<span data-ttu-id="73cc2-146">Para obter mais informações, consulte [Como configurar upgrades da edição do Windows 10](edition-upgrade-configure-windows-10.md) Há suporte para: somente Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-146">For more information, see [How to configure Windows 10 edition upgrades](edition-upgrade-configure-windows-10.md) Supports: Windows 10 only.</span></span>

## <span data-ttu-id="73cc2-147">Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="73cc2-147">Endpoint protection</span></span>
<a id="endpoint-protection" class="xliff"></a>
<span data-ttu-id="73cc2-148">Este tipo de perfil permite definir as configurações do BitLocker para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-148">This profile type lets you configure BitLocker settings for Windows 10 devices.</span></span>
<span data-ttu-id="73cc2-149">Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10](endpoint-protection-windows-10.md) Há suporte para: somente Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-149">For more information, see [Endpoint protection settings for Windows 10](endpoint-protection-windows-10.md) Supports: Windows 10 only.</span></span>

## <span data-ttu-id="73cc2-150">Windows Information Protection</span><span class="sxs-lookup"><span data-stu-id="73cc2-150">Windows Information Protection</span></span>
<a id="windows-information-protection" class="xliff"></a>
<span data-ttu-id="73cc2-151">A Proteção de Informações do Windows ajuda a proteger contra esses possíveis vazamentos de dados sem interferir na experiência do funcionário.</span><span class="sxs-lookup"><span data-stu-id="73cc2-151">Windows Information Protection helps to protect against data leakage without otherwise interfering with the employee experience.</span></span> <span data-ttu-id="73cc2-152">Ele também ajuda a proteger dados e aplicativos corporativos e contra vazamentos de dados acidentais em dispositivos pessoais e de funcionários que os funcionários trazem para o trabalho sem a necessidade de alterações em seu ambiente ou outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="73cc2-152">It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.</span></span>
<span data-ttu-id="73cc2-153">Para obter mais informações, consulte [Como configurar a Proteção de Informações do Windows](windows-information-protection-configure.md) Há suporte para: somente Windows 10.</span><span class="sxs-lookup"><span data-stu-id="73cc2-153">For more information, see [How to configure Windows Information Protection](windows-information-protection-configure.md) Supports: Windows 10 only.</span></span>

## <span data-ttu-id="73cc2-154">Personalizado</span><span class="sxs-lookup"><span data-stu-id="73cc2-154">Custom</span></span>
<a id="custom" class="xliff"></a>
<span data-ttu-id="73cc2-155">Configurações personalizadas permitem atribuir configurações de dispositivo que não são internos ao Intune.</span><span class="sxs-lookup"><span data-stu-id="73cc2-155">Custom settings let you assign device settings that are not built-into Intune.</span></span> <span data-ttu-id="73cc2-156">Por exemplo, em dispositivos Android, você pode especificar valores de OMA-URI que configuram o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="73cc2-156">For example, on Android devices, you can specify OMA-URI values that configure the device.</span></span> <span data-ttu-id="73cc2-157">Para dispositivos iOS, você pode importar um arquivo de configuração criado com o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="73cc2-157">For iOS devices, you can import a configuration file you created in the Apple Configurator.</span></span>
<span data-ttu-id="73cc2-158">Para obter mais informações, consulte [Como definir configurações personalizadas](custom-settings-configure.md) Há suporte para: Android, iOS, macOS e Windows Phone 8.1.</span><span class="sxs-lookup"><span data-stu-id="73cc2-158">For more information, see [How to configure custom settings](custom-settings-configure.md) Supports: Android, iOS, macOS, and Windows Phone 8.1.</span></span>

## <span data-ttu-id="73cc2-159">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="73cc2-159">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="73cc2-160">Escolha um dos tipos de perfil na lista para começar a configurar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="73cc2-160">Choose one of the profile types from the list to get started configuring devices.</span></span>
