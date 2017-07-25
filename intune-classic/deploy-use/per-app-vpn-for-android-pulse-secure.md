---
title: VPN por aplicativo para o Android usando o Pulse Secure
description: "Você pode criar um perfil de VPN por aplicativo para dispositivos Android gerenciados pelo Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 262cc461d5c1790fdfb162d5453a9cebd48271c4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f7635-103">Usar uma política personalizada para criar um perfil de VPN por aplicativo para dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="f7635-103">Use a custom policy to create a per-app VPN profile for Android devices</span></span>
<a id="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f7635-104">Você pode criar um perfil de VPN por aplicativo para dispositivos Android 5.0 e posterior gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="f7635-104">You can create a per-app VPN profile for Android 5.0 and later devices that are managed by Intune.</span></span> <span data-ttu-id="f7635-105">Primeiro, crie um perfil de VPN que use o tipo de conexão Pulse Secure ou Citrix.</span><span class="sxs-lookup"><span data-stu-id="f7635-105">First, create a VPN profile that uses the Pulse Secure or Citrix connection type.</span></span> <span data-ttu-id="f7635-106">Em seguida, crie uma política de configuração personalizada que associa o perfil de VPN com aplicativos específicos.</span><span class="sxs-lookup"><span data-stu-id="f7635-106">Then, create a custom configuration policy that associates the VPN profile with specific apps.</span></span> 

<span data-ttu-id="f7635-107">Após você implantar a política nos grupos de usuários ou no dispositivo Android, os usuários deverão iniciar o VPN do Pulse Secure ou Citrix.</span><span class="sxs-lookup"><span data-stu-id="f7635-107">After you deploy the policy to your Android device or user groups, users should start the Pulse Secure or Citrix VPN.</span></span> <span data-ttu-id="f7635-108">A conexão permitirá o tráfego apenas de aplicativos especificados para usar a conexão VPN aberta.</span><span class="sxs-lookup"><span data-stu-id="f7635-108">The connection will then allow traffic only from the specified apps to use the open VPN connection.</span></span>

> [!NOTE]
>
> <span data-ttu-id="f7635-109">Para este perfil, há suporte apenas para o tipo de conexão Pulse Secure e Citrix.</span><span class="sxs-lookup"><span data-stu-id="f7635-109">Only the Pulse Secure and Citrix connection types are supported for this profile.</span></span>


### <span data-ttu-id="f7635-110">Etapa 1: Criar um perfil de VPN</span><span class="sxs-lookup"><span data-stu-id="f7635-110">Step 1: Create a VPN profile</span></span>
<a id="step-1-create-a-vpn-profile" class="xliff"></a>

1. <span data-ttu-id="f7635-111">No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="f7635-111">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Add Policy**.</span></span>
2. <span data-ttu-id="f7635-112">Para selecionar um modelo para a nova política, expanda **Android** e escolha **Perfil de VPN (Android 4 e posterior)**.</span><span class="sxs-lookup"><span data-stu-id="f7635-112">To select a template for the new policy, expand **Android**, and then choose **VPN Profile (Android 4 and later)**.</span></span>
3. <span data-ttu-id="f7635-113">No modelo, para **Tipo de conexão**, escolha **Pulse Secure** ou **Citrix**.</span><span class="sxs-lookup"><span data-stu-id="f7635-113">In the template, for **Connection type**, choose **Pulse Secure** or **Citrix**.</span></span>
4. <span data-ttu-id="f7635-114">Conclua e salve o perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="f7635-114">Finish and save the VPN profile.</span></span> <span data-ttu-id="f7635-115">Para obter mais detalhes sobre perfis de VPN, consulte [Conexões VPN](../deploy-use/vpn-connections-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="f7635-115">For more details about VPN profiles, see [VPN connections](../deploy-use/vpn-connections-in-microsoft-intune.md).</span></span>

> [!NOTE]
>
> <span data-ttu-id="f7635-116">Anote o **nome da Conexão VPN (exibido aos usuários):** valor especificado ao criar o perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="f7635-116">Take note of the **VPN Connection name (displayed to users):** value you specify when creating the VPN profile.</span></span> <span data-ttu-id="f7635-117">Isso será necessário na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="f7635-117">This will be needed in the next step.</span></span> <span data-ttu-id="f7635-118">Por exemplo, **MyAppVpnProfile**.</span><span class="sxs-lookup"><span data-stu-id="f7635-118">For example, **MyAppVpnProfile**.</span></span>

### <span data-ttu-id="f7635-119">Etapa 2: Criar uma política de configuração personalizada</span><span class="sxs-lookup"><span data-stu-id="f7635-119">Step 2: Create a custom configuration policy</span></span>
<a id="step-2-create-a-custom-configuration-policy" class="xliff"></a>

   1. <span data-ttu-id="f7635-120">No console de administração do Intune, escolha **Política** > **Adicionar Política** > **Android** > **Configuração personalizada** > **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="f7635-120">In the Intune admin console, choose **Policy** > **Add Policy** > **Android** > **Custom configuration** > **Create Policy**.</span></span>
   2. <span data-ttu-id="f7635-121">Insira um nome para a política.</span><span class="sxs-lookup"><span data-stu-id="f7635-121">Enter a name for the policy.</span></span>
   3. <span data-ttu-id="f7635-122">Em **Configurações OMA-URI**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f7635-122">Under **OMA-URI settings**, choose **Add**.</span></span>
   4. <span data-ttu-id="f7635-123">Insira um nome para a configuração.</span><span class="sxs-lookup"><span data-stu-id="f7635-123">Enter a setting name.</span></span>
   5. <span data-ttu-id="f7635-124">Para **Tipo de dados**, especifique **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="f7635-124">For **Data type**, specify **String**.</span></span>
   6. <span data-ttu-id="f7635-125">Para **OMA-URI**, especifique esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/PackageList**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f7635-125">For **OMA-URI**, specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="f7635-126">Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span><span class="sxs-lookup"><span data-stu-id="f7635-126">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span></span>
   7.   <span data-ttu-id="f7635-127">Em **Valor**, crie uma lista separada por ponto e vírgula dos pacotes a serem associados ao perfil.</span><span class="sxs-lookup"><span data-stu-id="f7635-127">For **Value**, create a semicolon-separated list of packages to associate with the profile.</span></span> <span data-ttu-id="f7635-128">Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: **com.microsoft.office.excel;com.android.chrome**.</span><span class="sxs-lookup"><span data-stu-id="f7635-128">For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter **com.microsoft.office.excel;com.android.chrome**.</span></span>

![Exemplo de política personalizada de VPN por aplicativo Android](./media/android_per_app_vpn_oma_uri.png)

#### <span data-ttu-id="f7635-130">Definir sua lista de aplicativos como lista de bloqueios ou lista de permissões (opcional)</span><span class="sxs-lookup"><span data-stu-id="f7635-130">Set your app list to blacklist or whitelist (optional)</span></span>
<a id="set-your-app-list-to-blacklist-or-whitelist-optional" class="xliff"></a>
  <span data-ttu-id="f7635-131">Você pode especificar uma lista de aplicativos que *não podem* usar a conexão VPN usando o valor **BLACKLIST**.</span><span class="sxs-lookup"><span data-stu-id="f7635-131">You can specify a list of apps that *cannot* use the VPN connection by using the **BLACKLIST** value.</span></span> <span data-ttu-id="f7635-132">Todos os outros aplicativos se conectarão por meio da VPN.</span><span class="sxs-lookup"><span data-stu-id="f7635-132">All other apps will connect through the VPN.</span></span>
<span data-ttu-id="f7635-133">Como alternativa, você pode usar o valor **WHITELIST** para especificar uma lista de aplicativos que *podem* usar a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="f7635-133">Alternatively, you can use the **WHITELIST** value to specify a list of apps that *can* use the VPN connection.</span></span> <span data-ttu-id="f7635-134">Aplicativos que não estão na lista não se conectarão por meio da VPN.</span><span class="sxs-lookup"><span data-stu-id="f7635-134">Apps that are not on the list will not connect through the VPN.</span></span>
  1.    <span data-ttu-id="f7635-135">Em **Configurações OMA-URI**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f7635-135">Under **OMA-URI** settings, choose **Add**.</span></span>
  2.    <span data-ttu-id="f7635-136">Insira um nome para a configuração.</span><span class="sxs-lookup"><span data-stu-id="f7635-136">Enter a setting name.</span></span>
  3.    <span data-ttu-id="f7635-137">Para **Tipo de dados**, especifique **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="f7635-137">For **Data type**, specify **String**.</span></span>
  4.    <span data-ttu-id="f7635-138">Para **OMA-URI**, use esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/Mode**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="f7635-138">For **OMA-URI**, use this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="f7635-139">Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span><span class="sxs-lookup"><span data-stu-id="f7635-139">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span></span>
  5.    <span data-ttu-id="f7635-140">Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.</span><span class="sxs-lookup"><span data-stu-id="f7635-140">For **Value**, enter **BLACKLIST** or **WHITELIST**.</span></span>



### <span data-ttu-id="f7635-141">Etapa 3: implantar ambas as políticas</span><span class="sxs-lookup"><span data-stu-id="f7635-141">Step 3: Deploy both policies</span></span>
<a id="step-3-deploy-both-policies" class="xliff"></a>

<span data-ttu-id="f7635-142">Você deve implantar *ambas* políticas para o *mesmo* grupo do Intune.</span><span class="sxs-lookup"><span data-stu-id="f7635-142">You must deploy *both* policies to the *same* Intune groups.</span></span>

1.  <span data-ttu-id="f7635-143">No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="f7635-143">In the **Policy** workspace, select the policy that you want to deploy, and then choose **Manage Deployment**.</span></span>
2.  <span data-ttu-id="f7635-144">Na caixa de diálogo **Gerenciar implantação** :</span><span class="sxs-lookup"><span data-stu-id="f7635-144">In the **Manage Deployment** dialog box:</span></span>
    -   <span data-ttu-id="f7635-145">**Para implantar a política**, selecione um ou mais grupos nos quais implantar a política e escolha **Adicionar** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7635-145">**To deploy the policy**, select one or more groups to deploy the policy to, then choose **Add** > **OK**.</span></span>
    -   <span data-ttu-id="f7635-146">**Para fechar a caixa de diálogo sem implantar a política**, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="f7635-146">**To close the dialog box without deploying the policy**, choose **Cancel**.</span></span>

<span data-ttu-id="f7635-147">Um resumo de status e alertas na página **Visão geral** do espaço de trabalho **Política** identifica problemas com a política que exigem atenção.</span><span class="sxs-lookup"><span data-stu-id="f7635-147">A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention.</span></span> <span data-ttu-id="f7635-148">Um resumo de status também aparece no espaço de trabalho **Painel**.</span><span class="sxs-lookup"><span data-stu-id="f7635-148">A status summary also appears in the **Dashboard** workspace.</span></span>
