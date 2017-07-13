---
title: "Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune"
description: "Criar e implantar a política de proteção do aplicativo WIP com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51e53e28-5c34-4d0f-a4b1-6390a337514c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7aa879307ef3b72660d1ba7b3c3c2f99fc82dc97
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="89a0b-103">Criar e implantar a política de proteção de aplicativo WIP (Proteção de Informações do Windows) com o Intune</span><span class="sxs-lookup"><span data-stu-id="89a0b-103">Create and deploy Windows Information Protection (WIP) app protection policy with Intune</span></span>
<a id="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune" class="xliff"></a>

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="89a0b-104">A partir da versão 1704 do Intune, você poderá usar políticas de proteção de aplicativo com o Windows 10 no MAM (gerenciamento de aplicativo móvel) sem o cenário de registro.</span><span class="sxs-lookup"><span data-stu-id="89a0b-104">Beginning with Intune 1704 release, you can use app protection policies with Windows 10 in the mobile application management (MAM) without enrollment scenario.</span></span>

## <span data-ttu-id="89a0b-105">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="89a0b-105">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="89a0b-106">Vamos falar sobre alguns conceitos ao adicionar uma política WIP.</span><span class="sxs-lookup"><span data-stu-id="89a0b-106">Let’s talk about a few concepts when adding a WIP policy.</span></span>

### <span data-ttu-id="89a0b-107">Lista de aplicativos permitidos e isentos</span><span class="sxs-lookup"><span data-stu-id="89a0b-107">List of Allowed and Exempt apps</span></span>
<a id="list-of-allowed-and-exempt-apps" class="xliff"></a>

-   <span data-ttu-id="89a0b-108">**Aplicativos permitidos**: estes são os aplicativos que precisam atender a esta política.</span><span class="sxs-lookup"><span data-stu-id="89a0b-108">**Allowed apps:** These are the apps that need to adhere to this policy.</span></span>

-   <span data-ttu-id="89a0b-109">**Aplicativos isentos**: estes aplicativos são isentos desta política e podem acessar dados corporativos sem restrições.</span><span class="sxs-lookup"><span data-stu-id="89a0b-109">**Exempt apps:** These apps are exempt from this policy and can access corporate data without restrictions.</span></span>

### <span data-ttu-id="89a0b-110">Tipos de aplicativos</span><span class="sxs-lookup"><span data-stu-id="89a0b-110">Types of apps</span></span>
<a id="types-of-apps" class="xliff"></a>

-   <span data-ttu-id="89a0b-111">**Aplicativos recomendados:** uma lista pré-populada de aplicativos (principalmente do Microsoft Office) que permite que os administradores importem facilmente para a política.</span><span class="sxs-lookup"><span data-stu-id="89a0b-111">**Recommended apps:** a pre-populated list of (mostly Microsoft Office) apps that allow admins easily import into policy.</span></span>

-   <span data-ttu-id="89a0b-112">**Aplicativos da loja:** O administrador pode adicionar qualquer aplicativo da Windows Store à política.</span><span class="sxs-lookup"><span data-stu-id="89a0b-112">**Store apps:** Admin can add any app from the Windows store to policy.</span></span>

-   <span data-ttu-id="89a0b-113">**Aplicativos da área de trabalho do Windows:** O administrador pode adicionar qualquer aplicativo tradicional de área de trabalho do Windows à política (por exemplo, exe, dll, etc.)</span><span class="sxs-lookup"><span data-stu-id="89a0b-113">**Windows desktop apps:** Admin can add any traditional Windows desktop apps to the policy (e.g. exe, dll, etc.)</span></span>

## <span data-ttu-id="89a0b-114">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="89a0b-114">Pre-requisites</span></span>
<a id="pre-requisites" class="xliff"></a>

<span data-ttu-id="89a0b-115">Você precisa configurar o provedor MAM antes de criar uma política de proteção de aplicativo WIP.</span><span class="sxs-lookup"><span data-stu-id="89a0b-115">You need to configure the MAM provider before you can create a WIP app protection policy.</span></span>

-   <span data-ttu-id="89a0b-116">Saiba mais sobre [como configurar seu provedor MAM com o Intune](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10).</span><span class="sxs-lookup"><span data-stu-id="89a0b-116">Learn more about [how to configure your MAM provider with Intune](/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10).</span></span>

<span data-ttu-id="89a0b-117">Além disso, você precisará ter o seguintes:</span><span class="sxs-lookup"><span data-stu-id="89a0b-117">Additionally, you need to have the following:</span></span>

-   <span data-ttu-id="89a0b-118">Licença do [AD Premium do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium).</span><span class="sxs-lookup"><span data-stu-id="89a0b-118">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) license.</span></span>
-   [<span data-ttu-id="89a0b-119">Atualização do Windows para Criadores</span><span class="sxs-lookup"><span data-stu-id="89a0b-119">Windows Creators Update</span></span>](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> <span data-ttu-id="89a0b-120">O WIP não oferece suporte a várias identidades. Pode haver apenas uma identidade gerenciada de cada vez.</span><span class="sxs-lookup"><span data-stu-id="89a0b-120">WIP does not support multi-identity, only one managed identity can exist at a time.</span></span>

## <span data-ttu-id="89a0b-121">Para adicionar uma política WIP</span><span class="sxs-lookup"><span data-stu-id="89a0b-121">To add a WIP policy</span></span>
<a id="to-add-a-wip-policy" class="xliff"></a>

<span data-ttu-id="89a0b-122">Depois de configurar o Intune em sua organização, você poderá criar uma política específica WIP por meio do [Portal do Azure](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).</span><span class="sxs-lookup"><span data-stu-id="89a0b-122">After you set up Intune in your organization, you can create a WIP-specific policy through the [Azure portal](/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).</span></span>

1.  <span data-ttu-id="89a0b-123">Vá para o **painel de gerenciamento de aplicativos móveis do Intune**, escolha **Todas as Configurações** e, em seguida, escolha **Política de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-123">Go to the **Intune mobile application management dashboard**, choose **All settings**, and then choose **App policy**.</span></span>

2.  <span data-ttu-id="89a0b-124">Na folha **Política de aplicativo**, escolha **Adicionar uma política**, em seguida, insira os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="89a0b-124">In the **App policy** blade, choose **Add a policy**, then enter the following values:</span></span>

    <span data-ttu-id="89a0b-125">a.</span><span class="sxs-lookup"><span data-stu-id="89a0b-125">a.</span></span>  <span data-ttu-id="89a0b-126">**Nome:** digite um nome (obrigatório) para a nova política.</span><span class="sxs-lookup"><span data-stu-id="89a0b-126">**Name:** Type a name (required) for your new policy.</span></span>

    <span data-ttu-id="89a0b-127">b.</span><span class="sxs-lookup"><span data-stu-id="89a0b-127">b.</span></span>  <span data-ttu-id="89a0b-128">**Descrição:** digite uma descrição opcional.</span><span class="sxs-lookup"><span data-stu-id="89a0b-128">**Description:** Type an optional description.</span></span>

    <span data-ttu-id="89a0b-129">c.</span><span class="sxs-lookup"><span data-stu-id="89a0b-129">c.</span></span>  <span data-ttu-id="89a0b-130">**Plataforma:** escolha **Windows 10** como uma plataforma com suporte para a política de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89a0b-130">**Platform:** Choose **Windows 10** as the supported platform for your app protection policy.</span></span>

    <span data-ttu-id="89a0b-131">d.</span><span class="sxs-lookup"><span data-stu-id="89a0b-131">d.</span></span>  <span data-ttu-id="89a0b-132">**Estado do registro:** escolha **Sem registro** como o estado de registro para a política.</span><span class="sxs-lookup"><span data-stu-id="89a0b-132">**Enrollment state:** Choose **Without enrollment** as the enrollment state for your policy.</span></span>

3.  <span data-ttu-id="89a0b-133">Escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-133">Choose **Create**.</span></span> <span data-ttu-id="89a0b-134">A política é criada e aparece na tabela na folha **Política de Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-134">The policy is created and appears in the table on the **App Policy** blade.</span></span>

## <span data-ttu-id="89a0b-135">Para adicionar aplicativos recomendados à sua lista de aplicativos permitidos</span><span class="sxs-lookup"><span data-stu-id="89a0b-135">To add recommended apps to your Allowed apps list</span></span>
<a id="to-add-recommended-apps-to-your-allowed-apps-list" class="xliff"></a>

1.  <span data-ttu-id="89a0b-136">Na folha **Política de aplicativo**, escolha o nome da política e escolha **Aplicativos permitidos** na folha **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-136">From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the **Add a policy** blade.</span></span> <span data-ttu-id="89a0b-137">A folha **Aplicativos permitidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista para esta política de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89a0b-137">The **Allowed apps** blade opens, showing you all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="89a0b-138">Na folha **Aplicativos permitidos**, escolha **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-138">From the **Allowed apps** blade, choose **Add apps**.</span></span> <span data-ttu-id="89a0b-139">A folha **Adicionar aplicativos** é aberta, mostrando todos os aplicativos que fazem parte dessa lista.</span><span class="sxs-lookup"><span data-stu-id="89a0b-139">The **Add apps** blade opens, showing you all apps that are part of this list.</span></span>

3.  <span data-ttu-id="89a0b-140">Selecione cada aplicativo que você deseja que acesse seus dados corporativos e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-140">Select each app you want to access your corporate data, and then choose **OK**.</span></span> <span data-ttu-id="89a0b-141">A folha **Aplicativos permitidos** é atualizada, mostrando todos os aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="89a0b-141">The **Allowed apps** blade gets updated showing you all selected apps.</span></span>

## <span data-ttu-id="89a0b-142">Adicionar um aplicativo da Store à sua lista de aplicativos permitidos</span><span class="sxs-lookup"><span data-stu-id="89a0b-142">Add a Store app to your Allowed apps list</span></span>
<a id="add-a-store-app-to-your-allowed-apps-list" class="xliff"></a>

<span data-ttu-id="89a0b-143">**Para adicionar um aplicativo da Store**</span><span class="sxs-lookup"><span data-stu-id="89a0b-143">**To add a Store app**</span></span>

1.  <span data-ttu-id="89a0b-144">Na folha **Política de aplicativo**, escolha o nome da política e escolha **Aplicativos permitidos** no menu que aparece mostrando todos os aplicativos que já estão incluídos na lista para esta política de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89a0b-144">From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the menu that appears showing all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="89a0b-145">Na folha **Aplicativos permitidos**, escolha **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-145">From the **Allowed apps** blade, choose **Add apps**.</span></span>

3.  <span data-ttu-id="89a0b-146">Na folha **Adicionar aplicativos**, escolha **Aplicativos da Store** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="89a0b-146">On the **Add apps** blade, choose **Store apps** from the dropdown list.</span></span> <span data-ttu-id="89a0b-147">A folha é alterada para mostrar caixas para você adicionar um **editor** e um **nome** de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89a0b-147">The blade changes to show boxes for you to add a **publisher** and app **name**.</span></span>

4.  <span data-ttu-id="89a0b-148">Digite o nome do aplicativo e o nome do editor e, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-148">Type the name of the app and the name of its publisher, and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="89a0b-149">Veja um exemplo de aplicativo, onde o **Editor** é *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* e o **nome** do produto é *Microsoft.MicrosoftAppForWindows*.</span><span class="sxs-lookup"><span data-stu-id="89a0b-149">Here’s an app example, where the **Publisher** is *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* and the Product **name** is *Microsoft.MicrosoftAppForWindows*.</span></span>

5.  <span data-ttu-id="89a0b-150">Depois de inserir as informações nos campos, escolha **OK** para adicionar o aplicativo a sua lista de **Aplicativos permitidos**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-150">After you’ve entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.</span></span>

> [!NOTE]
> <span data-ttu-id="89a0b-151">Para adicionar vários aplicativos da Store ao mesmo tempo, clique no menu **(...)**  no final da linha de aplicativo, em seguida, continue a adicionar mais aplicativos.</span><span class="sxs-lookup"><span data-stu-id="89a0b-151">To add multiple Store apps at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps.</span></span> <span data-ttu-id="89a0b-152">Quando terminar, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-152">Once you’re done, choose **OK**.</span></span>

## <span data-ttu-id="89a0b-153">Adicionar um aplicativo da Área de Trabalho à sua lista de aplicativos permitidos</span><span class="sxs-lookup"><span data-stu-id="89a0b-153">Add a Desktop app to your Allowed apps list</span></span>
<a id="add-a-desktop-app-to-your-allowed-apps-list" class="xliff"></a>

<span data-ttu-id="89a0b-154">**Para adicionar um aplicativo da Área de Trabalho**</span><span class="sxs-lookup"><span data-stu-id="89a0b-154">**To add a Desktop app**</span></span>

1.  <span data-ttu-id="89a0b-155">Na folha **Política de aplicativo**, escolha o nome da política e escolha **Aplicativos permitidos.**</span><span class="sxs-lookup"><span data-stu-id="89a0b-155">From the **App policy** blade, choose the name of your policy, and then choose **Allowed apps.**</span></span> <span data-ttu-id="89a0b-156">A folha **Aplicativos permitidos** é aberta, mostrando todos os aplicativos que já estão incluídos na lista para esta política de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89a0b-156">The **Allowed apps** blade opens showing you all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="89a0b-157">Na folha **Aplicativos permitidos**, escolha **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-157">From the **Allowed apps** blade, choose **Add apps**.</span></span>

3.  <span data-ttu-id="89a0b-158">Na folha **Adicionar aplicativos**, escolha **Aplicativos da Área de Trabalho** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="89a0b-158">On the **Add apps** blade, choose **Desktop apps** from the drop-down list.</span></span>

4.  <span data-ttu-id="89a0b-159">Depois de inserir as informações nos campos, escolha **OK** para adicionar o aplicativo a sua lista de **Aplicativos permitidos**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-159">After you entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.</span></span>

> [!NOTE]
> <span data-ttu-id="89a0b-160">Para adicionar vários **aplicativos da Área de Trabalho** ao mesmo tempo, clique no menu **(…)** no final da linha de aplicativo, em seguida, continue a adicionar mais aplicativos.</span><span class="sxs-lookup"><span data-stu-id="89a0b-160">To add multiple **Desktop apps** at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps.</span></span> <span data-ttu-id="89a0b-161">Quando terminar, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-161">Once you’re done, choose **OK**.</span></span>

## <span data-ttu-id="89a0b-162">Aprendizado de WIP (Proteção de Informações do Windows)</span><span class="sxs-lookup"><span data-stu-id="89a0b-162">Windows Information Protection (WIP) Learning</span></span>
<a id="windows-information-protection-wip-learning" class="xliff"></a>

<span data-ttu-id="89a0b-163">Depois de adicionar os aplicativos que deseja proteger com WIP, você precisará aplicar um modo de proteção por meio de **Aprendizado de WIP**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-163">After you add the apps you want to protect with WIP, you need to apply a protection mode by using **WIP Learning**.</span></span>

### <span data-ttu-id="89a0b-164">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="89a0b-164">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="89a0b-165">O aprendizado de WIP (Proteção de Informações do Windows) é um relatório que permite que os administradores monitorem seus aplicativos desconhecidos de WIP.</span><span class="sxs-lookup"><span data-stu-id="89a0b-165">Windows Information Protection (WIP) Learning is a report that allows admins to monitor their WIP unknown apps.</span></span> <span data-ttu-id="89a0b-166">Os aplicativos desconhecidos são aqueles que não são implantados pelo departamento de TI da sua organização.</span><span class="sxs-lookup"><span data-stu-id="89a0b-166">The unknown apps are the ones not deployed by your organization’s IT department.</span></span> <span data-ttu-id="89a0b-167">O administrador pode exportar esses aplicativos do relatório e adicioná-los a suas políticas de WIP para evitar a interrupção de produtividade antes de imporem o WIP no modo "Ocultar Substituições".</span><span class="sxs-lookup"><span data-stu-id="89a0b-167">The admin can export these apps from the report and add them to their WIP policies to avoid productivity disruption before they enforce WIP in “Hide Override” mode.</span></span>

<span data-ttu-id="89a0b-168">Recomendamos que você inicie com **Silencioso** ou **Permitir Substituições** durante a verificação com um pequeno grupo que você tenha os aplicativos certos em sua lista de aplicativos permitidos.</span><span class="sxs-lookup"><span data-stu-id="89a0b-168">We recommend that you start with **Silent** or **Allow Overrides** while verifying with a small group that you have the right apps on your allowed apps list.</span></span> <span data-ttu-id="89a0b-169">Depois de terminar, você poderá alterar sua política de imposição final, **Ocultar Substituições**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-169">After you're done, you can change to your final enforcement policy, **Hide Overrides**.</span></span>

#### <span data-ttu-id="89a0b-170">Quais são os modos de proteção?</span><span class="sxs-lookup"><span data-stu-id="89a0b-170">What the protection modes are?</span></span>
<a id="what-the-protection-modes-are" class="xliff"></a>

- <span data-ttu-id="89a0b-171">**Ocultar Substituições:**</span><span class="sxs-lookup"><span data-stu-id="89a0b-171">**Hide Overrides:**</span></span>
    - <span data-ttu-id="89a0b-172">O WIP procura práticas inadequadas de compartilhamento de dados e impede que o usuário conclua a ação.</span><span class="sxs-lookup"><span data-stu-id="89a0b-172">WIP looks for inappropriate data sharing practices and stops the user from completing the action.</span></span>
    - <span data-ttu-id="89a0b-173">Isso pode incluir compartilhar informações entre aplicativos protegidos não corporativos e compartilhar dados corporativos entre outras pessoas e dispositivos fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="89a0b-173">This can include sharing info across non-corporate-protected apps, and sharing corporate data between other people and devices outside of your organization.</span></span>
<br></br>

- <span data-ttu-id="89a0b-174">**Permitir Substituições:**</span><span class="sxs-lookup"><span data-stu-id="89a0b-174">**Allow Overrides:**</span></span>
    - <span data-ttu-id="89a0b-175">O WIP procura compartilhamento inadequado de dados, avisando os usuários se eles fizerem algo considerado potencialmente não seguro.</span><span class="sxs-lookup"><span data-stu-id="89a0b-175">WIP looks for inappropriate data sharing, warning users if they do something deemed potentially unsafe.</span></span>
    - <span data-ttu-id="89a0b-176">No entanto, esse modo permite que o usuário substitua a política e compartilhe os dados, registrando a ação no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="89a0b-176">However, this mode lets the user override the policy and share the data, logging the action to your audit log.</span></span>
<br></br>
- <span data-ttu-id="89a0b-177">**Silencioso:**</span><span class="sxs-lookup"><span data-stu-id="89a0b-177">**Silent:**</span></span>
    - <span data-ttu-id="89a0b-178">O WIP é executado silenciosamente, registrando em log o compartilhamento inadequado de dados, sem bloquear nada que tenha solicitado a interação do funcionário enquanto estava no modo Permitir Substituições.</span><span class="sxs-lookup"><span data-stu-id="89a0b-178">WIP runs silently, logging inappropriate data sharing, without blocking anything that would’ve been prompted for employee interaction while in Allow Override mode.</span></span>
    - <span data-ttu-id="89a0b-179">As ações não permitidas, como aplicativos tentando acessar indevidamente um recurso de rede ou dados protegidos por WIP, ainda são interrompidas.</span><span class="sxs-lookup"><span data-stu-id="89a0b-179">Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.</span></span>
<br></br>
- <span data-ttu-id="89a0b-180">**Desligado (não recomendado):**</span><span class="sxs-lookup"><span data-stu-id="89a0b-180">**Off (not recommended):**</span></span>
    - <span data-ttu-id="89a0b-181">O WIP é desativado e não ajuda a proteger ou auditar seus dados.</span><span class="sxs-lookup"><span data-stu-id="89a0b-181">WIP is turned off and doesn't help to protect or audit your data.</span></span>
    - <span data-ttu-id="89a0b-182">Depois de desativar o WIP, é feita uma tentativa de descriptografar arquivos marcados por WIP nas unidades conectadas localmente.</span><span class="sxs-lookup"><span data-stu-id="89a0b-182">After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives.</span></span> <span data-ttu-id="89a0b-183">Lembre-se de que suas informações anteriores de política e a descriptografia não serão reaplicadas automaticamente se você ativar novamente a proteção de WIP.</span><span class="sxs-lookup"><span data-stu-id="89a0b-183">Be aware that your previous decryption and policy info isn’t automatically reapplied if you turn WIP protection back on.</span></span>

### <span data-ttu-id="89a0b-184">Para adicionar um modo de proteção</span><span class="sxs-lookup"><span data-stu-id="89a0b-184">To add a protection mode</span></span>
<a id="to-add-a-protection-mode" class="xliff"></a>

1.  <span data-ttu-id="89a0b-185">Na folha **Política de aplicativo**, escolha o nome da política e clique em **Configurações necessárias** na folha **Adicionar Política**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-185">From the **App policy** blade, choose the name of your policy, then click **Required settings** from the **Add Policy** blade.</span></span>

    ![Captura de tela do modo de aprendizado](../media/AppManagement/learning-mode-sc1.png)

1.  <span data-ttu-id="89a0b-187">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-187">Choose **Save**.</span></span>

### <span data-ttu-id="89a0b-188">Para usar o aprendizado de WIP</span><span class="sxs-lookup"><span data-stu-id="89a0b-188">To use WIP Learning</span></span>
<a id="to-use-wip-learning" class="xliff"></a>

1. <span data-ttu-id="89a0b-189">Vá até o painel do Azure.</span><span class="sxs-lookup"><span data-stu-id="89a0b-189">Go to the Azure Dashboard.</span></span>

2. <span data-ttu-id="89a0b-190">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="89a0b-190">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="89a0b-191">Escolha **Intune**, o **painel do Intune** é aberto, escolha **Aplicativos Móveis**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-191">Choose **Intune**, the **Intune dashboard** opens, choose **Mobile Apps**.</span></span>

4. <span data-ttu-id="89a0b-192">Escolha **Aprendizado de WIP** na seção **Monitor**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-192">Choose **WIP Learning** under **Monitor** section.</span></span> <span data-ttu-id="89a0b-193">Você verá os aplicativos desconhecidos registrados pelo Aprendizado de WIP.</span><span class="sxs-lookup"><span data-stu-id="89a0b-193">You see the unknown apps logged by the WIP Learning.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89a0b-194">Quando os aplicativos estiverem aparecendo no relatório de log do Aprendizado de WIP, você poderá inseri-los em suas políticas de proteção do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="89a0b-194">Once you have the apps showing up in the WIP Learning logging report, you can them into your app protection policies.</span></span>

## <span data-ttu-id="89a0b-195">Para implantar sua política de proteção de aplicativo WIP</span><span class="sxs-lookup"><span data-stu-id="89a0b-195">To deploy your WIP app protection policy</span></span>
<a id="to-deploy-your-wip-app-protection-policy" class="xliff"></a>

> [!IMPORTANT]
> <span data-ttu-id="89a0b-196">Isso se aplica a WIP com gerenciamento de aplicativos móveis (MAM) sem o cenário de registro.</span><span class="sxs-lookup"><span data-stu-id="89a0b-196">This applies for WIP with mobile application management (MAM) without enrollment scenario.</span></span>

<span data-ttu-id="89a0b-197">Depois que você tiver criado a política de proteção de aplicativo WIP, precisará implantá-la em sua organização usando MAM.</span><span class="sxs-lookup"><span data-stu-id="89a0b-197">After you created your WIP app protection policy, you need to deploy it to your organization using MAM.</span></span>

1.  <span data-ttu-id="89a0b-198">Na folha **Política de aplicativo**, escolha a política de proteção de aplicativo recém-criada, escolha **Grupos de usuários**, em seguida, escolha **Adicionar grupo de usuários**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-198">On the **App policy** blade, choose your newly-created app protection policy, choose **User groups**, then choose **Add user group**.</span></span>

    <span data-ttu-id="89a0b-199">Uma lista de grupos de usuários é aberta, composta por todos os grupos de segurança no Azure Active Directory, na folha **Adicionar grupo de usuários**.</span><span class="sxs-lookup"><span data-stu-id="89a0b-199">A list of user groups, made up of all the security groups in your Azure Active Directory, opens in the **Add user group** blade.</span></span>

1.  <span data-ttu-id="89a0b-200">Escolha o grupo ao qual você quer que sua política se aplique e clique em **Selecionar** para implantar a política.</span><span class="sxs-lookup"><span data-stu-id="89a0b-200">Choose the group you want your policy to apply to, then click **Select** to deploy the policy.</span></span>
