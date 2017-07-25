---
title: "Criar e implantar políticas de proteção do aplicativo"
titleSuffix: Intune on Azure
description: "Saiba como as políticas de Proteção de Aplicativo do Intune podem ajudar a proteger os dados da empresa usados pelos aplicativos gerenciados."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 56a19bc4d970f230f719af9369dada45ffb65e76
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1193f-103">Como criar e atribuir as políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1193f-103">How to create and assign app protection policies</span></span>
<a id="how-to-create-and-assign-app-protection-policies" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <span data-ttu-id="1193f-104">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="1193f-104">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="1193f-105">Se você estiver procurando instruções no console clássico do Intune, consulte [Como criar políticas de proteção de aplicativo](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="1193f-105">If you're looking for instructions in the Intune classic console, see [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).</span></span>

<span data-ttu-id="1193f-106">Políticas de proteção de aplicativo podem ser aplicadas a aplicativos em execução em dispositivos que podem ou não ser gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="1193f-106">App protection policies can be applied to apps running on devices that may or may not be managed by Intune.</span></span> <span data-ttu-id="1193f-107">Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários com suporte nas políticas de proteção de aplicativo do Intune, consulte [O que são as políticas de proteção de aplicativo do Microsoft Intune](app-protection-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1193f-107">For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [What is Microsoft Intune app protection policies](app-protection-policy.md).</span></span>

<span data-ttu-id="1193f-108">Se você estiver procurando uma lista de aplicativos com suporte no MAM, consulte [Lista de aplicativos do MAM](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span><span class="sxs-lookup"><span data-stu-id="1193f-108">If you're looking for a list of MAM supported apps, see [MAM apps list](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span></span>

##  <span data-ttu-id="1193f-109">Criar uma política de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1193f-109">Create an app protection policy</span></span>
<a id="create-an-app-protection-policy" class="xliff"></a>
1.  <span data-ttu-id="1193f-110">Na carga de trabalho **Aplicativos móveis**, escolha **Gerenciar** > **Políticas de proteção de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="1193f-110">In the **Mobile apps** workload, choose **Manage** > **App protection policies**.</span></span>

2.  <span data-ttu-id="1193f-111">Isso abre a folha **Políticas de proteção de aplicativo**, em que você criará novas políticas e editará as políticas existentes.</span><span class="sxs-lookup"><span data-stu-id="1193f-111">This opens the **App protection policies** blade, where you'll create new policies and edit existing policies.</span></span> <span data-ttu-id="1193f-112">Escolha **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="1193f-112">Choose **Add a policy**.</span></span>

  ![Captura de tela da folha Adicionar uma política](./media/app-protection-add-policy.png)

3.  <span data-ttu-id="1193f-114">Digite um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para criar uma política para iOS ou Android.</span><span class="sxs-lookup"><span data-stu-id="1193f-114">Type a name for the policy, add a brief description, and select the platform type to create a policy for iOS or Android.</span></span> <span data-ttu-id="1193f-115">Você pode criar mais de uma política para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="1193f-115">You can create more than one policy for each platform.</span></span>

4.  <span data-ttu-id="1193f-116">Escolha **Aplicativos** para abrir a **folha Aplicativos**, em que uma lista de aplicativos disponíveis é exibida.</span><span class="sxs-lookup"><span data-stu-id="1193f-116">Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed.</span></span> <span data-ttu-id="1193f-117">Selecione um ou mais aplicativos da lista que deseja associar à política que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="1193f-117">Select one or more apps from the list that you want to associate with the policy that you are creating.</span></span> <span data-ttu-id="1193f-118">Depois de selecionar os aplicativos, escolha **Selecionar** na parte inferior da folha **Aplicativos** para salvar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="1193f-118">Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1193f-119">Você deve selecionar pelo menos um aplicativo para criar uma política.</span><span class="sxs-lookup"><span data-stu-id="1193f-119">You must select at least one app to create a policy.</span></span>

5.  <span data-ttu-id="1193f-120">Na folha **Adicionar uma política**, escolha **Definir as configurações necessárias** para abrir a folha de configurações da política.</span><span class="sxs-lookup"><span data-stu-id="1193f-120">On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.</span></span>

    <span data-ttu-id="1193f-121">Há duas categorias de configurações de política, **Realocação dos dados** e **Acesso**.</span><span class="sxs-lookup"><span data-stu-id="1193f-121">There are two categories of policy settings, **Data relocation** and **Access**.</span></span>  <span data-ttu-id="1193f-122">Políticas de realocação de dados aplicam-se à movimentação de dados dentro e fora dos aplicativos, enquanto as políticas de acesso determinam como o usuário final acessa os aplicativos em um contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1193f-122">Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end user accesses the apps in a work context.</span></span>
    <span data-ttu-id="1193f-123">As configurações de política têm valores padrão para que você possa começar mais facilmente.</span><span class="sxs-lookup"><span data-stu-id="1193f-123">To get you started, the policy settings have default values.</span></span> <span data-ttu-id="1193f-124">Não é necessário fazer alterações se os valores padrão atendem às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="1193f-124">You do not have to make any changes if the default values meet your requirements.</span></span>

    > [!TIP]
    > <span data-ttu-id="1193f-125">Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo.</span><span class="sxs-lookup"><span data-stu-id="1193f-125">These policy settings are enforced only when using apps in the work context.</span></span>  <span data-ttu-id="1193f-126">Quando o usuário final usa o aplicativo para executar uma tarefa pessoal, ele não é afetado por essas políticas.</span><span class="sxs-lookup"><span data-stu-id="1193f-126">When the end user uses the app to do a personal task, they will not be affected by these policies.</span></span>



6.  <span data-ttu-id="1193f-127">Escolha **OK** para salvar esta configuração.</span><span class="sxs-lookup"><span data-stu-id="1193f-127">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="1193f-128">Agora você retornou à folha **Adicionar uma política** .</span><span class="sxs-lookup"><span data-stu-id="1193f-128">You are now back in the **Add a policy** blade.</span></span> <span data-ttu-id="1193f-129">Escolha **Criar** para criar a política e salvar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="1193f-129">Choose **Create** to create the policy and save your settings.</span></span>


<span data-ttu-id="1193f-130">Ao terminar de criar uma política conforme descrito no procedimento anterior, ela não é implantada para nenhum usuários.</span><span class="sxs-lookup"><span data-stu-id="1193f-130">When you finish creating a policy as described in the previous procedure, it is not deployed to any users.</span></span> <span data-ttu-id="1193f-131">Para implantar uma política, consulte a seção a seguir, "Implantar uma política para usuários".</span><span class="sxs-lookup"><span data-stu-id="1193f-131">To deploy a policy, see the following section, "Deploy a policy to users."</span></span>

## <span data-ttu-id="1193f-132">Implantar uma política para os usuários</span><span class="sxs-lookup"><span data-stu-id="1193f-132">Deploy a policy to users</span></span>
<a id="deploy-a-policy-to-users" class="xliff"></a>

1.  <span data-ttu-id="1193f-133">Na folha **Política**, escolha **Grupos de usuários**, o que abre a folha **Grupos de usuários**.</span><span class="sxs-lookup"><span data-stu-id="1193f-133">In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade.</span></span> <span data-ttu-id="1193f-134">Escolha **Adicionar grupo de usuários** na folha **Grupos de usuários** para abrir a folha **Adicionar grupo de usuários**.</span><span class="sxs-lookup"><span data-stu-id="1193f-134">Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.</span></span>

  ![Captura de tela da folha Grupos de usuários com a opção de menu Adicionar grupo de usuários realçada](./media/app-protection-policy-add-users.png)

2.  <span data-ttu-id="1193f-136">Uma lista de grupos de usuários é exibida na folha **Adicionar grupo de usuários** .</span><span class="sxs-lookup"><span data-stu-id="1193f-136">A list of user groups is displayed on the **Add user group** blade.</span></span> <span data-ttu-id="1193f-137">Esta é uma lista de todos os grupos de segurança no seu **Active Directory do Azure**.</span><span class="sxs-lookup"><span data-stu-id="1193f-137">This is a list of all the security groups in your **Azure Active Directory**.</span></span> <span data-ttu-id="1193f-138">Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="1193f-138">Select the user groups you want this policy to apply to, and then choose **Select**.</span></span> <span data-ttu-id="1193f-139">A escolha de **Selecionar** implanta a política para os usuários.</span><span class="sxs-lookup"><span data-stu-id="1193f-139">Choosing **Select**, deploys the policy to users.</span></span>
  <span data-ttu-id="1193f-140">![Captura de tela da folha Adicionar grupo de usuários adicionar mostrando a lista de usuários do Azure Active Directory](./media/azure-ad-user-group-list.png)</span><span class="sxs-lookup"><span data-stu-id="1193f-140">![Screenshot of the Add user group blade showing the list of Azure Active Directory users](./media/azure-ad-user-group-list.png)</span></span>

<span data-ttu-id="1193f-141">Agora você criou uma política e a implantou para os usuários.</span><span class="sxs-lookup"><span data-stu-id="1193f-141">You have now created a policy and deployed it to users.</span></span>

<span data-ttu-id="1193f-142">Somente usuários com licenças do Microsoft Intune atribuídas a eles serão afetados pela política.</span><span class="sxs-lookup"><span data-stu-id="1193f-142">Only users with Microsoft Intune licenses assigned to them are affected by the policy.</span></span> <span data-ttu-id="1193f-143">Os usuários que estão no grupo de segurança que você selecionou e que não têm uma licença do Microsoft Intune atribuída a eles não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="1193f-143">Users who are in the security group that you selected who don’t have a Microsoft Intune license assigned to them are not affected.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="1193f-144">Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos Android e iOS, a política só será aplicada aos usuários diretamente no grupo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="1193f-144">If you are using Intune with Configuration Manager to manage your iOS and Android devices, the policy is only applied to the users directly in the group that you selected.</span></span> <span data-ttu-id="1193f-145">Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="1193f-145">Members of child groups nested within the group you selected are not affected.</span></span>

<span data-ttu-id="1193f-146">Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play.</span><span class="sxs-lookup"><span data-stu-id="1193f-146">End users can download the apps from the App store or Google Play.</span></span> <span data-ttu-id="1193f-147">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="1193f-147">For more information, see:</span></span>
* [<span data-ttu-id="1193f-148">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1193f-148">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="1193f-149">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1193f-149">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)

##  <span data-ttu-id="1193f-150">Alterar políticas existentes</span><span class="sxs-lookup"><span data-stu-id="1193f-150">Change existing policies</span></span>
<a id="change-existing-policies" class="xliff"></a>
<span data-ttu-id="1193f-151">Você pode editar uma política existente e aplicá-la aos usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="1193f-151">You can edit an existing policy and apply it to the targeted users.</span></span> <span data-ttu-id="1193f-152">No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="1193f-152">However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.</span></span>

<span data-ttu-id="1193f-153">Para ver o efeito das alterações imediatamente, o usuário final precisará sair do aplicativo e entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="1193f-153">To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.</span></span>

### <span data-ttu-id="1193f-154">Para alterar a lista de aplicativos associados à política</span><span class="sxs-lookup"><span data-stu-id="1193f-154">To change the list of apps associated with the policy</span></span>
<a id="to-change-the-list-of-apps-associated-with-the-policy" class="xliff"></a>

1.  <span data-ttu-id="1193f-155">Na folha **Política de aplicativos**, escolha a política que quer alterar.</span><span class="sxs-lookup"><span data-stu-id="1193f-155">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="1193f-156">Isso abrirá uma folha específica para a política que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="1193f-156">This opens a blade specific to the policy you just selected.</span></span>

2.  <span data-ttu-id="1193f-157">Na folha de política, escolha **Aplicativos de destino** para abrir a lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="1193f-157">In the policy blade, choose **Targeted apps** to open the list of apps.</span></span>

3.  <span data-ttu-id="1193f-158">Remova ou adicione aplicativos da lista e escolha o ícone **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="1193f-158">Remove or add apps from the list and choose the **Save** icon to save your changes.</span></span>

### <span data-ttu-id="1193f-159">Para alterar a lista de grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="1193f-159">To change the list of user groups</span></span>
<a id="to-change-the-list-of-user-groups" class="xliff"></a>

1.  <span data-ttu-id="1193f-160">Na folha **Política de aplicativos**, escolha a política que quer alterar.</span><span class="sxs-lookup"><span data-stu-id="1193f-160">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="1193f-161">Isso abrirá a folha específica para a política selecionada.</span><span class="sxs-lookup"><span data-stu-id="1193f-161">This opens the blade specific to the policy you selected.</span></span>

2.  <span data-ttu-id="1193f-162">Na folha da política, escolha **Grupos de usuários** para abrir a folha **Grupo de usuários** que mostra a lista atual de grupos de usuários que têm essa política.</span><span class="sxs-lookup"><span data-stu-id="1193f-162">In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.</span></span>

3.  <span data-ttu-id="1193f-163">Para adicionar um novo grupo de usuários à política, escolha **Adicionar grupo de usuários** e selecione o grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="1193f-163">To add a new user group to the policy, choose **Add user group**, and select the user group.</span></span> <span data-ttu-id="1193f-164">Escolha **Selecionar** para implantar a política no grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1193f-164">Choose **Select** to deploy the policy to the group you selected.</span></span>

4.  <span data-ttu-id="1193f-165">Para excluir um grupo de usuários, realce o grupo de usuários que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="1193f-165">To delete a user group, highlight the user group you want to remove.</span></span> <span data-ttu-id="1193f-166">Em seguida, selecione as reticências (...) e escolha **Excluir** para remover o grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="1193f-166">Then choose the ellipses (…), and choose **Delete** to remove the user group.</span></span>
  <span data-ttu-id="1193f-167">![Captura de tela mostrando a opção Excluir ](./media/app-protection-policy-delete-user.png)</span><span class="sxs-lookup"><span data-stu-id="1193f-167">![Screenshot showing Delete option ](./media/app-protection-policy-delete-user.png)</span></span>

### <span data-ttu-id="1193f-168">Para alterar as configurações de política</span><span class="sxs-lookup"><span data-stu-id="1193f-168">To change policy settings</span></span>
<a id="to-change-policy-settings" class="xliff"></a>

1.  <span data-ttu-id="1193f-169">Na folha **Política de aplicativos**, escolha a política que quer alterar.</span><span class="sxs-lookup"><span data-stu-id="1193f-169">In the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="1193f-170">Isso abrirá uma folha específica para a política que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="1193f-170">This opens a blade specific to the policy you just selected.</span></span>


2.  <span data-ttu-id="1193f-171">Escolha **Configurações de política** para abrir a folha **Configurações de política**.</span><span class="sxs-lookup"><span data-stu-id="1193f-171">Choose **Policy settings** to open the **Policy settings** blade.</span></span>

3.  <span data-ttu-id="1193f-172">Altere as configurações e escolha o ícone **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="1193f-172">Change the settings, and choose the **Save** icon to save your changes.</span></span>

## <span data-ttu-id="1193f-173">Configurações de política</span><span class="sxs-lookup"><span data-stu-id="1193f-173">Policy settings</span></span>
<a id="policy-settings" class="xliff"></a>
<span data-ttu-id="1193f-174">Para ver uma lista completa de configurações de política para iOS e Android, selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1193f-174">To see a full list of the policy settings for iOS and Android, select one of the following:</span></span>

- [<span data-ttu-id="1193f-175">Políticas do iOS</span><span class="sxs-lookup"><span data-stu-id="1193f-175">iOS policies</span></span>](app-protection-policy-settings-ios.md)
- [<span data-ttu-id="1193f-176">Políticas do Android</span><span class="sxs-lookup"><span data-stu-id="1193f-176">Android policies</span></span>](app-protection-policy-settings-android.md)

## <span data-ttu-id="1193f-177">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="1193f-177">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="1193f-178">Monitorar conformidade e status do usuário</span><span class="sxs-lookup"><span data-stu-id="1193f-178">Monitor compliance and user status</span></span>](app-protection-policies-monitor.md)

### <span data-ttu-id="1193f-179">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1193f-179">See also</span></span>
<a id="see-also" class="xliff"></a>
* [<span data-ttu-id="1193f-180">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1193f-180">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="1193f-181">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="1193f-181">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
