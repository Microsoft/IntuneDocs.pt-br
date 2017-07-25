---
title: Registro em massa no Windows 10
titleSuffix: Intune on Azure
description: Criar um pacote de registro em massa para o Microsoft Intune
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.openlocfilehash: 4e9dae27b981533dfff2080a5b7f9ca961509cd8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="83b0b-103">Registro em massa para dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="83b0b-103">Bulk enrollment for Windows devices</span></span>
=======
# Registro em massa para dispositivos Windows
>>>>>>> live
<a id="bulk-enrollment-for-windows-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="83b0b-104">Como administrador, você pode ingressar muitos dispositivos novos com Windows ao Azure Active Directory e ao Intune.</span><span class="sxs-lookup"><span data-stu-id="83b0b-104">As an administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune.</span></span> <span data-ttu-id="83b0b-105">Para registrar em massa os dispositivos em seu locatário do Azure AD, você cria um pacote de provisionamento com o aplicativo WCD (Windows Configuration Designer).</span><span class="sxs-lookup"><span data-stu-id="83b0b-105">To bulk enroll devices for your Azure AD tenant, you create a provisioning package with the Windows Configuration Designer (WCD) app.</span></span> <span data-ttu-id="83b0b-106">A aplicação do pacote de provisionamento em dispositivos corporativos ingressa os dispositivos ao seu locatário do Azure AD e os registra no gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="83b0b-106">Applying the provisioning package to corporate-owned devices joins the devices to your Azure AD tenant and enrolls them for Intune management.</span></span> <span data-ttu-id="83b0b-107">Após a aplicação do pacote, ele estará pronto para logon de seus usuários do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="83b0b-107">Once the package is applied, it's ready for your Azure AD users to log on.</span></span>

<span data-ttu-id="83b0b-108">Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas do Intune atribuídas e os aplicativos necessários.</span><span class="sxs-lookup"><span data-stu-id="83b0b-108">Azure AD users are standard users on these devices and receive assigned Intune policies and required apps.</span></span> <span data-ttu-id="83b0b-109">Não há suporte no momento para cenários de autoatendimento e de Portal da empresa.</span><span class="sxs-lookup"><span data-stu-id="83b0b-109">Self-service and Company Portal scenarios are not supported at this time.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="83b0b-110">Pré-requisitos para registro em massa de dispositivos Windows</span><span class="sxs-lookup"><span data-stu-id="83b0b-110">Prerequisites for Windows devices bulk enrollment</span></span>
=======
## Pré-requisitos para registro em massa de dispositivos Windows
>>>>>>> live
<a id="prerequisites-for-windows-devices-bulk-enrollment" class="xliff"></a>

<span data-ttu-id="83b0b-111">O registro em massa para dispositivos Windows exige o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83b0b-111">Bulk enrollment for Window devices requires the following:</span></span>

- <span data-ttu-id="83b0b-112">Dispositivos com Atualização do Windows 10 para Criadores ou posteriores</span><span class="sxs-lookup"><span data-stu-id="83b0b-112">Devices running Windows 10 Creator update or later</span></span>
- [<span data-ttu-id="83b0b-113">Registro automático do Windows</span><span class="sxs-lookup"><span data-stu-id="83b0b-113">Windows automatic enrollment</span></span>](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)

<<<<<<< HEAD
## <span data-ttu-id="83b0b-114">Criar um pacote de provisionamento</span><span class="sxs-lookup"><span data-stu-id="83b0b-114">Create a provisioning package</span></span>
=======
## Criar um pacote de provisionamento
>>>>>>> live
<a id="create-a-provisioning-package" class="xliff"></a>

1. <span data-ttu-id="83b0b-115">Baixe o [WCD (Windows Configuration Designer)](https://www.microsoft.com/store/apps/9nblggh4tx22) da Windows Store.</span><span class="sxs-lookup"><span data-stu-id="83b0b-115">Download [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) from the Windows Store.</span></span>
<span data-ttu-id="83b0b-116">![Capturas de tela e descrição do Windows Configuration Designer](media/bulk-enroll-store.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-116">![Screenshot of the Windows Configuration Designer app Store screenshots and description](media/bulk-enroll-store.png)</span></span>

2. <span data-ttu-id="83b0b-117">Abra o aplicativo **Windows Configuration Designer** e selecione **Provisionar dispositivos de área de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="83b0b-117">Open the **Windows Configuration Designer** app and select **Provision desktop devices**.</span></span>
<span data-ttu-id="83b0b-118">![Captura de tela da seleção de Provisionar dispositivos de área de trabalho no aplicativo Windows Configuration Designer](media/bulk-enroll-select.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-118">![Screenshot of selecting Provision desktop devices in the Windows Configuration Designer app](media/bulk-enroll-select.png)</span></span>

3. <span data-ttu-id="83b0b-119">A janela **Novo projeto** é aberta e é possível especificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="83b0b-119">A **New project** window opens where you specify the following:</span></span>
  - <span data-ttu-id="83b0b-120">**Nome** - um nome para seu projeto</span><span class="sxs-lookup"><span data-stu-id="83b0b-120">**Name** - A name for your project</span></span>
  - <span data-ttu-id="83b0b-121">**Pasta do projeto** - onde seu novo projeto será salvo</span><span class="sxs-lookup"><span data-stu-id="83b0b-121">**Project folder** - Where your project will be saved</span></span>
  - <span data-ttu-id="83b0b-122">**Descrição** - uma descrição opcional do projeto ![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-name.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-122">**Description** - An optional description of the project ![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-name.png)</span></span>

<<<<<<< HEAD
4.  <span data-ttu-id="83b0b-123">Insira um nome exclusivo para seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="83b0b-123">Enter a unique name for your devices.</span></span> <span data-ttu-id="83b0b-124">Os nomes podem incluir um número de série (%%SERIAL%%) ou um conjunto aleatório de caracteres.</span><span class="sxs-lookup"><span data-stu-id="83b0b-124">Names can include a serial number (%%SERIAL%%) or a random set of characters.</span></span> <span data-ttu-id="83b0b-125">Como opção, também é possível inserir uma chave do produto, se você estiver atualizando a edição do Windows, configurá-lo para uso compartilhado e remover o software pré-instalado.</span><span class="sxs-lookup"><span data-stu-id="83b0b-125">Optionally, you can also enter a product key if you are upgrading the edition of Windows, configure the device for shared use, and remove pre-installed software.</span></span>
<span data-ttu-id="83b0b-126">![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-device.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-126">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-device.png)</span></span>

5.  <span data-ttu-id="83b0b-127">Como opção, você pode configurar a rede Wi-Fi à qual os dispositivos se conectem na primeira inicialização.</span><span class="sxs-lookup"><span data-stu-id="83b0b-127">Optionally, you can configure the Wi-Fi network devices connect to when they first start.</span></span>  <span data-ttu-id="83b0b-128">Se isso não estiver configurado, uma conexão de rede com fio será exigida quando o dispositivo for iniciado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="83b0b-128">If this isn’t configured, a wired network connection is required when the device is first started.</span></span>
<span data-ttu-id="83b0b-129">![Captura de tela da habilitação de Wi-Fi, incluindo as opções de SSID da Rede e o Tipo da rede, no aplicativo Windows Configuration Designer](media/bulk-enroll-network.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-129">![Screenshot of enabling Wi-Fi including Network SSID and Network type options in the Windows Configuration Designer app](media/bulk-enroll-network.png)</span></span>

6.  <span data-ttu-id="83b0b-130">Selecione **Registrar no Azure AD**, insira uma data de **Expiração do Token em Massa** e selecione **Obter Token em Massa** .</span><span class="sxs-lookup"><span data-stu-id="83b0b-130">Select **Enroll in Azure AD**, enter a **Bulk Token Expiry** date, and then select **Get Bulk Token**.</span></span>
<span data-ttu-id="83b0b-131">![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-account.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-131">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-account.png)</span></span>
=======
4.  Insira um nome exclusivo para seus dispositivos. Os nomes podem incluir um número de série (%%SERIAL%%) ou um conjunto aleatório de caracteres. Como opção, também é possível inserir uma chave do produto, se você estiver atualizando a edição do Windows, configurá-lo para uso compartilhado e remover o software pré-instalado.
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-device.png)

5.  Como opção, você pode configurar a rede Wi-Fi à qual os dispositivos se conectem na primeira inicialização.  Se isso não estiver configurado, uma conexão de rede com fio será exigida quando o dispositivo for iniciado pela primeira vez.
![Captura de tela da habilitação de Wi-Fi, incluindo as opções de SSID da Rede e o Tipo da rede, no aplicativo Windows Configuration Designer](media/bulk-enroll-network.png)

6.  Selecione **Registrar no Azure AD**, insira uma data de **Expiração do Token em Massa** e selecione **Obter Token em Massa** .
![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-account.png)
>>>>>>> live

7. <span data-ttu-id="83b0b-132">Forneça suas credenciais do Azure AD para obter um token em massa.</span><span class="sxs-lookup"><span data-stu-id="83b0b-132">Provide your Azure AD credentials to get a bulk token.</span></span>
<span data-ttu-id="83b0b-133">![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-cred.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-133">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-cred.png)</span></span>

<<<<<<< HEAD
8.  <span data-ttu-id="83b0b-134">Clique em **Avançar** quando o **Token em Massa** for obtido com êxito.</span><span class="sxs-lookup"><span data-stu-id="83b0b-134">Click **Next** when **Bulk Token** is fetched successfully.</span></span>
=======
8.  Clique em **Avançar** quando o **Token em Massa** for obtido com êxito.
>>>>>>> live

9. <span data-ttu-id="83b0b-135">Como opção, você pode **Adicionar aplicativos** e **Adicionar certificados**.</span><span class="sxs-lookup"><span data-stu-id="83b0b-135">Optionally, you can **Add applications** and **Add certificates**.</span></span> <span data-ttu-id="83b0b-136">Esses aplicativos e certificados são provisionados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83b0b-136">These apps and certificates are provisioned on the device.</span></span>

10. <span data-ttu-id="83b0b-137">Como opção, você pode proteger com senha seu pacote de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="83b0b-137">Optionally, you can password protect your provisioning package.</span></span>  <span data-ttu-id="83b0b-138">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="83b0b-138">Click **Create**.</span></span>
<span data-ttu-id="83b0b-139">![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-create.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-139">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-create.png)</span></span>

<<<<<<< HEAD
## <span data-ttu-id="83b0b-140">Provisionar dispositivos</span><span class="sxs-lookup"><span data-stu-id="83b0b-140">Provision devices</span></span>
=======
## Provisionar dispositivos
>>>>>>> live
<a id="provision-devices" class="xliff"></a>

1. <span data-ttu-id="83b0b-141">Acesse o pacote de provisionamento no local especificado, na **Pasta do projeto** especificada no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="83b0b-141">Access the provisioning package in the location specified in **Project folder** specified in the app.</span></span>

2. <span data-ttu-id="83b0b-142">Escolha como você pretende aplicar o pacote de provisionamento ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83b0b-142">Choose how you’re going to apply the provisioning package to the device.</span></span>  <span data-ttu-id="83b0b-143">Um pacote de provisionamento pode ser aplicado a um dispositivo usando uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="83b0b-143">A provisioning package can be applied to a device one of the following ways:</span></span>
 - <span data-ttu-id="83b0b-144">Coloque o pacote de provisionamento em uma unidade USB, insira a unidade USB no dispositivo que você deseja registrar em massa, e aplique-o durante a instalação inicial</span><span class="sxs-lookup"><span data-stu-id="83b0b-144">Place the provisioning package on a USB drive, insert the USB drive into the device you’d like to bulk enroll, and apply it during initial setup</span></span>
 - <span data-ttu-id="83b0b-145">Coloque o pacote de provisionamento em uma pasta de rede e aplique-o no dispositivo que você deseja registrar em massa após a instalação inicial</span><span class="sxs-lookup"><span data-stu-id="83b0b-145">Place the provisioning package on a network folder, and apply it insert on the device you’d like to bulk enroll after initial setup</span></span>

 <span data-ttu-id="83b0b-146">Para obter instruções passo a passo sobre como aplicar um pacote de provisionamento, confira [Aplicar um pacote de provisionamento](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).</span><span class="sxs-lookup"><span data-stu-id="83b0b-146">For step-by-step instruction on applying a provisioning package, see [Apply a provisioning package](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).</span></span>

3. <span data-ttu-id="83b0b-147">Depois de aplicar o pacote, o dispositivo será reiniciado automaticamente em um minuto.</span><span class="sxs-lookup"><span data-stu-id="83b0b-147">After you apply the package, the device will automatically restart in 1 minute.</span></span>
 <span data-ttu-id="83b0b-148">![Captura de tela da especificação do nome, da pasta do projeto e da descrição no aplicativo Windows Configuration Designer](media/bulk-enroll-add.png)</span><span class="sxs-lookup"><span data-stu-id="83b0b-148">![Screenshot of specifying name, project folder, and description in the Windows Configuration Designer app](media/bulk-enroll-add.png)</span></span>

4. <span data-ttu-id="83b0b-149">Quando o dispositivo for reiniciado, ele se conectará ao Azure Active Directory e registrará no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="83b0b-149">When the device restarts, it connects to the Azure Active Directory and enrolls in Microsoft Intune.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="83b0b-150">Solução de problemas de registro em massa do Windows</span><span class="sxs-lookup"><span data-stu-id="83b0b-150">Troubleshooting Windows bulk enrollment</span></span>
<a id="troubleshooting-windows-bulk-enrollment" class="xliff"></a>

### <span data-ttu-id="83b0b-151">Problemas de provisionamento</span><span class="sxs-lookup"><span data-stu-id="83b0b-151">Provisioning issues</span></span>
<a id="provisioning-issues" class="xliff"></a>
<span data-ttu-id="83b0b-152">O provisionamento deve ser usado em novos dispositivos com Windows.</span><span class="sxs-lookup"><span data-stu-id="83b0b-152">Provisioning is intended to be used on new Windows devices.</span></span> <span data-ttu-id="83b0b-153">As falhas de provisionamento podem exigir a redefinição de fábrica do dispositivo ou a recuperação do dispositivo a partir de uma imagem de inicialização.</span><span class="sxs-lookup"><span data-stu-id="83b0b-153">Provisioning failures might require a factory reset of the device or device recovery from a boot image.</span></span> <span data-ttu-id="83b0b-154">Estes exemplos descrevem alguns dos motivos para falhas de provisionamento:</span><span class="sxs-lookup"><span data-stu-id="83b0b-154">These examples describe some reasons for provisioning failures:</span></span>

- <span data-ttu-id="83b0b-155">Um pacote de provisionamento que tenta ingressar em um domínio do Active Directory ou locatário do Azure Active Directory que não cria uma conta local poderia tornar o dispositivo inacessível se o processo de ingresso no domínio falhar devido à falta de conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="83b0b-155">A provisioning package that attempts to join an Active Directory domain or Azure Active Directory tenant that does not create a local account could make the device unreachable if the domain-join process fails due to lack of network connectivity.</span></span>
- <span data-ttu-id="83b0b-156">Os scripts executados pelo pacote de provisionamento são executados no contexto do sistema e podem fazer alterações aleatórias no sistema de arquivos e configurações do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83b0b-156">Scripts run by the provisioning package are run in system context, and are able to make arbitrary changes to the device file system and configurations.</span></span> <span data-ttu-id="83b0b-157">Um script mal-intencionado ou incorreto pode colocar o dispositivo em um estado que só pode ser recuperado refazendo a imagem ou redefinindo o dispositivo para as configurações de fábrica.</span><span class="sxs-lookup"><span data-stu-id="83b0b-157">A malicious or bad script could put the device in a state that can only be recovered by reimaging or factory resetting the device.</span></span>

### <span data-ttu-id="83b0b-158">Problemas com o Portal da Empresa e registro em massa</span><span class="sxs-lookup"><span data-stu-id="83b0b-158">Problems with bulk enrollment and Company Portal</span></span>
<a id="problems-with-bulk-enrollment-and-company-portal" class="xliff"></a>
<span data-ttu-id="83b0b-159">Se um usuário tenta registrar um dispositivo previamente registrado em massa usando o Portal da Empresa, eles receberão um aviso de que seu dispositivo precisa de outras ações, seja instalação ou registro.</span><span class="sxs-lookup"><span data-stu-id="83b0b-159">If a user tries to enroll a previously bulk-enrolled device using the Company Portal, they will receive a warning that their device needs further actions, either setup or enrollment.</span></span> <span data-ttu-id="83b0b-160">O dispositivo é registrado, mas o registro não é reconhecido pelo aplicativo de Portal da Empresa ou site.</span><span class="sxs-lookup"><span data-stu-id="83b0b-160">The device is enrolled, but the enrollment is not recognized by the Company Portal app or website.</span></span>

### <span data-ttu-id="83b0b-161">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="83b0b-161">Conditional access</span></span>
<a id="conditional-access" class="xliff"></a>
<span data-ttu-id="83b0b-162">O acesso condicional não está disponível para dispositivos Windows registrados em massa.</span><span class="sxs-lookup"><span data-stu-id="83b0b-162">Conditional access is not available for Windows devices enrolled using bulk enrollment.</span></span>
=======
## Solução de problemas de registro em massa do Windows
<a id="troubleshooting-windows-bulk-enrollment" class="xliff"></a>

### Problemas de provisionamento
<a id="provisioning-issues" class="xliff"></a>
O provisionamento deve ser usado em novos dispositivos com Windows. As falhas de provisionamento podem exigir a redefinição de fábrica do dispositivo ou a recuperação do dispositivo a partir de uma imagem de inicialização. Estes exemplos descrevem alguns dos motivos para falhas de provisionamento:

- Um pacote de provisionamento que tenta ingressar em um domínio do Active Directory ou locatário do Azure Active Directory que não cria uma conta local poderia tornar o dispositivo inacessível se o processo de ingresso no domínio falhar devido à falta de conectividade de rede.
- Os scripts executados pelo pacote de provisionamento são executados no contexto do sistema e podem fazer alterações aleatórias no sistema de arquivos e configurações do dispositivo. Um script mal-intencionado ou incorreto pode colocar o dispositivo em um estado que só pode ser recuperado refazendo a imagem ou redefinindo o dispositivo para as configurações de fábrica.

### Problemas com o Portal da Empresa e registro em massa
<a id="problems-with-bulk-enrollment-and-company-portal" class="xliff"></a>
Se um usuário tenta registrar um dispositivo previamente registrado em massa usando o Portal da Empresa, eles receberão um aviso de que seu dispositivo precisa de outras ações, seja instalação ou registro. O dispositivo é registrado, mas o registro não é reconhecido pelo aplicativo de Portal da Empresa ou site.

### Acesso condicional
<a id="conditional-access" class="xliff"></a>
O acesso condicional não está disponível para dispositivos Windows registrados em massa.
>>>>>>> live
