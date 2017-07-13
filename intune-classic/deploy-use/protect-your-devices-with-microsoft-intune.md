---
title: Proteger dispositivos com o Microsoft Intune
description: "Conheça algumas das maneiras que o Intune pode ajudar a que proteger seus dispositivos contra acesso não autorizado e outras ameaças."
keywords: 
author: Robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71e0cbf3-2bfb-412e-8a12-8503df08b4cf
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8acde93c1c0c0d3bf443daf61d5f8d75b3d061df
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="051b1-103">Proteger dispositivos com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="051b1-103">Protect devices with Microsoft Intune</span></span>
<a id="protect-devices-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="051b1-104">O Microsoft Intune oferece um conjunto completo de recursos para ajudá-lo a proteger dispositivos gerenciados e os dados armazenados nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="051b1-104">Microsoft Intune offers a full set of capabilities to help you protect the devices you manage, and the data stored on those devices.</span></span> <span data-ttu-id="051b1-105">Leia este tópico para conhecer as noções básicas sobre esses recursos e saber como obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="051b1-105">Read this topic to learn the basics of these capabilities and to find out how to learn more.</span></span>

## <span data-ttu-id="051b1-106">Maneiras gerais para proteger todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="051b1-106">General ways to protect all devices</span></span>
<a id="general-ways-to-protect-all-devices" class="xliff"></a>

### <span data-ttu-id="051b1-107">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="051b1-107">Device configuration</span></span>
<a id="device-configuration" class="xliff"></a>
<span data-ttu-id="051b1-108">As [políticas de configuração](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) do Intune o ajudam a proteger e configurar dispositivos controlando uma infinidade de recursos e configurações.</span><span class="sxs-lookup"><span data-stu-id="051b1-108">Intune [configuration policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md), help you protect and configure devices by controlling a multitude of settings and features.</span></span> <span data-ttu-id="051b1-109">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="051b1-109">For example:</span></span>
- <span data-ttu-id="051b1-110">Você pode restringir o uso de recursos de hardware no dispositivo, como a câmera ou o Bluetooth.</span><span class="sxs-lookup"><span data-stu-id="051b1-110">You can restrict use of hardware features on the device such as the camera, or Bluetooth.</span></span>
- <span data-ttu-id="051b1-111">Você pode configurar aplicativos compatíveis e incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="051b1-111">You can configure compliant and noncompliant apps.</span></span> <span data-ttu-id="051b1-112">Você será alertado se um aplicativo não compatível for instalado (e algumas plataformas podem realmente bloquear a instalação).</span><span class="sxs-lookup"><span data-stu-id="051b1-112">You will be alerted if a noncompliant app is installed (and some platforms can actually block the install).</span></span>

### <span data-ttu-id="051b1-113">Redefinir senhas quando os usuários estão bloqueados de seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="051b1-113">Reset passcodes when users are locked out of their devices</span></span>
<a id="reset-passcodes-when-users-are-locked-out-of-their-devices" class="xliff"></a>
<span data-ttu-id="051b1-114">Como a primeira etapa na proteção dos dados da empresa em dispositivos móveis é exigir uma senha para usar o dispositivo, às vezes, você precisa [redefinir uma senha](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) ou ajudar um funcionário a fazê-lo, removendo a senha ou configurando uma senha temporária remotamente.</span><span class="sxs-lookup"><span data-stu-id="051b1-114">Since the first step in protecting company data on mobile devices is to require a passcode to use the device, sometimes you have to [reset a passcode](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) or help an employee do so, either by removing the passcode or setting a temporary passcode remotely.</span></span> <span data-ttu-id="051b1-115">Você também poderá [bloquear um dispositivo remotamente](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) se ele for perdido ou roubado.</span><span class="sxs-lookup"><span data-stu-id="051b1-115">You can also [lock a device remotely](use-remote-lock-and-passcode-reset-in-microsoft-intune.md) if it is lost or stolen.</span></span>

### <span data-ttu-id="051b1-116">Desativar dispositivos e remover dados</span><span class="sxs-lookup"><span data-stu-id="051b1-116">Retire devices and remove data</span></span>
<a id="retire-devices-and-remove-data" class="xliff"></a>
<span data-ttu-id="051b1-117">Quando um dispositivo precisa ser [removido do gerenciamento do Intune](retire-devices-from-microsoft-intune-management.md) (por exemplo, um usuário sai ou o dispositivo é perdido ou roubado), é provável que você queira remover dados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="051b1-117">When a device needs to be [removed from Intune management](retire-devices-from-microsoft-intune-management.md) (for example, a user leaves, or the device is lost or stolen), it's likely that you will want to remove data from that device.</span></span> <span data-ttu-id="051b1-118">O Intune fornece diversos métodos para garantir que os dados da empresa permaneçam seguros.</span><span class="sxs-lookup"><span data-stu-id="051b1-118">Intune provides a range of methods to ensure your company data remains secure.</span></span>

### <span data-ttu-id="051b1-119">Exigir que is dispositivos sejam compatíveis</span><span class="sxs-lookup"><span data-stu-id="051b1-119">Require devices to be compliant</span></span>
<a id="require-devices-to-be-compliant" class="xliff"></a>
<span data-ttu-id="051b1-120">O Intune tem [políticas de conformidade do dispositivo](introduction-to-device-compliance-policies-in-microsoft-intune.md) que permitem avaliar (e, em alguns casos, corrigir) dispositivos que não são compatíveis com as regras que você especifica.</span><span class="sxs-lookup"><span data-stu-id="051b1-120">Intune features [device compliance policies](introduction-to-device-compliance-policies-in-microsoft-intune.md) that let you evaluate (and in some cases remediate) devices that are not compliant with rules you specify.</span></span> <span data-ttu-id="051b1-121">Por exemplo, você pode relatar dispositivos iOS que são desbloqueados, se os dispositivos são criptografados ou se dispositivos Windows 10 são relatados como íntegros pelo Serviço de Atestado de Integridade.</span><span class="sxs-lookup"><span data-stu-id="051b1-121">For example, you can report about iOS devices that are jailbroken, whether devices are encrypted, or whether Windows 10 devices are reported as healthy by the Health Attestation Service.</span></span>

### <span data-ttu-id="051b1-122">Proteger aplicativos e os dados que eles usam</span><span class="sxs-lookup"><span data-stu-id="051b1-122">Protect apps and the data they use</span></span>
<a id="protect-apps-and-the-data-they-use" class="xliff"></a>
<span data-ttu-id="051b1-123">O Intune oferece vários recursos para ajudá-lo a proteger seus dados e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="051b1-123">Intune gives you a range of features to help you protect apps and their data.</span></span> <span data-ttu-id="051b1-124">Por exemplo, políticas de MAM (gerenciamento de aplicativos móveis) podem impedir que seja feito backup dos dados de um aplicativo protegido, restringir as opções de copiar e colar em outros aplicativos, exigir um PIN para acessar um aplicativo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="051b1-124">For example, mobile application management (MAM) policies can prevent data from being backed up from a protected app, restrict copy and paste to other apps, require a PIN to access an app, and more.</span></span> <span data-ttu-id="051b1-125">Para obter mais detalhes sobre como proteger aplicativos, veja [Proteger aplicativos e dados com o Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="051b1-125">For more details about protecting apps, see [Protect apps and data with Microsoft Intune](protect-apps-and-data-with-microsoft-intune.md)</span></span>

### <span data-ttu-id="051b1-126">Adicionar uma camada adicional de proteção aos dispositivos</span><span class="sxs-lookup"><span data-stu-id="051b1-126">Add an additional layer of protection to devices</span></span>
<a id="add-an-additional-layer-of-protection-to-devices" class="xliff"></a>
<span data-ttu-id="051b1-127">O [MFA (autenticação multifator)](multi-factor-authentication-azure-active-directory.md) é uma maneira mais segura de autenticar os usuários de dispositivos na rede.</span><span class="sxs-lookup"><span data-stu-id="051b1-127">[Multi-factor authentication (MFA)](multi-factor-authentication-azure-active-directory.md) is a more secure way of authenticating the users of devices on the network.</span></span>  <span data-ttu-id="051b1-128">Com o MFA, os usuários precisam confirmar sua identidade além do nome de usuário e a senha, por meio de uma chamada telefônica ou mensagem de texto.</span><span class="sxs-lookup"><span data-stu-id="051b1-128">With MFA, users need to confirm their identity beyond user name and password, through a phone call, or text message.</span></span>

## <span data-ttu-id="051b1-129">Recursos adicionais para dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="051b1-129">Further capabilities for Windows devices</span></span>
<a id="further-capabilities-for-windows-devices" class="xliff"></a>

### <span data-ttu-id="051b1-130">Controlar configurações do Windows Hello para Empresas em dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="051b1-130">Control Windows Hello for Business settings on Windows devices</span></span>
<a id="control-windows-hello-for-business-settings-on-windows-devices" class="xliff"></a>
<span data-ttu-id="051b1-131">O Intune permite integrar-se ao [Windows Hello for Business](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (conhecido anteriormente como Microsoft Passport), que é um método de entrada alternativo para o Windows 10 e posterior que usa o Active Directory ou uma conta do Azure Active Directory para substituir uma senha, um cartão inteligente ou um cartão inteligente virtual.</span><span class="sxs-lookup"><span data-stu-id="051b1-131">Intune lets you integrate with [Windows Hello for Business](control-microsoft-passport-settings-on-devices-with-microsoft-intune.md) (formerly Microsoft Passport) which is an alternative sign-in method for Windows 10 and later that uses Active Directory, or an Azure Active Directory account to replace a password, smart card, or virtual smart card.</span></span>

## <span data-ttu-id="051b1-132">Recursos adicionais para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="051b1-132">Further capabilities for iOS devices</span></span>
<a id="further-capabilities-for-ios-devices" class="xliff"></a>

### <span data-ttu-id="051b1-133">Bypass do Bloqueio de Ativação em dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="051b1-133">Bypass Activation Lock on iOS devices</span></span>
<a id="bypass-activation-lock-on-ios-devices" class="xliff"></a>
<span data-ttu-id="051b1-134">O Bloqueio de Ativação é um recurso que ajuda a proteger os dispositivos dos usuários exigindo que a ID da Apple e a senha sejam inseridas antes do usuário poder apagar ou reativar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="051b1-134">Activation Lock is a feature that help protect users' devices by requiring their Apple ID and password to be entered before anyone can erase, or reactivate the device.</span></span> <span data-ttu-id="051b1-135">No entanto, isso pode causar problemas, por exemplo, se o usuário deixar a empresa sem remover o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="051b1-135">However, this can lead to problems, for example if the user leaves the company without removing the lock.</span></span> <span data-ttu-id="051b1-136">[Ignorar o Bloqueio de Ativação do iOS](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) pode ajudar, removendo o bloqueio de dispositivos iOS supervisionado e permitindo que ele seja realocado ou apagado.</span><span class="sxs-lookup"><span data-stu-id="051b1-136">[iOS Activation Lock bypass](help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune.md) can help by removing the lock from supervised iOS devices allowing you to reallocate, or erase them.</span></span>



## <span data-ttu-id="051b1-137">Proteger computadores Windows gerenciados com o cliente Intune</span><span class="sxs-lookup"><span data-stu-id="051b1-137">Protect Windows PCs managed with the Intune client</span></span>
<a id="protect-windows-pcs-managed-with-the-intune-client" class="xliff"></a>
<span data-ttu-id="051b1-138">O Intune continua a dar suporte às políticas de segurança para computadores Windows que não são registrados, mas que são gerenciados com o software cliente do computador Intune.</span><span class="sxs-lookup"><span data-stu-id="051b1-138">Intune continues to support security policies for Windows PCs that you don't enroll, but manage with the Intune computer client software.</span></span> <span data-ttu-id="051b1-139">Para descobrir como essas políticas podem ajudar a proteger seus computadores Windows, consulte [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md) (Usar políticas para ajudar a proteger os computadores Windows que executam o software cliente do Intune).</span><span class="sxs-lookup"><span data-stu-id="051b1-139">To find out how these policies can help you secure your Windows PCs, see [Use policies to help protect Windows PCs that run the Intune client software](policies-to-protect-windows-pcs-in-microsoft-intune.md).</span></span>
