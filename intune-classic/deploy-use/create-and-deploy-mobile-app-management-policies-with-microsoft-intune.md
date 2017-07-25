---
title: "Criar e implantar políticas de MAM"
description: "Use as instruções passo a passo neste tópico para criar e implantar políticas de gerenciamento de aplicativos móveis."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ebb4b03307f8af7e1390c6db994d3120942fae89
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6881b-103">Criar e implantar as políticas de proteção de aplicativo com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6881b-103">Create and deploy app protection policies with Microsoft Intune</span></span>
<a id="create-and-deploy-app-protection-policies-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6881b-104">Esse tópico descreve o processo de criação de uma política de proteção de aplicativo no **Portal do Azure**.</span><span class="sxs-lookup"><span data-stu-id="6881b-104">This topic describes the process of creating an app protection policy in the **Azure portal**.</span></span> <span data-ttu-id="6881b-105">O portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo e é recomendável que você use este portal para criá-las.</span><span class="sxs-lookup"><span data-stu-id="6881b-105">The Azure portal is the new admin console for creating app protection policies, and we recommend that you use this portal to create app protection policies.</span></span> <span data-ttu-id="6881b-106">O portal do Azure dá suporte aos seguintes cenários MAM:</span><span class="sxs-lookup"><span data-stu-id="6881b-106">Azure portal supports the following MAM scenarios:</span></span>

- <span data-ttu-id="6881b-107">Dispositivos registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="6881b-107">Devices enrolled in Intune.</span></span>
- <span data-ttu-id="6881b-108">Dispositivos gerenciados por uma solução de MDM terceirizada.</span><span class="sxs-lookup"><span data-stu-id="6881b-108">Devices managed by a third-party MDM solution.</span></span>
- <span data-ttu-id="6881b-109">Dispositivos que não são gerenciados por uma solução MDM (BYOD).</span><span class="sxs-lookup"><span data-stu-id="6881b-109">Devices that are not managed by any MDM solution (BYOD).</span></span>

>[!IMPORTANT]
<span data-ttu-id="6881b-110">Aqui estão algumas considerações caso você esteja usando o **console de administração do Intune** para gerenciar seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="6881b-110">Here are a few considerations if you're using the **Intune admin console** to manage your devices:</span></span>

> * <span data-ttu-id="6881b-111">você pode criar uma política de proteção de aplicativo que dá suporte a aplicativos para dispositivos registrados no Intune usando o [console de administração do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span><span class="sxs-lookup"><span data-stu-id="6881b-111">You can create an app protection policy that supports apps for devices enrolled in Intune using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span></span>
> * <span data-ttu-id="6881b-112">As políticas de proteção de aplicativo criadas no console de administração do Intune não podem ser importadas no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="6881b-112">App protection policies created in the Intune admin console cannot be imported into the Azure portal.</span></span>  <span data-ttu-id="6881b-113">As políticas de proteção de aplicativo devem ser recriadas no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="6881b-113">The app protection policies must be re-created in the Azure portal.</span></span>

> * <span data-ttu-id="6881b-114">Você não poderá ver todas as configurações de política de proteção de aplicativo no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="6881b-114">You may not see all app protection policy settings in the Intune admin console.</span></span> <span data-ttu-id="6881b-115">O portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-115">The Azure portal is the new admin console for creating app protection policies.</span></span>

> * <span data-ttu-id="6881b-116">Para implantar aplicativos gerenciados, você precisa criar uma política de proteção de aplicativo no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="6881b-116">To deploy managed apps, you must create a app protection policy in the Intune admin console.</span></span> <span data-ttu-id="6881b-117">Nesse caso, talvez você queira criar política de proteção de aplicativo no console de administração do Intune e no portal do Azure: no console de administração do Intune para poder implantar aplicativos gerenciados e no portal do Azure porque ele é o novo console de administração que tem todas as configurações de política de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-117">In this case, you may want to create app protection policies in both the Intune admin console and the Azure portal: Intune admin console to make sure you have the ability to deploy managed apps, and the Azure portal because it is the new admin console that has all the app protection policy settings.</span></span>

> * <span data-ttu-id="6881b-118">Se você criar políticas de proteção de aplicativo no console de administração do Intune e no portal do Azure, a política criada no portal do Azure será aplicada aos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6881b-118">If you create app protection policies on both Intune admin console and Azure portal, the policy that is created in the Azure portal is applied to the apps.</span></span>

<span data-ttu-id="6881b-119">Para ver uma lista de configurações de política com suporte para as plataformas Android e iOS, selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6881b-119">To see a list of policy settings supported for Android and iOS platforms, select one of the following:</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="6881b-120">Políticas do iOS</span><span class="sxs-lookup"><span data-stu-id="6881b-120">iOS policies</span></span>](ios-mam-policy-settings.md)
- [<span data-ttu-id="6881b-121">Políticas do Android</span><span class="sxs-lookup"><span data-stu-id="6881b-121">Android policies</span></span>](android-mam-policy-settings.md)

- <span data-ttu-id="6881b-122">Para obter uma descrição mais detalhada do funcionamento das políticas de proteção de aplicativo e os cenários com suporte nas políticas de proteção de aplicativo do Intune, consulte [proteger dados de aplicativo usando as políticas de proteção de aplicativo](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="6881b-122">For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [protect app data using app protection policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).</span></span>

##  <span data-ttu-id="6881b-123">Criar uma política de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6881b-123">Create an app protection policy</span></span>
<a id="create-an-app-protection-policy" class="xliff"></a>
<span data-ttu-id="6881b-124">As políticas de proteção de aplicativo são criadas no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="6881b-124">App protection policies are created at the Azure Portal.</span></span> <span data-ttu-id="6881b-125">Se esta é a primeira vez que você está usando o Portal do Azure, leia [Portal do Azure para políticas de proteção de aplicativo do Microsoft Intune](azure-portal-for-microsoft-intune-mam-policies.md) para se familiarizar com o Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="6881b-125">If this is the first time you are using the Azure portal, read [Azure portal for Microsoft Intune app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) to get more familiar with the Azure Portal.</span></span> <span data-ttu-id="6881b-126">Antes de criar uma política de proteção de aplicativo, examine as informações de [pré-requisitos e suporte](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="6881b-126">Before creating an app protection policy, review the [pre-requisites and support](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) information.</span></span>

<span data-ttu-id="6881b-127">Siga as etapas abaixo para criar as políticas de proteção de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="6881b-127">Follow the steps below to create app protection policies:</span></span>

1. <span data-ttu-id="6881b-128">Acesse o [Portal do Azure](https://portal.azure.com) e insira suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="6881b-128">Go to the [Azure portal](https://portal.azure.com), and enter your credentials.</span></span>

2. <span data-ttu-id="6881b-129">Escolha **Mais Serviços** e digite "Intune".</span><span class="sxs-lookup"><span data-stu-id="6881b-129">Choose **More Services**, and type "Intune".</span></span>

3. <span data-ttu-id="6881b-130">Escolha **Proteção de Aplicativo do Intune**.</span><span class="sxs-lookup"><span data-stu-id="6881b-130">Choose **Intune App Protection**.</span></span>

4. <span data-ttu-id="6881b-131">Escolha **Gerenciamento de aplicativos móveis do Intune &gt; Configurações** para abrir a folha **Todas as Configurações**.</span><span class="sxs-lookup"><span data-stu-id="6881b-131">Choose **Intune mobile application management &gt; Settings** to open the **All Settings** blade.</span></span>

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  <span data-ttu-id="6881b-133">Na folha **Todas as configurações**, escolha **Política de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="6881b-133">In the **All Settings** blade, choose **App policy**.</span></span> <span data-ttu-id="6881b-134">Isso abre a folha **Política de aplicativo**, em que você criará novas políticas e editará as políticas existentes.</span><span class="sxs-lookup"><span data-stu-id="6881b-134">This opens the **App policy** blade, where you'll create new policies and edit existing policies.</span></span> <span data-ttu-id="6881b-135">Escolha **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="6881b-135">Choose **Add a policy**.</span></span>

    ![<span data-ttu-id="6881b-136">Captura de tela da folha Política de aplicativos com a opção de menu Adicionar uma política realçada</span><span class="sxs-lookup"><span data-stu-id="6881b-136">Screenshot of the App policy blade with the Add a policy menu option highlighted</span></span> ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  <span data-ttu-id="6881b-137">Digite um nome para a política, adicione uma breve descrição e selecione o tipo de plataforma para criar uma política para iOS ou Android.</span><span class="sxs-lookup"><span data-stu-id="6881b-137">Type a name for the policy, add a brief description, and select the platform type to create a policy for iOS or Android.</span></span> <span data-ttu-id="6881b-138">Você pode criar mais de uma política para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="6881b-138">You can create more than one policy for each platform.</span></span>

    ![Captura de tela da folha Adicionar uma política](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  <span data-ttu-id="6881b-140">Escolha **Aplicativos** para abrir a **folha Aplicativos**, em que uma lista de aplicativos disponíveis é exibida.</span><span class="sxs-lookup"><span data-stu-id="6881b-140">Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed.</span></span> <span data-ttu-id="6881b-141">Selecione um ou mais aplicativos da lista que deseja associar à política que está sendo criada.</span><span class="sxs-lookup"><span data-stu-id="6881b-141">Select one or more apps from the list that you want to associate with the policy that you are creating.</span></span> <span data-ttu-id="6881b-142">Depois de selecionar os aplicativos, escolha **Selecionar** na parte inferior da folha **Aplicativos** para salvar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="6881b-142">Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6881b-143">Você deve selecionar pelo menos um aplicativo para criar uma política.</span><span class="sxs-lookup"><span data-stu-id="6881b-143">You must select at least one app to create a policy.</span></span>

5.  <span data-ttu-id="6881b-144">Na folha **Adicionar uma política**, escolha **Definir as configurações necessárias** para abrir a folha de configurações da política.</span><span class="sxs-lookup"><span data-stu-id="6881b-144">On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.</span></span>

    <span data-ttu-id="6881b-145">Há duas categorias de configurações de política, **Realocação dos dados** e **Acesso**.</span><span class="sxs-lookup"><span data-stu-id="6881b-145">There are two categories of policy settings, **Data relocation** and **Access**.</span></span>  <span data-ttu-id="6881b-146">Políticas de realocação de dados aplicam-se à movimentação de dados dentro e fora dos aplicativos, enquanto as políticas de acesso determinam como o usuário final acessa os aplicativos em um contexto de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6881b-146">Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end user accesses the apps in a work context.</span></span>
    <span data-ttu-id="6881b-147">As configurações de política têm valores padrão para que você possa começar mais facilmente.</span><span class="sxs-lookup"><span data-stu-id="6881b-147">To get you started, the policy settings have default values.</span></span> <span data-ttu-id="6881b-148">Não é necessário fazer alterações se os valores padrão atendem às suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="6881b-148">You do not have to make any changes if the default values meet your requirements.</span></span>

    > [!TIP]
    > <span data-ttu-id="6881b-149">Essas configurações de política só são aplicadas ao usar aplicativos no contexto corporativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-149">These policy settings are enforced only when using apps in the work context.</span></span>  <span data-ttu-id="6881b-150">Quando o usuário final usa o aplicativo para executar uma tarefa pessoal, ele não é afetado por essas políticas.</span><span class="sxs-lookup"><span data-stu-id="6881b-150">When the end user uses the app to do a personal task, they will not be affected by these policies.</span></span>

    ![Captura de tela da folha de configurações, juntamente com a folha Adicionar uma política](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  <span data-ttu-id="6881b-152">Escolha **OK** para salvar esta configuração.</span><span class="sxs-lookup"><span data-stu-id="6881b-152">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="6881b-153">Agora você retornou à folha **Adicionar uma política** .</span><span class="sxs-lookup"><span data-stu-id="6881b-153">You are now back in the **Add a policy** blade.</span></span> <span data-ttu-id="6881b-154">Escolha **Criar** para criar a política e salvar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="6881b-154">Choose **Create** to create the policy and save your settings.</span></span>

    ![Captura de tela da folha Adicionar uma política mostrando que aplicativos e configurações foram definidos](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

<span data-ttu-id="6881b-156">Ao terminar de criar uma política conforme descrito no procedimento anterior, ela não é implantada para nenhum usuários.</span><span class="sxs-lookup"><span data-stu-id="6881b-156">When you finish creating a policy as described in the previous procedure, it is not deployed to any users.</span></span> <span data-ttu-id="6881b-157">Para implantar uma política, consulte a seção a seguir, "Implantar uma política para usuários".</span><span class="sxs-lookup"><span data-stu-id="6881b-157">To deploy a policy, see the following section, "Deploy a policy to users."</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6881b-158">Se você criar uma política de proteção de aplicativo para um aplicativo usando o console de administração do Intune e uma política de proteção de aplicativo usando o portal do Azure, a política criada usando o portal do Azure terá precedência.</span><span class="sxs-lookup"><span data-stu-id="6881b-158">If you create an app protection policy for an app using the Intune admin console and an app protection policy using the Azure portal, the policy you created using the Azure portal takes precedence.</span></span> <span data-ttu-id="6881b-159">No entanto, o relatório no console do Intune ou do Configuration Manager relatará as configurações de política criadas no console de administração do Intune.</span><span class="sxs-lookup"><span data-stu-id="6881b-159">However, the reporting in the Intune or Configuration Manager console will report the policy settings created from the Intune admin console.</span></span> <span data-ttu-id="6881b-160">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6881b-160">For example:</span></span>
>
> -   <span data-ttu-id="6881b-161">Você criou uma política de proteção de aplicativo no console de administração do Intune que bloqueia a cópia de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-161">You created an app protection policy in the Intune admin console that blocks copy from an app.</span></span>
> -   <span data-ttu-id="6881b-162">Você criou uma política de proteção de aplicativo no console do Azure que permite a cópia em um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-162">You created an app protection policy in the Azure console that allows copy from an app.</span></span>
> -   <span data-ttu-id="6881b-163">Você associa essas duas políticas ao mesmo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-163">You associate both of these policies to the same app.</span></span>
> -   <span data-ttu-id="6881b-164">A política criada no console do Azure tem precedência e a cópia é permitida.</span><span class="sxs-lookup"><span data-stu-id="6881b-164">The policy you created from the Azure console takes precedence, and copy is allowed.</span></span>
> -   <span data-ttu-id="6881b-165">No entanto, status e relatórios no console do Intune indicarão incorretamente que a cópia está bloqueada.</span><span class="sxs-lookup"><span data-stu-id="6881b-165">However, status and reports in the Intune console will incorrectly indicate that copy is blocked.</span></span>

## <span data-ttu-id="6881b-166">Aplicativos de linha de negócios (LOB) (opcionais)</span><span class="sxs-lookup"><span data-stu-id="6881b-166">Line of Business (LOB) apps (optional)</span></span>
<a id="line-of-business-lob-apps-optional" class="xliff"></a>

<span data-ttu-id="6881b-167">Começando com a versão do Intune 1703, você tem a opção de adicionar de modo geral aplicativos LOB no Intune ao criar uma nova política de proteção de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6881b-167">Beginning with Intune 1703 version, you have the option to generally add LOB apps into Intune when creating a new app protection policy.</span></span> <span data-ttu-id="6881b-168">Isso lhe dá a opção de definir políticas de proteção de aplicativos para aplicativos LOB usando o SDK do MAM sem a necessidade de permissões totais de implantação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="6881b-168">This gives you the option to define app protection policies for LOB apps using the MAM SDK without requiring full app deployment permissions.</span></span>
<span data-ttu-id="6881b-169">/intune/app-sdk-get-started</span><span class="sxs-lookup"><span data-stu-id="6881b-169">/intune/app-sdk-get-started</span></span>
> [!TIP]
> <span data-ttu-id="6881b-170">Você também pode adicionar aplicativos LOB no Intune percorrendo o fluxo de trabalho do [Intune App SDK](/intune/app-sdk-get-started).</span><span class="sxs-lookup"><span data-stu-id="6881b-170">You can also add LOB apps into Intune when going through the [Intune App SDK](/intune/app-sdk-get-started) work-flow.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6881b-171">Se os usuários tiverem apenas permissões específicas para implantar aplicativos MAM e não permissões totais de implantação de aplicativos, o que lhes permitiria implantar qualquer aplicativo no Intune, eles não conseguirão percorrer o fluxo de trabalho Intune SDK, mas ainda poderão adicionar seus aplicativos LOB por meio do fluxo de trabalho de criação de política de proteção de aplicativos MAM.</span><span class="sxs-lookup"><span data-stu-id="6881b-171">If users only have specific permissions for deploying MAM apps and not full app deployment permissions, which would allow them to deploy any apps in Intune, they won’t be able to go through the Intune SDK work-flow, but they can still add their LOB apps through the MAM app protection policy creation work-flow.</span></span>

### <span data-ttu-id="6881b-172">Para adicionar aplicativos LOB (iOS e Android)</span><span class="sxs-lookup"><span data-stu-id="6881b-172">To add LOB apps (iOS and Android)</span></span>
<a id="to-add-lob-apps-ios-and-android" class="xliff"></a>

1.  <span data-ttu-id="6881b-173">Na caixa Adicionar uma folha de política, selecione Configurar **aplicativos** para abrir a folha de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6881b-173">On the Add a policy blade, choose Configure **Apps** to open the Apps blade.</span></span>

    ![MAM Adicionar uma folha de política](../media/AppManagement/mam-lob-apps-1.png)

2.  <span data-ttu-id="6881b-175">Clique em **Mais aplicativos**, em seguida, digite a **ID do pacote** (para iOS), **ID do pacote** (para Android), clique em Selecionar para adicionar seus aplicativos LOB.</span><span class="sxs-lookup"><span data-stu-id="6881b-175">Click **More apps**, then enter the **Bundle ID** (for iOS), **package ID** (for Android), then click Select to add your LOB apps.</span></span>

    ![MAM Folha de mais aplicativos](../media/AppManagement/mam-lob-apps-2.png)

### <span data-ttu-id="6881b-177">Para adicionar aplicativos LOB (Windows)</span><span class="sxs-lookup"><span data-stu-id="6881b-177">To add LOB apps (Windows)</span></span>
<a id="to-add-lob-apps-windows" class="xliff"></a>

> [!IMPORTANT]
> <span data-ttu-id="6881b-178">Você precisa selecionar o Windows 10 na lista suspensa da plataforma ao criar uma nova política de proteção de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6881b-178">You need to select Windows 10 from the platform drop-down list when creating a new app protection policy.</span></span>

1.  <span data-ttu-id="6881b-179">Na caixa Adicionar uma folha de política, selecione **Aplicativos permitidos** ou **Aplicativos isentos** para abrir a folha de aplicativos permitidos ou isentos.</span><span class="sxs-lookup"><span data-stu-id="6881b-179">On the Add a policy blade, choose **Allowed apps** or **Exempt apps** to open the Allowed or Exempt apps blade.</span></span>

    > [!NOTE]
    >
    - <span data-ttu-id="6881b-180">**Aplicativos permitidos**: Estes são os aplicativos que precisam atender a esta política.</span><span class="sxs-lookup"><span data-stu-id="6881b-180">**Allowed apps**: These are the apps that need to adhere to this policy.</span></span>
    - <span data-ttu-id="6881b-181">**Aplicativos isentos**: Estes aplicativos são isentos desta política e podem acessar dados corporativos sem restrições.</span><span class="sxs-lookup"><span data-stu-id="6881b-181">**Exempt apps**: These apps are exempt from this policy and can access corporate data without restrictions.</span></span>
<br></br>
2. <span data-ttu-id="6881b-182">Na folha de aplicativos permitidos ou isentos, clique em **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="6881b-182">On Allowed or Exempt apps blade, click **Add apps**.</span></span> <span data-ttu-id="6881b-183">Você pode adicionar aplicativos recomendados pela Microsoft, adicionar aplicativos da área de trabalho ou da loja.</span><span class="sxs-lookup"><span data-stu-id="6881b-183">You can add recommended Microsoft apps, add store or desktop apps.</span></span>

    <span data-ttu-id="6881b-184">a.</span><span class="sxs-lookup"><span data-stu-id="6881b-184">a.</span></span>  <span data-ttu-id="6881b-185">**Aplicativos recomendados:** uma lista pré-populada de aplicativos (principalmente do Office) que deixamos os administradores importar facilmente para a política.</span><span class="sxs-lookup"><span data-stu-id="6881b-185">**Recommended apps:** a pre-populated list of (mostly Office) apps that we let admins easily import into policy.</span></span>

    <span data-ttu-id="6881b-186">b.</span><span class="sxs-lookup"><span data-stu-id="6881b-186">b.</span></span>  <span data-ttu-id="6881b-187">**Aplicativos da loja:** O administrador pode adicionar qualquer aplicativo da Windows Store à política.</span><span class="sxs-lookup"><span data-stu-id="6881b-187">**Store apps:** Admin can add any app from the Windows store to policy.</span></span>

    <span data-ttu-id="6881b-188">c.</span><span class="sxs-lookup"><span data-stu-id="6881b-188">c.</span></span>  <span data-ttu-id="6881b-189">**Aplicativos da área de trabalho do Windows:** O administrador pode adicionar qualquer aplicativo tradicional de área de trabalho do Windows à política (por exemplo, exe, dll, etc.)</span><span class="sxs-lookup"><span data-stu-id="6881b-189">**Windows desktop apps:** Admin can add any traditional Windows desktop apps to the policy (e.g. exe, dll, etc.)</span></span>

## <span data-ttu-id="6881b-190">Implantar uma política para os usuários</span><span class="sxs-lookup"><span data-stu-id="6881b-190">Deploy a policy to users</span></span>
<a id="deploy-a-policy-to-users" class="xliff"></a>

1.  <span data-ttu-id="6881b-191">Na folha **Política**, escolha **Grupos de usuários**, o que abre a folha **Grupos de usuários**.</span><span class="sxs-lookup"><span data-stu-id="6881b-191">In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade.</span></span> <span data-ttu-id="6881b-192">Escolha **Adicionar grupo de usuários** na folha **Grupos de usuários** para abrir a folha **Adicionar grupo de usuários**.</span><span class="sxs-lookup"><span data-stu-id="6881b-192">Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.</span></span>

    ![Captura de tela da folha Grupos de usuários com a opção de menu Adicionar grupo de usuários realçada](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  <span data-ttu-id="6881b-194">Uma lista de grupos de usuários é exibida na folha **Adicionar grupo de usuários** .</span><span class="sxs-lookup"><span data-stu-id="6881b-194">A list of user groups is displayed on the **Add user group** blade.</span></span> <span data-ttu-id="6881b-195">Esta é uma lista de todos os grupos de segurança no seu **Active Directory do Azure**.</span><span class="sxs-lookup"><span data-stu-id="6881b-195">This is a list of all the security groups in your **Azure Active Directory**.</span></span> <span data-ttu-id="6881b-196">Selecione os grupos de usuários aos quais deseja que essa política seja aplicada e escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="6881b-196">Select the user groups you want this policy to apply to, and then choose **Select**.</span></span> <span data-ttu-id="6881b-197">A escolha de **Selecionar** implanta a política para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6881b-197">Choosing **Select**, deploys the policy to users.</span></span>

    ![Captura de tela da folha Adicionar grupo de usuários adicionar mostrando a lista de usuários do Azure Active Directory](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    <span data-ttu-id="6881b-199">Agora você criou uma política e a implantou para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6881b-199">You have now created a policy and deployed it to users.</span></span>

<span data-ttu-id="6881b-200">Somente usuários com licenças do Intune atribuídas serão afetados pela política.</span><span class="sxs-lookup"><span data-stu-id="6881b-200">Only users with Intune licenses assigned to them are affected by the policy.</span></span> <span data-ttu-id="6881b-201">Os usuários que estão no grupo de segurança que você selecionou e que não têm uma licença do Intune atribuída não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="6881b-201">Users who are in the security group that you selected who don’t have a Intune license assigned to them are not affected.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="6881b-202">Se você estiver usando o Intune com o Configuration Manager para gerenciar seus dispositivos Android e iOS, a política só será aplicada aos usuários diretamente no grupo que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="6881b-202">If you are using Intune with Configuration Manager to manage your iOS and Android devices, the policy is only applied to the users directly in the group that you selected.</span></span> <span data-ttu-id="6881b-203">Membros de grupos filho aninhados dentro do grupo selecionado não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="6881b-203">Members of child groups nested within the group you selected are not affected.</span></span>

<span data-ttu-id="6881b-204">Os usuários finais podem baixar os aplicativos da loja de aplicativos ou do Google Play.</span><span class="sxs-lookup"><span data-stu-id="6881b-204">End users can download the apps from the App store or Google Play.</span></span> <span data-ttu-id="6881b-205">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="6881b-205">For more information, see:</span></span>
* [<span data-ttu-id="6881b-206">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6881b-206">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="6881b-207">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6881b-207">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)

##  <span data-ttu-id="6881b-208">Alterar políticas existentes</span><span class="sxs-lookup"><span data-stu-id="6881b-208">Change existing policies</span></span>
<a id="change-existing-policies" class="xliff"></a>
<span data-ttu-id="6881b-209">Você pode editar uma política existente e aplicá-la aos usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="6881b-209">You can edit an existing policy and apply it to the targeted users.</span></span> <span data-ttu-id="6881b-210">No entanto, quando você altera as políticas existentes, os usuários já conectados aos aplicativos só verão as alterações após um período de 8 horas.</span><span class="sxs-lookup"><span data-stu-id="6881b-210">However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.</span></span>

<span data-ttu-id="6881b-211">Para ver o efeito das alterações imediatamente, o usuário final precisará sair do aplicativo e entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="6881b-211">To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.</span></span>

### <span data-ttu-id="6881b-212">Para alterar a lista de aplicativos associados à política</span><span class="sxs-lookup"><span data-stu-id="6881b-212">To change the list of apps associated with the policy</span></span>
<a id="to-change-the-list-of-apps-associated-with-the-policy" class="xliff"></a>

1.  <span data-ttu-id="6881b-213">Na folha **Política de aplicativos**, escolha a política que quer alterar.</span><span class="sxs-lookup"><span data-stu-id="6881b-213">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="6881b-214">Isso abrirá uma folha específica para a política que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="6881b-214">This opens a blade specific to the policy you just selected.</span></span>

    ![Captura de tela de uma política existente aberta em uma folha separada](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  <span data-ttu-id="6881b-216">Na folha de política, escolha **Aplicativos de destino** para abrir a lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="6881b-216">In the policy blade, choose **Targeted apps** to open the list of apps.</span></span>

3.  <span data-ttu-id="6881b-217">Remova ou adicione aplicativos da lista e escolha o ícone **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="6881b-217">Remove or add apps from the list and choose the **Save** icon to save your changes.</span></span>

### <span data-ttu-id="6881b-218">Para alterar a lista de grupos de usuários</span><span class="sxs-lookup"><span data-stu-id="6881b-218">To change the list of user groups</span></span>
<a id="to-change-the-list-of-user-groups" class="xliff"></a>

1.  <span data-ttu-id="6881b-219">Na folha **Política de aplicativos**, escolha a política que quer alterar.</span><span class="sxs-lookup"><span data-stu-id="6881b-219">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="6881b-220">Isso abrirá a folha específica para a política selecionada.</span><span class="sxs-lookup"><span data-stu-id="6881b-220">This opens the blade specific to the policy you selected.</span></span>

2.  <span data-ttu-id="6881b-221">Na folha da política, escolha **Grupos de usuários** para abrir a folha **Grupo de usuários** que mostra a lista atual de grupos de usuários que têm essa política.</span><span class="sxs-lookup"><span data-stu-id="6881b-221">In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.</span></span>

3.  <span data-ttu-id="6881b-222">Para adicionar um novo grupo de usuários à política, escolha **Adicionar grupo de usuários** e selecione o grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="6881b-222">To add a new user group to the policy, choose **Add user group**, and select the user group.</span></span> <span data-ttu-id="6881b-223">Escolha **Selecionar** para implantar a política no grupo selecionado.</span><span class="sxs-lookup"><span data-stu-id="6881b-223">Choose **Select** to deploy the policy to the group you selected.</span></span>

    ![Captura de tela da folha Adicionar grupo de usuários, com dois grupos de usuários selecionados](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  <span data-ttu-id="6881b-225">Para excluir um grupo de usuários, realce o grupo de usuários que deseja remover.</span><span class="sxs-lookup"><span data-stu-id="6881b-225">To delete a user group, highlight the user group you want to remove.</span></span> <span data-ttu-id="6881b-226">Em seguida, selecione as reticências (...) e escolha **Excluir** para remover o grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="6881b-226">Then choose the ellipses (…), and choose **Delete** to remove the user group.</span></span>

    ![<span data-ttu-id="6881b-227">Captura de tela mostrando a opção Excluir</span><span class="sxs-lookup"><span data-stu-id="6881b-227">Screenshot showing Delete option</span></span> ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <span data-ttu-id="6881b-228">Para alterar as configurações de política</span><span class="sxs-lookup"><span data-stu-id="6881b-228">To change policy settings</span></span>
<a id="to-change-policy-settings" class="xliff"></a>

1.  <span data-ttu-id="6881b-229">Na folha **Política de aplicativos**, escolha a política que quer alterar.</span><span class="sxs-lookup"><span data-stu-id="6881b-229">In the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="6881b-230">Isso abrirá uma folha específica para a política que você selecionou.</span><span class="sxs-lookup"><span data-stu-id="6881b-230">This opens a blade specific to the policy you just selected.</span></span>

    ![<span data-ttu-id="6881b-231">Captura de tela de uma política existente aberta em uma folha separada</span><span class="sxs-lookup"><span data-stu-id="6881b-231">Screenshot of an existing policy open in a separate blade</span></span> ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  <span data-ttu-id="6881b-232">Escolha **Configurações de política** para abrir a folha **Configurações de política**.</span><span class="sxs-lookup"><span data-stu-id="6881b-232">Choose **Policy settings** to open the **Policy settings** blade.</span></span>

3.  <span data-ttu-id="6881b-233">Altere as configurações e escolha o ícone **Salvar** para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="6881b-233">Change the settings, and choose the **Save** icon to save your changes.</span></span>

    ![Captura de tela da folha Configurações de política mostrando a opção de menu Salvar na parte superior](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <span data-ttu-id="6881b-235">Configurações de política</span><span class="sxs-lookup"><span data-stu-id="6881b-235">Policy settings</span></span>
<a id="policy-settings" class="xliff"></a>
<span data-ttu-id="6881b-236">Para ver uma lista completa de configurações de política para iOS e Android, selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="6881b-236">To see a full list of the policy settings for iOS and Android, select one of the following:</span></span>

> [!div class="op_single_selector"]
- [<span data-ttu-id="6881b-237">Políticas do iOS</span><span class="sxs-lookup"><span data-stu-id="6881b-237">iOS policies</span></span>](ios-mam-policy-settings.md)
- [<span data-ttu-id="6881b-238">Políticas do Android</span><span class="sxs-lookup"><span data-stu-id="6881b-238">Android policies</span></span>](android-mam-policy-settings.md)

## <span data-ttu-id="6881b-239">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="6881b-239">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="6881b-240">Monitorar conformidade e status do usuário</span><span class="sxs-lookup"><span data-stu-id="6881b-240">Monitor compliance and user status</span></span>](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <span data-ttu-id="6881b-241">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6881b-241">See also</span></span>
<a id="see-also" class="xliff"></a>
* [<span data-ttu-id="6881b-242">O que esperar quando seu aplicativo Android é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6881b-242">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="6881b-243">O que esperar quando seu aplicativo iOS é gerenciado por políticas de proteção de aplicativo</span><span class="sxs-lookup"><span data-stu-id="6881b-243">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)
