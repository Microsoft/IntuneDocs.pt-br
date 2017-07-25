---
title: Usar aplicativos gerenciados no dispositivo iOS | Microsoft Docs
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: ee43647190da705581eaa5a266db3712391e06f2
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7ff3c-102">Usar aplicativos gerenciados no seu dispositivo iOS</span><span class="sxs-lookup"><span data-stu-id="7ff3c-102">Use managed apps on your iOS device</span></span>
<a id="use-managed-apps-on-your-ios-device" class="xliff"></a>

<span data-ttu-id="7ff3c-103">Aplicativos gerenciados são aplicativos que o administrador de TI pode configurar para ajudar a proteger os dados da empresa que você pode acessar nesse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-103">Managed apps are apps that your IT admin can set up to help protect company data that you can access in that app.</span></span> <span data-ttu-id="7ff3c-104">Ao acessar dados da empresa em um aplicativo gerenciado no seu dispositivo iOS, você pode perceber que o aplicativo funciona um pouco diferente do esperado.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-104">When you access company data in a managed app on your iOS device, you may notice that the app works a little differently than what you expect.</span></span> <span data-ttu-id="7ff3c-105">Por exemplo, não é possível copiar e colar os dados da empresa protegidos, ou você pode não conseguir salvar esses dados em determinados locais.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-105">For example, you might not be able to copy and paste protected company data, or you might not be able to save that data to certain locations.</span></span>

<span data-ttu-id="7ff3c-106">Diferentes aplicativos gerenciados também podem trabalhar juntos no seu dispositivo para permitir que você possa fazer as tarefas diárias mantendo dados corporativos protegidos.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-106">Different managed apps can also work together on your device to allow you to do your daily tasks, while keeping corporate data protected.</span></span> <span data-ttu-id="7ff3c-107">Por exemplo, se você abre um arquivo da empresa em um aplicativo gerenciado, e o outro aplicativo gerenciado é necessário para exibir o arquivo, o aplicativo gerenciado que permite que você exiba o arquivo é aberto automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-107">For example, if you open a company file in one managed app, and another managed app is required to view that file, the managed app that allows you to view the file opens automatically.</span></span> <span data-ttu-id="7ff3c-108">Se um aplicativo necessário não estiver disponível, determinadas ações, como abrir um documento ou acessar um link da Web de dentro de um documento gerenciado, poderão não estar disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-108">If a required app is not available, certain actions, like opening a document or accessing a web link from within a managed document, might not be available.</span></span>

<span data-ttu-id="7ff3c-109">Ao acessar dados da empresa em um aplicativo gerenciado, você verá uma mensagem como a mostrada abaixo, que permite que você saiba que o aplicativo que você está abrindo é gerenciado.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-109">When you access company data in a managed app, you see a message like the one below, which lets you know that the app you are opening is managed.</span></span>

![managed-apps-message-ios](./media/managed-apps-message.png)

### <span data-ttu-id="7ff3c-111">Como obtenho os aplicativos gerenciados?</span><span class="sxs-lookup"><span data-stu-id="7ff3c-111">How do I get managed apps?</span></span>
<a id="how-do-i-get-managed-apps" class="xliff"></a>
<span data-ttu-id="7ff3c-112">Você pode obter aplicativos gerenciados de duas maneiras diferentes:</span><span class="sxs-lookup"><span data-stu-id="7ff3c-112">You get managed apps in a couple of different ways:</span></span>

-   <span data-ttu-id="7ff3c-113">Quando o dispositivo é registrado no Microsoft Intune, você instala o aplicativo do seu aplicativo Portal da Empresa ou um site do Portal da Empresa, ou seu administrador de TI pode instalá-lo em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-113">When your device is enrolled in Microsoft Intune, you either install the app from your Company Portal app or Company Portal website, or your IT admin might install it on your device.</span></span> <span data-ttu-id="7ff3c-114">Para saber mais sobre o registro, consulte [Registrar o dispositivo iOS no Intune](enroll-your-device-in-intune-ios.md) ou [Registrar o dispositivo macOS no Intune](enroll-your-device-in-intune-macos.md).</span><span class="sxs-lookup"><span data-stu-id="7ff3c-114">To learn about enrolling, see [Enroll your iOS device in Intune](enroll-your-device-in-intune-ios.md) or [Enroll your macOS device in Intune](enroll-your-device-in-intune-macos.md).</span></span>

-   <span data-ttu-id="7ff3c-115">Instale um aplicativo da Windows Store e entre com sua conta de usuário corporativo que é gerenciada pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-115">You install an app from the App Store, and then sign in with your corporate user account that is managed by Intune.</span></span>

### <span data-ttu-id="7ff3c-116">O que meu administrador de TI pode gerenciar em um aplicativo?</span><span class="sxs-lookup"><span data-stu-id="7ff3c-116">What can my IT admin manage in an app?</span></span>
<a id="what-can-my-it-admin-manage-in-an-app" class="xliff"></a>
<span data-ttu-id="7ff3c-117">Aqui estão alguns exemplos de opções que seu administrador de TI pode gerenciar em um aplicativo e que podem afetar suas interações com os dados da empresa no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7ff3c-117">Here are some examples of options that your IT admin can manage in an app, and that can affect your interactions with company data on your device:</span></span>

-   <span data-ttu-id="7ff3c-118">Acesso a sites específicos</span><span class="sxs-lookup"><span data-stu-id="7ff3c-118">Access to specific websites</span></span>

-   <span data-ttu-id="7ff3c-119">Transferências de dados entre aplicativos</span><span class="sxs-lookup"><span data-stu-id="7ff3c-119">Transfers of data between apps</span></span>

-   <span data-ttu-id="7ff3c-120">Salvando arquivos</span><span class="sxs-lookup"><span data-stu-id="7ff3c-120">Saving files</span></span>

-   <span data-ttu-id="7ff3c-121">Operações de copiar e colar</span><span class="sxs-lookup"><span data-stu-id="7ff3c-121">Copy and paste operations</span></span>

-   <span data-ttu-id="7ff3c-122">Requisitos de acesso do PIN</span><span class="sxs-lookup"><span data-stu-id="7ff3c-122">PIN access requirements</span></span>

-   <span data-ttu-id="7ff3c-123">Suas credenciais, usando as credenciais da empresa</span><span class="sxs-lookup"><span data-stu-id="7ff3c-123">Your sign in, using company credentials</span></span>

-   <span data-ttu-id="7ff3c-124">Capacidade de fazer backup para a nuvem</span><span class="sxs-lookup"><span data-stu-id="7ff3c-124">Ability to back up to the cloud</span></span>

-   <span data-ttu-id="7ff3c-125">Capacidade de fazer capturas de tela</span><span class="sxs-lookup"><span data-stu-id="7ff3c-125">Ability to take screenshots</span></span>

-   <span data-ttu-id="7ff3c-126">Requisitos de criptografia de dados</span><span class="sxs-lookup"><span data-stu-id="7ff3c-126">Data encryption requirements</span></span>

<span data-ttu-id="7ff3c-127">Para obter mais informações sobre os aplicativos gerenciados em seu dispositivo, entre em contato com seu departamento de TI.</span><span class="sxs-lookup"><span data-stu-id="7ff3c-127">Contact your IT admin for more information about the managed apps on your device.</span></span> <span data-ttu-id="7ff3c-128">Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7ff3c-128">For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
