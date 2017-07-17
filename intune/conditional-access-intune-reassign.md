---
title: "Migrar políticas de acesso condicional no Portal Clássico do Intune para o novo Portal do Azure."
titleSuffix: Intune on Azure
description: "Migrar políticas de acesso condicional no Portal Clássico do Intune para o novo Portal do Azure."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2450a878424d8c992a43e8028ba59b7136e1d530
ms.sourcegitcommit: fd5b7aa26446d2fa92c21638cb29371e43fe169f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2017
---
# <span data-ttu-id="7a20e-103">Reatribuir políticas de acesso condicional no Portal Clássico do Intune para o novo Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="7a20e-103">Reassign conditional access policies from Intune classic portal to the new Azure portal</span></span>
<a id="reassign-conditional-access-policies-from-intune-classic-portal-to-the-new-azure-portal" class="xliff"></a>

<span data-ttu-id="7a20e-104">A partir do novo Portal do Azure, o acesso condicional dará suporte para várias políticas por aplicativo juntamente com maior capacidade de personalização.</span><span class="sxs-lookup"><span data-stu-id="7a20e-104">Starting in the new Azure portal, conditional access offers support for multiple policies per application along with more customizability.</span></span>

## <span data-ttu-id="7a20e-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7a20e-105">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="7a20e-106">Se você estiver pronto para mover para o novo Portal do Azure, siga as etapas abaixo para reatribuir as políticas de acesso condicional criadas anteriormente no portal clássico do Intune:</span><span class="sxs-lookup"><span data-stu-id="7a20e-106">If you’re ready to move to the new Azure portal, you can follow the steps below to reassign the conditional access policies previously created either in the Intune classic portal:</span></span>

- <span data-ttu-id="7a20e-107">Colete as políticas de acesso condicional criadas anteriormente no portal clássico do Intune para saber quais configurações você precisará reatribuir mais tarde.</span><span class="sxs-lookup"><span data-stu-id="7a20e-107">Gather the conditional access policies previously created in the Intune classic portal so you know what settings you need to reassign later.</span></span>

- <span data-ttu-id="7a20e-108">Siga as etapas deste tópico para recriar essas políticas no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-108">Follow the steps in this topic to recreate these policies in the new Azure portal.</span></span>

- <span data-ttu-id="7a20e-109">Desabilite as políticas condicionais no console clássico do Intune depois de verificar se as novas políticas estão funcionando conforme o esperado no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-109">Disable the conditional policies in the Intune classic console once you have verified that the new policies are working as expected in the new Azure portal.</span></span>
<br /><br />
    - <span data-ttu-id="7a20e-110">**Antes de desabilitar** as políticas de acesso condicional no portal clássico do Intune, planeje como você moverá os usuários para a nova política.</span><span class="sxs-lookup"><span data-stu-id="7a20e-110">**Before you disable** the conditional access policies in the Intune classic portal, plan how you'll move users over to the new policy.</span></span> <span data-ttu-id="7a20e-111">Há duas abordagens:</span><span class="sxs-lookup"><span data-stu-id="7a20e-111">There are two approaches:</span></span>
<br /><br />
        - <span data-ttu-id="7a20e-112">**Usar o mesmo grupo de inclusão para aplicar as políticas criadas no novo Portal do Azure e criar um novo grupo de isenção para ser usado com as políticas aplicadas pelo portal clássico do Intune**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-112">**Use the same inclusion group to apply policies created in the new Azure portal, and create a new exemption group to use with the policies applied by the Intune classic portal**.</span></span>
            - <span data-ttu-id="7a20e-113">Mova gradualmente alguns usuários para o grupo de isolamento especificado no portal clássico.</span><span class="sxs-lookup"><span data-stu-id="7a20e-113">Gradually move some users into the exemption group specified in the classic portal.</span></span>  <span data-ttu-id="7a20e-114">Isso impede que as políticas direcionadas pelo portal clássico do Intune sejam aplicadas.</span><span class="sxs-lookup"><span data-stu-id="7a20e-114">This prevents the policies targeted by the Intune classic portal to be applied.</span></span> <span data-ttu-id="7a20e-115">As políticas criadas e direcionadas para o mesmo grupo de usuários no novo Portal do Azure são aplicadas além daquelas aplicadas no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="7a20e-115">The policies created and targeted to the same user group in the new Azure portal are applied in addition to the ones applied in the Intune classic portal.</span></span> 
<br /><br />
        - <span data-ttu-id="7a20e-116">**Crie um novo grupo para direcionar as políticas de acesso condicional no novo Portal do Azure**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-116">**Create a new group to target the conditional access policies in the new Azure portal**.</span></span> <span data-ttu-id="7a20e-117">Se você escolher essa abordagem, precisará fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7a20e-117">If you choose this approach, you need to do the following:</span></span>
            - <span data-ttu-id="7a20e-118">Remova gradualmente os usuários dos grupos de segurança que têm políticas de acesso condicional direcionadas para o portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="7a20e-118">Gradually remove users from the security groups that have conditional access policies targeted to in the Intune classic portal.</span></span>
            - <span data-ttu-id="7a20e-119">Depois de confirmar que a nova política está funcionando para esses usuários, você poderá desabilitar a política no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="7a20e-119">Once you have confirmed the new policy is working for those users, you can disable the policy in the Intune classic portal.</span></span> 
<br /><br />
- <span data-ttu-id="7a20e-120">Se as configurações de política de acesso condicional forem configuradas para usar o EAS (Exchange Active Sync) no portal clássico do Intune, consulte as [instruções neste tópico](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) para **reatribuir as configurações de política de acesso condicional EAS no novo Portal do Azure**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-120">If you have your conditional access policy settings configured to use Exchange Active Sync (EAS) in the Intune classic portal, see [instructions in this topic](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) to **reassign EAS conditional access policy settings in the new Azure portal**.</span></span>

### <span data-ttu-id="7a20e-121">Verificar as políticas de acesso condicional com base em dispositivo no portal clássico do Intune</span><span class="sxs-lookup"><span data-stu-id="7a20e-121">To verify your device-based conditional access policies in the Intune classic portal</span></span>
<a id="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal" class="xliff"></a>

1.  <span data-ttu-id="7a20e-122">Acesse o [Portal Clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="7a20e-122">Go to [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.</span></span>

2.  <span data-ttu-id="7a20e-123">Escolha **Política** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="7a20e-123">Choose **Policy** from the left menu.</span></span>

3.  <span data-ttu-id="7a20e-124">Escolha **Acesso condicional** e selecione o serviço de nuvem da Microsoft (Exchange Online, SharePoint Online, etc.) para o qual você criou uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="7a20e-124">Choose **Conditional access**, then select the Microsoft cloud service (Exchange Online, SharePoint Online, etc.) you created a conditional access policy for.</span></span>

4.  <span data-ttu-id="7a20e-125">Anote as configurações de acesso condicional e use essas notas como referência para criar as mesmas políticas de acesso condicional no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-125">Take notes of your conditional access settings and use these notes as reference to create the same conditional access policies in the new Azure portal.</span></span>

### <span data-ttu-id="7a20e-126">Políticas de acesso condicional baseado em aplicativo e dispositivo funcionando juntas</span><span class="sxs-lookup"><span data-stu-id="7a20e-126">App and device-based conditional access policies working together</span></span>
<a id="app-and-device-based-conditional-access-policies-working-together" class="xliff"></a>

<span data-ttu-id="7a20e-127">A folha **Proteção de Aplicativo do Intune** no novo Portal do Azure permite que os administradores definam as regras condicionais baseado em aplicativo para que somente os aplicativos que dão suporte às políticas de proteção de aplicativo do Intune tenham permissão de acesso aos recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="7a20e-127">The **Intune App Protection** blade in the new Azure portal enables admins to set app-based conditional rules so that only apps that support the Intune app protection policies are allowed access to corporate resources.</span></span> <span data-ttu-id="7a20e-128">Você pode optar por sobrepor essas políticas de acesso condicional baseado em aplicativo usando políticas de acesso condicional baseado em dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7a20e-128">You can choose to overlap these app-based conditional access policies using device-based conditional access policies.</span></span> <span data-ttu-id="7a20e-129">Dependendo se você deseja combinar as políticas condicionais baseadas em aplicativo e em dispositivo (AND lógico) ou fornecer uma opção (OR lógico).</span><span class="sxs-lookup"><span data-stu-id="7a20e-129">Depending on whether you want to combine the device-based and app-based conditional policies (logical AND) or provide an option (logical OR).</span></span> <span data-ttu-id="7a20e-130">Se seus requisitos de política de acesso condicional são:</span><span class="sxs-lookup"><span data-stu-id="7a20e-130">If your conditional access policy requirements are:</span></span>

- <span data-ttu-id="7a20e-131">Exigir dispositivo em conformidade **AND** usar o aplicativo aprovado.</span><span class="sxs-lookup"><span data-stu-id="7a20e-131">Require compliant device **AND** use the approved app.</span></span>
    - <span data-ttu-id="7a20e-132">Você deve definir sua política de acesso condicional usando a [folha de acesso condicional do Azure AD](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e a [folha de Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span><span class="sxs-lookup"><span data-stu-id="7a20e-132">You should set your conditional access policy using the [Azure AD conditional access blade](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span></span>
<br /><br />
- <span data-ttu-id="7a20e-133">Exigir dispositivo em conformidade **OR** usar o aplicativo aprovado.</span><span class="sxs-lookup"><span data-stu-id="7a20e-133">Require compliant device **OR** use the approved app.</span></span>
    - <span data-ttu-id="7a20e-134">Você deve definir sua política de acesso condicional usando as folhas de [Portal Clássico do Intune](https://manage.microsoft.com) e [Proteção de Aplicativo do Intune](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span><span class="sxs-lookup"><span data-stu-id="7a20e-134">You should set your conditional access policy using the [Intune classic portal](https://manage.microsoft.com) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span></span>

> [!TIP] 
> <span data-ttu-id="7a20e-135">Este tópico fornece capturas de tela que comparam a experiência do usuário no portal clássico do Intune com o novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-135">This topic provides screenshots comparing the user experience in both Intune classic portal and the new Azure portal.</span></span>

## <span data-ttu-id="7a20e-136">Reatribuir as políticas de acesso condicional baseado em dispositivo do Intune</span><span class="sxs-lookup"><span data-stu-id="7a20e-136">To re-assign Intune device-based conditional access policies</span></span>
<a id="to-re-assign-intune-device-based-conditional-access-policies" class="xliff"></a>

1. <span data-ttu-id="7a20e-137">Vá para [Acesso condicional no novo Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="7a20e-137">Go to [Conditional access in the new Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and sign in with your credentials.</span></span>

2. <span data-ttu-id="7a20e-138">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-138">Choose **New policy**.</span></span>

3. <span data-ttu-id="7a20e-139">Forneça um nome para a política.</span><span class="sxs-lookup"><span data-stu-id="7a20e-139">Provide a name for the policy.</span></span>

4. <span data-ttu-id="7a20e-140">Escolha **Usuários e grupos** na seção **Atribuições** direcionada para a nova política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="7a20e-140">Choose **Users and groups** under the **Assignments** section to target the new conditional access policy.</span></span>
    
    ![Comparação da interface do usuário do grupo de usuários entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="7a20e-142">Se todos os usuários forem selecionados no Portal Clássico do Intune, inclua Todos os Usuários.</span><span class="sxs-lookup"><span data-stu-id="7a20e-142">If you have all users selected in the Intune classic portal, include All users.</span></span> <span data-ttu-id="7a20e-143">O mesmo se aplica a grupos. Se você tiver grupos selecionados, será necessário escolher **selecionar usuários e grupos individuais** para incluir esses grupos.</span><span class="sxs-lookup"><span data-stu-id="7a20e-143">The same applies for groups, if you have groups selected, you need to choose **select individual users and groups** to include those groups.</span></span> <span data-ttu-id="7a20e-144">Além disso, se você tiver escolhido a opção **Isentar grupos** no Portal Clássico do Intune, será necessário excluir os grupos selecionados no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-144">Additionally, if you’ve have chosen the **Exempt groups** option in the Intune classic portal, you need to exclude those select groups in the new Azure portal.</span></span>

5. <span data-ttu-id="7a20e-145">Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-145">After you chose your group, click **Select**, then **Done**.</span></span>

6. <span data-ttu-id="7a20e-146">Escolha **Aplicativos de nuvem** na seção **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-146">Choose **Cloud apps** under the **Assignments** section.</span></span>

7. <span data-ttu-id="7a20e-147">Na folha **Aplicativos de nuvem**, escolha **Selecionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-147">On the **Cloud apps** blade, choose **Select apps**.</span></span>

8. <span data-ttu-id="7a20e-148">Escolha o aplicativo para o qual você deseja aplicar a nova política de acesso condicional e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-148">Choose the app you want to apply the new conditional access policy to, click **Select**.</span></span>

9. <span data-ttu-id="7a20e-149">Clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-149">Click **Done**.</span></span>

    ![Comparação da interface do usuário do aplicativo de nuvem entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-3.png)

    > [!TIP] 
    > <span data-ttu-id="7a20e-151">Se você tiver vários aplicativos com a mesma política, considere consolidá-las em uma única política no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-151">If you have multiple apps with the same policy, you can consider consolidating them into a single policy in the new Azure portal.</span></span>

10. <span data-ttu-id="7a20e-152">Escolha **Condições** na seção **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-152">Choose **Conditions** under the **Assignments** section.</span></span>

11. <span data-ttu-id="7a20e-153">Na folha **Condições**, escolha **Plataformas de Dispositivo** e escolha as plataformas de dispositivo aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="7a20e-153">On the **Conditions** blade, choose **Device platforms**, then choose the applicable device platforms.</span></span>

12. <span data-ttu-id="7a20e-154">Quando você terminar de escolher as plataformas de dispositivo, clique em **Concluído** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="7a20e-154">Once you finished choosing the device platforms, click **Done** twice.</span></span>

    ![Comparação da interface do usuário da plataforma de dispositivos entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-4.png)

    > [!TIP] 
    > <span data-ttu-id="7a20e-156">Se você tiver escolhido plataformas individuais no portal clássico do Intune, escolha as plataformas individuais no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-156">If you have chosen individual platforms in the Intune classic portal, choose the individual platforms in the new Azure portal.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="7a20e-157">Você pode especificar as opções de ingresso no domínio ou conformidade para o Windows posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7a20e-157">You can specify the domain join or compliant options for Windows later.</span></span>

13. <span data-ttu-id="7a20e-158">Escolha **Condições** na seção **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-158">Choose **Conditions** under the **Assignments** section.</span></span>

14. <span data-ttu-id="7a20e-159">Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável.</span><span class="sxs-lookup"><span data-stu-id="7a20e-159">On the **Conditions** blade, choose **Client apps**, then choose the applicable client app.</span></span>

15. <span data-ttu-id="7a20e-160">Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="7a20e-160">Once you finished choosing the client app, click **Done** twice.</span></span>

    ![Comparação da interface do usuário de aplicativos cliente entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-6.png)

16. <span data-ttu-id="7a20e-162">Se você tiver escolhido as configurações do navegador no portal clássico do Intune, selecione ambos **Navegador** e **Aplicativos móveis e clientes de desktop** no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-162">If you have chosen the browser settings in the Intune classic portal, select both **Browser** and **Mobile apps and desktop clients** in the new Azure portal.</span></span> <span data-ttu-id="7a20e-163">Caso você não tenha escolhido as configurações do navegador no portal clássico do Intune, escolha apenas **Aplicativos móveis e clientes de área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-163">In case you have not chosen the browser settings in the Intune classic portal choose **Mobile apps and desktop clients** only.</span></span> 

17. <span data-ttu-id="7a20e-164">Escolha **Conceder** na seção **Controles de acesso**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-164">Choose **Grant** under the **Access controls** section.</span></span>

18. <span data-ttu-id="7a20e-165">Escolha **Exigir que o dispositivo esteja marcado como em conformidade** em **Conceder controles de acesso** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-165">Choose **Require device to be marked as compliant** under **Grant Access Controls,** then click **Select**.</span></span>

19. <span data-ttu-id="7a20e-166">Se você tiver uma política para exigir que os dispositivos sejam ingressados no Windows e também permitir dispositivos registrado no Intune e em conformidade com o Windows, escolha **Exigir dispositivo ingressado no domínio** e **Exigir que o dispositivo esteja marcado como em conformidade** junto com **Exigir um dos controles selecionados**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-166">If you have a policy to require domain joined Windows devices, and you also allow Intune-enrolled and compliant Windows devices, choose **Require domain joined device** and **Require device to be marked as compliant** along with **Require one of the selected controls**.</span></span>

20. <span data-ttu-id="7a20e-167">Se você não permitir que dispositivos registrados no Intune e em conformidade com o Windows, isente a política do Windows da política atual e crie um política separada com as **Plataformas de dispositivo** definido como **Windows**, inclua as outras condições conforme definido acima e escolha **Exigir dispositivo ingressado no domínio** em **Conceder controles de acesso**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-167">If you do not allow Intune enrolled and compliant Windows devices, exempt the Windows policy from the current policy and then create a separate policy with **Device platform**s set to **Windows ,** include the other conditions as set per above, and choose **Require domain joined device** under **Grant Access Controls**.</span></span>

21. <span data-ttu-id="7a20e-168">Ative o botão de alternância **Habilitar política** na folha da política de acesso condicional **Novo** e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-168">Turn on the **Enable policy** toggle on the **New** conditional access policy blade, then click **Create**.</span></span>

    ![Habilitar a comparação da interface do usuário da política de AC entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-11.png)

## <span data-ttu-id="7a20e-170">Reatribuir as políticas de acesso condicional baseado em dispositivo do Intune para clientes EAS</span><span class="sxs-lookup"><span data-stu-id="7a20e-170">To reassign Intune device-based conditional access policies for EAS clients</span></span>
<a id="to-reassign-intune-device-based-conditional-access-policies-for-eas-clients" class="xliff"></a>

<span data-ttu-id="7a20e-171">Se você tiver definido as configurações do EAS (Exchange Active Sync) como parte de uma política do Exchange Online no portal clássico do Intune, será necessário criar uma segunda política de acesso condicional no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-171">If you have configured Exchange Active Sync (EAS) settings as part of an Exchange Online policy in the Intune classic portal, you need to create a second conditional access policy in the new Azure portal.</span></span>

1. <span data-ttu-id="7a20e-172">Vá para [Acesso condicional no novo Portal do Azure](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="7a20e-172">Go to [Conditional access in the new Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and sign in with your credentials.</span></span>

2. <span data-ttu-id="7a20e-173">Escolha **Nova política**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-173">Choose **New policy**.</span></span>

3. <span data-ttu-id="7a20e-174">Forneça um nome para a política.</span><span class="sxs-lookup"><span data-stu-id="7a20e-174">Provide a name for the policy.</span></span>

4. <span data-ttu-id="7a20e-175">Escolha **Usuários e grupos** na seção **Atribuições** direcionada para a nova política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="7a20e-175">Choose **Users and groups** under the **Assignments** section to target the new conditional access policy.</span></span>

    ![Comparação da interface do usuário do grupo de usuários entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="7a20e-177">Se todos os usuários forem selecionados no Portal Clássico do Intune, inclua Todos os Usuários.</span><span class="sxs-lookup"><span data-stu-id="7a20e-177">If you have all users selected in the Intune classic portal, include All users.</span></span> <span data-ttu-id="7a20e-178">O mesmo se aplica a grupos. Se você tiver grupos selecionados, será necessário escolher **selecionar usuários e grupos individuais** para incluir esses grupos.</span><span class="sxs-lookup"><span data-stu-id="7a20e-178">The same applies for groups, If you have groups selected, you need to choose **select individual users and groups** to include those groups.</span></span> <span data-ttu-id="7a20e-179">Além disso, se você tiver escolhido a opção **Isentar grupos** no Portal Clássico do Intune, será necessário excluir os grupos selecionados no novo Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="7a20e-179">Additionally, if you’ve have chosen the **Exempt groups** option in the Intune classic portal, you need to exclude those select groups in the new Azure portal.</span></span>

5. <span data-ttu-id="7a20e-180">Depois de escolher o grupo, clique em **Selecionar** e **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-180">After you chose your group, click **Select**, then **Done**.</span></span>

6. <span data-ttu-id="7a20e-181">Escolha **Aplicativos de nuvem** na seção **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-181">Choose **Cloud apps** under the **Assignments** section.</span></span>

7. <span data-ttu-id="7a20e-182">Na folha **Aplicativos de nuvem**, clique em **Aplicativos selecionados**, escolha **Exchange Online**, clique em **Selecionar** e em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-182">On the **Cloud apps** blade, click **Selected apps**, choose **Exchange Online**, click **Select**, then click **Done**.</span></span>

    ![Comparação da interface do usuário de aplicativos de nuvem entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="7a20e-184">Políticas de acesso condicional para clientes EAS não podem incluir nenhum outro aplicativo de nuvem.</span><span class="sxs-lookup"><span data-stu-id="7a20e-184">Conditional Access policies for EAS clients cannot include any other cloud app.</span></span>

8. <span data-ttu-id="7a20e-185">Na folha **Condições**, escolha **Aplicativos cliente** e escolha o aplicativo cliente aplicável.</span><span class="sxs-lookup"><span data-stu-id="7a20e-185">On the **Conditions** blade, choose **Client apps**, then choose the applicable client app.</span></span> <span data-ttu-id="7a20e-186">Se você tiver optado por bloquear os clientes sem suporte no Intune, use a opção **Aplicar política somente a plataformas com suporte**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-186">If you have chosen to block clients that aren’t supported by Intune, use the **Apply policy only to supported platforms** option.</span></span>

    ![Comparação da interface do usuário de aplicativos cliente entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-15.png)

9. <span data-ttu-id="7a20e-188">Quando você terminar de escolher o aplicativo cliente, clique em **Concluído** duas vezes.</span><span class="sxs-lookup"><span data-stu-id="7a20e-188">Once you finished choosing the client app, click **Done** twice.</span></span>

10. <span data-ttu-id="7a20e-189">Escolha **Conceder** na seção **Controles de acesso**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-189">Choose **Grant** under the **Access controls** section.</span></span>

11. <span data-ttu-id="7a20e-190">Escolha **Exigir que o dispositivo esteja marcado como em conformidade** em **Conceder controles de acesso** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-190">Choose **Require device to be marked as compliant** under **Grant Access Controls,** then click **Select**.</span></span>

    ![Comparação da interface do usuário de Conceder acesso entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-16.png)

12. <span data-ttu-id="7a20e-192">Ative o botão de alternância **Habilitar política** na folha da política de acesso condicional **Novo** e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-192">Turn on the **Enable policy** toggle on the **New** conditional access policy blade, then click **Create**.</span></span>

    ![Habilitar a comparação da interface do usuário da política de AC entre o Intune clássico e o novo Portal do Azure](./media/reassign-ca-17.png)

## <span data-ttu-id="7a20e-194">Desabilitar as políticas de acesso condicional no Portal Clássico do Intune</span><span class="sxs-lookup"><span data-stu-id="7a20e-194">Disable conditional access policies in the Intune classic portal</span></span>
<a id="disable-conditional-access-policies-in-the-intune-classic-portal" class="xliff"></a>
### <span data-ttu-id="7a20e-195">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="7a20e-195">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

<span data-ttu-id="7a20e-196">Depois que tiver reatribuído suas políticas de acesso condicional no novo Portal do Azure, é importante desabilitar gradualmente as políticas de acesso condicional criadas anteriormente no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="7a20e-196">Once you reassigned your conditional access policies in the new Azure portal, it's important to gradually disable the conditional access policies previously created in the Intune classic portal.</span></span> <span data-ttu-id="7a20e-197">Além disso, pode ser necessário usar o mesmo grupo de segurança para aplicar as políticas de acesso condicional criadas no novo Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="7a20e-197">Additionally, you might need to use the same security group to apply the conditional access policies created in the new Azure portal</span></span>

- <span data-ttu-id="7a20e-198">Consulte a seção [antes de começar](#before-you-begin) no início deste tópico antes de desabilitar as políticas de acesso condicional no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="7a20e-198">See the [before you begin](#before-you-begin) section at the beginning of this topic before disabling your conditional access policies in the Intune classic portal.</span></span>

### <span data-ttu-id="7a20e-199">Desabilitar as políticas de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="7a20e-199">To disable the conditional access policies</span></span>
<a id="to-disable-the-conditional-access-policies" class="xliff"></a>

1.  <span data-ttu-id="7a20e-200">Acesse o [Portal Clássico do Intune](https://manage.microsoft.com) e entre com suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="7a20e-200">Go to [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.</span></span>

2.  <span data-ttu-id="7a20e-201">Escolha **Política** no menu à esquerda.</span><span class="sxs-lookup"><span data-stu-id="7a20e-201">Choose **Policy** from the left menu.</span></span>

3.  <span data-ttu-id="7a20e-202">Escolha **Acesso condicional** e selecione o serviço de nuvem da Microsoft (Exchange Online, SharePoint Online, etc.) para o qual você criou uma política de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="7a20e-202">Choose **Conditional access**, then select the Microsoft cloud service (Exchange Online, SharePoint Online, etc.) that you created a conditional access policy for.</span></span>

4.  <span data-ttu-id="7a20e-203">Desmarque a opção **Habilitar política de acesso condicional** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7a20e-203">Uncheck the option **Enable conditional access policy**, then click **Save**.</span></span>

    ![Desabilitar as políticas de acesso condicional no Portal Clássico do Intune](./media/reassign-ca-18.png)

## <span data-ttu-id="7a20e-205">Consulte também</span><span class="sxs-lookup"><span data-stu-id="7a20e-205">See also</span></span>
<a id="see-also" class="xliff"></a>

- [<span data-ttu-id="7a20e-206">Maneiras comuns de usar o acesso condicional com o Intune</span><span class="sxs-lookup"><span data-stu-id="7a20e-206">Common ways to use conditional access with Intune</span></span>](conditional-access-intune-common-ways-use.md)
- [<span data-ttu-id="7a20e-207">Acesso condicional baseado no aplicativo com o Intune</span><span class="sxs-lookup"><span data-stu-id="7a20e-207">App-based conditional access with Intune</span></span>](app-based-conditional-access-intune.md)
- [<span data-ttu-id="7a20e-208">Acesso condicional no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7a20e-208">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)