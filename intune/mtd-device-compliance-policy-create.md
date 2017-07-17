---
title: "Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis com o Intune"
titleSuffix: Intune on Azure
description: "Criar uma política de conformidade de dispositivo de Defesa contra Ameaças Móveis no Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1354d3170f007af2a4bf7f5b2f233a186175c621
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6846c-103">Criar uma política de conformidade de dispositivo de MTD (Defesa contra Ameaças Móveis) com o Intune</span><span class="sxs-lookup"><span data-stu-id="6846c-103">Create Mobile Threat Defense (MTD) device compliance policy with Intune</span></span>
<a id="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune" class="xliff"></a>

<span data-ttu-id="6846c-104">O Intune com MTD ajuda a detectar ameaças e avaliar os riscos em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="6846c-104">Intune with MTD helps you detect threats and assess risk on mobile devices.</span></span> <span data-ttu-id="6846c-105">Você pode criar uma regra de política de conformidade do dispositivo Intune que avalia o risco para determinar se o dispositivo está em conformidade ou não.</span><span class="sxs-lookup"><span data-stu-id="6846c-105">You can create an Intune device compliance policy rule that assesses risk to determine if the device is compliant or not.</span></span> <span data-ttu-id="6846c-106">Em seguida, é possível usar uma política de acesso condicional para bloquear o acesso a serviços de acordo com a conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6846c-106">You can then use a conditional access policy to block access to services based on device compliance.</span></span>

## <span data-ttu-id="6846c-107">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="6846c-107">Before you begin</span></span>
<a id="before-you-begin" class="xliff"></a>

<span data-ttu-id="6846c-108">Como parte da configuração de MTD, no console do parceiro de MTD, foi criada uma política que classifica diversas ameaças como os níveis alto, médio e baixo.</span><span class="sxs-lookup"><span data-stu-id="6846c-108">As part of the MTD setup, in the MTD partner console, you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="6846c-109">Agora é necessário definir o nível de Defesa conta Ameaças Móveis na política de conformidade de dispositivo Intune.</span><span class="sxs-lookup"><span data-stu-id="6846c-109">You now need to set the Mobile Threat Defense level in the Intune device compliance policy.</span></span>

<span data-ttu-id="6846c-110">Pré-requisitos da política de conformidade do dispositivo com MTD:</span><span class="sxs-lookup"><span data-stu-id="6846c-110">Prerequisites for device compliance policy with MTD:</span></span>

-   <span data-ttu-id="6846c-111">Configurar a integração do MTD com o Intune</span><span class="sxs-lookup"><span data-stu-id="6846c-111">Set up MTD integration with Intune</span></span>

-   <span data-ttu-id="6846c-112">Habilitar o conector do MTD no Intune</span><span class="sxs-lookup"><span data-stu-id="6846c-112">Enable the MTD connector in Intune</span></span>

## <span data-ttu-id="6846c-113">Para criar uma política de conformidade de dispositivo MTD</span><span class="sxs-lookup"><span data-stu-id="6846c-113">To create a MTD device compliance policy</span></span>
<a id="to-create-a-mtd-device-compliance-policy" class="xliff"></a>

1.  <span data-ttu-id="6846c-114">Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="6846c-114">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="6846c-115">No **Painel do Azure**, escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="6846c-115">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3.  <span data-ttu-id="6846c-116">Escolha **Intune** e o **Painel do Intune** se abrirá.</span><span class="sxs-lookup"><span data-stu-id="6846c-116">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="6846c-117">No **Painel do Intune**, escolha **Conformidade do dispositivo** e selecione **Políticas** na seção **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="6846c-117">On the **Intune Dashboard**, choose **Device compliance**, then choose **Policies** under the **Manage** section.</span></span>

5.  <span data-ttu-id="6846c-118">Escolha **Criar política**, insira o **Nome** e a **Descrição** da conformidade do dispositivo, selecione a **Plataforma**, escolha **Configurar** na seção **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="6846c-118">Choose **Create policy**, enter the device compliance **Name**, **Description**, select the **Platform**, then choose **Configure** under the **Settings** section.</span></span>

6.  <span data-ttu-id="6846c-119">Na folha **política de conformidade**, escolha **Integridade do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6846c-119">On the **compliance policy** blade, choose **Device Health**.</span></span>

7.  <span data-ttu-id="6846c-120">Na folha **Integridade do Dispositivo**, escolha o Nível de Ameaça Móvel na lista suspensa abaixo de **Exigir que o dispositivo esteja no Nível de Defesa contra Ameaças Móveis ou abaixo dele**.</span><span class="sxs-lookup"><span data-stu-id="6846c-120">On the **Device Health** blade, choose the Mobile Threat Level from the drop-down list under the **Require the device to be at or under the Mobile threat Defense Level**.</span></span>

    <span data-ttu-id="6846c-121">a.</span><span class="sxs-lookup"><span data-stu-id="6846c-121">a.</span></span>  <span data-ttu-id="6846c-122">**Seguro**: este é o mais seguro.</span><span class="sxs-lookup"><span data-stu-id="6846c-122">**Secured**: This is the most secure.</span></span> <span data-ttu-id="6846c-123">O dispositivo não pode ter nenhuma ameaça presente e ainda acessar os recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="6846c-123">The device cannot have any threats present and still access company resources.</span></span> <span data-ttu-id="6846c-124">Se nenhuma ameaça for encontrada, o dispositivo será avaliado como fora de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6846c-124">If any threats are found, the device is evaluated as non-compliant.</span></span>

    <span data-ttu-id="6846c-125">b.</span><span class="sxs-lookup"><span data-stu-id="6846c-125">b.</span></span>  <span data-ttu-id="6846c-126">**Baixo**: o dispositivo estará em conformidade se apenas ameaças de nível baixo estiverem presentes.</span><span class="sxs-lookup"><span data-stu-id="6846c-126">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="6846c-127">Qualquer coisa acima disso coloca o dispositivo no estado de não compatível.</span><span class="sxs-lookup"><span data-stu-id="6846c-127">Anything higher puts the device in a non-compliant status.</span></span>

    <span data-ttu-id="6846c-128">c.</span><span class="sxs-lookup"><span data-stu-id="6846c-128">c.</span></span>  <span data-ttu-id="6846c-129">**Médio**: o dispositivo estará em conformidade se as ameaças encontradas no dispositivo forem de nível baixo ou médio.</span><span class="sxs-lookup"><span data-stu-id="6846c-129">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="6846c-130">Se ameaças de nível alto forem detectadas, o dispositivo será determinado como não compatível.</span><span class="sxs-lookup"><span data-stu-id="6846c-130">If high level threats are detected, the device is determined as non-compliant.</span></span>

    <span data-ttu-id="6846c-131">d.</span><span class="sxs-lookup"><span data-stu-id="6846c-131">d.</span></span>  <span data-ttu-id="6846c-132">**Alto**: esta é a opção menos segura.</span><span class="sxs-lookup"><span data-stu-id="6846c-132">**High**: This is the least secure.</span></span> <span data-ttu-id="6846c-133">Isso permite todos os níveis de ameaça e usa a Defesa contra Ameaças Móveis do Skycure apenas para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="6846c-133">This allows all threat levels, and uses Skycure Mobile Threat Defense for reporting purposes only.</span></span>

8.  <span data-ttu-id="6846c-134">Clique em **OK** duas vezes e escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="6846c-134">Click **OK** twice, then choose **Create**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6846c-135">Se você criar políticas de acesso condicional para o Office 365 ou outros serviços, essa avaliação de conformidade do dispositivo será avaliada e os dispositivos que não estiverem em conformidade serão impedidos de acessar os recursos corporativos até que a ameaça seja resolvida no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6846c-135">If you create conditional access policies for Office 365 or other services, the device compliance evaluation is assessed and non-compliant devices are blocked from accessing corporate resources until the threat is resolved in the device.</span></span>

## <span data-ttu-id="6846c-136">Atribuir uma política de conformidade de dispositivo MTD</span><span class="sxs-lookup"><span data-stu-id="6846c-136">To assign a MTD device compliance policy</span></span>
<a id="to-assign-a-mtd-device-compliance-policy" class="xliff"></a>

<span data-ttu-id="6846c-137">Para atribuir uma política de conformidade de dispositivo aos usuários, escolha uma política previamente configurada por você.</span><span class="sxs-lookup"><span data-stu-id="6846c-137">To assign a device compliance policy to users, choose a policy that you have previously configured.</span></span> <span data-ttu-id="6846c-138">As políticas existentes podem ser encontradas na folha **Políticas de conformidade de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="6846c-138">Existing policies can be found in the **Device Compliance policies** blade.</span></span>

1. <span data-ttu-id="6846c-139">Escolha a política que você deseja atribuir aos usuários e escolha **Atribuições**.</span><span class="sxs-lookup"><span data-stu-id="6846c-139">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="6846c-140">Isso abrirá a folha na qual é possível selecionar **Grupos de segurança do Azure Active Directory** e atribuí-los à política.</span><span class="sxs-lookup"><span data-stu-id="6846c-140">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>

2. <span data-ttu-id="6846c-141">Escolha **Selecionar grupos** para abrir a folha que exibe os grupos de segurança do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6846c-141">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>  <span data-ttu-id="6846c-142">Escolher **Selecionar** implanta a política para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6846c-142">Choosing **Select**  deploys the policy to users.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="6846c-143">Você aplicou a política para os usuários.</span><span class="sxs-lookup"><span data-stu-id="6846c-143">You have applied the policy to users.</span></span> <span data-ttu-id="6846c-144">A conformidade dos dispositivos usados pelos usuários de destino da política será avaliada.</span><span class="sxs-lookup"><span data-stu-id="6846c-144">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>