---
title: "Registrar seu dispositivo iOS no gerenciamento de despesas de telecomunicações com o Intune"
description: "Saiba como registrar um dispositivo iOS no gerenciamento de despesas de telecomunicações."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope: User help
ROBOTS: 
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: a71b8d1a100100e204eb7e90ba0ab00573ffc5c6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3b10d-103">Registrar seu dispositivo iOS no gerenciamento de despesas de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="3b10d-103">Enroll your iOS device in telecom expense management</span></span>
<a id="enroll-your-ios-device-in-telecom-expense-management" class="xliff"></a>

<span data-ttu-id="3b10d-104">Sua organização pode estar usando o software de gerenciamento de despesas de telecomunicações para garantir que seus planos de voz e dados estejam sendo usados dentro dos limites aceitáveis.</span><span class="sxs-lookup"><span data-stu-id="3b10d-104">Your organization may be using telecom expense management software to ensure that their data and voice plans are being used within acceptable limits.</span></span> <span data-ttu-id="3b10d-105">Depois de ter concluído o registro de seu dispositivo, você será solicitado a selecionar a melhor categoria para esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b10d-105">Once you have completed enrolling your device, you will then be prompted select the best category for that device.</span></span>

  ![Uma captura da tela "selecionando a melhor categoria para um dispositivo" em um dispositivo iOS.](./media/ios-enroll-10-tem-select-best-category.png)

<span data-ttu-id="3b10d-108">Selecione a opção apropriada, e você receberá uma notificação para instalar o aplicativo [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) da App Store.</span><span class="sxs-lookup"><span data-stu-id="3b10d-108">Select the appropriate option, and you will receive a notification to install the [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) app from the App Store.</span></span> <span data-ttu-id="3b10d-109">O aplicativo Datalert é a forma como sua organização pode medir o uso de dados.</span><span class="sxs-lookup"><span data-stu-id="3b10d-109">The Datalert app is how your organization can measure data usage.</span></span> <span data-ttu-id="3b10d-110">Se sua organização tiver configurado a opção de registro corporativo ou estudante da Microsoft, será necessário fazer logon com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="3b10d-110">If your organization has configured the Microsoft work or school enrollment option, you will be required to log in with your work or school account.</span></span> <span data-ttu-id="3b10d-111">Se isso ainda não tiver sido habilitado, você precisará fornecer informações como o número de telefone e confirmar seu dispositivo usando um código para registrar-se no serviço Datalert do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3b10d-111">If this hasn't been enabled, you will need to provide information such as your phone number and verify your device using a code to enroll into the Datalert service from the app.</span></span>

  ![Uma captura de tela da tela de boas-vindas do aplicativo Datalert, que solicita que você vá para a próxima tela depois de fornecer uma breve explicação sobre como o Datalert pode ajudá-lo a obter o máximo possível de seu plano de dados.](./media/ios-enroll-11-tem-datalert-setup.png)

## <span data-ttu-id="3b10d-113">Registrar no Datalert usando sua conta corporativa ou de estudante da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b10d-113">Enroll into Datalert using your Microsoft work or school account</span></span>
<a id="enroll-into-datalert-using-your-microsoft-work-or-school-account" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="3b10d-114">O aplicativo [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) deve estar instalado e ativo em seu telefone para registrar-se dessa maneira.</span><span class="sxs-lookup"><span data-stu-id="3b10d-114">You need to have the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) app installed and active on your phone to enroll this way.</span></span>

1. <span data-ttu-id="3b10d-115">Selecione __Registrar-se com a conta da Microsoft__.</span><span class="sxs-lookup"><span data-stu-id="3b10d-115">Select __Enroll with Microsoft account__.</span></span>

  ![Uma imagem de tela Configurações do aplicativo Datalert, que oferece um campo de número de telefone para registrar um dispositivo na metade superior da tela e "registrar com a conta da Microsoft" na parte inferior, desde que você tenha uma conta do Microsoft Office 365 e uma assinatura do Intune.](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. <span data-ttu-id="3b10d-117">Você receberá uma notificação de que o __"Datalert" deseja abrir o "Autenticador"__.</span><span class="sxs-lookup"><span data-stu-id="3b10d-117">You'll receive a notification that __"Datalert" wants to open "Authenticator"__.</span></span> <span data-ttu-id="3b10d-118">Selecione __Abrir__.</span><span class="sxs-lookup"><span data-stu-id="3b10d-118">Select __Open__.</span></span>

  ![Uma imagem da janela pop-up solicitando que o usuário abra o aplicativo Authenticator mediante solicitação do aplicativo Datalert.](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. <span data-ttu-id="3b10d-120">Entre com sua __conta corporativa ou de estudante da Microsoft__.</span><span class="sxs-lookup"><span data-stu-id="3b10d-120">Sign in with your __Microsoft school or work account__.</span></span> <span data-ttu-id="3b10d-121">A instalação do Datalert ocorrerá por alguns instantes até ser concluída.</span><span class="sxs-lookup"><span data-stu-id="3b10d-121">Datalert setup will work for a few moments, then should complete.</span></span> <span data-ttu-id="3b10d-122">Toque em __Concluir__ após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="3b10d-122">Tap __Finish__ when it completes.</span></span>

## <span data-ttu-id="3b10d-123">Registrar no Datalert usando seu número de telefone</span><span class="sxs-lookup"><span data-stu-id="3b10d-123">Enroll into Datalert using your phone number</span></span>
<a id="enroll-into-datalert-using-your-phone-number" class="xliff"></a>

1. <span data-ttu-id="3b10d-124">Forneça o número de telefone do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3b10d-124">Provide your device's phone number.</span></span>

  ![Uma captura de tela do aplicativo Datalert solicitando um número de telefone.](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. <span data-ttu-id="3b10d-126">Você receberá um código de verificação por meio de uma mensagem SMS.</span><span class="sxs-lookup"><span data-stu-id="3b10d-126">You will then receive a verification code through an SMS message.</span></span> <span data-ttu-id="3b10d-127">Forneça o código e toque em __OK__.</span><span class="sxs-lookup"><span data-stu-id="3b10d-127">Provide the code and tap __OK__.</span></span>

  ![Uma captura de tela do aplicativo Datalert solicitando o código de verificação SMS.](./media/ios-enroll-13-tem-datalert-sms.png)

3. <span data-ttu-id="3b10d-129">Se você tiver fornecido o código de verificação, a instalação de Datalert estará concluída.</span><span class="sxs-lookup"><span data-stu-id="3b10d-129">Once you've provided the verification code, Datalert setup will complete.</span></span> <span data-ttu-id="3b10d-130">Toque em __Concluir__ e você será capaz de monitorar os dados do aplicativo Datalert.</span><span class="sxs-lookup"><span data-stu-id="3b10d-130">Tap __Finish__ and you will be able to monitor your data from the Datalert app.</span></span>

  ![Uma captura de tela do aplicativo Datalert monitorando o uso de dados de hoje.](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

<span data-ttu-id="3b10d-132">Depois de ter registrado, você começará a ver o seu uso de dados no aplicativo Datalert.</span><span class="sxs-lookup"><span data-stu-id="3b10d-132">Once you've enrolled, you will begin to see your data usage in the Datalert app.</span></span>

<span data-ttu-id="3b10d-133">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="3b10d-133">Still need help?</span></span> <span data-ttu-id="3b10d-134">Entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="3b10d-134">Contact your IT admin.</span></span> <span data-ttu-id="3b10d-135">Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3b10d-135">For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
