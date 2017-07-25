---
title: "Implantar e monitorar uma política de conformidade"
description: "Use as instruções passo a passo neste tópico para implantar e monitorar uma política de conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d0d48724a8c09a5dac0bfa2987a1eee05f218950
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="348f2-103">Implantar e monitorar política de conformidade de dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="348f2-103">Deploy and monitor a device compliance policy in Microsoft Intune</span></span>
<a id="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <span data-ttu-id="348f2-104">Implantar uma política de conformidade</span><span class="sxs-lookup"><span data-stu-id="348f2-104">Deploy a compliance policy</span></span>
<a id="deploy-a-compliance-policy" class="xliff"></a>
<span data-ttu-id="348f2-105">Implante a política de conformidade [criada](create-a-device-compliance-policy-in-microsoft-intune.md) para um ou mais grupos de usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="348f2-105">Deploy the compliance policy that you [created](create-a-device-compliance-policy-in-microsoft-intune.md) to one or more groups of users in your organization.</span></span> <span data-ttu-id="348f2-106">Quando uma política de conformidade é implantada para um usuário, os dispositivos dos usuários são verificados quanto à conformidade.</span><span class="sxs-lookup"><span data-stu-id="348f2-106">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span>

1.  <span data-ttu-id="348f2-107">No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="348f2-107">In the **Policy** workspace, select the policy you want to deploy, and then choose **Manage Deployment**.</span></span>
<span data-ttu-id="348f2-108">![Captura de tela da página de política de conformidade, mostrando a opção de menu Gerenciar Implantação na parte superior](./media/intune-sa-3c-deploy-compliance-policy2.png)</span><span class="sxs-lookup"><span data-stu-id="348f2-108">![Screenshot of the compliance policy page showing the Manage Deployment menu option at the top](./media/intune-sa-3c-deploy-compliance-policy2.png)</span></span>

2.  <span data-ttu-id="348f2-109">Na caixa de diálogo **Gerenciar Implantação**, escolha um ou mais grupos nos quais você deseja implantar a política e escolha **Adicionar** > **OK**.</span><span class="sxs-lookup"><span data-stu-id="348f2-109">In the **Manage Deployment** dialog box, choose one or more groups to which you want to deploy the policy, and then choose **Add** > **OK**.</span></span>
<span data-ttu-id="348f2-110">![Captura de tela da caixa de diálogo Gerenciar Implantação](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Use os grupos do Active Directory que você já criou e sincronizou com o Intune ou crie esses grupos manualmente no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="348f2-110">![Screenshot of the Manage Deployment dialog box](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Use Active Directory groups that you have already created and synced to Intune, or create these groups manually in the Intune console.</span></span> <span data-ttu-id="348f2-111">Para saber mais sobre como implantar políticas, consulte [Implantar uma política de configuração](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="348f2-111">To learn more about how to deploy policies, see [Deploy a configuration policy](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

<span data-ttu-id="348f2-112">Use o resumo de status e alertas na página **Visão Geral** do espaço de trabalho **Política** para identificar problemas com a política que exigem sua atenção.</span><span class="sxs-lookup"><span data-stu-id="348f2-112">Use the status summary and alerts on the **Overview** page of the **Policy** workspace to identify problems with the policy that need your attention.</span></span> <span data-ttu-id="348f2-113">Além disso, um resumo de status aparece no espaço de trabalho **Painel** .</span><span class="sxs-lookup"><span data-stu-id="348f2-113">Additionally, a status summary appears in the **Dashboard** workspace.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="348f2-114">Se você não tiver implantado uma política de conformidade e habilitar a política de acesso condicional do Exchange, todos os dispositivos de destino terão acesso.</span><span class="sxs-lookup"><span data-stu-id="348f2-114">If you have not deployed a compliance policy and you enable an Exchange conditional access policy, all targeted devices will have access.</span></span>

## <span data-ttu-id="348f2-115">Monitorar a política de conformidade</span><span class="sxs-lookup"><span data-stu-id="348f2-115">Monitor the compliance policy</span></span>
<a id="monitor-the-compliance-policy" class="xliff"></a>

#### <span data-ttu-id="348f2-116">Para exibir os dispositivos que não estão de acordo com uma política de conformidade</span><span class="sxs-lookup"><span data-stu-id="348f2-116">To view devices that do not conform to a compliance policy</span></span>
<a id="to-view-devices-that-do-not-conform-to-a-compliance-policy" class="xliff"></a>

1.  <span data-ttu-id="348f2-117">No [console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Grupos** > **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="348f2-117">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** > **All Devices**.</span></span>

2.  <span data-ttu-id="348f2-118">Clique duas vezes no nome de um dispositivo na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="348f2-118">Double-click the name of a device in the list of devices.</span></span>

3.  <span data-ttu-id="348f2-119">Escolha a guia **Política** para ver uma lista de políticas para esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="348f2-119">Choose the **Policy** tab to see a list of the policies for that device.</span></span>

4.  <span data-ttu-id="348f2-120">Da lista suspensa **Filtros**, escolha **Não está em conformidade com a política de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="348f2-120">From the **Filters** drop-down list, choose **Does not conform to compliance policy**.</span></span>
<span data-ttu-id="348f2-121">![Captura de tela que exibe a lista de opções na lista de filtros](./media/intune-sa-3e-view-device-noncompliance.png)</span><span class="sxs-lookup"><span data-stu-id="348f2-121">![Screenshot that shows the list of options in the filters list](./media/intune-sa-3e-view-device-noncompliance.png)</span></span>

#### <span data-ttu-id="348f2-122">Para exibir os relatórios de atestado de integridade</span><span class="sxs-lookup"><span data-stu-id="348f2-122">To view the health attestation reports</span></span>
<a id="to-view-the-health-attestation-reports" class="xliff"></a>

1.  <span data-ttu-id="348f2-123">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), selecione **Política**.</span><span class="sxs-lookup"><span data-stu-id="348f2-123">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Reports**.</span></span>

2.  <span data-ttu-id="348f2-124">Na página **Relatório de Atestado de Integridade – Criar um novo relatório**, você pode exibir um relatório com todos os dados do atestado de integridade do Windows 10 coletados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="348f2-124">On the **Health Attestation Report - Create a new report** page, you can view a report with all the Windows 10 health attestation data that Intune has collected.</span></span> <span data-ttu-id="348f2-125">Você também pode criar um relatório com um subconjunto dos dados usando filtros.</span><span class="sxs-lookup"><span data-stu-id="348f2-125">You can also create a report with a subset of the data by using filters.</span></span> <span data-ttu-id="348f2-126">Os filtros podem ser baseados no tipo de dispositivo, no sistema operacional ou apenas em um subconjunto de pontos de dados.</span><span class="sxs-lookup"><span data-stu-id="348f2-126">The filters can be based on the type of device, the operating system, or only a subset of data points.</span></span>

## <span data-ttu-id="348f2-127">Como o Intune resolve conflitos de política</span><span class="sxs-lookup"><span data-stu-id="348f2-127">How Intune resolves policy conflicts</span></span>
<a id="how-intune-resolves-policy-conflicts" class="xliff"></a>
<span data-ttu-id="348f2-128">Podem ocorrer conflitos de política quando várias políticas do Intune são aplicadas a um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="348f2-128">Policy conflicts can occur when multiple Intune policies are applied to a device.</span></span> <span data-ttu-id="348f2-129">Se as configurações de política se sobrepuserem, o Intune resolverá os conflitos usando as seguintes regras:</span><span class="sxs-lookup"><span data-stu-id="348f2-129">If the policy settings overlap, Intune resolves any conflicts by using the following rules:</span></span>

-   <span data-ttu-id="348f2-130">Se as configurações conflitantes forem de uma política de configuração do Intune e de uma política de conformidade, as configurações na política de conformidade têm precedência sobre as configurações na política de configuração.</span><span class="sxs-lookup"><span data-stu-id="348f2-130">If the conflicting settings are from an Intune configuration policy and a compliance policy, the settings in the compliance policy take precedence over the settings in the configuration policy.</span></span> <span data-ttu-id="348f2-131">Isso acontece mesmo que as configurações na política de configuração sejam mais seguras.</span><span class="sxs-lookup"><span data-stu-id="348f2-131">This happens even if the settings in the configuration policy are more secure.</span></span>

-   <span data-ttu-id="348f2-132">Se você tiver implantado várias políticas de conformidade, o Intune usará a mais segura dessas políticas.</span><span class="sxs-lookup"><span data-stu-id="348f2-132">If you have deployed multiple compliance policies, Intune will use the most secure of these policies.</span></span>

## <span data-ttu-id="348f2-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="348f2-133">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="348f2-134">Para saber como usar a política de conformidade com políticas de acesso condicional para controlar o acesso a serviços em sua organização, consulte [Restringir o acesso ao email e aos serviços do O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="348f2-134">To learn how to use the compliance policy with conditional access policies to control access to services in your organization, see [Restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span>


### <span data-ttu-id="348f2-135">Consulte também</span><span class="sxs-lookup"><span data-stu-id="348f2-135">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="348f2-136">Introdução a políticas de conformidade de dispositivo no Intune</span><span class="sxs-lookup"><span data-stu-id="348f2-136">Introduction to device compliance polices in Intune</span></span>](introduction-to-device-compliance-policies-in-microsoft-intune.md)
