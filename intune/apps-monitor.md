---
title: "Como monitorar informações e atribuições de aplicativo"
titleSuffix: Intune on Azure
description: "Depois de atribuir um aplicativo a usuários ou dispositivos, use essas informações para ajudar a monitorar seu status."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d588ecc8f2e211b5a8ccdfe7b7720869cc6327b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1c637-103">Como monitorar atribuições e informações de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1c637-103">How to monitor app information and assignments with Microsoft Intune</span></span>
<a id="how-to-monitor-app-information-and-assignments-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1c637-104">O Intune fornece várias maneiras nas quais você pode monitorar as propriedades dos aplicativos que gerencia, além de seu status de atribuição.</span><span class="sxs-lookup"><span data-stu-id="1c637-104">Intune provides a number of ways in which you can monitor the properties of apps you manage, as well as their assignment status.</span></span>

1. <span data-ttu-id="1c637-105">Na carga de trabalho **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="1c637-105">In the **Mobile Apps** workload, choose **Manage** > **Apps**.</span></span>
2. <span data-ttu-id="1c637-106">Na lista da folha de aplicativos, escolha o aplicativo para o qual deseja ver informações.</span><span class="sxs-lookup"><span data-stu-id="1c637-106">In the list of apps blade, choose the app you want to see information for.</span></span> <span data-ttu-id="1c637-107">Em seguida, você verá a folha <*nome do aplicativo*> **Status de instalação do dispositivo**: ![folha de status de instalação do aplicativo.](./media/monitor-apps.png)</span><span class="sxs-lookup"><span data-stu-id="1c637-107">You'll then see the <*app name*> **Device install status** blade: ![App install status blade.](./media/monitor-apps.png)</span></span>

<span data-ttu-id="1c637-108">Em seguida, execute uma das ações a seguir para saber mais sobre seus aplicativos e suas atribuições.</span><span class="sxs-lookup"><span data-stu-id="1c637-108">Then, take one of the following actions to learn more about your apps, and their assignments.</span></span>

## <span data-ttu-id="1c637-109">Geral</span><span class="sxs-lookup"><span data-stu-id="1c637-109">General</span></span>
<a id="general" class="xliff"></a>

- <span data-ttu-id="1c637-110">**Visão geral** - fornece uma visão geral básica do aplicativo e informações sobre o status de qualquer atribuição para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1c637-110">**Overview** - Provides a basic overview of the app, and information about the status of any assignments for that app.</span></span> <span data-ttu-id="1c637-111">Você pode escolher um dos gráficos para abrir as folhas **Status de instalação do dispositivo** ou **Status de instalação do usuário** para obter informações mais detalhadas.</span><span class="sxs-lookup"><span data-stu-id="1c637-111">You can choose one of the charts to open the **Device install status** or **User install status** blades to get more detailed information.</span></span>

## <span data-ttu-id="1c637-112">Gerenciar</span><span class="sxs-lookup"><span data-stu-id="1c637-112">Manage</span></span>
<a id="manage" class="xliff"></a>

- <span data-ttu-id="1c637-113">**Propriedades** - permite exibir e alterar informações sobre o aplicativo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1c637-113">**Properties** - Let's you view and change information about the selected app.</span></span> <span data-ttu-id="1c637-114">Para saber mais sobre as propriedades do aplicativo, veja [Como adicionar um aplicativo ao Microsoft Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="1c637-114">For more information about app properties, see [How to add an app to Microsoft Intune](apps-add.md).</span></span>
- <span data-ttu-id="1c637-115">**Atribuições** - fornece informações sobre as atribuições para esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1c637-115">**Assignments** - Provides information about assignments for this app.</span></span> <span data-ttu-id="1c637-116">Para obter mais informações, consulte [Como atribuir aplicativos a grupos com o Microsoft Intune](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="1c637-116">For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).</span></span>

## <span data-ttu-id="1c637-117">Monitor</span><span class="sxs-lookup"><span data-stu-id="1c637-117">Monitor</span></span>
<a id="monitor" class="xliff"></a>

- <span data-ttu-id="1c637-118">**Status de instalação do dispositivo** - fornece informações detalhadas para cada dispositivo ao qual você atribuiu o aplicativo selecionado para incluir o nome do dispositivo, o sistema operacional, quando o dispositivo fez check-in por último no Intune e o status da instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1c637-118">**Device install status** - Provides detailed information for each device you assigned the selected app to including the device name, operating system, when the device last checked-in to Intune, and the status of the app installation.</span></span>
- <span data-ttu-id="1c637-119">**Status de instalação do usuário** - fornece informações detalhadas para o usuário ao qual você atribuiu o aplicativo selecionado para incluir o número de instalações do aplicativo que o usuário tem em todos os dispositivos e as informações sobre as falhas de instalação.</span><span class="sxs-lookup"><span data-stu-id="1c637-119">**User install status** - Provides detailed information fro user to you assigned the selected app to including the number of installations of the app the user has on all their devices, and information about any installation failures.</span></span>