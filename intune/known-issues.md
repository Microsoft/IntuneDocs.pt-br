---
title: Problemas conhecidos no Microsoft Intune no Azure
titleSuffix: Intune on Azure
description: Leia mais sobre os problemas conhecidos no Intune
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4fda224613d8b69be82ef7f9681ba9165be33e52
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="707be-103">Problemas conhecidos no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="707be-103">Known issues in Microsoft Intune</span></span>
=======
# Problemas conhecidos no Microsoft Intune
>>>>>>> live
<a id="known-issues-in-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<<<<<<< HEAD
<span data-ttu-id="707be-104">Use este tópico para saber mais sobre os problemas conhecidos no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="707be-104">Use this topic to learn about any known issues in Microsoft Intune.</span></span>

<span data-ttu-id="707be-105">Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](get-support.md).</span><span class="sxs-lookup"><span data-stu-id="707be-105">If you want to report a bug that is not listed here, [open a support request](get-support.md).</span></span>

<span data-ttu-id="707be-106">Caso você deseje solicitar um novo recurso para o Intune, considere enviar um relatório em nosso site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).</span><span class="sxs-lookup"><span data-stu-id="707be-106">If you want to request a new feature for Intune, consider filing a report on our [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) site.</span></span>

## <span data-ttu-id="707be-107">Migração</span><span class="sxs-lookup"><span data-stu-id="707be-107">Migration</span></span>
<a id="migration" class="xliff"></a>

### <span data-ttu-id="707be-108">Os grupos criados pelo Intune durante a migração podem afetar a funcionalidade de outros produtos da Microsoft</span><span class="sxs-lookup"><span data-stu-id="707be-108">Groups created by Intune during migration might affect functionality of other Microsoft products</span></span>
<a id="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products" class="xliff"></a>

<span data-ttu-id="707be-109">Ao migrar do Intune clássico para o Azure, você poderá ver um novo grupo chamado **Todos os Usuários – b0b08746-4dbe-4a37-9adf-9e7652c0b421**.</span><span class="sxs-lookup"><span data-stu-id="707be-109">When you migrate from classic Intune to the Azure, you might see a new group named **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**.</span></span> <span data-ttu-id="707be-110">Esse grupo contém todos os usuários em seu Azure Active Directory, não apenas os usuários licenciados do Intune.</span><span class="sxs-lookup"><span data-stu-id="707be-110">This group contains all users in your Azure Active Directory, not only Intune licensed users.</span></span> <span data-ttu-id="707be-111">Esse uso pode causar problemas com outros produtos da Microsoft, caso você espere que alguns usuários novos ou existentes não sejam membros de nenhum grupo.</span><span class="sxs-lookup"><span data-stu-id="707be-111">This usage can cause issues with other Microsoft products if you expect some existing or new users to not be a member of any groups.</span></span>

### <span data-ttu-id="707be-112">Migração secundária necessária para funcionalidades selecionadas</span><span class="sxs-lookup"><span data-stu-id="707be-112">Secondary migration required for select capabilities</span></span>
<a id="secondary-migration-required-for-select-capabilities" class="xliff"></a>

<span data-ttu-id="707be-113">As contas do Intune criadas antes de janeiro de 2017 devem ser migradas antes que essas funcionalidades possam ser usadas no portal do Azure:</span><span class="sxs-lookup"><span data-stu-id="707be-113">Intune accounts created before January 2017 must be migrated before these capabilities can be used in the Azure portal:</span></span>

- <span data-ttu-id="707be-114">Perfis de Registro de Dispositivo Corporativo</span><span class="sxs-lookup"><span data-stu-id="707be-114">Corporate Device Enrollment profiles</span></span>
- <span data-ttu-id="707be-115">Programa de Registro do Dispositivo da Apple</span><span class="sxs-lookup"><span data-stu-id="707be-115">Apple Device Enrollment Program</span></span>
- <span data-ttu-id="707be-116">Dispositivos corporativos pré-registrados por grupo de número de série do iOS</span><span class="sxs-lookup"><span data-stu-id="707be-116">Corporate Pre-enrolled devices by iOS Serial Number group</span></span>
- <span data-ttu-id="707be-117">Gerenciadores de Registro de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="707be-117">Device Enrollment Managers</span></span>
- <span data-ttu-id="707be-118">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="707be-118">Apple Volume Purchase Program</span></span>

<span data-ttu-id="707be-119">Como essas funcionalidades não podem ser gerenciadas nos consoles clássicos do Silverlight e do Azure, a migração:</span><span class="sxs-lookup"><span data-stu-id="707be-119">Because these capabilities cannot be managed from both the classic Silverlight and Azure consoles, the migration:</span></span>
- <span data-ttu-id="707be-120">Desabilita-as no console clássico</span><span class="sxs-lookup"><span data-stu-id="707be-120">Disables them in the classic console</span></span>
- <span data-ttu-id="707be-121">Habilita-as no console do Azure.</span><span class="sxs-lookup"><span data-stu-id="707be-121">Enables them in the Azure console.</span></span>  

<span data-ttu-id="707be-122">Se você gerenciar essas funcionalidades do Intune no Portal do Azure agora, lembre-se dos seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="707be-122">If you now manage these Intune capabilities in the Azure portal, be aware of the following points:</span></span>

#### <span data-ttu-id="707be-123">Remove os perfis de Registro de Dispositivo Corporativo no Apple DEP</span><span class="sxs-lookup"><span data-stu-id="707be-123">Removes default Corporate Device Enrollment profiles in Apple DEP</span></span>
<a id="removes-default-corporate-device-enrollment-profiles-in-apple-dep" class="xliff"></a>
<span data-ttu-id="707be-124">O Portal do Azure não dá suporte ao perfil de Registro de Dispositivo Corporativo padrão em dispositivos Apple DEP (Programa de Registro de dispositivos).</span><span class="sxs-lookup"><span data-stu-id="707be-124">The Azure Portal does not support a default Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) devices.</span></span> <span data-ttu-id="707be-125">Essa funcionalidade, disponível no console clássico do Intune no Silverlight, foi descontinuada para impedir a atribuição acidental de perfis.</span><span class="sxs-lookup"><span data-stu-id="707be-125">This functionality, available in the classic Silverlight Intune console, is discontinued to prevent unintentional profile assignment.</span></span> <span data-ttu-id="707be-126">Quando os números de série DEP são sincronizados no Portal do Azure, nenhum perfil de Registro de Dispositivo Corporativo é atribuído.</span><span class="sxs-lookup"><span data-stu-id="707be-126">When DEP serial numbers sync in the Azure Portal, no Corporate Device Enrollment profile is assigned.</span></span> <span data-ttu-id="707be-127">Um perfil de registro deve ser atribuído antes do uso do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="707be-127">An enrollment profile must be assigned before using the device.</span></span>

#### <span data-ttu-id="707be-128">Token de DEP da Apple restaurado com a migração</span><span class="sxs-lookup"><span data-stu-id="707be-128">Apple DEP token restored with migration</span></span>
<a id="apple-dep-token-restored-with-migration" class="xliff"></a>

<span data-ttu-id="707be-129">Se você excluir um token do Programa de registro de dispositivos da Apple no Portal Clássico do Intune (Silverlight) e não carregar um novo token para o Portal do Azure, o token original será restaurado no Portal do Azure durante a migração.</span><span class="sxs-lookup"><span data-stu-id="707be-129">If you deleted an Apple Device Enrollment Program token in the Intune classic (Silverlight) portal and do not upload a new token to the Azure portal, the original token is restored in the Azure portal when you migrate.</span></span> <span data-ttu-id="707be-130">Para remover esse token e impedir o registro DEP, exclua o token no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="707be-130">To remove this token and prevent DEP enrollment, delete the token from the Azure portal.</span></span>

### <span data-ttu-id="707be-131">As folhas de status das políticas migradas não funcionam</span><span class="sxs-lookup"><span data-stu-id="707be-131">Status blades for migrated policies do not work</span></span>
<a id="status-blades-for-migrated-policies-do-not-work" class="xliff"></a>

<span data-ttu-id="707be-132">Não é possível exibir informações de status de políticas que foram migradas do portal clássico no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="707be-132">You cannot view status information for policies that were migrated from the classic portal in the Azure portal.</span></span> <span data-ttu-id="707be-133">No entanto, você pode continuar exibindo relatórios dessas políticas no portal Clássico.</span><span class="sxs-lookup"><span data-stu-id="707be-133">However, you can continue to view reports for these policies in the Classic portal.</span></span>
<span data-ttu-id="707be-134">Para exibir informações de status das políticas de configuração migradas, recrie-as no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="707be-134">To view status information for migrated configuration policies, recreate them in the Azure portal.</span></span>

## <span data-ttu-id="707be-135">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="707be-135">Apps</span></span>
<a id="apps" class="xliff"></a>

### <span data-ttu-id="707be-136">Aplicativos iOS adquiridos por volume disponíveis somente no idioma padrão do locatário do Intune</span><span class="sxs-lookup"><span data-stu-id="707be-136">iOS volume-purchased apps only available in default Intune tenant language</span></span>
<a id="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language" class="xliff"></a>
<span data-ttu-id="707be-137">Aplicativos do iOS adquiridos por volume são exibidos e podem ser atribuídos apenas para o mesmo código de país que sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="707be-137">iOS volume-purchased apps are displayed, and can be assigned only for the same country code as your Intune account.</span></span> <span data-ttu-id="707be-138">O Intune somente sincroniza aplicativos da mesma localidade do iTunes do código de país de conta de locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="707be-138">Intune only sync apps from the same iTunes locale as the Intune tenant account country code.</span></span> <span data-ttu-id="707be-139">Por exemplo, se você comprar um aplicativo que está disponível apenas na loja dos EUA, mas sua conta do Intune é da Alemanha, o Intune não mostrará o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="707be-139">For example, if you purchase an app which is only available in the US store, but your Intune account is German, Intune will not show that app.</span></span>

### <span data-ttu-id="707be-140">Várias cópias do mesmo programa iOS de compra por volume serão carregadas</span><span class="sxs-lookup"><span data-stu-id="707be-140">Multiple copies of the same iOS volume-purchase program are uploaded</span></span>
<a id="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded" class="xliff"></a>
<span data-ttu-id="707be-141">Não clique no botão **Carregar** várias vezes para o mesmo token VPP.</span><span class="sxs-lookup"><span data-stu-id="707be-141">Do not click the **Upload** button multiple times for the same VPP token.</span></span> <span data-ttu-id="707be-142">Isso resultará no carregamento de tokens VPP duplicados e na sincronização do aplicativo diversas vezes para o mesmo token VPP.</span><span class="sxs-lookup"><span data-stu-id="707be-142">This will result in duplicate VPP tokens being uploaded, and apps syncing multiple times for the same VPP token.</span></span> 

<!-- ## Groups -->

## <span data-ttu-id="707be-143">Configuração do dispositivo</span><span class="sxs-lookup"><span data-stu-id="707be-143">Device configuration</span></span>
<a id="device-configuration" class="xliff"></a>

### <span data-ttu-id="707be-144">Não é possível salvar uma política de Proteção de Informações do Windows em alguns dispositivos</span><span class="sxs-lookup"><span data-stu-id="707be-144">You cannot save a Windows Information Protection policy for some devices</span></span>
<a id="you-cannot-save-a-windows-information-protection-policy-for-some-devices" class="xliff"></a>

<span data-ttu-id="707be-145">Para dispositivos não registrados com o Intune, só é possível especificar um domínio primário no campo **Identificação Corporativa** nas configurações de uma política de Proteção de Informações do Windows.</span><span class="sxs-lookup"><span data-stu-id="707be-145">For devices not enrolled with Intune, you can only specify a primary domain in the **Corporate Identify** field in the settings for a Windows Information Protection policy.</span></span>
<span data-ttu-id="707be-146">Se você adicionar outros domínios (usando **Configurações avançadas** > **Perímetro da rede** > **Adicionar um domínio protegido**), não poderá salvar a política.</span><span class="sxs-lookup"><span data-stu-id="707be-146">If you add additional domains (using **Advanced settings** > **Network perimeter** > **Add a protected domain**), you cannot save the policy.</span></span> <span data-ttu-id="707be-147">A mensagem de erro exibida será alterada em breve para ser mais precisa.</span><span class="sxs-lookup"><span data-stu-id="707be-147">The error message you see will soon be changed to be more accurate.</span></span>

### <span data-ttu-id="707be-148">Suporte ao cliente VPN do Cisco AnyConnect</span><span class="sxs-lookup"><span data-stu-id="707be-148">Cisco AnyConnect VPN client support</span></span>
<a id="cisco-anyconnect-vpn-client-support" class="xliff"></a>
 
<span data-ttu-id="707be-149">A versão mais recente do cliente VPN do Cisco AnyConnect (4.0.07072) não é compatível com o Intune no momento.</span><span class="sxs-lookup"><span data-stu-id="707be-149">The latest release of the Cisco AnyConnect VPN client (4.0.07072) is not currently compatible with Intune.</span></span> <span data-ttu-id="707be-150">Uma atualização futura do Intune incluirá a compatibilidade com esta versão do cliente VPN.</span><span class="sxs-lookup"><span data-stu-id="707be-150">A future Intune update will include compatibility with this VPN client version.</span></span> <span data-ttu-id="707be-151">Até lá, recomendamos não atualizar o cliente VPN do Cisco AnyConnect e continuar a usar a versão existente.</span><span class="sxs-lookup"><span data-stu-id="707be-151">Until then, we recommend that you do not update your Cisco AnyConnect VPN client, and continue to use the existing version.</span></span>

### <span data-ttu-id="707be-152">Usando o tipo de senha numérica com dispositivos macOS Serra</span><span class="sxs-lookup"><span data-stu-id="707be-152">Using the numeric password type with macOS Sierra devices</span></span>
<a id="using-the-numeric-password-type-with-macos-sierra-devices" class="xliff"></a>

<span data-ttu-id="707be-153">Atualmente, se você selecionar o **Tipo de senha necessário** **Numérica** em um perfil de restrição de dispositivo em dispositivos macOS Sierra, ele será imposto como **Alfanumérica**.</span><span class="sxs-lookup"><span data-stu-id="707be-153">Currently, if you select the **Numeric** **Required password type** in a device restriction profile for macOS Sierra devices, it is enforced as **Alphanumeric**.</span></span> <span data-ttu-id="707be-154">Se você desejar usar uma senha numérica com esses dispositivos, não defina essa configuração.</span><span class="sxs-lookup"><span data-stu-id="707be-154">If you want to use a numeric password with these devices, do not configure this setting.</span></span>
<span data-ttu-id="707be-155">Esse problema poderá ser corrigido em uma versão futura do macOS.</span><span class="sxs-lookup"><span data-stu-id="707be-155">This issue might be corrected in a future version of macOS.</span></span>

<span data-ttu-id="707be-156">Para obter mais informações sobre essas configurações, consulte [Configurações de restrição de dispositivo macOS no Microsoft Intune](device-restrictions-macos.md).</span><span class="sxs-lookup"><span data-stu-id="707be-156">For more information about these settings, see [macOS device restriction settings in Microsoft Intune](device-restrictions-macos.md).</span></span>

## <span data-ttu-id="707be-157">Conformidade</span><span class="sxs-lookup"><span data-stu-id="707be-157">Compliance</span></span>
<a id="compliance" class="xliff"></a>

### <span data-ttu-id="707be-158">As políticas de conformidade do Intune não são mostradas no novo console</span><span class="sxs-lookup"><span data-stu-id="707be-158">Compliance policies from Intune do not show up in new console</span></span>
<a id="compliance-policies-from-intune-do-not-show-up-in-new-console" class="xliff"></a>

<span data-ttu-id="707be-159">As políticas de conformidade criadas no portal clássico são migradas, mas não são exibidas no portal do Azure, devido às alterações de design no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="707be-159">Compliance policies you created in the classic portal are migrated, but are not displayed in the Azure portal because of design changes in the Azure portal.</span></span> <span data-ttu-id="707be-160">As políticas de conformidade criadas no portal clássico do Intune ainda são impostas, mas devem ser exibidas e editadas no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="707be-160">Compliance policies you created in the classic Intune portal are still enforced, but you must view and edit them in the classic Intune portal.</span></span>
<span data-ttu-id="707be-161">Além disso, novas políticas de conformidade criadas no portal do Azure não estão visíveis no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="707be-161">Additionally, new compliance policies you create in the Azure portal are not visible in the classic Intune portal.</span></span>

<span data-ttu-id="707be-162">Para saber mais, veja [O que é a conformidade do dispositivo](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="707be-162">For more information, see [What is device compliance](device-compliance.md).</span></span>

<!-- ## Enrollment -->


<!-- ## Data protection -->


## <span data-ttu-id="707be-163">Administração e contas</span><span class="sxs-lookup"><span data-stu-id="707be-163">Administration and accounts</span></span>
<a id="administration-and-accounts" class="xliff"></a>

<span data-ttu-id="707be-164">Administradores Globais (também conhecidos como Administradores de Locatários) podem continuar realizando tarefas de administração diárias sem uma licença separada do Intune ou do EMS (Enterprise Mobility Suite).</span><span class="sxs-lookup"><span data-stu-id="707be-164">Global Admins (also referred to as Tenant Admins) can continue day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license.</span></span> <span data-ttu-id="707be-165">No entanto, para usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisam de uma licença do Intune ou do EMS.</span><span class="sxs-lookup"><span data-stu-id="707be-165">However, to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they need an Intune or EMS license.</span></span>

<!-- ## Additional items -->





=======
Use este tópico para saber mais sobre os problemas conhecidos no Microsoft Intune.

Se você deseja relatar um bug que não está listado aqui, [abra uma solicitação de suporte](get-support.md).

Caso você deseje solicitar um novo recurso para o Intune, considere enviar um relatório em nosso site [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console).

## Migração
<a id="migration" class="xliff"></a>

### Os grupos criados pelo Intune durante a migração podem afetar a funcionalidade de outros produtos da Microsoft
<a id="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products" class="xliff"></a>

Ao migrar do Intune clássico para o Azure, você poderá ver um novo grupo chamado **Todos os Usuários – b0b08746-4dbe-4a37-9adf-9e7652c0b421**. Esse grupo contém todos os usuários em seu Azure Active Directory, não apenas os usuários licenciados do Intune. Esse uso pode causar problemas com outros produtos da Microsoft, caso você espere que alguns usuários novos ou existentes não sejam membros de nenhum grupo.

### Migração secundária necessária para funcionalidades selecionadas
<a id="secondary-migration-required-for-select-capabilities" class="xliff"></a>

As contas do Intune criadas antes de janeiro de 2017 devem ser migradas antes que essas funcionalidades possam ser usadas no portal do Azure:

- Perfis de Registro de Dispositivo Corporativo
- Programa de Registro do Dispositivo da Apple
- Dispositivos corporativos pré-registrados por grupo de número de série do iOS
- Gerenciadores de Registro de Dispositivos
- Apple Volume Purchase Program

Como essas funcionalidades não podem ser gerenciadas nos consoles clássicos do Silverlight e do Azure, a migração:
- Desabilita-as no console clássico
- Habilita-as no console do Azure.  

Se você gerenciar essas funcionalidades do Intune no Portal do Azure agora, lembre-se dos seguintes pontos:

#### Remove os perfis de Registro de Dispositivo Corporativo no Apple DEP
<a id="removes-default-corporate-device-enrollment-profiles-in-apple-dep" class="xliff"></a>
O Portal do Azure não dá suporte ao perfil de Registro de Dispositivo Corporativo padrão em dispositivos Apple DEP (Programa de Registro de dispositivos). Essa funcionalidade, disponível no console clássico do Intune no Silverlight, foi descontinuada para impedir a atribuição acidental de perfis. Quando os números de série DEP são sincronizados no Portal do Azure, nenhum perfil de Registro de Dispositivo Corporativo é atribuído. Um perfil de registro deve ser atribuído antes do uso do dispositivo.

#### Token de DEP da Apple restaurado com a migração
<a id="apple-dep-token-restored-with-migration" class="xliff"></a>

Se você excluir um token do Programa de registro de dispositivos da Apple no Portal Clássico do Intune (Silverlight) e não carregar um novo token para o Portal do Azure, o token original será restaurado no Portal do Azure durante a migração. Para remover esse token e impedir o registro DEP, exclua o token no Portal do Azure.

### As folhas de status das políticas migradas não funcionam
<a id="status-blades-for-migrated-policies-do-not-work" class="xliff"></a>

Não é possível exibir informações de status de políticas que foram migradas do portal clássico no portal do Azure. No entanto, você pode continuar exibindo relatórios dessas políticas no portal Clássico.
Para exibir informações de status das políticas de configuração migradas, recrie-as no portal do Azure.

## Aplicativos
<a id="apps" class="xliff"></a>

### Aplicativos iOS adquiridos por volume disponíveis somente no idioma padrão do locatário do Intune
<a id="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language" class="xliff"></a>
Aplicativos do iOS adquiridos por volume são exibidos e podem ser atribuídos apenas para o mesmo código de país que sua conta do Intune. O Intune somente sincroniza aplicativos da mesma localidade do iTunes do código de país de conta de locatário do Intune. Por exemplo, se você comprar um aplicativo que está disponível apenas na loja dos EUA, mas sua conta do Intune é da Alemanha, o Intune não mostrará o aplicativo.

### Várias cópias do mesmo programa iOS de compra por volume serão carregadas
<a id="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded" class="xliff"></a>
Não clique no botão **Carregar** várias vezes para o mesmo token VPP. Isso resultará no carregamento de tokens VPP duplicados e na sincronização do aplicativo diversas vezes para o mesmo token VPP. 

<!-- ## Groups -->

## Configuração do dispositivo
<a id="device-configuration" class="xliff"></a>

### Não é possível salvar uma política de Proteção de Informações do Windows em alguns dispositivos
<a id="you-cannot-save-a-windows-information-protection-policy-for-some-devices" class="xliff"></a>

Para dispositivos não registrados com o Intune, só é possível especificar um domínio primário no campo **Identificação Corporativa** nas configurações de uma política de Proteção de Informações do Windows.
Se você adicionar outros domínios (usando **Configurações avançadas** > **Perímetro da rede** > **Adicionar um domínio protegido**), não poderá salvar a política. A mensagem de erro exibida será alterada em breve para ser mais precisa.

### Suporte ao cliente VPN do Cisco AnyConnect
<a id="cisco-anyconnect-vpn-client-support" class="xliff"></a>
 
A versão mais recente do cliente VPN do Cisco AnyConnect (4.0.07072) não é compatível com o Intune no momento. Uma atualização futura do Intune incluirá a compatibilidade com esta versão do cliente VPN. Até lá, recomendamos não atualizar o cliente VPN do Cisco AnyConnect e continuar a usar a versão existente.

### Usando o tipo de senha numérica com dispositivos macOS Serra
<a id="using-the-numeric-password-type-with-macos-sierra-devices" class="xliff"></a>

Atualmente, se você selecionar o **Tipo de senha necessário** **Numérica** em um perfil de restrição de dispositivo em dispositivos macOS Sierra, ele será imposto como **Alfanumérica**. Se você desejar usar uma senha numérica com esses dispositivos, não defina essa configuração.
Esse problema poderá ser corrigido em uma versão futura do macOS.

Para obter mais informações sobre essas configurações, consulte [Configurações de restrição de dispositivo macOS no Microsoft Intune](device-restrictions-macos.md).

## Conformidade
<a id="compliance" class="xliff"></a>

### As políticas de conformidade do Intune não são mostradas no novo console
<a id="compliance-policies-from-intune-do-not-show-up-in-new-console" class="xliff"></a>

As políticas de conformidade criadas no portal clássico são migradas, mas não são exibidas no portal do Azure, devido às alterações de design no portal do Azure. As políticas de conformidade criadas no portal clássico do Intune ainda são impostas, mas devem ser exibidas e editadas no portal clássico do Intune.
Além disso, novas políticas de conformidade criadas no portal do Azure não estão visíveis no portal clássico do Intune.

Para saber mais, veja [O que é a conformidade do dispositivo](device-compliance.md).
>>>>>>> live

<!-- ## Enrollment -->


<!-- ## Data protection -->


## Administração e contas
<a id="administration-and-accounts" class="xliff"></a>

Administradores Globais (também conhecidos como Administradores de Locatários) podem continuar realizando tarefas de administração diárias sem uma licença separada do Intune ou do EMS (Enterprise Mobility Suite). No entanto, para usar o serviço, como registrar seus próprios dispositivos, um dispositivo corporativo ou usar o Portal da Empresa do Intune, eles precisam de uma licença do Intune ou do EMS.

<!-- ## Additional items -->












 
