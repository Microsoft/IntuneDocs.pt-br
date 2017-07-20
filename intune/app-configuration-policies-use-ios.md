---
title: "<span data-ttu-id=\"c06b1-101\">Como usar políticas de configuração de aplicativo do Intune para o iOS</span><span class=\"sxs-lookup\"><span data-stu-id=\"c06b1-101\">How to use Intune app configuration policies for iOS</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"c06b1-102\">Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo iOS quando ele é executado.</span><span class=\"sxs-lookup\"><span data-stu-id=\"c06b1-102\">Learn how to use app configuration policies to provide configuration data to an iOS app when it is run.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0cbcf70af17ba7690f54196790da04becd8ba1eb
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-ios"></a><span data-ttu-id="c06b1-103">Como usar as políticas de configuração de aplicativo do Microsoft Intune para o iOS</span><span class="sxs-lookup"><span data-stu-id="c06b1-103">How to use Microsoft Intune app configuration policies for iOS</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c06b1-104">Use políticas de configuração de aplicativo no Microsoft Intune para fornecer as configurações usadas quando os usuários executam um aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="c06b1-104">Use app configuration policies in Microsoft Intune to supply settings that are used when users run an iOS app.</span></span> <span data-ttu-id="c06b1-105">Por exemplo, um aplicativo pode exigir que os usuários especifiquem:</span><span class="sxs-lookup"><span data-stu-id="c06b1-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="c06b1-106">Um número da porta personalizado.</span><span class="sxs-lookup"><span data-stu-id="c06b1-106">A custom port number.</span></span>

-   <span data-ttu-id="c06b1-107">Configurações de idioma.</span><span class="sxs-lookup"><span data-stu-id="c06b1-107">Language settings.</span></span>

-   <span data-ttu-id="c06b1-108">Configurações de segurança.</span><span class="sxs-lookup"><span data-stu-id="c06b1-108">Security settings.</span></span>

-   <span data-ttu-id="c06b1-109">Configurações de identidade visual, como um logotipo da empresa.</span><span class="sxs-lookup"><span data-stu-id="c06b1-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="c06b1-110">Quando os usuários inserem essas configurações incorretamente, isso pode aumentar a carga do suporte técnico e reduzir a adoção de novos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c06b1-110">If users enter these settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="c06b1-111">As políticas de configuração de aplicativo podem ajudar a eliminar esses problemas, permitindo que você atribua essas configurações para os usuários em uma política antes que eles executem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c06b1-111">App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="c06b1-112">As configurações então são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="c06b1-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="c06b1-113">Você não atribui essas políticas diretamente para usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c06b1-113">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="c06b1-114">Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c06b1-114">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="c06b1-115">As configurações de política serão usadas sempre que o aplicativo verificá-las, normalmente na primeira vez em que é executado.</span><span class="sxs-lookup"><span data-stu-id="c06b1-115">The policy settings are used whenever the app checks for them (typically, the first time it is run).</span></span>

> [!TIP]
> <span data-ttu-id="c06b1-116">No momento, este tipo de política está disponível somente para dispositivos que executam o iOS 8.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="c06b1-116">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="c06b1-117">Ela dá suporte aos seguintes tipos de instalação de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c06b1-117">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="c06b1-118">**Aplicativo iOS gerenciado da loja de aplicativos**</span><span class="sxs-lookup"><span data-stu-id="c06b1-118">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="c06b1-119">**Pacote do aplicativo do iOS**</span><span class="sxs-lookup"><span data-stu-id="c06b1-119">**App package for iOS**</span></span>
>
> <span data-ttu-id="c06b1-120">Para obter mais informações sobre os tipos de instalação do aplicativo, consulte [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="c06b1-120">For more information about app installation types, see [How to add an app to Microsoft Intune](apps-add.md).</span></span>

## <a name="create-an-app-configuration-policy"></a><span data-ttu-id="c06b1-121">Criar uma política de configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="c06b1-121">Create an app configuration policy</span></span>
1.  <span data-ttu-id="c06b1-122">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="c06b1-122">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="c06b1-123">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c06b1-123">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="c06b1-124">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="c06b1-124">On the **Intune** blade, choose **Mobile apps**.</span></span>
4.  <span data-ttu-id="c06b1-125">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Políticas de Configuração de Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c06b1-125">In the **Mobile apps** workload, choose **Manage** > **App Configuration Policies**.</span></span>
5.  <span data-ttu-id="c06b1-126">Na folha da lista de políticas, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c06b1-126">In the list of policies blade, choose **Add**.</span></span>
6.  <span data-ttu-id="c06b1-127">Na folha **Adicionar Política de Configuração**, forneça um **Nome** e uma **Descrição** opcional para a política de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c06b1-127">On the **Add Configuration Policy** blade, supply a **Name** and an optional **Description** for the app configuration policy.</span></span>
7.  <span data-ttu-id="c06b1-128">Para o **Tipo de Registro do Dispositivo**, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c06b1-128">For **Device enrollment type**, choose one of:</span></span>
    - <span data-ttu-id="c06b1-129">**Registrado com o Intune** – Para aplicativos que integraram o SDK do aplicativo do Intune e são gerenciados pelo Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="c06b1-129">**Enrolled with Intune** - For apps that have integrated the Intune App SDK and are managed by Intune.</span></span>
    - <span data-ttu-id="c06b1-130">**Não registrado com o Intune** – Para aplicativos que integraram o SDK do aplicativo do Intune e não são gerenciados pelo Microsoft Intune ou são gerenciados por outra solução.</span><span class="sxs-lookup"><span data-stu-id="c06b1-130">**Not enrolled with Intune** - For apps that have integrated the Intune App SDK and are not managed by Intune, or are managed by another solution.</span></span>
8.  <span data-ttu-id="c06b1-131">Para **Plataforma**, escolha **iOS** (apenas para dispositivos registrados com o Microsoft Intune)</span><span class="sxs-lookup"><span data-stu-id="c06b1-131">For **Platform**, choose **iOS** (for devices enrolled with Intune only)</span></span>
9.  <span data-ttu-id="c06b1-132">Escolha **Aplicativo associado** e, na folha **Aplicativo associado**, escolha o aplicativo gerenciado para o qual você deseja aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c06b1-132">Choose **Associated App**, then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.</span></span>
10. <span data-ttu-id="c06b1-133">Na folha **Adicionar Política de Configuração**, escolha **Definições de configuração**</span><span class="sxs-lookup"><span data-stu-id="c06b1-133">On the **Add Configuration Policy** blade, choose **Configuration settings**</span></span>
11. <span data-ttu-id="c06b1-134">Na folha **Definições de configuração**, escolha como deseja especificar os valores de XML que compõem o perfil de configuração em:</span><span class="sxs-lookup"><span data-stu-id="c06b1-134">On the **Configuration Settings** blade, choose how you want to specify the XML values that make up the configuration profile from:</span></span>
    - <span data-ttu-id="c06b1-135">**Inserir dados XML** (apenas para dispositivos registrados com o Microsoft Intune) – Digite ou cole uma lista de propriedades XML que contém as definições de configuração do aplicativo desejadas.</span><span class="sxs-lookup"><span data-stu-id="c06b1-135">**Enter XML data** (for devices enrolled with Intune only) - Enter or paste an XML property list that contains the app configuration settings that you want.</span></span> <span data-ttu-id="c06b1-136">O formato da lista de propriedades XML varia dependendo do aplicativo que você está configurando.</span><span class="sxs-lookup"><span data-stu-id="c06b1-136">The format of the XML property list varies depending on the app you are configuring.</span></span> <span data-ttu-id="c06b1-137">Entre em contato com o fornecedor do aplicativo para obter detalhes sobre o formato exato a ser usado.</span><span class="sxs-lookup"><span data-stu-id="c06b1-137">Contact the supplier of the app for details about the exact format to use.</span></span>
<span data-ttu-id="c06b1-138">O Intune verifica se o XML que você inseriu está em um formato válido.</span><span class="sxs-lookup"><span data-stu-id="c06b1-138">Intune checks that the XML you entered is in a valid format.</span></span> <span data-ttu-id="c06b1-139">Ele não verifica se a lista de propriedades XML funcionará com o aplicativo ao qual está associada.</span><span class="sxs-lookup"><span data-stu-id="c06b1-139">It does not check that the XML property list works with the app that it is associated with.</span></span>
<span data-ttu-id="c06b1-140">Para obter mais informações sobre listas de propriedades XML, consulte [Compreender as listas de propriedades XML](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) na biblioteca do desenvolvedor do iOS.</span><span class="sxs-lookup"><span data-stu-id="c06b1-140">To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>
    - <span data-ttu-id="c06b1-141">**Usar o Designer de Configuração** (dispositivos registrados ou não com o Microsoft Intune) – Permite especificar os pares de chave e valor XML diretamente no portal.</span><span class="sxs-lookup"><span data-stu-id="c06b1-141">**Use configuration designer** (whether or not the device is enrolled with Intune) - Lets you specify XML key and value pairs directly in the portal.</span></span>
11. <span data-ttu-id="c06b1-142">Após terminar, volte para a folha **Adicionar Política de Configuração** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c06b1-142">When you're done, go back to the **Add Configuration Policy** blade, and hit **Create**.</span></span>

<span data-ttu-id="c06b1-143">A política será criada e exibida na folha da lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="c06b1-143">The policy is created and appears on the policies list blade.</span></span>



>[!Note]
><span data-ttu-id="c06b1-144">Use o [SDK do aplicativo do Intune](https://docs.microsoft.com/intune/app-sdk-ios) a fim de preparar aplicativos LOB para gerenciamento pelas políticas de proteção do aplicativo e pelas políticas de configuração de aplicativo do Microsoft Intune, para dispositivos registrados ou não por meio desta plataforma.</span><span class="sxs-lookup"><span data-stu-id="c06b1-144">You can use the [Intune App SDK](https://docs.microsoft.com/intune/app-sdk-ios) to prepare line-of-business apps to be managed by Intune app protection policies, and app configuration policies, whether the device is enrolled with Intune or not.</span></span> <span data-ttu-id="c06b1-145">Por exemplo, você pode usar uma política de configuração de aplicativo para configurar URLs bloqueadas e permitidas para o [Intune Managed Browser](app-configuration-managed-browser.md).</span><span class="sxs-lookup"><span data-stu-id="c06b1-145">For example, you can use an app configuration policy to configure allowed and blocked URLs for the [Intune Managed Browser](app-configuration-managed-browser.md).</span></span> <span data-ttu-id="c06b1-146">Quando um aplicativo é compatível com essas políticas, você pode configurá-lo usando uma política.</span><span class="sxs-lookup"><span data-stu-id="c06b1-146">Once an app is compatible with these policies, you can configure them using a policy.</span></span>


<span data-ttu-id="c06b1-147">Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c06b1-147">When the assigned app is run on a device, it runs with the settings that you configured in the app configuration policy.</span></span>
<span data-ttu-id="c06b1-148">Confira a documentação do aplicativo que você está configurando para saber mais sobre o que acontece quando uma ou mais políticas de configuração de aplicativo são conflitantes.</span><span class="sxs-lookup"><span data-stu-id="c06b1-148">See the documentation for the app you are configuring for information about what happens if one or more app configuration policies conflict.</span></span>

>[!Tip]
><span data-ttu-id="c06b1-149">Além disso, você pode usar a API do Graph para realizar essas tarefas.</span><span class="sxs-lookup"><span data-stu-id="c06b1-149">Additionally, you can use Graph API to accomplish these tasks.</span></span> <span data-ttu-id="c06b1-150">Para saber mais, confira [Configuração direcionada do MAM na referência da API do Graph](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span><span class="sxs-lookup"><span data-stu-id="c06b1-150">For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span>


## <a name="information-about-the-xml-file-format"></a><span data-ttu-id="c06b1-151">Informações sobre o formato de arquivo XML</span><span class="sxs-lookup"><span data-stu-id="c06b1-151">Information about the XML file format</span></span>

<span data-ttu-id="c06b1-152">O Intune dá suporte para os seguintes tipos de dados em uma lista de propriedades:</span><span class="sxs-lookup"><span data-stu-id="c06b1-152">Intune supports the following data types in a property list:</span></span>

- <span data-ttu-id="c06b1-153">&lt;inteiro&gt;</span><span class="sxs-lookup"><span data-stu-id="c06b1-153">&lt;integer&gt;</span></span>
- <span data-ttu-id="c06b1-154">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="c06b1-154">&lt;real&gt;</span></span>
- <span data-ttu-id="c06b1-155">&lt;cadeia de caracteres&gt;</span><span class="sxs-lookup"><span data-stu-id="c06b1-155">&lt;string&gt;</span></span>
- <span data-ttu-id="c06b1-156">&lt;matriz&gt;</span><span class="sxs-lookup"><span data-stu-id="c06b1-156">&lt;array&gt;</span></span>
- <span data-ttu-id="c06b1-157">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="c06b1-157">&lt;dict&gt;</span></span>
- <span data-ttu-id="c06b1-158">&lt;true /&gt; ou &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="c06b1-158">&lt;true /&gt; or &lt;false /&gt;</span></span>

<span data-ttu-id="c06b1-159">Para obter mais informações sobre tipos de dados, consulte o artigo [sobre listas de propriedades](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) na biblioteca do desenvolvedor do iOS.</span><span class="sxs-lookup"><span data-stu-id="c06b1-159">For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.</span></span>

<span data-ttu-id="c06b1-160">Além disso, o Intune dá suporte aos seguintes tipos de token na lista de propriedades:</span><span class="sxs-lookup"><span data-stu-id="c06b1-160">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="c06b1-161">\{\{userprincipalname\}\} – (Exemplo: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-161">\{\{userprincipalname\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="c06b1-162">\{\{mail\}\} – (Exemplo: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-162">\{\{mail\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="c06b1-163">\{\{partialupn\}\} – (Exemplo: **Samuel**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-163">\{\{partialupn\}\} - (Example: **John**)</span></span>
- <span data-ttu-id="c06b1-164">\{\{accountid\}\} – (Exemplo: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-164">\{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span></span>
- <span data-ttu-id="c06b1-165">\{\{deviceid\}\} – (Exemplo: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-165">\{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span></span>
- <span data-ttu-id="c06b1-166">\{\{userid\}\} – (Exemplo: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-166">\{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span></span>
- <span data-ttu-id="c06b1-167">\{\{username\}\} – (Exemplo: **Samuel Ferreira**)</span><span class="sxs-lookup"><span data-stu-id="c06b1-167">\{\{username\}\} - (Example: **John Doe**)</span></span>
- <span data-ttu-id="c06b1-168">\{\{serialnumber\}\} – (Exemplo: **F4KN99ZUG5V2**) para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="c06b1-168">\{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices</span></span>
- <span data-ttu-id="c06b1-169">\{\{serialnumberlast4digits\}\} – (Exemplo: **G5V2**) para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="c06b1-169">\{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices</span></span>

<span data-ttu-id="c06b1-170">Os caracteres \{\{ e \}\} são usados apenas por tipos de token e não devem ser usados para outras finalidades.</span><span class="sxs-lookup"><span data-stu-id="c06b1-170">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <a name="example-format-for-an-app-configuration-xml-file"></a><span data-ttu-id="c06b1-171">Exemplo de formato de arquivo XML de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="c06b1-171">Example format for an app configuration XML file</span></span>

<span data-ttu-id="c06b1-172">Quando você cria um arquivo de configuração de aplicativo, você pode especificar um ou mais dos seguintes valores usando este formato:</span><span class="sxs-lookup"><span data-stu-id="c06b1-172">When you create an app configuration file, you can specify one or more of the following values by using this format:</span></span>

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

## <a name="next-steps"></a><span data-ttu-id="c06b1-173">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c06b1-173">Next steps</span></span>

<span data-ttu-id="c06b1-174">Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.</span><span class="sxs-lookup"><span data-stu-id="c06b1-174">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>