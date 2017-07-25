---
title: "<span data-ttu-id=\"b55a6-101\">Usar políticas de configuração de aplicativo do Intune para o Android for Work</span><span class=\"sxs-lookup\"><span data-stu-id=\"b55a6-101\">Use Intune app configuration policies for Android for Work</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"b55a6-102\">Saiba como usar políticas de configuração de aplicativo para fornecer dados de configuração para um aplicativo Android for Work quando ele é executado.</span><span class=\"sxs-lookup\"><span data-stu-id=\"b55a6-102\">Learn how to use app configuration policies to provide configuration data to an Android for Work app when it is run.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b86d2d7f4d295ed41168c9dfdbaf8d4c253a0f75
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="how-to-use-microsoft-intune-app-configuration-policies-for-android-for-work"></a><span data-ttu-id="b55a6-103">Como usar as políticas de configuração de aplicativo do Microsoft Intune no Android for Work</span><span class="sxs-lookup"><span data-stu-id="b55a6-103">How to use Microsoft Intune app configuration policies for Android for Work</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="b55a6-104">Use as políticas de configuração de aplicativo do Microsoft Intune para fornecer as configurações que podem estar disponíveis quando os usuários executam um aplicativo Android for Work.</span><span class="sxs-lookup"><span data-stu-id="b55a6-104">Use app configuration policies in Microsoft Intune to supply settings that might be available when users run an Android for Work app.</span></span> <span data-ttu-id="b55a6-105">Nem todos os aplicativos dão suporte à configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b55a6-105">Not all apps support app configuration.</span></span> <span data-ttu-id="b55a6-106">Verifique com o desenvolvedor do aplicativo se ele criou o aplicativo para dar suporte a políticas de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b55a6-106">Check with the app’s developer to see whether or not they have built their app to support app configuration policies.</span></span>

<span data-ttu-id="b55a6-107">As políticas de configuração de aplicativo podem ajudá-lo a predefinir as configurações de aplicativo disponíveis para os usuários antes que eles executem o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b55a6-107">App configuration policies can help you pre-configure available app settings for your users before they run the app.</span></span> <span data-ttu-id="b55a6-108">Alguns aplicativos Android dão suporte a opções de configurações gerenciadas que podem ser definidas no console do Intune com o [designer de configuração](#use-configuration-designer).</span><span class="sxs-lookup"><span data-stu-id="b55a6-108">Some Android apps support managed configurations options that you can configure in the Intune console with the [configuration designer](#use-configuration-designer).</span></span> <span data-ttu-id="b55a6-109">Algumas definições de configuração em aplicativos (como aquelas com os tipos Pacote) não podem ser configuradas com o designer de configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-109">Some configuration settings on apps (such as those with Bundle types) cannot be configured with the configuration designer.</span></span>  <span data-ttu-id="b55a6-110">Você precisará usar o [editor de JSON](#use-json-editor) para esses valores.</span><span class="sxs-lookup"><span data-stu-id="b55a6-110">You will need to use the [JSON editor](#use-json-editor) for those values.</span></span>   <span data-ttu-id="b55a6-111">As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.</span><span class="sxs-lookup"><span data-stu-id="b55a6-111">Settings are supplied to apps automatically when the app is installed.</span></span>

<span data-ttu-id="b55a6-112">Você não atribui essas políticas diretamente para usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b55a6-112">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="b55a6-113">Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b55a6-113">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="b55a6-114">As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.</span><span class="sxs-lookup"><span data-stu-id="b55a6-114">The policy settings is used when the app checks for them, typically the first time it is run).</span></span>

## <a name="use-configuration-designer"></a><span data-ttu-id="b55a6-115">Usar o designer de configuração</span><span class="sxs-lookup"><span data-stu-id="b55a6-115">Use configuration designer</span></span>

1. <span data-ttu-id="b55a6-116">No portal do Intune, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-116">In the Intune portal, choose **Mobile apps**.</span></span> <span data-ttu-id="b55a6-117">Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-117">Under **Manage**, choose **App configuration policies** and then click **Add**.</span></span>
2. <span data-ttu-id="b55a6-118">Defina os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b55a6-118">Set the following details:</span></span>
    - <span data-ttu-id="b55a6-119">**Nome** – o nome do perfil que será exibido no console do Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-119">**Name** - The name of the profile that will appear in the Intune console</span></span>
    - <span data-ttu-id="b55a6-120">**Descrição** – a descrição do perfil que será exibida no console do Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-120">**Description** - The  description of the profile that will appear in the Intune console</span></span>
    - <span data-ttu-id="b55a6-121">**Plataforma** – selecione **Android**</span><span class="sxs-lookup"><span data-stu-id="b55a6-121">**Platform** - Select **Android**</span></span>
    - <span data-ttu-id="b55a6-122">A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.</span><span class="sxs-lookup"><span data-stu-id="b55a6-122">**Device enrollment type** - **Enrolled with Intune** is pre-selected for you.</span></span>
3. <span data-ttu-id="b55a6-123">Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-123">Select **Associated App** to choose the app for which you want to define a configuration policy.</span></span>  <span data-ttu-id="b55a6-124">Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-124">Select from the list of Android for Work apps that you have approved and synchronized with Intune</span></span>
4. <span data-ttu-id="b55a6-125">Selecione **Definições de configuração**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-125">Select **Configuration settings**.</span></span>
5. <span data-ttu-id="b55a6-126">Em **Formato de definições de configuração**, selecione **Usar o designer de configuração**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-126">For **Configuration settings format**, select **Use configuration designer**.</span></span>
6. <span data-ttu-id="b55a6-127">Escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-127">Choose **Add**.</span></span> <span data-ttu-id="b55a6-128">Uma lista das definições de configuração disponíveis é exibida.</span><span class="sxs-lookup"><span data-stu-id="b55a6-128">A list of  available configuration settings is displayed.</span></span> <span data-ttu-id="b55a6-129">A lista inclui:</span><span class="sxs-lookup"><span data-stu-id="b55a6-129">The list includes:</span></span>
    - <span data-ttu-id="b55a6-130">**Chaves de configuração** – nome da configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-130">**Configuration keys** - Name of the setting.</span></span>
    - <span data-ttu-id="b55a6-131">**Tipo de valor** – a configuração que pode ser definida, por exemplo, **Booliano** ou **Cadeia de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-131">**Value type** - The setting that can be configured, for example **Boolean** or **String**.</span></span>
    - <span data-ttu-id="b55a6-132">**Descrição** – uma descrição da definição de configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-132">**Description** - A description of the configuration setting.</span></span>
7. <span data-ttu-id="b55a6-133">Marque as caixas de seleção das configurações que você deseja definir com esse perfil e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-133">Select the checkboxes of settings you want to configure with this profile, and then click **OK**.</span></span>
8. <span data-ttu-id="b55a6-134">É exibida uma lista das configurações selecionadas com o **Valor de configuração** disponível.</span><span class="sxs-lookup"><span data-stu-id="b55a6-134">A list of your selected settings is displayed with the available **Configuration value**.</span></span> <span data-ttu-id="b55a6-135">Especifique um valor para cada configuração e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-135">Specify a value for each setting, and then click **OK**.</span></span>

## <a name="use-json-editor"></a><span data-ttu-id="b55a6-136">Usar o editor de JSON</span><span class="sxs-lookup"><span data-stu-id="b55a6-136">Use JSON editor</span></span>

1. <span data-ttu-id="b55a6-137">No portal do Intune, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-137">In the Intune portal, choose **Mobile apps**.</span></span> <span data-ttu-id="b55a6-138">Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-138">Under **Manage**, choose **App configuration policies** and then click **Add**.</span></span>
2. <span data-ttu-id="b55a6-139">Defina os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b55a6-139">Set the following details:</span></span>
    - <span data-ttu-id="b55a6-140">**Nome** – o nome do perfil que será exibido no console do Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-140">**Name** - The name of the profile that will appear in the Intune console</span></span>
    - <span data-ttu-id="b55a6-141">**Descrição** – a descrição do perfil que será exibida no console do Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-141">**Description** - The  description of the profile that will appear in the Intune console</span></span>
    - <span data-ttu-id="b55a6-142">**Plataforma** – selecione **Android**</span><span class="sxs-lookup"><span data-stu-id="b55a6-142">**Platform** - Select **Android**</span></span>
    - <span data-ttu-id="b55a6-143">A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.</span><span class="sxs-lookup"><span data-stu-id="b55a6-143">**Device enrollment type** - **Enrolled with Intune** is pre-selected for you.</span></span>
3. <span data-ttu-id="b55a6-144">Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-144">Select **Associated App** to choose the app for which you want to define a configuration policy.</span></span>  <span data-ttu-id="b55a6-145">Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b55a6-145">Select from the list of Android for Work apps that you have approved and synchronized with Intune.</span></span>
5. <span data-ttu-id="b55a6-146">Selecione **Definições de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-146">Select **Configuration Settings**.</span></span>
6. <span data-ttu-id="b55a6-147">Em **Formato de definições de configuração**, selecione **Inserir editor de JSON**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-147">For **Configuration settings format**, select **Enter JSON editor**.</span></span>
7. <span data-ttu-id="b55a6-148">No editor, é possível definir os valores JSON para as definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-148">In the editor you can define JSON values for configuration settings.</span></span> <span data-ttu-id="b55a6-149">Escolha **Baixar modelo de JSON** para baixar um arquivo de exemplo que, em seguida, pode ser configurado.</span><span class="sxs-lookup"><span data-stu-id="b55a6-149">You can choose **Download JSON template** to download a sample file that you can then configure.</span></span>
8. <span data-ttu-id="b55a6-150">Quando terminar, escolha **OK** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-150">When you're done, choose **OK** and then click **Add**.</span></span>

<span data-ttu-id="b55a6-151">A política será criada e aparecerá na folha da lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="b55a6-151">The policy will be created and appears on the policies list blade.</span></span>



<span data-ttu-id="b55a6-152">Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b55a6-152">When the assigned app is run on a device, it will run with the settings that you configured in the app configuration policy.</span></span>

## <a name="preconfigure-permissions-grant-state-for-apps"></a><span data-ttu-id="b55a6-153">Pré-configurar o estado de concessão de permissões para aplicativos</span><span class="sxs-lookup"><span data-stu-id="b55a6-153">Preconfigure permissions grant state for apps</span></span>

<span data-ttu-id="b55a6-154">Você também pode pré-configurar a permissão para que os aplicativos acessem os recursos do dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="b55a6-154">You can also preconfigure permission for apps to access Android device features.</span></span> <span data-ttu-id="b55a6-155">Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso à localização ou à câmera do dispositivo solicitam que os usuários aceite ou negue as permissões.</span><span class="sxs-lookup"><span data-stu-id="b55a6-155">By default, Android apps that require device permissions such as access to location or the device camera prompt users to accept or deny permissions.</span></span> <span data-ttu-id="b55a6-156">Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final deverá conceder a permissão de aplicativo para usar o microfone.</span><span class="sxs-lookup"><span data-stu-id="b55a6-156">For example, if an app uses the device's microphone then the end user is prompted to grant the app permission to use the microphone.</span></span>

1. <span data-ttu-id="b55a6-157">No portal do Intune, escolha **Aplicativos móveis**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-157">In the Intune portal, choose **Mobile apps**.</span></span> <span data-ttu-id="b55a6-158">Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-158">Under **Manage**, choose **App configuration policies** and then click **Add**.</span></span>
2. <span data-ttu-id="b55a6-159">Defina os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b55a6-159">Set the following details:</span></span>
    - <span data-ttu-id="b55a6-160">**Nome** – o nome do perfil que será exibido no console do Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-160">**Name** - The name of the profile that will appear in the Intune console</span></span>
    - <span data-ttu-id="b55a6-161">**Descrição** – a descrição do perfil que será exibida no console do Intune</span><span class="sxs-lookup"><span data-stu-id="b55a6-161">**Description** - The  description of the profile that will appear in the Intune console</span></span>
    - <span data-ttu-id="b55a6-162">**Plataforma** – selecione **Android**</span><span class="sxs-lookup"><span data-stu-id="b55a6-162">**Platform** - Select **Android**</span></span>
    - <span data-ttu-id="b55a6-163">A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.</span><span class="sxs-lookup"><span data-stu-id="b55a6-163">**Device enrollment type** - **Enrolled with Intune** is pre-selected for you.</span></span>
3. <span data-ttu-id="b55a6-164">Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.</span><span class="sxs-lookup"><span data-stu-id="b55a6-164">Select **Associated App** to choose the app for which you want to define a configuration policy.</span></span>  <span data-ttu-id="b55a6-165">Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.</span><span class="sxs-lookup"><span data-stu-id="b55a6-165">Select from the list of Android for Work apps that you have approved and synchronized with Intune.</span></span>
5. <span data-ttu-id="b55a6-166">Selecione **Permissões** e, em seguida, escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-166">Select **Permissions** and then choose **Add**.</span></span>
6. <span data-ttu-id="b55a6-167">Selecione na lista de permissões de aplicativo disponíveis e, em seguida, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-167">Select from the list of available app permissions and then choose **OK**.</span></span>
7. <span data-ttu-id="b55a6-168">Selecione uma opção para cada permissão a ser concedida com esta política:</span><span class="sxs-lookup"><span data-stu-id="b55a6-168">Select an option for each permission to grant with this policy:</span></span>
    - <span data-ttu-id="b55a6-169">**Prompt** – solicite que o usuário aceite ou negue.</span><span class="sxs-lookup"><span data-stu-id="b55a6-169">**Prompt** - Prompt the user to accept or deny.</span></span>
    - <span data-ttu-id="b55a6-170">**Concessão automática** – aprove automaticamente sem notificar o usuário.</span><span class="sxs-lookup"><span data-stu-id="b55a6-170">**Auto grant** - Automatically approve without notifying the user.</span></span>
    - <span data-ttu-id="b55a6-171">**Negação automática** – negue automaticamente sem notificar o usuário.</span><span class="sxs-lookup"><span data-stu-id="b55a6-171">**Auto deny** - Automatically deny without notifying the user.</span></span>
8. <span data-ttu-id="b55a6-172">Para atribuir a política de configuração de aplicativo, selecione a política de configuração de aplicativo, selecione **Atribuição** e, em seguida, selecione **Selecionar grupos**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-172">To assign the app configuration policy, select the app configuration policy, select **Assignment**, and then select **Select groups**.</span></span>
9. <span data-ttu-id="b55a6-173">Selecione os grupos de usuários a serem atribuídos e, em seguida, escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b55a6-173">Select the user groups to assign, and then choose **Select**.</span></span>
10. <span data-ttu-id="b55a6-174">Escolha **Salvar** para atribuir a política.</span><span class="sxs-lookup"><span data-stu-id="b55a6-174">Choose **Save** to assign the policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b55a6-175">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b55a6-175">Next steps</span></span>

<span data-ttu-id="b55a6-176">Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.</span><span class="sxs-lookup"><span data-stu-id="b55a6-176">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>
=======
Use as políticas de configuração de aplicativo do Microsoft Intune para fornecer as configurações que podem estar disponíveis quando os usuários executam um aplicativo Android for Work. Nem todos os aplicativos dão suporte à configuração de aplicativo. Verifique com o desenvolvedor do aplicativo se ele criou o aplicativo para dar suporte a políticas de configuração de aplicativo.

As políticas de configuração de aplicativo podem ajudá-lo a predefinir as configurações de aplicativo disponíveis para os usuários antes que eles executem o aplicativo. Alguns aplicativos Android dão suporte a opções de configurações gerenciadas que podem ser definidas no console do Intune com o [designer de configuração](#use-configuration-designer). Algumas definições de configuração em aplicativos (como aquelas com os tipos Pacote) não podem ser configuradas com o designer de configuração.  Você precisará usar o [editor de JSON](#use-json-editor) para esses valores.   As configurações são fornecidas para os aplicativos automaticamente quando o aplicativo é instalado.

Você não atribui essas políticas diretamente para usuários e dispositivos. Em vez disso, você associa uma política a um aplicativo e atribui o aplicativo. As configurações de política são usadas quando o aplicativo as verifica, normalmente, na primeira vez em que ele é executado.

## <a name="use-configuration-designer"></a>Usar o designer de configuração

1. No portal do Intune, escolha **Aplicativos móveis**. Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.
2. Defina os seguintes detalhes:
    - **Nome** – o nome do perfil que será exibido no console do Intune
    - **Descrição** – a descrição do perfil que será exibida no console do Intune
    - **Plataforma** – selecione **Android**
    - A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.
3. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.  Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune
4. Selecione **Definições de configuração**.
5. Em **Formato de definições de configuração**, selecione **Usar o designer de configuração**.
6. Escolha **Adicionar**. Uma lista das definições de configuração disponíveis é exibida. A lista inclui:
    - **Chaves de configuração** – nome da configuração.
    - **Tipo de valor** – a configuração que pode ser definida, por exemplo, **Booliano** ou **Cadeia de caracteres**.
    - **Descrição** – uma descrição da definição de configuração.
7. Marque as caixas de seleção das configurações que você deseja definir com esse perfil e, em seguida, clique em **OK**.
8. É exibida uma lista das configurações selecionadas com o **Valor de configuração** disponível. Especifique um valor para cada configuração e, em seguida, clique em **OK**.

## <a name="use-json-editor"></a>Usar o editor de JSON

1. No portal do Intune, escolha **Aplicativos móveis**. Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.
2. Defina os seguintes detalhes:
    - **Nome** – o nome do perfil que será exibido no console do Intune
    - **Descrição** – a descrição do perfil que será exibida no console do Intune
    - **Plataforma** – selecione **Android**
    - A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.
3. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.  Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.
5. Selecione **Definições de Configuração**.
6. Em **Formato de definições de configuração**, selecione **Inserir editor de JSON**.
7. No editor, é possível definir os valores JSON para as definições de configuração. Escolha **Baixar modelo de JSON** para baixar um arquivo de exemplo que, em seguida, pode ser configurado.
8. Quando terminar, escolha **OK** e, em seguida, clique em **Adicionar**.

A política será criada e aparecerá na folha da lista de políticas.



Quando o aplicativo atribuído é executado em um dispositivo, ele é executado com as configurações definidas na política de configuração do aplicativo.

## <a name="preconfigure-permissions-grant-state-for-apps"></a>Pré-configurar o estado de concessão de permissões para aplicativos

Você também pode pré-configurar a permissão para que os aplicativos acessem os recursos do dispositivo Android. Por padrão, os aplicativos Android que exigem permissões de dispositivo como o acesso à localização ou à câmera do dispositivo solicitam que os usuários aceite ou negue as permissões. Por exemplo, se um aplicativo usar o microfone do dispositivo, o usuário final deverá conceder a permissão de aplicativo para usar o microfone.

1. No portal do Intune, escolha **Aplicativos móveis**. Em **Gerenciar**, escolha **Políticas de configuração de aplicativo** e, em seguida, clique em **Adicionar**.
2. Defina os seguintes detalhes:
    - **Nome** – o nome do perfil que será exibido no console do Intune
    - **Descrição** – a descrição do perfil que será exibida no console do Intune
    - **Plataforma** – selecione **Android**
    - A opção **Tipo de registro de dispositivo** - **Registrado no Intune** é pré-selecionada para você.
3. Selecione **Aplicativo Associado** para escolher o aplicativo para o qual você deseja definir uma política de configuração.  Selecione na lista de aplicativos Android for Work que foram aprovados e sincronizados com o Intune.
5. Selecione **Permissões** e, em seguida, escolha **Adicionar**.
6. Selecione na lista de permissões de aplicativo disponíveis e, em seguida, escolha **OK**.
7. Selecione uma opção para cada permissão a ser concedida com esta política:
    - **Prompt** – solicite que o usuário aceite ou negue.
    - **Concessão automática** – aprove automaticamente sem notificar o usuário.
    - **Negação automática** – negue automaticamente sem notificar o usuário.
8. Para atribuir a política de configuração de aplicativo, selecione a política de configuração de aplicativo, selecione **Atribuição** e, em seguida, selecione **Selecionar grupos**.
9. Selecione os grupos de usuários a serem atribuídos e, em seguida, escolha **Selecionar**.
10. Escolha **Salvar** para atribuir a política.

## <a name="next-steps"></a>Próximas etapas

Continue a [atribuir](apps-deploy.md) e a [monitorar](apps-monitor.md) o aplicativo como de costume.
>>>>>>> live

