---
title: Perfis de provisionamento de aplicativo
description: "O Intune fornece as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e975aa7ee22f826c7a0a60d637d651fd347bc54
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="786f6-103">Usar políticas de perfil de provisionamento móvel do iOS para impedir que os aplicativos expirem</span><span class="sxs-lookup"><span data-stu-id="786f6-103">Use iOS mobile provisioning profile policies to prevent your apps from expiring</span></span>
<a id="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="786f6-104">Os aplicativos de linha de negócios de iOS da Apple implantados em iPhones e iPads são criados com um perfil de provisionamento incluído e código assinado com um certificado.</span><span class="sxs-lookup"><span data-stu-id="786f6-104">Apple iOS line of business apps that are deployed to iPhones and iPads are built with an included provisioning profile and code that is signed with a certificate.</span></span> <span data-ttu-id="786f6-105">Quando o aplicativo é executado, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="786f6-105">When the app is run, iOS confirms the integrity of the iOS app and enforces policies that are defined by the provisioning profile.</span></span> <span data-ttu-id="786f6-106">As validações a seguir ocorrem:</span><span class="sxs-lookup"><span data-stu-id="786f6-106">The following validations happen:</span></span>

- <span data-ttu-id="786f6-107">**Integridade do arquivo de instalação** – o iOS compara os detalhes de aplicativos com a chave pública do certificado de assinatura de empresa.</span><span class="sxs-lookup"><span data-stu-id="786f6-107">**Installation file integrity** - iOS compares the app's details with the enterprise signing certificate's public key.</span></span> <span data-ttu-id="786f6-108">Se eles forem diferentes, o conteúdo dos aplicativos poderá ter sido alterado e ele não poderá ser executado.</span><span class="sxs-lookup"><span data-stu-id="786f6-108">If they differ, the app's content might have changed, and the app will not be allowed to run.</span></span>
- <span data-ttu-id="786f6-109">**Imposição de funcionalidades** – o iOS tenta aplicar as funcionalidades do aplicativo do perfil de provisionamento corporativo (não perfis de provisionamento de desenvolvedor individuais) contidas no arquivo de instalação (.ipa) do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="786f6-109">**Capabilities enforcement** - iOS attempts to enforce the app's capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) that are in the app installation (.ipa) file.</span></span>


<span data-ttu-id="786f6-110">A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos.</span><span class="sxs-lookup"><span data-stu-id="786f6-110">The enterprise signing certificate that you use to sign apps typically lasts for three years.</span></span> <span data-ttu-id="786f6-111">No entanto, o perfil de provisionamento expira após um ano.</span><span class="sxs-lookup"><span data-stu-id="786f6-111">However, the provisioning profile expires after a year.</span></span> <span data-ttu-id="786f6-112">Enquanto o certificado ainda for válido, o Intune fornecerá as ferramentas para implantar proativamente uma nova política de perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.</span><span class="sxs-lookup"><span data-stu-id="786f6-112">While the certificate is still valid, Intune gives you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are nearing expiry.</span></span>
<span data-ttu-id="786f6-113">Depois que o certificado expirar, você deverá assinar o aplicativo novamente com um novo certificado e inserir um novo perfil de provisionamento com a chave do novo certificado.</span><span class="sxs-lookup"><span data-stu-id="786f6-113">After the certificate expires, you must sign the app again with a new certificate and embed a new provisioning profile with the key of the new certificate.</span></span>



## <span data-ttu-id="786f6-114">Como descobrir quando um aplicativo de linha de negócios expirará</span><span class="sxs-lookup"><span data-stu-id="786f6-114">How to find out when a line of business app will expire</span></span>
<a id="how-to-find-out-when-a-line-of-business-app-will-expire" class="xliff"></a>

1. <span data-ttu-id="786f6-115">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="786f6-115">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** > **Apps**.</span></span>
2. <span data-ttu-id="786f6-116">Na lista de aplicativos, examine a coluna **Data de expiração** para ver a data de expiração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="786f6-116">In the list of apps, look at the **Expiration date** column to see the expiry date for the app.</span></span> <span data-ttu-id="786f6-117">Você também pode definir a lista suspensa **Filtros** como **Expirado/prestes a expirar** para ver apenas os aplicativos para os quais é necessário tomar providências.</span><span class="sxs-lookup"><span data-stu-id="786f6-117">You can also set the **Filters** drop-down list to **Expired/about to expire** to see only the apps for which you must take action.</span></span>

## <span data-ttu-id="786f6-118">Como criar uma política de perfil de provisionamento móvel iOS</span><span class="sxs-lookup"><span data-stu-id="786f6-118">How to create an iOS mobile provisioning profile policy</span></span>
<a id="how-to-create-an-ios-mobile-provisioning-profile-policy" class="xliff"></a>


1. <span data-ttu-id="786f6-119">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Política** > **Visão Geral** > **Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="786f6-119">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Overview** > **Add Policy**.</span></span>
2. <span data-ttu-id="786f6-120">Na caixa de diálogo **Criar Nova Política**, selecione **iOS** > **Política de perfil de provisionamento móvel** e selecione **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="786f6-120">In the **Create a New Policy** dialog box, choose **iOS** > **Mobile Provisioning Profile Policy**, and then choose **Create Policy**.</span></span>
3. <span data-ttu-id="786f6-121">Na página **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="786f6-121">On the **General** page, configure the following values:</span></span>
    - <span data-ttu-id="786f6-122">**Nome** – forneça um nome para essa política de perfil de provisionamento móvel.</span><span class="sxs-lookup"><span data-stu-id="786f6-122">**Name** - Provide a name for this mobile provisioning profile policy.</span></span>
    - <span data-ttu-id="786f6-123">**Descrição** – de maneira opcional, forneça uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="786f6-123">**Description** - Optionally, provide a description for the policy.</span></span>
    - <span data-ttu-id="786f6-124">**Arquivo do perfil de configuração** – Clique em **Importar** e escolha um arquivo de Perfil de Configuração Móvel da Apple (com a extensão **.mobileprovision**) que você baixou do site do Desenvolvedor da Apple.</span><span class="sxs-lookup"><span data-stu-id="786f6-124">**Configuration profile file** - Click **Import**, and then choose an Apple Mobile Configuration Profile file (with the extension **.mobileprovision**) that you downloaded from the Apple Developer website.</span></span>
4. <span data-ttu-id="786f6-125">Quando terminar, selecione **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="786f6-125">When you are done, choose **Save Policy**.</span></span>
5. <span data-ttu-id="786f6-126">Agora, implante a política aos dispositivos iOS necessários.</span><span class="sxs-lookup"><span data-stu-id="786f6-126">Now, deploy the policy to the required iOS devices.</span></span> <span data-ttu-id="786f6-127">Para obter mais informações, consulte [Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="786f6-127">For more information, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>
