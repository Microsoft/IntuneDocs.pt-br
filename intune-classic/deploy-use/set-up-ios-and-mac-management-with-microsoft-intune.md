---
title: Set up iOS and Mac management
description: "Habilite MDM (gerenciamento de dispositivo móvel) para dispositivos iOS, inclusive iPads e iPhones, bem como dispositivos Mac OS X com o Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: af300534b3868a829c0b648d4df2587886ef749b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="048df-103">Configurar gerenciamento de dispositivos iOS e Mac</span><span class="sxs-lookup"><span data-stu-id="048df-103">Set up iOS and Mac device management</span></span>
<a id="set-up-ios-and-mac-device-management" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="048df-104">O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e dispositivos macOS, além de permitir acesso a aplicativos e ao email da empresa aos usuários.</span><span class="sxs-lookup"><span data-stu-id="048df-104">Intune enables mobile device management (MDM) of iPads, iPhones, and macOS devices and gives users access to company email and apps.</span></span> <span data-ttu-id="048df-105">Um certificado APNs (Apple Push Notification Service) é necessário para o Intune gerenciar dispositivos iOS e Mac.</span><span class="sxs-lookup"><span data-stu-id="048df-105">An Apple Push Notification service (APNs) certificate is required for Intune to manage iOS and Mac devices.</span></span> <span data-ttu-id="048df-106">Depois que o certificado for adicionado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos ou o administrador poderá configurar o [gerenciamento de dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="048df-106">After the certificate is added to Intune, users can install the Company Portal app to enroll their devices, or the admin can set up [corporate-owned iOS device management](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

1.  <span data-ttu-id="048df-107">**Configurar Intune**</span><span class="sxs-lookup"><span data-stu-id="048df-107">**Set up Intune**</span></span><br>
    <span data-ttu-id="048df-108">Se ainda não tiver feito isso, prepare-se para o gerenciamento de dispositivo móvel [configurando a autoridade de gerenciamento do dispositivo móvel](prerequisites-for-enrollment.md#step-2-set-mdm-authority) como **Microsoft Intune** e configure o MDM.</span><span class="sxs-lookup"><span data-stu-id="048df-108">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.</span></span>

2.  <span data-ttu-id="048df-109">**Obtenha uma solicitação de assinatura de certificado**</span><span class="sxs-lookup"><span data-stu-id="048df-109">**Get a certificate signing request**</span></span><br>
    <span data-ttu-id="048df-110">Como usuário administrativo, abra o [Console de administração do Microsoft Intune](https://manage.microsoft.com), acesse **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e escolha **Baixar a Solicitação de Certificado APNs**.</span><span class="sxs-lookup"><span data-stu-id="048df-110">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Download the APNs certificate request**.</span></span> <span data-ttu-id="048df-111">Salve o arquivo (.csr) da solicitação de assinatura do certificado localmente.</span><span class="sxs-lookup"><span data-stu-id="048df-111">Save the certificate signing request (.csr) file locally.</span></span> <span data-ttu-id="048df-112">O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.</span><span class="sxs-lookup"><span data-stu-id="048df-112">The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>

    ![Caixa de diálogo para carregar certificado do APNs](../media/Intune-iOS-enrollment-with-apns.png)

3.  <span data-ttu-id="048df-114">**Obtenha um certificado do serviço Apple Push Notification**</span><span class="sxs-lookup"><span data-stu-id="048df-114">**Get an Apple Push Notification service certificate**</span></span><br>
    <span data-ttu-id="048df-115">Vá para o [Portal Apple Push Certificates](http://go.microsoft.com/fwlink/?LinkId=269844) e entre com sua ID da Apple corporativa para criar o certificado APNs usando o arquivo .csr.</span><span class="sxs-lookup"><span data-stu-id="048df-115">Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844), and sign in with your company Apple ID to create the APNs certificate by using the .csr file.</span></span> <span data-ttu-id="048df-116">Depois de clicar em **Carregar** no Portal Apple Push Certificates, você receberá um arquivo .json que não pode ser usado para o APNs.</span><span class="sxs-lookup"><span data-stu-id="048df-116">After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file that cannot be used for APNs.</span></span> <span data-ttu-id="048df-117">Conclua o download e retorne ao Portal Certificados por Push da Apple para **Certificados de Servidores de Terceiros** e escolha **Download**.</span><span class="sxs-lookup"><span data-stu-id="048df-117">Complete the download, return to the Apple Push Certificates Portal for **Certificates for Third-Party Servers**, and then choose **Download**.</span></span>

    <span data-ttu-id="048df-118">Baixe o certificado APNs (.pem) e salve o arquivo localmente.</span><span class="sxs-lookup"><span data-stu-id="048df-118">Download the APNs (.pem) certificate, and save the file locally.</span></span>

    > [!NOTE]
    > <span data-ttu-id="048df-119">Todo ano, você precisa renovar (não substituir) este certificado APNs.</span><span class="sxs-lookup"><span data-stu-id="048df-119">Every year, you need to renew (not replace) this APNs certificate.</span></span> <span data-ttu-id="048df-120">Use essa mesma ID Apple para entrar no Portal de Certificados por Push da Apple para renovar o certificado e, em seguida, use as mesmas instruções deste tópico para baixar o certificado e, em seguida, carregá-lo no Intune.</span><span class="sxs-lookup"><span data-stu-id="048df-120">Use this same Apple ID to sign in to Apple's Push Certificate Portal to renew the certificate, and then use the same instructions in this topic to download the certificate, and then upload it to Intune.</span></span>

4.  <span data-ttu-id="048df-121">**Adicionar o certificado de APNs ao Intune**</span><span class="sxs-lookup"><span data-stu-id="048df-121">**Add the APNs certificate to Intune**</span></span><br>
    <span data-ttu-id="048df-122">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), vá para **Administração** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **iOS e Mac OS X** &gt; **Carregar um Certificado APNs** e escolha **Carregar o certificado APNs**.</span><span class="sxs-lookup"><span data-stu-id="048df-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Upload the APNs certificate**.</span></span> <span data-ttu-id="048df-123">Vá até o arquivo de certificado (.pem), escolha **Abrir** e digite sua **ID da Apple**.</span><span class="sxs-lookup"><span data-stu-id="048df-123">Go to the certificate (.pem) file, choose **Open**, and then enter your **Apple ID**.</span></span> <span data-ttu-id="048df-124">Com o certificado APNs, o Intune pode registrar e gerenciar dispositivos iOS enviando políticas para dispositivos móveis registrados.</span><span class="sxs-lookup"><span data-stu-id="048df-124">With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.</span></span>

5.  <span data-ttu-id="048df-125">**Informe aos usuários como registrar seus dispositivos para obter acesso aos recursos da empresa.**</span><span class="sxs-lookup"><span data-stu-id="048df-125">**Tell your users how to enroll their devices to get access to company resources.**</span></span>

    <span data-ttu-id="048df-126">Para obter instruções sobre o registro de usuário final, confira [Registrar seu dispositivo iOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) e [Registrar seu dispositivo macOS no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span><span class="sxs-lookup"><span data-stu-id="048df-126">For end-user enrollment instructions, see [Enroll your iOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) and [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span></span> <span data-ttu-id="048df-127">O processo de registro informa aos usuários o que eles podem esperar, e o que os administradores de TI podem e não podem ver em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="048df-127">The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.</span></span>

    <span data-ttu-id="048df-128">Para saber mais sobre outras tarefas de usuário final, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="048df-128">For information about other end-user tasks, see these articles:</span></span>
    - [<span data-ttu-id="048df-129">Recursos sobre a experiência do usuário final com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="048df-129">Resources about the end-user experience with Microsoft Intune</span></span>](/intune/end-user-educate)
    - [<span data-ttu-id="048df-130">Diretrizes do usuário final para dispositivos iOS e Mac</span><span class="sxs-lookup"><span data-stu-id="048df-130">End user guidance for iOS and Mac devices</span></span>](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

<span data-ttu-id="048df-131">Se sua empresa ou organização adquirir dispositivos iOS para os usuários, esses dispositivos também poderão ser registrados para gerenciamento como [dispositivos iOS de propriedade da empresa](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="048df-131">If your company or organization buys iOS devices for users, those devices can also be enrolled for management as [company-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

### <span data-ttu-id="048df-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="048df-132">See Also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="048df-133">Pré-requisitos para registro no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="048df-133">Prerequisites for enrollment with Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
