---
title: Gerenciar aplicativos adquiridos por volume no iOS
titleSuffix: Intune on Azure
description: "Saiba como você pode sincronizar no Intune os aplicativos comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16b7ce81eb63a81534af2911b34904d870ac41ad
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="dddc1-103">Como gerenciar aplicativos iOS adquiridos por meio de um programa de aquisição com base em volume com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dddc1-103">How to manage iOS apps you purchased through a volume-purchase program with Microsoft Intune</span></span>
<a id="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="dddc1-104">A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa.</span><span class="sxs-lookup"><span data-stu-id="dddc1-104">The iOS app store lets you purchase multiple licenses for an app that you want to run in your company.</span></span> <span data-ttu-id="dddc1-105">Adquirir várias cópias de um aplicativo ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="dddc1-105">Purchasing multiple copies of an app helps you reduce the administrative overhead of tracking multiple purchased copies of apps.</span></span>

<span data-ttu-id="dddc1-106">O Microsoft Intune ajuda você a gerenciar aplicativos comprados por meio desse programa ao:</span><span class="sxs-lookup"><span data-stu-id="dddc1-106">Microsoft Intune helps you manage apps that you purchased through this program by:</span></span>

- <span data-ttu-id="dddc1-107">Importar as informações de licença da loja de aplicativos</span><span class="sxs-lookup"><span data-stu-id="dddc1-107">Importing the license information from the app store</span></span>
- <span data-ttu-id="dddc1-108">Acompanhar quantas licenças você usou</span><span class="sxs-lookup"><span data-stu-id="dddc1-108">Tracking how many of the licenses you have used</span></span>
- <span data-ttu-id="dddc1-109">Impedir a instalação de cópias do aplicativo além do que você possui</span><span class="sxs-lookup"><span data-stu-id="dddc1-109">Preventing you from installing more copies of the app than you own</span></span>

<span data-ttu-id="dddc1-110">Além disso, você pode sincronizar, gerenciar e atribuir livros adquiridos na loja Apple de programas adquiridos por volume com o Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-110">Additionally, you can synchronize, manage, and assign books you purchased from the Apple volume-purchase program store with Intune.</span></span> <span data-ttu-id="dddc1-111">Use a carga de trabalho **Books** no portal do Intune para gerenciar livros.</span><span class="sxs-lookup"><span data-stu-id="dddc1-111">Use the **Books** workload in the Intune portal to manage books.</span></span> <span data-ttu-id="dddc1-112">Os procedimentos para gerenciar livros são os mesmos utilizados para gerenciar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="dddc1-112">The procedures to manage books are the same as you use for managing apps.</span></span>
<span data-ttu-id="dddc1-113">Você deve ter carregado um token do Apple Volume Purchase Program para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="dddc1-113">You must have uploaded an Apple Volume Purchase Program token before you start.</span></span> <span data-ttu-id="dddc1-114">No momento, só é possível atribuir livros como uma instalação **Obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-114">Currently, you can only assign books as a **Required** install.</span></span>
<span data-ttu-id="dddc1-115">Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado.</span><span class="sxs-lookup"><span data-stu-id="dddc1-115">When you assign a book to a device, that device must have the built-in iBooks app installed.</span></span> <span data-ttu-id="dddc1-116">Caso contrário, o usuário final deverá reinstalar o aplicativo para ler o livro.</span><span class="sxs-lookup"><span data-stu-id="dddc1-116">If it is not, the end user must reinstall the app in order to read the book.</span></span> <span data-ttu-id="dddc1-117">No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.</span><span class="sxs-lookup"><span data-stu-id="dddc1-117">You cannot currently use Intune to restore removed built-in apps.</span></span>


## <span data-ttu-id="dddc1-118">Gerenciar aplicativos adquiridos por volume para dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="dddc1-118">Manage volume-purchased apps for iOS devices</span></span>
<a id="manage-volume-purchased-apps-for-ios-devices" class="xliff"></a>
<span data-ttu-id="dddc1-119">Compre várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store).</span><span class="sxs-lookup"><span data-stu-id="dddc1-119">Purchase multiple licenses for iOS apps through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) or the [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store).</span></span> <span data-ttu-id="dddc1-120">Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-120">This process involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="dddc1-121">Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.</span><span class="sxs-lookup"><span data-stu-id="dddc1-121">You can then synchronize your volume purchase information with Intune and track your volume-purchased app use.</span></span>

## <span data-ttu-id="dddc1-122">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dddc1-122">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="dddc1-123">Antes de começar, você precisará obter um token do VPP da Apple e carregá-lo em sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-123">Before you start, you need to get a VPP token from Apple and upload it to your Intune account.</span></span> <span data-ttu-id="dddc1-124">Além disso, você deve compreender os seguintes critérios:</span><span class="sxs-lookup"><span data-stu-id="dddc1-124">Additionally, you should understand the following criteria:</span></span>
=======
# Como gerenciar aplicativos iOS adquiridos por meio de um programa de aquisição com base em volume com o Microsoft Intune
<a id="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A loja de aplicativos iOS permite comprar várias licenças de um aplicativo que você deseja executar na empresa. Adquirir várias cópias de um aplicativo ajuda a reduzir a sobrecarga administrativa de acompanhar várias cópias adquiridas de aplicativos.

O Microsoft Intune ajuda você a gerenciar aplicativos comprados por meio desse programa ao:

- Importar as informações de licença da loja de aplicativos
- Acompanhar quantas licenças você usou
- Impedir a instalação de cópias do aplicativo além do que você possui

Além disso, você pode sincronizar, gerenciar e atribuir livros adquiridos na loja Apple de programas adquiridos por volume com o Intune. Use a carga de trabalho **Books** no portal do Intune para gerenciar livros. Os procedimentos para gerenciar livros são os mesmos utilizados para gerenciar aplicativos.
Você deve ter carregado um token do Apple Volume Purchase Program para fazer isso. No momento, só é possível atribuir livros como uma instalação **Obrigatória**.
Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado. Caso contrário, o usuário final deverá reinstalar o aplicativo para ler o livro. No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.
>>>>>>> live

* <span data-ttu-id="dddc1-125">Você pode associar vários tokens de programa de compra por volume a sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-125">You can associate multiple volume-purchase program tokens with your Intune account.</span></span>
* <span data-ttu-id="dddc1-126">Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-126">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="dddc1-127">Cada token é válido por um ano.</span><span class="sxs-lookup"><span data-stu-id="dddc1-127">Each token is valid for one year.</span></span>
* <span data-ttu-id="dddc1-128">Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="dddc1-128">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="dddc1-129">É possível iniciar uma sincronização manual a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="dddc1-129">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="dddc1-130">Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-130">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="dddc1-131">Isso pode resultar na perda de registros de usuário e atribuição de licença.</span><span class="sxs-lookup"><span data-stu-id="dddc1-131">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="dddc1-132">Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="dddc1-132">Before you start to use iOS VPP with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="dddc1-133">O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança.</span><span class="sxs-lookup"><span data-stu-id="dddc1-133">Intune does not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="dddc1-134">O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-134">Intune only synchronizes data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="dddc1-135">O Intune dá suporte à adição de até 256 tokens VPP.</span><span class="sxs-lookup"><span data-stu-id="dddc1-135">Intune supports adding up to 256 VPP tokens.</span></span>
* <span data-ttu-id="dddc1-136">Se você atribuir um aplicativo comprado por volume para um dispositivo registrado por meio de um Perfil de Registro de Dispositivo ou o Apple Configurator, apenas os aplicativos voltados para os dispositivos funcionarão.</span><span class="sxs-lookup"><span data-stu-id="dddc1-136">If you assign a volume-purchased app for a device enrolled through a Device Enrollment Profile or Apple Configurator, only apps that are targeted to devices work.</span></span> <span data-ttu-id="dddc1-137">Não é possível direcionar aplicativos comprados por volume para os usuários de um dispositivo DEP, que não têm nenhuma afinidade de usuário.</span><span class="sxs-lookup"><span data-stu-id="dddc1-137">You cannot target volume-purchased apps to users of a DEP device, which does not have any user affinity.</span></span>
* <span data-ttu-id="dddc1-138">Só há suporte para um token VPP para uso em uma conta do Intune por vez.</span><span class="sxs-lookup"><span data-stu-id="dddc1-138">A VPP token is only supported for use on one Intune account at a time.</span></span> <span data-ttu-id="dddc1-139">Não reutilize o mesmo token VPP para vários locatários do Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-139">Do not reuse the same VPP token for multiple Intune tenants.</span></span>
* <span data-ttu-id="dddc1-140">Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-140">When you assign VPP apps using the user licensing model to users or devices (with user affinity), each Intune user needs to be associated with a unique Apple ID or an email address when they accept the Apple terms and conditions on their device.</span></span>
<span data-ttu-id="dddc1-141">Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar m dispositivo para um novo usuário do Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-141">Ensure that when you set up a device for a new Intune user, you configure it with that users unique Apple ID or email address.</span></span> <span data-ttu-id="dddc1-142">A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usado em até 5 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dddc1-142">The Apple ID or email address and Intune user form a unique pair and can used on up to 5 devices.</span></span>

<<<<<<< HEAD

## <span data-ttu-id="dddc1-143">Obter e carregar um token de VPP da Apple</span><span class="sxs-lookup"><span data-stu-id="dddc1-143">To get and upload an Apple VPP token</span></span>
<a id="to-get-and-upload-an-apple-vpp-token" class="xliff"></a>

1. <span data-ttu-id="dddc1-144">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dddc1-144">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="dddc1-145">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-145">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="dddc1-146">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-146">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="dddc1-147">Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Configurar** > **Tokens de VPP do iOS**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-147">In the **Mobile Apps** workload, choose **Setup** > **iOS VPP Tokens**.</span></span>
2.  <span data-ttu-id="dddc1-148">Na folha da lista de tokens do VPP, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-148">On the list of VPP tokens blade, click **Add**.</span></span>
3.  <span data-ttu-id="dddc1-149">Na folha **Novo Token VPP**, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="dddc1-149">On the **New VPP Token** blade, specify the following information:</span></span>
    - <span data-ttu-id="dddc1-150">**Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education.</span><span class="sxs-lookup"><span data-stu-id="dddc1-150">**VPP token file** - If you haven't already, sign up for the Volume Purchase Program for Business or the program for Education.</span></span> <span data-ttu-id="dddc1-151">Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.</span><span class="sxs-lookup"><span data-stu-id="dddc1-151">After you sign up, download the Apple VPP token for your account and select it here.</span></span>
    - <span data-ttu-id="dddc1-152">**ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.</span><span class="sxs-lookup"><span data-stu-id="dddc1-152">**Apple ID** - Enter the Apple ID of the account associated with the volume-purchase program.</span></span>
    - <span data-ttu-id="dddc1-153">**Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-153">**Type of VPP account** - Choose from **Business** or **Education**.</span></span>
4. <span data-ttu-id="dddc1-154">Quando terminar, clique em **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-154">When you are done, click **Upload**.</span></span>

<span data-ttu-id="dddc1-155">O token é exibido na lista da folha de tokens.</span><span class="sxs-lookup"><span data-stu-id="dddc1-155">The token is displayed in the list of tokens blade.</span></span>

=======
## Gerenciar aplicativos adquiridos por volume para dispositivos iOS
<a id="manage-volume-purchased-apps-for-ios-devices" class="xliff"></a>
Compre várias licenças para aplicativos iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.  Você pode sincronizar suas informações de compra por volume com o Intune e controlar o uso do aplicativo adquirido por volume.

## Antes de começar
<a id="before-you-start" class="xliff"></a>
Antes de começar, você precisará obter um token do VPP da Apple e carregá-lo em sua conta do Intune. Além disso, você deve compreender os seguintes critérios:

* Você pode associar vários tokens de programa de compra por volume a sua conta do Intune.
* Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.
* Cada token é válido por um ano.
* Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia. É possível iniciar uma sincronização manual a qualquer momento.
* Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo. Isso pode resultar na perda de registros de usuário e atribuição de licença.
* Antes de começar a usar o iOS VPP com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel). O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança. O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.
* O Intune dá suporte à adição de até 256 tokens VPP.
* Se você atribuir um aplicativo comprado por volume para um dispositivo registrado por meio de um Perfil de Registro de Dispositivo ou o Apple Configurator, apenas os aplicativos voltados para os dispositivos funcionarão. Não é possível direcionar aplicativos comprados por volume para os usuários de um dispositivo DEP, que não têm nenhuma afinidade de usuário.
* Só há suporte para um token VPP para uso em uma conta do Intune por vez. Não reutilize o mesmo token VPP para vários locatários do Intune.
* Quando você atribui aplicativos VPP usando o modelo de licenciamento de usuário para usuários ou dispositivos (com afinidade de usuário), cada usuário do Intune precisa ser associado com uma ID da Apple exclusiva ou um endereço de email ao aceitar os termos e condições da Apple em seu dispositivo.
Use a ID da Apple exclusiva ou o endereço de email do usuário ao configurar m dispositivo para um novo usuário do Intune. A ID da Apple ou o endereço de email e o usuário do Intune formam um par exclusivo e podem ser usado em até 5 dispositivos.


## Obter e carregar um token de VPP da Apple
<a id="to-get-and-upload-an-apple-vpp-token" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1.  Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Configurar** > **Tokens de VPP do iOS**.
2.  Na folha da lista de tokens do VPP, clique em **Adicionar**.
3.  Na folha **Novo Token VPP**, especifique as seguintes informações:
    - **Arquivo de token do VPP** – Se ainda não tiver feito isso, inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education. Depois de se inscrever, baixe o token do Apple VPP em sua conta e selecione-o aqui.
    - **ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.
    - **Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.
4. Quando terminar, clique em **Carregar**.
>>>>>>> live

<span data-ttu-id="dddc1-156">Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-156">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

> [!NOTE]
> <span data-ttu-id="dddc1-157">O Microsoft Intune sincroniza apenas as informações de aplicativos publicamente disponíveis por meio da iTunes Store.</span><span class="sxs-lookup"><span data-stu-id="dddc1-157">Microsoft Intune only syncs information of Apps, which are publicly available through the iTunes Store.</span></span> <span data-ttu-id="dddc1-158">Ainda não há suporte para **aplicativos B2B personalizados para iOS**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-158">**Custom B2B Apps for iOS** are not yet supported.</span></span> <span data-ttu-id="dddc1-159">Se seu cenário for voltado para esses aplicativos, as informações de aplicativo não serão sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="dddc1-159">If your scenario targets such apps, the app information is not synchronized.</span></span>

## <span data-ttu-id="dddc1-160">Para atribuir um aplicativo comprado por volume</span><span class="sxs-lookup"><span data-stu-id="dddc1-160">To assign a volume-purchased app</span></span>
<a id="to-assign-a-volume-purchased-app" class="xliff"></a>

<<<<<<< HEAD
1. <span data-ttu-id="dddc1-161">Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos Licenciados**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-161">In the **Mobile Apps** workload, choose **Manage** > **Licensed Apps**.</span></span>
2. <span data-ttu-id="dddc1-162">Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir e selecione “**...**”</span><span class="sxs-lookup"><span data-stu-id="dddc1-162">On the list of apps blade, choose the app you want to assign, and then choose '**...**'</span></span><span data-ttu-id="dddc1-163"> > **Atribuir Grupos**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-163"> > **Assign Groups**.</span></span>
3. <span data-ttu-id="dddc1-164">Na folha <*nome do aplicativo*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-164">On the <*app name*> - **Groups Assigned** blade, choose **Manage** > **Groups Assigned**.</span></span>
4. <span data-ttu-id="dddc1-165">Escolha **Atribuir Grupos** e então, na folha **Selecionar grupos**, escolha o usuário ou os grupos de dispositivos do Azure AD para o(s) qual(is) você deseja atribuir o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-165">Choose **Assign Groups** then, on the **Select groups** blade, choose the Azure AD user or device groups to which you want to assign the app.</span></span>
<span data-ttu-id="dddc1-166">Você deve escolher uma ação de atribuição de **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-166">You must choose an assignment action of **Required**.</span></span> <span data-ttu-id="dddc1-167">Além disso, as atribuições a grupos de dispositivos estão disponíveis para novos locatários criados depois de janeiro de 2017.</span><span class="sxs-lookup"><span data-stu-id="dddc1-167">Additionally, assignments to device groups are available to new tenants created after January 2017.</span></span> <span data-ttu-id="dddc1-168">Se seu locatário foi criado antes dessa data e você não tiver a opção de atribuir aplicativos VPP a grupos de dispositivos, entre em contato com o suporte do Intune.</span><span class="sxs-lookup"><span data-stu-id="dddc1-168">If your tenant was created before this date, and you do not have the option to assign VPP apps to device groups, contact Intune support.</span></span>
5. <span data-ttu-id="dddc1-169">Quando terminar, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-169">Once you are done, choose **Save**.</span></span>

>[!NOTE]
><span data-ttu-id="dddc1-170">A lista de aplicativos exibida está associada um token.</span><span class="sxs-lookup"><span data-stu-id="dddc1-170">The list of apps displayed is associated with a token.</span></span> <span data-ttu-id="dddc1-171">Se você tiver um aplicativo que está associado a vários tokens VPP, verá o mesmo aplicativo exibido várias vezes, uma vez para cada token.</span><span class="sxs-lookup"><span data-stu-id="dddc1-171">If you have an app that is associated with multiple VPP tokens, you see the same app being displayed multiple times; once for each token.</span></span>

<span data-ttu-id="dddc1-172">Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-172">See [How to monitor apps](apps-monitor.md) for information to help you monitor app assignments.</span></span>

## <span data-ttu-id="dddc1-173">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="dddc1-173">Further information</span></span>
=======
> [!NOTE]
> O Microsoft Intune sincroniza apenas as informações de aplicativos publicamente disponíveis por meio da iTunes Store. Ainda não há suporte para **aplicativos B2B personalizados para iOS**. Se seu cenário for voltado para esses aplicativos, as informações de aplicativo não serão sincronizadas.

## Para atribuir um aplicativo comprado por volume
<a id="to-assign-a-volume-purchased-app" class="xliff"></a>

1. Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos Licenciados**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir e selecione “**...**” > **Atribuir Grupos**.
3. Na folha <*nome do aplicativo*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.
4. Escolha **Atribuir Grupos** e então, na folha **Selecionar grupos**, escolha o usuário ou os grupos de dispositivos do Azure AD para o(s) qual(is) você deseja atribuir o aplicativo.
Você deve escolher uma ação de atribuição de **Obrigatório**. Além disso, as atribuições a grupos de dispositivos estão disponíveis para novos locatários criados depois de janeiro de 2017. Se seu locatário foi criado antes dessa data e você não tiver a opção de atribuir aplicativos VPP a grupos de dispositivos, entre em contato com o suporte do Intune.
5. Quando terminar, escolha **Salvar**.

>[!NOTE]
>A lista de aplicativos exibida está associada um token. Se você tiver um aplicativo que está associado a vários tokens VPP, verá o mesmo aplicativo exibido várias vezes, uma vez para cada token.

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.

## Informações adicionais
>>>>>>> live
<a id="further-information" class="xliff"></a>

<span data-ttu-id="dddc1-174">Quando você atribui o aplicativo como uma instalação **Obrigatória**, cada usuário que instala o aplicativo usa uma licença.</span><span class="sxs-lookup"><span data-stu-id="dddc1-174">When you assign the app as a **Required** installation, each user who installs the app uses a license.</span></span>

<span data-ttu-id="dddc1-175">Para recuperar uma licença, você deve alterar a ação de atribuição para **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="dddc1-175">To reclaim a license, you must change the assignment action to **Uninstall**.</span></span> <span data-ttu-id="dddc1-176">A licença será recuperada após a desinstalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-176">The license will be reclaimed after the app is uninstalled.</span></span>

<<<<<<< HEAD
<span data-ttu-id="dddc1-177">Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase.</span><span class="sxs-lookup"><span data-stu-id="dddc1-177">When a user with an eligible device first tries to install a VPP app, they are asked to join the Apple Volume Purchase program.</span></span> <span data-ttu-id="dddc1-178">É necessário ingressar para continuar a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-178">They must join before the app installation proceeds.</span></span> <span data-ttu-id="dddc1-179">O convite para ingressar no Apple Volume Purchase Program exige que o usuário possa usar o aplicativo do iTunes no dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="dddc1-179">The invitation to join the Apple Volume Purchase program requires that the user can use the iTunes app on the iOS device.</span></span> <span data-ttu-id="dddc1-180">Se você tiver definido uma política para desabilitar o aplicativo da iTunes Store, o licenciamento baseado em usuário para aplicativos VPP não funcionará.</span><span class="sxs-lookup"><span data-stu-id="dddc1-180">If you have set a policy to disable the iTunes Store app, user-based licensing for VPP apps does not work.</span></span> <span data-ttu-id="dddc1-181">A solução é permitir o aplicativo do iTunes removendo a política ou usar o licenciamento baseado em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dddc1-181">The solution is to either allow the iTunes app by removing the policy, or use device-based licensing.</span></span>

<span data-ttu-id="dddc1-182">Quando você atribui um aplicativo VPP como Disponível, o respectivo conteúdo e a licença são atribuídos diretamente da App Store.</span><span class="sxs-lookup"><span data-stu-id="dddc1-182">When you assign a VPP app as Available, the app content and license are assigned directly from the app store.</span></span>
=======
Quando um usuário com um dispositivo qualificado tenta instalar um aplicativo VPP pela primeira vez, será solicitado que ele participe do programa Apple Volume Purchase. É necessário ingressar para continuar a instalação do aplicativo. O convite para ingressar no Apple Volume Purchase Program exige que o usuário possa usar o aplicativo do iTunes no dispositivo iOS. Se você tiver definido uma política para desabilitar o aplicativo da iTunes Store, o licenciamento baseado em usuário para aplicativos VPP não funcionará. A solução é permitir o aplicativo do iTunes removendo a política ou usar o licenciamento baseado em dispositivo.

Quando você atribui um aplicativo VPP como Disponível, o respectivo conteúdo e a licença são atribuídos diretamente da App Store.
>>>>>>> live
