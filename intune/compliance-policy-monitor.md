---
title: "Monitorar as políticas de conformidade do dispositivo do Intune"
titleSuffix: Intune on Azure
description: "Saiba como monitorar políticas de conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d0105e49bac2af0c241fe9203c411ef7f9e7d76
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="7b1c8-103">Monitorar as políticas de conformidade do Dispositivo do Intune</span><span class="sxs-lookup"><span data-stu-id="7b1c8-103">Monitor Intune Device compliance policies</span></span>
<a id="monitor-intune-device-compliance-policies" class="xliff"></a>

<span data-ttu-id="7b1c8-104">Os relatórios de conformidade ajudam os administradores a analisarem as condições de conformidade dos dispositivos em sua organização e solucionarem rapidamente os problemas relacionados à conformidade encontrados pelos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-104">Compliance reports help admins to analyze the compliance posture of devices in their organization, and quickly troubleshoot compliance related issues encountered by users inside their organization.</span></span> <span data-ttu-id="7b1c8-105">Você pode exibir informações sobre o estado de conformidade geral dos dispositivos, estado de conformidade de uma configuração individual, estado de conformidade de uma política individual e fazer uma busca detalhada nos dispositivos individuais para exibir as configurações específicas e políticas que afetam o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-105">You can view information about the overall compliance state of devices, compliance state for an individual setting, compliance state for an individual policy and drill down into individual devices to view specific settings and policies that affect the device.</span></span>

## <span data-ttu-id="7b1c8-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7b1c8-106">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="7b1c8-107">Siga as etapas abaixo para encontrar o **painel de conformidade do Dispositivo do Intune** no portal do Azure:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-107">Follow the steps below to find the **Intune Device compliance dashboard** in the Azure portal:</span></span>

1.  <span data-ttu-id="7b1c8-108">Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-108">Go to the [Azure Portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="7b1c8-109">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-109">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3.  <span data-ttu-id="7b1c8-110">Escolha **Intune** &gt; **Conformidade do dispositivo** &gt; **Visão Geral**,então, o **Painel de conformidade do dispositivo** será aberto.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-110">Choose **Intune** &gt; **Device compliance** &gt; **Overview**, then the **Device compliance dashboard** opens.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="7b1c8-111">Os dispositivos devem ser registrados no Intune para receber as políticas de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-111">Devices must be enrolled into Intune to receive device compliance policies.</span></span>

## <span data-ttu-id="7b1c8-112">Painel de conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="7b1c8-112">Device compliance dashboard</span></span>
<a id="device-compliance-dashboard" class="xliff"></a>

<span data-ttu-id="7b1c8-113">No **Painel de conformidade do dispositivo**, você pode monitorar os estados da política de conformidade do Dispositivo, que fornecem relatórios diferentes em blocos diferentes que dão a condição de conformidade dos dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-113">In the **Device compliance dashboard**, you can monitor the Device compliance policy states, which provides different reports within different tiles that give you the compliance posture of devices in your organization.</span></span> <span data-ttu-id="7b1c8-114">Você pode exibir os seguintes relatórios:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-114">You can view the following reports:</span></span>

-   <span data-ttu-id="7b1c8-115">Conformidade geral do dispositivo agregada</span><span class="sxs-lookup"><span data-stu-id="7b1c8-115">Overall device compliance aggregate</span></span>

-   <span data-ttu-id="7b1c8-116">Conformidade do dispositivo por política</span><span class="sxs-lookup"><span data-stu-id="7b1c8-116">Per-policy device compliance</span></span>

-   <span data-ttu-id="7b1c8-117">Conformidade do dispositivo por configuração</span><span class="sxs-lookup"><span data-stu-id="7b1c8-117">Per-setting device compliance</span></span>

![Painel de conformidade do dispositivo](./media/idc-1.png)

<span data-ttu-id="7b1c8-119">Você também pode exibir as políticas específicas de conformidade e as configurações que se aplicam a um dispositivo individual e o estado de conformidade final para cada uma dessas configurações no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-119">You can also view the specific compliance policies and settings that apply to an individual device, and the final compliance state for each of those settings on the device.</span></span>

### <span data-ttu-id="7b1c8-120">Relatório da conformidade geral do dispositivo agregada</span><span class="sxs-lookup"><span data-stu-id="7b1c8-120">Overall device compliance aggregate report</span></span>
<a id="overall-device-compliance-aggregate-report" class="xliff"></a>

<span data-ttu-id="7b1c8-121">É um gráfico de rosca mostrando o estado de conformidade agregada para todos os dispositivos do Intune registrados.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-121">It’s a donut chart showing the aggregate compliance state for all Intune enrolled devices.</span></span> <span data-ttu-id="7b1c8-122">Os estados de conformidade do dispositivo são mantidos em dois bancos de dados diferentes, o Intune e o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-122">The device compliance states are kept in two different databases, Intune and Azure Active Directory.</span></span> <span data-ttu-id="7b1c8-123">Mais detalhes sobre os estados da política de conformidade do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-123">Here’s more details about the device compliance policy states:</span></span>

-   <span data-ttu-id="7b1c8-124">**Compatível**: o dispositivo aplicou com êxito uma ou mais configurações da política de conformidade do dispositivo direcionadas pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-124">**Compliant**: The device successfully applied one or more device compliance policy settings targeted by the admin.</span></span>

-   <span data-ttu-id="7b1c8-125">**Incompatível:** o dispositivo falhou ao aplicar uma ou mais configurações da política de conformidade do dispositivo direcionadas pelo administrador ou o usuário não está em conformidade com as políticas direcionadas pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-125">**Not-compliant:** The device failed to apply one or more device compliance policy settings targeted by the admin or the user hasn’t complied with the policies targeted by the admin.</span></span>

-   <span data-ttu-id="7b1c8-126">**Período de cortesia:** o dispositivo foi direcionado pelo administrador com uma ou mais configurações da política de conformidade do dispositivo, mas o usuário não aplicou as políticas ainda, significando que o dispositivo é incompatível, mas ele está no período de cortesia definido pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-126">**In-grace period:** The device was targeted by the admin with one or more device compliance policy settings, but the user hasn’t applied the policies yet, which means the device is not-compliant, but it’s in the grace-period defined by the admin.</span></span>

    -   <span data-ttu-id="7b1c8-127">Saiba mais sobre as Ações dos dispositivos incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-127">Learn more about Actions for non-compliant devices.</span></span>

-   <span data-ttu-id="7b1c8-128">**Dispositivo não sincronizado:** o dispositivo falhou ao relatar seu status da política de conformidade do dispositivo por um dos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-128">**Device not synced:** The device failed to report its device compliance policy status because one of the following:</span></span>

    -   <span data-ttu-id="7b1c8-129">**Desconhecido**: o dispositivo está offline ou falhou ao se comunicar com o Intune ou o Azure AD por outras razões.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-129">**Unknown**: The device is offline or failed to communicate with Intune or Azure AD for other reasons.</span></span>

    -   <span data-ttu-id="7b1c8-130">**Erro**: o dispositivo falhou ao se comunicar com o Intune e o Azure AD, e recebeu uma mensagem de erro com o motivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-130">**Error**: The device failed to communicate with Intune and Azure AD, and received an error message with the reason.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="7b1c8-131">Os dispositivos registrados no Intune, mas não direcionados por quaisquer políticas de conformidade do dispositivo, serão incluídos neste relatório no bloco **Compatível**.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-131">Devices that are enrolled into Intune, but not targeted by any device compliance policies will be included in this report under the **Compliant** bucket.</span></span>

#### <span data-ttu-id="7b1c8-132">Opção de detalhamento</span><span class="sxs-lookup"><span data-stu-id="7b1c8-132">Drill-down option</span></span>
<a id="drill-down-option" class="xliff"></a>

<span data-ttu-id="7b1c8-133">No **Painel de conformidade do dispositivo**, se você clicar no bloco Conformidade do dispositivo, poderá fazer uma busca detalhada em um determinado **status de conformidade**, **alias de email do usuário**, **modelo de dispositivo** e **local** para cada dispositivo que foi direcionado pelas políticas de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-133">From the **Device compliance dashboard**, If you click on the Device compliance tile, you can drill-down into a specific **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by the device compliance policies.</span></span>

![Busca detalhada do painel de conformidade do dispositivo](./media/idc-2.png)

<span data-ttu-id="7b1c8-135">Se você precisar de mais detalhes sobre um usuário específico, poderá filtrar o relatório do Gráfico de conformidade do dispositivo digitando o alias de email do usuário.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-135">If you need more details about a specific user, you can filter the Device compliance chart report by typing the user’s e-mail alias.</span></span>

![Usuário específico do painel de conformidade do dispositivo](./media/idc-3.png)

<span data-ttu-id="7b1c8-137">Você também pode clicar no status de conformidade diferente no Gráfico de conformidade do dispositivo para ver mais detalhes sobre os status da política de conformidade dos dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-137">You can also click the different compliance status on the Device compliance chart to see more details about the user’s devices compliance policy statuses.</span></span>

![Status diferentes do painel de conformidade do dispositivo](./media/idc-4.png)

#### <span data-ttu-id="7b1c8-139">Filter</span><span class="sxs-lookup"><span data-stu-id="7b1c8-139">Filter</span></span>
<a id="filter" class="xliff"></a>

<span data-ttu-id="7b1c8-140">Se você clicar no **botão Filtrar**, o filtro suspenso será aberto com as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7b1c8-140">If you click on **Filter button**, the filter fly-out opens with the following options:</span></span>

-   <span data-ttu-id="7b1c8-141">Modelo</span><span class="sxs-lookup"><span data-stu-id="7b1c8-141">Model</span></span>

    -   <span data-ttu-id="7b1c8-142">Caixa de texto que aceita uma cadeia de caracteres de pesquisa livre</span><span class="sxs-lookup"><span data-stu-id="7b1c8-142">Textbox accepting free search string</span></span>
<br></br>
-   <span data-ttu-id="7b1c8-143">Plataforma</span><span class="sxs-lookup"><span data-stu-id="7b1c8-143">Platform</span></span>

    -   <span data-ttu-id="7b1c8-144">Android</span><span class="sxs-lookup"><span data-stu-id="7b1c8-144">Android</span></span>

    -   <span data-ttu-id="7b1c8-145">iOS</span><span class="sxs-lookup"><span data-stu-id="7b1c8-145">iOS</span></span>

    -   <span data-ttu-id="7b1c8-146">Mac OS</span><span class="sxs-lookup"><span data-stu-id="7b1c8-146">Mac OS</span></span>

    -   <span data-ttu-id="7b1c8-147">Windows</span><span class="sxs-lookup"><span data-stu-id="7b1c8-147">Windows</span></span>

    -   <span data-ttu-id="7b1c8-148">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="7b1c8-148">Windows Phone</span></span>

-   <span data-ttu-id="7b1c8-149">Status</span><span class="sxs-lookup"><span data-stu-id="7b1c8-149">Status</span></span>

    -   <span data-ttu-id="7b1c8-150">Compatível</span><span class="sxs-lookup"><span data-stu-id="7b1c8-150">Compliant</span></span>

    -   <span data-ttu-id="7b1c8-151">Incompatível</span><span class="sxs-lookup"><span data-stu-id="7b1c8-151">Not Compliant</span></span>

    -   <span data-ttu-id="7b1c8-152">Período de cortesia</span><span class="sxs-lookup"><span data-stu-id="7b1c8-152">In Grace period</span></span>

    -   <span data-ttu-id="7b1c8-153">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="7b1c8-153">Unknown</span></span>

    -   <span data-ttu-id="7b1c8-154">Erro do</span><span class="sxs-lookup"><span data-stu-id="7b1c8-154">Error</span></span>

<span data-ttu-id="7b1c8-155">Se você clicar no **botão Atualizar**, o menu suspenso deverá fechar e os resultados deverão ser atualizados de acordo com os critérios do filtro selecionados.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-155">If clicking the **Update button**, the fly out should close and the results should update as per the selected filter criteria.</span></span>

##### <span data-ttu-id="7b1c8-156">Detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="7b1c8-156">Device details</span></span>
<a id="device-details" class="xliff"></a>

<span data-ttu-id="7b1c8-157">Clicar em um dispositivo abre o **Folha de Dispositivos** com o dispositivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-157">Clicking on a device, opens the **Devices Blade** with the device selected.</span></span> <span data-ttu-id="7b1c8-158">Isso fornece mais detalhes sobre a configuração da política de conformidade do dispositivo aplicada nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-158">This provides more details on the device compliance policy setting applied for that device.</span></span>

![Painel de conformidade do dispositivo](./media/idc-6.png)

<span data-ttu-id="7b1c8-160">Quando você clica na própria configuração da política do dispositivo, pode ver que o nome da política de conformidade do dispositivo originou essa configuração de conformidade do dispositivo direcionada pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-160">When you click on the device policy setting itself, you can see the device compliance policy name originated that device compliance setting targeted by the admin.</span></span>

![Nome da configuração da conformidade do dispositivo](./media/idc-7.png)

### <span data-ttu-id="7b1c8-162">Relatório de conformidade do dispositivo por política</span><span class="sxs-lookup"><span data-stu-id="7b1c8-162">Per-policy device compliance report</span></span>
<a id="per-policy-device-compliance-report" class="xliff"></a>

<span data-ttu-id="7b1c8-163">Este relatório fornece uma exibição da política por conformidade e o número total de dispositivos em cada estado de conformidade.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-163">This report provides you per compliance policy view and the total number of devices in each compliance state.</span></span> <span data-ttu-id="7b1c8-164">O título **Conformidade da política** está disponível no **Painel de conformidade do dispositivo** e mostra todas as políticas criadas anteriormente pelo administrador, as plataformas nas quais a política é aplicada e o número de dispositivos compatíveis e incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-164">The **Policy compliance** title is available from the **Device compliance dashboard**, and it shows all policies previously created by the admin, the platforms the policy is applied, number of compliant devices and number of non-compliant devices.</span></span>

![Relatório de conformidade do dispositivo por política](./media/idc-8.png)

<span data-ttu-id="7b1c8-166">Quando você clicar no bloco de Conformidade da política, então, clicar em uma das políticas de conformidade do dispositivo, poderá ver o **status de conformidade**, **alias de email do usuário**, **modelo do dispositivo** e **local** de cada dispositivo que foi direcionado por essa política de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-166">When you click on the Policy compliance tile, then click on one of the device compliance policies, you’ll be able to see the **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by that device compliance policy.</span></span>

![Bloco de conformidade da política](./media/idc-9.png)

### <span data-ttu-id="7b1c8-168">Relatório de conformidade do dispositivo por configuração</span><span class="sxs-lookup"><span data-stu-id="7b1c8-168">Per-setting device compliance report</span></span>
<a id="per-setting-device-compliance-report" class="xliff"></a>

<span data-ttu-id="7b1c8-169">Este relatório permite exibir - a configuração por conformidade - o número total de dispositivos em cada estado de conformidade.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-169">This report allows you to view, per compliance setting, the total number of devices in each compliance state.</span></span> <span data-ttu-id="7b1c8-170">O título **Conformidade das configurações** está disponível no **painel de Conformidade do dispositivo** e mostra todas as configurações da política de conformidade do dispositivo a partir de todas as políticas de conformidade do dispositivo criadas pelo administrador, as plataformas nas quais as configurações da política foram aplicadas e o número de dispositivos incompatíveis.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-170">The **Settings compliance** title is available from the **Device compliance dashboard**, and it shows all device compliance policy settings from all device compliance policies created by the admin, the platforms which the policy settings were applied, and the number of non-compliant devices.</span></span>

![Relatório de conformidade do dispositivo por configuração](./media/idc-10.png)

<span data-ttu-id="7b1c8-172">Quando você clicar no bloco de Conformidade da configuração, então, clicar em uma das configurações da política de conformidade do dispositivo, conseguirá ver o **status de conformidade**, **alias de email do usuário**, **modelo do dispositivo** e **local** de cada dispositivo que foi direcionado por essa configuração da política de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7b1c8-172">When you click on the Setting compliance tile, then click on one of the device compliance policy settings, you’ll be able to see the **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by that device compliance policy setting.</span></span>

![Bloco de conformidade da configuração](./media/idc-11.png)
