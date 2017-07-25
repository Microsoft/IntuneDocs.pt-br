---
title: "Usar políticas de configuração de aplicativo móvel do iOS"
description: "Use políticas de configuração de aplicativo móvel no Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f13baeec9e0a38ac27ae42d1bc766cf22d73634
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c7f76-103">Configurar aplicativos iOS com as políticas de configuração de aplicativo móvel no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c7f76-103">Configure iOS apps with mobile app configuration policies in Microsoft Intune</span></span>
<a id="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c7f76-104">Use políticas de configuração de aplicativo móvel no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c7f76-104">Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app.</span></span> <span data-ttu-id="c7f76-105">Por exemplo, um aplicativo pode exigir que os usuários especifiquem:</span><span class="sxs-lookup"><span data-stu-id="c7f76-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="c7f76-106">Um número da porta personalizado.</span><span class="sxs-lookup"><span data-stu-id="c7f76-106">A custom port number.</span></span>

-   <span data-ttu-id="c7f76-107">Configurações de idioma.</span><span class="sxs-lookup"><span data-stu-id="c7f76-107">Language settings.</span></span>

-   <span data-ttu-id="c7f76-108">Configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="c7f76-108">Security settings.</span></span>

-   <span data-ttu-id="c7f76-109">Configurações de identidade visual, como um logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="c7f76-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="c7f76-110">Se os usuários inserirem essas configurações incorretamente, isso poderá aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c7f76-110">If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="c7f76-111">Políticas de configuração de aplicativo móvel podem ajudar a eliminar esses problemas, permitindo que você implante essas configurações para os usuários em uma política antes que eles executem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c7f76-111">Mobile app configuration policies can help you eliminate these problems by letting you deploy these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="c7f76-112">As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="c7f76-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="c7f76-113">Você não implanta essas políticas diretamente para usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c7f76-113">You do not deploy these policies directly to users and devices.</span></span> <span data-ttu-id="c7f76-114">Em vez disso, você associa uma política a um aplicativo e implanta o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c7f76-114">Instead, you associate a policy with an app, and then deploy the app.</span></span> <span data-ttu-id="c7f76-115">As configurações de política serão usadas sempre que o aplicativo verificá-las (normalmente, na primeira vez que é executado).</span><span class="sxs-lookup"><span data-stu-id="c7f76-115">The policy settings will be used whenever the app checks for them (typically, the first time it is run).</span></span>

> [!TIP]
> <span data-ttu-id="c7f76-116">No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="c7f76-116">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="c7f76-117">Ela dá suporte aos seguintes tipos de instalação de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c7f76-117">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="c7f76-118">**Aplicativo iOS gerenciado da loja de aplicativos**</span><span class="sxs-lookup"><span data-stu-id="c7f76-118">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="c7f76-119">**Pacote do aplicativo do iOS**</span><span class="sxs-lookup"><span data-stu-id="c7f76-119">**App package for iOS**</span></span>
>
> <span data-ttu-id="c7f76-120">Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Deploy apps with Microsoft Intune](deploy-apps.md) (Implantar aplicativos com o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="c7f76-120">For more information about app installation types, see [Deploy apps with Microsoft Intune](deploy-apps.md).</span></span>

## <span data-ttu-id="c7f76-121">Configurar uma política de configuração do aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="c7f76-121">Configure a mobile app configuration policy</span></span>
<a id="configure-a-mobile-app-configuration-policy" class="xliff"></a>

1.  <span data-ttu-id="c7f76-122">No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="c7f76-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="c7f76-123">Na lista de políticas, expanda **iOS**, escolha **Configuração do Aplicativo Móvel** e, em seguida, escolha **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="c7f76-123">In the list of policies, expand **iOS**, choose **Mobile App Configuration**, and then choose **Create Policy**.</span></span>

    > [!TIP]
    > <span data-ttu-id="c7f76-124">Você só pode definir configurações personalizadas para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="c7f76-124">You can configure only custom settings for this policy type.</span></span> <span data-ttu-id="c7f76-125">Configurações recomendadas não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c7f76-125">Recommended settings are not available.</span></span>

3.  <span data-ttu-id="c7f76-126">Na seção **Geral** da página **Criar Política**, forneça um nome e uma descrição opcional para a política de configuração de aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="c7f76-126">In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.</span></span>

4.  <span data-ttu-id="c7f76-127">Na seção **Política de Configuração de Aplicativo Móvel** da página, na caixa, digite ou cole uma lista de propriedades XML que contenha as definições de configuração do aplicativo que você quer.</span><span class="sxs-lookup"><span data-stu-id="c7f76-127">In the **Mobile App Configuration Policy** section of the page, in the box, enter or paste an  XML property list that contains the app configuration settings that you want.</span></span> <span data-ttu-id="c7f76-128">O formato da lista de propriedades XML vai variar dependendo do aplicativo que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="c7f76-128">The format of the XML property list will vary depending on the app you are configuring.</span></span> <span data-ttu-id="c7f76-129">Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.</span><span class="sxs-lookup"><span data-stu-id="c7f76-129">Contact the supplier of the app for details about the exact format to use.</span></span>

    > [!TIP]
    > <span data-ttu-id="c7f76-130">Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.</span><span class="sxs-lookup"><span data-stu-id="c7f76-130">To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>

5.  <span data-ttu-id="c7f76-131">Clique em **Validar** para garantir que o XML que você inseriu está em um formato de lista de propriedades válido.</span><span class="sxs-lookup"><span data-stu-id="c7f76-131">Click **Validate** to ensure that the XML that you entered is in a valid property list format.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c7f76-132">Quando você clica em **Validar**, o Intune verifica se o XML que você inseriu está em um formato válido.</span><span class="sxs-lookup"><span data-stu-id="c7f76-132">When you click **Validate**, Intune checks that the XML you entered is in a valid format.</span></span> <span data-ttu-id="c7f76-133">Ele não verifica se a lista de propriedades XML funcionará com o aplicativo a que está associada.</span><span class="sxs-lookup"><span data-stu-id="c7f76-133">It does not check that the XML property list will work with the app that it is associated with.</span></span>

6.  <span data-ttu-id="c7f76-134">Quando terminar, clique em **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="c7f76-134">When you are done, click **Save Policy**.</span></span>

<span data-ttu-id="c7f76-135">A nova política é exibida no nó **Políticas de Configuração** .</span><span class="sxs-lookup"><span data-stu-id="c7f76-135">The new policy is displayed in the **Configuration Policies** node.</span></span>

## <span data-ttu-id="c7f76-136">Informações sobre o formato de arquivo XML</span><span class="sxs-lookup"><span data-stu-id="c7f76-136">Information about the XML file format</span></span>
<a id="information-about-the-xml-file-format" class="xliff"></a>

<span data-ttu-id="c7f76-137">O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:</span><span class="sxs-lookup"><span data-stu-id="c7f76-137">Intune supports the following data types in a property list:</span></span>
    
- <span data-ttu-id="c7f76-138">&lt;inteiro&gt;</span><span class="sxs-lookup"><span data-stu-id="c7f76-138">&lt;integer&gt;</span></span>
- <span data-ttu-id="c7f76-139">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="c7f76-139">&lt;real&gt;</span></span>
- <span data-ttu-id="c7f76-140">&lt;cadeia de caracteres&gt;</span><span class="sxs-lookup"><span data-stu-id="c7f76-140">&lt;string&gt;</span></span>
- <span data-ttu-id="c7f76-141">&lt;matriz&gt;</span><span class="sxs-lookup"><span data-stu-id="c7f76-141">&lt;array&gt;</span></span>
- <span data-ttu-id="c7f76-142">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="c7f76-142">&lt;dict&gt;</span></span>
- <span data-ttu-id="c7f76-143">&lt;true /&gt; ou &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="c7f76-143">&lt;true /&gt; or &lt;false /&gt;</span></span>
     
<span data-ttu-id="c7f76-144">Para obter mais informações sobre tipos de dados, consulte o artigo [sobre listas de propriedades](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) na biblioteca do desenvolvedor do iOS.</span><span class="sxs-lookup"><span data-stu-id="c7f76-144">For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.</span></span>

<span data-ttu-id="c7f76-145">Além disso, o Intune dá suporte aos seguintes tipos de token na lista de propriedades:</span><span class="sxs-lookup"><span data-stu-id="c7f76-145">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="c7f76-146">\{\{userprincipalname\}\} – (Exemplo: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-146">\{\{userprincipalname\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="c7f76-147">\{\{mail\}\} – (Exemplo: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-147">\{\{mail\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="c7f76-148">\{\{partialupn\}\} – (Exemplo: **Samuel**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-148">\{\{partialupn\}\} - (Example: **John**)</span></span>
- <span data-ttu-id="c7f76-149">\{\{accountid\}\} – (Exemplo: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-149">\{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span></span>
- <span data-ttu-id="c7f76-150">\{\{deviceid\}\} – (Exemplo: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-150">\{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span></span>
- <span data-ttu-id="c7f76-151">\{\{userid\}\} – (Exemplo: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-151">\{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span></span>
- <span data-ttu-id="c7f76-152">\{\{username\}\} – (Exemplo: **Samuel Ferreira**)</span><span class="sxs-lookup"><span data-stu-id="c7f76-152">\{\{username\}\} - (Example: **John Doe**)</span></span>
- <span data-ttu-id="c7f76-153">\{\{serialnumber\}\} – (Exemplo: **F4KN99ZUG5V2**) para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="c7f76-153">\{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices</span></span>
- <span data-ttu-id="c7f76-154">\{\{serialnumberlast4digits\}\} – (Exemplo: **G5V2**) para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="c7f76-154">\{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices</span></span>
    
<span data-ttu-id="c7f76-155">Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.</span><span class="sxs-lookup"><span data-stu-id="c7f76-155">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <span data-ttu-id="c7f76-156">Associar uma política de configuração de aplicativo móvel a um aplicativo</span><span class="sxs-lookup"><span data-stu-id="c7f76-156">Associate a mobile app configuration policy with an app</span></span>
<a id="associate-a-mobile-app-configuration-policy-with-an-app" class="xliff"></a>
<span data-ttu-id="c7f76-157">Depois de criar uma política de configuração do aplicativo móvel, você deve associá-la ao aplicativo iOS ao qual você deseja aplicar as definições da política de configuração.</span><span class="sxs-lookup"><span data-stu-id="c7f76-157">After you have created a mobile app configuration policy, you must associate it with the iOS app to which you want the settings in the configuration policy to apply.</span></span>

<span data-ttu-id="c7f76-158">Para fazer isso, siga as etapas para criar uma implantação de aplicativo em [Adicionar aplicativos para dispositivos registrados ao Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) e [Implantar aplicativos com o Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="c7f76-158">To do this, follow the steps to create an app deployment in [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) and [Deploy apps with Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span> <span data-ttu-id="c7f76-159">Quando você chegar à página **Configuração do Aplicativo Móvel** do assistente, selecione a política que deseja associar ao aplicativo na lista suspensa **Política de Configuração do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="c7f76-159">When you reach the **Mobile App Configuration** page of the wizard, select the policy that you want to associate with the app from the **App Configuration Policy** drop-down list.</span></span>

<span data-ttu-id="c7f76-160">Em seguida, continue a implantar e monitorar a implantação de aplicativo como de costume.</span><span class="sxs-lookup"><span data-stu-id="c7f76-160">Then, continue to deploy and monitor the app deployment as usual.</span></span>

<span data-ttu-id="c7f76-161">Quando o aplicativo implantado é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="c7f76-161">When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="c7f76-162">Se uma ou mais políticas de configuração de aplicativo móvel entrarem em conflito, nenhuma delas será aplicada.</span><span class="sxs-lookup"><span data-stu-id="c7f76-162">If one or more mobile app configuration policies conflict, neither policy is enforced.</span></span> <span data-ttu-id="c7f76-163">O conflito será relatado no **Painel** do console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="c7f76-163">The conflict will be reported in the Intune administration console **Dashboard**.</span></span>

## <span data-ttu-id="c7f76-164">Exemplo de formato de um arquivo XML de configuração de aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="c7f76-164">Example format for a mobile app configuration XML file</span></span>
<a id="example-format-for-a-mobile-app-configuration-xml-file" class="xliff"></a>

<span data-ttu-id="c7f76-165">Quando você cria um arquivo de configuração de aplicativo móvel, você pode especificar um ou mais dos seguintes valores usando este formato:</span><span class="sxs-lookup"><span data-stu-id="c7f76-165">When you create a mobile app configuration file, you can specify one or more of the following values by using this format:</span></span>

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
