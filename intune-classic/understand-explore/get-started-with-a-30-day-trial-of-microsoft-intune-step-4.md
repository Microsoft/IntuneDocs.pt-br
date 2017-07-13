---
title: "Criar políticas e publicar um aplicativo para os usuários"
description: "Como criar políticas e publicar um aplicativo quando você se inscrever para uma avaliação gratuita de 30 dias do Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 12/12/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c3a17884-442a-44f5-bc81-4589e823f65e
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 335d91cd6583052bfcc72fc018b387eed8823b7e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="27d4e-103">Criar políticas e publicar um aplicativo para usuários de avaliação</span><span class="sxs-lookup"><span data-stu-id="27d4e-103">Create policies and publish an app to evaluation users</span></span>
<a id="create-policies-and-publish-an-app-to-evaluation-users" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="27d4e-104">As políticas do Intune fornecem configurações que ajudam a controlar as configurações de segurança em dispositivos móveis, a manter as configurações do Firewall do Windows e do Endpoint Protection para computadores e a implantar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="27d4e-104">Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications.</span></span> <span data-ttu-id="27d4e-105">Se você estiver planejando usar o Intune em dispositivos que configura para uso em produção após a avaliação, será absolutamente essencial que você siga as instruções em [Gerenciar configurações e recursos em seus dispositivos com as políticas do Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="27d4e-105">If you are planning to use Intune for devices that you configure for production use after the evaluation, it's absolutely essential that you follow the instructions in [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).</span></span>

<span data-ttu-id="27d4e-106">Você pode executar dois tipos de instalações de aplicativos usando o Intune.</span><span class="sxs-lookup"><span data-stu-id="27d4e-106">You can perform two types of app installations using Intune.</span></span> <span data-ttu-id="27d4e-107">A primeira é uma **instalação obrigatória**, que implanta automaticamente o aplicativo em dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="27d4e-107">The first is a **required install**, which automatically deploys the app to managed devices.</span></span> <span data-ttu-id="27d4e-108">A outra é uma **instalação disponível**, que implanta o aplicativo ou um link para o aplicativo, no Portal da Empresa do Intune para que os usuários possam optar por instalá-lo em seus computadores ou em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="27d4e-108">The other is an **available install**, which deploys the app, or a link to the app, to the Intune Company Portal so that users can choose whether to install it on their computers or on their mobile devices.</span></span>

<span data-ttu-id="27d4e-109">Antes de usar o Intune para implantar aplicativos, certifique-se de ter as licenças apropriadas para publicar, distribuir e usar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="27d4e-109">Before using Intune to deploy apps, make sure that you have the appropriate licenses to publish, distribute, and use the app.</span></span> <span data-ttu-id="27d4e-110">O espaço de trabalho **Licenças** permite adicionar e gerenciar informações de contrato de licença para aplicativos ou software adquiridos por meio de contratos de Licenciamento por Volume da Microsoft e para aplicativos e softwares, da Microsoft ou não, que tenham sido adquiridos por outros meios.</span><span class="sxs-lookup"><span data-stu-id="27d4e-110">The **Licenses** workspace lets you add and manage license agreement information for apps or software purchased through Microsoft Volume Licensing agreements, and for Microsoft or non-Microsoft apps or software purchased by other means.</span></span> <span data-ttu-id="27d4e-111">Você pode criar relatórios de licenças que exibam informações de uso de licença gerenciado em toda a empresa para se manter informado sobre a atividade de uso da licença.</span><span class="sxs-lookup"><span data-stu-id="27d4e-111">You can then create license reports, which display managed license usage information throughout your company, to stay informed of license usage activity.</span></span>

<span data-ttu-id="27d4e-112">Nestas etapas, você vai configurar uma política de configuração de dispositivo móvel e uma política de firewall de computador do Windows, além de configurar o Skype como uma instalação disponível para dispositivos móveis depois de eles serem registrados.</span><span class="sxs-lookup"><span data-stu-id="27d4e-112">In these steps, you'll set up a mobile device configuration policy and a Windows computer firewall policy, and configure Skype as an available install for mobile devices after they're enrolled.</span></span> <span data-ttu-id="27d4e-113">Depois de você adicionar e implantar uma nova política, todos os usuários ou dispositivos do grupo no qual você implantou a política herdam as configurações como sua política de linha de base.</span><span class="sxs-lookup"><span data-stu-id="27d4e-113">After you add and deploy a new policy, all users or devices in the group to which you deployed the policy inherit the settings as their baseline policy.</span></span> <span data-ttu-id="27d4e-114">Você poderá sempre examinar e editar os detalhes dessas políticas posteriormente usando o espaço de trabalho **Política** no console de administração.</span><span class="sxs-lookup"><span data-stu-id="27d4e-114">You can always review and edit the details of these policies later from the **Policy** workspace in the administration console.</span></span>

## <span data-ttu-id="27d4e-115">Criar e implantar uma política de segurança de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="27d4e-115">Create and deploy a mobile device configuration policy</span></span>
<a id="create-and-deploy-a-mobile-device-configuration-policy" class="xliff"></a>

1.  <span data-ttu-id="27d4e-116">Abra o [Console de administração do Intune](https://manage.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="27d4e-116">Open the [Intune administration console](https://manage.microsoft.com/).</span></span>

2.  <span data-ttu-id="27d4e-117">No painel à esquerda, escolha o ícone **Política**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-117">In the left pane, choose the **Policy** icon.</span></span>

3.  <span data-ttu-id="27d4e-118">Na lista **Tarefas**, na página **Visão Geral de Políticas**, escolha **Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-118">In the **Tasks** list on the **Policy Overview** page, choose **Add Policy**.</span></span>

4.  <span data-ttu-id="27d4e-119">Na lista de políticas, expanda a plataforma para a qual deseja criar uma política, selecione **Configuração Geral**, escolha **Criar e Implantar uma Política Personalizada** e escolha **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-119">In the policy list, expand the platform you want to create a policy for, select **General Configuration**, choose **Create and Deploy a Custom Policy**, and then choose **Create Policy**.</span></span>

5.  <span data-ttu-id="27d4e-120">Quando for solicitado para **Selecionar os grupos aos quais você deseja implantar essa política**, selecione **Meus Usuários de Avaliação** na lista e escolha **Adicionar** &gt; **OK**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-120">When prompted to **Select the groups to which you want to deploy this policy**, select **My Trial Users** from the list, and choose **Add** &gt; **OK**.</span></span>

<span data-ttu-id="27d4e-121">Sua política aparece na lista de políticas de configuração e foi implantada no grupo **Meus usuários de avaliação**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-121">Your policy appears in the list of configuration policies, and has been deployed to the **My Trial Users** group.</span></span> <span data-ttu-id="27d4e-122">Clique duas vezes na política para exibir suas configurações.</span><span class="sxs-lookup"><span data-stu-id="27d4e-122">Double-click the policy to view its settings.</span></span>

## <span data-ttu-id="27d4e-123">Publicar o aplicativo do Skype para dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="27d4e-123">Publish the Skype app for mobile devices</span></span>
<a id="publish-the-skype-app-for-mobile-devices" class="xliff"></a>

1.  <span data-ttu-id="27d4e-124">No [console de administração do Intune](https://manage.microsoft.com/), escolha o ícone **Aplicativos** e, em seguida, escolha **Aplicativos** &gt; **Adicionar Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-124">In the [Intune administration console](https://manage.microsoft.com/), choose the **Apps** icon, then choose **Apps** &gt; **Add App**.</span></span> <span data-ttu-id="27d4e-125">Quando solicitado, insira suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="27d4e-125">If prompted, enter your Intune credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27d4e-126">Ao iniciar o **Intune Software Publisher** pela primeira vez, um pequeno atraso ocorrerá durante a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="27d4e-126">When you start the **Intune Software Publisher** for the first time, a short delay occurs while the application is installed.</span></span>

2.  <span data-ttu-id="27d4e-127">Examine o aviso de segurança e selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-127">Review the security warning, and choose **Run**.</span></span>

3.  <span data-ttu-id="27d4e-128">Na página **Antes de começar**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-128">On the **Before you begin** page, choose **Next**.</span></span>

4.  <span data-ttu-id="27d4e-129">Na página **Configuração de software**, em **Selecionar como esse software será disponibilizado para os dispositivos**, selecione **Link externo**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-129">On the **Software setup** page in **Select how this software is made available to devices**, select **External link**.</span></span>

5.  <span data-ttu-id="27d4e-130">Insira o link externo para o software em **Especificar a URL** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-130">Enter the external link for the software in **Specify the URL**, and then choose **Next**.</span></span> <span data-ttu-id="27d4e-131">Certifique-se de iniciar a URL com **https://**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-131">Make sure that you preface the URL with **https://**.</span></span> <span data-ttu-id="27d4e-132">Para o aplicativo do Skype, use o link abaixo que corresponda à plataforma de dispositivo móvel que você está usando:</span><span class="sxs-lookup"><span data-stu-id="27d4e-132">For the Skype app, use the link below that matches the mobile device platform you're using:</span></span>

    -   <span data-ttu-id="27d4e-133">**iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)</span><span class="sxs-lookup"><span data-stu-id="27d4e-133">**iOS:** [https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8](https://itunes.apple.com/us/app/skype-for-iphone/id304878510?mt%3D8)</span></span>

    -   <span data-ttu-id="27d4e-134">**Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)</span><span class="sxs-lookup"><span data-stu-id="27d4e-134">**Android:** [https://play.google.com/store/apps/details?id=com.skype.raider](https://play.google.com/store/apps/details?id=com.skype.raider)</span></span>

    -   <span data-ttu-id="27d4e-135">**Windows Phone 8.1:** [http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)</span><span class="sxs-lookup"><span data-stu-id="27d4e-135">**Windows Phone 8.1:** [http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51](http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51)</span></span>

6.  <span data-ttu-id="27d4e-136">Na página **Descrição do software**, forneça as informações que deseja que os usuários vejam no Portal da Empresa para o software e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-136">On the **Software description** page, provide the information that you want users to see in the Company Portal for the software, and then choose **Next**.</span></span> <span data-ttu-id="27d4e-137">As configurações a seguir estão disponíveis (este exemplo refere-se ao Skype):</span><span class="sxs-lookup"><span data-stu-id="27d4e-137">The following settings are available (this example refers to Skype):</span></span>

    -   <span data-ttu-id="27d4e-138">**Editor:** insira o nome do editor, **Microsoft**</span><span class="sxs-lookup"><span data-stu-id="27d4e-138">**Publisher:** Enter the name of the publisher, **Microsoft**</span></span>

    -   <span data-ttu-id="27d4e-139">**Nome:** Insira **Skype**</span><span class="sxs-lookup"><span data-stu-id="27d4e-139">**Name:** Enter **Skype**</span></span>

    -   <span data-ttu-id="27d4e-140">**Descrição:** Insira uma descrição para o software, como **Aplicativo de comunicação do Skype**</span><span class="sxs-lookup"><span data-stu-id="27d4e-140">**Description:** Enter a description for the software, such as **Skype communication app**</span></span>

    -   <span data-ttu-id="27d4e-141">**Categoria:** Selecione a categoria mais adequada a esse software, como **Colaboração**</span><span class="sxs-lookup"><span data-stu-id="27d4e-141">**Category:** Select the category that best fits this software, such as **Collaboration**</span></span>

    -   <span data-ttu-id="27d4e-142">**Exibir isto como um aplicativo em destaque e realçá-lo no portal da empresa:** selecione esta opção para exibir o aplicativo em destaque no Portal da Empresa em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="27d4e-142">**Display this as a featured app and highlight it in the company portal:** Select this option to display the app prominently in the Company Portal on mobile devices.</span></span>

    -   <span data-ttu-id="27d4e-143">**Ícone:** (Opcional) Escolha se deseja associar um ícone ao software.</span><span class="sxs-lookup"><span data-stu-id="27d4e-143">**Icon:**  (Optional) Choose whether to associate an icon with the software.</span></span> <span data-ttu-id="27d4e-144">O tamanho máximo do ícone é de 250 x 250 pixels, mas o tamanho do ícone recomendado é 32 x 32 pixels.</span><span class="sxs-lookup"><span data-stu-id="27d4e-144">The maximum icon size is 250 x 250 pixels, but the recommended icon size is 32 x 32 pixels.</span></span>

7.  <span data-ttu-id="27d4e-145">Na página **Resumo**, verifique as informações do software e, em seguida, escolha **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-145">On the **Summary** page, verify the software information, and then choose **Upload**.</span></span> <span data-ttu-id="27d4e-146">Selecione **Fechar** para sair do assistente.</span><span class="sxs-lookup"><span data-stu-id="27d4e-146">Choose **Close** to exit the wizard.</span></span>

8.  <span data-ttu-id="27d4e-147">No [console de administração do Intune](https://manage.microsoft.com/), escolha **Aplicativos** &gt; **Aplicativos** &gt; **Skype** &gt; **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-147">In the [Intune administration console](https://manage.microsoft.com/), choose **Apps** &gt; **Apps** &gt; **Skype** &gt; **Manage Deployment**.</span></span>

9. <span data-ttu-id="27d4e-148">Na página **Selecionar grupos**, selecione **Meus Usuários de Avaliação** para implantar o software a esse grupo de usuários e escolha **Adicionar** &gt; **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-148">On the **Select Groups** page, select **My Trial Users** to deploy the software to that user group, and then choose **Add** &gt; **Next**.</span></span>

10. <span data-ttu-id="27d4e-149">Na página **Ação de implantação**, selecione **Instalação disponível** na coluna **Aprovação** de seu grupo.</span><span class="sxs-lookup"><span data-stu-id="27d4e-149">On the **Deployment Action** page, select **Available Install** from the **Approval** column for your group.</span></span>

11. <span data-ttu-id="27d4e-150">Escolha **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="27d4e-150">Choose **Finish**.</span></span>

## <span data-ttu-id="27d4e-151">Instalar o aplicativo do Skype</span><span class="sxs-lookup"><span data-stu-id="27d4e-151">Install the Skype app</span></span>
<a id="install-the-skype-app" class="xliff"></a>
<span data-ttu-id="27d4e-152">Abra o Portal da Empresa no dispositivo móvel, escolha **Aplicativos**e, em seguida, instale o Microsoft Skype.</span><span class="sxs-lookup"><span data-stu-id="27d4e-152">Open the Company Portal on the mobile device, choose **Apps**, and then install Microsoft Skype.</span></span>

<span data-ttu-id="27d4e-153">Isso conclui o guia de gerenciamento de dispositivos móveis do Intune, mas você pode aprender mais sobre o Intune seguindo os links na seção Próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="27d4e-153">This completes the Intune mobile device management guide, but you can learn more about Intune by following the links in the Next steps section.</span></span>
## <span data-ttu-id="27d4e-154">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="27d4e-154">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="27d4e-155">Saber mais sobre outros [recursos do Intune](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)</span><span class="sxs-lookup"><span data-stu-id="27d4e-155">Learn more about other [Intune capabilities](get-started-with-a-30-day-trial-of-microsoft-intune-step-6.md)</span></span>

<span data-ttu-id="27d4e-156">Ler sobre as [formas comuns para usar o Intune](/intune/common-scenarios)</span><span class="sxs-lookup"><span data-stu-id="27d4e-156">Read about the [common ways to use Intune](/intune/common-scenarios)</span></span>

<span data-ttu-id="27d4e-157">Converter em uma [assinatura paga](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md)</span><span class="sxs-lookup"><span data-stu-id="27d4e-157">Convert to a [paid subscription](get-started-with-a-30-day-trial-of-microsoft-intune-step-7.md)</span></span>
