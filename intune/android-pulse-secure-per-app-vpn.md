---
title: "Perfil VPN por aplicativo para Android – Pulse Secure"
titleSuffix: Intune on Azure
description: Saiba como criar um perfil de VPN por aplicativo para dispositivos Android gerenciados pelo Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f0e3a8363eb25ba3a3b2c16f15b8188acb694938
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6835f-103">Use um perfil personalizado do Microsoft Intune para criar um perfil de VPN por aplicativo para dispositivos Android</span><span class="sxs-lookup"><span data-stu-id="6835f-103">Use a Microsoft Intune custom profile to create a per-app VPN profile for Android devices</span></span>
<a id="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6835f-104">Você pode criar um perfil de VPN por aplicativo para dispositivos Android 5.0 e posterior gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="6835f-104">You can create a per-app VPN profile for Android 5.0 and later devices that are managed by Intune.</span></span> <span data-ttu-id="6835f-105">Primeiro, crie um perfil de VPN que usa o tipo de conexão Pulse Secure.</span><span class="sxs-lookup"><span data-stu-id="6835f-105">First, create a VPN profile that uses the Pulse Secure connection type.</span></span> <span data-ttu-id="6835f-106">Em seguida, crie uma política de configuração personalizada que associa o perfil de VPN com aplicativos específicos.</span><span class="sxs-lookup"><span data-stu-id="6835f-106">Then, create a custom configuration policy that associates the VPN profile with specific apps.</span></span>

<span data-ttu-id="6835f-107">Depois que você atribuir a política para os grupos de usuários ou o dispositivo Android, os usuários deverão iniciar o PulseSecure VPN.</span><span class="sxs-lookup"><span data-stu-id="6835f-107">After you assign the policy to your Android device or user groups, users should start the PulseSecure VPN.</span></span> <span data-ttu-id="6835f-108">Em seguida, o PulseSecure permite que somente o tráfego dos aplicativos especificados use a conexão VPN aberta.</span><span class="sxs-lookup"><span data-stu-id="6835f-108">PulseSecure then allows only traffic from the specified apps to use the open VPN connection.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6835f-109">Para este perfil, há suporte apenas para o tipo de conexão Pulse Secure.</span><span class="sxs-lookup"><span data-stu-id="6835f-109">Only the Pulse Secure connection type is supported for this profile.</span></span>


## <span data-ttu-id="6835f-110">Etapa 1: Criar um perfil de VPN</span><span class="sxs-lookup"><span data-stu-id="6835f-110">Step 1: Create a VPN profile</span></span>
<a id="step-1-create-a-vpn-profile" class="xliff"></a>


1. <span data-ttu-id="6835f-111">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="6835f-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="6835f-112">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6835f-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="6835f-113">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6835f-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="6835f-114">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="6835f-114">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="6835f-115">Na folha da lista de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="6835f-115">On the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="6835f-116">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil VPN.</span><span class="sxs-lookup"><span data-stu-id="6835f-116">On the **Create Profile** blade, enter a **Name** and optional **Description** for the VPN profile.</span></span>
4. <span data-ttu-id="6835f-117">Na lista suspensa **Plataforma**, escolha **Android**.</span><span class="sxs-lookup"><span data-stu-id="6835f-117">From the **Platform** drop-down list, choose **Android**.</span></span>
5. <span data-ttu-id="6835f-118">Na lista suspensa **Tipo de perfil**, escolha **VPN**.</span><span class="sxs-lookup"><span data-stu-id="6835f-118">From the **Profile type** drop-down list, choose **VPN**.</span></span>
3. <span data-ttu-id="6835f-119">Escolha **Configurações** > **Definir** e defina o perfil VPN de acordo com as configurações em [Como definir as configurações de VPN](vpn-settings-configure.md) e [Configurações VPN do Intune para dispositivos Android](vpn-settings-android.md).</span><span class="sxs-lookup"><span data-stu-id="6835f-119">Choose **Settings** > **Configure** and then configure the VPN profile as per the settings in [How to configure VPN settings](vpn-settings-configure.md) and [Intune VPN settings for Android devices](vpn-settings-android.md).</span></span>

<span data-ttu-id="6835f-120">Anote o valor de **Nome da Conexão** que você especificou ao criar o perfil de VPN.</span><span class="sxs-lookup"><span data-stu-id="6835f-120">Take note of the **Connection Name** value you specify when creating the VPN profile.</span></span> <span data-ttu-id="6835f-121">Esse nome será necessário na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="6835f-121">This name will be needed in the next step.</span></span> <span data-ttu-id="6835f-122">Por exemplo, **MyAppVpnProfile**.</span><span class="sxs-lookup"><span data-stu-id="6835f-122">For example, **MyAppVpnProfile**.</span></span>

## <span data-ttu-id="6835f-123">Etapa 2: Criar uma política de configuração personalizada</span><span class="sxs-lookup"><span data-stu-id="6835f-123">Step 2: Create a custom configuration policy</span></span>
<a id="step-2-create-a-custom-configuration-policy" class="xliff"></a>

1. <span data-ttu-id="6835f-124">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="6835f-124">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="6835f-125">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6835f-125">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="6835f-126">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6835f-126">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="6835f-127">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="6835f-127">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="6835f-128">Na folha de perfis, clique em **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="6835f-128">On the profiles blade, click **Create Profile**.</span></span>
4. <span data-ttu-id="6835f-129">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil personalizado.</span><span class="sxs-lookup"><span data-stu-id="6835f-129">On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.</span></span>
5. <span data-ttu-id="6835f-130">Na lista suspensa **Plataforma**, escolha **Android**.</span><span class="sxs-lookup"><span data-stu-id="6835f-130">From the **Platform** drop-down list, choose **Android**.</span></span>
6. <span data-ttu-id="6835f-131">Na lista suspensa **Tipo de perfil**, escolha **Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="6835f-131">From the **Profile type** drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="6835f-132">Escolha **Configurações** > **Definir**.</span><span class="sxs-lookup"><span data-stu-id="6835f-132">Choose **Settings** > **Configure**.</span></span>
3. <span data-ttu-id="6835f-133">Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6835f-133">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
    - <span data-ttu-id="6835f-134">Insira um nome para a configuração.</span><span class="sxs-lookup"><span data-stu-id="6835f-134">Enter a setting name.</span></span>
    - <span data-ttu-id="6835f-135">Para **Tipo de dados**, especifique **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="6835f-135">For **Data type**, specify **String**.</span></span>
    - <span data-ttu-id="6835f-136">Para **OMA-URI**, especifique esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/PackageList**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="6835f-136">For **OMA-URI**, specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="6835f-137">Nesse exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span><span class="sxs-lookup"><span data-stu-id="6835f-137">In this example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span></span>
    - <span data-ttu-id="6835f-138">Em **Valor**, crie uma lista separada por ponto e vírgula dos pacotes a serem associados ao perfil.</span><span class="sxs-lookup"><span data-stu-id="6835f-138">For **Value**, create a semicolon-separated list of packages to associate with the profile.</span></span> <span data-ttu-id="6835f-139">Por exemplo, se desejar que o Excel e o navegador Google Chrome usem a conexão VPN, digite: **com.microsoft.office.excel;com.android.chrome**.</span><span class="sxs-lookup"><span data-stu-id="6835f-139">For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter **com.microsoft.office.excel;com.android.chrome**.</span></span>

![Exemplo de política personalizada de VPN por aplicativo Android](./media/android_per_app_vpn_oma_uri.png)

### <span data-ttu-id="6835f-141">Definir sua lista de aplicativos como lista de bloqueios ou lista de permissões (opcional)</span><span class="sxs-lookup"><span data-stu-id="6835f-141">Set your app list to blacklist or whitelist (optional)</span></span>
<a id="set-your-app-list-to-blacklist-or-whitelist-optional" class="xliff"></a>
  <span data-ttu-id="6835f-142">Você pode especificar uma lista de aplicativos que *não podem* usar a conexão VPN usando o valor **BLACKLIST**.</span><span class="sxs-lookup"><span data-stu-id="6835f-142">You can specify a list of apps that *cannot* use the VPN connection by using the **BLACKLIST** value.</span></span> <span data-ttu-id="6835f-143">Todos os outros aplicativos se conectam por meio da VPN.</span><span class="sxs-lookup"><span data-stu-id="6835f-143">All other apps connect through the VPN.</span></span>
<span data-ttu-id="6835f-144">Como alternativa, você pode usar o valor **WHITELIST** para especificar uma lista de aplicativos que *podem* usar a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="6835f-144">Alternatively, you can use the **WHITELIST** value to specify a list of apps that *can* use the VPN connection.</span></span> <span data-ttu-id="6835f-145">Os aplicativos que não estão na lista não se conectam por meio da VPN.</span><span class="sxs-lookup"><span data-stu-id="6835f-145">Apps that are not on the list do not connect through the VPN.</span></span>
  1.    <span data-ttu-id="6835f-146">Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="6835f-146">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
  2.    <span data-ttu-id="6835f-147">Insira um nome para a configuração.</span><span class="sxs-lookup"><span data-stu-id="6835f-147">Enter a setting name.</span></span>
  3.    <span data-ttu-id="6835f-148">Para **Tipo de dados**, especifique **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="6835f-148">For **Data type**, specify **String**.</span></span>
  4.    <span data-ttu-id="6835f-149">Para **OMA-URI**, use esta cadeia de caracteres: **./Vendor/MSFT/VPN/Profile/*Nome*/Mode**, em que *Nome* é o nome do perfil de VPN que você anotou na Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="6835f-149">For **OMA-URI**, use this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="6835f-150">Em nosso exemplo, a cadeia de caracteres seria **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span><span class="sxs-lookup"><span data-stu-id="6835f-150">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span></span>
  5.    <span data-ttu-id="6835f-151">Em **Valor**, digite **BLACKLIST** ou **WHITELIST**.</span><span class="sxs-lookup"><span data-stu-id="6835f-151">For **Value**, enter **BLACKLIST** or **WHITELIST**.</span></span>



## <span data-ttu-id="6835f-152">Etapa 3: atribuir ambas as políticas</span><span class="sxs-lookup"><span data-stu-id="6835f-152">Step 3: Assign both policies</span></span>
<a id="step-3-assign-both-policies" class="xliff"></a>

<span data-ttu-id="6835f-153">Use as instruções em [Como atribuir perfis de dispositivo](device-profile-assign.md) para atribuir os dois perfis para os dispositivos ou usuários necessários.</span><span class="sxs-lookup"><span data-stu-id="6835f-153">Use the instructions in [How to assign device profiles](device-profile-assign.md) to assign both profiles to the required users or devices.</span></span>
