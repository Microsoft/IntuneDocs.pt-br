---
title: Gerenciar aplicativos iOS adquiridos por volume
description: "Use o Intune para gerenciar aplicativos adquiridos por volume na Apple, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f2600864eaf127810639e76932adbd422b4e0008
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="8fdd6-103">Gerenciar aplicativos iOS adquiridos por meio de um programa de compra por volume com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8fdd6-103">Manage iOS apps you purchased through a volume-purchase program with Microsoft Intune</span></span>
<a id="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8fdd6-104">A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-104">The iOS app store lets you purchase multiple licenses for an app that you want to run in your company.</span></span> <span data-ttu-id="8fdd6-105">Isso ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-105">This helps you reduce the administrative overhead of tracking multiple purchased copies of apps.</span></span>

<span data-ttu-id="8fdd6-106">O Microsoft Intune ajuda a gerenciar aplicativos adquiridos por meio desse programa, importando as informações de licença da loja de aplicativos, acompanhando a quantidade de licenças utilizadas e impedindo a instalação de um número maior de cópias de seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-106">Microsoft Intune helps you manage apps that you purchased through this program by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.</span></span>

> [!Important]
> <span data-ttu-id="8fdd6-107">Atualmente, o Intune atribui licenças de aplicativo do iOS VPP (Volume Purchase Program) for Business a usuários, não a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-107">Currently, Intune assigns iOS Volume Purchase Program for Business (VPP) app licenses to users and not devices.</span></span> <span data-ttu-id="8fdd6-108">Por isso, os usuários devem inserir sua senha de ID da Apple para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-108">Because of this, users must enter their Apple ID password to install the app.</span></span>
> <span data-ttu-id="8fdd6-109">Não há suporte para o Apple Volume Purchase Program for Education nesta versão.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-109">The Apple Volume Purchase Program for Education is not supported in this release.</span></span>

## <span data-ttu-id="8fdd6-110">Gerenciar aplicativos adquiridos por volume para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="8fdd6-110">Manage volume-purchased apps for iOS devices</span></span>
<a id="manage-volume-purchased-apps-for-ios-devices" class="xliff"></a>
<span data-ttu-id="8fdd6-111">Você compra várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/).</span><span class="sxs-lookup"><span data-stu-id="8fdd6-111">You purchase multiple licenses for iOS apps through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/).</span></span> <span data-ttu-id="8fdd6-112">Isso envolve a configuração de uma conta do Apple VPP no site da Apple e upload do token do Apple VPP no Intune.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-112">This involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="8fdd6-113">Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-113">You can then synchronize your volume purchase information with Intune and track your volume-purchased app use.</span></span>

## <span data-ttu-id="8fdd6-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8fdd6-114">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="8fdd6-115">Antes de começar, você precisará obter um token do Apple VPP e carregá-lo em sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-115">Before you start, you'll need to get a VPP token from Apple and upload this to your Intune account.</span></span> <span data-ttu-id="8fdd6-116">Além disso, você deve compreender o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8fdd6-116">Additionally, you should understand the following:</span></span>

* <span data-ttu-id="8fdd6-117">O Intune dá suporte à adição de até 256 tokens VPP.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-117">Intune supports adding up to 256 VPP tokens.</span></span>
* <span data-ttu-id="8fdd6-118">Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-118">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="8fdd6-119">Cada token é válido por um ano.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-119">Each token is valid for one year.</span></span>
* <span data-ttu-id="8fdd6-120">Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-120">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="8fdd6-121">É possível iniciar uma sincronização manual a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-121">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="8fdd6-122">Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-122">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="8fdd6-123">Isso pode resultar na perda de registros de usuário e atribuição de licença.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-123">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="8fdd6-124">Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="8fdd6-124">Before you start to use iOS VPP with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="8fdd6-125">O Intune não sincronizará essas contas de usuário no Intune como medida de segurança.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-125">Intune will not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="8fdd6-126">O Intune somente sincronizará os dados do serviço do Apple VPP criados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-126">Intune will only synchronize data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="8fdd6-127">Somente será possível implantar aplicativos VPP do iOS em dispositivos do usuário que foram registrados usando o DEP (Protocolo de Registro de Dispositivo) se a afinidade do usuário para o dispositivo estiver configurada.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-127">You can only deploy iOS VPP apps to user's devices that were enrolled using the Device Enrollment Protocol (DEP) if user affinity for the device is configured.</span></span>

## <span data-ttu-id="8fdd6-128">Obter e carregar um token de VPP da Apple</span><span class="sxs-lookup"><span data-stu-id="8fdd6-128">To get and upload an Apple VPP token</span></span>
<a id="to-get-and-upload-an-apple-vpp-token" class="xliff"></a>

1.  <span data-ttu-id="8fdd6-129">No [console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Administrador** &gt; **iOS e Mac OS X** &gt;  **Volume Purchase Program**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-129">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **iOS and Mac OS X** &gt;  **Volume Purchase Program**.</span></span>

2.  <span data-ttu-id="8fdd6-130">Escolha o link **Conta do Apple VPP**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-130">Choose the **Apple VPP Account** link.</span></span> <span data-ttu-id="8fdd6-131">Se você ainda não fez isso, inscreva-se no Volume Purchase Program for Business.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-131">If you haven't already, sign up for the Volume Purchase Program for Business.</span></span> <span data-ttu-id="8fdd6-132">Depois de se inscrever, baixe o token do Apple VPP em sua conta.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-132">After you sign up, download the Apple VPP token for your account.</span></span>

3.  <span data-ttu-id="8fdd6-133">Na página **Gerenciar VPP (Apple Volume Purchase Program)** do console do Intune, selecione **Carregar o token VPP**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-133">On the **Manage Apple Volume Purchase Program (VPP)** page of the Intune console, choose **Upload the VPP token**.</span></span>

4.  <span data-ttu-id="8fdd6-134">Na caixa de diálogo **Carregar token do VPP**, insira ou cole o nome do token do VPP e sua ID da Apple e escolha **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-134">In the **Upload the VPP token** dialog box, enter or paste the VPP token name and your Apple ID, and then choose **Upload**.</span></span>

5.  <span data-ttu-id="8fdd6-135">Na caixa de diálogo de aviso, marque a caixa para indicar que você entende que não é possível mudar para uma conta do VPP diferente mais tarde e escolha **Sim**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-135">In the warning dialog box, check the box to indicate that you understand that you can't change to a different VPP account later, and then choose **Yes**.</span></span>

<span data-ttu-id="8fdd6-136">Na página **Volume Purchase Program**, agora você pode exibir informações sobre o token do Apple VPP, incluindo quando foi sua última atualização, quando ele expirará e quando foi sincronizado pela última vez com o Intune.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-136">On the **Volume Purchase Program** page, you can now view information about the Apple VPP token, including when it was last updated, when it will expire, and when it was last synchronized with Intune.</span></span>

<span data-ttu-id="8fdd6-137">Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-137">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

## <span data-ttu-id="8fdd6-138">Implantar um aplicativo comprado por volume</span><span class="sxs-lookup"><span data-stu-id="8fdd6-138">To deploy a volume-purchased app</span></span>
<a id="to-deploy-a-volume-purchased-app" class="xliff"></a>

1.  <span data-ttu-id="8fdd6-139">No [console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Aplicativos** &gt; **Aplicativos** &gt; **Aplicativos de Compra por Volume**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-139">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps** &gt; **Volume-Purchased Apps**.</span></span> <span data-ttu-id="8fdd6-140">Esta lista mostra todos os aplicativos que foram sincronizados do serviço VPP da Apple.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-140">This list shows all apps that were synchronized from the Apple VPP service.</span></span>

2.  <span data-ttu-id="8fdd6-141">Escolha o aplicativo que você deseja implantar, escolha **Gerenciar Implantação** e use as instruções no tópico [Implantar aplicativos no Microsoft Intune](deploy-apps-in-microsoft-intune.md) para concluir o carregamento, a criação e a implantação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-141">Choose the app that you want to deploy, choose **Manage Deployment**, and then use the instructions in the [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) topic to finish uploading, creation, and deployment of the app.</span></span>

> [!TIP]
> <span data-ttu-id="8fdd6-142">Você deve escolher uma ação de implantação do tipo **Necessária**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-142">You must choose a deployment action of **Required**.</span></span> <span data-ttu-id="8fdd6-143">Atualmente, não há suporte para as instalações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-143">Available installations are not currently supported.</span></span> <span data-ttu-id="8fdd6-144">Além disso, é possível implantar o aplicativo somente em grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-144">Additionally, you can only deploy the app to user groups.</span></span>

<span data-ttu-id="8fdd6-145">Quando você implanta o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-145">When you deploy the app as a **Required** installation, each user who installs the app uses a license.</span></span>

<span data-ttu-id="8fdd6-146">Para recuperar uma licença, você deve alterar a ação de implantação para **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-146">To reclaim a license, you must change the deployment action to **Uninstall**.</span></span> <span data-ttu-id="8fdd6-147">A licença será recuperada após a desinstalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-147">The license will be reclaimed after the app is uninstalled.</span></span>

<span data-ttu-id="8fdd6-148">Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-148">When a user with an eligible device first tries to install a VPP app, they will be asked to join the Apple Volume Purchase program.</span></span> <span data-ttu-id="8fdd6-149">Eles devem fazer isso antes que a instalação do aplicativo prossiga.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-149">They must do this before the app installation proceeds.</span></span>

<span data-ttu-id="8fdd6-150">Se não houver nenhuma outra licença disponível, a implantação falhará.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-150">If there are no more licenses available, the deployment will fail.</span></span>

## <span data-ttu-id="8fdd6-151">Para monitorar aplicativos de VPP da Apple</span><span class="sxs-lookup"><span data-stu-id="8fdd6-151">To monitor Apple VPP apps</span></span>
<a id="to-monitor-apple-vpp-apps" class="xliff"></a>
<span data-ttu-id="8fdd6-152">Você pode monitorar quais aplicativos do VPP foram implantados e a quantidade de licenças utilizadas no espaço de trabalho **Aplicativos**, no nó **Aplicativos Adquiridos com Base em Volume**.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-152">You can monitor which VPP apps have been deployed, and how many licenses are used, from the **Apps** workspace in the **Volume-Purchased Apps** node.</span></span>

> [!TIP]
> <span data-ttu-id="8fdd6-153">Você também pode usar o aplicativo **Filtros** para examinar o status de cada instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8fdd6-153">You can also use app **Filters** to examine the status of each app installation.</span></span>

### <span data-ttu-id="8fdd6-154">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8fdd6-154">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="8fdd6-155">Implantar aplicativos no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8fdd6-155">Deploy apps in Microsoft Intune</span></span>](deploy-apps-in-microsoft-intune.md)
