---
title: "Como monitorar as políticas de proteção de aplicativo"
titleSuffix: Intune on Azure
description: "Veja quantos usuários têm a política e faça uma busca detalhada para encontrar mais detalhes."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: de40d149818b2655a8fc3b647a7e850973814165
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="251d6-103">Como monitorar as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="251d6-103">How to monitor app protection policies</span></span>
<a id="how-to-monitor-app-protection-policies" class="xliff"></a>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="251d6-104">**Se você não estiver no portal do Azure**, este tópico explicará [como criar políticas de proteção de aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) no console clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="251d6-104">**If you are not in the Azure portal**, this topic explains [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) in the classic Intune console.</span></span>


<span data-ttu-id="251d6-105">É possível monitorar o status de conformidade das políticas de MAM (gerenciamento de aplicativo móvel) que você aplicou aos usuários na folha de proteção do aplicativo do Intune no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="251d6-105">You can monitor the compliance status of the mobile app management (MAM) policies that you've applied to users at the Intune app protection blade on the [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="251d6-106">Você poderá encontrar informações sobre os usuários afetados pelas políticas de MAM, seu status de conformidade e quaisquer problemas que os usuários possam encontrar.</span><span class="sxs-lookup"><span data-stu-id="251d6-106">You'll be able to find information about the users affected by the MAM policies, its compliance status, and any issues that your users might be experiencing.</span></span>

<span data-ttu-id="251d6-107">Há três locais diferentes para monitorar o status de conformidade:</span><span class="sxs-lookup"><span data-stu-id="251d6-107">There are three different places to monitor the compliance status:</span></span>

-   <span data-ttu-id="251d6-108">Exibição de Resumo</span><span class="sxs-lookup"><span data-stu-id="251d6-108">Summary view</span></span>

-   <span data-ttu-id="251d6-109">Exibição detalhada</span><span class="sxs-lookup"><span data-stu-id="251d6-109">Detailed view</span></span>

-   <span data-ttu-id="251d6-110">Exibição de Relatórios</span><span class="sxs-lookup"><span data-stu-id="251d6-110">Reporting view</span></span>

## <span data-ttu-id="251d6-111">Exibição de Resumo</span><span class="sxs-lookup"><span data-stu-id="251d6-111">Summary view</span></span>
<a id="summary-view" class="xliff"></a>

1. <span data-ttu-id="251d6-112">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="251d6-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="251d6-113">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="251d6-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="251d6-114">Na folha **Intune**, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="251d6-114">On the **Intune** blade, choose **Mobile apps**.</span></span>
4. <span data-ttu-id="251d6-115">Na carga de trabalho **Aplicativos móveis**, escolha **Monitorar** > **Status do usuário da proteção de aplicativo**, para ver a exibição de resumo:</span><span class="sxs-lookup"><span data-stu-id="251d6-115">In the **Mobile apps** workload, choose **Monitor** > **App protection user status**, to see the summary view:</span></span>

![Bloco de Resumo da folha de gerenciamento de aplicativos móveis do Intune](./media/app-protection-user-status-summary.png)

-   <span data-ttu-id="251d6-117">**Usuários**: o número total de usuários da sua empresa que usam os aplicativos que estão associados à política.</span><span class="sxs-lookup"><span data-stu-id="251d6-117">**Users**: The total number of users in your company who are using the apps that are associated with the policy.</span></span>

-   <span data-ttu-id="251d6-118">**GERENCIADO PELA POLÍTICA**: este é o número de usuários que usaram pelo menos um dos aplicativos no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="251d6-118">**MANAGED BY POLICY**: The number of users who have used at least one of the apps in the work context.</span></span>

-   <span data-ttu-id="251d6-119">**SEM POLÍTICA**: o número de usuários que estão usando os aplicativos associados à política, mas que não são afetados pela política.</span><span class="sxs-lookup"><span data-stu-id="251d6-119">**NO POLICY**: The number of users who are using the apps that are associated with the policy, but who are not targeted by the policy.</span></span> <span data-ttu-id="251d6-120">Você pode considerar adicionar esses usuários à política.</span><span class="sxs-lookup"><span data-stu-id="251d6-120">You might consider adding these users to the policy.</span></span>

- <span data-ttu-id="251d6-121">**Usuários sinalizados**: o número de usuários que estão tendo problemas.</span><span class="sxs-lookup"><span data-stu-id="251d6-121">**Flagged users**: The number of users who are experiencing issues.</span></span> <span data-ttu-id="251d6-122">Atualmente, apenas usuários com dispositivos com jailbreak são relatados em **Usuários sinalizados**.</span><span class="sxs-lookup"><span data-stu-id="251d6-122">Currently, only users with jailbroken devices are reported under **Flagged users**.</span></span>


## <span data-ttu-id="251d6-123">Exibição detalhada</span><span class="sxs-lookup"><span data-stu-id="251d6-123">Detailed view</span></span>
<a id="detailed-view" class="xliff"></a>
<span data-ttu-id="251d6-124">Você pode obter a exibição detalhada do resumo escolhendo os blocos **Status do usuário** (com base na plataforma do sistema operacional) e **Usuários sinalizados**.</span><span class="sxs-lookup"><span data-stu-id="251d6-124">You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.</span></span>

### <span data-ttu-id="251d6-125">Status do usuário</span><span class="sxs-lookup"><span data-stu-id="251d6-125">User status</span></span>
<a id="user-status" class="xliff"></a>
<span data-ttu-id="251d6-126">Você pode pesquisar por um único usuário e verificar o status de conformidade dele.</span><span class="sxs-lookup"><span data-stu-id="251d6-126">You can search for a single user and check the compliance status for that user.</span></span> <span data-ttu-id="251d6-127">A folha **Relatório de aplicativo** exibe as seguintes informações para um usuário selecionado:</span><span class="sxs-lookup"><span data-stu-id="251d6-127">The **App reporting** blade shows the following information for a selected user:</span></span>
- <span data-ttu-id="251d6-128">Dispositivos que estão associados à conta de usuário</span><span class="sxs-lookup"><span data-stu-id="251d6-128">Devices that are associated with the user account</span></span>

- <span data-ttu-id="251d6-129">Aplicativos com política de MAM no dispositivo</span><span class="sxs-lookup"><span data-stu-id="251d6-129">Apps with a MAM policy on the device</span></span>

- <span data-ttu-id="251d6-130">Status:</span><span class="sxs-lookup"><span data-stu-id="251d6-130">Status:</span></span>

  - <span data-ttu-id="251d6-131">**Check-in**: a política foi implantada para o usuário e o aplicativo foi usado no contexto de trabalho pelo menos uma vez.</span><span class="sxs-lookup"><span data-stu-id="251d6-131">**Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.</span></span>

  - <span data-ttu-id="251d6-132">**Check-in não realizado**: a política foi implantada para o usuário, mas o aplicativo ainda não foi usado no contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="251d6-132">**Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.</span></span>

>[!NOTE]
> <span data-ttu-id="251d6-133">Se os usuários pesquisados não tiverem a política de MAM implantada neles, você verá uma mensagem informando que o usuário não é alvo de nenhuma política de MAM.</span><span class="sxs-lookup"><span data-stu-id="251d6-133">If the users you searched for does not have the MAM policy deployed to them, you'll see a message informing you that the user is not targeted by any MAM policies.</span></span>

<span data-ttu-id="251d6-134">Para ver o relatório para um usuário, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="251d6-134">To see the reporting for a user, follow these steps:</span></span>

1.  <span data-ttu-id="251d6-135">Para selecionar um usuário, escolha o bloco **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="251d6-135">To select a user, choose the **Summary** tile.</span></span>

    ![Captura de tela 3](./media/MAM-reporting-6.png)

2. <span data-ttu-id="251d6-137">Na folha **Relatório de aplicativo** que é aberta, escolha **Selecionar usuário** para pesquisar por um usuário do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="251d6-137">On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.</span></span>

    ![Selecione a opção de usuário na folha Relatório de aplicativo](./media/MAM-reporting-2.png)

3. <span data-ttu-id="251d6-139">Selecione um usuário da lista.</span><span class="sxs-lookup"><span data-stu-id="251d6-139">Select the user from the list.</span></span> <span data-ttu-id="251d6-140">Você verá os detalhes do status de conformidade para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="251d6-140">You will see the details of the compliance status for that user.</span></span>

### <span data-ttu-id="251d6-141">Usuários sinalizados</span><span class="sxs-lookup"><span data-stu-id="251d6-141">Flagged users</span></span>
<a id="flagged-users" class="xliff"></a>
<span data-ttu-id="251d6-142">A exibição detalhada mostra a mensagem de erro, o aplicativo que foi acessado quando o erro ocorreu, a plataforma do sistema operacional dispositivo afetada e o carimbo de data/hora.</span><span class="sxs-lookup"><span data-stu-id="251d6-142">The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.</span></span>

## <span data-ttu-id="251d6-143">Exibição de Relatórios</span><span class="sxs-lookup"><span data-stu-id="251d6-143">Reporting view</span></span>
<a id="reporting-view" class="xliff"></a>

<span data-ttu-id="251d6-144">Você pode encontrar os mesmos relatórios da exibição detalhada e relatórios adicionais para ajudá-lo com o status de conformidade de política de MAM:</span><span class="sxs-lookup"><span data-stu-id="251d6-144">You can find the same reports from the Detailed view, and additional reports to help you with the MAM policy compliance status:</span></span>

![Captura de tela 4](./media/MAM-reporting-7.png)

-   <span data-ttu-id="251d6-146">**App protection user report (Relatório de usuário da proteção do aplicativo):** descreve as mesmas informações que podem ser encontradas no relatório **Status do usuário** na exibição detalhada acima.</span><span class="sxs-lookup"><span data-stu-id="251d6-146">**App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.</span></span>

-   <span data-ttu-id="251d6-147">**Relatório de aplicativo de proteção do aplicativo:** fornece dois status de proteção de aplicativo diferentes que os administradores podem selecionar antes de gerar o relatório.</span><span class="sxs-lookup"><span data-stu-id="251d6-147">**App protection app report:** It provides two different app protection statuses that admins can select before generating the report.</span></span> <span data-ttu-id="251d6-148">Os status podem ser protegidos ou não protegidos.</span><span class="sxs-lookup"><span data-stu-id="251d6-148">The statuses can be protected or unprotected.</span></span>

    -   <span data-ttu-id="251d6-149">Status do usuário para a atividade de MAM gerenciada (protegido): este relatório descreve a atividade de cada aplicativo MAM gerenciado, por usuário.</span><span class="sxs-lookup"><span data-stu-id="251d6-149">User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.</span></span>

        -   <span data-ttu-id="251d6-150">Ele mostra todos os aplicativos alvo das políticas de MAM para cada usuário e divide o status de cada aplicativo como com check-in feito nas políticas de MAM ou que eram alvo de uma política de MAM, mas nunca foi feito o check-in do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="251d6-150">It shows all apps targeted by MAM policies for each user, and break down the status of each app as checked in with MAM policies, or that was targeted with a MAM policy but the app was never checked in.</span></span>
<br></br>
    -   <span data-ttu-id="251d6-151">Status do usuário para a atividade de MAM não gerenciada (desprotegido): este relatório descreve a atividade de aplicativos habilitados para MAM atualmente não gerenciados, por usuário.</span><span class="sxs-lookup"><span data-stu-id="251d6-151">User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis.</span></span> <span data-ttu-id="251d6-152">Isso pode acontecer de acordo com os seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="251d6-152">This might happen according to the following reasons:</span></span>

        -   <span data-ttu-id="251d6-153">Esses aplicativos estão sendo usados por um usuário ou um aplicativo que no momento não é alvo de uma política de MAM.</span><span class="sxs-lookup"><span data-stu-id="251d6-153">These apps are either being used by a user or an app that is not currently targeted by a MAM policy.</span></span>

        -   <span data-ttu-id="251d6-154">Todos os aplicativos têm o check-in feito, mas não estão recebendo nenhuma política de MAM.</span><span class="sxs-lookup"><span data-stu-id="251d6-154">All apps are checked in, but aren't getting any MAM policies.</span></span>

![Captura de tela 2](./media/MAM-reporting-4.png)

## <span data-ttu-id="251d6-156">Agrupamento de tabela</span><span class="sxs-lookup"><span data-stu-id="251d6-156">Table grouping</span></span>
<a id="table-grouping" class="xliff"></a>

<span data-ttu-id="251d6-157">Depois que os dados do **Relatório do usuário de proteção de aplicativo** aparecerem, você poderá agregar os dados fazendo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="251d6-157">Once the **App protection user report** data shows up, you can aggregate data by the following:</span></span>

- <span data-ttu-id="251d6-158">**Resultado da validação:** os dados aparecem agrupados pelo status de proteção do aplicativo, que pode ser êxito, aviso ou falha.</span><span class="sxs-lookup"><span data-stu-id="251d6-158">**Validation result:** The data shows up grouped by app protection status, which can be failure, warning or success.</span></span>
- <span data-ttu-id="251d6-159">**Nome do aplicativo:** os dados aparecem agrupados por aplicativos (o nome real do aplicativo) com falha, aviso ou êxito.</span><span class="sxs-lookup"><span data-stu-id="251d6-159">**App name:** The data shows up grouped by apps (the actual app name) with failure, warning or success.</span></span>

## <span data-ttu-id="251d6-160">Exportar as atividades de proteção do aplicativo para CSV</span><span class="sxs-lookup"><span data-stu-id="251d6-160">Export app protection activities to CSV</span></span>
<a id="export-app-protection-activities-to-csv" class="xliff"></a>

<span data-ttu-id="251d6-161">Você pode exportar todas as atividades de política de proteção de aplicativo para um único arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="251d6-161">You can export all your app protection policy activities to a single .csv file.</span></span> <span data-ttu-id="251d6-162">Isso pode ser útil para analisar todos os status de proteção de aplicativo relatados dos usuários.</span><span class="sxs-lookup"><span data-stu-id="251d6-162">This can be helpful to analyze all the app protection statuses reported from the users.</span></span>

<span data-ttu-id="251d6-163">Siga estas etapas para gerar o relatório de proteção do aplicativo:</span><span class="sxs-lookup"><span data-stu-id="251d6-163">Follow these steps to generate the App protection report:</span></span>

1. <span data-ttu-id="251d6-164">Na folha Gerenciamento de aplicativo móvel do Intune, escolha Relatório de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="251d6-164">On the Intune mobile application management blade, choose App protection report.</span></span>

    ![Captura de tela-6](./media/app-protection-report-csv-2.png)

2. <span data-ttu-id="251d6-166">Escolha Sim para salvar o relatório, escolha Salvar como e selecione a pasta na qual você deseja salvar o relatório.</span><span class="sxs-lookup"><span data-stu-id="251d6-166">Choose Yes to save your report, then choose Save As and select the folder you want to save the report in.</span></span>

    ![Captura de tela-7](./media/app-protection-report-csv-1.png)

## <span data-ttu-id="251d6-168">Consulte também</span><span class="sxs-lookup"><span data-stu-id="251d6-168">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="251d6-169">Gerenciar a transferência de dados entre aplicativos iOS</span><span class="sxs-lookup"><span data-stu-id="251d6-169">Manage data transfer between iOS apps</span></span>](data-transfer-between-apps-manage-ios.md)

* [<span data-ttu-id="251d6-170">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="251d6-170">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="251d6-171">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="251d6-171">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
