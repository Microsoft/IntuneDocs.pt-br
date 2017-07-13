---
title: "O dispositivo não tem um certificado | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: b1f4176704ba25f5e4ff1b1572a6f1e5ce0f620b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="13725-102">O dispositivo Android não tem um certificado exigido pelo administrador de TI</span><span class="sxs-lookup"><span data-stu-id="13725-102">Your Android device is missing a certificate required by your IT admin</span></span>
<a id="your-android-device-is-missing-a-certificate-required-by-your-it-admin" class="xliff"></a>

<span data-ttu-id="13725-103">Se o dispositivo não estiver registrado no Intune e não tiver um certificado específico exigido pelo administrador de TI, você não conseguirá entrar no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="13725-103">If your device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your IT admin, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="13725-104">Quando você tentar entrar, verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="13725-104">When you try to sign in, you'll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="13725-106">Para corrigir esse problema e obter o certificado necessário, há duas etapas principais que você precisará realizar:</span><span class="sxs-lookup"><span data-stu-id="13725-106">To fix this issue and get the required certificate, there are two main steps that you'll need to do:</span></span>

- <span data-ttu-id="13725-107">Identificar o certificado que está faltando procurando em um computador corporativo ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="13725-107">Identify the missing certificate by looking on a company or school PC.</span></span>
- <span data-ttu-id="13725-108">Usar seu dispositivo para baixar o certificado que está faltando da Internet.</span><span class="sxs-lookup"><span data-stu-id="13725-108">Use your device to download the missing certificate from the Internet.</span></span>

## <span data-ttu-id="13725-109">Identificar o certificado que está faltando procurando em um computador corporativo ou de estudante</span><span class="sxs-lookup"><span data-stu-id="13725-109">Identify the missing certificate by looking on a company or school PC</span></span>
<a id="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc" class="xliff"></a>

1. <span data-ttu-id="13725-110">Em um computador, abra o Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="13725-110">On a PC, open Internet Explorer.</span></span> <span data-ttu-id="13725-111">Se você não tiver um computador para usar para essa finalidade, entre em contato com seu administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="13725-111">If you don't have a PC to use for this purpose, contact your IT admin.</span></span> <span data-ttu-id="13725-112">Para obter as informações de contato do administrador de TI, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13725-112">For your IT admin's contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>

2. <span data-ttu-id="13725-113">Acesse o [site do Portal da Empresa](http://portal.manage.microsoft.com) e entre usando suas credenciais corporativas ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="13725-113">Go to the [Company Portal website](http://portal.manage.microsoft.com), and sign in using your work or school credentials.</span></span>

3. <span data-ttu-id="13725-114">Na extremidade direita da barra de endereços do navegador, escolha o símbolo que se parece com um cadeado, conforme mostrado a captura de tela abaixo.</span><span class="sxs-lookup"><span data-stu-id="13725-114">At the far right of the browser's address bar, choose the symbol that looks like a padlock, as shown in the following screenshot.</span></span>

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    <span data-ttu-id="13725-116">Se você não vir o símbolo de cadeado, pare e entre em contato com seu administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="13725-116">If you don't see the padlock symbol, stop and contact your IT admin.</span></span> <span data-ttu-id="13725-117">O cadeado significa que você está conectado com segurança, portanto, você não deve continuar a menos que veja esse símbolo.</span><span class="sxs-lookup"><span data-stu-id="13725-117">The lock means that you are securely signed in, so you should not proceed unless you see that symbol.</span></span>

4. <span data-ttu-id="13725-118">Escolha **Exibir certificados**.</span><span class="sxs-lookup"><span data-stu-id="13725-118">Choose **View certificates**.</span></span>

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. <span data-ttu-id="13725-120">Na caixa de diálogo **Certificado**, escolha a guia **Caminho de certificação** e identifique o certificado que precisa ser obtido da Internet.</span><span class="sxs-lookup"><span data-stu-id="13725-120">In the **Certificate** dialog box, choose the **Certification path** tab, and then identify the certificate that you need to get from the Internet.</span></span> <span data-ttu-id="13725-121">O nome do certificado de que você precisa estará na mesma posição que o que está realçado na captura de tela de exemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="13725-121">The name of the certificate that you need will be in the same position as the one that is highlighted in the previous example screenshot.</span></span>

## <span data-ttu-id="13725-122">Baixar e instalar o certificado que está faltando em seu dispositivo móvel Android</span><span class="sxs-lookup"><span data-stu-id="13725-122">Download and install the missing certificate on your Android mobile device</span></span>
<a id="download-and-install-the-missing-certificate-on-your-android-mobile-device" class="xliff"></a>

1. <span data-ttu-id="13725-123">Usando um mecanismo de pesquisa como o Bing ou o Google, pesquise o nome do certificado que está faltando identificado na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="13725-123">Using a search engine like Bing or Google, search for the name of the missing certificate that you identified in the previous section.</span></span> <span data-ttu-id="13725-124">O certificado pode terminar com “extensões” diferentes, como ".crt" ou ".pem" etc.</span><span class="sxs-lookup"><span data-stu-id="13725-124">The certificate may end in different "extensions," like ".crt" or ".pem", etc.</span></span>

2. <span data-ttu-id="13725-125">Baixe o certificado raiz do site.</span><span class="sxs-lookup"><span data-stu-id="13725-125">Download the root certificate from the website.</span></span>

3. <span data-ttu-id="13725-126">Após o certificado ser baixado, arraste a parte superior da tela para baixo para abrir suas notificações e toque no nome do certificado na lista de notificações.</span><span class="sxs-lookup"><span data-stu-id="13725-126">After the certificate downloads, drag down from the top of your device to open your notifications, and then tap the name of the certificate in the list of notifications.</span></span>

4. <span data-ttu-id="13725-127">Na caixa de diálogo **Nome do Certificado** mostrada na captura de tela abaixo, aceite o nome de certificado padrão.</span><span class="sxs-lookup"><span data-stu-id="13725-127">In the **Name the Certificate** dialog box shown in the following screenshot, accept the default certificate name.</span></span>

5. <span data-ttu-id="13725-128">Certifique-se de que o **Uso da Credencial** é definido como **Usado para aplicativos e VPN**, e, em seguida, toque em **OK**.</span><span class="sxs-lookup"><span data-stu-id="13725-128">Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.</span></span>

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. <span data-ttu-id="13725-130">Feche o aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="13725-130">Close the Company Portal app.</span></span>

7. <span data-ttu-id="13725-131">Abra o aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="13725-131">Reopen the Company Portal app.</span></span> <span data-ttu-id="13725-132">Agora, você poderá entrar no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="13725-132">You should now be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="13725-133">Se precisar de ajuda, entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="13725-133">If you need help, contact your IT admin.</span></span>

<span data-ttu-id="13725-134">Se você vir a mesma mensagem de “certificado faltando” mostrada acima e já tiver seguido o procedimento, provavelmente ainda há outro certificado que seu administrador de TI precisará ajudá-lo a instalar.</span><span class="sxs-lookup"><span data-stu-id="13725-134">If you see the same "missing certificate" message as the one shown previously, and you have already followed the procedure, there is probably still another certificate that your IT admin will need to help you install.</span></span> <span data-ttu-id="13725-135">Contate o administrador de TI para obter ajuda usando as informações de contato disponíveis no [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="13725-135">Contact your IT admin for help using contact information available at the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
