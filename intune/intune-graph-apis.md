---
title: Como usar o Azure AD para acessar a API do Graph no Intune
description: "Descreve as etapas necessárias para que os aplicativos usem o Azure AD para acessar a API do Graph no Intune"
keywords: "funções de permissão PowerShell C# Intune API do Graph"
author: lleonard-msft
manager: angrobe
ms.author: alleonar
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4ff36855e7a20aa7696444416d8993f9be62cbe5
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="41a4b-104">Como usar o Azure AD para acessar a API do Graph no Intune</span><span class="sxs-lookup"><span data-stu-id="41a4b-104">How to use Azure AD to access the Intune Graph API</span></span>
<a id="how-to-use-azure-ad-to-access-the-intune-graph-api" class="xliff"></a>

<span data-ttu-id="41a4b-105">A [API do Microsoft Graph](https://developer.microsoft.com/graph/) agora dá suporte ao Microsoft Intune com APIs e funções de permissão específicas.</span><span class="sxs-lookup"><span data-stu-id="41a4b-105">The [Microsoft Graph API](https://developer.microsoft.com/graph/) now supports Microsoft Intune with specific APIs and permission roles.</span></span>  <span data-ttu-id="41a4b-106">A API do Graph usa o Azure AD (Azure Active Directory) para autenticação e controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="41a4b-106">The Graph API uses Azure Active Directory (Azure AD) for authentication and access control.</span></span>  
<span data-ttu-id="41a4b-107">O acesso à API do Graph no Intune exige:</span><span class="sxs-lookup"><span data-stu-id="41a4b-107">Access to the Intune Graph API requires:</span></span>

- <span data-ttu-id="41a4b-108">Uma ID de aplicativo com:</span><span class="sxs-lookup"><span data-stu-id="41a4b-108">An application ID with:</span></span>

    - <span data-ttu-id="41a4b-109">Permissão para chamar o Azure AD e as APIs do Graph.</span><span class="sxs-lookup"><span data-stu-id="41a4b-109">Permission to call Azure AD and Graph APIs.</span></span>
    - <span data-ttu-id="41a4b-110">Escopos de permissões relevantes para as tarefas de aplicativo específicas.</span><span class="sxs-lookup"><span data-stu-id="41a4b-110">Permission scopes relevant to the specific application tasks.</span></span>

- <span data-ttu-id="41a4b-111">Credenciais do usuário com:</span><span class="sxs-lookup"><span data-stu-id="41a4b-111">User credentials with:</span></span>

    - <span data-ttu-id="41a4b-112">Permissão para acessar o locatário do Azure AD associado ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a4b-112">Permission to access the Azure AD tenant associated with the application.</span></span>
    - <span data-ttu-id="41a4b-113">Permissões de função necessárias para dar suporte aos escopos de permissões do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a4b-113">Role permissions required to support the application permission scopes.</span></span>

- <span data-ttu-id="41a4b-114">O usuário final para conceder permissão ao aplicativo para executar tarefas de aplicativos para seu locatário do Azure.</span><span class="sxs-lookup"><span data-stu-id="41a4b-114">The end user to grant permission to the app to perform applications tasks for their Azure tenant.</span></span>

<span data-ttu-id="41a4b-115">Este artigo:</span><span class="sxs-lookup"><span data-stu-id="41a4b-115">This article:</span></span>

- <span data-ttu-id="41a4b-116">Mostra como registrar um aplicativo com acesso à API do Graph e a funções de permissão relevantes.</span><span class="sxs-lookup"><span data-stu-id="41a4b-116">Shows how to register an application with access to the Graph API and relevant permission roles.</span></span>

- <span data-ttu-id="41a4b-117">Descreve as funções de permissão da API do Graph no Intune.</span><span class="sxs-lookup"><span data-stu-id="41a4b-117">Describes the Intune Graph API permission roles.</span></span>

- <span data-ttu-id="41a4b-118">Fornece exemplos de autenticação da API do Graph no Intune para C# e PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41a4b-118">Provides Intune Graph API authentication examples for C# and PowerShell.</span></span>

- <span data-ttu-id="41a4b-119">Descreve como dar suporte a vários locatários</span><span class="sxs-lookup"><span data-stu-id="41a4b-119">Describes how to support multiple tenants</span></span>

<span data-ttu-id="41a4b-120">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="41a4b-120">To learn more, see:</span></span>

- [<span data-ttu-id="41a4b-121">Autorizar o acesso a aplicativos Web usando o OAuth 2.0 e o Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="41a4b-121">Authorize access to web applications using OAuth 2.0 and Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [<span data-ttu-id="41a4b-122">Introdução à autenticação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="41a4b-122">Getting start with Azure AD authentication</span></span>](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [<span data-ttu-id="41a4b-123">Integrando aplicativos ao Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="41a4b-123">Integrating applications with Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [<span data-ttu-id="41a4b-124">Entender o OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="41a4b-124">Understand OAuth 2.0</span></span>](https://oauth.net/2/)

## <span data-ttu-id="41a4b-125">Registrar aplicativos para usar a API do Graph</span><span class="sxs-lookup"><span data-stu-id="41a4b-125">Register apps to use Graph API</span></span>
<a id="register-apps-to-use-graph-api" class="xliff"></a>

<span data-ttu-id="41a4b-126">Para registrar um aplicativo para usar a API do Graph:</span><span class="sxs-lookup"><span data-stu-id="41a4b-126">To register an app to use Graph API:</span></span>

1.  <span data-ttu-id="41a4b-127">Entre no [portal do Azure](https://portal.azure.com) usando credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="41a4b-127">Sign into [the Azure portal](https://portal.azure.com) using administrative credentials.</span></span>

    <span data-ttu-id="41a4b-128">Conforme apropriado, você poderá usar:</span><span class="sxs-lookup"><span data-stu-id="41a4b-128">As appropriate, you may use:</span></span>
    - <span data-ttu-id="41a4b-129">A conta do administrador de locatários.</span><span class="sxs-lookup"><span data-stu-id="41a4b-129">The tenant admin account.</span></span>
    - <span data-ttu-id="41a4b-130">Uma conta de usuário do locatário com a configuração **Os usuários podem registrar aplicativos** habilitada.</span><span class="sxs-lookup"><span data-stu-id="41a4b-130">A tenant user account with the **Users can register applications** setting enabled.</span></span>

2.  <span data-ttu-id="41a4b-131">No menu, escolha **Azure Active Directory** &gt; **Registros do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-131">From the menu, choose **Azure Active Directory** &gt; **App Registrations**.</span></span>

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  <span data-ttu-id="41a4b-132">Escolha **Novo registro de aplicativo** para criar um novo aplicativo ou escolha um aplicativo existente.</span><span class="sxs-lookup"><span data-stu-id="41a4b-132">Either choose **New application registration** to create a new application or choose an existing application.</span></span>  <span data-ttu-id="41a4b-133">(Se você escolher um aplicativo existente, pule a próxima etapa).</span><span class="sxs-lookup"><span data-stu-id="41a4b-133">(If you choose an existing application, skip the next step.)</span></span>

4.  <span data-ttu-id="41a4b-134">Na folha **Criar**, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="41a4b-134">On the **Create** blade, specify the following:</span></span>

    1.  <span data-ttu-id="41a4b-135">Um **Nome** para o aplicativo (exibido quando os usuários entram).</span><span class="sxs-lookup"><span data-stu-id="41a4b-135">A **Name** for the application (displayed when users sign in).</span></span>

    2.  <span data-ttu-id="41a4b-136">Os valores de **Tipo de aplicativo** e **URI de Redirecionamento**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-136">The **Application type** and **Redirect URI** values.</span></span>

        <span data-ttu-id="41a4b-137">Eles variam de acordo com suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="41a4b-137">These vary according to your requirements.</span></span> <span data-ttu-id="41a4b-138">Por exemplo, se você estiver usando uma [ADAL](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (Biblioteca de Autenticação) do Azure AD, defina **Tipo de aplicativo** como `Native` e **URI de Redirecionamento** como `urn:ietf:wg:oauth:2.0:oob`.</span><span class="sxs-lookup"><span data-stu-id="41a4b-138">For example, if you're using an Azure AD [Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL), set **Application Type** to `Native` and **Redirect URI** to `urn:ietf:wg:oauth:2.0:oob`.</span></span>

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        <span data-ttu-id="41a4b-139">Para saber mais, consulte [Cenários de autenticação do Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span><span class="sxs-lookup"><span data-stu-id="41a4b-139">To learn more, see [Authentication Scenarios for Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span></span>

5.  <span data-ttu-id="41a4b-140">Na folha do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="41a4b-140">From the application blade:</span></span>

    1.  <span data-ttu-id="41a4b-141">Anote o valor de **ID do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-141">Note the **Application ID** value.</span></span>

    2.  <span data-ttu-id="41a4b-142">Escolha **Configurações** &gt; **Acesso à API** &gt; **Permissões Necessárias**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-142">Choose **Settings** &gt; **API access** &gt; **Required permissions**.</span></span>

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  <span data-ttu-id="41a4b-143">Na folha **Permissões Necessárias**, escolha **Adicionar** &gt; **Adicionar acesso à API** &gt; **Selecionar uma API**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-143">From the **Required Permissions** blade, choose **Add** &gt; **Add API access** &gt; **Select an API**.</span></span>

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  <span data-ttu-id="41a4b-144">Na folha **Selecionar uma API**, escolha **Microsoft Graph** &gt; **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-144">From the **Select an API** blade, choose **Microsoft Graph** &gt; **Select**.</span></span>  <span data-ttu-id="41a4b-145">A folha **Habilitar acesso** é aberta e lista os escopos de permissões disponíveis para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a4b-145">The **Enable access** blade opens and lists permission scopes available to your application.</span></span>

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    <span data-ttu-id="41a4b-146">Escolha as funções necessárias para o aplicativo colocando uma marca de seleção à esquerda dos nomes de relevantes.</span><span class="sxs-lookup"><span data-stu-id="41a4b-146">Choose the roles required for your app by placing a checkmark to the left of the relevant names.</span></span>  <span data-ttu-id="41a4b-147">Para saber mais sobre escopos de permissões específicos do Intune, consulte [Escopos de permissões do Intune](#user-content-intune-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="41a4b-147">To learn about specific Intune permission scopes, see [Intune permission scopes](#user-content-intune-permission-scopes).</span></span>  <span data-ttu-id="41a4b-148">Para saber mais sobre outros escopos de permissões da API do Graph, consulte [Referência de permissões do Microsoft Graph](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="41a4b-148">To learn about other Graph API permission scopes, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>

    <span data-ttu-id="41a4b-149">Para obter melhores resultados, escolha o menor número de funções necessárias para implementar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="41a4b-149">For best results, choose the fewest roles needed to implement your application.</span></span>

    <span data-ttu-id="41a4b-150">Quando terminar, escolha **Selecionar** e **Concluído** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="41a4b-150">When finished, choose **Select** and **Done** to save you changes.</span></span>

<span data-ttu-id="41a4b-151">Neste ponto, você também poderá:</span><span class="sxs-lookup"><span data-stu-id="41a4b-151">At this point, you may also:</span></span>

- <span data-ttu-id="41a4b-152">Optar por conceder permissão para todas as contas de locatário para usar o aplicativo sem fornecer credenciais.</span><span class="sxs-lookup"><span data-stu-id="41a4b-152">Choose to grant permission for all tenant accounts to use the app without providing credentials.</span></span>  

    <span data-ttu-id="41a4b-153">Para fazer isso, escolha **Conceder permissões** e aceite o prompt de confirmação.</span><span class="sxs-lookup"><span data-stu-id="41a4b-153">To do so, choose **Grant permissions** and accept the confirmation prompt.</span></span>

    <span data-ttu-id="41a4b-154">Ao executar o aplicativo pela primeira vez, você deverá conceder a permissão de aplicativo para executar as funções selecionadas.</span><span class="sxs-lookup"><span data-stu-id="41a4b-154">When you run the application for the first time, you're prompted to grant the app permission to perform the selected roles.</span></span>

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- <span data-ttu-id="41a4b-155">Disponibilize o aplicativo para usuários que estão fora do locatário.</span><span class="sxs-lookup"><span data-stu-id="41a4b-155">Make the app available to users outside your tenant.</span></span>  <span data-ttu-id="41a4b-156">(Normalmente, isso é necessário apenas para parceiros que dão suporte a vários locatários e organizações.)</span><span class="sxs-lookup"><span data-stu-id="41a4b-156">(This is typically only required for partners supporting multiple tenants/organizations.)</span></span>  

    <span data-ttu-id="41a4b-157">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="41a4b-157">To do so:</span></span>

    1. <span data-ttu-id="41a4b-158">Escolha **Manifesto** na folha do aplicativo, que abrirá a folha **Editar Manifesto**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-158">Choose **Manifest** from the application blade, which opens the **Edit Manifest** blade.</span></span>

    <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

    2. <span data-ttu-id="41a4b-159">Altere o valor da configuração `availableToOtherTenants` para `true`.</span><span class="sxs-lookup"><span data-stu-id="41a4b-159">Change the value of the `availableToOtherTenants` setting to `true`.</span></span>

    3. <span data-ttu-id="41a4b-160">Salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="41a4b-160">Save your changes.</span></span>

## <span data-ttu-id="41a4b-161">Escopos de permissões do Intune</span><span class="sxs-lookup"><span data-stu-id="41a4b-161">Intune permission scopes</span></span>
<a id="intune-permission-scopes" class="xliff"></a>

<span data-ttu-id="41a4b-162">O Azure AD e a API do Graph usam escopos de permissões para controlar o acesso a recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="41a4b-162">Azure AD and the Graph API use permission scopes to control access to corporate resources.</span></span>  

<span data-ttu-id="41a4b-163">Os escopos de permissões (também chamados de _escopos do OAuth_) controlam o acesso a entidades específicas do Intune e suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="41a4b-163">Permission scopes (also called the _OAuth scopes_) control access to specific Intune entities and their properties.</span></span> <span data-ttu-id="41a4b-164">Esta seção resume os escopos de permissões para os recursos da API do Graph no Intune.</span><span class="sxs-lookup"><span data-stu-id="41a4b-164">This section summarizes the permission scopes for Intune Graph API features.</span></span>

<span data-ttu-id="41a4b-165">Para saber mais:</span><span class="sxs-lookup"><span data-stu-id="41a4b-165">To learn more:</span></span>
- [<span data-ttu-id="41a4b-166">Autenticação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="41a4b-166">Azure AD authentication</span></span>](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [<span data-ttu-id="41a4b-167">Escopos de permissões de aplicativo</span><span class="sxs-lookup"><span data-stu-id="41a4b-167">Application permission scopes</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

<span data-ttu-id="41a4b-168">Ao conceder permissão para a API do Graph, você pode especificar os seguintes escopos para controlar o acesso aos recursos do Intune: a tabela a seguir resume os escopos de permissões da API do Graph no Intune.</span><span class="sxs-lookup"><span data-stu-id="41a4b-168">When you grant permission to the Graph API, you can specify the following scopes to control access to Intune features: The following table summarizes the Intune Graph API permission scopes.</span></span>  <span data-ttu-id="41a4b-169">A primeira coluna mostra o nome do recurso, conforme exibido no portal do Azure e a segunda coluna fornece o nome do escopo de permissão.</span><span class="sxs-lookup"><span data-stu-id="41a4b-169">The first column shows the name of the feature as displayed in the Azure portal and the second column provides the permission scope name.</span></span>

<span data-ttu-id="41a4b-170">Configuração _Habilitar o Acesso_</span><span class="sxs-lookup"><span data-stu-id="41a4b-170">_Enable Access_ setting</span></span> | <span data-ttu-id="41a4b-171">Nome do escopo</span><span class="sxs-lookup"><span data-stu-id="41a4b-171">Scope name</span></span>
:--|:--
<span data-ttu-id="41a4b-172">__Executar ações remotas que afetam o usuário em dispositivos Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-172">__Perform user-impacting remote actions on Microsoft Intune devices__</span></span> | [<span data-ttu-id="41a4b-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>](#user-content-mgd-po)
<span data-ttu-id="41a4b-174">__Ler e gravar dispositivos Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-174">__Read and write Microsoft Intune devices__</span></span> | [<span data-ttu-id="41a4b-175">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-175">DeviceManagementManagedDevices.ReadWrite.All</span></span>](#mgd-rw)
<span data-ttu-id="41a4b-176">__Ler dispositivos Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-176">__Read Microsoft Intune devices__</span></span> | [<span data-ttu-id="41a4b-177">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-177">DeviceManagementManagedDevices.Read.All</span></span>](#mgd-ro)
<span data-ttu-id="41a4b-178">__Ler e gravar configurações de RBAC do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-178">__Read and write Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="41a4b-179">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-179">DeviceManagementRBAC.ReadWrite.All</span></span>](#rac-rw)
<span data-ttu-id="41a4b-180">__Ler configurações de RBAC do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-180">__Read Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="41a4b-181">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-181">DeviceManagementRBAC.Read.All</span></span>](#rac=ro)
<span data-ttu-id="41a4b-182">__Ler e gravar em aplicativos do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-182">__Read and write Microsoft Intune apps__</span></span> | [<span data-ttu-id="41a4b-183">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-183">DeviceManagementApps.ReadWrite.All</span></span>](#app-rw)
<span data-ttu-id="41a4b-184">__Ler aplicativos do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-184">__Read Microsoft Intune apps__</span></span> | [<span data-ttu-id="41a4b-185">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-185">DeviceManagementApps.Read.All</span></span>](#app-ro)
<span data-ttu-id="41a4b-186">__Ler e gravar as Políticas e a Configuração de Dispositivo do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-186">__Read and write Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="41a4b-187">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-187">DeviceManagementConfiguration.ReadWrite.All</span></span>](#cfg-rw)
<span data-ttu-id="41a4b-188">__Ler as Políticas e a Configuração de Dispositivo do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-188">__Read Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="41a4b-189">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-189">DeviceManagementConfiguration.Read.All</span></span>](#cfg-ro)
<span data-ttu-id="41a4b-190">__Ler e gravar a configuração do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-190">__Read and write Microsoft Intune configuration__</span></span> | [<span data-ttu-id="41a4b-191">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-191">DeviceManagementServiceConfig.ReadWrite.All</span></span>](#svc-rw)
<span data-ttu-id="41a4b-192">__Ler a configuração do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-192">__Read Microsoft Intune configuration__</span></span> | [<span data-ttu-id="41a4b-193">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-193">DeviceManagementServiceConfig.Read.All</span></span>](#svc-ra)

<span data-ttu-id="41a4b-194">A tabela lista as configurações na ordem em que são exibidas no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="41a4b-194">The table lists the settings as they appear in the Azure portal.</span></span> <span data-ttu-id="41a4b-195">As próximas seções descrevem os escopos em ordem alfabética.</span><span class="sxs-lookup"><span data-stu-id="41a4b-195">The following sections describe the scopes in alphabetical order.</span></span>

<span data-ttu-id="41a4b-196">No momento, todos os escopos de permissões do Intune exigem o acesso de administrador.</span><span class="sxs-lookup"><span data-stu-id="41a4b-196">At this time, all Intune permission scopes require administrator access.</span></span>  <span data-ttu-id="41a4b-197">Isso significa que você precisa ter credenciais correspondentes ao executar aplicativos ou scripts que acessam os recursos da API do Graph no Intune.</span><span class="sxs-lookup"><span data-stu-id="41a4b-197">This means you need corresponding credentials when running apps or scripts that access Intune Graph API resources.</span></span>

### <span data-ttu-id="41a4b-198"><a name="app-ro"></a>DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-198"><a name="app-ro"></a>DeviceManagementApps.Read.All</span></span>

- <span data-ttu-id="41a4b-199">Configuração **Habilitar o Acesso**: __Ler aplicativos do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-199">**Enable Access** setting: __Read Microsoft Intune apps__</span></span>

- <span data-ttu-id="41a4b-200">Permite o acesso de leitura às seguintes propriedades e status de entidade:</span><span class="sxs-lookup"><span data-stu-id="41a4b-200">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="41a4b-201">Aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="41a4b-201">Mobile Apps</span></span>
    - <span data-ttu-id="41a4b-202">Categorias de aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="41a4b-202">Mobile App Categories</span></span>
    - <span data-ttu-id="41a4b-203">Políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="41a4b-203">App Protection Policies</span></span>
    - <span data-ttu-id="41a4b-204">Configurações de aplicativo</span><span class="sxs-lookup"><span data-stu-id="41a4b-204">App Configurations</span></span>

### <span data-ttu-id="41a4b-205"><a name="app-rw"></a>DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-205"><a name="app-rw"></a>DeviceManagementApps.ReadWrite.All</span></span>

- <span data-ttu-id="41a4b-206">Configuração **Habilitar o Acesso**: __Ler e gravar aplicativos do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-206">**Enable Access** setting: __Read and write Microsoft Intune apps__</span></span>

- <span data-ttu-id="41a4b-207">Permite as mesmas operações de __DeviceManagementApps.Read.All__</span><span class="sxs-lookup"><span data-stu-id="41a4b-207">Allows the same operations as __DeviceManagementApps.Read.All__</span></span>

- <span data-ttu-id="41a4b-208">Também permite alterações às seguintes entidades:</span><span class="sxs-lookup"><span data-stu-id="41a4b-208">Also permits changes to the following entities:</span></span>

    - <span data-ttu-id="41a4b-209">Aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="41a4b-209">Mobile Apps</span></span>
    - <span data-ttu-id="41a4b-210">Categorias de aplicativos móveis</span><span class="sxs-lookup"><span data-stu-id="41a4b-210">Mobile App Categories</span></span>
    - <span data-ttu-id="41a4b-211">Políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="41a4b-211">App Protection Policies</span></span>
    - <span data-ttu-id="41a4b-212">Configurações de aplicativo</span><span class="sxs-lookup"><span data-stu-id="41a4b-212">App Configurations</span></span>

### <span data-ttu-id="41a4b-213"><a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-213"><a name="cfg-ro"></a>DeviceManagementConfiguration.Read.All</span></span>

- <span data-ttu-id="41a4b-214">Configuração **Habilitar o Acesso**: __Ler as políticas e a configuração de dispositivo do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-214">**Enable Access** setting: __Read Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="41a4b-215">Permite o acesso de leitura às seguintes propriedades e status de entidade:</span><span class="sxs-lookup"><span data-stu-id="41a4b-215">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="41a4b-216">Configuração de dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-216">Device Configuration</span></span>
    - <span data-ttu-id="41a4b-217">Política de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-217">Device Compliance Policy</span></span>
    - <span data-ttu-id="41a4b-218">Mensagens de notificação</span><span class="sxs-lookup"><span data-stu-id="41a4b-218">Notification Messages</span></span>

### <span data-ttu-id="41a4b-219"><a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-219"><a name="cfg-ra"></a>DeviceManagementConfiguration.ReadWrite.All</span></span>

- <span data-ttu-id="41a4b-220">Configuração **Habilitar o Acesso**: __Ler e gravar as políticas e a configuração de dispositivo do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-220">**Enable Access** setting: __Read and write Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="41a4b-221">Permite as mesmas operações de __DeviceManagementConfiguration.Read.All__</span><span class="sxs-lookup"><span data-stu-id="41a4b-221">Allows the same operations as __DeviceManagementConfiguration.Read.All__</span></span>

- <span data-ttu-id="41a4b-222">Os aplicativos também podem criar, atribuir, excluir e alterar as seguintes entidades:</span><span class="sxs-lookup"><span data-stu-id="41a4b-222">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="41a4b-223">Configuração de dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-223">Device Configuration</span></span>
    - <span data-ttu-id="41a4b-224">Política de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-224">Device Compliance Policy</span></span>
    - <span data-ttu-id="41a4b-225">Mensagens de notificação</span><span class="sxs-lookup"><span data-stu-id="41a4b-225">Notification Messages</span></span>

### <span data-ttu-id="41a4b-226"><a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-226"><a name="mgd-po"></a>DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>

- <span data-ttu-id="41a4b-227">Configuração **Habilitar o Acesso**: __Executar ações remotas que afetam o usuário em dispositivos Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-227">**Enable Access** setting: __Perform user-impacting remote actions on Microsoft Intune devices__</span></span>

- <span data-ttu-id="41a4b-228">Permite as seguintes ações remotas em um dispositivo gerenciado:</span><span class="sxs-lookup"><span data-stu-id="41a4b-228">Permits the following remote actions on a managed device:</span></span>
    - <span data-ttu-id="41a4b-229">Desativar</span><span class="sxs-lookup"><span data-stu-id="41a4b-229">Retire</span></span>
    - <span data-ttu-id="41a4b-230">Apagamento</span><span class="sxs-lookup"><span data-stu-id="41a4b-230">Wipe</span></span>
    - <span data-ttu-id="41a4b-231">Redefinir/Recuperar Senha</span><span class="sxs-lookup"><span data-stu-id="41a4b-231">Reset/Recover Passcode</span></span>
    - <span data-ttu-id="41a4b-232">Bloqueio remoto</span><span class="sxs-lookup"><span data-stu-id="41a4b-232">Remote Lock</span></span>
    - <span data-ttu-id="41a4b-233">Habilitar/Desabilitar Modo Perdido</span><span class="sxs-lookup"><span data-stu-id="41a4b-233">Enable/Disable Lost Mode</span></span>
    - <span data-ttu-id="41a4b-234">Limpar Computador</span><span class="sxs-lookup"><span data-stu-id="41a4b-234">Clean PC</span></span>
    - <span data-ttu-id="41a4b-235">Reinicialização</span><span class="sxs-lookup"><span data-stu-id="41a4b-235">Reboot</span></span>
    - <span data-ttu-id="41a4b-236">Excluir Usuário do Dispositivo Compartilhado</span><span class="sxs-lookup"><span data-stu-id="41a4b-236">Delete User from Shared Device</span></span>

### <span data-ttu-id="41a4b-237"><a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-237"><a name="mgd-ro"></a>DeviceManagementManagedDevices.Read.All</span></span>

- <span data-ttu-id="41a4b-238">Configuração **Habilitar o Acesso**: __Ler dispositivos Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-238">**Enable Access** setting: __Read Microsoft Intune devices__</span></span>

- <span data-ttu-id="41a4b-239">Permite o acesso de leitura às seguintes propriedades e status de entidade:</span><span class="sxs-lookup"><span data-stu-id="41a4b-239">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="41a4b-240">Dispositivo gerenciado</span><span class="sxs-lookup"><span data-stu-id="41a4b-240">Managed Device</span></span>
    - <span data-ttu-id="41a4b-241">Categoria de dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-241">Device Category</span></span>
    - <span data-ttu-id="41a4b-242">Aplicativo detectado</span><span class="sxs-lookup"><span data-stu-id="41a4b-242">Detected App</span></span>
    - <span data-ttu-id="41a4b-243">Ações remotas</span><span class="sxs-lookup"><span data-stu-id="41a4b-243">Remote actions</span></span>
    - <span data-ttu-id="41a4b-244">Informações sobre malware</span><span class="sxs-lookup"><span data-stu-id="41a4b-244">Malware information</span></span>

### <span data-ttu-id="41a4b-245"><a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-245"><a name="mgd-rw"></a>DeviceManagementManagedDevices.ReadWrite.All</span></span>

- <span data-ttu-id="41a4b-246">Configuração **Habilitar o Acesso**: __Ler e gravar dispositivos Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-246">**Enable Access** setting: __Read and write Microsoft Intune devices__</span></span>

- <span data-ttu-id="41a4b-247">Permite as mesmas operações de __DeviceManagementManagedDevices.Read.All__</span><span class="sxs-lookup"><span data-stu-id="41a4b-247">Allows the same operations as __DeviceManagementManagedDevices.Read.All__</span></span>

- <span data-ttu-id="41a4b-248">Os aplicativos também podem criar, excluir e alterar as seguintes entidades:</span><span class="sxs-lookup"><span data-stu-id="41a4b-248">Apps can also create, delete, and change the following entities:</span></span>
    - <span data-ttu-id="41a4b-249">Dispositivo gerenciado</span><span class="sxs-lookup"><span data-stu-id="41a4b-249">Managed Device</span></span>
    - <span data-ttu-id="41a4b-250">Categoria de dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-250">Device Category</span></span>

- <span data-ttu-id="41a4b-251">As seguintes ações remotas também são permitidas:</span><span class="sxs-lookup"><span data-stu-id="41a4b-251">The following remote actions are also allowed:</span></span>
    - <span data-ttu-id="41a4b-252">Localizar dispositivos</span><span class="sxs-lookup"><span data-stu-id="41a4b-252">Locate devices</span></span>
    - <span data-ttu-id="41a4b-253">Ignorar bloqueio de ativação</span><span class="sxs-lookup"><span data-stu-id="41a4b-253">Bypass activation lock</span></span>
    - <span data-ttu-id="41a4b-254">Solicitar assistência remota</span><span class="sxs-lookup"><span data-stu-id="41a4b-254">Request remote assistance</span></span>

### <span data-ttu-id="41a4b-255"><a name="rac-ro"></a>DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-255"><a name="rac-ro"></a>DeviceManagementRBAC.Read.All</span></span>

- <span data-ttu-id="41a4b-256">Configuração **Habilitar o Acesso**: __Ler configurações de RBAC do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-256">**Enable Access** setting: __Read Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="41a4b-257">Permite o acesso de leitura às seguintes propriedades e status de entidade:</span><span class="sxs-lookup"><span data-stu-id="41a4b-257">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="41a4b-258">Atribuições de função</span><span class="sxs-lookup"><span data-stu-id="41a4b-258">Role Assignments</span></span>
    - <span data-ttu-id="41a4b-259">Definições de função</span><span class="sxs-lookup"><span data-stu-id="41a4b-259">Role Definitions</span></span>
    - <span data-ttu-id="41a4b-260">Operações de recursos</span><span class="sxs-lookup"><span data-stu-id="41a4b-260">Resource Operations</span></span>

### <span data-ttu-id="41a4b-261"><a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-261"><a name="rac-rw"></a>DeviceManagementRBAC.ReadWrite.All</span></span>

- <span data-ttu-id="41a4b-262">Configuração **Habilitar o Acesso**: __Ler e gravar configurações de RBAC do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-262">**Enable Access** setting: __Read and write Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="41a4b-263">Permite as mesmas operações de __DeviceManagementRBAC.Read.All__</span><span class="sxs-lookup"><span data-stu-id="41a4b-263">Allows the same operations as __DeviceManagementRBAC.Read.All__</span></span>

- <span data-ttu-id="41a4b-264">Os aplicativos também podem criar, atribuir, excluir e alterar as seguintes entidades:</span><span class="sxs-lookup"><span data-stu-id="41a4b-264">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="41a4b-265">Atribuições de função</span><span class="sxs-lookup"><span data-stu-id="41a4b-265">Role Assignments</span></span>
    - <span data-ttu-id="41a4b-266">Definições de função</span><span class="sxs-lookup"><span data-stu-id="41a4b-266">Role Definitions</span></span>

### <span data-ttu-id="41a4b-267"><a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-267"><a name="svc-ro"></a>DeviceManagementServiceConfig.Read.All</span></span>

- <span data-ttu-id="41a4b-268">Configuração **Habilitar o Acesso**: __Ler a configuração do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-268">**Enable Access** setting: __Read Microsoft Intune configuration__</span></span>

- <span data-ttu-id="41a4b-269">Permite o acesso de leitura às seguintes propriedades e status de entidade:</span><span class="sxs-lookup"><span data-stu-id="41a4b-269">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="41a4b-270">Registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-270">Device Enrollment</span></span>
    - <span data-ttu-id="41a4b-271">Certificado de Notificação por Push da Apple</span><span class="sxs-lookup"><span data-stu-id="41a4b-271">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="41a4b-272">Programa de Registro do Dispositivo da Apple</span><span class="sxs-lookup"><span data-stu-id="41a4b-272">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="41a4b-273">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="41a4b-273">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="41a4b-274">Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="41a4b-274">Exchange Connector</span></span>
    - <span data-ttu-id="41a4b-275">Termos e condições</span><span class="sxs-lookup"><span data-stu-id="41a4b-275">Terms and Conditions</span></span>
    - <span data-ttu-id="41a4b-276">Gerenciamento de Despesas de Telecomunicações</span><span class="sxs-lookup"><span data-stu-id="41a4b-276">Telecoms Expense Management</span></span>
    - <span data-ttu-id="41a4b-277">PKI de Nuvem</span><span class="sxs-lookup"><span data-stu-id="41a4b-277">Cloud PKI</span></span>
    - <span data-ttu-id="41a4b-278">Identidade Visual</span><span class="sxs-lookup"><span data-stu-id="41a4b-278">Branding</span></span>
    - <span data-ttu-id="41a4b-279">Defesa contra Ameaças Móveis</span><span class="sxs-lookup"><span data-stu-id="41a4b-279">Mobile Threat Defense</span></span>

### <span data-ttu-id="41a4b-280"><a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="41a4b-280"><a name="svc-rw"></a>DeviceManagementServiceConfig.ReadWrite.All</span></span>

- <span data-ttu-id="41a4b-281">Configuração **Habilitar o Acesso**: __Ler e gravar a configuração do Microsoft Intune__</span><span class="sxs-lookup"><span data-stu-id="41a4b-281">**Enable Access** setting: __Read and write Microsoft Intune configuration__</span></span>

- <span data-ttu-id="41a4b-282">Permite as mesmas operações que DeviceManagementServiceConfig.Read.All_</span><span class="sxs-lookup"><span data-stu-id="41a4b-282">Allows the same operations as DeviceManagementServiceConfig.Read.All_</span></span>

- <span data-ttu-id="41a4b-283">Os aplicativos também podem configurar os seguintes recursos do Intune:</span><span class="sxs-lookup"><span data-stu-id="41a4b-283">Apps can also configure the following Intune features:</span></span>
    - <span data-ttu-id="41a4b-284">Registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="41a4b-284">Device Enrollment</span></span>
    - <span data-ttu-id="41a4b-285">Certificado de Notificação por Push da Apple</span><span class="sxs-lookup"><span data-stu-id="41a4b-285">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="41a4b-286">Programa de Registro do Dispositivo da Apple</span><span class="sxs-lookup"><span data-stu-id="41a4b-286">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="41a4b-287">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="41a4b-287">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="41a4b-288">Exchange Connector</span><span class="sxs-lookup"><span data-stu-id="41a4b-288">Exchange Connector</span></span>
    - <span data-ttu-id="41a4b-289">Termos e condições</span><span class="sxs-lookup"><span data-stu-id="41a4b-289">Terms and Conditions</span></span>
    - <span data-ttu-id="41a4b-290">Gerenciamento de Despesas de Telecomunicações</span><span class="sxs-lookup"><span data-stu-id="41a4b-290">Telecoms Expense Management</span></span>
    - <span data-ttu-id="41a4b-291">PKI de Nuvem</span><span class="sxs-lookup"><span data-stu-id="41a4b-291">Cloud PKI</span></span>
    - <span data-ttu-id="41a4b-292">Identidade Visual</span><span class="sxs-lookup"><span data-stu-id="41a4b-292">Branding</span></span>
    - <span data-ttu-id="41a4b-293">Defesa contra Ameaças Móveis</span><span class="sxs-lookup"><span data-stu-id="41a4b-293">Mobile Threat Defense</span></span>

## <span data-ttu-id="41a4b-294">Exemplos de autenticação do Azure AD</span><span class="sxs-lookup"><span data-stu-id="41a4b-294">Azure AD authentication examples</span></span>
<a id="azure-ad-authentication-examples" class="xliff"></a>

<span data-ttu-id="41a4b-295">Esta seção mostra como incorporar o Azure AD em seus projetos do C# e PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41a4b-295">This section shows how to incorporate Azure AD into your C# and PowerShell projects.</span></span>

<span data-ttu-id="41a4b-296">Em cada exemplo, você precisará especificar uma ID de aplicativo que tem, pelo menos, o escopo de permissão `DeviceManagementManagedDevices.Read.All` (abordado anteriormente).</span><span class="sxs-lookup"><span data-stu-id="41a4b-296">In each example, you'll need to specify an application ID that has at least the `DeviceManagementManagedDevices.Read.All` permission scope (discussed earlier).</span></span>

<span data-ttu-id="41a4b-297">Ao testar um dos exemplos, você poderá receber erros de status HTTP 403 (Proibido) semelhantes ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="41a4b-297">When testing either example, you may receive HTTP status 403 (Forbidden) errors similar to the following:</span></span>

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

<span data-ttu-id="41a4b-298">Se isso acontecer, verifique se:</span><span class="sxs-lookup"><span data-stu-id="41a4b-298">If this happens, verify that:</span></span>

- <span data-ttu-id="41a4b-299">Você atualizou a ID do aplicativo para uma autorizada a usar a API do Graph e o escopo de permissão `DeviceManagementManagedDevices.Read.All`.</span><span class="sxs-lookup"><span data-stu-id="41a4b-299">You've updated the application ID to one authorized to use the Graph API and the `DeviceManagementManagedDevices.Read.All` permission scope.</span></span>

- <span data-ttu-id="41a4b-300">Suas credenciais de locatário dão suporte a funções administrativas.</span><span class="sxs-lookup"><span data-stu-id="41a4b-300">Your tenant credentials support administrative functions.</span></span>

- <span data-ttu-id="41a4b-301">O código é semelhante às amostras exibidas.</span><span class="sxs-lookup"><span data-stu-id="41a4b-301">Your code is similar to the displayed samples.</span></span>


### <span data-ttu-id="41a4b-302">Autenticar o Azure AD no C\#</span><span class="sxs-lookup"><span data-stu-id="41a4b-302">Authenticate Azure AD in C\#</span></span>
<a id="authenticate-azure-ad-in-c" class="xliff"></a>

<span data-ttu-id="41a4b-303">Este exemplo mostra como usar o C# para recuperar uma lista de dispositivos associados à sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="41a4b-303">This example shows how to use C# to retrieve a list of devices associated with your Intune account.</span></span>

1.  <span data-ttu-id="41a4b-304">Inicie o Visual Studio e, em seguida, crie um novo projeto de aplicativo (.NET Framework) do Console do Visual C#.</span><span class="sxs-lookup"><span data-stu-id="41a4b-304">Start Visual Studio and then create a new Visual C# Console app (.NET Framework) project.</span></span>

2.  <span data-ttu-id="41a4b-305">Insira um nome para o projeto e forneça outros detalhes, conforme desejado.</span><span class="sxs-lookup"><span data-stu-id="41a4b-305">Enter a name for your project and provide other details as desired.</span></span>

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  <span data-ttu-id="41a4b-306">Use o Gerenciador de Soluções para adicionar o pacote NuGet da ADAL da Microsoft ao projeto.</span><span class="sxs-lookup"><span data-stu-id="41a4b-306">Use the Solution Explorer to add the Microsoft ADAL NuGet package to the project.</span></span>

    1.  <span data-ttu-id="41a4b-307">Clique com o botão direito do mouse em Gerenciador de Soluções.</span><span class="sxs-lookup"><span data-stu-id="41a4b-307">Right-click the Solution Explorer.</span></span>
    2.  <span data-ttu-id="41a4b-308">Escolha **Gerenciar Pacotes NuGet…**</span><span class="sxs-lookup"><span data-stu-id="41a4b-308">Choose **Manage NuGet Packages…**</span></span> <span data-ttu-id="41a4b-309">&gt; **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-309">&gt; **Browse**.</span></span>
    3.  <span data-ttu-id="41a4b-310">Selecione `Microsoft.IdentityModel.Clients.ActiveDirectory` e, em seguida, escolha **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-310">Select `Microsoft.IdentityModel.Clients.ActiveDirectory` and then choose **Install**.</span></span>

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  <span data-ttu-id="41a4b-311">Adicione as seguintes instruções ao início do **Program.cs**:</span><span class="sxs-lookup"><span data-stu-id="41a4b-311">Add the following statements to the top of **Program.cs**:</span></span>

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  <span data-ttu-id="41a4b-312">Adicione um método para criar o cabeçalho de autorização:</span><span class="sxs-lookup"><span data-stu-id="41a4b-312">Add a method to create the authorization header:</span></span>

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    <span data-ttu-id="41a4b-313">Lembre-se de alterar o valor de `application_ID` para que ele corresponda a um que recebeu, pelo menos, o escopo de permissão `DeviceManagementManagedDevices.Read.All`, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="41a4b-313">Remember to change the value of `application_ID` to match one granted at least the `DeviceManagementManagedDevices.Read.All` permission scope, as described earlier.</span></span>

6. <span data-ttu-id="41a4b-314">Adicione um método para recuperar a lista de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="41a4b-314">Add a method to retrieve the list of devices:</span></span>

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  <span data-ttu-id="41a4b-315">Atualize **Principal** para chamar **GetMyManagedDevices**:</span><span class="sxs-lookup"><span data-stu-id="41a4b-315">Update **Main** to call **GetMyManagedDevices**:</span></span>

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  <span data-ttu-id="41a4b-316">Compile e execute o programa.</span><span class="sxs-lookup"><span data-stu-id="41a4b-316">Compile and run your program.</span></span>  

<span data-ttu-id="41a4b-317">Ao executar o programa pela primeira vez, você deverá receber dois prompts.</span><span class="sxs-lookup"><span data-stu-id="41a4b-317">When you first run your program, you should receive two prompts.</span></span>  <span data-ttu-id="41a4b-318">O primeiro solicita suas credenciais e o segundo concede permissões para a solicitação `managedDevices`.</span><span class="sxs-lookup"><span data-stu-id="41a4b-318">The first requests your credentials and the second grants permissions for the `managedDevices` request.</span></span>  

<span data-ttu-id="41a4b-319">Para referência, este é o programa concluído:</span><span class="sxs-lookup"><span data-stu-id="41a4b-319">For reference, here's the completed program:</span></span>

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <span data-ttu-id="41a4b-320">Autenticar o Azure AD (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="41a4b-320">Authenticate Azure AD (PowerShell)</span></span>
<a id="authenticate-azure-ad-powershell" class="xliff"></a>

<span data-ttu-id="41a4b-321">O script do PowerShell a seguir usa o módulo Azure AD PowerShell para autenticação.</span><span class="sxs-lookup"><span data-stu-id="41a4b-321">The following PowerShell script uses the AzureAD PowerShell module for authentication.</span></span>  <span data-ttu-id="41a4b-322">Para saber mais, consulte [Azure Active Directory PowerShell Versão 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) e os [exemplos do Intune PowerShell](https://github.com/microsoftgraph/powershell-intune-samples).</span><span class="sxs-lookup"><span data-stu-id="41a4b-322">To learn more, see [Azure Active Directory PowerShell Version 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) and the [Intune PowerShell examples](https://github.com/microsoftgraph/powershell-intune-samples).</span></span>

<span data-ttu-id="41a4b-323">Neste exemplo, atualize o valor de `$clientID` para que ele corresponda a uma ID de aplicativo válida.</span><span class="sxs-lookup"><span data-stu-id="41a4b-323">In this example, update the value of `$clientID` to match a valid application ID.</span></span>

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <span data-ttu-id="41a4b-324">Dar suporte a vários locatários e parceiros</span><span class="sxs-lookup"><span data-stu-id="41a4b-324">Support multiple tenants and partners</span></span>
<a id="support-multiple-tenants-and-partners" class="xliff"></a>

<span data-ttu-id="41a4b-325">Caso sua organização dê suporte a organizações com seus próprios locatários do Azure AD, é recomendável permitir que os clientes usem seu aplicativo com os respectivos locatários deles.</span><span class="sxs-lookup"><span data-stu-id="41a4b-325">If your organization supports organizations with their own Azure AD tenants, you may want to permit your clients to use your application with their respective tenants.</span></span>

<span data-ttu-id="41a4b-326">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="41a4b-326">To do so:</span></span>

1.  <span data-ttu-id="41a4b-327">Verifique se a conta do cliente existe no locatário de destino do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="41a4b-327">Verify that the client account exists in the target Azure AD tenant.</span></span>

2.  <span data-ttu-id="41a4b-328">Verifique se sua conta de locatário permite aos usuários registrar aplicativos (consulte **Configurações do usuário**).</span><span class="sxs-lookup"><span data-stu-id="41a4b-328">Verify that your tenant account allows users to register applications (see **User settings**).</span></span>

3.  <span data-ttu-id="41a4b-329">Estabeleça uma relação entre cada locatário.</span><span class="sxs-lookup"><span data-stu-id="41a4b-329">Establish a relationship between each tenant.</span></span>  

    <span data-ttu-id="41a4b-330">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="41a4b-330">To do so, either:</span></span>

    <span data-ttu-id="41a4b-331">a.</span><span class="sxs-lookup"><span data-stu-id="41a4b-331">a.</span></span> <span data-ttu-id="41a4b-332">Use o [Microsoft Partner Center](https://partnercenter.microsoft.com/) para definir uma relação com o cliente e seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="41a4b-332">Use the [Microsoft Partner Center](https://partnercenter.microsoft.com/) to define a relationship with your client and their email address.</span></span>

    <span data-ttu-id="41a4b-333">b.</span><span class="sxs-lookup"><span data-stu-id="41a4b-333">b.</span></span> <span data-ttu-id="41a4b-334">Convide o usuário para se tornar um convidado de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="41a4b-334">Invite the user to become a guest of your tenant.</span></span>

<span data-ttu-id="41a4b-335">Para convidar o usuário para ser um convidado de seu locatário:</span><span class="sxs-lookup"><span data-stu-id="41a4b-335">To invite the user to be a guest of your tenant:</span></span>

1.  <span data-ttu-id="41a4b-336">Escolha **Adicionar um usuário convidado** no painel **Tarefas rápidas**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-336">Choose **Add a guest user** from the **Quick tasks** panel.</span></span>

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  <span data-ttu-id="41a4b-337">Insira o endereço de email do cliente e (opcionalmente) adicione uma mensagem personalizada ao convite.</span><span class="sxs-lookup"><span data-stu-id="41a4b-337">Enter the client's email address and (optionally) add a personalized message for the invite.</span></span>

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  <span data-ttu-id="41a4b-338">Escolha **Convidar**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-338">Choose **Invite**.</span></span>

<span data-ttu-id="41a4b-339">Isso envia um convite para o usuário.</span><span class="sxs-lookup"><span data-stu-id="41a4b-339">This sends an invite to the user.</span></span>

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   <span data-ttu-id="41a4b-340">O usuário precisa escolher o link **Introdução** para aceitar o convite.</span><span class="sxs-lookup"><span data-stu-id="41a4b-340">The user needs to choose the **Get Started** link to accept your invitation.</span></span>

<span data-ttu-id="41a4b-341">Quando a relação é estabelecida (ou seu convite foi aceito), adicione a conta de usuário à **Função do diretório**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-341">When the relationship is established (or your invitation has been accepted), add the user account to the **Directory role**.</span></span>

<span data-ttu-id="41a4b-342">Lembre-se de adicionar o usuário a outras funções, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="41a4b-342">Remember to add the user to other roles as needed.</span></span> <span data-ttu-id="41a4b-343">Por exemplo, para permitir que o usuário gerencie as configurações do Intune, ele precisa ser um **Administrador Global** ou um **Administrador de Serviços do Intune**.</span><span class="sxs-lookup"><span data-stu-id="41a4b-343">For example, to allow the user to manage Intune settings, they need to be either a **Global Administrator** or an **Intune Service administrator**.</span></span>

<span data-ttu-id="41a4b-344">Também:</span><span class="sxs-lookup"><span data-stu-id="41a4b-344">Also:</span></span>

- <span data-ttu-id="41a4b-345">Use http://portal.office.com para atribuir uma licença do Intune à sua conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="41a4b-345">Use http://portal.office.com to assign an Intune license to your user account.</span></span>

- <span data-ttu-id="41a4b-346">Atualize o código do aplicativo para autenticação no domínio de locatário do Azure AD do cliente, em vez de em seu próprio.</span><span class="sxs-lookup"><span data-stu-id="41a4b-346">Update application code to authenticate to the client's Azure AD tenant domain, rather than your own.</span></span>

    <span data-ttu-id="41a4b-347">Por exemplo, suponha que seu domínio de locatário seja `contosopartner.onmicrosoft.com` e que o domínio de locatário do cliente seja `northwind.onmicrosoft.com`. Assim, você deverá atualizar o código para autenticação no locatário do cliente.</span><span class="sxs-lookup"><span data-stu-id="41a4b-347">For example, suppose your tenant domain is `contosopartner.onmicrosoft.com` and your client's tenant domain is `northwind.onmicrosoft.com`, you would update your code to authenticate to your client's tenant.</span></span>

    <span data-ttu-id="41a4b-348">Para fazer isso em um aplicativo C# com base no exemplo anterior, altere o valor da variável `authority`:</span><span class="sxs-lookup"><span data-stu-id="41a4b-348">To do so in a C# application based on the earlier example, you'd change the value of the `authority` variable:</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    <span data-ttu-id="41a4b-349">como</span><span class="sxs-lookup"><span data-stu-id="41a4b-349">to</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
