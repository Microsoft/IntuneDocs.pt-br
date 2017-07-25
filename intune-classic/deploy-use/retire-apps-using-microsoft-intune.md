---
title: Desativar aplicativos
description: Saiba como desativar ou desinstalar aplicativos usando o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1851fa03d36ffe42a49fd557cdd0c2c6250726f4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="4325a-103">Desativar aplicativos usando o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4325a-103">Retire apps using Microsoft Intune</span></span>
<a id="retire-apps-using-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4325a-104">Para desativar um aplicativo, basta desinstalá-lo.</span><span class="sxs-lookup"><span data-stu-id="4325a-104">To retire an app, you simply uninstall it.</span></span> <span data-ttu-id="4325a-105">Quando você implanta e gerencia aplicativos com o Intune, o processo de desinstalação do aplicativo é o mesmo para computadores Windows e dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="4325a-105">When you deploy and manage apps with Intune, the process for uninstalling the app is the same for both mobile devices and Windows PCs.</span></span> <span data-ttu-id="4325a-106">O aplicativo deve dar suporte ao processo de desinstalação para que o procedimento tenha êxito.</span><span class="sxs-lookup"><span data-stu-id="4325a-106">The app must support the uninstallation process for this procedure to succeed.</span></span>

## <span data-ttu-id="4325a-107">Desinstalar um aplicativo</span><span class="sxs-lookup"><span data-stu-id="4325a-107">Uninstall an app</span></span>
<a id="uninstall-an-app" class="xliff"></a>

1.  <span data-ttu-id="4325a-108">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Aplicativos** &gt; **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="4325a-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="4325a-109">Selecione o aplicativo que você deseja desinstalar (que já foi implantado anteriormente) e selecione **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="4325a-109">Select the app you want to uninstall (one that has been previously deployed), and then choose **Manage Deployment**.</span></span>

3.  <span data-ttu-id="4325a-110">Na página **Ação de Implantação** , selecione **Desinstalar** na coluna **Aprovação** .</span><span class="sxs-lookup"><span data-stu-id="4325a-110">On the **Deployment Action** page, select **Uninstall** from the **Approval** column.</span></span>

<span data-ttu-id="4325a-111">Quando o dispositivo ou computador verificar se existem aplicativos em seguida, o aplicativo será desinstalado.</span><span class="sxs-lookup"><span data-stu-id="4325a-111">When the device or computer next checks for apps, the app will be uninstalled.</span></span>

### <span data-ttu-id="4325a-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4325a-112">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="4325a-113">Adicionar aplicativos no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4325a-113">Add apps in Microsoft Intune</span></span>](add-apps.md)
