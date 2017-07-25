---
title: "Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune"
description: "Habilite a Defesa contra Ameaças Móveis do Skycure no console clássico do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4dad45d15fec7189fdcf184839040b9e3f9a3a48
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="304ee-103">Habilitar a Defesa contra Ameaças Móveis do Skycure no Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-103">Enable Skycure Mobile Threat Defense in Intune</span></span>
<a id="enable-skycure-mobile-threat-defense-in-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="304ee-104">Para habilitar a defesa contra ameaças móveis do Skycure, você deve já ter configurado o [Conector do Intune no console do Skycure] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).</span><span class="sxs-lookup"><span data-stu-id="304ee-104">To enable the Skycure mobile threat defense, you should have already configured the [Intune Connector in the Skycure console] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).</span></span>

## <span data-ttu-id="304ee-105">Para habilitar a conexão do Skycure MTD no Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-105">To enable the Skycure MTD connection in Intune</span></span>
<a id="to-enable-the-skycure-mtd-connection-in-intune" class="xliff"></a>

1.  <span data-ttu-id="304ee-106">Acesse o [console clássico Intune](https://manage.microsoft.com/) e insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="304ee-106">Go to the [Intune classic console](https://manage.microsoft.com/) then enter your credentials.</span></span>

2.  <span data-ttu-id="304ee-107">Escolha **Administrador** &gt; **Integração de Serviços de Terceiros**, escolha **Status do Skycure** e habilite **Sincronização com MTD** usando o botão de alternância.</span><span class="sxs-lookup"><span data-stu-id="304ee-107">Choose **Admin** &gt; **Third Party Service Integration**, then choose **Skycure Status** and enable **Synchronization with MTD** using the toggle button.</span></span>

    ![Habilitar alternância do Skycure no console clássico do Intune](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> <span data-ttu-id="304ee-109">Você precisa configurar os aplicativos do Skycure antes de criar regras de política de conformidade e configurar o acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="304ee-109">You must configure the Skycure apps before creating compliance policy rules and configuring conditional access.</span></span> <span data-ttu-id="304ee-110">Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="304ee-110">This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

<span data-ttu-id="304ee-111">Isso conclui a configuração da integração do Skycure com o Intune no console de administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="304ee-111">This completes the setup of the Skycure and Intune integration in the Intune administrator console.</span></span> <span data-ttu-id="304ee-112">As próximas etapas para implementar esta solução envolvem a implantação de aplicativos do Skycure for Work e a configuração da política de conformidade.</span><span class="sxs-lookup"><span data-stu-id="304ee-112">The next few steps to implement this solution involve deploying the Skycure for Work apps and setting up the compliance policy.</span></span>

## <span data-ttu-id="304ee-113">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="304ee-113">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

[<span data-ttu-id="304ee-114">Criar a política de conformidade da Defesa contra Ameaças Móveis do Skycure</span><span class="sxs-lookup"><span data-stu-id="304ee-114">Create Skycure Mobile Threat Defense compliance policy</span></span>](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
