---
title: "Autenticação multifator para o registro de dispositivo do Intune"
description: "Como exigir a autenticação multifator no Azure AD para registro de dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: 
ms.custom: intune-classic
ms.openlocfilehash: 805ca79932788786636d365109e06aee836d8a0e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2f684-103">Autenticação multifator para registros de dispositivo do Intune</span><span class="sxs-lookup"><span data-stu-id="2f684-103">Multi-factor authentication for Intune device enrollments</span></span>
<a id="multi-factor-authentication-for-intune-device-enrollments" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2f684-104">O Intune integra a MFA (autenticação multifator do Azure AD) para registro de dispositivos para ajudá-lo a proteger seus recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="2f684-104">Intune integrates Azure AD multi-factor authentication (MFA) for device enrollment to help you secure your corporate resources.</span></span>

<span data-ttu-id="2f684-105">A MFA funciona solicitando dois ou mais dos métodos de verificação a seguir:</span><span class="sxs-lookup"><span data-stu-id="2f684-105">MFA works by requiring any two or more of the following verification methods:</span></span> 

- <span data-ttu-id="2f684-106">Algo que você conhece (normalmente uma senha ou PIN).</span><span class="sxs-lookup"><span data-stu-id="2f684-106">Something you know (typically a password or PIN).</span></span>
- <span data-ttu-id="2f684-107">Algo que você tem (um dispositivo de confiança que não é facilmente duplicado, como um telefone).</span><span class="sxs-lookup"><span data-stu-id="2f684-107">Something you have (a trusted device that is not easily duplicated, like a phone).</span></span>
- <span data-ttu-id="2f684-108">Algo que você é (biometria).</span><span class="sxs-lookup"><span data-stu-id="2f684-108">Something you are (biometrics).</span></span>

<span data-ttu-id="2f684-109">MFA tem suporte para dispositivos iOS, Android, Windows 8.1 ou posterior ou Windows Phone 8.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="2f684-109">MFA is supported for iOS, Android, Windows 8.1 or later, or Windows Phone 8.1 or later devices.</span></span>

> [!NOTE]
> <span data-ttu-id="2f684-110">Em versões mais antigas do Configuration Manager (anteriores à versão 1610), você ainda verá a configuração de MFA no console de administração do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="2f684-110">In older versions of Configuration Manager (earlier than release 1610), you will still see the MFA setting in the Configuration Manager admin console.</span></span> <span data-ttu-id="2f684-111">Não tente configurar a MFA no console de administração do Configuration Manager, pois ela não funcionará.</span><span class="sxs-lookup"><span data-stu-id="2f684-111">Do not attempt to configure MFA in the Configuration Manager admin console, as it will not work.</span></span> <span data-ttu-id="2f684-112">Configure a MFA conforme descrito neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2f684-112">Configure MFA as described in this topic.</span></span>

### <span data-ttu-id="2f684-113">Configurar o Intune para exigir a autenticação multifator no registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2f684-113">Configure Intune to require multi-factor authentication at device enrollment</span></span>
<a id="configure-intune-to-require-multi-factor-authentication-at-device-enrollment" class="xliff"></a>
<span data-ttu-id="2f684-114">Para exigir MFA quando um dispositivo é registrado, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="2f684-114">To require MFA when a device is enrolled, follow these steps:</span></span>

1. <span data-ttu-id="2f684-115">Entre no [Portal do Microsoft Azure](https://manage.windowsazure.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="2f684-115">Sign in to your [Microsoft Azure portal](https://manage.windowsazure.com) with your admin credentials.</span></span>
2. <span data-ttu-id="2f684-116">Escolha seu locatário.</span><span class="sxs-lookup"><span data-stu-id="2f684-116">Choose your tenant.</span></span>
2. <span data-ttu-id="2f684-117">Escolha a guia **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2f684-117">Choose the **applications** tab.</span></span> <span data-ttu-id="2f684-118">Você verá uma lista de serviços para os quais pode configurar recursos de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f684-118">You will see a list of services for which you can configure Azure AD security features.</span></span>
3. <span data-ttu-id="2f684-119">Escolha **Registro do Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="2f684-119">Choose **Microsoft Intune enrollment**.</span></span>
4. <span data-ttu-id="2f684-120">Escolha **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2f684-120">Choose **Configure**.</span></span> 
5. <span data-ttu-id="2f684-121">Em **autenticação multifator e regras de acesso com base em localização**, você pode:</span><span class="sxs-lookup"><span data-stu-id="2f684-121">Under **multi-factor authentication and location-based access rules** you can:</span></span>
    
    -  <span data-ttu-id="2f684-122">Habilitar as regras de acesso</span><span class="sxs-lookup"><span data-stu-id="2f684-122">Enable the access rules</span></span>
    -  <span data-ttu-id="2f684-123">Escolher se deseja aplicar as regras a todos os usuários ou a grupos de segurança específicos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2f684-123">Choose whether to apply the rules to all users or to specific Azure AD security groups.</span></span>
    -  <span data-ttu-id="2f684-124">Exigir a autenticação multifator para o registro de todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2f684-124">Require multi-factor authentication for enrollment of all devices.</span></span>
    -  <span data-ttu-id="2f684-125">Exigir a autenticação multifator para o registro quando o dispositivo não estiver no trabalho.</span><span class="sxs-lookup"><span data-stu-id="2f684-125">Require multi-factor authentication for enrollment when the device is not at work.</span></span>
    -  <span data-ttu-id="2f684-126">Escolha **Bloquear o acesso a recursos corporativos** para impedir o registro de um dispositivo quando ele não estiver conectado à rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="2f684-126">Choose **Block access to corporate resources** to prevent enrollment of a device when it is not connected to the corporate network.</span></span> 
4. <span data-ttu-id="2f684-127">Você também pode clicar no link para **definir/editar seu local de rede de trabalho**, a fim de configurar os requisitos de conectividade de rede para o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f684-127">You can also click the link to **define/edit your work network location**, to configure network connectivity requirements for device enrollment.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="2f684-128">Não configure **Regras de acesso com base em dispositivo** para o Registro do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2f684-128">Do not configure **Device based access rules** for Microsoft Intune Enrollment.</span></span>
