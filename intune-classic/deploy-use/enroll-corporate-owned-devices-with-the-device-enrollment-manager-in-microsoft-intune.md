---
title: Registrar com o gerenciador de registros de dispositivo
description: "A conta do DEM (Gerenciador de Registro de Dispositivos) pode gerenciar grandes quantidades de dispositivos móveis corporativos compartilhados com uma única conta de usuário."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a23abc61-69ed-44f1-9b71-b86aefc6ba03
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 095b89d1428d6b8f06143043d8bb6ed37fd8fa5b
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="52596-103">Registrar dispositivos corporativos com o Gerenciador de registro de dispositivo no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="52596-103">Enroll corporate-owned devices with the device enrollment manager in Microsoft Intune</span></span>
<a id="enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="52596-104">As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="52596-104">Organizations can use Intune to manage large numbers of mobile devices with a single user account.</span></span> <span data-ttu-id="52596-105">A conta do *DEM* (gerenciador de registro de dispositivos) é uma conta especial do usuário que pode registrar até 1.000 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52596-105">The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices.</span></span> <span data-ttu-id="52596-106">Adicionar usuários existentes à conta do DEM para fornecer recursos de DEM especiais.</span><span class="sxs-lookup"><span data-stu-id="52596-106">You add existing users to the DEM account to give them the special DEM capabilities.</span></span> <span data-ttu-id="52596-107">Cada dispositivo registrado usa uma única licença.</span><span class="sxs-lookup"><span data-stu-id="52596-107">Each enrolled device uses a single license.</span></span> <span data-ttu-id="52596-108">Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados (ou seja, sem afinidade do usuário) em vez de dispositivos pessoais ("BYOD").</span><span class="sxs-lookup"><span data-stu-id="52596-108">We recommend that you use devices enrolled through this account as shared devices (that is, with no user affinity) rather than personal ("BYOD") devices.</span></span>  

<span data-ttu-id="52596-109">Os usuários devem existir no Portal do Azure para serem adicionados como gerenciadores de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52596-109">Users must exist in the Azure portal to be added as device enrollment managers.</span></span> <span data-ttu-id="52596-110">Para uma melhor segurança, o usuário do DEM não deve ser um administrador do Intune também.</span><span class="sxs-lookup"><span data-stu-id="52596-110">For optimal security, the DEM user should not also be an Intune admin.</span></span>

>[!NOTE]
><span data-ttu-id="52596-111">O método de registro DEM não pode ser usado com o [Apple Configurator Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) ou [registro direto](ios-direct-enrollment-in-microsoft-intune.md) ou com o [método de registro de DEP](ios-device-enrollment-program-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="52596-111">The DEM enrollment method can't be used with the [Apple Configurator Setup Assistant](ios-setup-assistant-enrollment-in-microsoft-intune.md) or [direct enrollment](ios-direct-enrollment-in-microsoft-intune.md), or the [DEP enrollment method](ios-device-enrollment-program-in-microsoft-intune.md).</span></span>

## <span data-ttu-id="52596-112">Exemplo de um cenário do gerenciador de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="52596-112">Example of a device enrollment manager scenario</span></span>
<a id="example-of-a-device-enrollment-manager-scenario" class="xliff"></a>

<span data-ttu-id="52596-113">Um restaurante quer fornecer 50 tablets de ponto de venda para sua equipe e faz o pedido de monitores para sua equipe da cozinha.</span><span class="sxs-lookup"><span data-stu-id="52596-113">A restaurant wants to provide 50 point-of-sale tablets for its wait staff, and order monitors for its kitchen staff.</span></span> <span data-ttu-id="52596-114">Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários.</span><span class="sxs-lookup"><span data-stu-id="52596-114">The employees never need to access company data or sign in as users.</span></span> <span data-ttu-id="52596-115">O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e adiciona um supervisor do restaurante à conta DEM, na verdade concedendo recursos de DEM a esse supervisor.</span><span class="sxs-lookup"><span data-stu-id="52596-115">The Intune admin creates a device enrollment manager account and adds a restaurant supervisor to the DEM account, in effect giving that supervisor DEM capabilities.</span></span> <span data-ttu-id="52596-116">O supervisor agora pode registrar os 50 dispositivos de tablets usando as credenciais do DEM.</span><span class="sxs-lookup"><span data-stu-id="52596-116">The supervisor can now enroll the 50 tablets devices by using the DEM credentials.</span></span>

<span data-ttu-id="52596-117">Somente os usuários no console do Intune podem gerenciadores de registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52596-117">Only users in the Intune console can be device enrollment managers.</span></span> <span data-ttu-id="52596-118">O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="52596-118">The device enrollment manager user cannot be an Intune admin.</span></span>

<span data-ttu-id="52596-119">O usuário do DEM pode:</span><span class="sxs-lookup"><span data-stu-id="52596-119">The DEM user can:</span></span>

-   <span data-ttu-id="52596-120">Registrar até 1000 dispositivos no Intune</span><span class="sxs-lookup"><span data-stu-id="52596-120">Enroll up to 1000 devices in Intune</span></span>
-   <span data-ttu-id="52596-121">Usar o aplicativo Portal de Empresa para obter os aplicativos corporativos</span><span class="sxs-lookup"><span data-stu-id="52596-121">Use the Company Portal app to get company apps</span></span>
-   <span data-ttu-id="52596-122">Configurar o acesso aos dados da empresa implantando aplicativos específicos da função nos tablets</span><span class="sxs-lookup"><span data-stu-id="52596-122">Configure access to company data by deploying role-specific apps to the tablets</span></span>

## <span data-ttu-id="52596-123">Limitações de dispositivos registrados com uma conta do DEM</span><span class="sxs-lookup"><span data-stu-id="52596-123">Limitations of devices that are enrolled with a DEM account</span></span>
<a id="limitations-of-devices-that-are-enrolled-with-a-dem-account" class="xliff"></a>

<span data-ttu-id="52596-124">Dispositivos registrados com uma conta de gerenciador de registro de dispositivos têm as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="52596-124">Devices that are enrolled with a device enrollment manager account have the following limitations:</span></span>

  - <span data-ttu-id="52596-125">Não há nenhum "usuário" de dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="52596-125">There is no specific device "user."</span></span> <span data-ttu-id="52596-126">Portanto, não há nenhum acesso a dados da empresa ou email.</span><span class="sxs-lookup"><span data-stu-id="52596-126">Therefore, there is no email or company data access.</span></span> <span data-ttu-id="52596-127">No entanto, a VPN, por exemplo, ainda pode ser usada para fornecer aplicativos de dispositivo com acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="52596-127">However VPN, for example, could still be used to provide device apps with access to data.</span></span>

  - <span data-ttu-id="52596-128">Não há acesso condicional, pois esses são cenários por usuário.</span><span class="sxs-lookup"><span data-stu-id="52596-128">There is no conditional access because these are per-user scenarios.</span></span>

  - <span data-ttu-id="52596-129">O usuário do DEM não pode cancelar o registro de dispositivos registrados pelo DEM no próprio dispositivo usando o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="52596-129">The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal.</span></span> <span data-ttu-id="52596-130">O administrador do Intune tem essa funcionalidade, mas o usuário do DEM não.</span><span class="sxs-lookup"><span data-stu-id="52596-130">The Intune admin has this capability, but the DEM user does not.</span></span>

  - <span data-ttu-id="52596-131">Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.</span><span class="sxs-lookup"><span data-stu-id="52596-131">Only the local device appears in the Company Portal app or website.</span></span>

  - <span data-ttu-id="52596-132">Os usuários não podem usar aplicativos VPP (Apple Volume Purchase Program) devido aos requisitos de ID da Apple por usuário para o gerenciamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="52596-132">Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.</span></span>

  - <span data-ttu-id="52596-133">(somente iOS) Se você usar o DEM para registrar dispositivos iOS, não poderá usar o Apple Configurator ou o DEP(Programa de registro de dispositivo) da Apple para registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52596-133">(iOS only) If you use DEM to enroll iOS devices, you can't use the Apple Configurator or Apple Device Enrollment Program (DEP) to enroll devices.</span></span>

> [!NOTE]
> <span data-ttu-id="52596-134">Para implantar aplicativos da empresa em dispositivos gerenciados pelo gerenciador de registro do dispositivo, implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** para a conta de usuário do gerenciador de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="52596-134">To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.</span></span>
> <span data-ttu-id="52596-135">Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="52596-135">To improve performance, viewing the Company Portal app on a DEM device shows only the local device.</span></span> <span data-ttu-id="52596-136">Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="52596-136">Remote management of other DEM devices can only be done from the Intune admin console.</span></span>


## <span data-ttu-id="52596-137">Adicionar um gerenciador de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="52596-137">Add a device enrollment manager</span></span>
<a id="add-a-device-enrollment-manager" class="xliff"></a>

1.  <span data-ttu-id="52596-138">Certifique-se de que o usuário que você deseja adicionar à conta DEM já exista.</span><span class="sxs-lookup"><span data-stu-id="52596-138">Ensure that the user that you want to add to the DEM account already exists.</span></span> <span data-ttu-id="52596-139">Se você precisar adicionar o usuário, entre no [Portal do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=698854) e siga as etapas em [Adicionar usuários individualmente ou em lote ao portal do Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="52596-139">If you need to add the user, sign in to the [Office 365 portal](https://go.microsoft.com/fwlink/p/?LinkId=698854), and follow the steps in [Add users individually or in bulk to the Office 365 portal](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span>

2.  <span data-ttu-id="52596-140">Entre no [Console de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="52596-140">Sign in to the [Microsoft Intune administration console](https://manage.microsoft.com) with your admin credentials.</span></span>

3.  <span data-ttu-id="52596-141">No painel de navegação, escolha **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="52596-141">In the navigation pane, choose **Admin**, go to **Administrator Management**, and select **Device Enrollment Manager**.</span></span> <span data-ttu-id="52596-142">A página **Gerenciadores de Registro de Dispositivos** abre.</span><span class="sxs-lookup"><span data-stu-id="52596-142">The **Device Enrollment Managers** page opens.</span></span>

4.  <span data-ttu-id="52596-143">Escolha **Adicionar...**.</span><span class="sxs-lookup"><span data-stu-id="52596-143">Choose **Add…**.</span></span> <span data-ttu-id="52596-144">A caixa de diálogo **Adicionar Gerenciador de Registro de Dispositivos** é aberta.</span><span class="sxs-lookup"><span data-stu-id="52596-144">The **Add Device Enrollment Manager** dialog box opens.</span></span>

5.  <span data-ttu-id="52596-145">Insira a **ID de usuário** da conta do Intune e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="52596-145">Enter the **User ID** of the Intune account, and then choose **OK**.</span></span>

    <span data-ttu-id="52596-146">O usuário do DEM pode registrar dispositivos móveis usando o mesmo procedimento que um usuário final utiliza para um cenário de BYOD no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="52596-146">The DEM user can now enroll mobile devices by using the same procedure that an end user uses for a BYOD scenario in the Company Portal.</span></span> <span data-ttu-id="52596-147">O usuário final do gerenciador pode instalar o aplicativo do Portal da Empresa e registrar o dispositivo usando suas credenciais do DEM em até 1.000 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52596-147">The manager end user can install the Company Portal app and enroll the device using her DEM credentials on up to 1000 devices.</span></span> <span data-ttu-id="52596-148">Para as etapas de registro do usuário final para cada plataforma, consulte:</span><span class="sxs-lookup"><span data-stu-id="52596-148">For the end-user enrollment steps for each platform, see:</span></span>

  - [<span data-ttu-id="52596-149">Registrar seu dispositivo iOS no Intune</span><span class="sxs-lookup"><span data-stu-id="52596-149">Enroll your iOS device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)
  - [<span data-ttu-id="52596-150">Registrar seu dispositivo macOS no Intune</span><span class="sxs-lookup"><span data-stu-id="52596-150">Enroll your macOS device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos)
  - [<span data-ttu-id="52596-151">Registrar seu dispositivo Android no Intune</span><span class="sxs-lookup"><span data-stu-id="52596-151">Enroll your Android device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)
  - [<span data-ttu-id="52596-152">Registrar seu dispositivo Windows no Intune</span><span class="sxs-lookup"><span data-stu-id="52596-152">Enroll your Windows device in Intune</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows)

## <span data-ttu-id="52596-153">Excluir um gerenciador de registro de dispositivos do Intune</span><span class="sxs-lookup"><span data-stu-id="52596-153">Delete a device enrollment manager from Intune</span></span>
<a id="delete-a-device-enrollment-manager-from-intune" class="xliff"></a>

1.  <span data-ttu-id="52596-154">Entre no [Portal de administração do Microsoft Intune](https://manage.microsoft.com) com suas credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="52596-154">Sign in to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span>

2.  <span data-ttu-id="52596-155">No painel de navegação, escolha **Administração**, vá para **Gerenciamento do Administrador** e selecione **Gerenciador de Registro de Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="52596-155">In the navigation pane, choose **Admin**, go to **Administrator Management**, and select **Device Enrollment Manager**.</span></span> <span data-ttu-id="52596-156">A página **Gerenciadores de Registro de Dispositivos** abre.</span><span class="sxs-lookup"><span data-stu-id="52596-156">The **Device Enrollment Managers** page opens.</span></span>

3.  <span data-ttu-id="52596-157">Selecione o **Usuário** gerenciador de registro de dispositivos que você deseja excluir e escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="52596-157">Select the device enrollment manager **User** that you want to delete, and then choose **Delete**.</span></span> <span data-ttu-id="52596-158">Este usuário não será excluído do Intune e os dispositivos gerenciados por ele permanecerão registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="52596-158">This user won’t be deleted from Intune, and the devices this user manages will remain enrolled in Intune.</span></span> <span data-ttu-id="52596-159">Excluir um gerenciador de registro de dispositivos impede que tal usuário registre outros dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="52596-159">Deleting a device enrollment manager prevents that user from enrolling more devices in Intune.</span></span>

4.  <span data-ttu-id="52596-160">Escolha **Sim** para confirmar que deseja excluir o gerenciador de registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52596-160">Choose **Yes** to confirm that you want to delete the device enrollment manager.</span></span>

<span data-ttu-id="52596-161">Excluir um gerenciador de registro de dispositivos não afeta os dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="52596-161">Deleting a device enrollment manager does not affect enrolled devices.</span></span> <span data-ttu-id="52596-162">Quando um gerenciador de registro de dispositivos é excluído:</span><span class="sxs-lookup"><span data-stu-id="52596-162">When a device enrollment manager is deleted:</span></span>

-   <span data-ttu-id="52596-163">Nenhum dispositivo registrado é afetado.</span><span class="sxs-lookup"><span data-stu-id="52596-163">No enrolled devices are affected.</span></span>

-   <span data-ttu-id="52596-164">Os dispositivos registrados continuam sendo totalmente gerenciados.</span><span class="sxs-lookup"><span data-stu-id="52596-164">Enrolled devices continue to be fully managed.</span></span>

-   <span data-ttu-id="52596-165">As credenciais da conta do gerenciador de registro de dispositivos excluído continuam válidas para entrar no Portal da Empresa para acessar aplicativos.</span><span class="sxs-lookup"><span data-stu-id="52596-165">The deleted device enrollment manager account credentials remain valid to sign in to the Company Portal to access apps.</span></span>

-   <span data-ttu-id="52596-166">As credenciais da conta do gerenciador de registro de dispositivos excluído não podem mais apagar ou desativar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="52596-166">The deleted device enrollment manager account credentials still cannot wipe or retire devices.</span></span>

-   <span data-ttu-id="52596-167">A relação da conta do gerenciador de registro de dispositivos excluído com os dispositivos registrados permanece, mas nenhum dispositivo adicional pode ser registrado.</span><span class="sxs-lookup"><span data-stu-id="52596-167">The deleted device enrollment manager account’s relationship to enrolled devices remains, but no additional devices can be enrolled.</span></span>
