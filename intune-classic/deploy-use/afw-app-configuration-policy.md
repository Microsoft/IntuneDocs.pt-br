---
title: "Política de configuração de aplicativo do Android for Work"
description: "Use políticas de configuração de aplicativo móvel no Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo Android for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f2284920852de5a79cf47fee81922a5b069157c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="54816-103">Configurar aplicativos Android for Work com as políticas de configuração de aplicativo móvel no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="54816-103">Configure Android for Work apps with mobile app configuration policies in Microsoft Intune</span></span>
<a id="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="54816-104">Use políticas de configuração de aplicativo móvel no Microsoft Intune para fornecer as configurações que podem ser necessárias quando os usuários executam um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="54816-104">Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app.</span></span> <span data-ttu-id="54816-105">Por exemplo, um aplicativo pode exigir que os usuários especifiquem:</span><span class="sxs-lookup"><span data-stu-id="54816-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="54816-106">Um número de porta personalizado</span><span class="sxs-lookup"><span data-stu-id="54816-106">A custom port number</span></span>
-   <span data-ttu-id="54816-107">Configurações de idioma</span><span class="sxs-lookup"><span data-stu-id="54816-107">Language settings</span></span>
-   <span data-ttu-id="54816-108">Configurações de identidade visual, como um logotipo da empresa</span><span class="sxs-lookup"><span data-stu-id="54816-108">Branding settings such as a company logo</span></span>

<span data-ttu-id="54816-109">Se os usuários inserirem as configurações incorretamente, a carga do suporte técnico poderá aumentar e a adoção de novos aplicativos poderá ser mais lenta.</span><span class="sxs-lookup"><span data-stu-id="54816-109">If users enter settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="54816-110">As políticas de configuração de aplicativo móvel permitem implantar essas configurações nos dispositivos antes de os usuários executarem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="54816-110">Mobile app configuration policies let you deploy these settings to devices before users run the app.</span></span> <span data-ttu-id="54816-111">As configurações são fornecidas automaticamente e os usuários não precisam executar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="54816-111">The settings are supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="54816-112">Para usar as políticas de configuração do aplicativo, as configurações do aplicativo corporativo devem ter sido expostas pelo desenvolvedor ao criá-lo.</span><span class="sxs-lookup"><span data-stu-id="54816-112">To utilize app configuration policies, the app developer must have exposed enterprise app configurations when they created it.</span></span> <span data-ttu-id="54816-113">Por exemplo, o Google Chrome expõe as configurações que permitem que você defina indicadores padrão, sites autorizados e negados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="54816-113">For example, Google Chrome exposes settings that let you set default bookmarks, allowed and denied sites, and more.</span></span> <span data-ttu-id="54816-114">Entre em contato com o desenvolvedor do aplicativo para saber se há suporte para essas configurações e como especificá-las na política.</span><span class="sxs-lookup"><span data-stu-id="54816-114">Contact the developer of the app to see if these settings are supported and how to specify them in the policy.</span></span>

<span data-ttu-id="54816-115">A política de configuração do aplicativo é implantada para os mesmos usuários para os quais você implantou o aplicativo que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="54816-115">You deploy the app configuration policy to the same users to whom you have deployed the app you want to configure.</span></span> <span data-ttu-id="54816-116">As configurações do aplicativo são aplicadas quando o aplicativo é executado.</span><span class="sxs-lookup"><span data-stu-id="54816-116">App settings are applied when the app is run.</span></span>

## <span data-ttu-id="54816-117">Configurar uma política de configuração do aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="54816-117">Configure a mobile app configuration policy</span></span>
<a id="configure-a-mobile-app-configuration-policy" class="xliff"></a>

1.  <span data-ttu-id="54816-118">No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política** &gt; **Visão geral** &gt; **Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="54816-118">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="54816-119">Na lista de políticas, expanda **Android for Work**, escolha **Política de Configuração do Aplicativo Móvel (Android for Work)** e, em seguida, escolha **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="54816-119">In the list of policies, expand **Android for Work**, choose **Mobile App Configuration Policy (Android for Work)**, and then choose **Create Policy**.</span></span>

    > [!TIP]
    > <span data-ttu-id="54816-120">Você só pode definir configurações personalizadas para esse tipo de política.</span><span class="sxs-lookup"><span data-stu-id="54816-120">You can configure only custom settings for this policy type.</span></span> <span data-ttu-id="54816-121">Configurações recomendadas não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="54816-121">Recommended settings are not available.</span></span>

3.  <span data-ttu-id="54816-122">Na seção **Geral** da página **Criar Política**, forneça um nome e uma descrição opcional para a política de configuração de aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="54816-122">In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.</span></span>

4. <span data-ttu-id="54816-123">Na seção **Política de Configuração do Aplicativo Móvel** da página, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="54816-123">In the **Mobile App Configuration Policy** section of the page, specify the following information:</span></span>
    - <span data-ttu-id="54816-124">**ID do pacote do aplicativo ao qual essa configuração se aplica** – A ID do pacote pode ser encontrada na seção 'id =' da URL da página do aplicativo no Google Play.</span><span class="sxs-lookup"><span data-stu-id="54816-124">**Package ID for the application that this configuration applies to** - The package ID can be found in the 'id=' section of the app URL on it's Google Play page.</span></span> <span data-ttu-id="54816-125">Por exemplo, a ID do pacote do aplicativo Microsoft Excel é **com.microsoft.office.excel**.</span><span class="sxs-lookup"><span data-stu-id="54816-125">For example, the package ID for the Microsoft Excel app is **com.microsoft.office.excel**.</span></span>
    - <span data-ttu-id="54816-126">Na caixa de texto, insira os dados para as configurações do aplicativo que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="54816-126">In the text box, enter the data for the app settings you want to configure.</span></span> <span data-ttu-id="54816-127">Você pode obter essas configurações por meio do fornecedor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="54816-127">You get these settings from the supplier of the app.</span></span> <span data-ttu-id="54816-128">Nem todos os aplicativos dão suporte a essas configurações.</span><span class="sxs-lookup"><span data-stu-id="54816-128">Not all apps support these settings.</span></span>
5.  <span data-ttu-id="54816-129">Clique em **Validar** para garantir que os dados que você inseriu estão em um formato de lista de propriedades válido.</span><span class="sxs-lookup"><span data-stu-id="54816-129">Click **Validate** to ensure that the data that you entered is in a valid property list format.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="54816-130">Quando você clica em **Validar**, o Intune verifica se os dados de configuração que você inseriu estão em um formato válido.</span><span class="sxs-lookup"><span data-stu-id="54816-130">When you click **Validate**, Intune checks that the configuration data you entered is in a valid format.</span></span> <span data-ttu-id="54816-131">Ele não verifica se os dados funcionarão com o aplicativo a que estão associados.</span><span class="sxs-lookup"><span data-stu-id="54816-131">It does not check that the data will work with the app that it is associated with.</span></span>

6.  <span data-ttu-id="54816-132">Quando terminar, clique em **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="54816-132">When you are done, click **Save Policy**.</span></span>

<span data-ttu-id="54816-133">A nova política é exibida no nó **Políticas de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="54816-133">The new policy is displayed in the **Configuration Policies** node.</span></span>


## <span data-ttu-id="54816-134">Implantar a política de configuração do aplicativo</span><span class="sxs-lookup"><span data-stu-id="54816-134">Deploy the app configuration policy</span></span>
<a id="deploy-the-app-configuration-policy" class="xliff"></a>
<span data-ttu-id="54816-135">Depois de criar uma política de configuração de aplicativo móvel, você deve implantá-la para os mesmos usuários para os quais você implantará o aplicativo ao qual tais configurações se aplicam.</span><span class="sxs-lookup"><span data-stu-id="54816-135">After you have created a mobile app configuration policy, you must deploy it to the same users to whom you deploy the app to which the settings will apply.</span></span>

<span data-ttu-id="54816-136">Para obter mais informações sobre como implantar políticas, consulte [implantar uma política de configuração](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)</span><span class="sxs-lookup"><span data-stu-id="54816-136">For information about how to deploy policies, see [deploy a configuration policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)</span></span>

<span data-ttu-id="54816-137">Para obter informações sobre como implantar aplicativos em dispositivos Android for Work, consulte [Como implantar aplicativos Android for Work com o Intune](android-for-work-apps.md).</span><span class="sxs-lookup"><span data-stu-id="54816-137">For information about how to deploy apps to Android for Work devices, see [How to deploy Android for Work apps with Intune](android-for-work-apps.md).</span></span>

<span data-ttu-id="54816-138">Quando o aplicativo implantado é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="54816-138">When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="54816-139">Apenas uma política de configuração de aplicativo para cada aplicativo deve ser implantada para o usuário.</span><span class="sxs-lookup"><span data-stu-id="54816-139">Only deploy one app configuration policy for each app to a user.</span></span>
