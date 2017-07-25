---
title: Perfis de provisionamento de aplicativo
titleSuffix: Intune on Azure
description: "O Intune fornece as ferramentas para atribuir de forma proativa um novo perfil de provisionamento a dispositivos que têm aplicativos que estão se aproximando da expiração."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bf2da880f0f092b9948a400f6a10bd9ad032f959
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f5f5e-103">Usar os perfis de provisionamento móvel do iOS para impedir que os aplicativos expirem</span><span class="sxs-lookup"><span data-stu-id="f5f5e-103">Use iOS mobile provisioning profiles to prevent your apps from expiring</span></span>
<a id="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <span data-ttu-id="f5f5e-104">Introdução</span><span class="sxs-lookup"><span data-stu-id="f5f5e-104">Introduction</span></span>
<a id="introduction" class="xliff"></a>

<span data-ttu-id="f5f5e-105">Os aplicativos de linha de negócios de iOS da Apple atribuídos em iPhones e iPads são criados com um perfil de provisionamento incluído e código assinado com um certificado.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-105">Apple iOS line of business apps that are assigned to iPhones and iPads are built with an included provisioning profile and code that is signed with a certificate.</span></span> <span data-ttu-id="f5f5e-106">Quando o aplicativo é executado, o iOS confirma a integridade do aplicativo iOS e impõe políticas definidas pelo perfil de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-106">When the app is run, iOS confirms the integrity of the iOS app and enforces policies that are defined by the provisioning profile.</span></span> <span data-ttu-id="f5f5e-107">As validações a seguir ocorrem:</span><span class="sxs-lookup"><span data-stu-id="f5f5e-107">The following validations happen:</span></span>

- <span data-ttu-id="f5f5e-108">**Integridade do arquivo de instalação** – o iOS compara os detalhes de aplicativos com a chave pública do certificado de assinatura de empresa.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-108">**Installation file integrity** - iOS compares the app's details with the enterprise signing certificate's public key.</span></span> <span data-ttu-id="f5f5e-109">Se eles forem diferentes, o conteúdo dos aplicativos poderá ter sido alterado e ele não poderá ser executado.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-109">If they differ, the app's content might have changed, and the app will not be allowed to run.</span></span>
- <span data-ttu-id="f5f5e-110">**Imposição de funcionalidades** – o iOS tenta aplicar as funcionalidades do aplicativo do perfil de provisionamento corporativo (não perfis de provisionamento de desenvolvedor individuais) contidas no arquivo de instalação (.ipa) do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-110">**Capabilities enforcement** - iOS attempts to enforce the app's capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) that are in the app installation (.ipa) file.</span></span>


<span data-ttu-id="f5f5e-111">A empresa de assinatura de certificado usada para assinar aplicativos normalmente tem duração de três anos.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-111">The enterprise signing certificate that you use to sign apps typically lasts for three years.</span></span> <span data-ttu-id="f5f5e-112">No entanto, o perfil de provisionamento expira após um ano.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-112">However, the provisioning profile expires after a year.</span></span> <span data-ttu-id="f5f5e-113">Enquanto o certificado ainda for válido, o Intune fornecerá as ferramentas para atribuir proativamente um novo perfil de provisionamento em dispositivos que têm aplicativos que estão se aproximando da expiração.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-113">While the certificate is still valid, Intune gives you the tools to proactively assign a new provisioning profile to devices that have apps that are nearing expiry.</span></span>
<span data-ttu-id="f5f5e-114">Depois que o certificado expirar, você deverá assinar o aplicativo novamente com um novo certificado e inserir um novo perfil de provisionamento com a chave do novo certificado.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-114">After the certificate expires, you must sign the app again with a new certificate and embed a new provisioning profile with the key of the new certificate.</span></span>


## <span data-ttu-id="f5f5e-115">Como criar um perfil de provisionamento de aplicativo móvel iOS</span><span class="sxs-lookup"><span data-stu-id="f5f5e-115">How to create an iOS mobile app provisioning profile</span></span>
<a id="how-to-create-an-ios-mobile-app-provisioning-profile" class="xliff"></a>

1. <span data-ttu-id="f5f5e-116">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="f5f5e-117">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-117">Choose **More Services** > **Monitoring +Management** > **Intune**.</span></span>
3. <span data-ttu-id="f5f5e-118">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-118">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="f5f5e-119">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Perfis de provisionamento iOS**.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-119">In the **Mobile apps** workload, choose **Manage** > **iOS provisioning profiles**.</span></span>
2.  <span data-ttu-id="f5f5e-120">Na folha da lista de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-120">In the list of profiles blade, choose **Create profile**.</span></span>
3. <span data-ttu-id="f5f5e-121">Na folha **Criar perfil**, configure os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5f5e-121">In the **Create profile** blade, configure the following values:</span></span>
    - <span data-ttu-id="f5f5e-122">**Nome** – forneça um nome para essa política de perfil de provisionamento móvel.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-122">**Name** - Provide a name for this mobile provisioning profile.</span></span>
    - <span data-ttu-id="f5f5e-123">**Descrição** – de maneira opcional, forneça uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-123">**Description** - Optionally, provide a description for the policy.</span></span>
    - <span data-ttu-id="f5f5e-124">**Carregar arquivo de perfil** – escolha **Importar** e escolha um arquivo de Perfil de Configuração Móvel da Apple (com a extensão **.mobileprovision**) que você baixou do site do Desenvolvedor da Apple.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-124">**Upload profile file** - Choose **Import**, and then choose an Apple Mobile Configuration Profile file (with the extension **.mobileprovision**) that you downloaded from the Apple Developer website.</span></span>
4. <span data-ttu-id="f5f5e-125">Ao terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-125">When you are done, choose **Create**.</span></span>

## <span data-ttu-id="f5f5e-126">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f5f5e-126">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="f5f5e-127">Atribua o perfil aos dispositivos iOS necessários.</span><span class="sxs-lookup"><span data-stu-id="f5f5e-127">Assign the profile to the required iOS devices.</span></span> <span data-ttu-id="f5f5e-128">Para saber mais, use as etapas em [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="f5f5e-128">For more information, use the steps in [How to assign device profiles](device-profile-assign.md).</span></span>
