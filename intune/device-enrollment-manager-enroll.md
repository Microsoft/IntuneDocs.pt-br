---
title: "Registrar dispositivos – gerenciador de registro de dispositivos"
titleSuffix: Intune on Azure
description: Use a conta do gerenciador de registros de dispositivo para registrar dispositivos no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1667470154e5d2485e3a372ab25d36eea12109a7
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ba81a-104">Registrar dispositivos usando o gerenciador de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba81a-104">Enroll devices using device enrollment manager</span></span>
<a id="enroll-devices-using-device-enrollment-manager" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ba81a-105">As organizações podem usar o Intune para gerenciar um grande número de dispositivos móveis com uma única conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ba81a-105">Organizations can use Intune to manage large numbers of mobile devices with a single user account.</span></span> <span data-ttu-id="ba81a-106">A conta do *DEM* (gerenciador de registro de dispositivos) é uma conta especial do usuário que pode registrar até 1.000 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba81a-106">The *device enrollment manager* (DEM) account is a special user account that can enroll up to 1,000 devices.</span></span> <span data-ttu-id="ba81a-107">Adicionar usuários existentes à conta do DEM para fornecer recursos de DEM especiais.</span><span class="sxs-lookup"><span data-stu-id="ba81a-107">You add existing users to the DEM account to give them the special DEM capabilities.</span></span> <span data-ttu-id="ba81a-108">Cada dispositivo registrado usa uma única licença.</span><span class="sxs-lookup"><span data-stu-id="ba81a-108">Each enrolled device uses a single license.</span></span> <span data-ttu-id="ba81a-109">Recomendamos o uso de dispositivos registrados com essa conta como dispositivos compartilhados em vez de dispositivos pessoais ("BYOD").</span><span class="sxs-lookup"><span data-stu-id="ba81a-109">We recommend that you use devices enrolled through this account as shared devices rather than personal ("BYOD") devices.</span></span>  

<span data-ttu-id="ba81a-110">Os usuários devem existir no Portal do Azure para serem adicionados como gerenciadores de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba81a-110">Users must exist in the Azure portal to be added as device enrollment managers.</span></span> <span data-ttu-id="ba81a-111">Para uma melhor segurança, o usuário do DEM não deve ser um administrador do Intune também.</span><span class="sxs-lookup"><span data-stu-id="ba81a-111">For optimal security, the DEM user should not also be an Intune admin.</span></span>

>[!NOTE]
><span data-ttu-id="ba81a-112">O método de registro DEM não pode ser usado com estes outros métodos de registro: [Apple Configurator com o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator com registro direto](apple-configurator-direct-enroll-ios.md), [ASM (Apple School Manager)](apple-school-manager-set-up-ios.md) ou [DEP (Programa de registro de dispositivos)](device-enrollment-program-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ba81a-112">The DEM enrollment method can't be used with these other enrollment methods: [Apple Configurator with Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator with direct enrollment](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md), or [Device Enrollment Program (DEP)](device-enrollment-program-enroll-ios.md).</span></span>

## <span data-ttu-id="ba81a-113">Exemplo de um cenário do gerenciador de registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ba81a-113">Example of a device enrollment manager scenario</span></span>
<a id="example-of-a-device-enrollment-manager-scenario" class="xliff"></a>

<span data-ttu-id="ba81a-114">Um restaurante quer fornecer 50 tablets de ponto de venda para sua equipe e faz o pedido de monitores para sua equipe da cozinha.</span><span class="sxs-lookup"><span data-stu-id="ba81a-114">A restaurant wants to provide 50 point-of-sale tablets for its wait staff, and order monitors for its kitchen staff.</span></span> <span data-ttu-id="ba81a-115">Os funcionários nunca precisam acessar os dados da empresa ou entrar como usuários.</span><span class="sxs-lookup"><span data-stu-id="ba81a-115">The employees never need to access company data or sign in as users.</span></span> <span data-ttu-id="ba81a-116">O administrador do Intune cria uma conta de gerenciador de registro de dispositivos e adiciona um supervisor do restaurante à conta DEM, na verdade concedendo recursos de DEM a esse supervisor.</span><span class="sxs-lookup"><span data-stu-id="ba81a-116">The Intune admin creates a device enrollment manager account and adds a restaurant supervisor to the DEM account, in effect giving that supervisor DEM capabilities.</span></span> <span data-ttu-id="ba81a-117">O supervisor agora pode registrar os 50 dispositivos de tablets usando as credenciais do DEM.</span><span class="sxs-lookup"><span data-stu-id="ba81a-117">The supervisor can now enroll the 50 tablets devices by using the DEM credentials.</span></span>

<span data-ttu-id="ba81a-118">Somente os usuários no console do Intune podem gerenciadores de registro de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba81a-118">Only users in the Intune console can be device enrollment managers.</span></span> <span data-ttu-id="ba81a-119">O usuário gerenciador de registro de dispositivos não pode ser um administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="ba81a-119">The device enrollment manager user cannot be an Intune admin.</span></span>

<span data-ttu-id="ba81a-120">O usuário do DEM pode:</span><span class="sxs-lookup"><span data-stu-id="ba81a-120">The DEM user can:</span></span>

-   <span data-ttu-id="ba81a-121">Registrar até 1000 dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="ba81a-121">Enroll up to 1000 devices in Intune.</span></span>
-   <span data-ttu-id="ba81a-122">Entre no Portal de Empresa para obter aplicativos corporativos.</span><span class="sxs-lookup"><span data-stu-id="ba81a-122">Sign in to the Company Portal to get company apps.</span></span>
-   <span data-ttu-id="ba81a-123">Configurar o acesso aos dados da empresa implantando aplicativos específicos da função nos tablets.</span><span class="sxs-lookup"><span data-stu-id="ba81a-123">Configure access to company data by deploying role-specific apps to the tablets.</span></span>

## <span data-ttu-id="ba81a-124">Limitações de dispositivos registrados com uma conta do DEM</span><span class="sxs-lookup"><span data-stu-id="ba81a-124">Limitations of devices that are enrolled with a DEM account</span></span>
<a id="limitations-of-devices-that-are-enrolled-with-a-dem-account" class="xliff"></a>

<span data-ttu-id="ba81a-125">Dispositivos registrados com uma conta de gerenciador de registro de dispositivos têm as seguintes limitações:</span><span class="sxs-lookup"><span data-stu-id="ba81a-125">Devices that are enrolled with a device enrollment manager account have the following limitations:</span></span>

  - <span data-ttu-id="ba81a-126">Sem acesso por usuário.</span><span class="sxs-lookup"><span data-stu-id="ba81a-126">No per-user access.</span></span> <span data-ttu-id="ba81a-127">Como os dispositivos não têm um usuário atribuído, o dispositivo não tem nenhum email ou acesso a dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="ba81a-127">Because devices don't have an assigned user, the device have no email or company data access.</span></span> <span data-ttu-id="ba81a-128">As configurações de VPN, por exemplo, ainda poderão ser usadas para fornecer aos aplicativos de dispositivo o acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="ba81a-128">VPN configurations, for example, could still be used to provide device apps with access to data.</span></span>
  - <span data-ttu-id="ba81a-129">Sem acesso condicional, pois esses cenários são por usuário.</span><span class="sxs-lookup"><span data-stu-id="ba81a-129">No conditional access because these scenarios are per-user.</span></span>
  - <span data-ttu-id="ba81a-130">O usuário do DEM não pode cancelar o registro de dispositivos registrados pelo DEM no próprio dispositivo usando o Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ba81a-130">The DEM user can't unenroll DEM-enrolled devices on the device itself by using the Company Portal.</span></span> <span data-ttu-id="ba81a-131">A administração do Intune pode fazer isso, ao contrário do usuário DEM.</span><span class="sxs-lookup"><span data-stu-id="ba81a-131">The Intune admin can do this, but the DEM user does not.</span></span>
  - <span data-ttu-id="ba81a-132">Somente o dispositivo local é exibido no aplicativo Portal da Empresa ou no site.</span><span class="sxs-lookup"><span data-stu-id="ba81a-132">Only the local device appears in the Company Portal app or website.</span></span>
  - <span data-ttu-id="ba81a-133">Os usuários não podem usar aplicativos VPP (Apple Volume Purchase Program) devido aos requisitos de ID da Apple por usuário para o gerenciamento de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ba81a-133">Users can't use Apple Volume Purchase Program (VPP) apps because of per-user Apple ID requirements for app management.</span></span>
  - <span data-ttu-id="ba81a-134">(Somente iOS) Se você usar o DEM para registrar dispositivos iOS, não poderá usar o Apple Configurator, o Apple DEP (Programa de registro de dispositivos) nem o ASM (Apple School Manager) para registrar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba81a-134">(iOS only) If you use DEM to enroll iOS devices, you can't use the Apple Configurator, Apple Device Enrollment Program (DEP), or Apple School Manager (ASM) to enroll devices.</span></span>
  - <span data-ttu-id="ba81a-135">Cada dispositivo exige uma licença de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba81a-135">Each device requires a device license.</span></span> <span data-ttu-id="ba81a-136">Saiba mais sobre [licenças de usuário e dispositivo](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).</span><span class="sxs-lookup"><span data-stu-id="ba81a-136">Learn more about [user and device licenses](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).</span></span>


> [!NOTE]
> <span data-ttu-id="ba81a-137">Para implantar aplicativos da empresa em dispositivos gerenciados pelo gerenciador de registro do dispositivo, implante o aplicativo Portal da Empresa como uma **Instalação Obrigatória** para a conta de usuário do gerenciador de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba81a-137">To deploy company apps to devices that are managed by the device enrollment manager, deploy the Company Portal app as a **Required Install** to the device enrollment manager's user account.</span></span>
> <span data-ttu-id="ba81a-138">Para melhorar o desempenho, exibir o aplicativo de Portal da Empresa em um dispositivo DEM mostra somente os dispositivos locais.</span><span class="sxs-lookup"><span data-stu-id="ba81a-138">To improve performance, viewing the Company Portal app on a DEM device shows only the local device.</span></span> <span data-ttu-id="ba81a-139">Gerenciamento remoto de outros dispositivos DEM só pode ser feito no console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="ba81a-139">Remote management of other DEM devices can only be done from the Intune admin console.</span></span>


## <span data-ttu-id="ba81a-140">Adicionar um gerenciador de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba81a-140">Add a device enrollment manager</span></span>
<a id="add-a-device-enrollment-manager" class="xliff"></a>

1.  <span data-ttu-id="ba81a-141">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-141">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2.  <span data-ttu-id="ba81a-142">Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-142">On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.</span></span>

3.  <span data-ttu-id="ba81a-143">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-143">Select **Add**.</span></span>

4.  <span data-ttu-id="ba81a-144">Na folha **Adicionar Usuário**, insira um nome UPN para o usuário DEM e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-144">On the **Add User** blade, enter a user principal name for the DEM user, and select **Add**.</span></span> <span data-ttu-id="ba81a-145">O usuário DEM é adicionado à lista de usuários DEM.</span><span class="sxs-lookup"><span data-stu-id="ba81a-145">The DEM user is added to the list of DEM users.</span></span>

## <span data-ttu-id="ba81a-146">Permissões para o DEM</span><span class="sxs-lookup"><span data-stu-id="ba81a-146">Permissions for DEM</span></span>
<a id="permissions-for-dem" class="xliff"></a>

<span data-ttu-id="ba81a-147">As funções do Azure AD Administrador Global ou de Serviços do Intune são necessárias para realizar tarefas de registro do DEM.</span><span class="sxs-lookup"><span data-stu-id="ba81a-147">Global or Intune Service Administrator Azure AD roles are required to perform DEM enrollment tasks.</span></span> <span data-ttu-id="ba81a-148">Essas funções também são necessárias para ver todos os usuários DEM, apesar de as permissões RBAC serem listadas e estarem disponíveis na função de Usuário personalizada.</span><span class="sxs-lookup"><span data-stu-id="ba81a-148">These roles are also required to see all DEM users despite RBAC permissions being listed and available under the custom User role.</span></span> <span data-ttu-id="ba81a-149">Um usuário sem uma função Administrador global ou Administrador de serviços do Intune atribuída, mas que tem permissões de leitura para a função Gerentes de Registro de Dispositivo, pode ver somente os usuários do DEM criados por ele.</span><span class="sxs-lookup"><span data-stu-id="ba81a-149">A user without Global administrator or Intune Service administrator role assigned, but who has read permissions for the Device Enrollment Managers role, can only see the DEM users they created.</span></span> <span data-ttu-id="ba81a-150">O suporte à função RBAC para esses recursos será anunciada no futuro.</span><span class="sxs-lookup"><span data-stu-id="ba81a-150">RBAC role support for these features will be announced in the future.</span></span>

<span data-ttu-id="ba81a-151">Se um usuário não tiver a função Administrador global ou Administrador de serviços do Intune atribuída a ele, mas tiver permissões de leitura habilitadas para a função Gerentes de Registro do Dispositivo atribuída a ele, poderá ver apenas os usuários do DEM criados por ele.</span><span class="sxs-lookup"><span data-stu-id="ba81a-151">If a user does not have Global administrator or Intune Service administrator role assigned to them but has read permissions enabled for the Device Enrollment Managers role assigned to them, they’ll only be able to see the DEM users they have created.</span></span>

## <span data-ttu-id="ba81a-152">Remover um gerenciador de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba81a-152">Remove a device enrollment manager</span></span>
<a id="remove-a-device-enrollment-manager" class="xliff"></a>

<span data-ttu-id="ba81a-153">Remover um gerenciador de registro de dispositivos não afeta os dispositivos registrados.</span><span class="sxs-lookup"><span data-stu-id="ba81a-153">Removing a device enrollment manager does not affect enrolled devices.</span></span> <span data-ttu-id="ba81a-154">Quando um gerenciador de registro de dispositivos é removido:</span><span class="sxs-lookup"><span data-stu-id="ba81a-154">When a device enrollment manager is removed:</span></span>

-   <span data-ttu-id="ba81a-155">Os dispositivos registrados não são afetados e continuam sendo totalmente gerenciados.</span><span class="sxs-lookup"><span data-stu-id="ba81a-155">Enrolled devices are unaffected and continue to be fully managed.</span></span>
-   <span data-ttu-id="ba81a-156">As credenciais de conta do gerenciador de registro de dispositivo removido permanecem válidas.</span><span class="sxs-lookup"><span data-stu-id="ba81a-156">The removed device enrollment manager account credentials remain valid.</span></span>
-   <span data-ttu-id="ba81a-157">O gerenciador de registro de dispositivos removido ainda não poderá apagar nem desativar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba81a-157">The removed device enrollment manager still cannot wipe or retire devices.</span></span>
-   <span data-ttu-id="ba81a-158">O gerenciador de registros de dispositivo removido pode registrar somente um número de dispositivos até o limite por usuário configurado pelo administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="ba81a-158">The removed device enrollment manager can only enroll a number of devices up to the per-user limit configured by the Intune admin.</span></span>

<span data-ttu-id="ba81a-159">**Para remover um gerenciador de registro de dispositivo**</span><span class="sxs-lookup"><span data-stu-id="ba81a-159">**To remove a device enrollment manager**</span></span>

1. <span data-ttu-id="ba81a-160">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-160">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="ba81a-161">Na folha Intune, escolha **Registrar dispositivos** e selecione **Gerenciadores de Registro de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-161">On the Intune blade, choose **Enroll devices**, and then choose **Device Enrollment Managers**.</span></span>
3. <span data-ttu-id="ba81a-162">Na folha **Gerenciadores de Registro de Dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-162">On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Remove**.</span></span>

## <span data-ttu-id="ba81a-163">Exibir as propriedades de um gerenciador de registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ba81a-163">View the properties of a device enrollment manager</span></span>
<a id="view-the-properties-of-a-device-enrollment-manager" class="xliff"></a>

1. <span data-ttu-id="ba81a-164">No portal do Intune, escolha **Registro de dispositivo** e, depois, **Gerentes de Registro de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-164">In the Intune portal, choose **Device enrollment**, and then choose **Device Enrollment Managers**.</span></span>
2. <span data-ttu-id="ba81a-165">Na folha **Gerenciadores de Registro de Dispositivo**, clique com o botão direito do mouse no usuário DEM e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="ba81a-165">On the **Device Enrollment Managers** blade, right-click the DEM user, and select **Properties**.</span></span>
