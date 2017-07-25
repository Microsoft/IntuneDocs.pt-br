---
title: Obtenha um Apple MDM Push Certificate
titleSuffix: Intune on Azure
description: "Conheça as etapas para obter um Apple MDM Push Certificate para gerenciar dispositivos iOS com o Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3df23e1f29543701cf3806a8fecc132ef3ac4f43
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1b9e7-103">Obtenha um certificado push de MDM da Apple</span><span class="sxs-lookup"><span data-stu-id="1b9e7-103">Get an Apple MDM push certificate</span></span>
<a id="get-an-apple-mdm-push-certificate" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1b9e7-104">O Intune habilita o MDM (gerenciamento de dispositivo móvel) de iPads, iPhones e computadores Mac, além de permitir acesso a aplicativos e ao email da empresa aos usuários.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-104">Intune enables mobile device management (MDM) of iPads, iPhones, and Mac computers and gives users access to company email and apps.</span></span> <span data-ttu-id="1b9e7-105">Um certificado de Push MDM é necessário para o Intune gerenciar dispositivos iOS e Mac.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-105">An MDM Push certificate is required for Intune to manage iOS and Mac devices.</span></span> <span data-ttu-id="1b9e7-106">Depois de adicionar o certificado ao Intune, os usuários poderão instalar o aplicativo de Portal da Empresa para registrar seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-106">After you add the certificate to Intune, your users can install the Company Portal app to enroll their devices.</span></span> <span data-ttu-id="1b9e7-107">Você também pode configurar o gerenciamento de dispositivos iOS corporativo com o Programa de Registro de Dispositivo Apple ou registrar dispositivos usando o Apple Configurator, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-107">You can also set up corporate-owned iOS device management with Apple's Device Enrollment Program or enroll devices using Apple Configurator, for example.</span></span> <span data-ttu-id="1b9e7-108">Para obter mais informações sobre opções de registro, confira [Escolher como registrar dispositivos iOS](enrollment-method-choose-ios.md).</span><span class="sxs-lookup"><span data-stu-id="1b9e7-108">For more information about enrollment options, see [Choose how to enroll iOS devices](enrollment-method-choose-ios.md).</span></span>

## <span data-ttu-id="1b9e7-109">Etapas para obter o certificado</span><span class="sxs-lookup"><span data-stu-id="1b9e7-109">Steps to get your certificate</span></span>
<a id="steps-to-get-your-certificate" class="xliff"></a>
<span data-ttu-id="1b9e7-110">No portal do Intune, escolha **Registro de dispositivo** > **Registro da Apple** **Apple MDM Push Certificate** e siga as etapas numeradas no portal do Azure, mostradas abaixo.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-110">In the Intune portal, choose **Device enrollment** > **Apple Enrollment** **Apple MDM Push Certificate**, and then follow the numbered steps in the Azure portal, which are shown below.</span></span>

<span data-ttu-id="1b9e7-111">**Etapa 1. Baixe a solicitação de assinatura de certificado do Intune necessária para criar um Apple MDM Push Certificate.**</span><span class="sxs-lookup"><span data-stu-id="1b9e7-111">**Step 1. Download the Intune certificate signing request required to create an Apple MDM push certificate.**</span></span><br>
<span data-ttu-id="1b9e7-112">Selecione **Transferir o CSR** para baixar e salvar o arquivo .csr localmente.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-112">Select **Download your CSR** to download and save the .csr file locally.</span></span> <span data-ttu-id="1b9e7-113">O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-113">The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>

<span data-ttu-id="1b9e7-114">**Etapa 2. Criar um Apple MDM Push Certificate.**</span><span class="sxs-lookup"><span data-stu-id="1b9e7-114">**Step 2. Create an Apple MDM push certificate.**</span></span><br>
<span data-ttu-id="1b9e7-115">Selecione **Criar o MDM Push Certificate** para ir para o Portal de Certificados Push da Apple.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-115">Select **Create your MDM push Certificate** to go to the Apple Push Certificates Portal.</span></span> <span data-ttu-id="1b9e7-116">Entre com sua ID da Apple corporativa para criar o certificado push usando o arquivo .csr.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-116">Sign in with your company Apple ID to create the push certificate by using the .csr file.</span></span> <span data-ttu-id="1b9e7-117">Depois de escolher **Carregar** no Portal de Certificado Push da Apple, você receberá um arquivo .json.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-117">After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file.</span></span> <span data-ttu-id="1b9e7-118">Use este arquivo para o certificado push.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-118">Do use this file for the push certificate.</span></span> <span data-ttu-id="1b9e7-119">Conclua o download e retorne ao Apple Push Certificates Portal para Certificados de Servidores de Terceiros e escolha **Download**.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-119">Complete the download, return to the Apple Push Certificates Portal for Certificates for Third-Party Servers, and then choose **Download**.</span></span> <span data-ttu-id="1b9e7-120">Baixe o certificado push (arquivo .pem) e salve-o localmente.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-120">Download the push certificate (.pem file), and save the file locally.</span></span>

> [!NOTE]
> <span data-ttu-id="1b9e7-121">O certificado está associado à ID da Apple usada para criá-lo.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-121">The certificate is associated with the Apple ID used to create it.</span></span> <span data-ttu-id="1b9e7-122">Como prática recomendada, use uma ID da Apple empresarial para as tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-122">As a best practice, use a company Apple ID for management tasks.</span></span> <span data-ttu-id="1b9e7-123">Nunca use uma ID da Apple pessoal.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-123">Never use a personal Apple ID.</span></span>

<span data-ttu-id="1b9e7-124">**Etapa 3. Insira a ID da Apple usada para criar o Apple MDM Push Certificate.**</span><span class="sxs-lookup"><span data-stu-id="1b9e7-124">**Step 3. Enter the Apple ID used to create your Apple MDM push certificate.**</span></span>

<span data-ttu-id="1b9e7-125">**Etapa 4. Procure seu Apple MDM Push Certificate a ser carregado.**</span><span class="sxs-lookup"><span data-stu-id="1b9e7-125">**Step 4. Browse to your Apple MDM push certificate to upload.**</span></span><br>
<span data-ttu-id="1b9e7-126">Vá até o arquivo de certificado (.pem), escolha **Abrir** e selecione **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-126">Go to the certificate (.pem) file, choose **Open**, and then choose **Upload**.</span></span> <span data-ttu-id="1b9e7-127">Com o certificado push, o Intune pode registrar e gerenciar dispositivos iOS enviando por push políticas para os dispositivos móveis registrados.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-127">With the push certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.</span></span>

## <span data-ttu-id="1b9e7-128">Renovar um certificado push de MDM da Apple</span><span class="sxs-lookup"><span data-stu-id="1b9e7-128">Renew Apple MDM push certificate</span></span>
<a id="renew-apple-mdm-push-certificate" class="xliff"></a>
<span data-ttu-id="1b9e7-129">O certificado push de MDM da Apple é válido por um ano e deve ser renovado anualmente para manter o gerenciamento de dispositivos iOS e macOS.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-129">The Apple MDM push certificate is valid for one year and must be renewed annually to maintain iOS and macOS device management.</span></span> <span data-ttu-id="1b9e7-130">Se o certificado expirar, os dispositivos Apple registrados não poderão ser contatados.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-130">If your certificate expires, enrolled Apple devices cannot be contacted.</span></span>

<span data-ttu-id="1b9e7-131">O certificado está associado à ID da Apple usada para criá-lo.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-131">The certificate is associated with the Apple ID used to create it.</span></span> <span data-ttu-id="1b9e7-132">Renove o certificado push de MDM da Apple com a mesma ID da Apple usada para criá-lo.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-132">Renew the MDM push certificate with the same Apple ID used to create it.</span></span>

> [!NOTE]
> <span data-ttu-id="1b9e7-133">O certificado está associado à ID da Apple usada para criá-lo.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-133">The certificate is associated with the Apple ID used to create it.</span></span> <span data-ttu-id="1b9e7-134">Como prática recomendada, use uma ID da Apple empresarial para as tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-134">As a best practice, use a company Apple ID for management tasks.</span></span> <span data-ttu-id="1b9e7-135">Nunca use uma ID da Apple pessoal.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-135">Never use a personal Apple ID.</span></span>

1. <span data-ttu-id="1b9e7-136">No portal do Intune, escolha **Registro de dispositivo** > **Registro da Apple** e, em seguida, selecione **Apple MDM Push Certificate**.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-136">In the Intune portal, choose **Device enrollment** > **Apple Enrollment** and then select **Apple MDM Push Certificate**.</span></span>
2. <span data-ttu-id="1b9e7-137">Selecione **Transferir o CSR** para baixar e salvar o arquivo .csr localmente.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-137">Select **Download your CSR** to download and save the .csr file locally.</span></span> <span data-ttu-id="1b9e7-138">O arquivo .csr é usado para solicitar um certificado de relação de confiança do Portal de Certificados Apple Push.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-138">The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>
3. <span data-ttu-id="1b9e7-139">Localize o certificado que você deseja renovar e selecione **Renovar**.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-139">Find the certificate you want to renew and select **Renew**.</span></span>
4. <span data-ttu-id="1b9e7-140">Na tela **Renovar o certificado push**, forneça anotações para ajudá-lo a identificar o certificado no futuro, selecione **Escolher arquivo** para navegar até o novo arquivo .csr baixado e escolha **Upload**.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-140">On the **Renew Push Certificate** screen, provide notes to help you identify the certificate in the future, select **Choose File** to browse to the new .csr file you downloaded, and choose **Upload**.</span></span>
5. <span data-ttu-id="1b9e7-141">Na tela **Confirmação**, selecione **Baixar** e salve o arquivo .pem localmente.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-141">On the **Confirmation** screen, select **Download** and save the .pem file locally.</span></span>
6. <span data-ttu-id="1b9e7-142">No portal do Azure Intune, selecione o ícone de navegação do **Certificado push de MDM da Apple**, selecione o arquivo .pem baixado da Apple e escolha **Upload**.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-142">In the Azure Intune portal, select the **Apple MDM push certificate** browse icon, select the .pem file downloaded from Apple, and choose **Upload**.</span></span>

<span data-ttu-id="1b9e7-143">O certificado push de MDM da Apple aparece **Ativo** e tem 365 dias até o vencimento.</span><span class="sxs-lookup"><span data-stu-id="1b9e7-143">Your Apple MDM push certificate appears **Active** and has 365 days until expiration.</span></span>
