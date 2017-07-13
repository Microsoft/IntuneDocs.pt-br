---
title: "Validar políticas de proteção do aplicativo"
titleSuffix: Intune on Azure
description: "Este tópico descreve como você pode testar e validar se a política de proteção de aplicativo está configurada corretamente e funcionando conforme esperado."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ddfecbcd8709569ff177e6c7021d3e8fdab39290
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="75112-103">Como validar sua configuração de política de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="75112-103">How to validate your app protection policy setup</span></span>
<a id="how-to-validate-your-app-protection-policy-setup" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="75112-104">Este tópico fornece informações sobre a verificação de problemas depois que você configura a política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75112-104">This topic provides information on checking for issues after you set up an app protection policy.</span></span> <span data-ttu-id="75112-105">Estas diretrizes se aplicam às políticas de proteção de aplicativo no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="75112-105">This guidance applies to app protection policies in the Azure portal.</span></span>

### <span data-ttu-id="75112-106">Verificar sintomas</span><span class="sxs-lookup"><span data-stu-id="75112-106">Checking for symptoms</span></span>
<a id="checking-for-symptoms" class="xliff"></a>
<span data-ttu-id="75112-107">Não é provável que os usuários relatem problemas, pois a proteção de aplicativo é uma ferramenta de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="75112-107">Users are unlikely to report issues since app protection is a data protection tool.</span></span> <span data-ttu-id="75112-108">Se houver um problema com a configuração de proteção de aplicativo, o usuário terá acesso irrestrito, como teria sem a proteção de aplicativo, e não estará ciente de que há um problema.</span><span class="sxs-lookup"><span data-stu-id="75112-108">If there is a problem with the app protection configuration the user will have unrestricted access, as they would have without app protection, and would not be aware that there is an issue.</span></span> <span data-ttu-id="75112-109">Por esse motivo, é recomendável que você valide sua configuração de proteção de aplicativo realizando um piloto de suas políticas de proteção de aplicativo com um pequeno grupo de usuários que podem testar deliberadamente as restrições de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75112-109">For this reason we recommend that you validate your app protection configuration by piloting your app protection policies with a small group of users who can deliberately test the app protection restrictions.</span></span>


### <span data-ttu-id="75112-110">O que verificar</span><span class="sxs-lookup"><span data-stu-id="75112-110">What to check</span></span>
<a id="what-to-check" class="xliff"></a>

<span data-ttu-id="75112-111">Se o teste mostra que o comportamento da política de proteção de aplicativo não é esperado, é recomendável que você verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="75112-111">If testing shows that your app protection policy behavior is not as anticipated, we recommend that you check the following:</span></span>

- <span data-ttu-id="75112-112">Os usuários estão licenciados para a proteção de aplicativo?</span><span class="sxs-lookup"><span data-stu-id="75112-112">Are the users licensed for app protection?</span></span>
- <span data-ttu-id="75112-113">Os usuários estão licenciados para o O365?</span><span class="sxs-lookup"><span data-stu-id="75112-113">Are the users licensed for O365?</span></span>
- <span data-ttu-id="75112-114">O status de cada um dos aplicativos de proteção de aplicativo dos usuários.</span><span class="sxs-lookup"><span data-stu-id="75112-114">The status of each of the users' app protection apps.</span></span> <span data-ttu-id="75112-115">Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.</span><span class="sxs-lookup"><span data-stu-id="75112-115">The possible statuses for the apps are **Checked in** and **Not checked in**.</span></span>

#### <span data-ttu-id="75112-116">Status de proteção de aplicativo do usuário</span><span class="sxs-lookup"><span data-stu-id="75112-116">User app protection status</span></span>
<a id="user-app-protection-status" class="xliff"></a>
1. <span data-ttu-id="75112-117">No Portal do Azure, escolha **Gerenciar aplicativos** > **Monitorar** >  **Status de usuário de proteção do aplicativo** > **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="75112-117">In the Azure portal choose **Manage apps** > **Monitor** >  **App protection user status** > **users**.</span></span>

2. <span data-ttu-id="75112-118">Escolha um usuário na lista ou procure e escolha um usuário e escolha **Selecionar usuário**.</span><span class="sxs-lookup"><span data-stu-id="75112-118">Choose a user from the list or search for and choose a user, then choose **Select user**.</span></span> <span data-ttu-id="75112-119">Na parte superior da coluna **Relatórios de aplicativo**, você verá se o usuário está licenciado para proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75112-119">At the top of the **App reporting** column you will see whether the user is licensed for app protection.</span></span> <span data-ttu-id="75112-120">Abaixo disso, você verá se o usuário está licenciado para o O365 e o status do aplicativo para todos os dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="75112-120">Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.</span></span>



### <span data-ttu-id="75112-121">O que fazer</span><span class="sxs-lookup"><span data-stu-id="75112-121">What to do</span></span>
<a id="what-to-do" class="xliff"></a>
<span data-ttu-id="75112-122">Aqui estão as ações necessárias com base no status do usuário:</span><span class="sxs-lookup"><span data-stu-id="75112-122">Here are the actions to take based on the user status:</span></span>

- <span data-ttu-id="75112-123">Se o usuário não está licenciado para proteção de aplicativo, atribua uma licença do Intune ao usuário.</span><span class="sxs-lookup"><span data-stu-id="75112-123">If the user is not licensed for app protection, assign an Intune license to the user.</span></span>
- <span data-ttu-id="75112-124">Se o usuário não está licenciado para o O365, obtenha uma licença para o usuário.</span><span class="sxs-lookup"><span data-stu-id="75112-124">If the user is not licensed for O365 obtain a license for the user.</span></span>
- <span data-ttu-id="75112-125">Se o aplicativo do usuário é listado como **Não submetido a check-in**, verifique se você configurou corretamente uma política de proteção de aplicativo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="75112-125">If a user's app is listed as **Not checked in**, check if you've correctly configured a app protection policy for that app.</span></span>
- <span data-ttu-id="75112-126">Verifique se essas condições são aplicadas a todos os usuários aos quais você deseja que as políticas de proteção de aplicativo sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="75112-126">Ensure that these conditions are applied across all users to which you want app protection policies to apply.</span></span>

### <span data-ttu-id="75112-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="75112-127">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="75112-128">O que é a política de proteção de aplicativo do Intune?</span><span class="sxs-lookup"><span data-stu-id="75112-128">What is Intune app protection policy?</span></span>](app-protection-policies.md)
