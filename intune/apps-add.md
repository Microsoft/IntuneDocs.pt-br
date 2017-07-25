---
<<<<<<< HEAD
title: <span data-ttu-id="827f9-101">Como adicionar aplicativos ao Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="827f9-101">How to add apps to Microsoft Intune</span></span>
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"827f9-102\">Estes procedimentos ajudam você a deixar seus aplicativos no Intune prontos para serem atribuídos a usuários e dispositivos.</span><span class=\"sxs-lookup\"><span data-stu-id=\"827f9-102\">These procedures help you get your apps into Intune ready to be assigned to users and devices.</span></span> <span data-ttu-id=\"827f9-103\">\"</span><span class=\"sxs-lookup\"><span data-stu-id=\"827f9-103\">\"</span></span>"
=======
title: Como adicionar aplicativos ao Microsoft Intune
titleSuffix: Intune on Azure
description: "Estes procedimentos ajudam você a deixar seus aplicativos no Intune prontos para serem atribuídos a usuários e dispositivos. \""
>>>>>>> live
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 69b1540d325f7cfa49e11f91fcb72a464f8a2e0e
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
<<<<<<< HEAD
# <a name="how-to-add-an-app-to-microsoft-intune"></a><span data-ttu-id="827f9-104">Como adicionar um aplicativo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="827f9-104">How to add an app to Microsoft Intune</span></span>
=======
# <a name="how-to-add-an-app-to-microsoft-intune"></a>Como adicionar um aplicativo no Microsoft Intune
>>>>>>> live

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="827f9-105">Antes de gerenciar e atribuir aplicativos aos seus usuários, você deve adicioná-los ao Intune.</span><span class="sxs-lookup"><span data-stu-id="827f9-105">Before you can manage and assign apps for your users, you must add them to Intune.</span></span> <span data-ttu-id="827f9-106">O Intune dá suporte a uma ampla variedade de tipos diferentes de aplicativos e as opções podem ser diferentes para cada tipo.</span><span class="sxs-lookup"><span data-stu-id="827f9-106">Intune supports a wide range of different app types, and the options might be different for each type.</span></span>

<span data-ttu-id="827f9-107">O Intune permite que você adicione e atribua esses tipos de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="827f9-107">Intune lets you add and assign these app types:</span></span>

![Tipos de aplicativo com suporte no Intune](./media/app-types.png)

<span data-ttu-id="827f9-109">Há suporte para as seguintes plataformas.</span><span class="sxs-lookup"><span data-stu-id="827f9-109">The following platforms are supported.</span></span>

- <span data-ttu-id="827f9-110">Aplicativos da Android Store</span><span class="sxs-lookup"><span data-stu-id="827f9-110">Android store apps</span></span>
- <span data-ttu-id="827f9-111">Aplicativos LOB para Android</span><span class="sxs-lookup"><span data-stu-id="827f9-111">Android line-of-business (LOB) apps</span></span>
- <span data-ttu-id="827f9-112">Aplicativos da iOS Store</span><span class="sxs-lookup"><span data-stu-id="827f9-112">iOS store apps</span></span>
- <span data-ttu-id="827f9-113">Aplicativos LOB para iOS</span><span class="sxs-lookup"><span data-stu-id="827f9-113">iOS line-of-business (LOB) apps</span></span>
- <span data-ttu-id="827f9-114">Aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="827f9-114">Web apps</span></span>
- <span data-ttu-id="827f9-115">Aplicativos da Windows Phone 8.1 Store</span><span class="sxs-lookup"><span data-stu-id="827f9-115">Windows Phone 8.1 store apps</span></span>
- <span data-ttu-id="827f9-116">Aplicativos de linha de negócios para Windows Phone (arquivos .xap)</span><span class="sxs-lookup"><span data-stu-id="827f9-116">Windows Phone line-of-business apps (.xap files)</span></span>
- <span data-ttu-id="827f9-117">Aplicativos da Windows Store</span><span class="sxs-lookup"><span data-stu-id="827f9-117">Windows store apps</span></span>
- <span data-ttu-id="827f9-118">Aplicativos de linha de negócios para Windows (apenas arquivos .msi)</span><span class="sxs-lookup"><span data-stu-id="827f9-118">Windows line-of-business apps (.msi files only)</span></span>

>[!TIP]
<<<<<<< HEAD
> <span data-ttu-id="827f9-119">Um aplicativo LOB (ou de linha de negócios) é aquele que você instala do arquivo de instalação, em vez de instalar de uma loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="827f9-119">A line-of-business (or LOB) app is one that you do not install from an app store, but install from the app installation file.</span></span> <span data-ttu-id="827f9-120">Por exemplo, para instalar um aplicativo LOB para iOS, adicione o respectivo arquivo morto cuja extensão seja .ipa.</span><span class="sxs-lookup"><span data-stu-id="827f9-120">For example, to install an iOS LOB app, you add the application archive file (with the extension .ipa).</span></span> <span data-ttu-id="827f9-121">Normalmente, são aplicativos que você tem gravados internamente.</span><span class="sxs-lookup"><span data-stu-id="827f9-121">These are typically apps you have written in-house.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="827f9-122">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="827f9-122">Before you start</span></span>

<span data-ttu-id="827f9-123">Considere os pontos a seguir antes de começar a adicionar e atribuir aplicativos.</span><span class="sxs-lookup"><span data-stu-id="827f9-123">Consider the following points before you begin to add and assign apps.</span></span>

- <span data-ttu-id="827f9-124">Quando você adiciona e atribui um aplicativo de uma loja, os usuários finais devem ter uma conta nessa loja para poder instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="827f9-124">When you add and assign an app from a store, end users must have an account with that store in order to be able to install the app.</span></span>
- <span data-ttu-id="827f9-125">Alguns aplicativos ou itens que você atribui podem ser dependentes de aplicativos internos do iOS.</span><span class="sxs-lookup"><span data-stu-id="827f9-125">Some apps or items you assign might be dependent on built-in iOS apps.</span></span> <span data-ttu-id="827f9-126">Por exemplo, quando você atribui um livro da iOS Store, o aplicativo iBooks deve estar presente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="827f9-126">For example, if you assign a book from the iOS store, then the iBooks app must be present on the device.</span></span> <span data-ttu-id="827f9-127">Se você tiver removido o aplicativo interno iBooks, não será possível usar o Intune para reabilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="827f9-127">If you have removed the iBooks built-in app, you cannot use Intune to reinstate it.</span></span>

## <a name="cloud-storage-space"></a><span data-ttu-id="827f9-128">Espaço de armazenamento em nuvem</span><span class="sxs-lookup"><span data-stu-id="827f9-128">Cloud storage space</span></span>
<span data-ttu-id="827f9-129">Todos os aplicativos que você cria usando o tipo de instalação do instalador do software (por exemplo, um aplicativo LOB) são empacotados e carregados no armazenamento em nuvem do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="827f9-129">All apps that you create by using the software installer installation type (for example, a line-of-business app) are packaged and uploaded to Intune cloud storage.</span></span> <span data-ttu-id="827f9-130">Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações.</span><span class="sxs-lookup"><span data-stu-id="827f9-130">A trial subscription of Intune includes 2 gigabytes (GB) of cloud-based storage that is used to store managed apps and updates.</span></span> <span data-ttu-id="827f9-131">A assinatura completa inclui 20 GB de espaço de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="827f9-131">A full subscription includes 20 GB of storage space.</span></span>

<span data-ttu-id="827f9-132">Você pode adquirir armazenamento adicional para o Intune usando seu método de compra original.</span><span class="sxs-lookup"><span data-stu-id="827f9-132">You can purchase additional storage for Intune using your original purchase method.</span></span>  <span data-ttu-id="827f9-133">Se você paga por cartão de crédito ou fatura, visite o [portal de Gerenciamento de Assinatura](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).</span><span class="sxs-lookup"><span data-stu-id="827f9-133">If you paid by invoice or credit card, visit the [Subscription Management portal](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).</span></span>  <span data-ttu-id="827f9-134">Caso contrário, entre em contato com seu parceiro ou associado de vendas.</span><span class="sxs-lookup"><span data-stu-id="827f9-134">Otherwise, contact your partner or sales associate.</span></span>

<span data-ttu-id="827f9-135">Os requisitos de espaço de armazenamento em nuvem são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="827f9-135">Requirements for cloud storage space are as follows:</span></span>

-   <span data-ttu-id="827f9-136">Todos os arquivos de instalação do aplicativo devem estar na mesma pasta.</span><span class="sxs-lookup"><span data-stu-id="827f9-136">All app installation files must be in the same folder.</span></span>
-   <span data-ttu-id="827f9-137">O tamanho máximo do arquivo para qualquer arquivo que você carregar é de 2 GB.</span><span class="sxs-lookup"><span data-stu-id="827f9-137">The maximum file size for any file that you upload is 2 GB.</span></span>

## <a name="how-to-create-and-edit-categories-for-apps"></a><span data-ttu-id="827f9-138">Como criar e editar categorias para aplicativos</span><span class="sxs-lookup"><span data-stu-id="827f9-138">How to create and edit categories for apps</span></span>

<span data-ttu-id="827f9-139">As categorias de aplicativo podem ser usadas para ajudar a classificar aplicativos para que os usuários possam encontrá-los com mais facilidade no portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="827f9-139">App categories can be used to help you sort apps to make them easier for users to find in the company portal.</span></span> <span data-ttu-id="827f9-140">Você pode atribuir uma ou mais categorias a um aplicativo, por exemplo, **Aplicativos de desenvolvedor** ou **Aplicativos de comunicação**.</span><span class="sxs-lookup"><span data-stu-id="827f9-140">You can assign one or more categories to an app, for example, **Developer apps**, or **Communication apps**.</span></span>
<span data-ttu-id="827f9-141">Quando você adiciona um aplicativo ao Intune, terá a opção de selecionar a categoria desejada.</span><span class="sxs-lookup"><span data-stu-id="827f9-141">When you add an app to Intune, you are given the option to select the category you want.</span></span> <span data-ttu-id="827f9-142">Use os tópicos específicos da plataforma para adicionar um aplicativo e atribuir categorias.</span><span class="sxs-lookup"><span data-stu-id="827f9-142">Use the platform-specific topics to add an app, and assign categories.</span></span> <span data-ttu-id="827f9-143">Para criar e editar suas próprias categorias, use o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="827f9-143">To create and edit your own categories, use the following procedure:</span></span>

1. <span data-ttu-id="827f9-144">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="827f9-144">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="827f9-145">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="827f9-145">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="827f9-146">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="827f9-146">On the **Intune** blade, choose **Mobile apps**.</span></span>
4. <span data-ttu-id="827f9-147">Na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Categorias de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="827f9-147">In the **Mobile apps** workload, choose **Setup** > **App categories**.</span></span>
5. <span data-ttu-id="827f9-148">Na folha **Categorias de aplicativos**, é mostrada uma lista de categorias atuais.</span><span class="sxs-lookup"><span data-stu-id="827f9-148">On the **App categories** blade, a list of the current categories is shown.</span></span> <span data-ttu-id="827f9-149">Escolha uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="827f9-149">Choose one of the following actions:</span></span>
    - <span data-ttu-id="827f9-150">**Criar uma categoria de** – Na folha **Criar categoria**, insira um nome para a nova categoria.</span><span class="sxs-lookup"><span data-stu-id="827f9-150">**Create a category** - On the **Create category** blade, enter a name for the new category.</span></span> <span data-ttu-id="827f9-151">Os nomes podem ser inseridos em apenas um idioma e não são traduzidos pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="827f9-151">Names can be entered in one language only, and are not translated by Intune.</span></span> <span data-ttu-id="827f9-152">Quando terminar, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="827f9-152">When you are done, click **Create**.</span></span>
    - <span data-ttu-id="827f9-153">**Editar uma categoria** – Para qualquer categoria na lista, escolha “**...** “.</span><span class="sxs-lookup"><span data-stu-id="827f9-153">**Edit a category** - For any category in the list, choose '**...**'.</span></span> <span data-ttu-id="827f9-154">Na folha **Propriedades**, você pode inserir um novo nome para a categoria ou excluí-la.</span><span class="sxs-lookup"><span data-stu-id="827f9-154">On the **Properties** blade, you can enter a new name for the category, or delete the category.</span></span>


## <a name="apps-added-automatically-by-intune"></a><span data-ttu-id="827f9-155">Aplicativos adicionados automaticamente pelo Intune</span><span class="sxs-lookup"><span data-stu-id="827f9-155">Apps added automatically by Intune</span></span>

<span data-ttu-id="827f9-156">Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente.</span><span class="sxs-lookup"><span data-stu-id="827f9-156">Previously, Intune contained a number of built-in apps that you could quickly assign.</span></span> <span data-ttu-id="827f9-157">Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.</span><span class="sxs-lookup"><span data-stu-id="827f9-157">Based on your feedback, we have removed this list, and you will no longer see built-in apps.</span></span>
<span data-ttu-id="827f9-158">No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="827f9-158">However, if you have already assigned any built-in apps, these will still be visible in the list of apps.</span></span> <span data-ttu-id="827f9-159">Você pode continuar a atribuir esses aplicativos conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="827f9-159">You can continue to assign these apps as required.</span></span>
<span data-ttu-id="827f9-160">Planejamos adicionar um método mais fácil para selecionar e atribuir aplicativos internos no portal Microsoft Intune, em um lançamento posterior.</span><span class="sxs-lookup"><span data-stu-id="827f9-160">In a later release, we plan to add an easier method to select and assign built-in apps from the Intune portal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="827f9-161">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="827f9-161">Next steps</span></span>

<span data-ttu-id="827f9-162">Escolha um dos tópicos a seguir para saber como adicionar aplicativos para cada plataforma no Microsoft Intune:</span><span class="sxs-lookup"><span data-stu-id="827f9-162">Choose one of the following topics to find out how to add apps for each platform to Intune:</span></span>

- [<span data-ttu-id="827f9-163">Aplicativos da Android Store</span><span class="sxs-lookup"><span data-stu-id="827f9-163">Android store apps</span></span>](store-apps-android.md)
- [<span data-ttu-id="827f9-164">Aplicativos LOB para Android</span><span class="sxs-lookup"><span data-stu-id="827f9-164">Android LOB apps</span></span>](lob-apps-android.md)
- [<span data-ttu-id="827f9-165">Aplicativos da iOS Store</span><span class="sxs-lookup"><span data-stu-id="827f9-165">iOS store apps</span></span>](store-apps-ios.md)
- [<span data-ttu-id="827f9-166">Aplicativos LOB para iOS</span><span class="sxs-lookup"><span data-stu-id="827f9-166">iOS LOB apps</span></span>](lob-apps-ios.md)
- [<span data-ttu-id="827f9-167">Aplicativos Web (para todas as plataformas)</span><span class="sxs-lookup"><span data-stu-id="827f9-167">Web apps (for all platforms)</span></span>](web-app.md)
- [<span data-ttu-id="827f9-168">Aplicação da loja do Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="827f9-168">Windows Phone 8.1 store apps</span></span>](store-apps-windows-phone-8-1.md)
- [<span data-ttu-id="827f9-169">Aplicativos LOB para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="827f9-169">Windows Phone LOB apps</span></span>](lob-apps-windows-phone.md)
- [<span data-ttu-id="827f9-170">Aplicativos da Windows Store</span><span class="sxs-lookup"><span data-stu-id="827f9-170">Windows store apps</span></span>](store-apps-windows.md)
- [<span data-ttu-id="827f9-171">Aplicativos LOB para Windows</span><span class="sxs-lookup"><span data-stu-id="827f9-171">Windows LOB app</span></span>](lob-apps-windows.md)
=======
> Um aplicativo LOB (ou de linha de negócios) é aquele que você instala do arquivo de instalação, em vez de instalar de uma loja de aplicativos. Por exemplo, para instalar um aplicativo LOB para iOS, adicione o respectivo arquivo morto cuja extensão seja .ipa. Normalmente, são aplicativos que você tem gravados internamente.

## <a name="before-you-start"></a>Antes de começar

Considere os pontos a seguir antes de começar a adicionar e atribuir aplicativos.

- Quando você adiciona e atribui um aplicativo de uma loja, os usuários finais devem ter uma conta nessa loja para poder instalar o aplicativo.
- Alguns aplicativos ou itens que você atribui podem ser dependentes de aplicativos internos do iOS. Por exemplo, quando você atribui um livro da iOS Store, o aplicativo iBooks deve estar presente no dispositivo. Se você tiver removido o aplicativo interno iBooks, não será possível usar o Intune para reabilitá-lo.

## <a name="cloud-storage-space"></a>Espaço de armazenamento em nuvem
Todos os aplicativos que você cria usando o tipo de instalação do instalador do software (por exemplo, um aplicativo LOB) são empacotados e carregados no armazenamento em nuvem do Microsoft Intune. Uma assinatura de avaliação do Intune inclui 2 GB de armazenamento baseado em nuvem que é usado para armazenar aplicativos gerenciados e atualizações. A assinatura completa inclui 20 GB de espaço de armazenamento.

Você pode adquirir armazenamento adicional para o Intune usando seu método de compra original.  Se você paga por cartão de crédito ou fatura, visite o [portal de Gerenciamento de Assinatura](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Caso contrário, entre em contato com seu parceiro ou associado de vendas.

Os requisitos de espaço de armazenamento em nuvem são os seguintes:

-   Todos os arquivos de instalação do aplicativo devem estar na mesma pasta.
-   O tamanho máximo do arquivo para qualquer arquivo que você carregar é de 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Como criar e editar categorias para aplicativos

As categorias de aplicativo podem ser usadas para ajudar a classificar aplicativos para que os usuários possam encontrá-los com mais facilidade no portal da empresa. Você pode atribuir uma ou mais categorias a um aplicativo, por exemplo, **Aplicativos de desenvolvedor** ou **Aplicativos de comunicação**.
Quando você adiciona um aplicativo ao Intune, terá a opção de selecionar a categoria desejada. Use os tópicos específicos da plataforma para adicionar um aplicativo e atribuir categorias. Para criar e editar suas próprias categorias, use o procedimento a seguir:

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
4. Na carga de trabalho **Aplicativos móveis**, escolha **Configurar** > **Categorias de aplicativos**.
5. Na folha **Categorias de aplicativos**, é mostrada uma lista de categorias atuais. Escolha uma das seguintes ações:
    - **Criar uma categoria de** – Na folha **Criar categoria**, insira um nome para a nova categoria. Os nomes podem ser inseridos em apenas um idioma e não são traduzidos pelo Intune. Quando terminar, clique em **Criar**.
    - **Editar uma categoria** – Para qualquer categoria na lista, escolha “**...** “. Na folha **Propriedades**, você pode inserir um novo nome para a categoria ou excluí-la.


## <a name="apps-added-automatically-by-intune"></a>Aplicativos adicionados automaticamente pelo Intune

Antes, o Intune incluía vários aplicativos internos que você podia atribuir rapidamente. Com base em seus comentários, removemos esta lista e você não precisa mais conferir os aplicativos internos.
No entanto, se você já atribuiu aplicativos internos, eles ainda estarão visíveis na lista de aplicativos. Você pode continuar a atribuir esses aplicativos conforme necessário.
Planejamos adicionar um método mais fácil para selecionar e atribuir aplicativos internos no portal Microsoft Intune, em um lançamento posterior.

## <a name="next-steps"></a>Próximas etapas

Escolha um dos tópicos a seguir para saber como adicionar aplicativos para cada plataforma no Microsoft Intune:

- [Aplicativos da Android Store](store-apps-android.md)
- [Aplicativos LOB para Android](lob-apps-android.md)
- [Aplicativos da iOS Store](store-apps-ios.md)
- [Aplicativos LOB para iOS](lob-apps-ios.md)
- [Aplicativos Web (para todas as plataformas)](web-app.md)
- [Aplicação da loja do Windows Phone 8.1](store-apps-windows-phone-8-1.md)
- [Aplicativos LOB para Windows Phone](lob-apps-windows-phone.md)
- [Aplicativos da Windows Store](store-apps-windows.md)
- [Aplicativos LOB para Windows](lob-apps-windows.md)
>>>>>>> live

