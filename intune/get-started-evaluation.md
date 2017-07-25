---
title: "Introdução ao Intune"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ef58e46118a0a44609abba5de4986b5a1526a151
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="5188b-102">O que é o Microsoft Intune?</span><span class="sxs-lookup"><span data-stu-id="5188b-102">What is Microsoft Intune?</span></span>
=======
# O que é o Microsoft Intune?
>>>>>>> live
<a id="what-is-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

![Microsoft Intune no Portal do Azure](./media/generic-intune-azure.png)

<<<<<<< HEAD
<span data-ttu-id="5188b-104">O Microsoft Intune é um dos serviços mais novos do Azure.</span><span class="sxs-lookup"><span data-stu-id="5188b-104">Microsoft Intune is one of Azure’s newest services.</span></span> <span data-ttu-id="5188b-105">Ele oferece ferramentas para gerenciar dispositivos móveis, computadores e aplicativos da sua organização que são [atualizadas regularmente](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="5188b-105">It offers tools for managing your organization’s mobile devices, PCs, and apps that are [regularly updated](whats-new.md).</span></span> <span data-ttu-id="5188b-106">Além do console moderno do Azure, o Intune também permite que você use o console Clássico.</span><span class="sxs-lookup"><span data-stu-id="5188b-106">Aside from the modern Azure console, Intune also allows you to use the Classic console.</span></span> <span data-ttu-id="5188b-107">O console Clássico é a primeira versão do Intune que ainda é acessado para [gerenciar computadores Windows com o cliente de software do Intune](/intune-classic/deploy-use/pc-management-comparison.md).</span><span class="sxs-lookup"><span data-stu-id="5188b-107">The Classic console is the first version of Intune, and where you still go to [manage Windows PCs with the Intune software client](/intune-classic/deploy-use/pc-management-comparison.md).</span></span> <span data-ttu-id="5188b-108">O portal Clássico, que é criado no Silverlight, é usado para um pequeno número de tarefas.</span><span class="sxs-lookup"><span data-stu-id="5188b-108">The Classic portal, which is built in Silverlight, is used for a small number of tasks.</span></span> <span data-ttu-id="5188b-109">Todo o resto, incluindo o gerenciamento de dispositivos móveis e aplicativos, é realizado no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="5188b-109">Everything else, including mobile device and app management, is accomplished in the Azure portal.</span></span> <span data-ttu-id="5188b-110">O guia de introdução aborda as tarefas básicas que você precisa realizar para usar o Intune no Portal do Azure com êxito.</span><span class="sxs-lookup"><span data-stu-id="5188b-110">The getting started guide takes you through the basic tasks you need to accomplish to be successful using Intune in the Azure portal.</span></span>

![A folha de ajuda e suporte, disponível na parte inferior da lista de ações na barra lateral esquerda do Intune.](./media/intune-azure-help-support-closeup.png)

## <span data-ttu-id="5188b-112">O que o Intune no Portal do Azure oferece?</span><span class="sxs-lookup"><span data-stu-id="5188b-112">What does Intune in the Azure portal provide?</span></span>
<a id="what-does-intune-in-the-azure-portal-provide" class="xliff"></a>

<span data-ttu-id="5188b-113">O Intune no Portal do Azure fornece:</span><span class="sxs-lookup"><span data-stu-id="5188b-113">Intune in the Azure portal provides you with:</span></span>

* <span data-ttu-id="5188b-114">Um console integrado para todos os seus [componentes de EMS (Enterprise Mobility + Security)](https://docs.microsoft.com/enterprise-mobility-security)</span><span class="sxs-lookup"><span data-stu-id="5188b-114">An integrated console for all your [Enterprise Mobility + Security (EMS) components](https://docs.microsoft.com/enterprise-mobility-security)</span></span>
* <span data-ttu-id="5188b-115">Um console baseado em HTML criado em padrões da Web que dá suporte aos [navegadores da Web modernos](supported-devices-browsers.md)</span><span class="sxs-lookup"><span data-stu-id="5188b-115">An HTML-based console built on web standards that supports [modern web browsers](supported-devices-browsers.md)</span></span>
* <span data-ttu-id="5188b-116">[Grupos do Azure Active Directory](groups-get-started.md) para fornecer compatibilidade entre todos os aplicativos do Azure</span><span class="sxs-lookup"><span data-stu-id="5188b-116">[Azure Active Directory groups](groups-get-started.md) to provide compatibility across all your Azure applications</span></span>
* <span data-ttu-id="5188b-117">Automação por meio da [API do Microsoft Graph](intune-graph-apis.md)</span><span class="sxs-lookup"><span data-stu-id="5188b-117">Automation through the [Microsoft Graph API](intune-graph-apis.md)</span></span>

## <span data-ttu-id="5188b-118">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5188b-118">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

<span data-ttu-id="5188b-119">Antes de começar, você deve ter uma conta de administrador e de locatário do Intune ativadas.</span><span class="sxs-lookup"><span data-stu-id="5188b-119">Before you start, you must have an Intune admin and tenant account activated.</span></span> <span data-ttu-id="5188b-120">Você pode se inscrever para essas contas [aqui](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).</span><span class="sxs-lookup"><span data-stu-id="5188b-120">You can sign up for those accounts [here](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).</span></span> <span data-ttu-id="5188b-121">Os assinantes atuais também podem executar essas atividades em seu locatário dinâmico.</span><span class="sxs-lookup"><span data-stu-id="5188b-121">Current subscribers can also complete these activities in your live tenant.</span></span> <span data-ttu-id="5188b-122">Verifique se que você está trabalhando somente em dispositivos de teste!</span><span class="sxs-lookup"><span data-stu-id="5188b-122">Make sure you’re only working on test devices!</span></span>

<span data-ttu-id="5188b-123">Também é necessário verificar se você é o administrador global da sua organização para concluir todas as tarefas no guia.</span><span class="sxs-lookup"><span data-stu-id="5188b-123">You also need to make sure that you are the global admin for your organization to complete all of the tasks in the guide.</span></span>
=======
O Microsoft Intune é um dos serviços mais novos do Azure. Ele oferece ferramentas para gerenciar dispositivos móveis, computadores e aplicativos da sua organização que são [atualizadas regularmente](whats-new.md). Além do console moderno do Azure, o Intune também permite que você use o console Clássico. O console Clássico é a primeira versão do Intune que ainda é acessado para [gerenciar computadores Windows com o cliente de software do Intune](/intune-classic/deploy-use/pc-management-comparison.md). O portal Clássico, que é criado no Silverlight, é usado para um pequeno número de tarefas. Todo o resto, incluindo o gerenciamento de dispositivos móveis e aplicativos, é realizado no Portal do Azure. O guia de introdução aborda as tarefas básicas que você precisa realizar para usar o Intune no Portal do Azure com êxito.

![A folha de ajuda e suporte, disponível na parte inferior da lista de ações na barra lateral esquerda do Intune.](./media/intune-azure-help-support-closeup.png)

## O que o Intune no Portal do Azure oferece?
<a id="what-does-intune-in-the-azure-portal-provide" class="xliff"></a>

O Intune no Portal do Azure fornece:

* Um console integrado para todos os seus [componentes de EMS (Enterprise Mobility + Security)](https://docs.microsoft.com/enterprise-mobility-security)
* Um console baseado em HTML criado em padrões da Web que dá suporte aos [navegadores da Web modernos](supported-devices-browsers.md)
* [Grupos do Azure Active Directory](groups-get-started.md) para fornecer compatibilidade entre todos os aplicativos do Azure
* Automação por meio da [API do Microsoft Graph](intune-graph-apis.md)

## Pré-requisitos
<a id="prerequisites" class="xliff"></a>

Antes de começar, você deve ter uma conta de administrador e de locatário do Intune ativadas. Você pode se inscrever para essas contas [aqui](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20). Os assinantes atuais também podem executar essas atividades em seu locatário dinâmico. Verifique se que você está trabalhando somente em dispositivos de teste!

Também é necessário verificar se você é o administrador global da sua organização para concluir todas as tarefas no guia.
>>>>>>> live
