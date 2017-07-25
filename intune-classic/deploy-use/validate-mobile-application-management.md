---
title: "Validar a configuração de MAM"
description: "Este tópico descreve como você pode testar e validar se a política de MAM está configurada corretamente e funcionando conforme o esperado."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ms.reviewer: joglocke
ms.custom: intune-classic
ms.openlocfilehash: 1e22be7b238cce195ee88c938b1cca009c0b21d3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2052b-103">Validar a configuração do gerenciamento de aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="2052b-103">Validating your mobile application management setup</span></span>
<a id="validating-your-mobile-application-management-setup" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="2052b-104">Este tópico fornece informações sobre a verificação de problemas depois que você configura o MAM (gerenciamento de aplicativos móveis).</span><span class="sxs-lookup"><span data-stu-id="2052b-104">This topic provides information on checking for issues after you set up mobile application management (MAM).</span></span> <span data-ttu-id="2052b-105">Esta orientação se aplica a políticas de MAM no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="2052b-105">This guidance applies to MAM policies in the Azure portal.</span></span>

### <span data-ttu-id="2052b-106">Verificar sintomas</span><span class="sxs-lookup"><span data-stu-id="2052b-106">Checking for symptoms</span></span>
<a id="checking-for-symptoms" class="xliff"></a>
<span data-ttu-id="2052b-107">Não é provável que os usuários relatem problemas, pois o MAM é uma ferramenta de proteção de dados.</span><span class="sxs-lookup"><span data-stu-id="2052b-107">Users are unlikely to report issues since MAM is a data protection tool.</span></span> <span data-ttu-id="2052b-108">Se houver um problema com a configuração de MAM, o usuário terá acesso irrestrito, como teria sem o MAM, e não estará ciente de que há um problema.</span><span class="sxs-lookup"><span data-stu-id="2052b-108">If there is a problem with the MAM configuration the user will have unrestricted access, as they would have without MAM, and would not be aware that there is an issue.</span></span> <span data-ttu-id="2052b-109">Por esse motivo, é recomendável que você valide sua configuração de MAM realizando um piloto de suas políticas de MAM com um pequeno grupo de usuários que podem testar deliberadamente as restrições de MAM.</span><span class="sxs-lookup"><span data-stu-id="2052b-109">For this reason we recommend that you validate your MAM configuration by piloting your MAM policies with a small group of users who can deliberately test the MAM restrictions.</span></span>


### <span data-ttu-id="2052b-110">O que verificar</span><span class="sxs-lookup"><span data-stu-id="2052b-110">What to check</span></span>
<a id="what-to-check" class="xliff"></a>

<span data-ttu-id="2052b-111">Se o teste mostrar que o comportamento da política de MAM não é esperado, é recomendável que você verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2052b-111">If testing shows that your MAM policy behavior is not as anticipated, we recommend that you check the following:</span></span>

- <span data-ttu-id="2052b-112">Os usuários estão licenciados para MAM?</span><span class="sxs-lookup"><span data-stu-id="2052b-112">Are the users licensed for MAM?</span></span>
- <span data-ttu-id="2052b-113">Os usuários estão licenciados para o O365?</span><span class="sxs-lookup"><span data-stu-id="2052b-113">Are the users licensed for O365?</span></span>
- <span data-ttu-id="2052b-114">O status de cada um dos aplicativos MAM dos usuários.</span><span class="sxs-lookup"><span data-stu-id="2052b-114">The status of each of the users' MAM apps.</span></span> <span data-ttu-id="2052b-115">Os status possíveis para os aplicativos são **Submetido a check-in** e **Não submetido a check-in**.</span><span class="sxs-lookup"><span data-stu-id="2052b-115">The possible statuses for the apps are **Checked in** and **Not checked in**.</span></span>

#### <span data-ttu-id="2052b-116">Status MAM do usuário</span><span class="sxs-lookup"><span data-stu-id="2052b-116">User MAM status</span></span>
<a id="user-mam-status" class="xliff"></a>
1. <span data-ttu-id="2052b-117">No Portal do Azure, escolha **Gerenciamento de aplicativos móveis do Intune** > **Configurações** > **Gerenciamento de aplicativo** > **Todas as configurações** > **Relatórios de aplicativos pelo usuário** > **usuários**.</span><span class="sxs-lookup"><span data-stu-id="2052b-117">In the Azure portal choose **Intune mobile application management** > **settings** > **app management** > **All settings** > **App reporting by user** > **users**.</span></span>

2. <span data-ttu-id="2052b-118">Escolha um usuário na lista ou procure e escolha um usuário e escolha **Selecionar usuário**.</span><span class="sxs-lookup"><span data-stu-id="2052b-118">Choose a user from the list or search for and choose a user, then choose **Select user**.</span></span> <span data-ttu-id="2052b-119">Na parte superior da coluna **Relatórios de aplicativo**, você verá se o usuário está licenciado para MAM.</span><span class="sxs-lookup"><span data-stu-id="2052b-119">At the top of the **App reporting** column you will see whether the user is licensed for MAM.</span></span> <span data-ttu-id="2052b-120">Abaixo disso, você verá se o usuário está licenciado para o O365 e o status do aplicativo para todos os dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="2052b-120">Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.</span></span>

![Status de aplicativo para MAM](..\media\ts-mam-user-apps.png)

### <span data-ttu-id="2052b-122">O que fazer</span><span class="sxs-lookup"><span data-stu-id="2052b-122">What to do</span></span>
<a id="what-to-do" class="xliff"></a>
<span data-ttu-id="2052b-123">Aqui estão as ações necessárias com base no status do usuário:</span><span class="sxs-lookup"><span data-stu-id="2052b-123">Here are the actions to take based on the user status:</span></span>

- <span data-ttu-id="2052b-124">Se o usuário não está licenciado para MAM, atribua uma licença do Intune ao usuário, conforme descrito em [Gerenciar licenças do Intune](/intune/setup-steps).</span><span class="sxs-lookup"><span data-stu-id="2052b-124">If the user is not licensed for MAM, assign an Intune license to the user as described in [Manage Intune licenses](/intune/setup-steps).</span></span>
- <span data-ttu-id="2052b-125">Se o usuário não está licenciado para o O365, obtenha uma licença para o usuário.</span><span class="sxs-lookup"><span data-stu-id="2052b-125">If the user is not licensed for O365 obtain a license for the user.</span></span>
- <span data-ttu-id="2052b-126">Se o aplicativo do usuário é listado como **Não submetido a check-in**, verifique se você configurou corretamente uma política de MAM para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2052b-126">If a user's app is listed as **Not checked in**, check if you've correctly configured a MAM policy for that app.</span></span>
- <span data-ttu-id="2052b-127">Verifique se essas condições são aplicadas a todos os usuários aos quais você deseja que as políticas MAM sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="2052b-127">Ensure that these conditions are applied across all users to which you want MAM policies to apply.</span></span>

### <span data-ttu-id="2052b-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2052b-128">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="2052b-129">Preparar-se para configurar as políticas de gerenciamento de aplicativos móveis com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2052b-129">Get ready to configure mobile app management policies with Microsoft Intune</span></span>](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="2052b-130">Proteger dados de aplicativo usando políticas de gerenciamento de aplicativos móveis com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2052b-130">Protect app data using mobile app management policies with Microsoft Intune</span></span>](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
