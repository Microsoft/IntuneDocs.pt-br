---
title: "O dispositivo não tem um certificado obrigatório | Microsoft Docs"
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
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 910fe2bc4e616c3b60d351efaffe173f58c04bc6
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1e81a-102">Falta ao dispositivo um certificado necessário</span><span class="sxs-lookup"><span data-stu-id="1e81a-102">Your device is missing a required certificate</span></span>
<a id="your-device-is-missing-a-required-certificate" class="xliff"></a>

## <span data-ttu-id="1e81a-103">O que é um certificado?</span><span class="sxs-lookup"><span data-stu-id="1e81a-103">What's a certificate?</span></span>
<a id="whats-a-certificate" class="xliff"></a>

<span data-ttu-id="1e81a-104">[Criptografia](https://technet.microsoft.com/library/cc962030.aspx) a ciência de fornecer segurança para informações.</span><span class="sxs-lookup"><span data-stu-id="1e81a-104">[Cryptography](https://technet.microsoft.com/library/cc962030.aspx) is the science of providing security for information.</span></span> <span data-ttu-id="1e81a-105">Tradicionalmente, a criptografia tem sido usada para passar mensagens codificadas, a fim de [garantir que a comunicação é mantida em sigilo](https://technet.microsoft.com/library/cc962019.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e81a-105">Traditionally, cryptography has been used to pass coded messages to [ensure that communication is kept secret](https://technet.microsoft.com/library/cc962019.aspx).</span></span> <span data-ttu-id="1e81a-106">Em sua forma mais simples, a criptografia substitui ou transpõe letras para criar uma mensagem codificada ilegível, embaralhada ou oculta.</span><span class="sxs-lookup"><span data-stu-id="1e81a-106">In its simpliest form, cryptography substitutes or transposes letters to create a coded message into an unreadable, scrambled, or hidden message.</span></span> <span data-ttu-id="1e81a-107">Somente alguém com uma chave de decodificação, ou _certificado_, pode converter a mensagem codificada de volta ao seu formato original e legível.</span><span class="sxs-lookup"><span data-stu-id="1e81a-107">Only someone with a decoding key, or _certificate_, can convert the coded message back into its original, readable form.</span></span> <span data-ttu-id="1e81a-108">Seu dispositivo Android usa certificados com o Intune para garantir que a comunicação entre o dispositivo e seus recursos organizacionais, como email e documentos, é mantida segura de uma extremidade, pelo ar, até a outra.</span><span class="sxs-lookup"><span data-stu-id="1e81a-108">Your Android device uses certificates with Intune to make sure that communications between your device and your organizational resources, such as email and documents, are kept safe from one end, through the air, to the other.</span></span>

## <span data-ttu-id="1e81a-109">Correção de problemas de certificados</span><span class="sxs-lookup"><span data-stu-id="1e81a-109">Fixing certificate issues</span></span>
<a id="fixing-certificate-issues" class="xliff"></a>

<span data-ttu-id="1e81a-110">Se o dispositivo Android não estiver registrado no Intune e não tiver um certificado específico exigido pelo administrador de TI, você não conseguirá entrar no aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="1e81a-110">If your Android device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your IT admin, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="1e81a-111">Quando você tentar entrar, verá a seguinte mensagem:</span><span class="sxs-lookup"><span data-stu-id="1e81a-111">When you try to sign in, you'll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="1e81a-113">A primeira etapa que você deve tentar é verificar se o dispositivo [não tem um certificado que normalmente vem pré-instalado nele](your-device-is-missing-a-preinstalled-certificate-android.md).</span><span class="sxs-lookup"><span data-stu-id="1e81a-113">The first step you should try is to see if your device is [missing a certificate that usually comes preinstalled on it](your-device-is-missing-a-preinstalled-certificate-android.md).</span></span>

<span data-ttu-id="1e81a-114">Se isso não funcionar, o administrador de TI poderá [exigir a instalação de um segundo certificado para segurança adicional](your-device-is-missing-an-IT-required-certificate-android.md).</span><span class="sxs-lookup"><span data-stu-id="1e81a-114">If this doesn't work, your IT admin could [require you to install a second certificate for additional security](your-device-is-missing-an-IT-required-certificate-android.md).</span></span>

<span data-ttu-id="1e81a-115">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="1e81a-115">Still need help?</span></span> <span data-ttu-id="1e81a-116">Entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="1e81a-116">Contact your IT admin.</span></span> <span data-ttu-id="1e81a-117">Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1e81a-117">For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
