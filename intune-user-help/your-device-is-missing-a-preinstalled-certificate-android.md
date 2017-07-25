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
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 63595e9905a220c326c315f5932379a9b743d3de
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1d610-102">Seu dispositivo Android não tem um certificado que normalmente vem instalado no telefone</span><span class="sxs-lookup"><span data-stu-id="1d610-102">Your Android device is missing a certificate that usually comes installed on your phone</span></span>
<a id="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone" class="xliff"></a>

<span data-ttu-id="1d610-103">Se o dispositivo não estiver registrado no Intune e não tiver um certificado que normalmente vem instalado no telefone, você não conseguirá entrar no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1d610-103">If your device isn’t enrolled in Intune, and it’s missing a certificate that usually comes installed on your phone, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="1d610-104">Quando você tentar entrar, verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="1d610-104">When you try to sign in, you’ll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="1d610-106">É possível corrigir esse problema obtendo o certificado necessário na [página de certificados do Digicert](https://www.digicert.com/digicert-root-certificates.htm).</span><span class="sxs-lookup"><span data-stu-id="1d610-106">You can fix this issue by getting the required certificate from [Digicert's certificate page](https://www.digicert.com/digicert-root-certificates.htm).</span></span>

1. <span data-ttu-id="1d610-107">Encontre e baixe o certificado __Baltimore CyberTrust Root__.</span><span class="sxs-lookup"><span data-stu-id="1d610-107">Find and download the __Baltimore CyberTrust Root__ certificate.</span></span> <span data-ttu-id="1d610-108">Também é possível baixá-lo diretamente [aqui](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).</span><span class="sxs-lookup"><span data-stu-id="1d610-108">You can also download it directly from [here](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).</span></span>

2. <span data-ttu-id="1d610-109">Arraste para baixo da parte superior da tela para exibir a lista das notificações recentes e toque em **BaltimoreCyberTrustRoot.crt**.</span><span class="sxs-lookup"><span data-stu-id="1d610-109">Drag down from the top of the screen to display the list of your recent notifications, and tap **BaltimoreCyberTrustRoot.crt**.</span></span>

3. <span data-ttu-id="1d610-110">Seu dispositivo solicitará que você **Nomeie o Certificado**.</span><span class="sxs-lookup"><span data-stu-id="1d610-110">Your device will ask you to **Name the Certificate**.</span></span> <span data-ttu-id="1d610-111">Não altere o nome padrão do certificado exibido.</span><span class="sxs-lookup"><span data-stu-id="1d610-111">Do not change the default certificate name that appears.</span></span>

4. <span data-ttu-id="1d610-112">Certifique-se de que o **Uso da Credencial** é definido como **Usado para aplicativos e VPN**, e, em seguida, toque em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d610-112">Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.</span></span>

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. <span data-ttu-id="1d610-114">Feche o navegador e o aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1d610-114">Close your browser and the Company Portal app.</span></span>

6. <span data-ttu-id="1d610-115">Abra o aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1d610-115">Reopen the Company Portal app.</span></span> <span data-ttu-id="1d610-116">Agora, você poderá entrar no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1d610-116">You should now be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="1d610-117">Se você ainda não conseguir usar o aplicativo Portal da Empresa, contate o administrador de TI usando as informações fornecidas no [site do Portal da Empresa](http://portal.manage.microsoft.com) para obter mais instruções.</span><span class="sxs-lookup"><span data-stu-id="1d610-117">If you still cannot use the Company Portal app, contact your IT admin using the information provided on the [Company Portal website](http://portal.manage.microsoft.com) for further instructions.</span></span>

>[!NOTE]
> <span data-ttu-id="1d610-118">Se a instalação desse certificado não resolver o problema e você receber outra mensagem “Certificado ausente”, será necessário realizar etapas adicionais para [instalar o certificado ausente](your-device-is-missing-an-IT-required-certificate-android.md).</span><span class="sxs-lookup"><span data-stu-id="1d610-118">If installing this certificate doesn't solve the issue, and you see a different "missing certificate" message, you will need to take additional steps to [install the missing certificate](your-device-is-missing-an-IT-required-certificate-android.md).</span></span>

<span data-ttu-id="1d610-119">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="1d610-119">Still need help?</span></span> <span data-ttu-id="1d610-120">Entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="1d610-120">Contact your IT admin.</span></span> <span data-ttu-id="1d610-121">Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1d610-121">For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
