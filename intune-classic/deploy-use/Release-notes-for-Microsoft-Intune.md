---
title: "Notas de versão do Microsoft Intune"
description: "Notas de versão do Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: db9479b2-582d-4a1a-9fbc-fbfc6c680e6f
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 751bd0bc90b762c5b51b85fae2129e53773b54fe
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2d39d-103">Notas de versão do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2d39d-103">Release notes for Microsoft Intune</span></span>
<a id="release-notes-for-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2d39d-104">O Microsoft Intune é uma solução integrada de gerenciamento de clientes baseado em nuvem que fornece ferramentas, relatórios e licenças de atualização para a versão mais recente do Windows.</span><span class="sxs-lookup"><span data-stu-id="2d39d-104">Microsoft Intune is an integrated, cloud-based client management solution that provides tools, reports, and upgrade licenses to the latest version of Windows.</span></span> <span data-ttu-id="2d39d-105">Ele também ajuda a manter seus computadores atualizados e protegidos.</span><span class="sxs-lookup"><span data-stu-id="2d39d-105">It also helps keep your computers up-to-date and secure.</span></span> <span data-ttu-id="2d39d-106">Além disso, o Intune permite que você gerencie dispositivos móveis na rede pelo Exchange ActiveSync ou diretamente pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="2d39d-106">In addition, Intune lets you manage mobile devices on the network either through Exchange ActiveSync or directly through Intune.</span></span> <span data-ttu-id="2d39d-107">As notas de versão a seguir descrevem informações importantes e problemas conhecidos no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="2d39d-107">The following release notes describe important information and known issues in Microsoft Intune.</span></span>

<!-- 3-6-17: customer asked if this is still current; Stacie asked Chris Baldwin about it. Chris said it's a Samsung issue, but that he hasn't heard any reports about it for months, so he suggested that I share that with the customer and remove this item from the release notes. I'm only going to comment it out in case it resurfaces.
## Android users can’t send email when conditional access for Exchange Online is implemented

**Issue:** Users running Samsung Android 5.1.1 and later on their devices can't send email when conditional access for Exchange Online has been set up. Samsung acknowledges that the issue is in its built-in email client in Android 5.1.1 and later, and is investigating a fix.

**Workaround 1:** Advise users to use the Outlook app for Android.

**Workaround 2:** To let affected users send email, you can follow these steps:

1. Put each affected user in a security group in the “exempted groups” section of the conditional access policy for Exchange Online.
2. Let the user temporarily sync email on the built-in email client.
3. Remove the affected user from the exempted group, and confirm that the user can now send email.

Microsoft will continue to work closely with Samsung on a fix or additional workarounds.
-->


## <span data-ttu-id="2d39d-108">A alteração de perfis de acesso de recursos entre grupos para iOS e Android pode falhar</span><span class="sxs-lookup"><span data-stu-id="2d39d-108">Changing resource access profiles between groups for iOS and Android might fail</span></span>
<a id="changing-resource-access-profiles-between-groups-for-ios-and-android-might-fail" class="xliff"></a>
<span data-ttu-id="2d39d-109">**Problema:** quando você altera o email ou perfis de acesso de recursos do protocolo SCEP entre os grupos, os perfis podem entrar em conflito e falhar.</span><span class="sxs-lookup"><span data-stu-id="2d39d-109">**Issue:** When you change email or Simple Certificate Enrollment Protocol (SCEP) resource access profiles between groups, the profiles might conflict and fail.</span></span> <span data-ttu-id="2d39d-110">Por exemplo, digamos que você tem um perfil existente que aponta para o servidor Exchange local, direcionado ao Grupo A. Em seguida, você cria um novo perfil de email que aponta para o Exchange Online, direcionado ao Grupo B. Quando você move usuários do Grupo A para o Grupo B, os dispositivos manterão o perfil de email do Exchange local e tentarão instalar o perfil de email do Exchange Online que está direcionado ao Grupo B.</span><span class="sxs-lookup"><span data-stu-id="2d39d-110">For example, let’s say that you have an existing email profile that points to an on-premises Exchange server, targeted to Group A. Then, you create a new email profile that points to Exchange Online, targeted to Group B. When you move users from Group A to Group B, devices will keep the on-premises Exchange email profile and try to install the Exchange Online email profile that is targeted to Group B.</span></span>

<span data-ttu-id="2d39d-111">Neste ponto, ocorre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d39d-111">At this point, one of the following occurs:</span></span> 
* <span data-ttu-id="2d39d-112">Se os perfis de email A e B são idênticos, o dispositivo rejeita o perfil de email B, pois o perfil de email B já contêm o perfil de email A.</span><span class="sxs-lookup"><span data-stu-id="2d39d-112">If email profiles A and B are identical, the device rejects email profile B because email profile B already contains email profile A.</span></span>
* <span data-ttu-id="2d39d-113">Se o perfil de email A for diferente do perfil de email B, conforme mencionado no exemplo, o dispositivo terá dois perfis de email.</span><span class="sxs-lookup"><span data-stu-id="2d39d-113">If email profile A is different from email profile B, as mentioned in the example, the device ends up with two email profiles.</span></span>

> [!NOTE]
> <span data-ttu-id="2d39d-114">O nome do host e o atributo usado para o nome de usuário são verificados para diferenciar um perfil de email do outro.</span><span class="sxs-lookup"><span data-stu-id="2d39d-114">The host name and the attribute used for user name are checked to distinguish one email profile from another.</span></span>

<span data-ttu-id="2d39d-115">Em ambos os casos, o perfil de acesso de recursos (perfil de email) não foi removido do dispositivo para evitar a remoção não intencional do acesso de um usuário ao email ou ao certificado SCEP do cliente.</span><span class="sxs-lookup"><span data-stu-id="2d39d-115">In both cases, the resource access profile (email profile) was not removed from the device in order to prevent the unintentional removal of a user’s access to email or the client's SCEP certificate.</span></span>

<span data-ttu-id="2d39d-116">**Solução alternativa:** nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2d39d-116">**Workaround:** None.</span></span>

## <span data-ttu-id="2d39d-117">Quando você registra um dispositivo Windows 8.1 que deve ser autenticado em um servidor proxy, o processo de registro falha sem motivo aparente</span><span class="sxs-lookup"><span data-stu-id="2d39d-117">When you enroll a Windows 8.1 device that must authenticate to a proxy server, the enrollment process fails with no visible cause</span></span>
<a id="when-you-enroll-a-windows-81-device-that-must-authenticate-to-a-proxy-server-the-enrollment-process-fails-with-no-visible-cause" class="xliff"></a>
<span data-ttu-id="2d39d-118">**Problema:** quando você registra um dispositivo Windows 8.1 e o dispositivo deve ser autenticado em um servidor proxy durante o processo de registro, o registro falha se o dispositivo não tiver credenciais do servidor proxy em cache.</span><span class="sxs-lookup"><span data-stu-id="2d39d-118">**Issue:** When you enroll a Windows 8.1 device and the device must authenticate to a proxy server during the enrollment process, the enrollment fails if the device has not cached the proxy server credentials.</span></span> <span data-ttu-id="2d39d-119">Quando as credenciais do servidor proxy não estão em cache no dispositivo, o processo de registro deve aguardar até que o usuário insira as credenciais.</span><span class="sxs-lookup"><span data-stu-id="2d39d-119">When the credentials for the proxy server are not cached on the device, the enrollment process must wait for the user to enter the credentials.</span></span> <span data-ttu-id="2d39d-120">No entanto, o aviso para fornecer credenciais do servidor proxy não aparece durante o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="2d39d-120">But, the prompt to provide the proxy server credentials does not appear during the enrollment process.</span></span> <span data-ttu-id="2d39d-121">O resultado é que o processo de registro não pode autenticar o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="2d39d-121">The result is that the enrollment process cannot authenticate to the proxy server.</span></span> <span data-ttu-id="2d39d-122">Nenhum motivo aparente para essa falha é apresentado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="2d39d-122">No visible indication of this failure is presented to the user.</span></span>

<span data-ttu-id="2d39d-123">**Solução alternativa:** para dispositivos Windows 8.1 que devem ser registrados em uma rede que requer o uso de um servidor proxy autenticado, configure e salve as credenciais do servidor proxy antes de registrar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d39d-123">**Workaround:** For Windows 8.1 devices that must enroll on a network that requires use of an authenticated proxy server, set up and save the credentials for the proxy server prior to enrollment of the device.</span></span> <span data-ttu-id="2d39d-124">Para configurar e salvar as credenciais em um dispositivo Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="2d39d-124">To set up and save the credentials on a Windows 8.1 device:</span></span>

1.  <span data-ttu-id="2d39d-125">No dispositivo Windows 8.1, abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2d39d-125">On the Windows 8.1 device, open Internet Explorer.</span></span>
2.  <span data-ttu-id="2d39d-126">Quando as credenciais do servidor proxy forem solicitadas, insira-as e então selecione a opção **Lembrar minhas credenciais**.</span><span class="sxs-lookup"><span data-stu-id="2d39d-126">When you're prompted for the proxy server credentials, enter the credentials and then choose the option **Remember my credentials**.</span></span>
3.  <span data-ttu-id="2d39d-127">Registre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2d39d-127">Enroll the device.</span></span>

## <span data-ttu-id="2d39d-128">Os dispositivos Windows Phone 8.1 não conseguem se registrar no Microsoft Intune quando a autenticação do dispositivo está habilitada no AD FS</span><span class="sxs-lookup"><span data-stu-id="2d39d-128">Windows Phone 8.1 devices fail to enroll with Microsoft Intune when device authentication is enabled in AD FS</span></span>
<a id="windows-phone-81-devices-fail-to-enroll-with-microsoft-intune-when-device-authentication-is-enabled-in-ad-fs" class="xliff"></a>
<span data-ttu-id="2d39d-129">**Problema:** quando você registra um dispositivo Windows Phone 8.1, o registro falha se a configuração opcional para a autenticação do dispositivo estiver habilitada como parte da política de autenticação global nos Serviços de Federação do Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="2d39d-129">**Issue:** When you enroll a Windows Phone 8.1 device, enrollment fails if the optional setting for device authentication is enabled as part of the global authentication policy in Active Directory Federation Services (AD FS).</span></span>

<span data-ttu-id="2d39d-130">**Solução alternativa**: desabilite a autenticação de dispositivos no servidor do AD FS desmarcando **Habilitar a autenticação de dispositivo** em **Editar política de autenticação global**.</span><span class="sxs-lookup"><span data-stu-id="2d39d-130">**Workaround:** Disable device authentication on the AD FS server by unchecking **Enable device authentication** in **Edit Global Authentication Policy**.</span></span> <span data-ttu-id="2d39d-131">Para obter mais informações, consulte [Configurando Políticas de Autenticação](http://technet.microsoft.com/library/dn486781.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d39d-131">For more information, see [Configuring Authentication Policies](http://technet.microsoft.com/library/dn486781.aspx).</span></span>


## <span data-ttu-id="2d39d-132">A Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para Android não tem nenhum recurso interno de desinstalação</span><span class="sxs-lookup"><span data-stu-id="2d39d-132">Microsoft Intune App Wrapping Tool for Android has no built-in uninstall capability</span></span>
<a id="microsoft-intune-app-wrapping-tool-for-android-has-no-built-in-uninstall-capability" class="xliff"></a>
<span data-ttu-id="2d39d-133">**Problema:** a **Ferramenta de Encapsulamento de Aplicativos do Microsoft Intune para Android** não tem uma funcionalidade interna de desinstalação da ferramenta.</span><span class="sxs-lookup"><span data-stu-id="2d39d-133">**Issue:** The **Microsoft App Wrapping Tool for Android** does not have built-in functionality for uninstalling the tool.</span></span>

<span data-ttu-id="2d39d-134">**Solução alternativa:** navegue até o local em que você instalou a ferramenta e exclua o diretório.</span><span class="sxs-lookup"><span data-stu-id="2d39d-134">**Workaround:** Browse to the location where you installed the tool, and delete the directory.</span></span> <span data-ttu-id="2d39d-135">O local de instalação padrão é: **C:\Program Files\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span><span class="sxs-lookup"><span data-stu-id="2d39d-135">The default installation location is: **C:\Program Files\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span></span> <span data-ttu-id="2d39d-136">Para saber mais sobre a ferramenta de encapsulamento de aplicativos, consulte [Preparar aplicativos Android para o gerenciamento com a Ferramenta de Encapsulamento de Aplicativos](/intune/app-wrapper-prepare-android).</span><span class="sxs-lookup"><span data-stu-id="2d39d-136">For more about the app wrapping tool, see [Prepare Android apps for management with App Wrapping Tool](/intune/app-wrapper-prepare-android).</span></span>

## <span data-ttu-id="2d39d-137">A assistência remota não está disponível em computadores que executam o Windows 8 ou o Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="2d39d-137">Remote assistance is not available on computers that run Windows 8 or Windows 8.1</span></span>
<a id="remote-assistance-is-not-available-on-computers-that-run-windows-8-or-windows-81" class="xliff"></a>
<span data-ttu-id="2d39d-138">**Problema:** nessa versão, o recurso de assistência remota não está disponível em computadores que executam Windows 8 ou Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="2d39d-138">**Issue:** In this release, the remote assistance feature is not available on computers that run Windows 8 or Windows 8.1.</span></span>

<span data-ttu-id="2d39d-139">**Solução alternativa:** nenhuma.</span><span class="sxs-lookup"><span data-stu-id="2d39d-139">**Workaround:** None.</span></span>

## <span data-ttu-id="2d39d-140">Notificações de alerta para os destinatários adicionados manualmente podem não funcionar</span><span class="sxs-lookup"><span data-stu-id="2d39d-140">Alert notifications for recipients that are automatically added might not work</span></span>
<a id="alert-notifications-for-recipients-that-are-automatically-added-might-not-work" class="xliff"></a>
<span data-ttu-id="2d39d-141">**Problema:** se os destinatários forem adicionados automaticamente a uma notificação de alerta, nem sempre eles poderão receber uma notificação.</span><span class="sxs-lookup"><span data-stu-id="2d39d-141">**Issue:** If recipients are automatically added to an alert notification, they might not always receive a notification.</span></span>

<span data-ttu-id="2d39d-142">**Solução alternativa:** para assegurar que os destinatários recebam as notificações de mensagem, você deve adicioná-los manualmente às notificações de alerta.</span><span class="sxs-lookup"><span data-stu-id="2d39d-142">**Workaround:** To make sure that recipients will receive message notifications, you should manually add recipients to alert notifications.</span></span>

## <span data-ttu-id="2d39d-143">Suporte a idiomas no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="2d39d-143">Language support in the Azure portal</span></span>
<a id="language-support-in-the-azure-portal" class="xliff"></a>
<span data-ttu-id="2d39d-144">O Portal do Azure têm suporte nos seguintes idiomas: chinês (simplificado), chinês (tradicional), tcheco, holandês, inglês, alemão, húngaro, italiano, japonês, português (Brasil), português (Portugal), russo, espanhol, inglês, francês, coreano, polonês, sueco e turco.</span><span class="sxs-lookup"><span data-stu-id="2d39d-144">The Azure portal supports these languages: Chinese (Simplified), Chinese (Traditional), Czech, Dutch, English, German, Hungarian, Italian, Japanese, Portuguese (Brazil), Portuguese (Portugal), Russian, Spanish, English, French, Korean, Polish, Swedish, Turkish.</span></span>

<span data-ttu-id="2d39d-145">O Console de Administração do Intune e as experiências móveis do usuário têm suporte nos idiomas dinamarquês, grego, finlandês, norueguês e romeno, além de todos os idiomas com suporte no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="2d39d-145">The Intune Admin Console and the user-facing mobile experiences support Danish, Greek, Finnish, Norwegian, and Romanian, in addition to all the languages that the Azure portal supports.</span></span>
