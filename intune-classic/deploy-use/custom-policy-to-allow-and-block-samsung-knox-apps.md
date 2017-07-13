---
title: Aplicativos permitidos e bloqueados no KNOX
description: Perfil personalizado para criar uma lista de aplicativos permitidos e bloqueados para KNOX.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b215425534e833db7e92e3f60fc507a168ef576f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="bb463-103">Usar políticas personalizadas para permitir e bloquear aplicativos para dispositivos Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="bb463-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices</span></span>
<a id="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bb463-104">Use os procedimentos neste tópico para criar uma política personalizada do Microsoft Intune que cria um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="bb463-104">Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="bb463-105">Uma lista de aplicativos cuja execução no dispositivo é bloqueada.</span><span class="sxs-lookup"><span data-stu-id="bb463-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="bb463-106">Aplicativos nesta lista serão impedidos de serem executados, mesmo se já tiverem sido instalados quando a política foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="bb463-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="bb463-107">Uma lista de aplicativos que os usuários do dispositivo podem instalar da loja Google Play.</span><span class="sxs-lookup"><span data-stu-id="bb463-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="bb463-108">Apenas os aplicativos listados podem ser instalados.</span><span class="sxs-lookup"><span data-stu-id="bb463-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="bb463-109">Nenhum outro aplicativo pode ser instalado da loja.</span><span class="sxs-lookup"><span data-stu-id="bb463-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="bb463-110">Essas configurações podem ser usadas apenas por dispositivos que executam o Samsung KNOX Standard.</span><span class="sxs-lookup"><span data-stu-id="bb463-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <span data-ttu-id="bb463-111">Para criar uma lista de aplicativos permitidos ou bloqueados</span><span class="sxs-lookup"><span data-stu-id="bb463-111">To create an allowed or blocked app list</span></span>
<a id="to-create-an-allowed-or-blocked-app-list" class="xliff"></a>

1. <span data-ttu-id="bb463-112">No [console de administração do Microsoft Intune](https://manage.microsoft.com/), clique em **Política** &gt; **Políticas de Configuração** &gt; **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bb463-112">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Policy** &gt; **Configuration Policies** &gt; **Add**.</span></span>
2. <span data-ttu-id="bb463-113">Na caixa de diálogo **Criar Nova política**, expanda **Android**, escolha **Configuração Personalizada** e escolha **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="bb463-113">In the **Create a New Policy** dialog box, expand **Android**, choose **Custom Configuration**, and then choose **Create Policy**.</span></span>
3. <span data-ttu-id="bb463-114">Forneça um nome e uma descrição opcional para a política e, na seção **Configurações do OMA-URI**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bb463-114">Provide a name and optional description for the policy and then, in the **OMA-URI Settings** section, choose **Add**.</span></span>
4. <span data-ttu-id="bb463-115">Na caixa de diálogo **Adicionar ou editar a Configuração do OMA-URI**, especifique o seguinte: para obter uma lista dos aplicativos que são impedidos de serem executados no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="bb463-115">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:  For a list of apps that are blocked from running on the device:</span></span>
    
    - <span data-ttu-id="bb463-116">**Nome da configuração.**</span><span class="sxs-lookup"><span data-stu-id="bb463-116">**Setting name.**</span></span> <span data-ttu-id="bb463-117">Digite **PreventStartPackages**.</span><span class="sxs-lookup"><span data-stu-id="bb463-117">Enter **PreventStartPackages**.</span></span>
    - <span data-ttu-id="bb463-118">**Descrição da configuração.**</span><span class="sxs-lookup"><span data-stu-id="bb463-118">**Setting description.**</span></span> <span data-ttu-id="bb463-119">Insira uma descrição opcional, como “Lista de aplicativos impedidos de serem executados”.</span><span class="sxs-lookup"><span data-stu-id="bb463-119">Enter an optional description like 'List of apps that are blocked from running.'</span></span>
    -   <span data-ttu-id="bb463-120">**Tipo de dados.**</span><span class="sxs-lookup"><span data-stu-id="bb463-120">**Data type.**</span></span> <span data-ttu-id="bb463-121">Na lista suspensa, escolha **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="bb463-121">From the drop-down list, choose **String**.</span></span>
    -   <span data-ttu-id="bb463-122">**OMA-URI.**</span><span class="sxs-lookup"><span data-stu-id="bb463-122">**OMA-URI.**</span></span> <span data-ttu-id="bb463-123">Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span><span class="sxs-lookup"><span data-stu-id="bb463-123">Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
    -   <span data-ttu-id="bb463-124">**Valor.**</span><span class="sxs-lookup"><span data-stu-id="bb463-124">**Value.**</span></span> <span data-ttu-id="bb463-125">Insira uma lista dos nomes de pacotes do aplicativo que deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="bb463-125">Enter a list of the app package names you want to block.</span></span> <span data-ttu-id="bb463-126">Você pode usar **; : ,** ou **|** como delimitador.</span><span class="sxs-lookup"><span data-stu-id="bb463-126">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="bb463-127">(Exemplo: pacote1; pacote2;)</span><span class="sxs-lookup"><span data-stu-id="bb463-127">(Example: package1;package2;)</span></span>

    <span data-ttu-id="bb463-128">Para obter uma lista dos aplicativos que os usuários do dispositivo podem instalar da loja Google Play enquanto todos os outros aplicativos são excluídos:</span><span class="sxs-lookup"><span data-stu-id="bb463-128">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>

    - <span data-ttu-id="bb463-129">**Nome da configuração.**</span><span class="sxs-lookup"><span data-stu-id="bb463-129">**Setting name.**</span></span> <span data-ttu-id="bb463-130">Digite **AllowInstallPackages**.</span><span class="sxs-lookup"><span data-stu-id="bb463-130">Enter **AllowInstallPackages**.</span></span>
    - <span data-ttu-id="bb463-131">**Descrição da configuração.**</span><span class="sxs-lookup"><span data-stu-id="bb463-131">**Setting description.**</span></span> <span data-ttu-id="bb463-132">Insira uma descrição opcional, como “Lista de aplicativos que os usuários podem instalar do Google Play”.</span><span class="sxs-lookup"><span data-stu-id="bb463-132">Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
    - <span data-ttu-id="bb463-133">**Tipo de dados.**</span><span class="sxs-lookup"><span data-stu-id="bb463-133">**Data type.**</span></span> <span data-ttu-id="bb463-134">Na lista suspensa, escolha **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="bb463-134">From the drop-down list, choose **String**.</span></span>
    - <span data-ttu-id="bb463-135">**OMA-URI.**</span><span class="sxs-lookup"><span data-stu-id="bb463-135">**OMA-URI.**</span></span> <span data-ttu-id="bb463-136">Digite **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span><span class="sxs-lookup"><span data-stu-id="bb463-136">Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
    - <span data-ttu-id="bb463-137">**Valor.**</span><span class="sxs-lookup"><span data-stu-id="bb463-137">**Value.**</span></span> <span data-ttu-id="bb463-138">Insira uma lista dos nomes de pacotes do aplicativo que deseja permitir.</span><span class="sxs-lookup"><span data-stu-id="bb463-138">Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="bb463-139">Você pode usar **; : ,** ou **|** como delimitador.</span><span class="sxs-lookup"><span data-stu-id="bb463-139">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="bb463-140">(Exemplo: pacote1; pacote2;)</span><span class="sxs-lookup"><span data-stu-id="bb463-140">(Example: package1;package2;)</span></span>

4. <span data-ttu-id="bb463-141">Clique em **OK** e em **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="bb463-141">Click **OK**, and then click **Save Policy**.</span></span> 

>[!TIP]
> <span data-ttu-id="bb463-142">Você pode encontrar a ID do pacote de um aplicativo navegando até o aplicativo na loja do Google Play.</span><span class="sxs-lookup"><span data-stu-id="bb463-142">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="bb463-143">A ID do pacote está contida na URL da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bb463-143">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="bb463-144">Por exemplo, a ID do pacote do aplicativo Microsoft Word é **com.microsoft.office.word**.</span><span class="sxs-lookup"><span data-stu-id="bb463-144">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="bb463-145">Na próxima vez que cada dispositivo de destino fizer check-in, as configurações do aplicativo serão aplicadas.</span><span class="sxs-lookup"><span data-stu-id="bb463-145">The next time each targeted device checks in, the app settings will be applied.</span></span>


## <span data-ttu-id="bb463-146">Implantar a política</span><span class="sxs-lookup"><span data-stu-id="bb463-146">Deploy the policy</span></span>
<a id="deploy-the-policy" class="xliff"></a>

1.  <span data-ttu-id="bb463-147">No espaço de trabalho **Política**, selecione a política que deseja implantar e clique em **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="bb463-147">In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.</span></span>

2.  <span data-ttu-id="bb463-148">Na caixa de diálogo **Gerenciar Implantação**, selecione um ou mais grupos para os quais deseja implantar a política e clique em **Adicionar** &gt; **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb463-148">In the **Manage Deployment** dialog box, select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.</span></span>

 
<span data-ttu-id="bb463-149">Quando você seleciona uma política implantada, pode exibir mais informações sobre a implantação na parte inferior da lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="bb463-149">When you select a deployed policy, you can view further information about the deployment in the lower part of the policies list.</span></span>

### <span data-ttu-id="bb463-150">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bb463-150">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="bb463-151">Configurações de política do Android e do Samsung KNOX no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bb463-151">Android and Samsung KNOX policy settings in Microsoft Intune</span></span>](android-policy-settings-in-microsoft-intune.md)
