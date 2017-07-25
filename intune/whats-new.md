---
<<<<<<< HEAD
title: <span data-ttu-id="f51ab-101">Novidades do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f51ab-101">What's new in Microsoft Intune</span></span>
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"f51ab-102\">Conheça as novidades do portal do Intune no Azure</span><span class=\"sxs-lookup\"><span data-stu-id=\"f51ab-102\">Find out what's new in the Intune Azure portal</span></span>"
=======
title: Novidades do Microsoft Intune
titleSuffix: Intune on Azure
description: "Conheça as novidades do portal do Intune no Azure"
>>>>>>> live
keywords: 
author: brenduns
ms.author: brenduns
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dec4fb1d373f49c1f6c15b1f2a9acb2f8d20138d
ms.sourcegitcommit: be12974a7eaa4ce9cffe45aabe456c858d582e20
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2017
---
<<<<<<< HEAD
# <a name="whats-new-in-microsoft-intune"></a><span data-ttu-id="f51ab-103">Novidades do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f51ab-103">What's new in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f51ab-104">Conheça as novidades de cada semana do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-104">Learn what’s new each week in Microsoft Intune.</span></span> <span data-ttu-id="f51ab-105">Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-105">You can also find out about [upcoming changes](#whats-coming), [important notices](#notices) about the service, and information about [past releases](whats-new-archive.md).</span></span>

> [!Note]
> <span data-ttu-id="f51ab-106">Muitos desses recursos acabarão tendo suporte em implantações híbridas com o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="f51ab-106">Many of these features will eventually be supported for hybrid deployments with Configuration Manager.</span></span> <span data-ttu-id="f51ab-107">Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).</span><span class="sxs-lookup"><span data-stu-id="f51ab-107">For more information about new hybrid features, check out our [hybrid What’s New page](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).</span></span>
=======
# <a name="whats-new-in-microsoft-intune"></a>Novidades do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Conheça as novidades de cada semana do Microsoft Intune. Saiba mais também sobre [as próximas alterações](#whats-coming), [avisos importantes](#notices) sobre o serviço e informações sobre [versões anteriores](whats-new-archive.md).

> [!Note]
> Muitos desses recursos acabarão tendo suporte em implantações híbridas com o Configuration Manager. Para obter mais informações sobre os novos recursos híbridos, confira a [página Hybrid What’s New](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management) (Novidades do Híbrido).
>>>>>>> live


<!-- Common categories:  
  ### Role-based access control
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
-->   



<<<<<<< HEAD
## <a name="week-of-june-26th-2017"></a><span data-ttu-id="f51ab-108">Semana de 26 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="f51ab-108">Week of June 26th, 2017</span></span>

### <a name="role-based-access-control"></a><span data-ttu-id="f51ab-109">Controle de acesso baseado em função</span><span class="sxs-lookup"><span data-stu-id="f51ab-109">Role-based access control</span></span>
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a><span data-ttu-id="f51ab-110">Novo acesso de administração baseada em funções para administradores do Intune   <!-- 1099990 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-110">New role-based administration access for Intune admins   <!-- 1099990 --></span></span>  
<span data-ttu-id="f51ab-111">Uma nova função de administrador de acesso condicional está sendo adicionada para exibir, criar, modificar e excluir políticas de Acesso Condicional do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f51ab-111">A new conditional access admin role is being added to view, create, modify, and delete Azure AD Conditional Access policies.</span></span> <span data-ttu-id="f51ab-112">Anteriormente, somente os administradores globais e os administradores de segurança tinham essa permissão.</span><span class="sxs-lookup"><span data-stu-id="f51ab-112">Previously, only global admins and security admins had this permission.</span></span> <span data-ttu-id="f51ab-113">Os administradores do Intune podem receber essa permissão de função para ter acesso às políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="f51ab-113">Intune admins can be granted with this role permission so that they have access to conditional access policies.</span></span>


### <a name="device-enrollment"></a><span data-ttu-id="f51ab-114">Registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f51ab-114">Device enrollment</span></span>
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a><span data-ttu-id="f51ab-115">Marcar dispositivos de propriedade corporativa com o número de série <!-- 1215070 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-115">Tag corporate-owned devices with serial number <!-- 1215070 --></span></span>  
<span data-ttu-id="f51ab-116">O Intune agora dá suporte ao upload dos números de série de iOS, macOS e Android como Identificadores de Dispositivo Corporativo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-116">Intune now supports uploading iOS, macOS, and Android serial numbers as Corporate Device Identifiers.</span></span> <span data-ttu-id="f51ab-117">No momento, não é possível usar números de série para bloquear o registro de dispositivos pessoais, pois os números de série não são verificados durante o registro.</span><span class="sxs-lookup"><span data-stu-id="f51ab-117">You can't use serial numbers to block personal devices from enrolling at this time because serial numbers are not verified during enrollment.</span></span> <span data-ttu-id="f51ab-118">O bloqueio de dispositivos pessoais pelo número de série será liberado em breve.</span><span class="sxs-lookup"><span data-stu-id="f51ab-118">Blocking personal devices by serial number will be released in the near future.</span></span>


### <a name="device-management"></a><span data-ttu-id="f51ab-119">Gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f51ab-119">Device management</span></span>
#### <a name="new-remote-actions-for-ios-devices----854689---"></a><span data-ttu-id="f51ab-120">Novas ações remotas para dispositivos iOS <!-- 854689 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-120">New remote actions for iOS devices <!-- 854689 --></span></span>
<span data-ttu-id="f51ab-121">Neste lançamento, adicionamos duas novas ações remotas para dispositivos iPad compartilhados, que gerenciam o aplicativo Classroom da Apple:</span><span class="sxs-lookup"><span data-stu-id="f51ab-121">In this release, we've added two new remote device actions for shared iPad devices that manage the Apple Classroom app:</span></span>

-   <span data-ttu-id="f51ab-122">[Fazer logoff do usuário atual](device-logout-user.md) – Faz logoff do usuário atual de um dispositivo iOS escolhido.</span><span class="sxs-lookup"><span data-stu-id="f51ab-122">[Logout current user](device-logout-user.md) - Logs out the current user of an iOS device you choose.</span></span>
-   <span data-ttu-id="f51ab-123">[Remover usuário](device-remove-user.md) – Exclui um usuário escolhido do cache local de um dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-123">[Remove user](device-remove-user.md) - Deletes a user you choose from the local cache on an iOS device.</span></span>


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a><span data-ttu-id="f51ab-124">Suporte para iPads compartilhados com o aplicativo Sala de aula do iOS <!-- 1044681 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-124">Support for shared iPads with the iOS Classroom app <!-- 1044681 --></span></span>
<span data-ttu-id="f51ab-125">Nessa versão, expandimos o suporte do gerenciamento do aplicativo Classroom iOS para incluir os alunos que fazem logon em iPads compartilhados usando suas IDs da Apple gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="f51ab-125">In this release, we've expanded the support for managing the iOS Classroom app to include students who log into shared iPads using their managed Apple ID.</span></span>


### <a name="app-management"></a><span data-ttu-id="f51ab-126">Gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f51ab-126">App management</span></span>  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a><span data-ttu-id="f51ab-127">Alterações para aplicativos internos do Microsoft Intune <!-- 1332306 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-127">Changes to Intune built-in apps <!-- 1332306 --></span></span>

<span data-ttu-id="f51ab-128">Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente.</span><span class="sxs-lookup"><span data-stu-id="f51ab-128">Previously, Intune contained a number of built-in apps that you could quickly assign.</span></span> <span data-ttu-id="f51ab-129">Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.</span><span class="sxs-lookup"><span data-stu-id="f51ab-129">Based on your feedback, we have removed this list, and you will no longer see built-in apps.</span></span>
<span data-ttu-id="f51ab-130">No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f51ab-130">However, if you have already assigned any built-in apps, these will still be visible in the list of apps.</span></span> <span data-ttu-id="f51ab-131">Você pode continuar a atribuir esses aplicativos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f51ab-131">You can continue to assign these apps as required.</span></span>
<span data-ttu-id="f51ab-132">Planejamos adicionar um método mais fácil para selecionar e atribuir aplicativos internos no portal Microsoft Intune, em um lançamento posterior.</span><span class="sxs-lookup"><span data-stu-id="f51ab-132">In a later release, we plan to add an easier method to select and assign built-in apps from the Intune portal.</span></span>


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a><span data-ttu-id="f51ab-133">Suporte para aplicativos offline da Windows Store para Empresas <!--- 777044 ---></span><span class="sxs-lookup"><span data-stu-id="f51ab-133">Support for offline apps from the Windows Store for Business <!--- 777044 ---></span></span>
<span data-ttu-id="f51ab-134">Aplicativos offline comprados na Windows Store para Empresas agora serão sincronizados com o Portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-134">Offline apps you purchased from the Windows Store for Business will now be synchronized to the Intune portal.</span></span> <span data-ttu-id="f51ab-135">Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários.</span><span class="sxs-lookup"><span data-stu-id="f51ab-135">You can then deploy these apps to device groups, or user groups.</span></span> <span data-ttu-id="f51ab-136">Os aplicativos offline são instalados pelo Intune e não pela loja.</span><span class="sxs-lookup"><span data-stu-id="f51ab-136">Offline apps are installed by Intune, and not by the store.</span></span>

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a><span data-ttu-id="f51ab-137">O Microsoft Teams agora faz parte da lista de AC baseada em aplicativos de aplicativos aprovados   <!-- 1257019 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-137">Microsoft teams is now part of the App-based CA list of approved apps   <!-- 1257019 --></span></span>

<span data-ttu-id="f51ab-138">O aplicativo Microsoft Teams para iOS e Android fará parte dos aplicativos aprovados para as políticas de acesso condicional baseado em aplicativos do Exchange e do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f51ab-138">The Microsoft Teams app for iOS and Android is now part of approved apps for app-based conditional access policies for Exchange and SharePoint Online.</span></span> <span data-ttu-id="f51ab-139">O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários que usam o acesso condicional baseado em aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f51ab-139">The app can be configured through the Intune App Protection blade in the Azure portal to all tenants currently using app-based conditional access.</span></span>

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a><span data-ttu-id="f51ab-140">Navegador gerenciado e integração de proxy de aplicativo <!-- 1287310 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-140">Managed browser and app proxy integration <!-- 1287310 --></span></span>
 <span data-ttu-id="f51ab-141">O Navegador Gerenciado do Intune agora pode ser integrado ao serviço de Proxy de aplicativo do Azure AD para permitir que os usuários acessem os sites da Web internos, mesmo quando estão trabalhando remotamente.</span><span class="sxs-lookup"><span data-stu-id="f51ab-141">The Intune Managed Browser can now integrate with the Azure AD Application Proxy service to let users access internal web sites even when they are working remotely.</span></span> <span data-ttu-id="f51ab-142">Usuários do navegador simplesmente digitam a URL do site como normalmente fariam e o Managed Browser roteia a solicitação através do gateway de Web do proxy de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-142">Users of the browser simply enter the site URL as they normally would and the Managed Browser routes the request through the application proxy web gateway.</span></span> <span data-ttu-id="f51ab-143">Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-143">For more information, see [Manage Internet access using Managed browser policies](app-configuration-managed-browser.md).</span></span>


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a><span data-ttu-id="f51ab-144">Novas definições de configuração de aplicativo para o Intune Managed Browser <!-- 682951 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-144">New app configuration settings for the Intune Managed Browser <!-- 682951 --></span></span>
<span data-ttu-id="f51ab-145">Nesta versão, adicionamos configurações adicionais para o aplicativo Intune Managed Browser para iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="f51ab-145">In this release, we've added further configurations for the Intune Managed Browser app for iOS and Android.</span></span> <span data-ttu-id="f51ab-146">Agora você pode usar uma política de configuração de aplicativo para configurar a página inicial padrão e os indicadores do navegador.</span><span class="sxs-lookup"><span data-stu-id="f51ab-146">You can now use an app configuration policy to configure the default home page and bookmarks for the browser.</span></span>
<span data-ttu-id="f51ab-147">Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md)</span><span class="sxs-lookup"><span data-stu-id="f51ab-147">For more information, see [Manage Internet access using Managed browser policies](app-configuration-managed-browser.md)</span></span>
=======
## <a name="week-of-june-26th-2017"></a>Semana de 26 de junho de 2017

### <a name="role-based-access-control"></a>Controle de acesso baseado em função
#### <a name="new-role-based-administration-access-for-intune-admins------1099990---"></a>Novo acesso de administração baseada em funções para administradores do Intune   <!-- 1099990 -->  
Uma nova função de administrador de acesso condicional está sendo adicionada para exibir, criar, modificar e excluir políticas de Acesso Condicional do Azure AD. Anteriormente, somente os administradores globais e os administradores de segurança tinham essa permissão. Os administradores do Intune podem receber essa permissão de função para ter acesso às políticas de acesso condicional.


### <a name="device-enrollment"></a>Registro de dispositivo
#### <a name="tag-corporate-owned-devices-with-serial-number----1215070---"></a>Marcar dispositivos de propriedade corporativa com o número de série <!-- 1215070 -->  
O Intune agora dá suporte ao upload dos números de série de iOS, macOS e Android como Identificadores de Dispositivo Corporativo. No momento, não é possível usar números de série para bloquear o registro de dispositivos pessoais, pois os números de série não são verificados durante o registro. O bloqueio de dispositivos pessoais pelo número de série será liberado em breve.


### <a name="device-management"></a>Gerenciamento de dispositivos
#### <a name="new-remote-actions-for-ios-devices----854689---"></a>Novas ações remotas para dispositivos iOS <!-- 854689 -->
Neste lançamento, adicionamos duas novas ações remotas para dispositivos iPad compartilhados, que gerenciam o aplicativo Classroom da Apple:

-   [Fazer logoff do usuário atual](device-logout-user.md) – Faz logoff do usuário atual de um dispositivo iOS escolhido.
-   [Remover usuário](device-remove-user.md) – Exclui um usuário escolhido do cache local de um dispositivo iOS.


#### <a name="support-for-shared-ipads-with-the-ios-classroom-app----1044681---"></a>Suporte para iPads compartilhados com o aplicativo Sala de aula do iOS <!-- 1044681 -->
Nessa versão, expandimos o suporte do gerenciamento do aplicativo Classroom iOS para incluir os alunos que fazem logon em iPads compartilhados usando suas IDs da Apple gerenciadas.


### <a name="app-management"></a>Gerenciamento de aplicativos  

#### <a name="changes-to-intune-built-in-apps----1332306---"></a>Alterações para aplicativos internos do Microsoft Intune <!-- 1332306 -->

Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.
No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos. Você pode continuar a atribuir esses aplicativos conforme necessário.
Planejamos adicionar um método mais fácil para selecionar e atribuir aplicativos internos no portal Microsoft Intune, em um lançamento posterior.


#### <a name="support-for-offline-apps-from-the-windows-store-for-business-----777044----"></a>Suporte para aplicativos offline da Windows Store para Empresas <!--- 777044 --->
Aplicativos offline comprados na Windows Store para Empresas agora serão sincronizados com o Portal do Intune. Você poderá implantar esses aplicativos em grupos de dispositivos ou de usuários. Os aplicativos offline são instalados pelo Intune e não pela loja.

#### <a name="microsoft-teams-is-now-part-of-the-app-based-ca-list-of-approved-apps------1257019---"></a>O Microsoft Teams agora faz parte da lista de AC baseada em aplicativos de aplicativos aprovados   <!-- 1257019 -->

O aplicativo Microsoft Teams para iOS e Android fará parte dos aplicativos aprovados para as políticas de acesso condicional baseado em aplicativos do Exchange e do SharePoint Online. O aplicativo pode ser configurado por meio da folha Proteção de Aplicativo do Intune no Portal do Azure para todos os locatários que usam o acesso condicional baseado em aplicativos.

#### <a name="managed-browser-and-app-proxy-integration----1287310---"></a>Navegador gerenciado e integração de proxy de aplicativo <!-- 1287310 -->
 O Navegador Gerenciado do Intune agora pode ser integrado ao serviço de Proxy de aplicativo do Azure AD para permitir que os usuários acessem os sites da Web internos, mesmo quando estão trabalhando remotamente. Usuários do navegador simplesmente digitam a URL do site como normalmente fariam e o Managed Browser roteia a solicitação através do gateway de Web do proxy de aplicativo. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md).


#### <a name="new-app-configuration-settings-for-the-intune-managed-browser----682951---"></a>Novas definições de configuração de aplicativo para o Intune Managed Browser <!-- 682951 -->
Nesta versão, adicionamos configurações adicionais para o aplicativo Intune Managed Browser para iOS e Android. Agora você pode usar uma política de configuração de aplicativo para configurar a página inicial padrão e os indicadores do navegador.
Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser](app-configuration-managed-browser.md)
>>>>>>> live




<<<<<<< HEAD
### <a name="device-configuration"></a><span data-ttu-id="f51ab-148">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f51ab-148">Device configuration</span></span>  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a><span data-ttu-id="f51ab-149">Configurações do BitLocker para Windows 10  <!-- 951707 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-149">BitLocker settings for Windows 10  <!-- 951707 --></span></span>
<span data-ttu-id="f51ab-150">Agora você pode definir as configurações do BitLocker para dispositivos Windows 10 usando um novo perfil de dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-150">You can now configure BitLocker settings for Windows 10 devices using a new Intune device profile.</span></span> <span data-ttu-id="f51ab-151">Por exemplo, você pode exigir que os dispositivos sejam criptografados e também definir outras configurações que são aplicadas quando o BitLocker é ativado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-151">For example, you can require that devices are encrypted, and also configure further settings that are applied when BitLocker is turned on.</span></span>
<span data-ttu-id="f51ab-152">Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-152">For more information, see [Endpoint protection settings for Windows 10 and later](endpoint-protection-windows-10.md).</span></span>

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a><span data-ttu-id="f51ab-153">Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  ---></span><span class="sxs-lookup"><span data-stu-id="f51ab-153">New settings for Windows 10 device restriction profile <!--- 978527,  978550, 978569, 1050031, 1058611,  ---></span></span>

<span data-ttu-id="f51ab-154">Nesta versão, adicionamos novas configurações para o perfil de restrição de dispositivo do Windows 10 nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="f51ab-154">In this release, we've added new settings for the Windows 10 device restriction profile, in the following categories:</span></span>

 -  <span data-ttu-id="f51ab-155">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="f51ab-155">Windows Defender</span></span>
-  <span data-ttu-id="f51ab-156">Celular e conectividade</span><span class="sxs-lookup"><span data-stu-id="f51ab-156">Cellular and connectivity</span></span>
-  <span data-ttu-id="f51ab-157">Experiência na tela bloqueada</span><span class="sxs-lookup"><span data-stu-id="f51ab-157">Locked screen experience</span></span>
-  <span data-ttu-id="f51ab-158">Privacidade</span><span class="sxs-lookup"><span data-stu-id="f51ab-158">Privacy</span></span>
-  <span data-ttu-id="f51ab-159">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="f51ab-159">Search</span></span>
-  <span data-ttu-id="f51ab-160">Destaque do Windows</span><span class="sxs-lookup"><span data-stu-id="f51ab-160">Windows Spotlight</span></span>
-  <span data-ttu-id="f51ab-161">Navegador de borda</span><span class="sxs-lookup"><span data-stu-id="f51ab-161">Edge browser</span></span>

<span data-ttu-id="f51ab-162">Para obter mais informações sobre as configurações do Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](device-restrictions-windows-10.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-162">For more information about Windows 10 settings, see [Windows 10 and later device restriction settings](device-restrictions-windows-10.md).</span></span>

## <a name="week-of-june-12-2017"></a><span data-ttu-id="f51ab-163">Semana de 12 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="f51ab-163">Week of June 12, 2017</span></span>

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a><span data-ttu-id="f51ab-164">O aplicativo de Portal da Empresa para Android agora tem uma nova experiência do usuário final para as Políticas de Proteção do Aplicativo <!--1305217--></span><span class="sxs-lookup"><span data-stu-id="f51ab-164">Company Portal app for Android now has a new end user experience for App Protection Policies <!--1305217--></span></span>
<span data-ttu-id="f51ab-165">Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="f51ab-165">Based on customer feedback, we've modified the Company Portal app for Android to show an **Access Company Content** button.</span></span> <span data-ttu-id="f51ab-166">A intenção é impedir que os usuários finais passem pelo processo de registro desnecessariamente quando eles só precisam acessar os aplicativos que dão suporte às Políticas de Proteção de Aplicativo, um recurso de gerenciamento de aplicativos móveis do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-166">The intent is to prevent end users from unnecessarily going through the enrollment process when they only need to access apps that support App Protection Policies, a feature of Intune mobile application management.</span></span> <span data-ttu-id="f51ab-167">Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-167">You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page.</span></span>

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a><span data-ttu-id="f51ab-168">Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569--></span><span class="sxs-lookup"><span data-stu-id="f51ab-168">New menu action to easily remove Company Portal <!--1164569--></span></span>
<span data-ttu-id="f51ab-169">De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-169">Based on user feedback, the Company Portal app for Android has added a new menu action to initiate the removal of Company Portal from your device.</span></span> <span data-ttu-id="f51ab-170">Essa ação remove o dispositivo do gerenciamento do Intune, de forma que o aplicativo possa ser removido do dispositivo pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="f51ab-170">This action removes the device from Intune management so that the app can be removed from the device by the user.</span></span> <span data-ttu-id="f51ab-171">Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) e na [documentação do usuário final do Android](/intune-user-help/unenroll-your-device-from-intune-android).</span><span class="sxs-lookup"><span data-stu-id="f51ab-171">You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page and in the [Android end user documentation](/intune-user-help/unenroll-your-device-from-intune-android).</span></span>

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a><span data-ttu-id="f51ab-172">Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505--></span><span class="sxs-lookup"><span data-stu-id="f51ab-172">Improvements to app syncing with Windows 10 Creators Update <!--676505--></span></span>

<span data-ttu-id="f51ab-173">O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703).</span><span class="sxs-lookup"><span data-stu-id="f51ab-173">The Company Portal app for Windows 10 will now automatically initiate a sync for app install requests for devices with Windows 10 Creators Update (version 1703).</span></span> <span data-ttu-id="f51ab-174">Isso reduzirá o problema de paralisação de instalações de aplicativo durante o estado de "Sincronização pendente".</span><span class="sxs-lookup"><span data-stu-id="f51ab-174">This will reduce the issue of app installs stalling during the "Pending Sync" state.</span></span> <span data-ttu-id="f51ab-175">Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-175">In addition, users will be able to manually initiate a sync from within the app.</span></span> <span data-ttu-id="f51ab-176">Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-176">You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page.</span></span>

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a><span data-ttu-id="f51ab-177">Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938---></span><span class="sxs-lookup"><span data-stu-id="f51ab-177">New guided experience for Windows 10 Company Portal <!---1058938---></span></span>

<span data-ttu-id="f51ab-178">O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados.</span><span class="sxs-lookup"><span data-stu-id="f51ab-178">The Company Portal app for Windows 10 will include a guided Intune walkthrough experience for devices that have not been identified or enrolled.</span></span> <span data-ttu-id="f51ab-179">A nova experiência fornece instruções passo a passo que guiam o usuário pelo registro no Azure Active Directory (necessário para os recursos do Acesso Condicional) e pelo registro do MDM (necessário para os recursos de gerenciamento de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="f51ab-179">The new experience provides step-by-step instructions that guide the user through registering into Azure Active Directory (required for Conditional Access features) and MDM enrollment (required for device management features).</span></span> <span data-ttu-id="f51ab-180">A experiência guiada estará acessível na home page do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-180">The guided experience will be accessible from the Company Portal home page.</span></span> <span data-ttu-id="f51ab-181">Os usuários poderão continuar usando o aplicativo se não concluírem o registro, mas terão funcionalidade limitada.</span><span class="sxs-lookup"><span data-stu-id="f51ab-181">Users can continue to use the app if they do not complete registration and enrollment, but will experience limited functionality.</span></span>

<span data-ttu-id="f51ab-182">Esta atualização só é visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior.</span><span class="sxs-lookup"><span data-stu-id="f51ab-182">This update is only visible on devices running Windows 10 Anniversary Update (build 1607) or higher.</span></span> <span data-ttu-id="f51ab-183">Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-183">You can see these changes on the [what's new in app UI](whats-new-app-ui.md) page.</span></span>

## <a name="week-of-june-5-2017"></a><span data-ttu-id="f51ab-184">Semana de 5 de junho de 2017</span><span class="sxs-lookup"><span data-stu-id="f51ab-184">Week of June 5, 2017</span></span>

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a><span data-ttu-id="f51ab-185">Os consoles de administrador do Microsoft Intune e do Acesso Condicional estão disponíveis</span><span class="sxs-lookup"><span data-stu-id="f51ab-185">Microsoft Intune and Conditional Access admin consoles are generally available</span></span>

<span data-ttu-id="f51ab-186">Anunciamos a disponibilidade geral dos novos consoles de administrador do Intune no Azure e do Acesso Condicional.</span><span class="sxs-lookup"><span data-stu-id="f51ab-186">We’re announcing the general availability of both the new Intune on Azure admin console and the Conditional Access admin console.</span></span> <span data-ttu-id="f51ab-187">Por meio do Intune no Azure, agora você pode gerenciar todas as funcionalidades MAM e MDM do Intune em uma única experiência de administrador consolidada e aproveitar o agrupamento e direcionamento do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f51ab-187">Through Intune on Azure, you can now manage all Intune MAM and MDM capabilities in one consolidated admin experience, and leverage Azure AD grouping and targeting.</span></span> <span data-ttu-id="f51ab-188">O acesso condicional no Azure reúne funcionalidades avançadas no Azure AD e no Intune em um único console unificado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-188">Conditional access in Azure brings rich capabilities across Azure AD and Intune together in one unified console.</span></span> <span data-ttu-id="f51ab-189">Além disso, de uma experiência administrativa, a migração para a plataforma Azure permite o uso de navegadores modernos.</span><span class="sxs-lookup"><span data-stu-id="f51ab-189">And from an administrative experience, moving to the Azure platform allows you to use modern browsers.</span></span>

<span data-ttu-id="f51ab-190">O Intune agora está visível sem o rótulo **versão prévia** no console do Azure em portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="f51ab-190">Intune is now visible without the **preview** label in the Azure console at portal.azure.com.</span></span>

<span data-ttu-id="f51ab-191">No momento, nenhuma ação é necessária para os clientes existentes, a menos que você tenha recebido uma de uma série de mensagens no centro de mensagens solicitando uma ação de sua parte para que possamos migrar seus grupos.</span><span class="sxs-lookup"><span data-stu-id="f51ab-191">There is no action required for existing customers at this time, unless you have received one of a series of messages in the message center requesting that you take action so that we can migrate your groups.</span></span> <span data-ttu-id="f51ab-192">Talvez você também tenha recebido um aviso do centro de mensagens informando que a migração está levando mais tempo devido a bugs no nosso lado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-192">You may have also received a message center notice informing you that migration is taking longer due to bugs on our side.</span></span> <span data-ttu-id="f51ab-193">Continuaremos trabalhando incessantemente para migrar os clientes afetados.</span><span class="sxs-lookup"><span data-stu-id="f51ab-193">We are diligently continuing work to migrate any impacted customer.</span></span>

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a><span data-ttu-id="f51ab-194">Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS</span><span class="sxs-lookup"><span data-stu-id="f51ab-194">Improvements to the app tiles in the Company Portal app for iOS</span></span>
<span data-ttu-id="f51ab-195">Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-195">We updated the design of the app tiles on the homepage to reflect the branding color you set for the Company Portal.</span></span> <span data-ttu-id="f51ab-196">Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-196">For more information, see [what's new in app UI](whats-new-app-ui.md).</span></span>

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a><span data-ttu-id="f51ab-197">Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS</span><span class="sxs-lookup"><span data-stu-id="f51ab-197">Account picker now available for the Company Portal app for iOS</span></span>
<span data-ttu-id="f51ab-198">Os usuários de dispositivos iOS poderão ver nosso novo seletor de conta ao entrarem no Portal da Empresa, caso usem suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f51ab-198">Users of iOS devices might see our new account picker when they sign into the Company Portal if they use their work or school account to sign into other Microsoft apps.</span></span> <span data-ttu-id="f51ab-199">Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-199">For more information, see [what's new in app UI](whats-new-app-ui.md).</span></span>

## <a name="week-of-may-29-2017"></a><span data-ttu-id="f51ab-200">Semana de 29 de maio de 2017</span><span class="sxs-lookup"><span data-stu-id="f51ab-200">Week of May 29, 2017</span></span>

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a><span data-ttu-id="f51ab-201">Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950--></span><span class="sxs-lookup"><span data-stu-id="f51ab-201">Change your MDM authority without unenrolling managed devices <!--1103950--></span></span>

<span data-ttu-id="f51ab-202">Agora você pode alterar a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes.</span><span class="sxs-lookup"><span data-stu-id="f51ab-202">You can now change your MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices.</span></span> <span data-ttu-id="f51ab-203">No console do Configuration Manager, [altere a autoridade de MDM](/sccm/mdm/deploy-use/change-mdm-authority) em Definir como Configuration Manager (híbrido), como Microsoft Intune (autônomo) ou vice-versa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-203">In the Configuration Manager console, you can [change your MDM authority](/sccm/mdm/deploy-use/change-mdm-authority) from Set to Configuration Manager (hybrid) to Microsoft Intune (standalone) or vice versa.</span></span>


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a><span data-ttu-id="f51ab-204">Notificação aprimorada para PINs de inicialização do Samsung KNOX<!--1087143--></span><span class="sxs-lookup"><span data-stu-id="f51ab-204">Improved notification for Samsung KNOX startup PINs <!--1087143--></span></span>
<span data-ttu-id="f51ab-205">Quando os usuários finais precisarem definir um PIN de inicialização em dispositivos Samsung KNOX para ficarem em conformidade com a criptografia, a notificação exibida para eles os levará para o local exato no aplicativo de Configurações quando a notificação for tocada.</span><span class="sxs-lookup"><span data-stu-id="f51ab-205">When end users need to set a start-up PIN on Samsung KNOX devices to become compliant with encryption, the notification displayed to end users will bring them to the exact place in the Settings app when the notification is tapped.</span></span>  <span data-ttu-id="f51ab-206">Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.</span><span class="sxs-lookup"><span data-stu-id="f51ab-206">Previously, the notification brought the end user to the password change screen.</span></span>


### <a name="device-enrollment"></a><span data-ttu-id="f51ab-207">Registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f51ab-207">Device enrollment</span></span>

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a><span data-ttu-id="f51ab-208">Suporte para o ASM (Apple School Manager) com iPad compartilhado <!-- 748864, 770395--></span><span class="sxs-lookup"><span data-stu-id="f51ab-208">Apple School Manager (ASM) support with shared iPad <!-- 748864, 770395--></span></span>

<span data-ttu-id="f51ab-209">O Intune agora dá suporte ao uso do ASM (Apple School Manager) no lugar do Programa de registro de dispositivos da Apple para fornecer o registro pronto para uso de dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-209">Intune now supports use of Apple School Manager (ASM) in place of Apple Device Enrollment Program to provide out-of-box enrollment of iOS devices.</span></span> <span data-ttu-id="f51ab-210">A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS).</span><span class="sxs-lookup"><span data-stu-id="f51ab-210">ASM onboarding is required to use the Classroom app for Shared iPads, and is required to enable syncing data from ASM to Azure Active Directory via Microsoft School Data Sync (SDS).</span></span> <span data-ttu-id="f51ab-211">Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-211">For more information, see [Enable iOS device enrollment with Apple School Manager](apple-school-manager-set-up-ios.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f51ab-212">A configuração de iPads Compartilhados para trabalhar com o aplicativo Sala de aula exige configurações de Educação do iOS no Azure que ainda não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f51ab-212">Configuring Shared iPads to work with the Classroom app requires iOS Education configurations in Azure are that not yet available.</span></span>  <span data-ttu-id="f51ab-213">Essa funcionalidade será adicionada em breve.</span><span class="sxs-lookup"><span data-stu-id="f51ab-213">This functionality will be added soon.</span></span>

### <a name="device-management"></a><span data-ttu-id="f51ab-214">Gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="f51ab-214">Device management</span></span>

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a><span data-ttu-id="f51ab-215">Fornecer assistência remota para dispositivos Android usando o TeamViewer <!-- 675418 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-215">Provide remote assistance to Android devices using TeamViewer <!-- 675418 --></span></span>

<span data-ttu-id="f51ab-216">O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="f51ab-216">Intune can now use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Android devices.</span></span> <span data-ttu-id="f51ab-217">Para obter mais informações, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](device-profile-android-teamviewer.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-217">For more information, see [Provide remote assistance for Intune managed Android devices](device-profile-android-teamviewer.md).</span></span>

### <a name="app-management"></a><span data-ttu-id="f51ab-218">Gerenciamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="f51ab-218">App management</span></span>

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a><span data-ttu-id="f51ab-219">Novas condições de políticas de proteção de aplicativo para MAM <!-- 679864 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-219">New app protection policies conditions for MAM <!-- 679864 --></span></span>

<span data-ttu-id="f51ab-220">Agora você pode definir um requisito para o MAM sem os usuários do registro, que impõe as seguintes políticas:</span><span class="sxs-lookup"><span data-stu-id="f51ab-220">You can now set a requirement for MAM without enrollment users that enforces the following policies:</span></span>

- <span data-ttu-id="f51ab-221">Versão mínima do aplicativo</span><span class="sxs-lookup"><span data-stu-id="f51ab-221">Minimum application version</span></span>
- <span data-ttu-id="f51ab-222">Versão mínima do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f51ab-222">Minimum operating system version</span></span>
- <span data-ttu-id="f51ab-223">Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)</span><span class="sxs-lookup"><span data-stu-id="f51ab-223">Minimum Intune APP SDK version of the targeted application (iOS only)</span></span>

<span data-ttu-id="f51ab-224">Esse recurso está disponível no Android e no iOS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-224">This feature is available on both Android and iOS.</span></span> <span data-ttu-id="f51ab-225">O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-225">Intune supports minimum version enforcement for OS platform versions, application versions, and Intune APP SDK.</span></span> <span data-ttu-id="f51ab-226">No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK.</span><span class="sxs-lookup"><span data-stu-id="f51ab-226">On iOS, applications that have the SDK integrated can also set a minimum version enforcement at the SDK level.</span></span> <span data-ttu-id="f51ab-227">O usuário não poderá acessar o aplicativo direcionado se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos três diferentes níveis mencionados acima.</span><span class="sxs-lookup"><span data-stu-id="f51ab-227">The user will be unable to access the targeted application if the minimum requirements through the app protection policy are not met at the three different levels mentioned above.</span></span> <span data-ttu-id="f51ab-228">Neste ponto, o usuário poderá remover sua conta (para aplicativos de várias identidades), fechar o aplicativo ou atualizar a versão do sistema operacional ou do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-228">At this point, the user may either remove their account (for multi-identity applications), close the application, or update the version of the OS or application.</span></span>

<span data-ttu-id="f51ab-229">Defina também outras configurações para fornecer uma notificação sem bloqueio que recomenda uma atualização do sistema operacional ou do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-229">You can also configure additional settings to provide a non-blocking notification that recommends an OS or application upgrade.</span></span> <span data-ttu-id="f51ab-230">Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.</span><span class="sxs-lookup"><span data-stu-id="f51ab-230">This notification can be closed and the application may be used as normal.</span></span>

<span data-ttu-id="f51ab-231">Para obter mais informações, consulte [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md) e [Configurações da política de proteção de aplicativo do Android](app-protection-policy-settings-android.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-231">For more information, see [iOS app protection policy settings](app-protection-policy-settings-ios.md) and [Android app protection policy settings](app-protection-policy-settings-android.md).</span></span>

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a><span data-ttu-id="f51ab-232">Definir as configurações de aplicativo para o Android for Work <!-- 621621 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-232">Configure app configurations for Android for Work <!-- 621621 --></span></span>
<span data-ttu-id="f51ab-233">Alguns aplicativos Android da loja dão suporte a opções de configuração gerenciada que permitem a um administrador de TI controlar como um aplicativo é executado no perfil de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f51ab-233">Some Android apps from the store support managed configuration options that let an IT admin control how an app runs in the work profile.</span></span> <span data-ttu-id="f51ab-234">Com o Intune, agora você pode exibir as configurações com suporte em um aplicativo e defini-las no portal do Intune com um designer de configuração ou um editor de JSON.</span><span class="sxs-lookup"><span data-stu-id="f51ab-234">With Intune, you can now view the configurations supported by an app, and configure them from the Intune portal with a configuration designer or a JSON editor.</span></span> <span data-ttu-id="f51ab-235">Para obter mais informações, consulte [Usar configurações de aplicativo para o Android for Work](app-configuration-policies-use-android.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-235">For more information, see [Use app configurations for Android for Work](app-configuration-policies-use-android.md).</span></span>

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a><span data-ttu-id="f51ab-236">Nova funcionalidade de configuração de aplicativo para MAM sem registro <!-- 677969 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-236">New app configuration capability for MAM without enrollment <!-- 677969 --></span></span>

<span data-ttu-id="f51ab-237">Agora você pode criar políticas de configuração de aplicativo por meio do MAM sem um canal de registro.</span><span class="sxs-lookup"><span data-stu-id="f51ab-237">You can now create app configuration policies through the MAM without enrollment channel.</span></span> <span data-ttu-id="f51ab-238">Esse recurso é equivalente às políticas de configuração de aplicativo disponíveis na configuração de aplicativo do MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="f51ab-238">This feature is equivalent to the app configuration policies available in the mobile device management (MDM) app configuration.</span></span> <span data-ttu-id="f51ab-239">Para obter um exemplo de configuração de aplicativo que usa o MAM sem registro, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-239">For an example of app configuration using MAM without enrollment, see  [Manage Internet access using Managed browser policies with Microsoft Intune](app-configuration-managed-browser.md).</span></span>

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a><span data-ttu-id="f51ab-240">Configurar listas de permissões e bloqueios de URLs para o Managed Browser <!-- 682960 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-240">Configure allowed and blocked URL lists for the Managed Browser <!-- 682960 --></span></span>

<span data-ttu-id="f51ab-241">Agora você pode configurar uma lista de permissões e bloqueios de domínios e URLs para o Intune Managed Browser usando definições de configuração de aplicativo no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="f51ab-241">You can now configure a list of allowed and blocked domains and URLs for the Intune Managed Browser using app configuration settings in the Azure portal.</span></span> <span data-ttu-id="f51ab-242">Essas configurações podem ser definidas independentemente de estarem sendo usadas em um dispositivo gerenciado ou não gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-242">These settings can be configured regardless of whether it is being used on a managed or unmanaged device.</span></span> <span data-ttu-id="f51ab-243">Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-243">For more information, see [Manage Internet access using Managed browser policies with Microsoft Intune](app-configuration-managed-browser.md).</span></span>

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a><span data-ttu-id="f51ab-244">Exibição de assistência técnica da política de proteção de aplicativo <!-- 1069473 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-244">App protection policy helpdesk view <!-- 1069473 --></span></span>

<span data-ttu-id="f51ab-245">Os usuários da assistência técnica de TI agora podem verificar o status da licença do usuário e o status dos aplicativos da política de proteção de aplicativo atribuídos aos usuários na folha Solução de Problemas.</span><span class="sxs-lookup"><span data-stu-id="f51ab-245">IT Helpdesk users can now check user license status and the status of app protection policy apps assigned to users in the Troubleshooting blade.</span></span> <span data-ttu-id="f51ab-246">Para obter detalhes, consulte [Solução de problemas](./help-desk-operators.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-246">For details, see [Troubleshooting](./help-desk-operators.md).</span></span>

### <a name="device-configuration"></a><span data-ttu-id="f51ab-247">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f51ab-247">Device configuration</span></span>

#### <a name="control-website-visits-on-ios-devices----723832---"></a><span data-ttu-id="f51ab-248">Controlar visitas ao site em dispositivos iOS <!-- 723832 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-248">Control website visits on iOS devices <!-- 723832 --></span></span>

<span data-ttu-id="f51ab-249">Agora você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="f51ab-249">You can now control which websites users of iOS devices can visit using one of the following two methods:</span></span>

- <span data-ttu-id="f51ab-250">Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.</span><span class="sxs-lookup"><span data-stu-id="f51ab-250">Add permitted, and blocked URLs using Apples built-in web content filter.</span></span>

- <span data-ttu-id="f51ab-251">Permita que apenas sites especificado sejam acessados pelo navegador Safari.</span><span class="sxs-lookup"><span data-stu-id="f51ab-251">Allow only specified websites to be accessed by the Safari browser.</span></span> <span data-ttu-id="f51ab-252">Para cada site que você especificar são criados indicadores no Safari.</span><span class="sxs-lookup"><span data-stu-id="f51ab-252">Bookmarks are created in Safari for each site you specify.</span></span>

<span data-ttu-id="f51ab-253">Para obter mais informações, consulte [Configurações de filtro de conteúdo da Web para dispositivos iOS](web-content-filter-settings-ios.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-253">For more information, see [Web content filter settings for iOS devices](web-content-filter-settings-ios.md).</span></span>

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a><span data-ttu-id="f51ab-254">Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-254">Preconfigure device permissions for Android for Work apps <!-- 621614 --></span></span>

<span data-ttu-id="f51ab-255">Para aplicativos implantados em perfis de trabalho de dispositivos Android for Work, agora é possível configurar o estado de permissões em aplicativos individuais.</span><span class="sxs-lookup"><span data-stu-id="f51ab-255">For apps deployed to Android for Work device work profiles, you can now configure the permissions state for individual apps.</span></span>  <span data-ttu-id="f51ab-256">Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.</span><span class="sxs-lookup"><span data-stu-id="f51ab-256">By default, Android apps that require device permissions such as access to location or the device camera will prompt users to accept or deny permissions.</span></span>  <span data-ttu-id="f51ab-257">Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone.</span><span class="sxs-lookup"><span data-stu-id="f51ab-257">For example, if an app uses the device's microphone, then the end user is prompted to grant the app permission to use the microphone.</span></span> <span data-ttu-id="f51ab-258">Esse recurso permite definir permissões em nome do usuário final.</span><span class="sxs-lookup"><span data-stu-id="f51ab-258">This feature allows you to define permissions on behalf of the end user.</span></span>  <span data-ttu-id="f51ab-259">É possível configurar permissões para a) negar automaticamente sem notificar o usuário; b) aprovar automaticamente sem notificar o usuário ou c) solicitar que o usuário aceite ou recuse.</span><span class="sxs-lookup"><span data-stu-id="f51ab-259">You can configure permissions to a) automatically deny without notifying the user, b) automatically approve without notifying the user, or c) prompt the user to accept or deny.</span></span> <span data-ttu-id="f51ab-260">Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-260">For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).</span></span>

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a><span data-ttu-id="f51ab-261">Definir PIN específico do aplicativo para dispositivos Android for Work <!-- 728976, 1102534 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-261">Define app-specific PIN for Android for Work devices <!-- 728976, 1102534 --></span></span>

<span data-ttu-id="f51ab-262">Dispositivos Android 7.0 e superior com um perfil de trabalho gerenciados como um dispositivo Android for Work possibilitam ao administrador definir uma política de senha que se aplica somente aos aplicativos no perfil de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f51ab-262">Android 7.0 and above devices with a work profile managed as an Android for Work device let the administrator define a passcode policy that only applies to apps in the work profile.</span></span>  <span data-ttu-id="f51ab-263">As opções incluem:</span><span class="sxs-lookup"><span data-stu-id="f51ab-263">Options include:</span></span>

- <span data-ttu-id="f51ab-264">Definir apenas uma política de senha em todo o dispositivo – essa é a senha que o usuário deve usar para desbloquear seu dispositivo inteiro.</span><span class="sxs-lookup"><span data-stu-id="f51ab-264">Define just a device-wide passcode policy - This is the passcode that the user must use to unlock their entire device.</span></span>
 <span data-ttu-id="f51ab-265">Definir apenas uma política de senha de perfil de trabalho – os usuários deverão inserir uma senha sempre que um aplicativo no perfil de trabalho for aberto.</span><span class="sxs-lookup"><span data-stu-id="f51ab-265">-Define just a work profile passcode policy - Users will be prompted to enter a passcode whenever any app in the work profile is opened.</span></span>
- <span data-ttu-id="f51ab-266">Definir uma política de dispositivo e de perfil de trabalho – o administrador de TI tem a opção de definir uma política de senha de dispositivo e uma política de senha de perfil de trabalho em diferentes níveis (por exemplo, um PIN de quatro dígitos para desbloquear o dispositivo, mas um PIN de seis dígitos para abrir um aplicativo de trabalho).</span><span class="sxs-lookup"><span data-stu-id="f51ab-266">Define both a device and work profile policy - IT admin has the choice to define both a device passcode policy and a work profile passcode policy at differing strengths (for example, a four-digit PIN to unlock the device, but a six-digit PIN to open any work app).</span></span>

<span data-ttu-id="f51ab-267">Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).</span><span class="sxs-lookup"><span data-stu-id="f51ab-267">For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f51ab-268">Isso está disponível somente no Android 7.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="f51ab-268">This is only available on Android 7.0 and above.</span></span>  <span data-ttu-id="f51ab-269">Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.</span><span class="sxs-lookup"><span data-stu-id="f51ab-269">By default, the end user can use the two separately defined PINs or they can elect to combine the two defined PINs into the strongest of the two.</span></span>

#### <a name="new-settings-for-windows-10-devices----978585---"></a><span data-ttu-id="f51ab-270">Novas configurações para dispositivos Windows 10 <!-- 978585 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-270">New settings for Windows 10 devices <!-- 978585 --></span></span>

<span data-ttu-id="f51ab-271">Adicionamos novas [configurações de restrição de dispositivos Windows](device-restrictions-windows-10.md) que controlam recursos como vídeos sem fio, descoberta de dispositivo, alternância de tarefas e mensagens de erro do cartão SIM.</span><span class="sxs-lookup"><span data-stu-id="f51ab-271">We've added new [Windows device restriction settings](device-restrictions-windows-10.md) that control features like wireless displays, device discovery, task switching, and SIM card error messages.</span></span>

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a><span data-ttu-id="f51ab-272">Atualizações da configuração de certificado <!-- 918991 and 823198 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-272">Updates to certificate configuration <!-- 918991 and 823198 --></span></span>

<span data-ttu-id="f51ab-273">Ao criar um perfil de certificado SCEP, em **Formato do nome da entidade**, a opção **Personalizado** está disponível para dispositivos iOS, Android e Windows.</span><span class="sxs-lookup"><span data-stu-id="f51ab-273">When creating a SCEP certificate profile, for **Subject name format**, the **Custom** option is available for iOS, Android, and Windows devices.</span></span> <span data-ttu-id="f51ab-274">Antes dessa atualização, o campo **Personalizado** estava disponível apenas para dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-274">Before this update, the **Custom** field was available for iOS devices only.</span></span> <span data-ttu-id="f51ab-275">Para obter mais informações, consulte [Como criar um perfil de certificado SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).</span><span class="sxs-lookup"><span data-stu-id="f51ab-275">For more information, see [ How to create a SCEP certificate profile] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).</span></span>

<span data-ttu-id="f51ab-276">Ao criar um perfil de certificado PKCS, em **Nome alternativo da entidade**, o **Atributo personalizado do Azure AD** está disponível.</span><span class="sxs-lookup"><span data-stu-id="f51ab-276">When creating a PKCS certificate profile, for **Subject alternative name**, the **Custom Azure AD attribute** is available.</span></span> <span data-ttu-id="f51ab-277">A opção **Departamento** fica disponível quando você seleciona **Atributo personalizado do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="f51ab-277">The **Department** option is available when you select **Custom Azure AD attribute**.</span></span> <span data-ttu-id="f51ab-278">Para obter mais informações, consulte [Como criar um perfil de certificado PKCS] (certificates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).</span><span class="sxs-lookup"><span data-stu-id="f51ab-278">For more information, see [How to create a PKCS certificate profile] (certficates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).</span></span>

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a><span data-ttu-id="f51ab-279">Configurar vários aplicativos que podem ser executados quando um dispositivo Android está no modo de quiosque <!-- 662059 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-279">Configure multiple apps that can run when an Android device is in kiosk mode <!-- 662059 --></span></span>

<span data-ttu-id="f51ab-280">Anteriormente, quando um dispositivo Android estava no modo de quiosque, era possível configurar apenas um aplicativo que tinha permissão para ser executado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-280">When an Android device is in kiosk mode, you could previously only configure one app that was allowed to run.</span></span> <span data-ttu-id="f51ab-281">Agora é possível configurar vários aplicativos usando a ID do aplicativo, a URL da loja ou selecionando um aplicativo Android já gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-281">You can now configure multiple apps using the app ID, store URL, or by selecting an Android app you already manage.</span></span> <span data-ttu-id="f51ab-282">Para obter mais informações, consulte [Configurações do modo de quiosque](device-restrictions-android.md#kiosk).</span><span class="sxs-lookup"><span data-stu-id="f51ab-282">For more information, see [Kiosk mode settings](device-restrictions-android.md#kiosk).</span></span>


## <a name="notices"></a><span data-ttu-id="f51ab-283">Avisos</span><span class="sxs-lookup"><span data-stu-id="f51ab-283">Notices</span></span>

### <a name="ip-addresses-for-intune-updated----1175274---"></a><span data-ttu-id="f51ab-284">Endereços IP atualizados para o Intune <!-- 1175274 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-284">IP addresses for Intune updated <!-- 1175274 --></span></span>

<span data-ttu-id="f51ab-285">Uma [lista atualizada de nomes DNS e endereços IP](/intune/network-bandwidth-use) está disponível para as configurações de proxy do firewall.</span><span class="sxs-lookup"><span data-stu-id="f51ab-285">An [updated list of DNS names and IP addresses](/intune/network-bandwidth-use) is available for firewall proxy settings.</span></span>

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a><span data-ttu-id="f51ab-286">Usar o Azure Active Directory para o acesso condicional <!-- 967947 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-286">Use Azure Active Directory for conditional access <!-- 967947 --></span></span>

<span data-ttu-id="f51ab-287">O acesso condicional está disponível na seção Azure Active Directory do console do Azure e fornece uma estrutura mais avançada e flexível para definir políticas para aplicativos na nuvem como o Office 365 Exchange Online e o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f51ab-287">Conditional access is available in the Azure Active Directory section of the Azure console and provides a more powerful and flexible framework for setting policies for cloud apps like Office 365 Exchange Online and SharePoint Online.</span></span>  <span data-ttu-id="f51ab-288">Use a folha **Acesso condicional no Azure Active Directory** para configurar políticas em vez do console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-288">Use the **Conditional access in Azure Active Directory** blade to configure policies instead of the classic Intune console.</span></span> <span data-ttu-id="f51ab-289">As políticas existentes no console clássico do Intune precisam ser recriadas no console do Azure.</span><span class="sxs-lookup"><span data-stu-id="f51ab-289">Existing policies in the classic Intune console need to be re-created in the Azure console.</span></span> <span data-ttu-id="f51ab-290">Para obter mais informações, consulte [Criar políticas de acesso condicional do Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)</span><span class="sxs-lookup"><span data-stu-id="f51ab-290">For more information, see [Create Azure AD conditional access policies](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)</span></span>

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a><span data-ttu-id="f51ab-291">Acesso direto aos cenários de registro da Apple <!--951869--></span><span class="sxs-lookup"><span data-stu-id="f51ab-291">Direct access to Apple enrollment scenarios <!--951869--></span></span>

<span data-ttu-id="f51ab-292">Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="f51ab-292">For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal.</span></span> <span data-ttu-id="f51ab-293">Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-293">Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal.</span></span> <span data-ttu-id="f51ab-294">As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure.</span><span class="sxs-lookup"><span data-stu-id="f51ab-294">Intune accounts created before January 2017 require a one-time migration before these features are available in Azure.</span></span> <span data-ttu-id="f51ab-295">A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível.</span><span class="sxs-lookup"><span data-stu-id="f51ab-295">The schedule for migration has not been announced yet, but details will be made available as soon as possible.</span></span> <span data-ttu-id="f51ab-296">É altamente recomendável criar uma conta de avaliação para testar a nova experiência, caso sua conta existente não possa acessar o portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="f51ab-296">We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the Azure portal.</span></span>

### <a name="administration-roles-being-replaced-in-azure-portal"></a><span data-ttu-id="f51ab-297">Funções de administração que estão sendo substituídas no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="f51ab-297">Administration roles being replaced in Azure portal</span></span>

<span data-ttu-id="f51ab-298">As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure.</span><span class="sxs-lookup"><span data-stu-id="f51ab-298">The existing mobile application management (MAM) administration roles (Contributor, Owner, and Read-Only) used in the Intune classic portal (Silverlight) are being replaced with a full set of new role-based administration controls (RBAC) in the Intune Azure portal.</span></span> <span data-ttu-id="f51ab-299">Após a migração para o portal do Azure, você precisará reatribuir essas novas funções de administração aos administradores.</span><span class="sxs-lookup"><span data-stu-id="f51ab-299">Once you are migrated to the Azure portal, you will need to reassign your admins to these new administration roles.</span></span> <span data-ttu-id="f51ab-300">Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune/role-based-access-control).</span><span class="sxs-lookup"><span data-stu-id="f51ab-300">For more information about RBAC and the new roles, see [Role-based access control for Microsoft Intune](/intune/role-based-access-control).</span></span>

## <a name="whats-coming"></a><span data-ttu-id="f51ab-301">O que está por vir</span><span class="sxs-lookup"><span data-stu-id="f51ab-301">What's coming</span></span>

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a><span data-ttu-id="f51ab-302">Fim do suporte para Android 4.3 e inferior <!---1171127, 1326920 ---></span><span class="sxs-lookup"><span data-stu-id="f51ab-302">End of support for Android 4.3 and lower <!---1171127, 1326920 ---></span></span>
<span data-ttu-id="f51ab-303">Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-303">Managed apps and the Company Portal app for Android will require Android 4.4 and higher to access company resources.</span></span> <span data-ttu-id="f51ab-304">Dispositivos que não forem atualizados antes do início de outubro não poderão acessar o Portal da Empresa ou esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f51ab-304">Devices that aren't updated before the beginning of October will no longer be able to access the Company Portal or those apps.</span></span> <span data-ttu-id="f51ab-305">Em dezembro, todos os dispositivos registrados passarão por uma desativação forçada, resultando na perda de acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-305">By December, all enrolled devices will be force retired in December, resulting in loss of access to company resources.</span></span> <span data-ttu-id="f51ab-306">Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e a qualidade da sua experiência decairá ao longo do tempo.</span><span class="sxs-lookup"><span data-stu-id="f51ab-306">If you are using app protection policies without MDM, apps will not receive updates, and the quality of their experience will diminish over time.</span></span>


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a><span data-ttu-id="f51ab-307">Lembrete de suporte de plataforma: o suporte base do Windows Phone 8.1 terminará em 11 de julho de 2017</span><span class="sxs-lookup"><span data-stu-id="f51ab-307">Platform Support Reminder: Windows Phone 8.1 mainstream support will end July 11, 2017</span></span>
<!-- 1327781 -->

<span data-ttu-id="f51ab-308">Em 11 de julho de 2017, a plataforma Windows Phone 8.1 chegará ao fim do suporte base.</span><span class="sxs-lookup"><span data-stu-id="f51ab-308">On July 11, 2017,  the Windows Phone 8.1 platform will reach end of mainstream support.</span></span> <span data-ttu-id="f51ab-309">O suporte da versão Windows 8.1 de computador não é afetado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-309">Windows 8.1 PC support is not impacted.</span></span>

<span data-ttu-id="f51ab-310">Não há nenhum impacto imediato para qualquer dispositivo Windows Phone 8.1 que é gerenciado pelo serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-310">There is no immediate impact to any Windows Phone 8.1 device that is managed by the Intune service.</span></span> <span data-ttu-id="f51ab-311">Dispositivos registrados continuarão a funcionar e todas as políticas, configurações e aplicativos continuarão a funcionar como esperado.</span><span class="sxs-lookup"><span data-stu-id="f51ab-311">Devices that are enrolled will continue to work and all policies, configurations, and apps will continue to work as expected.</span></span> <span data-ttu-id="f51ab-312">Observe que não há nenhuma melhoria voltada para a plataforma Windows Phone 8.1 no Serviço do Intune e para o aplicativo de Portal da Empresa do Windows Phone 8.1.</span><span class="sxs-lookup"><span data-stu-id="f51ab-312">Note that there are no improvements targeted for the Windows Phone 8.1 platform within the Intune Service, and for the Windows Phone 8.1 Company Portal app.</span></span>

<span data-ttu-id="f51ab-313">É recomendável que você atualize os dispositivos Windows Phone 8.1 qualificados para Windows 10 Mobile assim que possível.</span><span class="sxs-lookup"><span data-stu-id="f51ab-313">We recommend that you upgrade eligible Windows Phone 8.1 devices to Windows 10 Mobile at your earliest opportunity.</span></span> 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a><span data-ttu-id="f51ab-314">Alterações no suporte para o aplicativo do Portal da Empresa iOS do Intune  <!-- 1164474  --></span><span class="sxs-lookup"><span data-stu-id="f51ab-314">Changes in support for the Intune iOS Company Portal app  <!-- 1164474  --></span></span>


<span data-ttu-id="f51ab-315">Em breve, haverá uma nova versão do aplicativo do Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 9.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f51ab-315">Coming soon, there will be a new version of the Microsoft Intune Company Portal app for iOS that will support only devices running iOS 9.0 or later.</span></span> <span data-ttu-id="f51ab-316">A versão do Portal da Empresa que dá suporte ao iOS 8 ainda estará disponível por um breve período.</span><span class="sxs-lookup"><span data-stu-id="f51ab-316">The version of the Company Portal that supports iOS 8 will still be available for a very short period of time.</span></span> <span data-ttu-id="f51ab-317">No entanto, observe que se você também usa aplicativos iOS habilitados para MAM, também damos suporte a iOS 9.0 e posterior, por isso é recomendável verificar se os usuários finais atualizaram para o sistema operacional mais recente.</span><span class="sxs-lookup"><span data-stu-id="f51ab-317">However, please note that if you also use MAM-enabled iOS apps we support iOS 9.0 and later, so you'll want to ensure your end users update to the latest OS.</span></span> 

#### <a name="how-does-this-affect-me"></a><span data-ttu-id="f51ab-318">Como isso me afeta?</span><span class="sxs-lookup"><span data-stu-id="f51ab-318">How does this affect me?</span></span>
<span data-ttu-id="f51ab-319">Estamos informando isso com antecedência, mesmo que não tenhamos datas específicas, para que você tenha tempo de planejar.</span><span class="sxs-lookup"><span data-stu-id="f51ab-319">We are letting you know this in advance, even though we don't have specific dates, so you have time to plan.</span></span> <span data-ttu-id="f51ab-320">Verifique se os usuários são atualizados para iOS 9 ou superior e, quando o aplicativo do Portal da Empresa for lançado, solicite que os usuários finais atualizem o aplicativo de Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-320">Please ensure your users are updated to iOS 9+ and when the Company Portal app releases, request that your end users update their Company Portal app.</span></span>

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="f51ab-321">O que preciso fazer para me preparar para essa alteração?</span><span class="sxs-lookup"><span data-stu-id="f51ab-321">What do I need to do to prepare for this change?</span></span>

<span data-ttu-id="f51ab-322">Recomendamos que os usuários atualizem para o iOS 9.0 ou posterior para que eles aproveitem os novos recursos do Intune.</span><span class="sxs-lookup"><span data-stu-id="f51ab-322">Encourage your users to update to iOS 9.0 or later to take full advantage of new Intune features.</span></span>  <span data-ttu-id="f51ab-323">Incentive os usuários a instalarem a nova versão do Portal da Empresa e aproveitar os novos recursos que ele oferece.</span><span class="sxs-lookup"><span data-stu-id="f51ab-323">Encourage users to install the new version of the Company Portal and take advantage of the new features it will offer.</span></span>

<span data-ttu-id="f51ab-324">Acesse o Intune no Portal do Azure e exiba Dispositivos > Todos os Dispositivos e filtre por versão do iOS para ver os dispositivos atuais com os sistemas operacionais anteriores ao iOS 9.</span><span class="sxs-lookup"><span data-stu-id="f51ab-324">Go to the Intune on Azure portal and view Devices > All Devices and filter by iOS version to see any current devices with operating systems earlier than iOS 9.</span></span>

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a><span data-ttu-id="f51ab-325">Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123--></span><span class="sxs-lookup"><span data-stu-id="f51ab-325">Improved sign in experience across Company Portal apps for all platforms <!--User Story 1132123--></span></span>

<span data-ttu-id="f51ab-326">Anunciamos uma alteração que entrará em vigor nos próximos meses, que visa melhorar a experiência de entrada para os aplicativos do Portal da Empresa do Intune para Android, iOS e Windows.</span><span class="sxs-lookup"><span data-stu-id="f51ab-326">We are announcing a change that is coming in the next few months that will improve the sign-in experience for the Intune Company Portal apps for Android, iOS, and Windows.</span></span> <span data-ttu-id="f51ab-327">A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="f51ab-327">The new user experience will automatically appear across all platforms for the Company Portal app when Azure AD makes this change.</span></span> <span data-ttu-id="f51ab-328">Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único.</span><span class="sxs-lookup"><span data-stu-id="f51ab-328">In addition, users can now sign in to the Company Portal from another device with a generated, single-use code.</span></span> <span data-ttu-id="f51ab-329">Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.</span><span class="sxs-lookup"><span data-stu-id="f51ab-329">This is especially useful in cases when users need to sign in without credentials.</span></span>

<span data-ttu-id="f51ab-330">Para ver capturas de tela da experiência de entrada anterior, a nova experiência de entrada com credenciais e a nova experiência de entrada em outro dispositivo, consulte [Novidades da interface do usuário do aplicativo](/intune/whats-new-app-ui).</span><span class="sxs-lookup"><span data-stu-id="f51ab-330">To see screenshots of the previous sign-in experience, the new sign-in experience with credentials, and the new sign-in experience from another device, see [What's new in app UI](/intune/whats-new-app-ui).</span></span>

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a><span data-ttu-id="f51ab-331">Planejar mudanças: o Intune está mudando a experiência do Portal do Parceiro <!-- 1050016 --></span><span class="sxs-lookup"><span data-stu-id="f51ab-331">Plan for change: Intune is changing the Intune Partner Portal experience <!-- 1050016 --></span></span>

<span data-ttu-id="f51ab-332">Vamos remover a página do Parceiro do Microsoft Intune em manage.microsoft.com, a partir da atualização do serviço em meados de maio de 2017.</span><span class="sxs-lookup"><span data-stu-id="f51ab-332">We are removing the Intune Partner page from manage.microsoft.com beginning with the service update in mid-May 2017.</span></span>  

<span data-ttu-id="f51ab-333">Se você for um administrador de parceiro, não será mais possível exibir conteúdo e tomar medidas em nome de seus clientes na página de Parceiro do Microsoft Intune. Em vez disso, deverá entrar em um dos outros Portais de Parceiro da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f51ab-333">If you are a partner administrator, you will no longer be able to view and take action on behalf of your customers from the Intune Partner page, but will instead need to sign in at one of two other partner portals at Microsoft.</span></span>

<span data-ttu-id="f51ab-334">O [Microsoft Partner Center](https://partnercenter.microsoft.com/) e o [Centro de administração do parceiro do Office 365](https://portal.office.com/) permitem entrar nas contas de clientes que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="f51ab-334">Both the [Microsoft Partner Center](https://partnercenter.microsoft.com/) and the [Microsoft Office 365 Partner Admin Center](https://portal.office.com/) will allow you to sign into the customer accounts you manage.</span></span> <span data-ttu-id="f51ab-335">Avançando como parceiro, use um desse sites para gerenciar os clientes.</span><span class="sxs-lookup"><span data-stu-id="f51ab-335">Moving forward as a partner, please use one of these sites to manage your customers.</span></span>


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a><span data-ttu-id="f51ab-336">Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318--></span><span class="sxs-lookup"><span data-stu-id="f51ab-336">Apple to require updates for Application Transport Security <!--748318--></span></span>

<span data-ttu-id="f51ab-337">A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo).</span><span class="sxs-lookup"><span data-stu-id="f51ab-337">Apple has announced that they will enforce specific requirements for Application Transport Security (ATS).</span></span> <span data-ttu-id="f51ab-338">O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-338">ATS is used to enforce stricter security on all app communications over HTTPS.</span></span> <span data-ttu-id="f51ab-339">Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-339">This change impacts Intune customers using the iOS Company Portal apps.</span></span>

<span data-ttu-id="f51ab-340">Disponibilizamos uma versão do aplicativo Portal da Empresa para iOS por meio do programa TestFlight da Apple, que impõe os novos requisitos de ATS.</span><span class="sxs-lookup"><span data-stu-id="f51ab-340">We have made available a version of the Company Portal app for iOS through the Apple TestFlight program that enforces the new ATS requirements.</span></span> <span data-ttu-id="f51ab-341">Se quiser experimentá-lo a fim de testar a conformidade com a ATS, envie um email para <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> informando seu nome e sobrenome, endereço de email e nome da empresa.</span><span class="sxs-lookup"><span data-stu-id="f51ab-341">If you would like to try it so you can test your ATS compliance, email <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> with your first name, last name, email address, and company name.</span></span> <span data-ttu-id="f51ab-342">Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f51ab-342">Review our [Intune support blog](https://aka.ms/compportalats) for more details.</span></span>

### <a name="see-also"></a><span data-ttu-id="f51ab-343">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f51ab-343">See also</span></span>
* [<span data-ttu-id="f51ab-344">Blog do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f51ab-344">Microsoft Intune Blog</span></span>](http://go.microsoft.com/fwlink/?LinkID=273882)
* [<span data-ttu-id="f51ab-345">Mapa da Plataforma de Nuvem</span><span class="sxs-lookup"><span data-stu-id="f51ab-345">Cloud Platform roadmap</span></span>](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [<span data-ttu-id="f51ab-346">Novidades na interface do usuário do Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="f51ab-346">What's new in the Company Portal UI</span></span>](whats-new-app-ui.md)
* [<span data-ttu-id="f51ab-347">Novidades nos meses anteriores</span><span class="sxs-lookup"><span data-stu-id="f51ab-347">What's new in previous months</span></span>](whats-new-archive.md)
=======
### <a name="device-configuration"></a>Configuração do dispositivo  
#### <a name="bitlocker-settings-for-windows-10-----951707---"></a>Configurações do BitLocker para Windows 10  <!-- 951707 -->
Agora você pode definir as configurações do BitLocker para dispositivos Windows 10 usando um novo perfil de dispositivo do Intune. Por exemplo, você pode exigir que os dispositivos sejam criptografados e também definir outras configurações que são aplicadas quando o BitLocker é ativado.
Para obter mais informações, consulte [Configurações do Endpoint Protection para Windows 10 e posterior](endpoint-protection-windows-10.md).

### <a name="new-settings-for-windows-10-device-restriction-profile-----978527--978550-978569-1050031-1058611-----"></a>Novas configurações de perfil de restrição de dispositivo do Windows 10 <!--- 978527,  978550, 978569, 1050031, 1058611,  --->

Nesta versão, adicionamos novas configurações para o perfil de restrição de dispositivo do Windows 10 nas seguintes categorias:

 -  Windows Defender
-  Celular e conectividade
-  Experiência na tela bloqueada
-  Privacidade
-  Pesquisar
-  Destaque do Windows
-  Navegador de borda

Para obter mais informações sobre as configurações do Windows 10, consulte [Configurações de restrição de dispositivo do Windows 10 e posterior](device-restrictions-windows-10.md).

## <a name="week-of-june-12-2017"></a>Semana de 12 de junho de 2017

### <a name="company-portal-app-for-android-now-has-a-new-end-user-experience-for-app-protection-policies---1305217--"></a>O aplicativo de Portal da Empresa para Android agora tem uma nova experiência do usuário final para as Políticas de Proteção do Aplicativo <!--1305217-->
Com base nos comentários dos clientes, modificamos o aplicativo de Portal da Empresa para Android mostrar um botão **Acessar Conteúdo da Empresa**. A intenção é impedir que os usuários finais passem pelo processo de registro desnecessariamente quando eles só precisam acessar os aplicativos que dão suporte às Políticas de Proteção de Aplicativo, um recurso de gerenciamento de aplicativos móveis do Intune. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-menu-action-to-easily-remove-company-portal---1164569--"></a>Nova ação de menu para remover o Portal da Empresa com facilidade <!--1164569-->
De acordo com os comentários dos usuários, o aplicativo do Portal da Empresa para Android adicionou uma nova ação de menu para iniciar a remoção do Portal da Empresa por meio do dispositivo. Essa ação remove o dispositivo do gerenciamento do Intune, de forma que o aplicativo possa ser removido do dispositivo pelo usuário. Veja essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md) e na [documentação do usuário final do Android](/intune-user-help/unenroll-your-device-from-intune-android).

### <a name="improvements-to-app-syncing-with-windows-10-creators-update---676505--"></a>Aprimoramentos à sincronização de aplicativo com a Atualização do Windows 10 para Criadores <!--676505-->

O aplicativo do Portal da Empresa para Windows 10 agora iniciará automaticamente uma sincronização para solicitações de instalação de aplicativo em dispositivos com a Atualização do Windows 10 para Criadores (versão 1703). Isso reduzirá o problema de paralisação de instalações de aplicativo durante o estado de "Sincronização pendente". Além disso, os usuários poderão iniciar manualmente uma sincronização de dentro do aplicativo. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="new-guided-experience-for-windows-10-company-portal----1058938---"></a>Nova experiência orientada para o Portal da Empresa do Windows 10 <!---1058938--->

O aplicativo do Portal da Empresa para o Windows 10 incluirá uma experiência de passo a passo guiado do Intune para dispositivos que não foram identificados nem registrados. A nova experiência fornece instruções passo a passo que guiam o usuário pelo registro no Azure Active Directory (necessário para os recursos do Acesso Condicional) e pelo registro do MDM (necessário para os recursos de gerenciamento de dispositivos). A experiência guiada estará acessível na home page do Portal da Empresa. Os usuários poderão continuar usando o aplicativo se não concluírem o registro, mas terão funcionalidade limitada.

Esta atualização só é visível em dispositivos que executam a Atualização de Aniversário do Windows 10 (build 1607) ou superior. Você pode ver essas alterações na página [Novidades na interface do usuário do aplicativo](whats-new-app-ui.md).

## <a name="week-of-june-5-2017"></a>Semana de 5 de junho de 2017

### <a name="microsoft-intune-and-conditional-access-admin-consoles-are-generally-available"></a>Os consoles de administrador do Microsoft Intune e do Acesso Condicional estão disponíveis

Anunciamos a disponibilidade geral dos novos consoles de administrador do Intune no Azure e do Acesso Condicional. Por meio do Intune no Azure, agora você pode gerenciar todas as funcionalidades MAM e MDM do Intune em uma única experiência de administrador consolidada e aproveitar o agrupamento e direcionamento do Azure AD. O acesso condicional no Azure reúne funcionalidades avançadas no Azure AD e no Intune em um único console unificado. Além disso, de uma experiência administrativa, a migração para a plataforma Azure permite o uso de navegadores modernos.

O Intune agora está visível sem o rótulo **versão prévia** no console do Azure em portal.azure.com.

No momento, nenhuma ação é necessária para os clientes existentes, a menos que você tenha recebido uma de uma série de mensagens no centro de mensagens solicitando uma ação de sua parte para que possamos migrar seus grupos. Talvez você também tenha recebido um aviso do centro de mensagens informando que a migração está levando mais tempo devido a bugs no nosso lado. Continuaremos trabalhando incessantemente para migrar os clientes afetados.

### <a name="improvements-to-the-app-tiles-in-the-company-portal-app-for-ios"></a>Melhorias nos blocos do aplicativo no aplicativo do Portal da Empresa para iOS
Atualizamos o design dos blocos do aplicativo na home page para refletir a cor da identidade visual definida para o Portal da Empresa. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

### <a name="account-picker-now-available-for-the-company-portal-app-for-ios"></a>Seletor de conta agora disponível para o aplicativo do Portal da Empresa para iOS
Os usuários de dispositivos iOS poderão ver nosso novo seletor de conta ao entrarem no Portal da Empresa, caso usem suas contas corporativas ou de estudante para entrar em outros aplicativos da Microsoft. Para obter mais informações, consulte [Novidades da interface do usuário do aplicativo](whats-new-app-ui.md).

## <a name="week-of-may-29-2017"></a>Semana de 29 de maio de 2017

### <a name="change-your-mdm-authority-without-unenrolling-managed-devices---1103950--"></a>Alterar sua autoridade MDM sem cancelar o registro de dispositivos gerenciados <!--1103950-->

Agora você pode alterar a autoridade de MDM sem precisar contatar o Suporte da Microsoft e sem cancelar o registro e registrar novamente os dispositivos gerenciados existentes. No console do Configuration Manager, [altere a autoridade de MDM](/sccm/mdm/deploy-use/change-mdm-authority) em Definir como Configuration Manager (híbrido), como Microsoft Intune (autônomo) ou vice-versa.


### <a name="improved-notification-for-samsung-knox-startup-pins---1087143--"></a>Notificação aprimorada para PINs de inicialização do Samsung KNOX<!--1087143-->
Quando os usuários finais precisarem definir um PIN de inicialização em dispositivos Samsung KNOX para ficarem em conformidade com a criptografia, a notificação exibida para eles os levará para o local exato no aplicativo de Configurações quando a notificação for tocada.  Anteriormente, a notificação levava o usuário final para a tela de alteração de senha.


### <a name="device-enrollment"></a>Registro de dispositivo

#### <a name="apple-school-manager-asm-support-with-shared-ipad----748864-770395--"></a>Suporte para o ASM (Apple School Manager) com iPad compartilhado <!-- 748864, 770395-->

O Intune agora dá suporte ao uso do ASM (Apple School Manager) no lugar do Programa de registro de dispositivos da Apple para fornecer o registro pronto para uso de dispositivos iOS. A integração do ASM é necessária para usar o aplicativo de sala de aula para iPads compartilhados e é necessário para habilitar a sincronização de dados do ASM para o Azure Active Directory por meio da sincronização do Microsoft School Data (SDS). Para obter mais informações, consulte [Habilitar o registro de dispositivo iOS com o Apple School Manager](apple-school-manager-set-up-ios.md).

> [!NOTE]
> A configuração de iPads Compartilhados para trabalhar com o aplicativo Sala de aula exige configurações de Educação do iOS no Azure que ainda não estão disponíveis.  Essa funcionalidade será adicionada em breve.

### <a name="device-management"></a>Gerenciamento de dispositivos

#### <a name="provide-remote-assistance-to-android-devices-using-teamviewer----675418---"></a>Fornecer assistência remota para dispositivos Android usando o TeamViewer <!-- 675418 -->

O Intune agora pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android. Para obter mais informações, consulte [Fornecer assistência remota para dispositivos Android gerenciados pelo Intune](device-profile-android-teamviewer.md).

### <a name="app-management"></a>Gerenciamento de aplicativos

#### <a name="new-app-protection-policies-conditions-for-mam----679864---"></a>Novas condições de políticas de proteção de aplicativo para MAM <!-- 679864 -->

Agora você pode definir um requisito para o MAM sem os usuários do registro, que impõe as seguintes políticas:

- Versão mínima do aplicativo
- Versão mínima do sistema operacional
- Versão mínima do SDK do aplicativo do Intune do aplicativo de destino (somente iOS)

Esse recurso está disponível no Android e no iOS. O Intune dá suporte à imposição de versão mínima para versões de plataforma do sistema operacional, versões de aplicativos e SDK do aplicativo do Intune. No iOS, os aplicativos que têm o SDK integrado também podem definir uma imposição de versão mínima no nível do SDK. O usuário não poderá acessar o aplicativo direcionado se os requisitos mínimos por meio da política de proteção de aplicativo não forem atendidos nos três diferentes níveis mencionados acima. Neste ponto, o usuário poderá remover sua conta (para aplicativos de várias identidades), fechar o aplicativo ou atualizar a versão do sistema operacional ou do aplicativo.

Defina também outras configurações para fornecer uma notificação sem bloqueio que recomenda uma atualização do sistema operacional ou do aplicativo. Essa notificação pode ser fechada e o aplicativo pode ser usado normalmente.

Para obter mais informações, consulte [Configurações da política de proteção de aplicativo do iOS](app-protection-policy-settings-ios.md) e [Configurações da política de proteção de aplicativo do Android](app-protection-policy-settings-android.md).

#### <a name="configure-app-configurations-for-android-for-work----621621---"></a>Definir as configurações de aplicativo para o Android for Work <!-- 621621 -->
Alguns aplicativos Android da loja dão suporte a opções de configuração gerenciada que permitem a um administrador de TI controlar como um aplicativo é executado no perfil de trabalho. Com o Intune, agora você pode exibir as configurações com suporte em um aplicativo e defini-las no portal do Intune com um designer de configuração ou um editor de JSON. Para obter mais informações, consulte [Usar configurações de aplicativo para o Android for Work](app-configuration-policies-use-android.md).

#### <a name="new-app-configuration-capability-for-mam-without-enrollment----677969---"></a>Nova funcionalidade de configuração de aplicativo para MAM sem registro <!-- 677969 -->

Agora você pode criar políticas de configuração de aplicativo por meio do MAM sem um canal de registro. Esse recurso é equivalente às políticas de configuração de aplicativo disponíveis na configuração de aplicativo do MDM (gerenciamento de dispositivo móvel). Para obter um exemplo de configuração de aplicativo que usa o MAM sem registro, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="configure-allowed-and-blocked-url-lists-for-the-managed-browser----682960---"></a>Configurar listas de permissões e bloqueios de URLs para o Managed Browser <!-- 682960 -->

Agora você pode configurar uma lista de permissões e bloqueios de domínios e URLs para o Intune Managed Browser usando definições de configuração de aplicativo no portal do Azure. Essas configurações podem ser definidas independentemente de estarem sendo usadas em um dispositivo gerenciado ou não gerenciado. Para obter mais informações, consulte [Gerenciar o acesso à Internet usando políticas do Managed Browser com o Microsoft Intune](app-configuration-managed-browser.md).

#### <a name="app-protection-policy-helpdesk-view----1069473---"></a>Exibição de assistência técnica da política de proteção de aplicativo <!-- 1069473 -->

Os usuários da assistência técnica de TI agora podem verificar o status da licença do usuário e o status dos aplicativos da política de proteção de aplicativo atribuídos aos usuários na folha Solução de Problemas. Para obter detalhes, consulte [Solução de problemas](./help-desk-operators.md).

### <a name="device-configuration"></a>Configuração do dispositivo

#### <a name="control-website-visits-on-ios-devices----723832---"></a>Controlar visitas ao site em dispositivos iOS <!-- 723832 -->

Agora você pode controlar quais sites os usuários de dispositivos iOS podem visitar usando um dos dois seguintes métodos:

- Adicione URLs permitidas e bloqueadas usando o filtro de conteúdo da web interno da Apple.

- Permita que apenas sites especificado sejam acessados pelo navegador Safari. Para cada site que você especificar são criados indicadores no Safari.

Para obter mais informações, consulte [Configurações de filtro de conteúdo da Web para dispositivos iOS](web-content-filter-settings-ios.md).

#### <a name="preconfigure-device-permissions-for-android-for-work-apps----621614---"></a>Pré-configurar permissões de dispositivo para os aplicativos do Android for Work <!-- 621614 -->

Para aplicativos implantados em perfis de trabalho de dispositivos Android for Work, agora é possível configurar o estado de permissões em aplicativos individuais.  Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso ao local ou a câmera do dispositivo perguntarão se os usuários aceitam ou recusam as permissões.  Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final será solicitado a conceder a permissão de aplicativo para usar o microfone. Esse recurso permite definir permissões em nome do usuário final.  É possível configurar permissões para a) negar automaticamente sem notificar o usuário; b) aprovar automaticamente sem notificar o usuário ou c) solicitar que o usuário aceite ou recuse. Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

#### <a name="define-app-specific-pin-for-android-for-work-devices----728976-1102534---"></a>Definir PIN específico do aplicativo para dispositivos Android for Work <!-- 728976, 1102534 -->

Dispositivos Android 7.0 e superior com um perfil de trabalho gerenciados como um dispositivo Android for Work possibilitam ao administrador definir uma política de senha que se aplica somente aos aplicativos no perfil de trabalho.  As opções incluem:

- Definir apenas uma política de senha em todo o dispositivo – essa é a senha que o usuário deve usar para desbloquear seu dispositivo inteiro.
 Definir apenas uma política de senha de perfil de trabalho – os usuários deverão inserir uma senha sempre que um aplicativo no perfil de trabalho for aberto.
- Definir uma política de dispositivo e de perfil de trabalho – o administrador de TI tem a opção de definir uma política de senha de dispositivo e uma política de senha de perfil de trabalho em diferentes níveis (por exemplo, um PIN de quatro dígitos para desbloquear o dispositivo, mas um PIN de seis dígitos para abrir um aplicativo de trabalho).

Para obter mais informações, consulte [Configurações de restrição de dispositivo do Android for Work no Microsoft Intune](device-restrictions-android-for-work.md).

> [!NOTE]
> Isso está disponível somente no Android 7.0 e superior.  Por padrão, o usuário final pode usar os dois PINs definidos separadamente ou optar por combinar os dois PINs definidos no mais forte dos dois.

#### <a name="new-settings-for-windows-10-devices----978585---"></a>Novas configurações para dispositivos Windows 10 <!-- 978585 -->

Adicionamos novas [configurações de restrição de dispositivos Windows](device-restrictions-windows-10.md) que controlam recursos como vídeos sem fio, descoberta de dispositivo, alternância de tarefas e mensagens de erro do cartão SIM.

#### <a name="updates-to-certificate-configuration----918991-and-823198---"></a>Atualizações da configuração de certificado <!-- 918991 and 823198 -->

Ao criar um perfil de certificado SCEP, em **Formato do nome da entidade**, a opção **Personalizado** está disponível para dispositivos iOS, Android e Windows. Antes dessa atualização, o campo **Personalizado** estava disponível apenas para dispositivos iOS. Para obter mais informações, consulte [Como criar um perfil de certificado SCEP] (certificates-scep-configure.md#how-to-create-a-scep-certificate-profile).

Ao criar um perfil de certificado PKCS, em **Nome alternativo da entidade**, o **Atributo personalizado do Azure AD** está disponível. A opção **Departamento** fica disponível quando você seleciona **Atributo personalizado do Azure AD**. Para obter mais informações, consulte [Como criar um perfil de certificado PKCS] (certificates-pfx-configure.md#how-to-create-a-pkcs-certificate-profile).

#### <a name="configure-multiple-apps-that-can-run-when-an-android-device-is-in-kiosk-mode----662059---"></a>Configurar vários aplicativos que podem ser executados quando um dispositivo Android está no modo de quiosque <!-- 662059 -->

Anteriormente, quando um dispositivo Android estava no modo de quiosque, era possível configurar apenas um aplicativo que tinha permissão para ser executado. Agora é possível configurar vários aplicativos usando a ID do aplicativo, a URL da loja ou selecionando um aplicativo Android já gerenciado. Para obter mais informações, consulte [Configurações do modo de quiosque](device-restrictions-android.md#kiosk).


## <a name="notices"></a>Avisos

### <a name="ip-addresses-for-intune-updated----1175274---"></a>Endereços IP atualizados para o Intune <!-- 1175274 -->

Uma [lista atualizada de nomes DNS e endereços IP](/intune/network-bandwidth-use) está disponível para as configurações de proxy do firewall.

### <a name="use-azure-active-directory-for-conditional-access----967947---"></a>Usar o Azure Active Directory para o acesso condicional <!-- 967947 -->

O acesso condicional está disponível na seção Azure Active Directory do console do Azure e fornece uma estrutura mais avançada e flexível para definir políticas para aplicativos na nuvem como o Office 365 Exchange Online e o SharePoint Online.  Use a folha **Acesso condicional no Azure Active Directory** para configurar políticas em vez do console clássico do Intune. As políticas existentes no console clássico do Intune precisam ser recriadas no console do Azure. Para obter mais informações, consulte [Criar políticas de acesso condicional do Azure AD](/intune/conditional-access-exchange-create.md#create-azure-ad-conditional-access-policies-in-intune-azure-preview)

### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Acesso direto aos cenários de registro da Apple <!--951869-->

Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 precisam de uma migração única antes que esses recursos estejam disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência, caso sua conta existente não possa acessar o portal do Azure.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Funções de administração que estão sendo substituídas no Portal do Azure

As funções de administração de MAM (gerenciamento de aplicativo móvel) existentes (Colaborador, Proprietário e Somente leitura) usadas no Portal Clássico (Silverlight) estão sendo substituídas por um conjunto completo de novos RBAC (Controles de administração baseados em função) no Portal do Intune no Azure. Após a migração para o portal do Azure, você precisará reatribuir essas novas funções de administração aos administradores. Para saber mais sobre RBAC e as novas funções, consulte [Controle de acesso baseado em função do Microsoft Intune](/intune/role-based-access-control).

## <a name="whats-coming"></a>O que está por vir

### <a name="end-of-support-for-android-43-and-lower----1171127-1326920----"></a>Fim do suporte para Android 4.3 e inferior <!---1171127, 1326920 --->
Aplicativos gerenciados e o aplicativo de Portal da Empresa para Android exigirão o Android 4.4 e superior para acessar os recursos da empresa. Dispositivos que não forem atualizados antes do início de outubro não poderão acessar o Portal da Empresa ou esses aplicativos. Em dezembro, todos os dispositivos registrados passarão por uma desativação forçada, resultando na perda de acesso aos recursos da empresa. Se você estiver usando políticas de proteção do aplicativo sem MDM, os aplicativos não receberão atualizações e a qualidade da sua experiência decairá ao longo do tempo.


### <a name="platform-support-reminder-windows-phone-81-mainstream-support-will-end-july-11-2017"></a>Lembrete de suporte de plataforma: o suporte base do Windows Phone 8.1 terminará em 11 de julho de 2017
<!-- 1327781 -->

Em 11 de julho de 2017, a plataforma Windows Phone 8.1 chegará ao fim do suporte base. O suporte da versão Windows 8.1 de computador não é afetado.

Não há nenhum impacto imediato para qualquer dispositivo Windows Phone 8.1 que é gerenciado pelo serviço do Intune. Dispositivos registrados continuarão a funcionar e todas as políticas, configurações e aplicativos continuarão a funcionar como esperado. Observe que não há nenhuma melhoria voltada para a plataforma Windows Phone 8.1 no Serviço do Intune e para o aplicativo de Portal da Empresa do Windows Phone 8.1.

É recomendável que você atualize os dispositivos Windows Phone 8.1 qualificados para Windows 10 Mobile assim que possível. 

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Alterações no suporte para o aplicativo do Portal da Empresa iOS do Intune  <!-- 1164474  -->


Em breve, haverá uma nova versão do aplicativo do Portal da Empresa do Microsoft Intune para iOS que dará suporte somente a dispositivos que executam o iOS 9.0 ou posterior. A versão do Portal da Empresa que dá suporte ao iOS 8 ainda estará disponível por um breve período. No entanto, observe que se você também usa aplicativos iOS habilitados para MAM, também damos suporte a iOS 9.0 e posterior, por isso é recomendável verificar se os usuários finais atualizaram para o sistema operacional mais recente. 

#### <a name="how-does-this-affect-me"></a>Como isso me afeta?
Estamos informando isso com antecedência, mesmo que não tenhamos datas específicas, para que você tenha tempo de planejar. Verifique se os usuários são atualizados para iOS 9 ou superior e, quando o aplicativo do Portal da Empresa for lançado, solicite que os usuários finais atualizem o aplicativo de Portal da Empresa.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração?

Recomendamos que os usuários atualizem para o iOS 9.0 ou posterior para que eles aproveitem os novos recursos do Intune.  Incentive os usuários a instalarem a nova versão do Portal da Empresa e aproveitar os novos recursos que ele oferece.

Acesse o Intune no Portal do Azure e exiba Dispositivos > Todos os Dispositivos e filtre por versão do iOS para ver os dispositivos atuais com os sistemas operacionais anteriores ao iOS 9.

### <a name="improved-sign-in-experience-across-company-portal-apps-for-all-platforms---user-story-1132123--"></a>Experiência de início de sessão aprimorada em aplicativos Portal da Empresa para todas as plataformas <!--User Story 1132123-->

Anunciamos uma alteração que entrará em vigor nos próximos meses, que visa melhorar a experiência de entrada para os aplicativos do Portal da Empresa do Intune para Android, iOS e Windows. A nova experiência do usuário será exibida automaticamente em todas as plataformas para o aplicativo Portal da Empresa quando o Azure AD fizer essa alteração. Além disso, agora os usuários poderão entrar no Portal da Empresa através de outro dispositivo, com um código gerado de uso único. Isso é especialmente útil nos casos em que os usuários precisam entrar sem credenciais.

Para ver capturas de tela da experiência de entrada anterior, a nova experiência de entrada com credenciais e a nova experiência de entrada em outro dispositivo, consulte [Novidades da interface do usuário do aplicativo](/intune/whats-new-app-ui).

### <a name="plan-for-change-intune-is-changing-the-intune-partner-portal-experience----1050016---"></a>Planejar mudanças: o Intune está mudando a experiência do Portal do Parceiro <!-- 1050016 -->

Vamos remover a página do Parceiro do Microsoft Intune em manage.microsoft.com, a partir da atualização do serviço em meados de maio de 2017.  

Se você for um administrador de parceiro, não será mais possível exibir conteúdo e tomar medidas em nome de seus clientes na página de Parceiro do Microsoft Intune. Em vez disso, deverá entrar em um dos outros Portais de Parceiro da Microsoft.

O [Microsoft Partner Center](https://partnercenter.microsoft.com/) e o [Centro de administração do parceiro do Office 365](https://portal.office.com/) permitem entrar nas contas de clientes que você gerencia. Avançando como parceiro, use um desse sites para gerenciar os clientes.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple para exigir atualizações para Segurança de Transporte do aplicativo <!--748318-->

A Apple anunciou que pretende impor requisitos específicos para ATS (Segurança de Transporte de Aplicativo). O ATS é usado para impor a segurança mais rígida em todas as comunicações de aplicativo via HTTPS. Essa alteração afeta os clientes do Intune que usam os aplicativos de Portal da Empresa do iOS.

Disponibilizamos uma versão do aplicativo Portal da Empresa para iOS por meio do programa TestFlight da Apple, que impõe os novos requisitos de ATS. Se quiser experimentá-lo a fim de testar a conformidade com a ATS, envie um email para <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a> informando seu nome e sobrenome, endereço de email e nome da empresa. Examine nosso [blog de suporte do Intune](https://aka.ms/compportalats) para obter mais detalhes.

### <a name="see-also"></a>Consulte também
* [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Mapa da Plataforma de Nuvem](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [Novidades na interface do usuário do Portal da Empresa](whats-new-app-ui.md)
* [Novidades nos meses anteriores](whats-new-archive.md)
>>>>>>> live
