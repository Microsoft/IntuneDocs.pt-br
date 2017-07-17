---
title: "Adicionar números de série do Apple Configurator"
titleSuffix: Intune on Azure
description: "Saiba como adicionar números de série a dispositivos iOS de propriedade corporativa usando o Apple Configurator."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 689008f278e676ce0bab075c6ad6b54748e56313
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="da596-103">Adicionar números de série do Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="da596-103">Add Apple Configurator serial numbers</span></span>
<a id="add-apple-configurator-serial-numbers" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="da596-104">Use estas etapas para adicionar números de série ao Intune quando quiser [registrar dispositivos iOS corporativos usando o Apple Configurator com o Assistente de Configuração](apple-configurator-setup-assistant-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="da596-104">Use these steps to add serial numbers to Intune when you want to [enroll corporate-owned iOS devices by using Apple Configurator with Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md).</span></span> <span data-ttu-id="da596-105">Você pode adicionar números de série um por vez ou carregar um arquivo de valores de separados por vírgula (CSV) dos números de série.</span><span class="sxs-lookup"><span data-stu-id="da596-105">You can add serial numbers one at a time, or upload a comma-separated-value (CSV) file of serial numbers.</span></span> <span data-ttu-id="da596-106">Depois de adicionar os números de série, você poderá atribuir um perfil para eles.</span><span class="sxs-lookup"><span data-stu-id="da596-106">After you add serial numbers, you can assign a profile to them.</span></span> <span data-ttu-id="da596-107">O perfil contém as configurações de gerenciamento específicas que você deseja aplicar aos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="da596-107">The profile contains specific management settings that you want to apply to devices.</span></span>

<span data-ttu-id="da596-108">Outros métodos de registrar dispositivos iOS são descritos em [Escolher como registrar dispositivos iOS no Intune](enrollment-method-choose-ios.md).</span><span class="sxs-lookup"><span data-stu-id="da596-108">Other methods of enrolling iOS devices are described in [Choose how to enroll iOS devices in Intune](enrollment-method-choose-ios.md).</span></span>

<span data-ttu-id="da596-109">**Para adicionar números de série do Apple Configurator ao Intune**</span><span class="sxs-lookup"><span data-stu-id="da596-109">**To add Apple Configurator serial numbers to Intune**</span></span>

1. <span data-ttu-id="da596-110">Crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="da596-110">Create a two-column, comma-separated value (.csv) list without a header.</span></span> <span data-ttu-id="da596-111">Adicione o identificador IMEI à coluna esquerda e os detalhes à coluna direita.</span><span class="sxs-lookup"><span data-stu-id="da596-111">Add the IMEI identifier in the left column, and the details in the right column.</span></span> <span data-ttu-id="da596-112">O máximo atual para a lista é de 500 linhas.</span><span class="sxs-lookup"><span data-stu-id="da596-112">The current maximum for the list is 500 rows.</span></span> <span data-ttu-id="da596-113">Em um editor de texto, a lista .csv é semelhante a:</span><span class="sxs-lookup"><span data-stu-id="da596-113">In a text editor, the .csv list looks something like this:</span></span>

    <span data-ttu-id="da596-114">F7TLWCLBX196, detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="da596-114">F7TLWCLBX196,device details</span></span></br>
    <span data-ttu-id="da596-115">DLXQPCWVGHMJ, detalhes do dispositivo</span><span class="sxs-lookup"><span data-stu-id="da596-115">DLXQPCWVGHMJ,device details</span></span>

2. <span data-ttu-id="da596-116">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="da596-116">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

3.  <span data-ttu-id="da596-117">Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.</span><span class="sxs-lookup"><span data-stu-id="da596-117">On the Intune blade, choose **Enroll devices**, and then choose **Apple Enrollment**.</span></span>

4. <span data-ttu-id="da596-118">Em **Gerenciar configurações de registro do Apple Configurator**, selecione **Números de Série do Apple Configurator**.</span><span class="sxs-lookup"><span data-stu-id="da596-118">Under **Manage Apple Configurator Enrollment Settings**, select **Apple Configurator Serial Numbers**.</span></span>

5. <span data-ttu-id="da596-119">Na folha **Números de Série do Apple Configurator**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="da596-119">On the **Apple Configurator Serial Numbers** blade, select **Add**.</span></span>

6. <span data-ttu-id="da596-120">Na folha **Adicionar números de série**, selecione um perfil para aplicar a números de série que você está importando.</span><span class="sxs-lookup"><span data-stu-id="da596-120">On the **Add Serial Numbers** blade, select a profile to apply to the serial numbers you're importing.</span></span> <span data-ttu-id="da596-121">Se você estiver importando um arquivo com novos detalhes que substituirão os existentes, selecione Substituir os detalhes para os identificadores existentes para que os novos detalhes substituam os existentes.</span><span class="sxs-lookup"><span data-stu-id="da596-121">If you are importing a file with new details that will overwrite the existing ones, select Overwrite details for existing identifiers to have the new details replace the existing details.</span></span>

7. <span data-ttu-id="da596-122">Navegue até o arquivo .csv de números de série e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="da596-122">Navigate to the .csv file of serial numbers, and select **Add**.</span></span>

## <span data-ttu-id="da596-123">Atribuir um perfil números de série específicos</span><span class="sxs-lookup"><span data-stu-id="da596-123">Assign a profile to specific serial numbers</span></span>
<a id="assign-a-profile-to-specific-serial-numbers" class="xliff"></a>

<span data-ttu-id="da596-124">O Intune permite atribuir perfis de dois locais diferentes no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="da596-124">Intune lets you assign profiles from two different places in the Azure portal.</span></span> <span data-ttu-id="da596-125">Você pode usar as etapas a seguir ou pode atribuir perfis na folha Perfis de Registro do Apple Configurator, na qual você cria o perfil (consulte [Registrar dispositivos iOS com Apple Configurator usando o Assistente de configuração](apple-configurator-setup-assistant-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="da596-125">You can use the steps below, or you can assign profiles from the Apple Configurator Enrollment Profiles blade, which is where you create the profile (see [Enroll iOS devices with Apple Configurator by using Setup Assistant](apple-configurator-setup-assistant-enroll-ios.md).</span></span> <span data-ttu-id="da596-126">Use as etapas a seguir para atribuir o perfil somente se você já o criou.</span><span class="sxs-lookup"><span data-stu-id="da596-126">You can use the steps below to assign the profile only if you have already created the profile.</span></span>

1. <span data-ttu-id="da596-127">No portal do Azure, selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="da596-127">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="da596-128">Na folha Intune, escolha **Registrar dispositivos** e escolha **Registro Apple**.</span><span class="sxs-lookup"><span data-stu-id="da596-128">On the Intune blade, choose **Enroll devices**, and then choose **Apple Enrollment**.</span></span>

3. <span data-ttu-id="da596-129">Na folha **Números de série do Apple Configurator**, selecione os números de série que você deseja atribuir a um perfil e, em seguida, selecione **Atribuir Perfil**.</span><span class="sxs-lookup"><span data-stu-id="da596-129">On the **Apple Configurator Serial Numbers** blade, select the serial numbers you want to assign a profile to, and then select **Assign Profile**.</span></span>

4. <span data-ttu-id="da596-130">Na folha **Atribuir Perfil**, selecione o perfil que você deseja atribuir e selecione **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="da596-130">On the **Assign Profile** blade, select the profile you want to assign, and then select **Assign**.</span></span>

## <span data-ttu-id="da596-131">Excluir números de série</span><span class="sxs-lookup"><span data-stu-id="da596-131">Delete serial numbers</span></span>
<a id="delete-serial-numbers" class="xliff"></a>
<span data-ttu-id="da596-132">Você pode excluir os números de série importados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="da596-132">You can delete serial numbers that you imported previously.</span></span> <span data-ttu-id="da596-133">Você poderá excluir os números de série apenas se o registro do dispositivo for cancelado primeiro.</span><span class="sxs-lookup"><span data-stu-id="da596-133">You can delete serial numbers only if the device is unenrolled first.</span></span> <span data-ttu-id="da596-134">Quando você remove um número de série, não é possível usar o Apple Configurator por meio do Assistente de configuração, a menos que você adicione novamente o número de série.</span><span class="sxs-lookup"><span data-stu-id="da596-134">Once you remove a serial number, you can’t use Apple Configurator via Setup Assistant unless you re-add the serial number.</span></span>

## <span data-ttu-id="da596-135">Exibir o estado de um dispositivo</span><span class="sxs-lookup"><span data-stu-id="da596-135">View the state of a device</span></span>
<a id="view-the-state-of-a-device" class="xliff"></a>
<span data-ttu-id="da596-136">Os números de série do dispositivo pode ter um dos dois estados:</span><span class="sxs-lookup"><span data-stu-id="da596-136">The device serial numbers can have one of two states:</span></span>

- <span data-ttu-id="da596-137">Registrado – o dispositivo é registrado e se conectou ao serviço do Intune</span><span class="sxs-lookup"><span data-stu-id="da596-137">Enrolled - the device is enrolled, and it has connected to the Intune service</span></span>
- <span data-ttu-id="da596-138">Não Contatado – o dispositivo nunca se conectou ao serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="da596-138">Not Contacted - the device has never connected to the Intune service.</span></span>
- <span data-ttu-id="da596-139">Redefinição pendente – o dispositivo foi registrado, mas uma alteração foi feita (por exemplo, configurações do registro ou o perfil DEP aplicado foi alterado).</span><span class="sxs-lookup"><span data-stu-id="da596-139">Pending Reset - the device is enrolled, but a change has been made (for example, enrollment settings or the applied DEP profile have changed).</span></span> <span data-ttu-id="da596-140">Se você alterar o perfil DEP de um dispositivo, as alterações não serão aplicadas até que o dispositivo seja cancelado e, em seguida, registrado novamente.</span><span class="sxs-lookup"><span data-stu-id="da596-140">If you change the DEP profile of a device, the changes are not applied until the device is unenrolled, and then re-enrolled.</span></span>

<span data-ttu-id="da596-141">**Para exibir o estado de um número de série**</span><span class="sxs-lookup"><span data-stu-id="da596-141">**To view the state of a serial number**</span></span>

<span data-ttu-id="da596-142">Na folha **Números de Série do Apple Configurator**, selecione o número de série cujo estado você deseja ver e procure o item **Estado**.</span><span class="sxs-lookup"><span data-stu-id="da596-142">On the **Apple Configurator Serial Numbers** blade, select the serial number whose state you want to see, and look under the **State** item.</span></span>
