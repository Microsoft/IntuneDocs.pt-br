---
title: "Introdução aos aplicativos"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a086da185681a91daad214f1be2d4ff0e2827fbb
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="582f2-102">Introdução aos aplicativos</span><span class="sxs-lookup"><span data-stu-id="582f2-102">Getting started with apps</span></span>
<a id="getting-started-with-apps" class="xliff"></a>

![Uma imagem da adição do aplicativo Microsoft Word.](/intune/media/generic-add-apps.png)

<span data-ttu-id="582f2-104">Dispositivos de trabalho são inúteis sem ter os aplicativos adequados neles.</span><span class="sxs-lookup"><span data-stu-id="582f2-104">Work devices are useless without the right apps on them.</span></span> <span data-ttu-id="582f2-105">O Intune dá suporte a algumas maneiras diferentes de implantar aplicativos em seus dispositivos corporativos:</span><span class="sxs-lookup"><span data-stu-id="582f2-105">Intune supports a few different ways for you to deploy apps to your corporate devices:</span></span>

* <span data-ttu-id="582f2-106">**Instaladores de software**: nos quais você pode carregar um arquivo que será baixado nos dispositivos dos usuários</span><span class="sxs-lookup"><span data-stu-id="582f2-106">**Software installers**: where you upload a file that is downloaded to your users' devices</span></span>
* <span data-ttu-id="582f2-107">__Links externos__: para quando você tem um aplicativo em uma loja de aplicativos pública ou um aplicativo Web</span><span class="sxs-lookup"><span data-stu-id="582f2-107">__External links__: for when you have an app in a public app store or a webapp</span></span>
* <span data-ttu-id="582f2-108">**Aplicativos gerenciados**: para dispositivos iOS nos quais você precisa de gerenciamento de aplicativos móveis adicional para os aplicativos disponíveis na App Store</span><span class="sxs-lookup"><span data-stu-id="582f2-108">**Managed apps**: for iOS devices where you need additional mobile application management applied to apps available in the App Store</span></span>

<span data-ttu-id="582f2-109">Acompanhe um dos métodos de implantação de aplicativos mais rápidos existente atribuindo um aplicativo de loja pública.</span><span class="sxs-lookup"><span data-stu-id="582f2-109">You’re going to go through one of the quicker application deployment methods by assigning a public store app.</span></span>

<span data-ttu-id="582f2-110">__Como atribuo um aplicativo de loja pública?__</span><span class="sxs-lookup"><span data-stu-id="582f2-110">__How do I assign a public store app?__</span></span>

1. <span data-ttu-id="582f2-111">Entre no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="582f2-111">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="582f2-112">Usando **Pesquisar recursos**, pesquise **Intune**.</span><span class="sxs-lookup"><span data-stu-id="582f2-112">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="582f2-113">Selecione **Aplicativos Móveis** e selecione **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="582f2-113">Select **Mobile Apps**, then select **Apps**.</span></span>
4. <span data-ttu-id="582f2-114">Selecione **Adicionar** e **Aplicativo da loja iOS** como o **Tipo de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="582f2-114">Select **Add**, then **iOS store app** as the **App type**.</span></span>
5. <span data-ttu-id="582f2-115">Na caixa de texto, pesquise um aplicativo para atribuir ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="582f2-115">In the text box, search for an app to assign to the device.</span></span> <span data-ttu-id="582f2-116">Escolha o aplicativo e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="582f2-116">Choose the app, then select **OK**.</span></span>
6. <span data-ttu-id="582f2-117">Na folha **Adicionar aplicativo**, selecione **Informações do aplicativo** e verifique se todas as informações do aplicativo foram populadas.</span><span class="sxs-lookup"><span data-stu-id="582f2-117">In the **Add app** blade, select **App information**, then make sure that all of the app information populated.</span></span> <span data-ttu-id="582f2-118">Você pode adicionar outros detalhes opcionais para ajudar a organizar este aplicativo, como **Proprietário**, **Notas**, **Desenvolvedor** e uma **URL de Privacidade** para a política de privacidade da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="582f2-118">You can add other optional details to help you organize this app, like **Owner**, **Notes**, **Developer**, and a **Privacy URL** for your company’s privacy policy.</span></span>
7. <span data-ttu-id="582f2-119">Verifique se você selecionou Sim para Exibir este aplicativo em destaque no Portal da Empresa e selecione OK.</span><span class="sxs-lookup"><span data-stu-id="582f2-119">Make sure that you’ve selected Yes for Display this as a featured app in the Company Portal, then select OK.</span></span>
8. <span data-ttu-id="582f2-120">Selecione **Adicionar** para adicionar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="582f2-120">Select **Add** to add the app.</span></span> <span data-ttu-id="582f2-121">Isso levará você para a **Visão geral** do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="582f2-121">This will take you to that app’s **Overview**.</span></span> <span data-ttu-id="582f2-122">Escolha **Atribuições** e clique em **Selecionar grupos** atribuí-lo ao seu grupo de teste.</span><span class="sxs-lookup"><span data-stu-id="582f2-122">Choose **Assignments**, then click **Select groups** to assign it to your test group.</span></span> <span data-ttu-id="582f2-123">Deixe o aplicativo **Disponível** para download.</span><span class="sxs-lookup"><span data-stu-id="582f2-123">Make the app **Available** for download.</span></span> <span data-ttu-id="582f2-124">O aplicativo deverá aparecer como uma **Aplicativo em Destaque** no seu dispositivo de teste.</span><span class="sxs-lookup"><span data-stu-id="582f2-124">The app should then appear as a **Featured App** on your test device.</span></span>
