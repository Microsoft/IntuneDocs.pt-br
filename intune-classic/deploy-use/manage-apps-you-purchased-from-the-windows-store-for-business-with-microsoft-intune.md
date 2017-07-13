---
title: Gerenciar aplicativos da Windows Store para Empresas
description: "Conecte o Microsoft Intune à Windows Store para Empresas se deseja gerenciar e implantar aplicativos adquiridos por volume no console do Intune"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e38d47d-0c5e-40ce-b379-29d3657f5c28
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 888d825fb9955e97b49e54a0c36ab882055076d8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="e90ff-103">Gerenciar aplicativos adquiridos na Windows Store para Empresas com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e90ff-103">Manage apps you purchased from the Windows Store for Business with Microsoft Intune</span></span>
<a id="manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e90ff-104">O [Windows Store para a Empresa](https://www.microsoft.com/business-store) fornece um local para encontrar e comprar aplicativos para sua organização, individualmente ou em um volume.</span><span class="sxs-lookup"><span data-stu-id="e90ff-104">The [Windows Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume.</span></span> <span data-ttu-id="e90ff-105">Ao conectar o repositório no Microsoft Intune, você pode gerenciar os aplicativos adquiridos por volume no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-105">By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Intune console.</span></span> <span data-ttu-id="e90ff-106">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e90ff-106">For example:</span></span>
* <span data-ttu-id="e90ff-107">Você pode sincronizar a lista de aplicativos que você adquiriu do armazenamento com o Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-107">You can synchronize the list of apps you have purchased from the store with Intune.</span></span>
* <span data-ttu-id="e90ff-108">Os aplicativos que são sincronizados aparecem no console de administração do Intune e você pode implantá-los como quaisquer outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e90ff-108">Apps that are synchronized appear in the Intune administration console, and you can deploy these like any other apps.</span></span>
* <span data-ttu-id="e90ff-109">Você pode controlar quantas licenças estão disponíveis e quantas estão sendo usadas no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-109">You can track how many licenses are available, and how many are being used in the Intune administration console.</span></span>
* <span data-ttu-id="e90ff-110">O Intune bloqueará a implantação e a instalação de aplicativos caso haja um número insuficiente de licenças disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e90ff-110">Intune blocks deployment and installation of apps if there are an insufficient number of licenses available.</span></span>

## <span data-ttu-id="e90ff-111">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="e90ff-111">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="e90ff-112">Examine as seguintes informações antes de iniciar a sincronização e a implantação de aplicativos da Windows Store for Business:</span><span class="sxs-lookup"><span data-stu-id="e90ff-112">Review the following information before you start syncing and deploying apps from the Windows Store for Business:</span></span>
* <span data-ttu-id="e90ff-113">Você deve configurar o Intune como a autoridade de gerenciamento de dispositivo móvel para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e90ff-113">You must configure Intune as the mobile device management authority for your organization.</span></span> <span data-ttu-id="e90ff-114">Para obter mais informações, consulte [Pre-requisitos para registrar dispositivos no Microsoft Intune](prerequisites-for-enrollment.md).</span><span class="sxs-lookup"><span data-stu-id="e90ff-114">For more information, see [Prerequisites for enrolling devices in Microsoft Intune](prerequisites-for-enrollment.md).</span></span>
* <span data-ttu-id="e90ff-115">Você deve se inscrever para uma conta na Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="e90ff-115">You must have signed up for an account on the Windows Store for Business.</span></span>
* <span data-ttu-id="e90ff-116">Depois que você tiver associado uma conta da Windows Business Store ao Intune, não será possível alterar para uma conta diferente no futuro.</span><span class="sxs-lookup"><span data-stu-id="e90ff-116">Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.</span></span>
* <span data-ttu-id="e90ff-117">Aplicativos adquiridos da loja não poderão ser adicionados ao Intune ou excluídos do Intune manualmente.</span><span class="sxs-lookup"><span data-stu-id="e90ff-117">Apps purchased from the store cannot be manually added to or deleted from Intune.</span></span> <span data-ttu-id="e90ff-118">Eles só poderão ser sincronizados com a Windows Store for Business.</span><span class="sxs-lookup"><span data-stu-id="e90ff-118">They can only be synchronized with the Windows Store for Business.</span></span>
* <span data-ttu-id="e90ff-119">O Intune sincroniza apenas aplicativos online licenciados que você adquiriu da Windows Store for Business.</span><span class="sxs-lookup"><span data-stu-id="e90ff-119">Intune synchronizes only online licensed apps you have purchased from the Windows Store for Business.</span></span>
* <span data-ttu-id="e90ff-120">Os dispositivos devem ser ingressados nos Serviços de Domínio do Active Directory ou ingressados no local de trabalho para que seja possível usar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e90ff-120">Devices must be joined to Active Directory Domain Services, or workplace-joined, to use this capability.</span></span>
* <span data-ttu-id="e90ff-121">Dispositivos registrados devem estar usando a versão 1511 do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="e90ff-121">Enrolled devices must be using the 1511 release of Windows 10.</span></span>

## <span data-ttu-id="e90ff-122">Associe sua conta da Windows Store for Business ao Intune</span><span class="sxs-lookup"><span data-stu-id="e90ff-122">Associate your Windows Store for Business account with Intune</span></span>
<a id="associate-your-windows-store-for-business-account-with-intune" class="xliff"></a>
<span data-ttu-id="e90ff-123">Antes de habilitar a sincronização no console do Intune, você deve configurar sua conta de repositório para usar o Intune como uma ferramenta de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="e90ff-123">Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:</span></span>
1. <span data-ttu-id="e90ff-124">Certifique-se de entrar no repositório de negócios usando a mesma conta de locatário usada para entrar no Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-124">Ensure that you sign into the Business Store using the same tenant account you use to sign into Intune.</span></span>
2. <span data-ttu-id="e90ff-125">Na Business Store, escolha **Configurações** > **Ferramentas de gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-125">In the Business Store, choose **Settings** > **Management tools**.</span></span>
3. <span data-ttu-id="e90ff-126">Na página Ferramentas de gerenciamento, escolha **Adicionar uma ferramenta de gerenciamento** e escolha **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-126">On the Management tools page, choose **Add a management tool**, and choose **Microsoft Intune**.</span></span>

> [!NOTE]
> <span data-ttu-id="e90ff-127">Se você está usando mais de uma ferramenta de gerenciamento para implantar aplicativos da Windows Store para Empresas, anteriormente, você podia associar apenas um deles à Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="e90ff-127">If you are using more than one management tool to deploy Windows Store for Business apps, previously, you could only associate one of these with the Windows Store for Business.</span></span> <span data-ttu-id="e90ff-128">Agora você pode associar várias ferramentas de gerenciamento com a loja, por exemplo, o Intune e o Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="e90ff-128">You can now associate multiple management tools with the store, for example, Intune and Configuration Manager.</span></span>

<span data-ttu-id="e90ff-129">Agora você pode continuar e configurar a sincronização no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-129">You can now continue, and set up synchronization in the Intune console.</span></span>

## <span data-ttu-id="e90ff-130">Configurar sincronização</span><span class="sxs-lookup"><span data-stu-id="e90ff-130">Configure synchronization</span></span>
<a id="configure-synchronization" class="xliff"></a>

1. <span data-ttu-id="e90ff-131">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-131">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
2. <span data-ttu-id="e90ff-132">No espaço de trabalho **Administração**, expanda **Gerenciamento de Dispositivo Móvel** > **Windows** e escolha **Store para Empresas**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-132">In the **Administration** workspace, expand **Mobile Device Management** > **Windows**, and then choose **Store for Business**.</span></span>
3. <span data-ttu-id="e90ff-133">Na página **Windows Store for Business**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e90ff-133">On the **Windows Store for Business** page, do the following:</span></span>
 * <span data-ttu-id="e90ff-134">Se você ainda tiver feito isso, clique no link para inscrever-se para a Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="e90ff-134">If you haven't already done so, click the link to sign-up for the Windows Store for Business.</span></span>
 * <span data-ttu-id="e90ff-135">Quando você estiver se inscrito, clique em **Configurar Sincronização**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-135">Once you are signed-up, choose **Configure Sync**.</span></span>
4. <span data-ttu-id="e90ff-136">Na caixa de diálogo **Configurar sincronização do aplicativo da Windows Store for Business**, selecione **Habilitar sincronização da Windows Store for Business**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-136">In the **Configure Windows Store for Business app sync** dialog box, select **Enable Windows Store for Business sync**.</span></span>
5. <span data-ttu-id="e90ff-137">Na lista suspensa **Idioma**, escolha o idioma em que os aplicativos da Windows Store for Business serão exibidos no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-137">From the **Language** drop-down list, choose the language in which apps from the Windows Store for Business will be displayed in the Intune console.</span></span> <span data-ttu-id="e90ff-138">Independentemente do idioma em que eles são exibidos, eles serão instalados no idioma do usuário final quando disponível.</span><span class="sxs-lookup"><span data-stu-id="e90ff-138">Regardless of the language in which they are displayed, they will be installed in the end user's language when available.</span></span>
6. <span data-ttu-id="e90ff-139">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e90ff-139">Click **OK**.</span></span>

## <span data-ttu-id="e90ff-140">Sincronizar aplicativos</span><span class="sxs-lookup"><span data-stu-id="e90ff-140">Synchronize apps</span></span>
<a id="synchronize-apps" class="xliff"></a>

1. <span data-ttu-id="e90ff-141">Na página **Windows Store para Empresas**, escolha **Sincronizar agora** para sincronizar os aplicativos que você comprou da loja com o Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-141">On the **Windows Store for Business** page, choose **Sync now** to synchronize the apps you've purchased from the store with Intune.</span></span>
2. <span data-ttu-id="e90ff-142">No espaço de trabalho **Aplicativos**, escolha **Aplicativos** > **Aplicativos Adquiridos com Base em Volume** para exibir os aplicativos que você pode implantar e verificar se os aplicativos comprados foram importados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e90ff-142">In the **Apps** workspace, choose **Apps** > **Volume-Purchased Apps** to view the apps you can deploy, and to verify that your purchased apps were imported correctly.</span></span> <span data-ttu-id="e90ff-143">Os aplicativos nesse nó são exibidos com o número total de licenças que você tem e o número de licenças disponíveis que você tem.</span><span class="sxs-lookup"><span data-stu-id="e90ff-143">The apps in this node are displayed with the total number of licenses you own, and the number of licenses you have available.</span></span>
<span data-ttu-id="e90ff-144">Por exemplo, você pode adquirir o aplicativo de Portal da Empresa (licenciado online) da Windows Store para Empresas, sincronizá-lo com o console do Intune e, em seguida, implantá-lo como um aplicativo necessário nos dispositivos Windows 10 em questão.</span><span class="sxs-lookup"><span data-stu-id="e90ff-144">For example, you can purchase the Company Portal app (online licensed) from the Windows Store for Business, sync it to the Intune console and then deploy this as a required app in to the required Windows 10 devices.</span></span> 


## <span data-ttu-id="e90ff-145">Implantar aplicativos</span><span class="sxs-lookup"><span data-stu-id="e90ff-145">Deploy apps</span></span>
<a id="deploy-apps" class="xliff"></a>

<span data-ttu-id="e90ff-146">Implante aplicativos da loja da mesma maneira que você implanta qualquer aplicativo do Intune.</span><span class="sxs-lookup"><span data-stu-id="e90ff-146">You deploy apps from the store in the same way you deploy any other Intune app.</span></span> <span data-ttu-id="e90ff-147">Para obter mais informações, consulte [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) (Implantar aplicativos no Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="e90ff-147">For more information, see [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>
<span data-ttu-id="e90ff-148">Quando você implanta um aplicativo da Windows Store for Business, uma licença é usada por cada usuário que instala o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e90ff-148">When you deploy a Windows Store for Business app, a license is used by each user who installs the app.</span></span> <span data-ttu-id="e90ff-149">Se você usar todas as licenças disponíveis para um aplicativo implantado, você não poderá implantar mais cópias.</span><span class="sxs-lookup"><span data-stu-id="e90ff-149">If you use all of the available licenses for a deployed app, you will not be able to deploy any more copies.</span></span> <span data-ttu-id="e90ff-150">Você deve executar uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e90ff-150">You must take one of the following actions:</span></span>
* <span data-ttu-id="e90ff-151">Desinstalar o aplicativo de alguns dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e90ff-151">Uninstall the app from some devices.</span></span>
* <span data-ttu-id="e90ff-152">Reduzir o escopo da implantação atual para o destino apenas os usuários para os quais você tiver licenças suficientes.</span><span class="sxs-lookup"><span data-stu-id="e90ff-152">Reduce the scope of the current deployment to target only the users you have sufficient licenses for.</span></span>
* <span data-ttu-id="e90ff-153">Comprar mais cópias do aplicativo da Windows Store para Empresas.</span><span class="sxs-lookup"><span data-stu-id="e90ff-153">Buy more copies of the app from the Windows Store for Business.</span></span>

> [!Important]
> <span data-ttu-id="e90ff-154">Aplicativos implantados só estão disponíveis para o usuário que originalmente registrou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e90ff-154">Deployed apps are only available to the user who originally enrolled the device.</span></span> <span data-ttu-id="e90ff-155">Nenhum outro usuário pode acessar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e90ff-155">No other users can access the app.</span></span>


### <span data-ttu-id="e90ff-156">Consulte também</span><span class="sxs-lookup"><span data-stu-id="e90ff-156">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="e90ff-157">Adicionar aplicativos a dispositivos móveis no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e90ff-157">Add apps for mobile devices in Microsoft Intune</span></span>](add-apps-for-mobile-devices-in-microsoft-intune.md)
