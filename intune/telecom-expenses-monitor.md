---
title: "Configurar um serviço de gestão de despesas de telecomunicações"
titleSuffix: Intune on Azure
description: "Configure o serviço de gerenciamento de despesas de telecomunicações da Saaswedo para integração com o Intune."
keywords: Saaswedo
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fe3735afccb30da9ea863943808e7cfad667899f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="2e581-104">Configurar um serviço de gerenciamento de despesas de telecomunicações no Intune</span><span class="sxs-lookup"><span data-stu-id="2e581-104">Set up a telecom expense management service in Intune</span></span>
<a id="set-up-a-telecom-expense-management-service-in-intune" class="xliff"></a>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="2e581-105">O Intune permite que você gerencie as despesas de telecomunicações decorrentes da utilização de dados em dispositivos móveis corporativos.</span><span class="sxs-lookup"><span data-stu-id="2e581-105">Intune enables you to manage telecom expenses incurred from data usage on corporate-owned mobile devices.</span></span> <span data-ttu-id="2e581-106">Para permitir este recurso, o Intune integrou-se à solução de gerenciamento de despesas de telecomunicações Datalert da desenvolvedora de software Saaswedo.</span><span class="sxs-lookup"><span data-stu-id="2e581-106">To enable this capability, Intune has integrated with the third-party software developer Saaswedo’s Datalert telecom expense management solution.</span></span> <span data-ttu-id="2e581-107">O Datalert é um software de gerenciamento de despesas de telecomunicações em tempo real que permite que você gerencie o uso de dados de telecomunicações e evitar excedentes de dados móveis e roaming inesperados e dispendiosos para os dispositivos gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="2e581-107">Datalert is real-time telecom expense management software that lets you manage telecom data usage and avoid costly and unexpected data and roaming overages for your Intune-managed devices.</span></span>

<span data-ttu-id="2e581-108">A integração do Intune com o Datalert permite definir, monitorar centralmente e impor limites de uso de dados de roaming e doméstico usando alertas automatizados quando excederem os limites definidos.</span><span class="sxs-lookup"><span data-stu-id="2e581-108">Intune's integration with Datalert enables you to centrally set, monitor and enforce roaming and domestic data usage limits by using automated alerts when the limits exceed defined thresholds.</span></span> <span data-ttu-id="2e581-109">Você pode configurar o serviço para aplicar diferentes ações a indivíduos ou grupos de usuários finais, incluindo desabilitar roaming quando os usuários excederem o limite.</span><span class="sxs-lookup"><span data-stu-id="2e581-109">You can configure the service to apply different actions to individuals or groups of end users, including disabling roaming, when users exceed the threshold.</span></span> <span data-ttu-id="2e581-110">Relatórios que fornecem o uso de dados e informações de monitoramento estão disponíveis no console de gerenciamento Datalert.</span><span class="sxs-lookup"><span data-stu-id="2e581-110">Reports that provide data usage and monitoring information are available from the Datalert management console.</span></span>

<span data-ttu-id="2e581-111">O diagrama a seguir mostra como o Intune se integra ao Datalert.</span><span class="sxs-lookup"><span data-stu-id="2e581-111">The following diagram shows how Intune integrates with Datalert.</span></span>

  ![Diagrama de integração do Intune e Datalert](./media/tem-datalert-intune-solution-diagram.png)

<span data-ttu-id="2e581-113">Antes de usar o serviço de Datalert com o Intune, você precisa definir as configurações no console de Datalert e no Intune.</span><span class="sxs-lookup"><span data-stu-id="2e581-113">Before you can use the Datalert service with Intune, you need to configure settings in the Datalert console and in Intune.</span></span> <span data-ttu-id="2e581-114">A conexão deve estar ativada para o serviço Datalert e para o Intune.</span><span class="sxs-lookup"><span data-stu-id="2e581-114">The connection must be turned on for the Datalert service and for Intune.</span></span> <span data-ttu-id="2e581-115">Se o lado do Datalert da conexão estiver habilitado, mas não o lado do Intune, o Intune receberá a comunicação, mas a ignorará.</span><span class="sxs-lookup"><span data-stu-id="2e581-115">If the Datalert side of the connection is enabled, but not the Intune side, Intune receives the communication, but ignores it.</span></span>

## <span data-ttu-id="2e581-116">Plataformas com suporte</span><span class="sxs-lookup"><span data-stu-id="2e581-116">Supported platforms</span></span>
<a id="supported-platforms" class="xliff"></a>

- <span data-ttu-id="2e581-117">Samsung Knox</span><span class="sxs-lookup"><span data-stu-id="2e581-117">Samsung Knox</span></span>
- <span data-ttu-id="2e581-118">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="2e581-118">iOS 8.0 and later</span></span>

## <span data-ttu-id="2e581-119">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2e581-119">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

- <span data-ttu-id="2e581-120">Uma assinatura do Microsoft Intune e acesso ao portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="2e581-120">A subscription to Microsoft Intune, and access to the Azure portal.</span></span>
- <span data-ttu-id="2e581-121">Uma assinatura para o serviço de gerenciamento de despesas de telecomunicações do Datalert</span><span class="sxs-lookup"><span data-stu-id="2e581-121">A subscription to the Datalert telecom expense management service</span></span>

## <span data-ttu-id="2e581-122">Lista de provedores de gerenciamento de despesas de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="2e581-122">List of telecom expense management providers</span></span>
<a id="list-of-telecom-expense-management-providers" class="xliff"></a>

<span data-ttu-id="2e581-123">O Intune atualmente se integra com os seguintes provedores de gerenciamento de despesas de telecomunicações:</span><span class="sxs-lookup"><span data-stu-id="2e581-123">Intune currently integrates with the following telecom expense management providers:</span></span>

[<span data-ttu-id="2e581-124">Serviço de gerenciamento de despesas de telecomunicações do Saaswedo Datalert</span><span class="sxs-lookup"><span data-stu-id="2e581-124">Saaswedo Datalert telecom expense management service</span></span>](http://www.datalert.biz/)

## <span data-ttu-id="2e581-125">Implantar a solução integrada do Intune e Datalert</span><span class="sxs-lookup"><span data-stu-id="2e581-125">Deploy the Intune and Datalert integrated solution</span></span>
<a id="deploy-the-intune-and-datalert-integrated-solution" class="xliff"></a>

<span data-ttu-id="2e581-126">Antes de começar, verifique se você já possui uma assinatura do Intune e do serviço de gerenciamento de gastos de telecomunicações do Datalert.</span><span class="sxs-lookup"><span data-stu-id="2e581-126">Before you start, make sure that you already have an Intune and a Datalert telecom expense management service subscription.</span></span>

### <span data-ttu-id="2e581-127">Etapa 1: conectar o serviço Datalert ao Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="2e581-127">Step 1: Connect the Datalert service to Microsoft Intune</span></span>
<a id="step-1-connect-the-datalert-service-to-microsoft-intune" class="xliff"></a>

1. <span data-ttu-id="2e581-128">Entre no console de gerenciamento Datalert com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="2e581-128">Sign into the Datalert management console with your administrator credentials.</span></span>

2. <span data-ttu-id="2e581-129">No console de gerenciamento Datalert, vá para a guia **Configurações** e, em seguida, **Configuração MDM**.</span><span class="sxs-lookup"><span data-stu-id="2e581-129">On the Datalert management console, go to the **Settings** tab, and then to **MDM configuration**.</span></span>

3. <span data-ttu-id="2e581-130">Selecione **Desbloquear** para permitir que você insira as configurações na página.</span><span class="sxs-lookup"><span data-stu-id="2e581-130">Select **Unblock** to enable you to enter the settings on the page.</span></span>

4. <span data-ttu-id="2e581-131">Para **Servidor MDM**, escolha **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="2e581-131">For **Server MDM**, choose **Microsoft Intune**.</span></span>

5. <span data-ttu-id="2e581-132">Para **domínio do Azure AD**, insira sua ID de locatário do Azure e, em seguida, selecione o botão **Conexão**.</span><span class="sxs-lookup"><span data-stu-id="2e581-132">For **Azure AD domain**, enter your Azure tenant ID, and then select the **Connection** button.</span></span>

    <span data-ttu-id="2e581-133">Selecionar **Conexão** faz o serviço do Datalert verificar com o Intune se não existem conexões Datalert já existentes com o Intune.</span><span class="sxs-lookup"><span data-stu-id="2e581-133">Selecting **Connection** makes the Datalert service check in with Intune to ensure that there are no pre-existing Datalert connections with Intune.</span></span> <span data-ttu-id="2e581-134">Depois de alguns segundos, uma página de logon do Microsoft aparecerá, seguida da autenticação do Datalert Azure.</span><span class="sxs-lookup"><span data-stu-id="2e581-134">After a few seconds, a Microsoft log-in page appears, followed by the Datalert Azure authentication.</span></span>

6. <span data-ttu-id="2e581-135">Na página de autenticação da Microsoft, selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="2e581-135">On the Microsoft authentication page, select **Accept**.</span></span> <span data-ttu-id="2e581-136">Você será redirecionado para uma página de agradecimento, que se fecha depois de alguns segundos.</span><span class="sxs-lookup"><span data-stu-id="2e581-136">You are redirected to a Datalert “thank you” page, which closes after a few seconds.</span></span> <span data-ttu-id="2e581-137">O Datalert valida a conexão e exibe marcas de seleção verde ao lado de uma lista de itens validados.</span><span class="sxs-lookup"><span data-stu-id="2e581-137">Datalert validates the connection, and displays green check marks beside a list of items that it validated.</span></span> <span data-ttu-id="2e581-138">Se a validação falhar, você verá uma mensagem vermelha.</span><span class="sxs-lookup"><span data-stu-id="2e581-138">If the validation fails, you see a message in red.</span></span> <span data-ttu-id="2e581-139">Nesse caso, contate o suporte de Datalert para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="2e581-139">If this happens, contact Datalert Support for help.</span></span>

    <span data-ttu-id="2e581-140">A captura de tela a seguir mostra as marcas de seleção verde que você pode esperar encontrar quando a conexão for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="2e581-140">The following screenshot shows the green check marks that you can expect to see once the connection is successful.</span></span>

  ![Página do Datalert mostrando a conexão bem-sucedida](./media/tem-mdm-configuration-mdm-server-page.png)

### <span data-ttu-id="2e581-142">Etapa 2: verificar se o recurso de gerenciamento de despesas de telecomunicações está ativo no Intune</span><span class="sxs-lookup"><span data-stu-id="2e581-142">Step 2: Check that the telecom expense management feature is Active in Intune</span></span>
<a id="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune" class="xliff"></a>

<span data-ttu-id="2e581-143">Depois de concluir a etapa 1 acima, a conexão deverá ser habilitada automaticamente e o status de conexão **Ativo** deverá aparecer no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="2e581-143">After you complete Step 1 above, your connection should be automatically enabled, and a connection status of **Active** should be showing in the Azure portal.</span></span> <span data-ttu-id="2e581-144">Estas etapas mostram como verificar o status **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="2e581-144">These steps show you how to check for the **Active** status.</span></span>

1. <span data-ttu-id="2e581-145">Entre no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="2e581-145">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="2e581-146">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="2e581-146">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

3. <span data-ttu-id="2e581-147">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="2e581-147">On the **Intune** blade, choose **Device configuration**.</span></span>

4. <span data-ttu-id="2e581-148">Na folha **Configuração do Dispositivo**, escolha **Instalação** > **Gerenciamento de Despesas de Telecomunicações**.</span><span class="sxs-lookup"><span data-stu-id="2e581-148">On the **Device Configuration** blade, choose **Setup** > **Telecom Expense Management**.</span></span>

   <span data-ttu-id="2e581-149">Procure o status de conexão **Ativo** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="2e581-149">Look for the **Active** connection status at the top of the page.</span></span>

  ![Portal do Azure mostrando o status de conexão do Datalert ativo](./media/tem-azure-portal-enable-service.png)

### <span data-ttu-id="2e581-151">Etapa 3: implantar o aplicativo Datalert em dispositivos corporativos registrados</span><span class="sxs-lookup"><span data-stu-id="2e581-151">Step 3: Deploy the Datalert app to corporate enrolled devices</span></span>
<a id="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices" class="xliff"></a>

<span data-ttu-id="2e581-152">Para garantir que o uso de dados somente de linhas de propriedade corporativas seja coletado, é necessário criar categorias de dispositivo no Intune e, em seguida, direcionar o aplicativo Datalert apenas para telefones corporativos.</span><span class="sxs-lookup"><span data-stu-id="2e581-152">To ensure that data usage from only corporate-owned lines is collected, you need to create device categories in Intune, and then target the Datalert app to only corporate phones.</span></span> <span data-ttu-id="2e581-153">Conclua as etapas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="2e581-153">Complete the steps in the following subsections.</span></span>

#### <span data-ttu-id="2e581-154">Definir grupos e categorias de dispositivos mapeados para as categorias</span><span class="sxs-lookup"><span data-stu-id="2e581-154">Define device categories and device groups mapped to the categories</span></span>
<a id="define-device-categories-and-device-groups-mapped-to-the-categories" class="xliff"></a>

<span data-ttu-id="2e581-155">Dependendo das suas necessidades organizacionais, você precisará criar ao menos duas categorias de dispositivos (por exemplo, Corporativo e Pessoal) e criar grupos de dispositivos dinâmicos para cada categoria.</span><span class="sxs-lookup"><span data-stu-id="2e581-155">Depending on your organizational needs, you'll need to create at least two device categories (for example, Corporate and Personal) and create dynamic device groups for each category.</span></span> <span data-ttu-id="2e581-156">Você pode criar mais categorias para sua organização, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2e581-156">You can create more categories for your organization, as needed.</span></span>

<span data-ttu-id="2e581-157">Essas categorias serão mostradas aos usuários durante o registro.</span><span class="sxs-lookup"><span data-stu-id="2e581-157">These categories will be shown to users during enrollment.</span></span> <span data-ttu-id="2e581-158">Dependendo de qual categoria o usuário escolher, o dispositivo registrado será movido para o grupo de dispositivo correspondente.</span><span class="sxs-lookup"><span data-stu-id="2e581-158">Depending on which category users choose, the enrolled device will be moved to the corresponding device group.</span></span> <span data-ttu-id="2e581-159">Para obter etapas sobre como criar categorias de dispositivos, consulte [Mapear dispositivos para grupos](device-group-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="2e581-159">For steps on how to create device categories, see [Map devices to groups](device-group-mapping.md).</span></span>

  ![Captura de tela da folha Adicionar uma política](./media/tem-dynamic-membership-rules.png)

#### <span data-ttu-id="2e581-161">Criar o aplicativo Datalert no Intune</span><span class="sxs-lookup"><span data-stu-id="2e581-161">Create the Datalert app in Intune</span></span>
<a id="create-the-datalert-app-in-intune" class="xliff"></a>

<span data-ttu-id="2e581-162">Siga estas etapas para criar o aplicativo Datalert no Intune para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="2e581-162">Follow these steps to create the Datalert app in Intune for each platform.</span></span> <span data-ttu-id="2e581-163">O iOS é usado como um exemplo nessas etapas.</span><span class="sxs-lookup"><span data-stu-id="2e581-163">iOS is used as an example in these steps.</span></span>

1. <span data-ttu-id="2e581-164">Na folha **Intune** do portal do Azure, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="2e581-164">On the **Intune** blade of the Azure portal, choose **Mobile apps**.</span></span>

2. <span data-ttu-id="2e581-165">Na folha **Aplicativos móveis**, escolha **Gerenciar** > **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2e581-165">On the **Mobile apps** blade, choose **Manage** > **Apps**.</span></span>

3. <span data-ttu-id="2e581-166">Selecione **Adicionar** para adicionar um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2e581-166">Select **Add** to add an app.</span></span>

4. <span data-ttu-id="2e581-167">Selecione o tipo de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2e581-167">Select the app type.</span></span> <span data-ttu-id="2e581-168">Por exemplo, para iOS, você selecionaria **iOS App Store**.</span><span class="sxs-lookup"><span data-stu-id="2e581-168">For example, for iOS, you would select **iOS Store App**.</span></span>

5. <span data-ttu-id="2e581-169">Em **Pesquisar na App Store**, procure o aplicativo Datalert digitando **Datalert** na janela de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="2e581-169">In **Search the App Store**, look for the Datalert app by typing **Datalert** in the search window.</span></span>

6. <span data-ttu-id="2e581-170">Selecione o aplicativo **Datalert** e selecione **Ok**.</span><span class="sxs-lookup"><span data-stu-id="2e581-170">Select the **Datalert** app, and select **OK**.</span></span>

  ![Captura de tela da folha Adicionar uma política](./media/tem-select-app-from-apple-app-store.png)

7. <span data-ttu-id="2e581-172">Conclua as etapas restantes para criar um aplicativo para iOS.</span><span class="sxs-lookup"><span data-stu-id="2e581-172">Complete the remaining steps to create an app for iOS.</span></span>

  ![Captura de tela da folha Adicionar uma política](./media/tem-steps-to-create-the-app.png)

#### <span data-ttu-id="2e581-174">Atribuir o aplicativo Datalert ao grupo de dispositivos corporativos</span><span class="sxs-lookup"><span data-stu-id="2e581-174">Assign the Datalert app to the corporate device group</span></span>
<a id="assign-the-datalert-app-to-the-corporate-device-group" class="xliff"></a>

1. <span data-ttu-id="2e581-175">Selecione o aplicativo Datalert para iOS que você criou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="2e581-175">Select the iOS Datalert app that you created in the previous step.</span></span>

2. <span data-ttu-id="2e581-176">Na folha **Aplicativos**, vá para **Gerenciar** > **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="2e581-176">On the **Apps** blade, go to **Manage** > **Assignments**.</span></span>

3. <span data-ttu-id="2e581-177">Escolha **Selecionar grupos** e siga as etapas para selecionar o grupo de dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="2e581-177">Choose **Select groups**, and follow the steps to select the corporate device group.</span></span>

4. <span data-ttu-id="2e581-178">Escolha se deseja tornar a instalação do aplicativo obrigatória ou opcional para o grupo.</span><span class="sxs-lookup"><span data-stu-id="2e581-178">Choose whether to make the app installation required or optional for the group.</span></span> <span data-ttu-id="2e581-179">A captura de tela de exemplo a seguir mostra a instalação conforme necessário, o que significa que os usuários devem instalar o aplicativo Datalert depois de registrar seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2e581-179">The following example screenshot shows the installation as required, which means that users must install the Datalert app installation after enrolling their device.</span></span>

  ![Captura de tela da folha Adicionar uma política](./media/tem-assign-datalert-app-to-device-group.png)

### <span data-ttu-id="2e581-181">Etapa 4: adicionar linhas telefônicas pagas corporativas ao console do Datalert</span><span class="sxs-lookup"><span data-stu-id="2e581-181">Step 4: Add corporate paid phone lines to the Datalert console</span></span>
<a id="step-4-add-corporate-paid-phone-lines-to-the-datalert-console" class="xliff"></a>

<span data-ttu-id="2e581-182">Agora você configurou os serviços Intune e Datalert para se comunicar entre si.</span><span class="sxs-lookup"><span data-stu-id="2e581-182">You now have configured the Intune and Datalert services to communicate with each other.</span></span> <span data-ttu-id="2e581-183">Você agora precisa adicionar linhas telefônicas pagas corporativas ao console do Datalert e definir limites e ações para qualquer violação de uso de dados celulares ou roaming.</span><span class="sxs-lookup"><span data-stu-id="2e581-183">You now need to add your corporate paid phone lines to the Datalert console and define thresholds and actions for any cellular or roaming usage violations.</span></span> <span data-ttu-id="2e581-184">Você pode adicionar manualmente linhas telefônicas corporativas pagas ao console do Datalert ou adicioná-las automaticamente após o registro do dispositivo no Intune.</span><span class="sxs-lookup"><span data-stu-id="2e581-184">You can either add corporate paid phone lines to the Datalert console manually or have the lines added automatically after the device is enrolled into Intune.</span></span>

<span data-ttu-id="2e581-185">Para definir esses itens, vá para [Configuração do Datalert para a página do Microsoft Intune](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup) e siga as etapas no assistente de instalação na guia **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="2e581-185">To set these items, go to the [Datalert setup for Microsoft Intune page](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup), and follow the steps in the setup wizard under the **Settings** tab.</span></span>

  ![Captura de tela da folha Adicionar uma política](./media/tem-add-phone-lines-to-datalert-console.png)


<span data-ttu-id="2e581-187">O serviço Datalert agora estará ativo e começará a monitorar o uso de dados e a desabilitar os dados em roaming em dispositivos que excederam os limites de uso configurados.</span><span class="sxs-lookup"><span data-stu-id="2e581-187">The Datalert service is now active, and it starts monitoring data usage and disabling cellular and roaming data on devices that exceed the configured usage limits.</span></span>

## <span data-ttu-id="2e581-188">Experiência de registro do cliente</span><span class="sxs-lookup"><span data-stu-id="2e581-188">Client enrollment experience</span></span>
<a id="client-enrollment-experience" class="xliff"></a>
<span data-ttu-id="2e581-189">Para a experiência de registro de cliente, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2e581-189">For client enrollment experience see following:</span></span>
-   [<span data-ttu-id="2e581-190">Registrar seu dispositivo iOS no gerenciamento de despesas de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="2e581-190">Enroll your iOS device in telecom expense management</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [<span data-ttu-id="2e581-191">Registrar seu dispositivo Android no gerenciamento de despesas de telecomunicações</span><span class="sxs-lookup"><span data-stu-id="2e581-191">Enroll your Android device in telecom expense management</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <span data-ttu-id="2e581-192">Desativar o serviço Datalert</span><span class="sxs-lookup"><span data-stu-id="2e581-192">Turning off the Datalert service</span></span>
<a id="turning-off-the-datalert-service" class="xliff"></a>

<span data-ttu-id="2e581-193">Se você desabilitar o serviço Datalert no Portal do Azure:</span><span class="sxs-lookup"><span data-stu-id="2e581-193">If you disable the Datalert service in the Azure portal:</span></span>

- <span data-ttu-id="2e581-194">Todas as ações que foram aplicadas aos dispositivos devido a violações passadas dos limites de uso serão desfeitas.</span><span class="sxs-lookup"><span data-stu-id="2e581-194">All of the actions that have been applied to devices, due to past violations of the usage limits, are undone.</span></span>
- <span data-ttu-id="2e581-195">Os usuários não são impedidos de acessar os dados e roaming.</span><span class="sxs-lookup"><span data-stu-id="2e581-195">Users are no longer blocked from data access and roaming.</span></span>
- <span data-ttu-id="2e581-196">O Intune ainda recebe os sinais proveniente do serviço, mas os ignora.</span><span class="sxs-lookup"><span data-stu-id="2e581-196">Intune still receives the signals coming from the service, but ignores them.</span></span>

<span data-ttu-id="2e581-197">**Para desligar o serviço**</span><span class="sxs-lookup"><span data-stu-id="2e581-197">**To turn off the service**</span></span>

1. <span data-ttu-id="2e581-198">Na folha **Gerenciamento de Despesas de Telecomunicações** no Portal do Azure, selecione **Desabilitar**.</span><span class="sxs-lookup"><span data-stu-id="2e581-198">On the **Telecom Expense Management** blade in the Azure portal, select **Disable**.</span></span>

2. <span data-ttu-id="2e581-199">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2e581-199">Select **Save**.</span></span>

## <span data-ttu-id="2e581-200">Exibindo o uso de dados e relatórios de roaming</span><span class="sxs-lookup"><span data-stu-id="2e581-200">Viewing data usage and roaming reports</span></span>
<a id="viewing-data-usage-and-roaming-reports" class="xliff"></a>

<span data-ttu-id="2e581-201">No momento, os relatórios de dados de uso estão disponíveis somente no console de gerenciamento do Saaswedo Datalert.</span><span class="sxs-lookup"><span data-stu-id="2e581-201">At this time, data usage reporting is available only in Saaswedo’s Datalert management console.</span></span>

<span data-ttu-id="2e581-202">As instruções que os usuários finais seguem para instalar o aplicativo Datalert serão adicionadas em breve.</span><span class="sxs-lookup"><span data-stu-id="2e581-202">The instructions that your end users follow to install the Datalert app will be added soon.</span></span>
