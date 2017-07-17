---
title: "Como usar políticas de configuração de aplicativo do Intune para o iOS"
titleSuffix: Intune on Azure
description: "Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 112f60ff208c27825ddd0f4c812535b255894333
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="2de72-103">Como usar as políticas de configuração de aplicativo do Microsoft Intune para o iOS</span><span class="sxs-lookup"><span data-stu-id="2de72-103">How to use Microsoft Intune app configuration policies for iOS</span></span>
<a id="how-to-use-microsoft-intune-app-configuration-policies-for-ios" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="2de72-104">Use políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="2de72-104">Use app configuration policies in Microsoft Intune to supply settings that might be required when users run an iOS app.</span></span> <span data-ttu-id="2de72-105">Por exemplo, um aplicativo pode exigir que os usuários especifiquem:</span><span class="sxs-lookup"><span data-stu-id="2de72-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="2de72-106">Um número da porta personalizado.</span><span class="sxs-lookup"><span data-stu-id="2de72-106">A custom port number.</span></span>

-   <span data-ttu-id="2de72-107">Configurações de idioma.</span><span class="sxs-lookup"><span data-stu-id="2de72-107">Language settings.</span></span>

-   <span data-ttu-id="2de72-108">Configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="2de72-108">Security settings.</span></span>

-   <span data-ttu-id="2de72-109">Configurações de identidade visual, como um logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="2de72-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="2de72-110">Se os usuários inserirem essas configurações incorretamente, isso poderá aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2de72-110">If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="2de72-111">As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-111">App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="2de72-112">As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="2de72-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="2de72-113">Você não atribui essas políticas diretamente para usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2de72-113">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="2de72-114">Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-114">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="2de72-115">As configurações de política serão usadas sempre que o aplicativo verificá-las (normalmente, na primeira vez que é executado).</span><span class="sxs-lookup"><span data-stu-id="2de72-115">The policy settings will be used whenever the app checks for them (typically, the first time it is run).</span></span>

> [!TIP]
> <span data-ttu-id="2de72-116">No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="2de72-116">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="2de72-117">Ela dá suporte aos seguintes tipos de instalação de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="2de72-117">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="2de72-118">**Aplicativo iOS gerenciado da loja de aplicativos**</span><span class="sxs-lookup"><span data-stu-id="2de72-118">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="2de72-119">**Pacote do aplicativo do iOS**</span><span class="sxs-lookup"><span data-stu-id="2de72-119">**App package for iOS**</span></span>
>
> <span data-ttu-id="2de72-120">Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="2de72-120">For more information about app installation types, see [How to add an app to Microsoft Intune](apps-add.md).</span></span>

## <span data-ttu-id="2de72-121">Criar uma política de configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="2de72-121">Create an app configuration policy</span></span>
<a id="create-an-app-configuration-policy" class="xliff"></a>

1. <span data-ttu-id="2de72-122">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="2de72-122">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="2de72-123">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="2de72-123">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="2de72-124">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="2de72-124">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="2de72-125">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Políticas de Configuração de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2de72-125">In the **Mobile apps** workload, choose **Manage** > **App Configuration Policies**.</span></span>

2.  <span data-ttu-id="2de72-126">Na folha da lista de políticas, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2de72-126">In the list of policies blade, choose **Add**.</span></span>

3.  <span data-ttu-id="2de72-127">Na folha **Adicionar política de configuração**, forneça um nome e uma descrição opcional para a política de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-127">On the **Add Configuration Policy** blade, supply a name and an optional description for the app configuration policy.</span></span>
4.  <span data-ttu-id="2de72-128">Escolha **Aplicativo associado** e, na folha **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="2de72-128">Choose **Associated App**, then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.</span></span>
5.  <span data-ttu-id="2de72-129">Na folha **Adicionar política de configuração**, escolha **Definições de configurações** e, na folha Definições de configurações, escolha como você deseja especificar os valores de XML que compõem o perfil de configuração de:</span><span class="sxs-lookup"><span data-stu-id="2de72-129">On the **Add Configuration Policy** blade, choose **Configuration settings** and then, on the Configuration Settings blade, choose how you want to specify the XML values that make up the configuration profile from:</span></span>
    - <span data-ttu-id="2de72-130">**Inserir dados XML** – Digite ou cole uma lista de propriedades XML que contém as definições de configuração do aplicativo que você deseja.</span><span class="sxs-lookup"><span data-stu-id="2de72-130">**Enter XML data** - enter or paste an  XML property list that contains the app configuration settings that you want.</span></span> <span data-ttu-id="2de72-131">O formato da lista de propriedades XML vai variar dependendo do aplicativo que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="2de72-131">The format of the XML property list will vary depending on the app you are configuring.</span></span> <span data-ttu-id="2de72-132">Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.</span><span class="sxs-lookup"><span data-stu-id="2de72-132">Contact the supplier of the app for details about the exact format to use.</span></span>
    <span data-ttu-id="2de72-133">O Intune verifica se o XML que você inseriu está em um formato válido.</span><span class="sxs-lookup"><span data-stu-id="2de72-133">Intune checks that the XML you entered is in a valid format.</span></span> <span data-ttu-id="2de72-134">Ele não verifica se a lista de propriedades XML funcionará com o aplicativo a que está associada.</span><span class="sxs-lookup"><span data-stu-id="2de72-134">It does not check that the XML property list will work with the app that it is associated with.</span></span>
    <span data-ttu-id="2de72-135">Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.</span><span class="sxs-lookup"><span data-stu-id="2de72-135">To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>
    - <span data-ttu-id="2de72-136">**Usar o designer de configuração** – Permite que você especifique os pares de chave e valor XML diretamente no portal.</span><span class="sxs-lookup"><span data-stu-id="2de72-136">**Use configuration designer** - Lets you specify XML key and value pairs directly in the portal.</span></span>
8. <span data-ttu-id="2de72-137">Após terminar, volte para a folha **Adicionar Política de Configuração** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="2de72-137">When you're done, go back to the **Add Configuration Policy** blade, and hit **Create**.</span></span>

<span data-ttu-id="2de72-138">A política será criada e aparecerá na folha da lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="2de72-138">The policy will be created and appears on the policies list blade.</span></span>

<span data-ttu-id="2de72-139">Em seguida, continue a [Atribuir](apps-deploy.md) e a [Monitor](apps-monitor.md) o aplicativo como de costume.</span><span class="sxs-lookup"><span data-stu-id="2de72-139">Then, continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>

<span data-ttu-id="2de72-140">Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-140">When the assigned app is run on a device, it will run with the settings that you configured in the app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="2de72-141">Se uma ou mais políticas de configuração de aplicativo entrarem em conflito, nenhuma delas será aplicada.</span><span class="sxs-lookup"><span data-stu-id="2de72-141">If one or more app configuration policies conflict, neither policy is enforced.</span></span>

## <span data-ttu-id="2de72-142">Criar uma política de configuração direcionada para o MAM</span><span class="sxs-lookup"><span data-stu-id="2de72-142">Create a MAM targeted configuration policy</span></span>
<a id="create-a-mam-targeted-configuration-policy" class="xliff"></a>
<span data-ttu-id="2de72-143">A configuração voltada para MAM permite que um aplicativo receba dados de configuração por meio do SDK do aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="2de72-143">MAM targeted configuration allows an app to receive configuration data through the Intune App SDK.</span></span> <span data-ttu-id="2de72-144">O formato e as variantes desses dados devem ser definidos e comunicados aos clientes do Intune pelo proprietário/desenvolvedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-144">The format and variants of this data must be defined and communicated to Intune customers by the application owner/developer.</span></span> <span data-ttu-id="2de72-145">Os administradores do Intune podem direcionar e implantar dados de configuração por meio do console do Intune Azure.</span><span class="sxs-lookup"><span data-stu-id="2de72-145">Intune administrators can target and deploy configuration data via the Intune Azure console.</span></span> <span data-ttu-id="2de72-146">Os dados de configuração direcionada para o MAM podem ser fornecidos por meio do Serviço MAM para aplicativos habilitados para MAM-WE.</span><span class="sxs-lookup"><span data-stu-id="2de72-146">MAM targeted configuration data can be provided via the MAM Service to MAM-WE enabled applications.</span></span> <span data-ttu-id="2de72-147">Por exemplo, o [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser) permitiu/bloqueou a lista de URLs.</span><span class="sxs-lookup"><span data-stu-id="2de72-147">For example, [Intune Managed Browser](https://docs.microsoft.com/intune/app-configuration-managed-browser) has allowed/blocked url list.</span></span> <span data-ttu-id="2de72-148">Os dados de configuração de aplicativo são enviados por push por meio de nosso Serviço MAM diretamente para o aplicativo em vez de pelo canal MDM.</span><span class="sxs-lookup"><span data-stu-id="2de72-148">The application configuration data is pushed through our MAM Service directly to the app instead of through the MDM channel.</span></span> <span data-ttu-id="2de72-149">As [políticas de configuração de aplicativo do MDM](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) são a solução nativa por meio de MDM.</span><span class="sxs-lookup"><span data-stu-id="2de72-149">[MDM app configuration policies](https://docs.microsoft.com/intune/app-configuration-policies-use-ios#create-an-app-configuration-policy) are the native solution through MDM.</span></span> <span data-ttu-id="2de72-150">A principal diferença com a configuração direcionada para o MAM é que o dispositivo em que o aplicativo é executado não precisa ser registrado pelo MDM.</span><span class="sxs-lookup"><span data-stu-id="2de72-150">The key difference with MAM targeted configuration is that the device that the app runs on does not need to be MDM-enrolled.</span></span> <span data-ttu-id="2de72-151">A configuração direcionada para o MAM está disponível no iOS e no Android.</span><span class="sxs-lookup"><span data-stu-id="2de72-151">MAM targeted configuration is available on iOS and Android.</span></span> <span data-ttu-id="2de72-152">Para iOS, o aplicativo deve incorporam o SDK do Intune APP para iOS (v 7.0.1) e estar participando de definições de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-152">For iOS, the app must have incorporated Intune APP SDK for iOS (v 7.0.1) and be participating in app config settings.</span></span> <span data-ttu-id="2de72-153">As etapas para criar uma política de configuração direcionada para o MAM são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="2de72-153">The steps for creating a MAM targeted configuration policy are as follows:</span></span> 

1. <span data-ttu-id="2de72-154">Entre no **portal do Azure**.</span><span class="sxs-lookup"><span data-stu-id="2de72-154">Sign into the **Azure portal**.</span></span>

2. <span data-ttu-id="2de72-155">Escolha **Intune > Aplicativos móveis – Políticas de configuração de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="2de72-155">Choose **Intune > Mobile apps - App configuration policies**.</span></span>

3. <span data-ttu-id="2de72-156">Na folha **Políticas de configuração de aplicativo**, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2de72-156">On the **App configuration policies** blade, choose **Add**.</span></span>

4. <span data-ttu-id="2de72-157">Insira um **Nome** e uma **Descrição** opcional para as definições de configuração de aplicativo e escolha **Não registrado no Intune**.</span><span class="sxs-lookup"><span data-stu-id="2de72-157">Enter a **Name**, and optional **Description** for the app configuration settings and choose **Not enrolled with Intune**.</span></span>

5. <span data-ttu-id="2de72-158">Escolha **Selecionar aplicativos necessários** e, em seguida, na folha de aplicativos **Direcionados**, escolha aplicativos para as plataformas desejadas.</span><span class="sxs-lookup"><span data-stu-id="2de72-158">Choose **Select required apps** and then, on the **Targeted** apps blade, choose apps for the platforms you intend.</span></span> <br><span data-ttu-id="2de72-159">
**Observação:** para aplicativos LOB, selecione **Mais aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2de72-159">
**Note:** For LOB apps, select **More apps**.</span></span> <span data-ttu-id="2de72-160">Insira a ID de pacote do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-160">Enter the package ID for your application.</span></span>

6. <span data-ttu-id="2de72-161">Escolha **OK** para retornar à folha **Adicionar configuração de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="2de72-161">Choose **OK** to return to the **Add app configuration** blade.</span></span>

7. <span data-ttu-id="2de72-162">Escolha **Definir configuração**.</span><span class="sxs-lookup"><span data-stu-id="2de72-162">Choose **Define configuration**.</span></span> <span data-ttu-id="2de72-163">Na folha **Configuração**, defina os pares de chave e valor para fornecer as configurações.</span><span class="sxs-lookup"><span data-stu-id="2de72-163">On the **Configuration** blade, you define key and value pairs to supply configurations.</span></span>

8. <span data-ttu-id="2de72-164">Quando terminar, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="2de72-164">When you are done, choose **OK**.</span></span>

9. <span data-ttu-id="2de72-165">Na **folha Adicionar configuração de aplicativo**, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="2de72-165">On the **Add app configuration blade**, choose **Create**.</span></span>

<span data-ttu-id="2de72-166">A nova configuração é criada e exibida na folha Configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2de72-166">The new configuration is created, and displayed on the App configuration blade.</span></span>

<span data-ttu-id="2de72-167">Em seguida, continue a [Atribuir](apps-deploy.md) e a [Monitor](apps-monitor.md) o aplicativo como de costume.</span><span class="sxs-lookup"><span data-stu-id="2de72-167">Then, continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>

<span data-ttu-id="2de72-168">Quando o aplicativo atribuído (integrado ao SDK do Aplicativo do Intune) for executado em um dispositivo, ele será executado com as configurações definidas na política de configuração direcionada para o MAM.</span><span class="sxs-lookup"><span data-stu-id="2de72-168">When the assigned app (integrated with the Intune APP SDK) is run on a device, it will run with the settings that you configured in the MAM targeted configuration policy.</span></span> <span data-ttu-id="2de72-169">O aplicativo atribuído precisa ter integrado a versão com suporte do SDK do Aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="2de72-169">The assigned app needs to have integrated the supported version of the Intune APP SDK.</span></span> <span data-ttu-id="2de72-170">Para obter mais informações sobre os requisitos de desenvolvimento de aplicativo para usar políticas de Configuração Direcionada para o MAM, consulte [Guia de integração do SDK do Aplicativo do Intune para iOS](https://docs.microsoft.com/intune/app-sdk-ios).</span><span class="sxs-lookup"><span data-stu-id="2de72-170">For more information about the app development requirements to use MAM Targeted Configuration policies, see [iOS Intune APP SDK Integration Guide](https://docs.microsoft.com/intune/app-sdk-ios).</span></span>

<span data-ttu-id="2de72-171">Para obter mais informações sobre as funcionalidades de nossa API do Graph em relação aos valores de configuração direcionada para o MAM, consulte [Referência da API do Graph para a Configuração Direcionada para o MAM](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span><span class="sxs-lookup"><span data-stu-id="2de72-171">For more information about the capabilities our Graph API with respect to the MAM targeted config values, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span>

## <span data-ttu-id="2de72-172">Informações sobre o formato de arquivo XML</span><span class="sxs-lookup"><span data-stu-id="2de72-172">Information about the XML file format</span></span>
<a id="information-about-the-xml-file-format" class="xliff"></a>

<span data-ttu-id="2de72-173">O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:</span><span class="sxs-lookup"><span data-stu-id="2de72-173">Intune supports the following data types in a property list:</span></span>

- <span data-ttu-id="2de72-174">&lt;inteiro&gt;</span><span class="sxs-lookup"><span data-stu-id="2de72-174">&lt;integer&gt;</span></span>
- <span data-ttu-id="2de72-175">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="2de72-175">&lt;real&gt;</span></span>
- <span data-ttu-id="2de72-176">&lt;cadeia de caracteres&gt;</span><span class="sxs-lookup"><span data-stu-id="2de72-176">&lt;string&gt;</span></span>
- <span data-ttu-id="2de72-177">&lt;matriz&gt;</span><span class="sxs-lookup"><span data-stu-id="2de72-177">&lt;array&gt;</span></span>
- <span data-ttu-id="2de72-178">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="2de72-178">&lt;dict&gt;</span></span>
- <span data-ttu-id="2de72-179">&lt;true /&gt; ou &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="2de72-179">&lt;true /&gt; or &lt;false /&gt;</span></span>

<span data-ttu-id="2de72-180">Para obter mais informações sobre tipos de dados, consulte o artigo [sobre listas de propriedades](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) na biblioteca do desenvolvedor do iOS.</span><span class="sxs-lookup"><span data-stu-id="2de72-180">For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.</span></span>

<span data-ttu-id="2de72-181">Além disso, o Intune dá suporte aos seguintes tipos de token na lista de propriedades:</span><span class="sxs-lookup"><span data-stu-id="2de72-181">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="2de72-182">\{\{userprincipalname\}\} – (Exemplo: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="2de72-182">\{\{userprincipalname\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="2de72-183">\{\{mail\}\} – (Exemplo: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="2de72-183">\{\{mail\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="2de72-184">\{\{partialupn\}\} – (Exemplo: **Samuel**)</span><span class="sxs-lookup"><span data-stu-id="2de72-184">\{\{partialupn\}\} - (Example: **John**)</span></span>
- <span data-ttu-id="2de72-185">\{\{accountid\}\} – (Exemplo: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span><span class="sxs-lookup"><span data-stu-id="2de72-185">\{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span></span>
- <span data-ttu-id="2de72-186">\{\{deviceid\}\} – (Exemplo: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span><span class="sxs-lookup"><span data-stu-id="2de72-186">\{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span></span>
- <span data-ttu-id="2de72-187">\{\{userid\}\} – (Exemplo: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span><span class="sxs-lookup"><span data-stu-id="2de72-187">\{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span></span>
- <span data-ttu-id="2de72-188">\{\{username\}\} – (Exemplo: **Samuel Ferreira**)</span><span class="sxs-lookup"><span data-stu-id="2de72-188">\{\{username\}\} - (Example: **John Doe**)</span></span>
- <span data-ttu-id="2de72-189">\{\{serialnumber\}\} – (Exemplo: **F4KN99ZUG5V2**) para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="2de72-189">\{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices</span></span>
- <span data-ttu-id="2de72-190">\{\{serialnumberlast4digits\}\} – (Exemplo: **G5V2**) para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="2de72-190">\{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices</span></span>

<span data-ttu-id="2de72-191">Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.</span><span class="sxs-lookup"><span data-stu-id="2de72-191">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <span data-ttu-id="2de72-192">Exemplo de formato de arquivo XML de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="2de72-192">Example format for an app configuration XML file</span></span>
<a id="example-format-for-an-app-configuration-xml-file" class="xliff"></a>

<span data-ttu-id="2de72-193">Quando você cria um arquivo de configuração de aplicativo, você pode especificar um ou mais dos seguintes valores usando este formato:</span><span class="sxs-lookup"><span data-stu-id="2de72-193">When you create an app configuration file, you can specify one or more of the following values by using this format:</span></span>

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>

```
