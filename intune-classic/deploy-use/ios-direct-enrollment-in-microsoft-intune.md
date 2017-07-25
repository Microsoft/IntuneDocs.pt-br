---
title: Registro direto para dispositivos iOS
description: "Use a Apple Configurator Tool para registrar diretamente dispositivos iOS corporativos com uma política predefinida conectando-os por USB a um computador Mac."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9909e1dd4f9891a2efb47383242ed7765d3f0291
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="e1984-103">Registrar dispositivos iOS diretamente usando o Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="e1984-103">Directly enroll iOS devices by using Apple Configurator</span></span>
<a id="directly-enroll-ios-devices-by-using-apple-configurator" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e1984-104">O Intune dá suporte ao registro de dispositivos iOS corporativos usando a ferramenta [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) em execução em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="e1984-104">Intune supports the enrollment of corporate-owned iOS devices by using the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.</span></span> <span data-ttu-id="e1984-105">Esse processo não restaura as configurações de fábrica do dispositivo e registra o dispositivo com uma política predefinida.</span><span class="sxs-lookup"><span data-stu-id="e1984-105">This process does not factory-reset the device and enrolls the device with a predefined policy.</span></span> <span data-ttu-id="e1984-106">Esse método é para dispositivos **Sem afinidade de usuário** e requer que você conecte por USB o dispositivo iOS a um computador Mac para configurar o registro corporativo.</span><span class="sxs-lookup"><span data-stu-id="e1984-106">This method is for devices with **No user affinity** and requires you to USB-connect the iOS device to a Mac computer to set up corporate enrollment.</span></span>

<span data-ttu-id="e1984-107">Ao registrar dispositivos iOS diretamente, você pode registrar um dispositivo sem adquirir o número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1984-107">When you're directly enrolling iOS devices, you can enroll a device without acquiring the device's serial number.</span></span> <span data-ttu-id="e1984-108">Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro.</span><span class="sxs-lookup"><span data-stu-id="e1984-108">You can also name the device for identification purposes before Intune captures the device name during enrollment.</span></span> <span data-ttu-id="e1984-109">Não há suporte para o aplicativo de Portal da Empresa para dispositivos registrados diretamente.</span><span class="sxs-lookup"><span data-stu-id="e1984-109">The Company Portal app is not supported for directly enrolled devices.</span></span> <span data-ttu-id="e1984-110">Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="e1984-110">This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.</span></span>

>[!NOTE]
><span data-ttu-id="e1984-111">Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="e1984-111">This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

1.  <span data-ttu-id="e1984-112">Se ainda não tiver feito isso, crie um perfil de registro para dispositivos iOS registrados usando o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="e1984-112">If you haven't already, create a device enrollment profile for iOS devices enrolled through Apple Configurator.</span></span> <span data-ttu-id="e1984-113">Um perfil de registro do dispositivo define as configurações aplicadas a dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e1984-113">A device enrollment profile defines the settings applied to devices.</span></span>

    1.  <span data-ttu-id="e1984-114">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), acesse **Política** &gt; **Registro do Dispositivo Corporativo** e escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1984-114">In the [Microsoft Intune administration console](https://manage.microsoft.com) go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

        ![Criar página de perfil de registro do dispositivo](../media/pol-sa-corp-enroll.png)

    2.  <span data-ttu-id="e1984-116">Insira os detalhes para os perfis de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="e1984-116">Enter details for the device profiles:</span></span>

        -   <span data-ttu-id="e1984-117">**Nome**: nome do perfil de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1984-117">**Name**: Name of the device enrollment profile.</span></span> <span data-ttu-id="e1984-118">Não é visível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="e1984-118">Not visible to users.</span></span>

        -   <span data-ttu-id="e1984-119">**Descrição**: descrição do perfil de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1984-119">**Description**: Description of the device enrollment profile.</span></span> <span data-ttu-id="e1984-120">Não é visível para os usuários.</span><span class="sxs-lookup"><span data-stu-id="e1984-120">Not visible to users.</span></span>

        -   <span data-ttu-id="e1984-121">**Afiliação do usuário**: especifica como os dispositivos são registrados.</span><span class="sxs-lookup"><span data-stu-id="e1984-121">**User affiliation**: Specifies how devices are enrolled.</span></span> <span data-ttu-id="e1984-122">Para o registro direto, escolha **Sem afinidade de usuário**.</span><span class="sxs-lookup"><span data-stu-id="e1984-122">For Direct Enrollment, choose **No user affinity**.</span></span>

        -   <span data-ttu-id="e1984-123">**Pré-atribuição de grupo de dispositivos**: todos os dispositivos que têm esse perfil pertencerão inicialmente a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="e1984-123">**Device group pre-assignment**: All devices that have this profile will initially belong to this group.</span></span> <span data-ttu-id="e1984-124">Você pode reatribuir dispositivos após o registro.</span><span class="sxs-lookup"><span data-stu-id="e1984-124">You can reassign devices after enrollment.</span></span>

            [!INCLUDE[groups deprecated](../includes/group-deprecation.md)]

    3.  <span data-ttu-id="e1984-125">Clique em **Salvar Perfil** para adicionar o perfil.</span><span class="sxs-lookup"><span data-stu-id="e1984-125">Choose **Save Profile** to add the profile.</span></span>

5.  <span data-ttu-id="e1984-126">Exporte um perfil como .mobileconfig para implantar em dispositivos iOS:</span><span class="sxs-lookup"><span data-stu-id="e1984-126">Export a profile as .mobileconfig to deploy to iOS devices:</span></span>

    1.   <span data-ttu-id="e1984-127">Selecione o perfil de dispositivo que você criou.</span><span class="sxs-lookup"><span data-stu-id="e1984-127">Select the device profile that you created.</span></span>

    2.   <span data-ttu-id="e1984-128">Escolha **Exportar** na barra de tarefas.</span><span class="sxs-lookup"><span data-stu-id="e1984-128">Choose **Export** in the taskbar.</span></span>

    3.   <span data-ttu-id="e1984-129">Selecione **Baixar perfil** e salve o arquivo .mobileconfig baixado.</span><span class="sxs-lookup"><span data-stu-id="e1984-129">Choose **Download profile** and save the downloaded .mobileconfig file.</span></span>

6.  <span data-ttu-id="e1984-130">Transfira o arquivo copiando o arquivo .mobileconfig baixado para um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="e1984-130">Transfer the file by copying the downloaded .mobileconfig file to a Mac computer.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e1984-131">A URL do perfil de registro é válida por duas semanas a partir de quando for exportada.</span><span class="sxs-lookup"><span data-stu-id="e1984-131">The enrollment profile URL is valid for two weeks from when it is exported.</span></span> <span data-ttu-id="e1984-132">Depois de duas semanas, você deve exportar uma nova URL de perfil de registro para registrar dispositivos iOS com o Assistente de Configuração.</span><span class="sxs-lookup"><span data-stu-id="e1984-132">After two weeks, you must export a new enrollment profile URL to enroll iOS devices with Setup Assistant.</span></span>

7.  <span data-ttu-id="e1984-133">Preparar o dispositivo com o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="e1984-133">Prepare the device with Apple Configurator.</span></span> <span data-ttu-id="e1984-134">Dispositivos iOS são conectados ao computador Mac e registrados para o gerenciamento de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="e1984-134">iOS devices are connected to the Mac computer and enrolled for mobile device management.</span></span>

    1.  <span data-ttu-id="e1984-135">Em um computador Mac, abra o **Apple Configurator 2.0**.</span><span class="sxs-lookup"><span data-stu-id="e1984-135">On a Mac computer, open **Apple Configurator 2.0**.</span></span>

    2.  <span data-ttu-id="e1984-136">Conecte o dispositivo iOS ao computador Mac com um cabo USB.</span><span class="sxs-lookup"><span data-stu-id="e1984-136">Connect the iOS device to the Mac computer with a USB cord.</span></span> <span data-ttu-id="e1984-137">Feche as **Fotos**, **iTunes**, e outros aplicativos que são abertos com o dispositivo quando ele é detectado.</span><span class="sxs-lookup"><span data-stu-id="e1984-137">Close **Photos**, **iTunes**, and other apps that open for the device when the device is detected.</span></span>

    3.  <span data-ttu-id="e1984-138">No Apple Configurator, escolha o dispositivo iOS conectado e selecione o botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1984-138">In Apple Configurator, choose the connected iOS device, and then choose the **Add** button.</span></span> <span data-ttu-id="e1984-139">As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="e1984-139">Options that can be added to the device appear in the drop-down list.</span></span> <span data-ttu-id="e1984-140">Escolha **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="e1984-140">Choose **Profiles**.</span></span>

    4.  <span data-ttu-id="e1984-141">Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e1984-141">Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**.</span></span> <span data-ttu-id="e1984-142">O perfil é adicionado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1984-142">The profile is added to the device.</span></span>  <span data-ttu-id="e1984-143">Se o dispositivo for **Sem supervisão**, a instalação necessitará da aceitação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1984-143">If the device is **Unsupervised**, the installation will require acceptance on the device.</span></span>

8.  <span data-ttu-id="e1984-144">Você está pronto para instalar o perfil no dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="e1984-144">You are ready to install the profile on the iOS device.</span></span> <span data-ttu-id="e1984-145">O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="e1984-145">The device must have already completed the Setup Assistant and be ready to use.</span></span> <span data-ttu-id="e1984-146">Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="e1984-146">If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.</span></span>

    1.  <span data-ttu-id="e1984-147">Desbloquear o dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="e1984-147">Unlock the iOS device.</span></span>

    2.  <span data-ttu-id="e1984-148">Na caixa de diálogo **Instalar perfil** para o **Perfil de gerenciamento**, escolha **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e1984-148">In the **Install profile** dialog box for **Management profile**,  choose **Install**.</span></span>

    3.  <span data-ttu-id="e1984-149">Forneça a **Senha do Dispositivo** ou **ID Apple**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e1984-149">Provide **Device Passcode** or **Apple ID**, if required.</span></span>

    4.  <span data-ttu-id="e1984-150">Aceite o **Aviso** e escolha **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="e1984-150">Accept the **Warning**, and choose **Install**.</span></span>

    5.  <span data-ttu-id="e1984-151">Aceite o **Aviso Remoto** e escolha **Confiar**.</span><span class="sxs-lookup"><span data-stu-id="e1984-151">Accept the **Remote Warning**, and choose **Trust**.</span></span>

    6.  <span data-ttu-id="e1984-152">Quando a caixa **Perfil Instalado** confirmar que o perfil foi **Instalado**, selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="e1984-152">When the **Profile Installed** box confirms the profile as **Installed**, choose **Done**.</span></span>

9.  <span data-ttu-id="e1984-153">No dispositivo iOS, abra **Configurações** e vá para **Geral** &gt; **Gerenciamento de Dispositivo** &gt; **Perfil de Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="e1984-153">On the iOS device, open **Settings** and go to **General** &gt; **Device Management** &gt; **Management Profile**.</span></span> <span data-ttu-id="e1984-154">Confirme que o perfil de instalação está listado, verifique as restrições de política do iOS e os aplicativos instalados.</span><span class="sxs-lookup"><span data-stu-id="e1984-154">Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps.</span></span> <span data-ttu-id="e1984-155">Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e1984-155">Policy restrictions and apps might take up to 10 minutes to appear on the device.</span></span>

10.  <span data-ttu-id="e1984-156">Distribuir dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e1984-156">Distribute devices.</span></span> <span data-ttu-id="e1984-157">O dispositivo iOS agora está registrado com o Intune e é gerenciado.</span><span class="sxs-lookup"><span data-stu-id="e1984-157">The iOS device is now enrolled with Intune and managed.</span></span>
