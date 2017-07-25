---
title: "Registrar dispositivos iOS com o Assistente de Configuração"
description: "Registre dispositivos iOS corporativos usando a ferramenta Apple Configurator para redefinir o dispositivo para as configurações de fábrica e prepará-lo para executar o Assistente de Configuração."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 402b5b469b1536e9f2ea13948e45c9232baca458
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="52485-103">Registrar dispositivos iOS com o Apple Configurator usando o Assistente de Configuração</span><span class="sxs-lookup"><span data-stu-id="52485-103">Enroll iOS devices with Apple Configurator by using Setup Assistant</span></span>
<a id="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="52485-104">O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="52485-104">Intune supports the enrollment of corporate-owned iOS devices using [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) running on a Mac computer.</span></span> <span data-ttu-id="52485-105">Esse processo redefine o dispositivo para as configurações de fábrica e o prepara para executar o Assistente de Configuração instalando as políticas da empresa para o novo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52485-105">This process resets the device to factory settings and prepares it to run Setup Assistant, installing the company's policies for the device’s new user.</span></span>

>[!NOTE]
><span data-ttu-id="52485-106">Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="52485-106">This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

<span data-ttu-id="52485-107">Usando o Apple Configurator, você pode redefinir um dispositivo iOS para as configurações de fábrica e prepará-lo para ser configurado para o novo usuário do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52485-107">Using Apple Configurator, you can reset an iOS device to factory settings and prepare it to be set up for the device’s new user.</span></span> <span data-ttu-id="52485-108">Esse método requer que você conecte o dispositivo iOS a um computador Mac via USB para configurar o registro corporativo e supõe que você esteja usando o Apple Configurator 2.0.</span><span class="sxs-lookup"><span data-stu-id="52485-108">This method requires you to connect the iOS device to a Mac computer via USB to set up corporate enrollment, and it assumes you are using Apple Configurator 2.0.</span></span> <span data-ttu-id="52485-109">A maioria dos cenários exige que a política aplicada ao dispositivo iOS inclua **afinidade do usuário** para habilitar o aplicativo Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="52485-109">Most scenarios require that the policy applied to the iOS device include **user affinity** to enable the Intune Company Portal app.</span></span>

## <span data-ttu-id="52485-110">Pré-requisitos para registro de dispositivos iOS usando o Apple Configurator com o Assistente de Configuração</span><span class="sxs-lookup"><span data-stu-id="52485-110">Prerequisites for enrolling iOS devices by using Apple Configurator with Setup Assistant</span></span>
<a id="prerequisites-for-enrolling-ios-devices-by-using-apple-configurator-with-setup-assistant" class="xliff"></a>

- [<span data-ttu-id="52485-111">Instalar um certificado APNs</span><span class="sxs-lookup"><span data-stu-id="52485-111">Install an APNs certificate</span></span>](set-up-ios-and-mac-management-with-microsoft-intune.md)

- <span data-ttu-id="52485-112">Certifique-se de que você tem acesso físico a dispositivos iOS&mdash;os dispositivos devem ser redefinidos para as configurações de fábrica, sem proteção de senha</span><span class="sxs-lookup"><span data-stu-id="52485-112">Ensure that you have physical access to iOS devices&mdash;devices must be reset to factory settings without password protection</span></span>

- <span data-ttu-id="52485-113">Obter números de série do dispositivo, &mdash;consulte [Como obter um número de série do iOS](https://support.apple.com/HT204308)</span><span class="sxs-lookup"><span data-stu-id="52485-113">Get device serial numbers&mdash;see [How to get an iOS serial number](https://support.apple.com/HT204308)</span></span>

- <span data-ttu-id="52485-114">Ter em mãos os cabos de conexão USB</span><span class="sxs-lookup"><span data-stu-id="52485-114">Have USB connection cables on hand</span></span>

- <span data-ttu-id="52485-115">Ter um computador Mac com o [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)</span><span class="sxs-lookup"><span data-stu-id="52485-115">Have a Mac computer with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)</span></span>


## <span data-ttu-id="52485-116">Etapas para registro de dispositivos iOS usando o Apple Configurator com o Assistente de Configuração</span><span class="sxs-lookup"><span data-stu-id="52485-116">Steps to enroll iOS devices by using Apple Configurator with Setup Assistant</span></span>
<a id="steps-to-enroll-ios-devices-by-using-apple-configurator-with-setup-assistant" class="xliff"></a>

<span data-ttu-id="52485-117">As etapas a seguir explicam como registrar dispositivos iOS no "dia 0" usando o Apple Configurator com o Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="52485-117">The following steps explain how to enroll iOS devices on "day 0" by using Apple Configurator with Setup Assistant.</span></span> <span data-ttu-id="52485-118">Conforme os dispositivos forem adicionados e removidos da sua organização, você provavelmente repetirá algumas dessas etapas como adicionar ou remover números de série, conforme descrito abaixo.</span><span class="sxs-lookup"><span data-stu-id="52485-118">As devices are added and removed from your organization, you will likely repeat some of these steps, such as adding or removing serial numbers, as described below.</span></span>

### <span data-ttu-id="52485-119">Criar grupos de dispositivos móveis (opcional)</span><span class="sxs-lookup"><span data-stu-id="52485-119">Create mobile device groups (optional)</span></span>
<a id="create-mobile-device-groups-optional" class="xliff"></a>

<span data-ttu-id="52485-120">Se sua empresa exige grupos de dispositivos móveis para ajudar a gerenciar dispositivos, você pode opcionalmente criar esses grupos.</span><span class="sxs-lookup"><span data-stu-id="52485-120">If your business requires mobile device groups to help manage devices, you can optionally create those groups.</span></span> <span data-ttu-id="52485-121">Para saber mais, consulte [Usar grupos para gerenciar usuários e dispositivos com o Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="52485-121">To learn more, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

### <span data-ttu-id="52485-122">Criar um perfil para dispositivos</span><span class="sxs-lookup"><span data-stu-id="52485-122">Create a profile for devices</span></span>
<a id="create-a-profile-for-devices" class="xliff"></a>

<span data-ttu-id="52485-123">Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52485-123">A device enrollment profile defines the settings applied to a group of devices.</span></span>

1. <span data-ttu-id="52485-124">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="52485-124">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

  ![Criar perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

2. <span data-ttu-id="52485-126">Insira os detalhes para os perfis de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="52485-126">Enter details for the device profiles:</span></span>

   -   <span data-ttu-id="52485-127">**Nome**&mdash;O nome do perfil de registro do dispositivo (não é visível para os usuários).</span><span class="sxs-lookup"><span data-stu-id="52485-127">**Name**&mdash;The name of the device enrollment profile (not visible to users).</span></span>

   -   <span data-ttu-id="52485-128">**Descrição**&mdash;Uma descrição do perfil de registro do dispositivo (não é visível para os usuários).</span><span class="sxs-lookup"><span data-stu-id="52485-128">**Description**&mdash;A description of the device enrollment profile (not visible to users).</span></span>

   -   <span data-ttu-id="52485-129">**Detalhes de Registro**&mdash;Especifica como os dispositivos são registrados.</span><span class="sxs-lookup"><span data-stu-id="52485-129">**Enrollment Details**&mdash;Specifies how devices are enrolled.</span></span>

       -   <span data-ttu-id="52485-130">**Solicitar afinidade do usuário**&mdash;O dispositivo deve ser afiliado a um usuário durante a configuração inicial e, depois, pode receber permissão para acessar dados e email da empresa.</span><span class="sxs-lookup"><span data-stu-id="52485-130">**Prompt for user affinity**&mdash;The device must be affiliated with a user during initial setup and can then be permitted to access company data and email.</span></span> <span data-ttu-id="52485-131">A **afinidade do usuário** deve ser configurada para dispositivos gerenciados que pertencem a usuários e que precisam usar o portal da empresa para serviços como instalar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="52485-131">**User affinity** should be set up for managed devices that belong to users and need to use the company portal for services like installing apps.</span></span>

       -   <span data-ttu-id="52485-132">**Sem afinidade do usuário**&mdash;O dispositivo não está afiliado a um usuário.</span><span class="sxs-lookup"><span data-stu-id="52485-132">**No user affinity**&mdash;The device is not affiliated with a user.</span></span> <span data-ttu-id="52485-133">Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local.</span><span class="sxs-lookup"><span data-stu-id="52485-133">Use this affiliation for devices that perform tasks without accessing local user data.</span></span> <span data-ttu-id="52485-134">Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="52485-134">Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.</span></span>

   -   <span data-ttu-id="52485-135">**Pré-atribuição de grupo de dispositivos**&mdash;Todos os dispositivos implantados nesse perfil pertencerão inicialmente a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="52485-135">**Device group pre-assignment**&mdash;All devices deployed with this profile will initially belong to this group.</span></span> <span data-ttu-id="52485-136">Você pode reatribuir dispositivos após o registro.</span><span class="sxs-lookup"><span data-stu-id="52485-136">You can reassign devices after enrollment.</span></span>

   > [!Important]
   > <span data-ttu-id="52485-137">As atribuições de grupo serão movidas do Intune para o Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52485-137">Group assignments are moving from Intune to Azure Active Directory.</span></span> <span data-ttu-id="52485-138">Depois que sua conta do Intune receber a atualização aplicável, você não verá a opção **Atribuir dispositivos ao grupo a seguir**.</span><span class="sxs-lookup"><span data-stu-id="52485-138">Once your Intune account receives the applicable update, you won't see the **Assign devices to the following group** option.</span></span> <span data-ttu-id="52485-139">[Saiba mais](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="52485-139">[Learn more](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).</span></span>

   -  <span data-ttu-id="52485-140">**Programa de Registro de Dispositivo**&mdash;O DEP (Programa de Registro de Dispositivo) da Apple não pode ser usado com o registro do Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="52485-140">**Device Enrollment Program**&mdash;The Apple Device Enrollment Program (DEP) cannot be used with Setup Assistant enrollment.</span></span> <span data-ttu-id="52485-141">Verifique se a alternância está definida como **desligado**.</span><span class="sxs-lookup"><span data-stu-id="52485-141">Ensure that the toggle is set to **off**.</span></span>

3.  <span data-ttu-id="52485-142">Clique em **Salvar Perfil** para adicionar o perfil.</span><span class="sxs-lookup"><span data-stu-id="52485-142">Choose **Save Profile** to add the profile.</span></span>

### <span data-ttu-id="52485-143">Adicionar dispositivos iOS para registro com o Assistente de Configuração</span><span class="sxs-lookup"><span data-stu-id="52485-143">Add iOS devices to enroll with Setup Assistant</span></span>
<a id="add-ios-devices-to-enroll-with-setup-assistant" class="xliff"></a>

1. <span data-ttu-id="52485-144">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), acesse **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os dispositivos de propriedade corporativa** &gt; **Todos os Dispositivos** e escolha **Adicionar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="52485-144">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices** &gt; **All Devices**, and then choose **Add devices**.</span></span>

   <span data-ttu-id="52485-145">Você pode adicionar dispositivos de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="52485-145">You can add devices in two ways:</span></span>

   ![Caixa de diálogo Adicionar dispositivos](../media/pol-SA-enroll-iOS-SetupAssistant.png)

   -  <span data-ttu-id="52485-147">**Carregar um arquivo CSV contendo números de série**&mdash;Crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, com limite de 5.000 dispositivos ou 5 MB por arquivo csv.</span><span class="sxs-lookup"><span data-stu-id="52485-147">**Upload a CSV file containing serial numbers**&mdash;Create a comma-separated value (.csv) list of two columns without a header, limited to 5,000 devices or 5 MB per .csv file.</span></span>

    |||
    |-|-|
    |<span data-ttu-id="52485-148">&lt;Nº de série 1&gt;</span><span class="sxs-lookup"><span data-stu-id="52485-148">&lt;Serial #1&gt;</span></span>|<span data-ttu-id="52485-149">&lt;Detalhes do dispositivo nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="52485-149">&lt;Device #1 Details&gt;</span></span>|
    |<span data-ttu-id="52485-150">&lt;Nº de série 2&gt;</span><span class="sxs-lookup"><span data-stu-id="52485-150">&lt;Serial#2&gt;</span></span>|<span data-ttu-id="52485-151">&lt;Detalhes do dispositivo nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="52485-151">&lt;Device #2 Details&gt;</span></span>|

  <span data-ttu-id="52485-152">Quando visualizado em um editor de texto, esse arquivo .csv aparece como:</span><span class="sxs-lookup"><span data-stu-id="52485-152">When viewed in a text editor, this .csv file appears as:</span></span>

    ```
    0000000,PO 1234
    111111111,PO 1234
    ```

  -  <span data-ttu-id="52485-153">**Adicionar manualmente os detalhes do dispositivo**&mdash;Insira o número de série e quaisquer observações ou detalhes de até 15 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52485-153">**Manually add device details**&mdash;Enter the serial number and any notes or details for up to 15 devices.</span></span>

  <span data-ttu-id="52485-154">No painel **Examinar Dispositivos**, você pode confirmar os números de série.</span><span class="sxs-lookup"><span data-stu-id="52485-154">On the **Review Devices** pane, you can confirm the serial numbers.</span></span> <span data-ttu-id="52485-155">Você também pode decidir se deseja substituir os **Detalhes** para números de série que estão sendo importados novamente ou você pode desmarcar a caixa **Substituir** para preservar os detalhes atuais.</span><span class="sxs-lookup"><span data-stu-id="52485-155">You can also decide whether to overwrite the **Details** for serial numbers that are being imported again, or you can uncheck the **Overwrite** box to preserve the Current details.</span></span>

  > [!NOTE]
  > <span data-ttu-id="52485-156">No console do administrador do Intune existente, os administradores podem aceitar detalhes associados de um CSV carregado e substituir os detalhes existentes para números de série individuais.</span><span class="sxs-lookup"><span data-stu-id="52485-156">In the existing Intune administrator console, admins can accept associated details from an uploaded CSV and overwrite the existing details for individual serial numbers.</span></span> <span data-ttu-id="52485-157">No novo Portal do Azure, você só poderá substituir os detalhes de todos os números de série ou ignorar os novos detalhes para todos os números de série.</span><span class="sxs-lookup"><span data-stu-id="52485-157">In the new Azure portal, you’ll only be able to overwrite the details for all serial numbers or to ignore new details for all serial numbers.</span></span>

  > [!NOTE]
  > <span data-ttu-id="52485-158">Se, posteriormente, você desejar remover dispositivos corporativos do gerenciamento do Intune, será necessário ir até **Por número de série do iOS** em **Dispositivos corporativos pré-registrados** e remover o número de série do dispositivo do Intune para desabilitar o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52485-158">If you want to remove corporate-owned devices from Intune management later, you might need to go to **By iOS Serial Number** device group under **Corporate Pre-enrolled devices** and remove the device serial number from Intune in order to disable device enrollment.</span></span> <span data-ttu-id="52485-159">Se o Intune executar um procedimento de recuperação de desastre quando ou próximo à época em que você remover os números de série, você precisará confirmar que apenas os números de série de dispositivos ativos estão presentes nesse grupo.</span><span class="sxs-lookup"><span data-stu-id="52485-159">If Intune performs a disaster recovery procedure on or around the time you remove serial numbers, you'll need to verify that only active devices’ serial numbers are present in that group.</span></span>

2. <span data-ttu-id="52485-160">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-160">Choose **Next**.</span></span>

3. <span data-ttu-id="52485-161">Selecione os dispositivos a serem registrados.</span><span class="sxs-lookup"><span data-stu-id="52485-161">Select the devices to enroll.</span></span> <span data-ttu-id="52485-162">Não é possível importar os números de série já registrados ou registrados por outros meios.</span><span class="sxs-lookup"><span data-stu-id="52485-162">Serial numbers already enrolled or enrolled by other means cannot be imported.</span></span> <span data-ttu-id="52485-163">Escolha **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="52485-163">Choose **Next** to continue.</span></span>

### <span data-ttu-id="52485-164">Atribuir um perfil</span><span class="sxs-lookup"><span data-stu-id="52485-164">Assign a profile</span></span>
<a id="assign-a-profile" class="xliff"></a>

<span data-ttu-id="52485-165">Especifique o perfil para atribuir a dispositivos adicionados na lista de perfis disponíveis, examine os **Detalhes do perfil de registro**e escolha **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="52485-165">Specify the profile to assign to added devices from the list of available profiles, review the **Enrollment profile details**, and then choose **Finish**.</span></span> <span data-ttu-id="52485-166">Dispositivos adicionados manualmente podem ser atribuídos a qualquer perfil de registro.</span><span class="sxs-lookup"><span data-stu-id="52485-166">Manually added devices can be assigned to any enrollment profile.</span></span>

> [!Important]
> <span data-ttu-id="52485-167">Atualmente, o Intune permite designar um perfil de registro do dispositivo "padrão", o que significa que novos números de série são automaticamente atribuídos a esse perfil padrão quando você sincroniza os novos números de série com o serviço da Apple.</span><span class="sxs-lookup"><span data-stu-id="52485-167">Currently, Intune let you designate a "default" device enrollment profile," which means that new serial numbers are automatically assigned to that default profile when you synchronize new serial numbers with the Apple service.</span></span> <span data-ttu-id="52485-168">Quando seu locatário for migrado para o novo portal do Azure em um futuro próximo, você não poderá definir um perfil padrão e ter números de série atribuídos automaticamente a esse perfil.</span><span class="sxs-lookup"><span data-stu-id="52485-168">When your tenant is migrated to the new Azure portal in the near future, you will no longer be able to set a default profile and have serial numbers be automatically assigned to that profile.</span></span> <span data-ttu-id="52485-169">Em vez disso, você precisará atribuir números de série a um perfil.</span><span class="sxs-lookup"><span data-stu-id="52485-169">Instead, you will have to assign serial numbers to a profile.</span></span> [<span data-ttu-id="52485-170">Saiba mais</span><span class="sxs-lookup"><span data-stu-id="52485-170">Learn more</span></span>](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <span data-ttu-id="52485-171">Exportar um perfil para ser implantado em dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="52485-171">Export a profile to deploy to iOS devices</span></span>
<a id="export-a-profile-to-deploy-to-ios-devices" class="xliff"></a>

1. <span data-ttu-id="52485-172">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), vá até **Política** &gt; **Registro de Dispositivo Corporativo** e selecione o perfil a ser implantado nos dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="52485-172">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to mobile devices.</span></span>

2. <span data-ttu-id="52485-173">Escolha **Exportar** na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="52485-173">Choose **Export** in the taskbar.</span></span> <span data-ttu-id="52485-174">Copie e salve a **URL do perfil**.</span><span class="sxs-lookup"><span data-stu-id="52485-174">Copy and save the **Profile URL**.</span></span> <span data-ttu-id="52485-175">Você fará o upload no Apple Configurator posteriormente para definir o perfil do Intune utilizado pelos dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="52485-175">You will upload it in Apple Configurator later to define the Intune profile used by iOS devices.</span></span>

   <span data-ttu-id="52485-176">Você carregará essa URL do perfil para o serviço Apple usando o Apple Configurator no procedimento a seguir para definir o perfil do Intune utilizado pelos dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="52485-176">You will upload this profile URL to the Apple service using Apple Configurator in the following procedure to define the Intune profile used by iOS devices.</span></span>

### <span data-ttu-id="52485-177">Preparar o dispositivo com o Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="52485-177">Prepare the device with Apple Configurator</span></span>
<a id="prepare-the-device-with-apple-configurator" class="xliff"></a>

<span data-ttu-id="52485-178">Dispositivos iOS são conectados ao computador Mac e registrados para o gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="52485-178">iOS devices are connected to the Mac computer and enrolled for mobile device management.</span></span>

1.  <span data-ttu-id="52485-179">Em um computador Mac, abra o **Apple Configurator 2**.</span><span class="sxs-lookup"><span data-stu-id="52485-179">On a Mac computer, open **Apple Configurator 2**.</span></span> <span data-ttu-id="52485-180">Na barra de menus, selecione **Apple Configurator 2** e clique em **Preferências**.</span><span class="sxs-lookup"><span data-stu-id="52485-180">In the menu bar, choose **Apple Configurator 2**, and then choose **Preferences**.</span></span>

   > [!WARNING]
   > <span data-ttu-id="52485-181">Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="52485-181">The devices will be reset to factory configurations during the enrollment process.</span></span> <span data-ttu-id="52485-182">Como melhor prática, redefina o dispositivo e ligue-o.</span><span class="sxs-lookup"><span data-stu-id="52485-182">As a best practice, reset the device and turn it on.</span></span> <span data-ttu-id="52485-183">Os dispositivos devem estar na tela **Olá** quando você conectar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52485-183">Devices should be at the **Hello** screen when you connect the device.</span></span>

2. <span data-ttu-id="52485-184">No painel de preferências, selecione **Servidores** e escolha o símbolo de mais (+) para inicializar o assistente do Servidor MDM.</span><span class="sxs-lookup"><span data-stu-id="52485-184">In the preferences pane, select **Servers** and choose the plus symbol (+) to launch the MDM Server wizard.</span></span> <span data-ttu-id="52485-185">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-185">Choose **Next**.</span></span>

3. <span data-ttu-id="52485-186">Insira o **Nome de Host ou a URL** e a **URL do Registro** para o servidor MDM em Registro do Assistente de Configuração para dispositivos iOS com o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="52485-186">Enter the **Hostname or URL** and **enrollment URL** for the MDM server under Setup Assistant enrollment for iOS devices with Microsoft Intune.</span></span> <span data-ttu-id="52485-187">Para URL de Registro, insira a URL do perfil de registro exportada do Intune.</span><span class="sxs-lookup"><span data-stu-id="52485-187">For the Enrollment URL, enter the enrollment profile URL exported from Intune.</span></span> <span data-ttu-id="52485-188">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-188">Choose **Next**.</span></span>  

   <span data-ttu-id="52485-189">Você pode desconsiderar com segurança um aviso indicando "URL do servidor não verificada".</span><span class="sxs-lookup"><span data-stu-id="52485-189">You can safely disregard a warning stating "server URL is not verified."</span></span> <span data-ttu-id="52485-190">Para continuar, clique em **Avançar** até que o assistente seja concluído.</span><span class="sxs-lookup"><span data-stu-id="52485-190">To continue, choose **Next** until the wizard is finished.</span></span>

4.  <span data-ttu-id="52485-191">Conecte os dispositivos móveis iOS ao computador Mac com um adaptador USB.</span><span class="sxs-lookup"><span data-stu-id="52485-191">Connect the iOS mobile devices to the Mac computer with a USB adapter.</span></span>

    > [!WARNING]
    > <span data-ttu-id="52485-192">Os dispositivos serão redefinidos para as configurações de fábrica durante o processo de registro.</span><span class="sxs-lookup"><span data-stu-id="52485-192">The devices will be reset to factory configurations during the enrollment process.</span></span> <span data-ttu-id="52485-193">Como melhor prática, redefina o dispositivo e ligue-o.</span><span class="sxs-lookup"><span data-stu-id="52485-193">As a best practice, reset the device and turn it on.</span></span> <span data-ttu-id="52485-194">Os dispositivos devem estar na tela **Olá** quando você iniciar o Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="52485-194">Devices should be at the **Hello** screen when you start Setup Assistant.</span></span>

5.  <span data-ttu-id="52485-195">Selecione **Preparar**.</span><span class="sxs-lookup"><span data-stu-id="52485-195">Choose **Prepare**.</span></span> <span data-ttu-id="52485-196">No painel Preparar o Dispositivo iOS, selecione **Manual** e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-196">On the Prepare iOS Device pane, select **Manual** and then choose **Next**.</span></span>

6. <span data-ttu-id="52485-197">No painel Registrar no Servidor MDM, selecione o nome do servidor que você criou e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-197">On the Enroll in MDM Server pane, select the server name you created, and then choose **Next**.</span></span>

7. <span data-ttu-id="52485-198">No painel Supervisionar Dispositivos, selecione o nível de supervisão e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-198">On the Supervise Devices pane, select the level of supervision, and then choose **Next**.</span></span>

8. <span data-ttu-id="52485-199">No painel Criar uma Organização, escolha **Organização** ou crie uma nova organização e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="52485-199">On the Create an Organization pane, choose the **Organization** or create a new organization, and then choose **Next**.</span></span>

9. <span data-ttu-id="52485-200">No painel Configurar o Assistente de Instalação do iOS, escolha as etapas que serão apresentadas ao usuário e escolha **Preparar**.</span><span class="sxs-lookup"><span data-stu-id="52485-200">On the Configure iOS Setup Assistant pane, choose the steps to be presented to the user, and then choose **Prepare**.</span></span> <span data-ttu-id="52485-201">Se solicitado, autentique para atualizar as configurações de confiança.</span><span class="sxs-lookup"><span data-stu-id="52485-201">If prompted, authenticate to update trust settings.</span></span>  

10. <span data-ttu-id="52485-202">Quando o dispositivo iOS concluir a preparação, desconecte o cabo USB.</span><span class="sxs-lookup"><span data-stu-id="52485-202">When the iOS device finishes preparing, disconnect the USB cable.</span></span>  

### <span data-ttu-id="52485-203">Distribuir dispositivos</span><span class="sxs-lookup"><span data-stu-id="52485-203">Distribute devices</span></span>
<a id="distribute-devices" class="xliff"></a>

<span data-ttu-id="52485-204">Os dispositivos agora estão prontos para registro corporativo.</span><span class="sxs-lookup"><span data-stu-id="52485-204">The devices are now ready for corporate enrollment.</span></span> <span data-ttu-id="52485-205">Desligue os dispositivos e distribua-os para os usuários.</span><span class="sxs-lookup"><span data-stu-id="52485-205">Turn off the devices and distribute them to users.</span></span> <span data-ttu-id="52485-206">Quando os usuários ligarem seus dispositivos, o Assistente de Configuração será iniciado.</span><span class="sxs-lookup"><span data-stu-id="52485-206">When users turn on their devices, Setup Assistant will start.</span></span>



### <span data-ttu-id="52485-207">Consulte também</span><span class="sxs-lookup"><span data-stu-id="52485-207">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="52485-208">Pré-requisitos para registrar dispositivos</span><span class="sxs-lookup"><span data-stu-id="52485-208">Prerequisites for enrolling devices</span></span>](prerequisites-for-enrollment.md)
