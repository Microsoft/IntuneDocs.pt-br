---
title: Registrar dispositivos iOS com o Apple Configurator e registro direto
titleSuffix: Intune on Azure
description: Saiba como usar o Apple Configurator para registrar dispositivos iOS de propriedade corporativa com o registro direto.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6c0a430-1851-4108-812a-87e0fc2623b5
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dd856cc3c9d11d1079c6092025200059f0ace437
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d12a6-103">Registrar dispositivos iOS com o Apple Configurator e registro direto</span><span class="sxs-lookup"><span data-stu-id="d12a6-103">Enroll iOS devices with Apple Configurator and direct enrollment</span></span>
<a id="enroll-ios-devices-with-apple-configurator-and-direct-enrollment" class="xliff"></a> 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d12a6-104">O Intune dá suporte ao registro de dispositivos iOS corporativos usando o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) em execução em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="d12a6-104">Intune supports the enrollment of corporate-owned iOS devices using [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) running on a Mac computer.</span></span> <span data-ttu-id="d12a6-105">Esse processo não restaura as configurações de fábrica do dispositivo e registra o dispositivo com uma política predefinida.</span><span class="sxs-lookup"><span data-stu-id="d12a6-105">This process does not factory-reset the device and enrolls the device with a predefined policy.</span></span> <span data-ttu-id="d12a6-106">Esse método destina-se a dispositivos **sem afinidade de usuário** e requer que você conecte o dispositivo iOS por USB a um computador Mac para configurar o registro corporativo.</span><span class="sxs-lookup"><span data-stu-id="d12a6-106">This method is for devices with **no user affinity** and requires you to USB-connect the iOS device to a Mac computer to set up corporate enrollment.</span></span>

>[!NOTE]
><span data-ttu-id="d12a6-107">Esse método de registro não pode ser usado com o método de [gerenciador de registro de dispositivos](device-enrollment-manager-enroll.md).</span><span class="sxs-lookup"><span data-stu-id="d12a6-107">This enrollment method can't be used with the [device enrollment manager](device-enrollment-manager-enroll.md) method.</span></span>

<span data-ttu-id="d12a6-108">Ao registrar dispositivos iOS diretamente, você pode registrar um dispositivo sem adquirir o número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d12a6-108">When you're directly enrolling iOS devices, you can enroll a device without acquiring the device's serial number.</span></span> <span data-ttu-id="d12a6-109">Você também pode nomear o dispositivo para fins de identificação antes de o Intune capturar o nome do dispositivo durante o registro.</span><span class="sxs-lookup"><span data-stu-id="d12a6-109">You can also name the device for identification purposes before Intune captures the device name during enrollment.</span></span> <span data-ttu-id="d12a6-110">Não há suporte para o aplicativo de Portal da Empresa para dispositivos registrados diretamente.</span><span class="sxs-lookup"><span data-stu-id="d12a6-110">The Company Portal app is not supported for directly enrolled devices.</span></span> <span data-ttu-id="d12a6-111">Esta diretriz presume que você está usando o Apple Configurator 2.0 em um computador Mac.</span><span class="sxs-lookup"><span data-stu-id="d12a6-111">This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.</span></span>

<span data-ttu-id="d12a6-112">Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](enrollment-method-choose-ios.md).</span><span class="sxs-lookup"><span data-stu-id="d12a6-112">Other methods of enrolling iOS devices are described in [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md).</span></span>


## <span data-ttu-id="d12a6-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d12a6-113">Prerequisites</span></span>
<a id="prerequisites" class="xliff"></a>

<span data-ttu-id="d12a6-114">Preencha os seguintes pré-requisitos antes de configurar o registro do dispositivo iOS:</span><span class="sxs-lookup"><span data-stu-id="d12a6-114">Complete the following prerequisites before setting up iOS device enrollment:</span></span>

- [<span data-ttu-id="d12a6-115">Configurar domínios</span><span class="sxs-lookup"><span data-stu-id="d12a6-115">Configure domains</span></span>](custom-domain-name-configure.md)
- [<span data-ttu-id="d12a6-116">Definir a Autoridade MDM</span><span class="sxs-lookup"><span data-stu-id="d12a6-116">Set the MDM Authority</span></span>](mdm-authority-set.md)
- [<span data-ttu-id="d12a6-117">Criar grupos</span><span class="sxs-lookup"><span data-stu-id="d12a6-117">Create groups</span></span>](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [<span data-ttu-id="d12a6-118">Configurar o Portal da Empresa</span><span class="sxs-lookup"><span data-stu-id="d12a6-118">Configure the Company Portal</span></span>](company-portal-app.md)
- <span data-ttu-id="d12a6-119">Atribuir licenças de usuário no [Portal do Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span><span class="sxs-lookup"><span data-stu-id="d12a6-119">Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span></span>
- [<span data-ttu-id="d12a6-120">Obtenha um certificado push de MDM da Apple</span><span class="sxs-lookup"><span data-stu-id="d12a6-120">Get an Apple MDM push certificate</span></span>](apple-mdm-push-certificate-get.md)
- <span data-ttu-id="d12a6-121">Verifique se você tem acesso físico aos dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="d12a6-121">Ensure that you have physical access to iOS devices</span></span>
- <span data-ttu-id="d12a6-122">Obter os números de série do dispositivo (consulte [Como obter um número de série do iOS](https://support.apple.com//HT204308))</span><span class="sxs-lookup"><span data-stu-id="d12a6-122">Have the device serial numbers (see [How to get an iOS serial number](https://support.apple.com//HT204308))</span></span>
- <span data-ttu-id="d12a6-123">Ter em mãos os cabos de conexão USB</span><span class="sxs-lookup"><span data-stu-id="d12a6-123">Have USB connection cables on hand</span></span>
- <span data-ttu-id="d12a6-124">Verifique se você tem um computador Mac com [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) instalado</span><span class="sxs-lookup"><span data-stu-id="d12a6-124">Ensure that you have a Mac PC with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) installed</span></span>

## <span data-ttu-id="d12a6-125">Criar um perfil do Apple Configurator para dispositivos</span><span class="sxs-lookup"><span data-stu-id="d12a6-125">Create an Apple Configurator profile for devices</span></span>
<a id="create-an-apple-configurator-profile-for-devices" class="xliff"></a>

<span data-ttu-id="d12a6-126">Um perfil de registro de dispositivos define as configurações aplicadas a um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d12a6-126">A device enrollment profile defines the settings applied to a group of devices.</span></span> <span data-ttu-id="d12a6-127">As etapas a seguir mostram como criar um perfil de registro de dispositivo para dispositivos iOS registrados usando o Apple Configurator.</span><span class="sxs-lookup"><span data-stu-id="d12a6-127">The following steps show how to create a device enrollment profile for iOS devices enrolled by using Apple Configurator.</span></span>

1. <span data-ttu-id="d12a6-128">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-128">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="d12a6-129">Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-129">On the Intune blade, choose **Enroll devices**, and then choose **Apple Enrollment**.</span></span>

3. <span data-ttu-id="d12a6-130">Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Perfis de CA**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-130">Under **Manage Apple Configurator Enrollment Settings**, select **AC Profiles**.</span></span>

4. <span data-ttu-id="d12a6-131">Na folha **Perfis de registro do Apple Configurator**, selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-131">On the **Apple Configurator Enrollment Profiles** blade, select **Create**.</span></span>

5. <span data-ttu-id="d12a6-132">Na folha **Criar Perfil de Registro**, insira um nome e uma descrição para o perfil.</span><span class="sxs-lookup"><span data-stu-id="d12a6-132">On the **Create Enrollment Profile** blade, enter a name and description for the profile.</span></span>

6. <span data-ttu-id="d12a6-133">Para **Afinidade de Usuário**, escolha **Registrar sem afinidade de usuário** para garantir que o dispositivo não esteja afiliado a um usuário.</span><span class="sxs-lookup"><span data-stu-id="d12a6-133">For **User Affinity** choose **Enroll without user affinity** to ensure that the device is not affiliated with a user.</span></span> <span data-ttu-id="d12a6-134">Use esta afiliação para dispositivos que executam tarefas sem acessar aos dados de usuário local.</span><span class="sxs-lookup"><span data-stu-id="d12a6-134">Use this affiliation for devices that perform tasks without accessing local user data.</span></span> <span data-ttu-id="d12a6-135">Aplicativos que exigem afiliação do usuário (incluindo o aplicativo do Portal da Empresa usado para instalar aplicativos de linha de negócios) não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="d12a6-135">Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.</span></span>

7. <span data-ttu-id="d12a6-136">Selecione **Criar** para salvar o perfil.</span><span class="sxs-lookup"><span data-stu-id="d12a6-136">Select **Create** to save the profile.</span></span>

## <span data-ttu-id="d12a6-137">Exporte um perfil como .mobileconfig para implantar em dispositivos iOS</span><span class="sxs-lookup"><span data-stu-id="d12a6-137">Export the profile as .mobileconfig to iOS devices</span></span>
<a id="export-the-profile-as-mobileconfig-to-ios-devices" class="xliff"></a>

1. <span data-ttu-id="d12a6-138">Na folha **Exportar Perfil**, baixe o perfil de registro para o [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) para envio por push diretamente como um perfil de gerenciamento para um dispositivo iOS conectado.</span><span class="sxs-lookup"><span data-stu-id="d12a6-138">On the **Export Profile** blade, download the enrollment profile to [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) to push directly as a management profile to a connected iOS device.</span></span> <span data-ttu-id="d12a6-139">Esse método não faz uma redefinição de fábrica do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d12a6-139">This method does not do a factory reset of the device.</span></span>

2. <span data-ttu-id="d12a6-140">Prepare o dispositivo com o Apple Configurator usando as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d12a6-140">Prepare the device with Apple Configurator by using the following steps.</span></span>

   <span data-ttu-id="d12a6-141">a.</span><span class="sxs-lookup"><span data-stu-id="d12a6-141">a.</span></span> <span data-ttu-id="d12a6-142">Em um computador Mac, abra o Apple Configurator 2.0.</span><span class="sxs-lookup"><span data-stu-id="d12a6-142">On a Mac computer, open Apple Configurator 2.0.</span></span>

   <span data-ttu-id="d12a6-143">b.</span><span class="sxs-lookup"><span data-stu-id="d12a6-143">b.</span></span> <span data-ttu-id="d12a6-144">Conecte o dispositivo iOS ao computador Mac com um cabo USB.</span><span class="sxs-lookup"><span data-stu-id="d12a6-144">Connect the iOS device to the Mac computer with a USB cord.</span></span> <span data-ttu-id="d12a6-145">Feche as Fotos, iTunes e outros aplicativos que são abertos com o dispositivo quando ele é detectado.</span><span class="sxs-lookup"><span data-stu-id="d12a6-145">Close Photos, iTunes, and other apps that open for the device when the device is detected.</span></span>

   <span data-ttu-id="d12a6-146">c.</span><span class="sxs-lookup"><span data-stu-id="d12a6-146">c.</span></span> <span data-ttu-id="d12a6-147">No Apple Configurator, escolha o dispositivo iOS conectado e selecione o botão **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-147">In Apple Configurator, choose the connected iOS device, and then choose the **Add** button.</span></span> <span data-ttu-id="d12a6-148">As opções que podem ser adicionadas ao dispositivo aparecem na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="d12a6-148">Options that can be added to the device appear in the drop-down list.</span></span> <span data-ttu-id="d12a6-149">Escolha **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-149">Choose **Profiles**.</span></span>

   <span data-ttu-id="d12a6-150">d.</span><span class="sxs-lookup"><span data-stu-id="d12a6-150">d.</span></span> <span data-ttu-id="d12a6-151">Use o seletor de arquivos para selecionar o arquivo .mobileconfig exportado do Intune e escolha **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-151">Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**.</span></span> <span data-ttu-id="d12a6-152">O perfil é adicionado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d12a6-152">The profile is added to the device.</span></span> <span data-ttu-id="d12a6-153">Se o dispositivo for Sem supervisão, a instalação necessitará da aceitação no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d12a6-153">If the device is Unsupervised, the installation will require acceptance on the device.</span></span>

3. <span data-ttu-id="d12a6-154">Use as etapas a seguir para instalar o perfil no dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="d12a6-154">Use the following steps to install the profile on the iOS device.</span></span> <span data-ttu-id="d12a6-155">O dispositivo já deve ter concluído o Assistente de Configuração e está pronto para uso.</span><span class="sxs-lookup"><span data-stu-id="d12a6-155">The device must have already completed the Setup Assistant and be ready to use.</span></span> <span data-ttu-id="d12a6-156">Se o registro envolve as implantações de aplicativo, o dispositivo deve ter uma ID Apple configurada, pois as implantações de aplicativo exigirão que você tenha uma ID Apple conectada na Windows Store.</span><span class="sxs-lookup"><span data-stu-id="d12a6-156">If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.</span></span>

   <span data-ttu-id="d12a6-157">a.</span><span class="sxs-lookup"><span data-stu-id="d12a6-157">a.</span></span> <span data-ttu-id="d12a6-158">Desbloquear o dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="d12a6-158">Unlock the iOS device.</span></span>

   <span data-ttu-id="d12a6-159">b.</span><span class="sxs-lookup"><span data-stu-id="d12a6-159">b.</span></span> <span data-ttu-id="d12a6-160">Na caixa de diálogo **Instalar perfil** para o **Perfil de gerenciamento**, escolha **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-160">In the **Install profile** dialog box for **Management profile**, choose **Install**.</span></span>

   <span data-ttu-id="d12a6-161">c.</span><span class="sxs-lookup"><span data-stu-id="d12a6-161">c.</span></span> <span data-ttu-id="d12a6-162">Forneça a Senha do Dispositivo ou a ID da Apple, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d12a6-162">Provide the Device Passcode or Apple ID, if required.</span></span>

   <span data-ttu-id="d12a6-163">d.</span><span class="sxs-lookup"><span data-stu-id="d12a6-163">d.</span></span> <span data-ttu-id="d12a6-164">Aceite o **Aviso** e escolha **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-164">Accept the **Warning**, and choose **Install**.</span></span>

   <span data-ttu-id="d12a6-165">e.</span><span class="sxs-lookup"><span data-stu-id="d12a6-165">e.</span></span> <span data-ttu-id="d12a6-166">Aceite o **Aviso Remoto** e escolha **Confiar**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-166">Accept the **Remote Warning**, and choose **Trust**.</span></span>

   <span data-ttu-id="d12a6-167">f.</span><span class="sxs-lookup"><span data-stu-id="d12a6-167">f.</span></span> <span data-ttu-id="d12a6-168">Quando a caixa **Perfil Instalado** confirmar que o perfil foi Instalado, escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-168">When the **Profile Installed** box confirms the profile as Installed, choose **Done**.</span></span>

4. <span data-ttu-id="d12a6-169">No dispositivo iOS, abra **Configurações** e vá para **Geral** > **Gerenciamento de Dispositivo** > **Perfil de Gerenciamento**.</span><span class="sxs-lookup"><span data-stu-id="d12a6-169">On the iOS device, open **Settings** and go to **General** > **Device Management** > **Management Profile**.</span></span> <span data-ttu-id="d12a6-170">Confirme que o perfil de instalação está listado, verifique as restrições de política do iOS e os aplicativos instalados.</span><span class="sxs-lookup"><span data-stu-id="d12a6-170">Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps.</span></span> <span data-ttu-id="d12a6-171">Aplicativos e restrições de política podem levar até 10 minutos para serem exibidos no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d12a6-171">Policy restrictions and apps might take up to 10 minutes to appear on the device.</span></span>

5. <span data-ttu-id="d12a6-172">Distribuir dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d12a6-172">Distribute devices.</span></span> <span data-ttu-id="d12a6-173">O dispositivo iOS agora está registrado com o Intune e é gerenciado.</span><span class="sxs-lookup"><span data-stu-id="d12a6-173">The iOS device is now enrolled with Intune and managed.</span></span>
