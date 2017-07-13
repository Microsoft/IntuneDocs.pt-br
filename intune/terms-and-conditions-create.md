---
title: "Definir termos e condições no Microsoft Intune"
titleSuffix: Intune on Azure
description: "Definir termos e condições que os usuários veem no Portal da Empresa do Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0262b8068ddf134de5ffec0965476fb513ceb9ab
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="98166-103">Conferir se os usuários aceitaram os termos da empresa para acesso</span><span class="sxs-lookup"><span data-stu-id="98166-103">Ensure users accept company terms for access</span></span>
<a id="ensure-users-accept-company-terms-for-access" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="98166-104">Como administrador do Intune, você pode exigir que os usuários aceitem os termos e condições de sua empresa antes de poderem usar o Portal da Empresa para registrar seus dispositivos e acessar recursos como aplicativos e email da empresa.</span><span class="sxs-lookup"><span data-stu-id="98166-104">As an Intune admin, you can require that users accept your company's terms and conditions before they can use the Company Portal to enroll their devices and access resources like company apps and email.</span></span> <span data-ttu-id="98166-105">A configuração dos termos e condições é opcional.</span><span class="sxs-lookup"><span data-stu-id="98166-105">Configuration of terms and conditions is optional.</span></span>

<span data-ttu-id="98166-106">Você pode criar vários conjuntos de termos e atribuí-los a grupos diferentes, por exemplo, para oferecer suporte a idiomas diferentes.</span><span class="sxs-lookup"><span data-stu-id="98166-106">You can create multiple sets of terms and assign them to different groups, such as to support different languages.</span></span>

## <span data-ttu-id="98166-107">Criar termos e condições</span><span class="sxs-lookup"><span data-stu-id="98166-107">Create terms and conditions</span></span>
<a id="create-terms-and-conditions" class="xliff"></a>
<span data-ttu-id="98166-108">Conclua estas etapas para criar termos e condições.</span><span class="sxs-lookup"><span data-stu-id="98166-108">Complete these steps to create terms and conditions.</span></span> <span data-ttu-id="98166-109">O nome de exibição e a descrição são para uso administrativo enquanto as propriedades dos termos são exibidas para os usuários no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98166-109">The display name and description are for administrative use while terms properties are displayed to users in the Company Portal.</span></span>

1. <span data-ttu-id="98166-110">No portal do Intune, escolha **Registro de dispositivo** e, depois, **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="98166-110">In the Intune portal, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="98166-111">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="98166-111">Select **Create**.</span></span>
<span data-ttu-id="98166-112">![Captura de tela do portal do Intune mostrando o botão Criar para termos e condições](media/terms-create-terms.png)</span><span class="sxs-lookup"><span data-stu-id="98166-112">![Screenshot of the Intune portal showing Create button for terms and conditions](media/terms-create-terms.png)</span></span>
3. <span data-ttu-id="98166-113">Na folha expandida, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="98166-113">On the expanded blade, specify the following information:</span></span>

   - <span data-ttu-id="98166-114">**Nome de exibição**: o nome para os termos no portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="98166-114">**Display name**: The name for the terms in the Intune portal.</span></span> <span data-ttu-id="98166-115">Os usuários não veem esse nome.</span><span class="sxs-lookup"><span data-stu-id="98166-115">Users don't see this name.</span></span>

   - <span data-ttu-id="98166-116">**Descrição**: detalhes opcionais que ajudam a identificar esse conjunto de termos no portal do Intune.</span><span class="sxs-lookup"><span data-stu-id="98166-116">**Description**: Optional details that help you identify this set of terms in the Intune portal.</span></span>

4. <span data-ttu-id="98166-117">Selecione a seta ao lado de Definir termos de uso para abrir a folha de Termos e Condições e, em seguida, insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="98166-117">Select the arrow next to Define terms of use to open the Terms and Conditions blade, and then enter the following information:</span></span>

   ![Captura da tela de aceitação de termos e condições do usuário final com o resumo dos termos](./media/terms-summary-create.png)

   - <span data-ttu-id="98166-119">**Título**: o nome dos termos que os usuários veem no Portal da Empresa acima de **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="98166-119">**Title**: The name for your terms that users see in the Company Portal above the **Summary**.</span></span>
   - <span data-ttu-id="98166-120">**Resumo dos Termos**: texto que explica a implicação de os usuários aceitarem os termos.</span><span class="sxs-lookup"><span data-stu-id="98166-120">**Summary of Terms**: Text that explains what it means when users accept the terms.</span></span> <span data-ttu-id="98166-121">Por exemplo, “Ao registrar seu dispositivo, você concorda com os termos de uso definidos pela Contoso”.</span><span class="sxs-lookup"><span data-stu-id="98166-121">For example, "By enrolling your device, you are agreeing to the terms of use set out by Contoso.</span></span> <span data-ttu-id="98166-122">Leia os termos com atenção antes de continuar".</span><span class="sxs-lookup"><span data-stu-id="98166-122">Read the terms carefully before proceeding."</span></span>
   - <span data-ttu-id="98166-123">**Termos e Condições**: os termos e condições que os usuários veem e devem aceitar ou rejeitar.</span><span class="sxs-lookup"><span data-stu-id="98166-123">**Terms and Conditions**: The terms and conditions that users see and must either accept or reject.</span></span>

5. <span data-ttu-id="98166-124">Selecione **OK** e **Criar**.</span><span class="sxs-lookup"><span data-stu-id="98166-124">Select **Ok** and then select **Create**.</span></span>

## <span data-ttu-id="98166-125">Ver como os termos são exibidos para os usuários</span><span class="sxs-lookup"><span data-stu-id="98166-125">See how terms are displayed to your users</span></span>
<a id="see-how-terms-are-displayed-to-your-users" class="xliff"></a>
<span data-ttu-id="98166-126">O exemplo a seguir mostra o **Título** e o **Resumo de Termos** no console de administrador e no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98166-126">The following example shows the **Title** and **Summary of Terms** in the admin console and Company Portal.</span></span>

![Captura de tela do Título e do Resumo de Termos no console de administrador e no Portal da Empresa.](./media/terms-summary-terms.png)

<span data-ttu-id="98166-128">O exemplo a seguir mostra os termos e condições no console de administrador e no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98166-128">The following example shows the terms and conditions in the admin console and the Company Portal.</span></span>

![Captura de tela dos termos e condições no console de administrador e no Portal da Empresa.](./media/terms-properties-terms.png)

## <span data-ttu-id="98166-130">Atribuir termos e condições</span><span class="sxs-lookup"><span data-stu-id="98166-130">Assign terms and conditions</span></span>
<a id="assign-terms-and-conditions" class="xliff"></a>

<span data-ttu-id="98166-131">Você pode atribuir termos e condições a grupos de usuários que devem aceitá-los antes de usar o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="98166-131">You can assign terms and conditions to groups of user who must accept them before using the Company Portal.</span></span>

1. <span data-ttu-id="98166-132">No portal do Intune, escolha **Registro de dispositivo** e, depois, **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="98166-132">In the Intune portal, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="98166-133">Na lista de termos e condições, selecione as condições que você deseja atribuir e, em seguida, selecione **Grupos Atribuídos**.</span><span class="sxs-lookup"><span data-stu-id="98166-133">In the list of terms and conditions, select the terms you want to assign, and then select **Assigned Groups**.</span></span>
<span data-ttu-id="98166-134">![Captura de tela da folha de atribuição de grupo do portal do Intune mostrando o botão Selecionar Grupo e o botão Selecionar para a atribuição de termos e condições](media/terms-assign-groups.png)</span><span class="sxs-lookup"><span data-stu-id="98166-134">![Screenshot of the Intune portal's Assign Group blade showing Select Group button and Select button for terms and conditions assignment](media/terms-assign-groups.png)</span></span>
3. <span data-ttu-id="98166-135">Clique no botão **Selecionar Grupo** e, na folha **Selecionar Grupos**, selecione os grupos a que você deseja atribuir os termos e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="98166-135">Click the **Select Group** button and in the **Select Groups** blade, select the groups you want to assign the terms, and then click **Select**.</span></span> <span data-ttu-id="98166-136">Não é possível atribui Termos e Condições a grupos dinâmicos.</span><span class="sxs-lookup"><span data-stu-id="98166-136">Dynamic groups cannot be assigned Terms and Conditions.</span></span>
4. <span data-ttu-id="98166-137">Na folha **Grupos Atribuídos**, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="98166-137">In the **Assigned Groups** blade, click **Save**.</span></span>  <span data-ttu-id="98166-138">Os termos e condições agora estão atribuídos aos usuários nos grupos selecionados.</span><span class="sxs-lookup"><span data-stu-id="98166-138">The terms and conditions are now assigned to users in the selected groups.</span></span> <span data-ttu-id="98166-139">Os usuários serão solicitados a aceitar os termos na próxima vez que acessarem o portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="98166-139">Users will be prompted to accept terms the next time they access the company portal.</span></span> <span data-ttu-id="98166-140">Os termos e condições precisam ser aceitos apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="98166-140">The terms and conditions only need to be accepted once.</span></span> <span data-ttu-id="98166-141">Usuários com vários dispositivos não precisam aceitá-los em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="98166-141">Users with multiple devices don't have to accept on each device.</span></span>


## <span data-ttu-id="98166-142">Monitorar os termos e condições</span><span class="sxs-lookup"><span data-stu-id="98166-142">Monitor terms and conditions</span></span>
<a id="monitor-terms-and-conditions" class="xliff"></a>

1. <span data-ttu-id="98166-143">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="98166-143">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span> <span data-ttu-id="98166-144">Na folha Intune, escolha **Registro de dispositivo** e escolha **Termos e Condições**.</span><span class="sxs-lookup"><span data-stu-id="98166-144">On the Intune blade, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="98166-145">Na lista de termos e condições, selecione os termos para os quais deseja exibir a aceitação e, em seguida, selecione **Status de Aceitação**.</span><span class="sxs-lookup"><span data-stu-id="98166-145">In the list of terms and conditions, select the terms you want to view acceptance for, and then select **Acceptance Statuses**.</span></span>

## <span data-ttu-id="98166-146">Trabalhar com várias versões dos termos e condições</span><span class="sxs-lookup"><span data-stu-id="98166-146">Work with multiple versions of terms and conditions</span></span>
<a id="work-with-multiple-versions-of-terms-and-conditions" class="xliff"></a>
<span data-ttu-id="98166-147">Você pode editar seus termos e condições e gerenciar suas versões.</span><span class="sxs-lookup"><span data-stu-id="98166-147">You can edit your terms and conditions and manage their versions.</span></span> <span data-ttu-id="98166-148">É recomendável aumentar o número de versão e exigir a aceitação sempre que você fizer alterações significativas em seus termos e condições.</span><span class="sxs-lookup"><span data-stu-id="98166-148">We recommend that you increase the version number and require acceptance any time you make significant changes to your terms and conditions.</span></span> <span data-ttu-id="98166-149">Se você estiver corrigindo erros de digitação ou alterando a formatação, por exemplo, mantenha o número de versão atual.</span><span class="sxs-lookup"><span data-stu-id="98166-149">Keep the current version number if, for example, you are fixing typos or changing formatting.</span></span>

1. <span data-ttu-id="98166-150">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="98166-150">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="98166-151">Na folha do Intune, escolha **Registro de dispositivo**, escolha **Termos e Condições**, selecione os termos e condições você deseja modificar e, em seguida, selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="98166-151">On the Intune blade, choose **Device enrollment**,  choose **Terms and Conditions**, select the terms and conditions you want to modify, and then select **Properties**.</span></span>

4. <span data-ttu-id="98166-152">Na folha **Propriedades**, selecione **Termos e Condições** e, em seguida, modifique o **Título**, o **Resumo de Termos** e os **Termos e Condições** conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="98166-152">On the **Properties** blade, select **Terms and Conditions** and then modify the **Title**, **Summary of Terms**, and **Terms and Conditions** as needed.</span></span> <span data-ttu-id="98166-153">Se as alterações feitas obrigarem os usuários a aceitar novamente os novos termos, clique em **Exigir que os usuários aceitem novamente e aumentar o número de versão para**</span><span class="sxs-lookup"><span data-stu-id="98166-153">If the changes you made make it necessary for users to reaccept the new terms, click **Require users to re-accept, and increment the version number to**</span></span>

4.  <span data-ttu-id="98166-154">Selecione **OK** e **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="98166-154">Select **OK** and then select **Save**.</span></span>

<span data-ttu-id="98166-155">Os usuários precisam aceitar os termos e condições atualizados apenas uma vez.</span><span class="sxs-lookup"><span data-stu-id="98166-155">Users only have to accept updated terms and conditions once.</span></span> <span data-ttu-id="98166-156">Usuários com vários dispositivos não precisam aceitar os termos e condições em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="98166-156">Users with multiple devices don't have to accept terms and conditions on each device.</span></span>
