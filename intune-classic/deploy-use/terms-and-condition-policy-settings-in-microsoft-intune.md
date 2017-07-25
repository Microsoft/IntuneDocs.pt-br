---
title: "Configurações de política de termos e condições"
description: "Você pode implantar os termos e condições do Intune em grupos de usuários para explicar como o registro, o acesso aos recursos de trabalho e o uso do aplicativo Portal da Empresa afetam usuários e dispositivos."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e8028abe5f25e4a05d79ae543d3029490c01668
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="bd64c-103">Configurações de política de termos e condições no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bd64c-103">Terms and condition policy settings in Microsoft Intune</span></span>
<a id="terms-and-condition-policy-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bd64c-104">Você pode implantar os termos e condições do Intune em grupos de usuários para explicar como o registro, o acesso aos recursos de trabalho e o aplicativo de Portal da Empresa afetam usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bd64c-104">You can deploy Intune terms and conditions to user groups to explain how enrollment, access to work resources, and the Company Portal app affect devices and users.</span></span> <span data-ttu-id="bd64c-105">Os usuários devem aceitar estes termos e condições antes de poderem usar o Portal da Empresa para registrar e acessar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="bd64c-105">Users must accept the terms and conditions before they can use the Company Portal to enroll and access their work.</span></span>

<span data-ttu-id="bd64c-106">Você pode criar e implantar várias políticas que contêm termos e condições diferentes.</span><span class="sxs-lookup"><span data-stu-id="bd64c-106">You can create and deploy multiple policies containing different terms and conditions.</span></span> <span data-ttu-id="bd64c-107">Você pode também gerar versões dos mesmos termos e condições em idiomas diferentes e, em seguida, implantá-las aos grupos apropriados.</span><span class="sxs-lookup"><span data-stu-id="bd64c-107">You can also produce versions of the same terms and conditions in different languages and then deploy these to their appropriate groups.</span></span>

## <span data-ttu-id="bd64c-108">Criar uma política de termos e condições</span><span class="sxs-lookup"><span data-stu-id="bd64c-108">Create a terms and conditions policy</span></span>
<a id="create-a-terms-and-conditions-policy" class="xliff"></a>

1.  <span data-ttu-id="bd64c-109">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-109">In the [Microsoft Intune administration console](https://manage.microsoft.com) click **Policy** &gt; **Terms and Conditions**.</span></span>

    ![Captura de tela da política de termos e condições](./media/pol-sa-terms-conditions.png)

2.  <span data-ttu-id="bd64c-111">Clique em **Adicionar** para criar uma nova política de termos e condições.</span><span class="sxs-lookup"><span data-stu-id="bd64c-111">Click **Add** to create a new terms and conditions policy.</span></span>

    <span data-ttu-id="bd64c-112">Você também pode **Editar** ou **Excluir** uma política existente.</span><span class="sxs-lookup"><span data-stu-id="bd64c-112">You can also **Edit** or **Delete** an existing policy.</span></span>

3.  <span data-ttu-id="bd64c-113">Na página **Criar Termos e Condições**, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="bd64c-113">On the **Create Terms and Conditions** page, specify the following information:</span></span>

    -   <span data-ttu-id="bd64c-114">**Nome**&mdash;Um nome de política exclusivo exibido no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="bd64c-114">**Name**&mdash;A unique policy name displayed in the Intune console.</span></span>

    -   <span data-ttu-id="bd64c-115">**Descrição**&mdash;Detalhes que ajudarão a identificar a política no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="bd64c-115">**Description**&mdash;Details that help you identify the policy in the Intune console.</span></span>

    -   <span data-ttu-id="bd64c-116">**Título**&mdash;O título que os usuários veem no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="bd64c-116">**Title**&mdash;The title users see in the company portal.</span></span>

    -   <span data-ttu-id="bd64c-117">**Texto para explicar o que significa se o usuário aceitar**&mdash;O rótulo que os usuários veem quanto a sua aceitação.</span><span class="sxs-lookup"><span data-stu-id="bd64c-117">**Text to explain what it means if the user accepts**&mdash;The label users see regarding acceptance.</span></span> <span data-ttu-id="bd64c-118">Por exemplo, "Eu concordo com os termos e condições".</span><span class="sxs-lookup"><span data-stu-id="bd64c-118">For example, “I agree to the terms and conditions.”</span></span>

4.  <span data-ttu-id="bd64c-119">Ao terminar, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-119">When you are finished, click **Save**.</span></span> <span data-ttu-id="bd64c-120">A nova política é exibida no nó **Termos e Condições** do espaço de trabalho **Política**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-120">The new policy is displayed in the **Terms and Conditions** node of the **Policy** workspace.</span></span>

## <span data-ttu-id="bd64c-121">Implantar uma política de termos e condições</span><span class="sxs-lookup"><span data-stu-id="bd64c-121">Deploy a terms and conditions policy</span></span>
<a id="deploy-a-terms-and-conditions-policy" class="xliff"></a>

1.  <span data-ttu-id="bd64c-122">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="bd64c-123">Na lista **Políticas de Termos e Condições**, selecione a política que você deseja implantar e clique em **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-123">In the **Terms and Conditions Policies** list, select the policy you want to deploy, and then click **Manage Deployment**.</span></span>

3.  <span data-ttu-id="bd64c-124">Na caixa de diálogo **Gerenciar Implantação**, selecione os grupos de usuário nos quais você implantará a política e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-124">In the **Manage Deployment** dialog box, select the user groups you will deploy the policy to, and then click **OK**.</span></span>

    <span data-ttu-id="bd64c-125">Quando os usuários de destino acessam o portal da empresa, o Intune exibe os termos e condições que você implantou.</span><span class="sxs-lookup"><span data-stu-id="bd64c-125">When targeted users access the company portal, Intune displays the terms and conditions you deployed.</span></span> <span data-ttu-id="bd64c-126">Os usuários devem aceitar esses termos antes de que possam obter acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="bd64c-126">Users must accept these terms before they can gain access to company resources.</span></span>

## <span data-ttu-id="bd64c-127">Monitorar uma política de termos e condições</span><span class="sxs-lookup"><span data-stu-id="bd64c-127">Monitor a terms and conditions policy</span></span>
<a id="monitor-a-terms-and-conditions-policy" class="xliff"></a>

1.  <span data-ttu-id="bd64c-128">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-128">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="bd64c-129">Na janela **Criar Novo Relatório**, clique em **Exibir Relatório**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-129">In the **Create New Report** window, click **View Report**.</span></span> <span data-ttu-id="bd64c-130">O relatório será aberto, detalhando quais usuários que aceitaram os termos e condições que você implantou.</span><span class="sxs-lookup"><span data-stu-id="bd64c-130">The report will open detailing which users have accepted the terms and conditions you deployed.</span></span>

### <span data-ttu-id="bd64c-131">Atualizações e controle de versão dos termos e condições</span><span class="sxs-lookup"><span data-stu-id="bd64c-131">Updates and version control for terms and conditions</span></span>
<a id="updates-and-version-control-for-terms-and-conditions" class="xliff"></a>
<span data-ttu-id="bd64c-132">Quando edita uma política de termos e condições existente, você pode escolher qual comportamento ocorre ao implantar a política.</span><span class="sxs-lookup"><span data-stu-id="bd64c-132">When you edit an existing terms and conditions policy, you can choose which behavior occurs when you deploy the policy.</span></span> <span data-ttu-id="bd64c-133">Use o procedimento a seguir para ajudá-lo a atualizar as políticas de termos e condições existentes.</span><span class="sxs-lookup"><span data-stu-id="bd64c-133">Use the following procedure to help you update existing terms and conditions policies.</span></span>

## <span data-ttu-id="bd64c-134">Trabalhar com várias versões dos termos e condições</span><span class="sxs-lookup"><span data-stu-id="bd64c-134">Work with multiple versions of terms and conditions</span></span>
<a id="work-with-multiple-versions-of-terms-and-conditions" class="xliff"></a>

1.  <span data-ttu-id="bd64c-135">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), clique em **Política** &gt; **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-135">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="bd64c-136">Selecione a política de termos e condições que deseja editar e, em seguida, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="bd64c-136">Select the terms and conditions policy that you want to edit, and then click **Edit**.</span></span>

3.  <span data-ttu-id="bd64c-137">Na página **Editar Termos e Condições**, faça as edições necessárias e especifique se essa nova versão requer que todos os usuários aceitem os termos e condições ou se somente novos usuários verão a nova versão.</span><span class="sxs-lookup"><span data-stu-id="bd64c-137">On the **Edit Terms and Conditions** page, make any required edits, and then specify whether this new version requires all users to accept the terms and conditions, or if only new users will see the new version.</span></span>

    <span data-ttu-id="bd64c-138">É recomendável aumentar o número de versão e exigir a aceitação sempre que você fizer alterações significativas em sua política de termos e condições.</span><span class="sxs-lookup"><span data-stu-id="bd64c-138">We recommend that you increase the version number and require acceptance any time you make significant changes to your terms and conditions policy.</span></span> <span data-ttu-id="bd64c-139">Se você estiver corrigindo erros de digitação ou alterando a formatação, por exemplo, mantenha o número de versão atual.</span><span class="sxs-lookup"><span data-stu-id="bd64c-139">Keep the current version number if you are fixing typos or changing formatting, for example.</span></span>

### <span data-ttu-id="bd64c-140">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bd64c-140">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="bd64c-141">Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bd64c-141">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
