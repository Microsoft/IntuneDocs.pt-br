---
title: "Gerenciar livros eletrônicos do iOS comprados por volume"
titleSuffix: Intune on Azure
description: "Saiba como você pode sincronizar no Intune os livros comprados por volume na loja do iOS e, depois, gerenciar e acompanhar seu uso."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e23c40eb4c13fd0d2593742c72086fc943fe2b54
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="a60ad-103">Como gerenciar livros eletrônicos do iOS comprados por meio de um programa de compra por volume com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a60ad-103">How to manage iOS eBooks you purchased through a volume-purchase program with Microsoft Intune</span></span>
<a id="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a60ad-104">O Apple VPP (Volume Purchase Program) permite que você compre várias licenças de um livro que você deseja distribuir aos usuários em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="a60ad-104">The Apple Volume Purchase Program (VPP) lets you purchase multiple licenses for a book that you want to distribute to users in your company.</span></span> <span data-ttu-id="a60ad-105">Distribua livros das lojas de Negócios ou Educação.</span><span class="sxs-lookup"><span data-stu-id="a60ad-105">You can distribute books from the Business, or Education stores.</span></span>

<span data-ttu-id="a60ad-106">O Microsoft Intune ajuda você a sincronizar, gerenciar e atribuir livros comprados por meio desse programa.</span><span class="sxs-lookup"><span data-stu-id="a60ad-106">Microsoft Intune helps you synchronize, manage, and assign books that you purchased through this program.</span></span> <span data-ttu-id="a60ad-107">Importe informações de licença da loja e acompanhe quantas licenças você utilizou.</span><span class="sxs-lookup"><span data-stu-id="a60ad-107">You can import license information from the store and track how many of the licenses you have used.</span></span>

<span data-ttu-id="a60ad-108">Os procedimentos para gerenciar livros são semelhantes aos usados para [gerenciar aplicativos VPP](vpp-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="a60ad-108">The procedures to manage books are similar to [managing VPP apps](vpp-apps-ios.md).</span></span>

## <span data-ttu-id="a60ad-109">Gerenciar aplicativos comprados por volume em dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="a60ad-109">Manage volume-purchased books for iOS devices</span></span>
<a id="manage-volume-purchased-books-for-ios-devices" class="xliff"></a>
<span data-ttu-id="a60ad-110">Você compra várias licenças para livros do iOS por meio do [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) ou do [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store).</span><span class="sxs-lookup"><span data-stu-id="a60ad-110">You buy multiple licenses for iOS books through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) or the [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store).</span></span> <span data-ttu-id="a60ad-111">Esse processo envolve a configuração de uma conta do Apple VPP no site da Apple e o upload do token do Apple VPP no Intune.</span><span class="sxs-lookup"><span data-stu-id="a60ad-111">This process involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="a60ad-112">Depois, você pode sincronizar suas informações de compra por volume com o Intune e acompanhar o uso de livros comprados por volume.</span><span class="sxs-lookup"><span data-stu-id="a60ad-112">You can then synchronize your volume purchase information with Intune and track your volume-purchased book use.</span></span>

## <span data-ttu-id="a60ad-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="a60ad-113">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="a60ad-114">Antes de começar, obtenha um token VPP da Apple e carregue-o em sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="a60ad-114">Before you start, get a VPP token from Apple and upload it to your Intune account.</span></span> <span data-ttu-id="a60ad-115">Além disso:</span><span class="sxs-lookup"><span data-stu-id="a60ad-115">Additionally:</span></span>

* <span data-ttu-id="a60ad-116">Você pode associar até 256 tokens VPP à sua conta do Intune.</span><span class="sxs-lookup"><span data-stu-id="a60ad-116">You can associate up to 256 VPP tokens with your Intune account.</span></span>
* <span data-ttu-id="a60ad-117">Se você já tiver usado um token do VPP com um produto diferente, será necessário gerar um novo para ser usado com o Intune.</span><span class="sxs-lookup"><span data-stu-id="a60ad-117">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="a60ad-118">Cada token é válido por um ano.</span><span class="sxs-lookup"><span data-stu-id="a60ad-118">Each token is valid for one year.</span></span>
* <span data-ttu-id="a60ad-119">Por padrão, o Intune é sincronizado com o serviço VPP da Apple duas vezes por dia.</span><span class="sxs-lookup"><span data-stu-id="a60ad-119">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="a60ad-120">É possível iniciar uma sincronização manual a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="a60ad-120">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="a60ad-121">Depois de importar o token do VPP no Intune, não importe o mesmo token em outra solução de gerenciamento de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a60ad-121">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="a60ad-122">Isso pode resultar na perda de registros de usuário e atribuição de licença.</span><span class="sxs-lookup"><span data-stu-id="a60ad-122">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="a60ad-123">Antes de começar a usar os livros do iOS com o Intune, remova todas as contas de usuário do VPP existentes criadas com outros fornecedores de MDM (gerenciamento de dispositivo móvel).</span><span class="sxs-lookup"><span data-stu-id="a60ad-123">Before you start to use iOS books with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="a60ad-124">O Intune não sincroniza essas contas de usuário no Intune como uma medida de segurança.</span><span class="sxs-lookup"><span data-stu-id="a60ad-124">Intune does not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="a60ad-125">O Intune sincroniza somente os dados do serviço Apple VPP criados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="a60ad-125">Intune synchronizes only data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="a60ad-126">No momento, só é possível atribuir livros como uma instalação **Obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-126">Currently, you can only assign books as a **Required** install.</span></span> <span data-ttu-id="a60ad-127">Quando você atribui o livro como uma instalação **Obrigatória**, cada usuário que instala o livro usa uma licença.</span><span class="sxs-lookup"><span data-stu-id="a60ad-127">When you assign the book as a **Required** installation, each user who installs the book uses a license.</span></span>
* <span data-ttu-id="a60ad-128">Quando você atribui um livro a um dispositivo, esse dispositivo deve ter o aplicativo interno iBooks instalado.</span><span class="sxs-lookup"><span data-stu-id="a60ad-128">When you assign a book to a device, that device must have the built-in iBooks app installed.</span></span> <span data-ttu-id="a60ad-129">Caso contrário, o usuário final deverá reinstalar o aplicativo antes de poder ler o livro.</span><span class="sxs-lookup"><span data-stu-id="a60ad-129">If it is not, the end user must reinstall the app before they can read the book.</span></span> <span data-ttu-id="a60ad-130">No momento, não é possível usar o Intune para restaurar aplicativos internos removidos.</span><span class="sxs-lookup"><span data-stu-id="a60ad-130">You cannot currently use Intune to restore removed built-in apps.</span></span>
* <span data-ttu-id="a60ad-131">Você pode atribuir somente livros do site do Apple Volume Purchase Program.</span><span class="sxs-lookup"><span data-stu-id="a60ad-131">You can only assign books from the Apple Volume Purchase Program site.</span></span> <span data-ttu-id="a60ad-132">Não é possível carregar nem, em seguida, atribuir livros que você criou internamente.</span><span class="sxs-lookup"><span data-stu-id="a60ad-132">You cannot upload, then assign books you created in-house.</span></span>
* <span data-ttu-id="a60ad-133">Atualmente, não é possível atribuir livros a categorias de usuário final da mesma maneira que os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="a60ad-133">You cannot currently assign books to end-user categories in the same way as you do apps.</span></span>
* <span data-ttu-id="a60ad-134">Não é possível recuperar uma licença depois que o livro é atribuído.</span><span class="sxs-lookup"><span data-stu-id="a60ad-134">You cannot reclaim a license once the book is assigned.</span></span>
* <span data-ttu-id="a60ad-135">Quando um usuário com um dispositivo qualificado tenta instalar um livro do VPP pela primeira vez, ele deve ingressar no Apple Volume Purchase Program antes de instalar um livro.</span><span class="sxs-lookup"><span data-stu-id="a60ad-135">When a user with an eligible device first tries to install a VPP book, they must join the Apple Volume Purchase program before they can install a book.</span></span> <span data-ttu-id="a60ad-136">Atribua também licenças a grupos de segurança com as IDs da Apple gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="a60ad-136">You can also assign licenses to security groups with managed Apple IDs.</span></span> <span data-ttu-id="a60ad-137">Se você fizer isso, os usuários não precisarão fornecer suas IDs da Apple quando um livro for instalado.</span><span class="sxs-lookup"><span data-stu-id="a60ad-137">If you do this, then users are not prompted for their Apple ID when a book is installed.</span></span>

## <span data-ttu-id="a60ad-138">Obter e carregar um token de VPP da Apple</span><span class="sxs-lookup"><span data-stu-id="a60ad-138">To get and upload an Apple VPP token</span></span>
<a id="to-get-and-upload-an-apple-vpp-token" class="xliff"></a>

1. <span data-ttu-id="a60ad-139">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="a60ad-139">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a60ad-140">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-140">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="a60ad-141">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-141">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="a60ad-142">Na carga de trabalho do recurso **Aplicativos Móveis**, escolha **Configurar** > **Tokens de VPP do iOS**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-142">In the **Mobile Apps** workload, choose **Setup** > **iOS VPP Tokens**.</span></span>
2.  <span data-ttu-id="a60ad-143">Na folha da lista de tokens do VPP, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-143">On the list of VPP tokens blade, click **Add**.</span></span>
3.  <span data-ttu-id="a60ad-144">Na folha **Novo Token VPP**, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="a60ad-144">On the **New VPP Token** blade, specify the following information:</span></span>
    - <span data-ttu-id="a60ad-145">**Arquivo de token VPP** – inscreva-se no Volume Purchase Program for Business ou no Volume Purchase Program for Education.</span><span class="sxs-lookup"><span data-stu-id="a60ad-145">**VPP token file** - Ensure you have signed for the Volume Purchase Program for Business or the Volume Purchase Program for Education.</span></span> <span data-ttu-id="a60ad-146">Depois, baixe o token Apple VPP em sua conta e selecione-o aqui.</span><span class="sxs-lookup"><span data-stu-id="a60ad-146">Then, download the Apple VPP token for your account and select it here.</span></span>
    - <span data-ttu-id="a60ad-147">**ID da Apple** – Insira a ID da Apple da conta associada ao programa de compra por volume.</span><span class="sxs-lookup"><span data-stu-id="a60ad-147">**Apple ID** - Enter the Apple ID of the account associated with the volume-purchase program.</span></span>
    - <span data-ttu-id="a60ad-148">**Tipo de conta do VPP** – Escolha **Comercial** ou **Educação**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-148">**Type of VPP account** - Choose from **Business** or **Education**.</span></span>
4. <span data-ttu-id="a60ad-149">Quando terminar, clique em **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-149">When you are done, click **Upload**.</span></span>

<span data-ttu-id="a60ad-150">O token é exibido na lista da folha de tokens.</span><span class="sxs-lookup"><span data-stu-id="a60ad-150">The token is displayed in the list of tokens blade.</span></span>


<span data-ttu-id="a60ad-151">Você pode sincronizar os dados mantidos pela Apple com o Intune a qualquer momento selecionando **Sincronizar agora**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-151">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

## <span data-ttu-id="a60ad-152">Para atribuir um aplicativo comprado por volume</span><span class="sxs-lookup"><span data-stu-id="a60ad-152">To assign a volume-purchased app</span></span>
<a id="to-assign-a-volume-purchased-app" class="xliff"></a>

1. <span data-ttu-id="a60ad-153">Na carga de trabalho **Livros Eletrônicos**, escolha **Gerenciar** > **Todos os Livros Eletrônicos**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-153">In the **eBooks** workload, choose **Manage** > **All eBooks**.</span></span>
2. <span data-ttu-id="a60ad-154">Na folha da lista de livros, escolha o livro que você deseja atribuir e, depois, selecione “**...**”</span><span class="sxs-lookup"><span data-stu-id="a60ad-154">On the list of books blade, choose the book you want to assign, and then choose '**...**'</span></span><span data-ttu-id="a60ad-155"> > **Atribuir Grupos**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-155"> > **Assign Groups**.</span></span>
3. <span data-ttu-id="a60ad-156">Na folha <*nome do livro*> – **Grupos Atribuídos**, escolha **Gerenciar** > **Grupos Atribuídos**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-156">On the <*book name*> - **Groups Assigned** blade, choose **Manage** > **Groups Assigned**.</span></span>
4. <span data-ttu-id="a60ad-157">Escolha **Atribuir Grupos** e, na folha **Selecionar grupos**, escolha os grupos de usuários do Azure AD aos quais você deseja atribuir o livro.</span><span class="sxs-lookup"><span data-stu-id="a60ad-157">Choose **Assign Groups** then, on the **Select groups** blade, choose the Azure AD user groups to which you want to assign the book.</span></span> <span data-ttu-id="a60ad-158">No momento, não há suporte para grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a60ad-158">Device groups are currently not supported.</span></span>
<span data-ttu-id="a60ad-159">Escolha a ação de atribuição **Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-159">Choose an assignment action of **Required**.</span></span> 
5. <span data-ttu-id="a60ad-160">Quando terminar, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a60ad-160">Once you are done, choose **Save**.</span></span>

## <span data-ttu-id="a60ad-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="a60ad-161">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="a60ad-162">Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de livro.</span><span class="sxs-lookup"><span data-stu-id="a60ad-162">See [How to monitor apps](apps-monitor.md) for information to help you monitor book assignments.</span></span>






