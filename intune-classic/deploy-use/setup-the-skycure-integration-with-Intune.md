---
title: "Configurar a integração do Skycure com o Intune"
description: "Configure a integração do Skycure com o Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93722f66-7641-4a3f-b1fb-3a0a58a36675
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1d5a59f34a5dacdc2e1a0d5c6601b4ede1a908e4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="34125-103">Configurar a integração do Skycure com o Intune</span><span class="sxs-lookup"><span data-stu-id="34125-103">Set up the Skycure integration with Intune</span></span>
<a id="set-up-the-skycure-integration-with-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="34125-104">Você precisa adicionar os aplicativos Skycure ao Azure AD com a funcionalidade de Logon único.</span><span class="sxs-lookup"><span data-stu-id="34125-104">You need to add Skycure apps into Azure AD to have Single Sign On capabilities.</span></span>

## <span data-ttu-id="34125-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="34125-105">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

### <span data-ttu-id="34125-106">Conta do Azure AD usada para integrar o Intune e o Skycure</span><span class="sxs-lookup"><span data-stu-id="34125-106">Azure AD account used to integrate Intune and Skycure</span></span>
<a id="azure-ad-account-used-to-integrate-intune-and-skycure" class="xliff"></a>

-   <span data-ttu-id="34125-107">Configure corretamente a conta do Azure AD no [Console de Gerenciamento do Skycure](https://aad.skycure.com), antes de começar o processo de configuração do Skycure Basic.</span><span class="sxs-lookup"><span data-stu-id="34125-107">Make sure you have the Azure AD account properly configured in the [Skycure Management console](https://aad.skycure.com), before starting the Skycure Basic setup process.</span></span>

### <span data-ttu-id="34125-108">Integração total versus Somente leitura.</span><span class="sxs-lookup"><span data-stu-id="34125-108">Full integration vs. Read-only</span></span>
<a id="full-integration-vs-read-only" class="xliff"></a>

<span data-ttu-id="34125-109">O Skycure dá suporte a dois modos de integração com o Intune:</span><span class="sxs-lookup"><span data-stu-id="34125-109">Skycure supports two modes of integration with Intune:</span></span>

-   <span data-ttu-id="34125-110">**Integração somente leitura (configuração Básica):** Somente faz o inventário de dispositivos do Azure Active Directory e os preenche no console do Skycure.</span><span class="sxs-lookup"><span data-stu-id="34125-110">**Read-only integration (Basic setup):** Only inventories devices from Azure Active Directory and populates them in the Skycure console.</span></span>
<br>
    -   <span data-ttu-id="34125-111">Se as caixas **Relatar a integridade e o risco de dispositivos ao Intune** e **Relatar também incidentes de segurança ao Intune** não estiverem marcadas no Console de Gerenciamento do Skycure, a integração será somente leitura e, portanto, nunca alterará o estado de um dispositivo (compatível ou incompatível) no Intune.</span><span class="sxs-lookup"><span data-stu-id="34125-111">If the **Report the health and risk of devices to Intune**, and **Also report security incidents to Intune** boxes are not selected in the Skycure Management console, the integration is read-only and therefore will never change a devices state (compliant or non-compliant) in Intune.</span></span>
<br></br>
-   <span data-ttu-id="34125-112">**Integração total:** permite que o Skycure reporte dispositivos com detalhes de incidente de risco e segurança ao Intune, que cria uma comunicação bidirecional entre os dois serviços em nuvem.</span><span class="sxs-lookup"><span data-stu-id="34125-112">**Full integration:** Allows Skycure to report devices on risk and security incident details to Intune, which creates a bi-directional communication between both cloud services.</span></span>

### <span data-ttu-id="34125-113">Como os aplicativos Skycure são usados com o Azure AD e o Intune?</span><span class="sxs-lookup"><span data-stu-id="34125-113">How the Skycure apps are used with Azure AD and Intune?</span></span>
<a id="how-the-skycure-apps-are-used-with-azure-ad-and-intune" class="xliff"></a>

-   <span data-ttu-id="34125-114">**Aplicativo iOS:** permite que os usuários finais entrem no Azure AD usando um aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="34125-114">**iOS app:** Allows end-users to sign in to Azure AD using an iOS app.</span></span>

-   <span data-ttu-id="34125-115">**Aplicativo Android:** permite que os usuários finais entrem no Azure AD usando um aplicativo Android.</span><span class="sxs-lookup"><span data-stu-id="34125-115">**Android app:** Allows end-users to sign in to Azure AD using an Android app.</span></span>

-   <span data-ttu-id="34125-116">**Aplicativo de gerenciamento:** este é o aplicativo multilocatário do Skycure Azure AD que permite a comunicação entre serviços com o Intune.</span><span class="sxs-lookup"><span data-stu-id="34125-116">**Management app:** This is the Skycure Azure AD multi-tenant app which enables service-to-service communication with Intune.</span></span>

## <span data-ttu-id="34125-117">Para configurar a integração somente leitura entre o Intune e o Skycure</span><span class="sxs-lookup"><span data-stu-id="34125-117">To set up the read-only integration between Intune and Skycure</span></span>
<a id="to-set-up-the-read-only-integration-between-intune-and-skycure" class="xliff"></a>

> [!IMPORTANT]
> <span data-ttu-id="34125-118">As credenciais de administrador do Skycure são um email que deve pertencer a um usuário válido no Azure Active Directory, caso contrário, o logon falhará.</span><span class="sxs-lookup"><span data-stu-id="34125-118">The Skycure admin credentials is an e-mail that must belong to a valid user in the Azure Active Directory, otherwise the login will fail.</span></span> <span data-ttu-id="34125-119">O Skycure usa o Azure Active Directory para autenticar seu administrador usando SSO (Logon único).</span><span class="sxs-lookup"><span data-stu-id="34125-119">Skycure uses Azure Active Directory to authenticate its admin using Single Sign On (SSO).</span></span>

1.  <span data-ttu-id="34125-120">Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).</span><span class="sxs-lookup"><span data-stu-id="34125-120">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="34125-121">Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="34125-121">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

3.  <span data-ttu-id="34125-122">Acesse **Configurações**, escolha **Configuração Básica** em **Integração com o Intune**.</span><span class="sxs-lookup"><span data-stu-id="34125-122">Go to **Settings**, choose **Basic Setup** under **Intune Integration**.</span></span>

4.  <span data-ttu-id="34125-123">No rótulo **Aplicativo iOS**, clique em **Adicionar ao Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="34125-123">On the **iOS App** label, click on **Add to Active Directory**.</span></span>

    ![Aplicativo iOS no Console de Gerenciamento do Skycure](../media/mtp/skycure-setup-1.png)

5.  <span data-ttu-id="34125-125">Na página de logon aberta, insira suas credenciais do Intune e clique em **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="34125-125">Login page opens, enter your Intune credentials, then click **Accept**.</span></span>

    ![Aviso de logon do Intune no aplicativo iOS](../media/mtp/skycure-setup-2.png)

6.  <span data-ttu-id="34125-127">Após a adição do aplicativo ao Azure AD, você pode ver uma indicação de que o aplicativo foi adicionado com êxito ao Azure AD no Console de Gerenciamento do Skycure.</span><span class="sxs-lookup"><span data-stu-id="34125-127">Once the app is added into Azure AD, you can see an indication that the app was successfully added into Azure AD on the Skycure Management console.</span></span>

    ![tela de conclusão de aplicativo do iOS](../media/mtp/skycure-setup-3.png)

> [!NOTE]
> <span data-ttu-id="34125-129">Repita o mesmo processo para os aplicativos **Skycure Android** e **Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="34125-129">Repeat the same process for the **Skycure Android** and **Management** apps.</span></span>

### <span data-ttu-id="34125-130">Adicionar um grupo de segurança do Azure AD ao Skycure</span><span class="sxs-lookup"><span data-stu-id="34125-130">Add an Azure AD Security group into Skycure</span></span>
<a id="add-an-azure-ad-security-group-into-skycure" class="xliff"></a>

<span data-ttu-id="34125-131">Você precisa adicionar um grupo de segurança do Azure AD que contém todos os dispositivos que executam o Skycure.</span><span class="sxs-lookup"><span data-stu-id="34125-131">You need to add an Azure AD security group that contains all devices running Skycure.</span></span>

1.  <span data-ttu-id="34125-132">Insira e selecione todos os grupos de segurança de dispositivos que estão executando o Skycure e clique em **Aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="34125-132">Enter and select all the security groups of devices that are running Skycure, then click on **Apply changes**.</span></span>

    ![Configurar o Console de Gerenciamento do Skycure no grupo de segurança](../media/mtp/skycure-setup-4.png)

<span data-ttu-id="34125-134">O Skycure sincroniza os dispositivos que executam seu serviço de Defesa contra Ameaças Móveis com os grupos de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="34125-134">Skycure syncs the devices running its Mobile Threat Defense service with the Azure AD security groups.</span></span>

![Configuração do grupo de segurança concluída no Console de Gerenciamento do Skycure](../media/mtp/skycure-setup-5.png)

## <span data-ttu-id="34125-136">Configurar a integração total entre o Intune e o Skycure</span><span class="sxs-lookup"><span data-stu-id="34125-136">Set up the full integration between Intune and Skycure</span></span>
<a id="set-up-the-full-integration-between-intune-and-skycure" class="xliff"></a>

1.  <span data-ttu-id="34125-137">Acesse o [Console de Gerenciamento do Skycure](https://aad.skycure.com).</span><span class="sxs-lookup"><span data-stu-id="34125-137">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="34125-138">Insira suas **credenciais de administrador do Skycure** e clique em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="34125-138">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

3.  <span data-ttu-id="34125-139">Acesse **Configurações**, escolha **Integração Total** em **Integração com o Intune**.</span><span class="sxs-lookup"><span data-stu-id="34125-139">Go to **Settings**, choose **Full Integration** under **Intune Integration**.</span></span>

4.  <span data-ttu-id="34125-140">Verifique as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="34125-140">Check the following settings:</span></span>

    <span data-ttu-id="34125-141">a.</span><span class="sxs-lookup"><span data-stu-id="34125-141">a.</span></span>  <span data-ttu-id="34125-142">Relatar a integridade e o risco do dispositivo ao Intune</span><span class="sxs-lookup"><span data-stu-id="34125-142">Report the health and risk of device to Intune</span></span>

    <span data-ttu-id="34125-143">b.</span><span class="sxs-lookup"><span data-stu-id="34125-143">b.</span></span>  <span data-ttu-id="34125-144">Relatar também incidentes de segurança ao Intune</span><span class="sxs-lookup"><span data-stu-id="34125-144">Also report security incidents to Intune</span></span>

5.  <span data-ttu-id="34125-145">Clique em **Aplicar Alterações**.</span><span class="sxs-lookup"><span data-stu-id="34125-145">Click on **Apply changes**.</span></span>

    ![Integração completa do Skycure concluída](../media/mtp/skycure-setup-6.png)

## <span data-ttu-id="34125-147">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="34125-147">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="34125-148">Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune</span><span class="sxs-lookup"><span data-stu-id="34125-148">Enable Skycure Mobile Threat Defense in Intune</span></span>](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)
