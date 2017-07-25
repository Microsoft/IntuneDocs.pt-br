---
title: "Configurar a Proteção de Informações do Windows – Intune"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para gerenciar a Proteção de Informações do Windows."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ac59456dd2bc59a0a50eeab4e483dea2033c0fa
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ec831-103">Como configurar a proteção de informações do Windows no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ec831-103">How to configure Windows Information Protection in Microsoft Intune</span></span>
<a id="how-to-configure-windows-information-protection-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ec831-104">Com o aumento de dispositivos do funcionário na empresa, também há um risco crescente de vazamentos de dados acidentais por meio de aplicativos e serviços, como email, mídia social e nuvem pública, que estão fora do controle da empresa.</span><span class="sxs-lookup"><span data-stu-id="ec831-104">With the increase of employee-owned devices in the enterprise, there’s also an increasing risk of accidental data leaks through apps and services, like email, social media, and the public cloud, which are outside of the enterprise’s control.</span></span> <span data-ttu-id="ec831-105">Por exemplo, um funcionário envia as imagens mais recentes de engenharia de uma conta de email pessoal, copia e cola informações do produto em um tweet ou salva um relatório de vendas em andamento no armazenamento de nuvem pública.</span><span class="sxs-lookup"><span data-stu-id="ec831-105">For example, an employee sends the latest engineering pictures from a personal email account, copies and pastes product info into a tweet, or saves an in-progress sales report to public cloud storage.</span></span>

<span data-ttu-id="ec831-106">A **Proteção de Informações do Windows** ajuda a proteger contra esse possível vazamentos de dados sem interferir na experiência do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ec831-106">**Windows Information Protection** helps to protect against this potential data leakage without otherwise interfering with the employee experience.</span></span> <span data-ttu-id="ec831-107">Ele também ajuda a proteger dados e aplicativos corporativos e contra vazamentos de dados acidentais em dispositivos pessoais e de funcionários que os funcionários trazem para o trabalho sem a necessidade de alterações em seu ambiente ou outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ec831-107">It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.</span></span>

<span data-ttu-id="ec831-108">Essa política do Intune gerencia a lista de aplicativos protegidos pelo Windows Information Protection, os locais de rede corporativa, o nível de proteção e as configurações de criptografia.</span><span class="sxs-lookup"><span data-stu-id="ec831-108">This Intune policy manages the list of apps protected by Windows Information Protection, enterprise network locations, protection level, and encryption settings.</span></span>

>[!NOTE]
> <span data-ttu-id="ec831-109">Para usar o aplicativo Portal da Empresa do Windows 10 com a Proteção de Informações do Windows, você deve adicionar o aplicativo Portal da Empresa no modo **Isento** da Proteção de Informações do Windows.</span><span class="sxs-lookup"><span data-stu-id="ec831-109">To use the Windows 10 Company Portal app with Windows Information Protection, you must add the Company Portal app under the Windows Information Protection mode of **Exempt**.</span></span> 

### <span data-ttu-id="ec831-110">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ec831-110">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="ec831-111">Para obter mais informações, consulte [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Proteger seus dados empresariais usando o Windows Information Protection).</span><span class="sxs-lookup"><span data-stu-id="ec831-111">For more information, see [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>
