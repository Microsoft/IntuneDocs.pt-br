---
title: "Política do Intune para permitir/bloquear aplicativos para o Samsung KNOX"
titleSuffix: Intune on Azure
description: Criar um perfil personalizado para permitir e bloquear aplicativos em dispositivos Samsung KNOX Standard.
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
ms.openlocfilehash: 8245bb3fa8f08e719df903a70f079f4fdf534ca5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="bd173-103">Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX Standard no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bd173-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune</span></span>
<a id="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune" class="xliff"></a>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]<span data-ttu-id="bd173-104">Use os procedimentos neste tópico para criar uma política personalizada do Microsoft Intune que cria um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="bd173-104"> Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="bd173-105">Uma lista de aplicativos cuja execução no dispositivo é bloqueada.</span><span class="sxs-lookup"><span data-stu-id="bd173-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="bd173-106">Aplicativos nesta lista serão impedidos de serem executados, mesmo se já tiverem sido instalados quando a política foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="bd173-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="bd173-107">Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play.</span><span class="sxs-lookup"><span data-stu-id="bd173-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="bd173-108">Apenas os aplicativos listados podem ser instalados.</span><span class="sxs-lookup"><span data-stu-id="bd173-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="bd173-109">Nenhum outro aplicativo pode ser instalado da loja.</span><span class="sxs-lookup"><span data-stu-id="bd173-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="bd173-110">Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX Standard.</span><span class="sxs-lookup"><span data-stu-id="bd173-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <span data-ttu-id="bd173-111">Criar uma lista de aplicativos permitidos ou bloqueados</span><span class="sxs-lookup"><span data-stu-id="bd173-111">Create an allowed or blocked app list</span></span>
<a id="create-an-allowed-or-blocked-app-list" class="xliff"></a>

1. <span data-ttu-id="bd173-112">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="bd173-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="bd173-113">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="bd173-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="bd173-114">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="bd173-114">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="bd173-115">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="bd173-115">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="bd173-116">Na folha da lista de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="bd173-116">In the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="bd173-117">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** opcional para o perfil do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bd173-117">On the **Create Profile** blade, enter a **Name** and optional **Description** for this device profile.</span></span>
2. <span data-ttu-id="bd173-118">Escolha um **Tipo de plataforma** **Android** e um Tipo de perfil **Personalizado**.</span><span class="sxs-lookup"><span data-stu-id="bd173-118">Choose a **Platform type** of **Android**, and a Profile type of **Custom**.</span></span>
3. <span data-ttu-id="bd173-119">Clique em **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="bd173-119">Click **Settings**.</span></span>
3. <span data-ttu-id="bd173-120">Na folha **Configurações personalizadas de OMA-URI**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bd173-120">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
4. <span data-ttu-id="bd173-121">Na caixa de diálogo **Adicionar ou Editar Configuração de OMA-URI**, especifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bd173-121">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:</span></span>

### <span data-ttu-id="bd173-122">Para ver uma lista de aplicativos cuja execução no dispositivo é bloqueada:</span><span class="sxs-lookup"><span data-stu-id="bd173-122">For a list of apps that are blocked from running on the device:</span></span>
<a id="for-a-list-of-apps-that-are-blocked-from-running-on-the-device" class="xliff"></a>

- <span data-ttu-id="bd173-123">**Nome** – Digite **PreventStartPackages**.</span><span class="sxs-lookup"><span data-stu-id="bd173-123">**Name** - Enter **PreventStartPackages**.</span></span>
- <span data-ttu-id="bd173-124">**Descrição** – Insira uma descrição opcional, como “Lista de aplicativos impedidos de serem executados”.</span><span class="sxs-lookup"><span data-stu-id="bd173-124">**Description** - Enter an optional description like 'List of apps that are blocked from running.'</span></span>
-   <span data-ttu-id="bd173-125">**Tipo de dados** – Na lista suspensa, escolha **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="bd173-125">**Data type** - From the drop-down list, choose **String**.</span></span>
-   <span data-ttu-id="bd173-126">**OMA-URI** – Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span><span class="sxs-lookup"><span data-stu-id="bd173-126">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
-   <span data-ttu-id="bd173-127">**Valor** – Insira uma lista com os nomes do pacote do aplicativo que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="bd173-127">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="bd173-128">Você pode usar **; : ,** ou **|** como delimitador.</span><span class="sxs-lookup"><span data-stu-id="bd173-128">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="bd173-129">(Exemplo: pacote1; pacote2;)</span><span class="sxs-lookup"><span data-stu-id="bd173-129">(Example: package1;package2;)</span></span>

### <span data-ttu-id="bd173-130">Para obter uma lista dos aplicativos que os usuários do dispositivo podem instalar da loja Google Play enquanto todos os outros aplicativos são excluídos:</span><span class="sxs-lookup"><span data-stu-id="bd173-130">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>
<a id="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps" class="xliff"></a>
- <span data-ttu-id="bd173-131">**Nome** – Digite **AllowInstallPackages**.</span><span class="sxs-lookup"><span data-stu-id="bd173-131">**Name** - Enter **AllowInstallPackages**.</span></span>
- <span data-ttu-id="bd173-132">**Descrição** – Insira uma descrição opcional, como “Lista de aplicativos que os usuários podem instalar do Google Play”.</span><span class="sxs-lookup"><span data-stu-id="bd173-132">**Description** - Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
- <span data-ttu-id="bd173-133">**Tipo de dados** – Na lista suspensa, escolha **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="bd173-133">**Data type** - From the drop-down list, choose **String**.</span></span>
- <span data-ttu-id="bd173-134">**OMA-URI** – Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span><span class="sxs-lookup"><span data-stu-id="bd173-134">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
- <span data-ttu-id="bd173-135">**Valor** – Insira uma lista com os nomes do pacote do aplicativo que você deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="bd173-135">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="bd173-136">Você pode usar **; : ,** ou **|** como delimitador.</span><span class="sxs-lookup"><span data-stu-id="bd173-136">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="bd173-137">(Exemplo: pacote1; pacote2;)</span><span class="sxs-lookup"><span data-stu-id="bd173-137">(Example: package1;package2;)</span></span>

4. <span data-ttu-id="bd173-138">Clique em **OK** e, em seguida, na folha **Criar Perfil**, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="bd173-138">Click **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

>[!TIP]
> <span data-ttu-id="bd173-139">Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play.</span><span class="sxs-lookup"><span data-stu-id="bd173-139">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="bd173-140">A ID do pacote está contida na URL da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bd173-140">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="bd173-141">Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.</span><span class="sxs-lookup"><span data-stu-id="bd173-141">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="bd173-142">Na próxima vez que cada dispositivo de destino fizer check-in, as configurações do aplicativo serão aplicadas.</span><span class="sxs-lookup"><span data-stu-id="bd173-142">The next time each targeted device checks in, the app settings will be applied.</span></span>


<!---## Assign the custom profile--->
