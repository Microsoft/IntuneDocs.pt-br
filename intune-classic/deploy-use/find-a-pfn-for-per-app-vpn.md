---
title: "Localizar um nome da família de pacotes (PFN) para VPN por aplicativo"
description: "Localize um PFN para que você possa configurar uma VPN por aplicativo."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: eea3b9e2888f07399c8cda1e81ae8a5318d02d42
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="36cc2-103">Localizar um PFN (nome da família de pacotes) para a configuração de VPN por aplicativo</span><span class="sxs-lookup"><span data-stu-id="36cc2-103">Find a package family name (PFN) for per-app VPN configuration</span></span>
<a id="find-a-package-family-name-pfn-for-per-app-vpn-configuration" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="36cc2-104">Há duas maneiras de localizar um PFN para que você possa configurar uma VPN por aplicativo.</span><span class="sxs-lookup"><span data-stu-id="36cc2-104">There are two ways to find a PFN so that you can set up a per-app VPN.</span></span>

## <span data-ttu-id="36cc2-105">Localizar um PFN para um aplicativo que está instalado em um computador Windows 10</span><span class="sxs-lookup"><span data-stu-id="36cc2-105">Find a PFN for an app that's installed on a Windows 10 computer</span></span>
<a id="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer" class="xliff"></a>

<span data-ttu-id="36cc2-106">Se o aplicativo no qual você está trabalhando já estiver instalado em um computador Windows 10, você poderá usar o cmdlet do PowerShell [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) para obter o PFN.</span><span class="sxs-lookup"><span data-stu-id="36cc2-106">If the app that you are working with is already installed on a Windows 10 computer, you can use the [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell cmdlet to get the PFN.</span></span>

<span data-ttu-id="36cc2-107">A sintaxe para Get-AppxPackage é:</span><span class="sxs-lookup"><span data-stu-id="36cc2-107">The syntax for Get-AppxPackage is:</span></span>

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
<span data-ttu-id="36cc2-108">Você precisará executar o PowerShell como administrador para recuperar o PFN.</span><span class="sxs-lookup"><span data-stu-id="36cc2-108">You may have to run PowerShell as an admin to retrieve the PFN.</span></span>

<span data-ttu-id="36cc2-109">Por exemplo, para obter informações sobre todos os aplicativos universais instalados no computador, use `Get-AppxPackage`.</span><span class="sxs-lookup"><span data-stu-id="36cc2-109">For example, to get info about all the universal apps installed on the computer, use `Get-AppxPackage`.</span></span>

<span data-ttu-id="36cc2-110">Para obter informações sobre um aplicativo do qual você sabe o nome, ou parte do nome, use `Get-AppxPackage *<app_name>`.</span><span class="sxs-lookup"><span data-stu-id="36cc2-110">To get info about an app when you know the name or part of the name, use `Get-AppxPackage *<app_name>`.</span></span> <span data-ttu-id="36cc2-111">Observe o uso do caractere curinga, particularmente útil se você não tiver certeza do nome completo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="36cc2-111">Note the use of the wildcard character, which is particularly helpful if you're not sure of the full name of the app.</span></span> <span data-ttu-id="36cc2-112">Por exemplo, para obter as informações sobre o OneNote, use `Get-AppxPackage *OneNote`.</span><span class="sxs-lookup"><span data-stu-id="36cc2-112">For example, to get the info for OneNote, use `Get-AppxPackage *OneNote`.</span></span>


<span data-ttu-id="36cc2-113">Eis aqui as informações recuperadas do OneNote:</span><span class="sxs-lookup"><span data-stu-id="36cc2-113">Here is the information retrieved for OneNote:</span></span>

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <span data-ttu-id="36cc2-114">Localizar um PFN se o aplicativo não estiver instalado em um computador</span><span class="sxs-lookup"><span data-stu-id="36cc2-114">Find a PFN if the app is not installed on a computer</span></span>
<a id="find-a-pfn-if-the-app-is-not-installed-on-a-computer" class="xliff"></a>

1.  <span data-ttu-id="36cc2-115">Acesse https://www.microsoft.com/store/apps.</span><span class="sxs-lookup"><span data-stu-id="36cc2-115">Go to https://www.microsoft.com/store/apps.</span></span>
2.  <span data-ttu-id="36cc2-116">Insira o nome do aplicativo na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="36cc2-116">Enter the name of the app in the search bar.</span></span> <span data-ttu-id="36cc2-117">No nosso exemplo, pesquise o OneNote.</span><span class="sxs-lookup"><span data-stu-id="36cc2-117">In our example, search for OneNote.</span></span>
3.  <span data-ttu-id="36cc2-118">Escolha o link para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="36cc2-118">Choose the link to the app.</span></span> <span data-ttu-id="36cc2-119">Observe que a URL tem uma série de letras no final.</span><span class="sxs-lookup"><span data-stu-id="36cc2-119">Note that the URL has a series of letters at the end.</span></span> <span data-ttu-id="36cc2-120">No nosso exemplo, a URL tem esta aparência: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.</span><span class="sxs-lookup"><span data-stu-id="36cc2-120">In our example, the URL looks like this: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.</span></span>
4.  <span data-ttu-id="36cc2-121">Em uma guia diferente, cole a URL a seguir, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`.</span><span class="sxs-lookup"><span data-stu-id="36cc2-121">In a different tab, paste the following URL, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`.</span></span> <span data-ttu-id="36cc2-122">Substitua `<app id>` pela ID do aplicativo obtida em https://www.microsoft.com/store/apps – a série de letras no final da URL na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="36cc2-122">Replace `<app id>` with the app id that you got from https://www.microsoft.com/store/apps - that series of letters at the end of the URL in step 3.</span></span> <span data-ttu-id="36cc2-123">Em nosso exemplo do OneNote, você colaria: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.</span><span class="sxs-lookup"><span data-stu-id="36cc2-123">In our example of OneNote, you'd paste: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.</span></span>

<span data-ttu-id="36cc2-124">O Microsoft Edge exibe as informações que você deseja. No Internet Explorer, selecione **Abrir** para ver as informações.</span><span class="sxs-lookup"><span data-stu-id="36cc2-124">Microsoft Edge shows the information that you want; in Internet Explorer, choose **Open** to see the information.</span></span> <span data-ttu-id="36cc2-125">O valor PFN é fornecido na primeira linha.</span><span class="sxs-lookup"><span data-stu-id="36cc2-125">The PFN value is given on the first line.</span></span> <span data-ttu-id="36cc2-126">Veja os resultados para nosso exemplo:</span><span class="sxs-lookup"><span data-stu-id="36cc2-126">Here are the results for our example:</span></span>


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
