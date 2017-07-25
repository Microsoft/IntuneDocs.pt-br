---
title: Habilitar registro de dispositivo
description: Definir a autoridade do MDM e habilitar o registro para dispositivos iOS, Windows, Android e Mac.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 64c6eb58246ac3ad232c1b8ee89d12a83e7e1784
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="54810-103">Habilitar registro para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="54810-103">Enable enrollment for mobile devices</span></span>
=======
# Habilitar registro para dispositivos móveis
>>>>>>> live
<a id="enable-enrollment-for-mobile-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="54810-104">Este tópico descreve como um administrador do Intune pode habilitar o registro de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="54810-104">This topic describes how an Intune administrator can enable mobile device enrollment.</span></span> <span data-ttu-id="54810-105">Para obter ajuda sobre como usar o Intune em seu telefone, consulte [usando dispositivos gerenciados para realizar seu trabalho](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="54810-105">For help using Intune on your phone, see [using managed devices to get work done](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).</span></span>

<span data-ttu-id="54810-106">Para configurar o gerenciamento de dispositivo móvel com o Intune, você deve primeiro definir a *autoridade de gerenciamento de dispositivo móvel*, que identifica o serviço que pode gerenciar dispositivos associados à sua conta.</span><span class="sxs-lookup"><span data-stu-id="54810-106">To set up mobile device management with Intune, you must first set the *mobile device management authority*, which identifies the service that can manage devices associated with your account.</span></span> <span data-ttu-id="54810-107">Estas diretrizes presumem que você usará o serviço do Intune em vez do System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="54810-107">This guidance assumes you will use the Intune service instead of System Center Configuration Manager.</span></span> <span data-ttu-id="54810-108">Depois que a autoridade MDM estiver configurada, você poderá habilitar o gerenciamento de plataformas de dispositivo e registrar seus dispositivos com o aplicativo de Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="54810-108">Once the MDM authority is set, you can enable management for device platforms, and enroll your devices with the Company Portal app.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="54810-109">Habilitar registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="54810-109">Enable device enrollment</span></span>
<a id="enable-device-enrollment" class="xliff"></a>

1. <span data-ttu-id="54810-110">**Torne o Intune sua autoridade de gerenciamento de dispositivo móvel** [No console de administração do Intune](https://manage.microsoft.com/), escolha **Admin** > **Gerenciamento de Dispositivo Móvel** e clique em **Definir Autoridade de MDM** em **Tarefas**.</span><span class="sxs-lookup"><span data-stu-id="54810-110">**Make Intune your mobile device management authority** In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Mobile Device Management**, and then choose **Set MDM Authority** under **Tasks**.</span></span>  
=======
## Habilitar registro de dispositivo
<a id="enable-device-enrollment" class="xliff"></a>

1. **Torne o Intune sua autoridade de gerenciamento de dispositivo móvel** [No console de administração do Intune](https://manage.microsoft.com/), escolha **Admin** > **Gerenciamento de Dispositivo Móvel** e clique em **Definir Autoridade de MDM** em **Tarefas**.  
>>>>>>> live

2. <span data-ttu-id="54810-111">Selecione **Sim** na caixa de diálogo de Autoridade de MDM.</span><span class="sxs-lookup"><span data-stu-id="54810-111">Choose **Yes** in the MDM Authority dialog box.</span></span>

    ![Console de administração.](../media/intune-mdm-authority.png)

<<<<<<< HEAD
## <span data-ttu-id="54810-114">Escolha como registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="54810-114">Choose how to enroll devices</span></span>
=======
## Escolha como registrar dispositivos
>>>>>>> live
<a id="choose-how-to-enroll-devices" class="xliff"></a>

<span data-ttu-id="54810-115">O Intune pode gerenciar dispositivos de várias maneiras, dependendo dos requisitos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="54810-115">Intune can manage devices in a variety of ways depending upon your company's requirements.</span></span> <span data-ttu-id="54810-116">"Traga seu próprio dispositivo" (BYOD), dispositivos de propriedade corporativa, "escolha seu próprio dispositivo" (CYOD) e os dispositivos de modo de quiosque são apenas alguns cenários de registro disponíveis.</span><span class="sxs-lookup"><span data-stu-id="54810-116">"Bring your own device" (BYOD), corpoarte-owned devices, "choose your own device" (CYOD), and kiosk-mode devices are just a few available enrollment scenarios.</span></span>

<span data-ttu-id="54810-117">Siga estas etapas para [Escolher como registrar dispositivos](choose-how-to-enroll-devices1.md).</span><span class="sxs-lookup"><span data-stu-id="54810-117">Follow these steps to [Choose how to enroll devices](choose-how-to-enroll-devices1.md).</span></span>

<<<<<<< HEAD
## <span data-ttu-id="54810-118">Habilitar o MDM para sua plataforma de dispositivo</span><span class="sxs-lookup"><span data-stu-id="54810-118">Enable MDM for your device platform</span></span>
<a id="enable-mdm-for-your-device-platform" class="xliff"></a>
<span data-ttu-id="54810-119">O registro deve ser habilitado para iOS, Mac e Android para dispositivos de Trabalho estabelecendo uma relação entre o provedor de plataforma e o seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="54810-119">Enrollment must be enabled for iOS, Mac, and Android for Work devices establishing a relationship between the platform provider and your Intune tenant.</span></span> <span data-ttu-id="54810-120">Dispositivos Android e Windows não exigem etapas adicionais, mas em dispositivos Windows, você pode simplificar o registro do dispositivo para seus usuários ao criar uma entrada de Registro DNS especial.</span><span class="sxs-lookup"><span data-stu-id="54810-120">Windows and Android devices do not require additional steps, but for Windows devices you can simplify device enrollment for your users by creating a special DNS registry entry.</span></span>
=======
## Habilitar o MDM para sua plataforma de dispositivo
<a id="enable-mdm-for-your-device-platform" class="xliff"></a>
O registro deve ser habilitado para iOS, Mac e Android para dispositivos de Trabalho estabelecendo uma relação entre o provedor de plataforma e o seu locatário do Intune. Dispositivos Android e Windows não exigem etapas adicionais, mas em dispositivos Windows, você pode simplificar o registro do dispositivo para seus usuários ao criar uma entrada de Registro DNS especial.
>>>>>>> live

<span data-ttu-id="54810-121">Habilite o registro de dispositivo para a plataforma de dispositivo que deseja gerenciar.</span><span class="sxs-lookup"><span data-stu-id="54810-121">Enable device enrollment for the device platform you want to manage.</span></span> <span data-ttu-id="54810-122">Dependendo de sua plataforma, são necessários requisitos diferentes:</span><span class="sxs-lookup"><span data-stu-id="54810-122">Depending on your platform, different requirements are needed:</span></span>

- [<span data-ttu-id="54810-123">iOS e macOS</span><span class="sxs-lookup"><span data-stu-id="54810-123">iOS and macOS</span></span>](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [<span data-ttu-id="54810-124">Windows 10 e Windows Phone</span><span class="sxs-lookup"><span data-stu-id="54810-124">Window 10 and Windows Phone</span></span>](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- [<span data-ttu-id="54810-125">PC com Windows</span><span class="sxs-lookup"><span data-stu-id="54810-125">Window PC</span></span>](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (cliente de software do Intune)
- [<span data-ttu-id="54810-126">Android for Work</span><span class="sxs-lookup"><span data-stu-id="54810-126">Android for Work</span></span>](/intune-classic/deploy-use/set-up-android-for-work)

<span data-ttu-id="54810-127">Quando o registro estiver habilitado, os usuários poderão baixar o aplicativo de Portal da Empresa em seu dispositivo e concluir o processo de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="54810-127">Once enrollment is enabled, users can download the Company Portal app to their device and complete the device enrollment process.</span></span>

<<<<<<< HEAD
### <span data-ttu-id="54810-128">Habilitar o registro de dispositivo da empresa</span><span class="sxs-lookup"><span data-stu-id="54810-128">Enable company-owned device enrollment</span></span>
<a id="enable-company-owned-device-enrollment" class="xliff"></a>
<span data-ttu-id="54810-129">Você também pode habilitar uma variedade de situações de [registro de dispositivo da empresa](/intune-classic/deploy-use/manage-corporate-owned-devices), incluindo:</span><span class="sxs-lookup"><span data-stu-id="54810-129">You can also enable a variety of [company-owned device enrollment](/intune-classic/deploy-use/manage-corporate-owned-devices) scenarios including:</span></span>
- [<span data-ttu-id="54810-130">Programa de Registro do Dispositivo da Apple</span><span class="sxs-lookup"><span data-stu-id="54810-130">Apple Device Enrollment Program</span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [<span data-ttu-id="54810-131">Registro do Assistente de Configuração do Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="54810-131">Apple Configurator Setup Assistant enrollment</span></span>](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [<span data-ttu-id="54810-132">Registro direto do Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="54810-132">Apple Configurator direct enrollment</span></span>](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [<span data-ttu-id="54810-133">Gerenciador de Registro de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="54810-133">Device Enrollment Manager</span></span>](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <span data-ttu-id="54810-134">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="54810-134">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="54810-135">Parabéns!</span><span class="sxs-lookup"><span data-stu-id="54810-135">Congratulations!</span></span> <span data-ttu-id="54810-136">Você acabou de concluir a última etapa do *Guia de início rápido do Intune*.</span><span class="sxs-lookup"><span data-stu-id="54810-136">You have just completed the last step of the *Intune quick start guide*.</span></span> <span data-ttu-id="54810-137">Agora que sua configuração inicial foi concluída, você pode considerar habilitar funcionalidades adicionais do MDM.</span><span class="sxs-lookup"><span data-stu-id="54810-137">Now that your initial configuration is complete, you can consider enabling additional MDM functionality.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="54810-138">&larr; **Registrar dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tarefas de pós-configuração** &rarr;</span><span class="sxs-lookup"><span data-stu-id="54810-138">&larr; **Enroll devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Post-configuration tasks** &rarr;</span></span>](.\post-configuration-tasks.md)  
=======
### Habilitar o registro de dispositivo da empresa
<a id="enable-company-owned-device-enrollment" class="xliff"></a>
Você também pode habilitar uma variedade de situações de [registro de dispositivo da empresa](/intune-classic/deploy-use/manage-corporate-owned-devices), incluindo:
- [Programa de Registro do Dispositivo da Apple](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [Registro do Assistente de Configuração do Apple Configurator](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [Registro direto do Apple Configurator](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [Gerenciador de Registro de Dispositivos](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### Próximas etapas
<a id="next-steps" class="xliff"></a>
Parabéns! Você acabou de concluir a última etapa do *Guia de início rápido do Intune*. Agora que sua configuração inicial foi concluída, você pode considerar habilitar funcionalidades adicionais do MDM.

>[!div class="step-by-step"]
>[&larr; **Registrar dispositivos**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Tarefas de pós-configuração** &rarr;](.\post-configuration-tasks.md)  
>>>>>>> live
