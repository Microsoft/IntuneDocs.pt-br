---
title: Habilitar o Lookout MTP no Intune
description: "Habilite a proteção contra ameaças móveis Lookout no console de administrador do Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aad5b158e1217155c3e3ec671654ee6e81054675
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f0fc0-103">Habilite a conexão da Consulta MTD no console clássico do Intune</span><span class="sxs-lookup"><span data-stu-id="f0fc0-103">Enable Lookout MTD connection in the Intune classic console</span></span>
<a id="enable-lookout-mtd-connection-in-the-intune-classic-console" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f0fc0-104">Para habilitar a conexão do MTD (defesa contra ameaças móveis) do Lookout no Intune, você já deve ter configurado o Conector do Intune no console do Lookout.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-104">To enable the Lookout Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Connector in the Lookout console.</span></span>  <span data-ttu-id="f0fc0-105">Se você ainda não fez isso, é necessário [Configurar sua assinatura na Defesa contra Ameaças Móveis do Lookout](setup-your-lookout-mtd-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="f0fc0-105">If you have not already done so, you should [Set up your Lookout Mobile Threat Defense subscription](setup-your-lookout-mtd-subscription.md).</span></span>

<span data-ttu-id="f0fc0-106">Para habilitar a conexão com o Consulta MTP no Intune, na página **Administração** no [Console do Administrador do Microsoft Intune](https://manage.microsoft.com), escolha **Integração de Serviço de Terceiros**.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-106">To enable the Lookout MTP connection in Intune, on the **Administration** page in the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Third Party Service Integration**.</span></span> <span data-ttu-id="f0fc0-107">Escolha **Status do Lookout** e habilite **Sincronização com MTP** usando o botão de alternância.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-107">Choose **Lookout status** and enable **Synchronization with MTP** using the toggle button.</span></span>

![captura de tela da página de sincronização do Lookout com o botão de alternância habilitar realçado](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> <span data-ttu-id="f0fc0-109">Você **precisa** configurar o aplicativo do Lookout for Work antes de criar regras de política de conformidade e configurar o acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-109">You **must** configure the Lookout for Work app before creating compliance policy rules and configuring conditional access.</span></span> <span data-ttu-id="f0fc0-110">Isso garante que o aplicativo esteja pronto e disponível para os usuários finais instalarem antes que possam ter acesso a emails ou outros recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-110">This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

<span data-ttu-id="f0fc0-111">Isso conclui a configuração da integração do Lookout com o Intune no console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="f0fc0-111">This completes the setup of the Lookout and Intune integration in the Intune administrator console.</span></span>  <span data-ttu-id="f0fc0-112">As próximas etapas para implementar esta solução envolvem a implantação da política dos [aplicativos do Lookout for Work](/intune-classic/deploy-use/device-threat-protection-policy).</span><span class="sxs-lookup"><span data-stu-id="f0fc0-112">The next few steps to implement this solution involve deploying the [Lookout for Work apps](/intune-classic/deploy-use/device-threat-protection-policy) policy.</span></span>


## <span data-ttu-id="f0fc0-113">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f0fc0-113">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="f0fc0-114">Configurar o aplicativo Lookout for Work </span><span class="sxs-lookup"><span data-stu-id="f0fc0-114">Configure Lookout for Work app </span></span>](/intune-classic/deploy-use/device-threat-protection-apps)
