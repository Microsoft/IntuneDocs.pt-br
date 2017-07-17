---
title: "Definir restrições de registro no Intune"
titleSuffix: Intune on Azure
description: Restrinja o registro pela plataforma e defina um limite de registro de dispositivo no Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2dfcba8c788f262ce816dcd23dc2921fd57f331b
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <span data-ttu-id="d8433-104">Definir restrições de registro</span><span class="sxs-lookup"><span data-stu-id="d8433-104">Set enrollment restrictions</span></span>
<a id="set-enrollment-restrictions" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d8433-105">Como um administrador do Intune, você pode determinar quais dispositivos podem ser registrados para gerenciamento com o Intune.</span><span class="sxs-lookup"><span data-stu-id="d8433-105">As an Intune admin, you can determine which devices can enroll into management with Intune.</span></span> <span data-ttu-id="d8433-106">Use o Portal do Intune para definir as seguintes restrições para o registro de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d8433-106">Use the Intune portal to set the following restrictions for device enrollment:</span></span>

- <span data-ttu-id="d8433-107">Número máximo de dispositivos registrados</span><span class="sxs-lookup"><span data-stu-id="d8433-107">Maximum number of enrolled devices</span></span>
- <span data-ttu-id="d8433-108">Plataformas de dispositivo que podem ser registradas:</span><span class="sxs-lookup"><span data-stu-id="d8433-108">Device platforms that can enroll:</span></span>
  - <span data-ttu-id="d8433-109">Android</span><span class="sxs-lookup"><span data-stu-id="d8433-109">Android</span></span>
  - <span data-ttu-id="d8433-110">iOS</span><span class="sxs-lookup"><span data-stu-id="d8433-110">iOS</span></span>
  - <span data-ttu-id="d8433-111">macOS</span><span class="sxs-lookup"><span data-stu-id="d8433-111">macOS</span></span>
  - <span data-ttu-id="d8433-112">Windows</span><span class="sxs-lookup"><span data-stu-id="d8433-112">Windows</span></span>
- <span data-ttu-id="d8433-113">Restringir dispositivos pessoais (somente Android e iOS)</span><span class="sxs-lookup"><span data-stu-id="d8433-113">Restrict personally owned devices (iOS and Android only)</span></span>

>[!NOTE]
><span data-ttu-id="d8433-114">Restrições de registro não são um recurso de segurança.</span><span class="sxs-lookup"><span data-stu-id="d8433-114">Enrollment restrictions are not a security feature.</span></span> <span data-ttu-id="d8433-115">Dispositivos comprometidos podem falsificar a identidade.</span><span class="sxs-lookup"><span data-stu-id="d8433-115">Compromised devices can misrepresent their character.</span></span> <span data-ttu-id="d8433-116">Tais restrições são uma barreira de melhor esforço para usuários que não são mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="d8433-116">These restrictions are a best-effort barrier for non-malicious users.</span></span>

## <span data-ttu-id="d8433-117">Definir restrições de tipo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d8433-117">Set device type restrictions</span></span>
<a id="set-device-type-restrictions" class="xliff"></a>
<span data-ttu-id="d8433-118">As restrições de registro padrão se aplicam a todos os usuários que não receberam restrições de registro de prioridade mais altas.</span><span class="sxs-lookup"><span data-stu-id="d8433-118">The default enrollment restrictions apply to all users who aren't assigned higher priority enrollment restrictions.</span></span>  
1. <span data-ttu-id="d8433-119">No Portal do Intune, escolha **Registro de dispositivo** e **Restrições de registro**.</span><span class="sxs-lookup"><span data-stu-id="d8433-119">In the Intune portal, choose **Device enrollment**, choose **Enrollment restrictions**.</span></span>
<span data-ttu-id="d8433-120">![Captura de tela do espaço de trabalho de restrições de dispositivo com as restrições de tipo de dispositivo padrão e restrições de limite de dispositivo.](media/device-restrictions-set-default.png)</span><span class="sxs-lookup"><span data-stu-id="d8433-120">![Screenshot of the device restrictions workspace with the default device type restrictions and device limit restrictions.](media/device-restrictions-set-default.png)</span></span>
2. <span data-ttu-id="d8433-121">Em **Restrições de registro** > **Restrições de Tipo de Dispositivo**, selecione **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="d8433-121">Under **Enrollment restrictions** > **Device Type Restrictions**, select **Default**.</span></span>
3. <span data-ttu-id="d8433-122">Em **Todos os Usuários**, selecione **Plataformas**.</span><span class="sxs-lookup"><span data-stu-id="d8433-122">Under **All Users**, select **Platforms**.</span></span> <span data-ttu-id="d8433-123">Escolha **Permitir** ou **Bloquear** para cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="d8433-123">Choose **Allow** or **Block** for each platform:</span></span>
  - <span data-ttu-id="d8433-124">**Android**</span><span class="sxs-lookup"><span data-stu-id="d8433-124">**Android**</span></span>
  - <span data-ttu-id="d8433-125">**iOS**</span><span class="sxs-lookup"><span data-stu-id="d8433-125">**iOS**</span></span>
  - <span data-ttu-id="d8433-126">**macOS**</span><span class="sxs-lookup"><span data-stu-id="d8433-126">**macOS**</span></span>
  - <span data-ttu-id="d8433-127">**Windows**</span><span class="sxs-lookup"><span data-stu-id="d8433-127">**Windows**</span></span>

  <span data-ttu-id="d8433-128">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8433-128">Click **Save**.</span></span>
4. <span data-ttu-id="d8433-129">Em **Todos os Usuários**, selecione **Configurações de Plataforma** e selecione as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="d8433-129">Under **All Users**, select **Platform Configurations** and select the following configurations:</span></span>
  - <span data-ttu-id="d8433-130">**Propriedade Pessoal** – Especifique se deseja **Permitir** ou **Bloquear** para dispositivos Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="d8433-130">**Personally Owned** - Specify whether to **Allow** or **Block** for Android and iOS devices.</span></span>
  <span data-ttu-id="d8433-131">![Captura de tela de espaço de trabalho de restrições de dispositivo com as configurações de plataforma de dispositivo padrão mostrando as configurações de propriedade pessoal definidas.](media/device-restrictions-platform-configurations.png)</span><span class="sxs-lookup"><span data-stu-id="d8433-131">![Screenshot of the device restrictions workspace with the default device platform configurations showing personally owned settings configured.](media/device-restrictions-platform-configurations.png)</span></span>
  <span data-ttu-id="d8433-132">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8433-132">Click **Save**.</span></span>

>[!NOTE]
><span data-ttu-id="d8433-133">Se você impedir o registro de dispositivos pessoais Android, dispositivos Android for Work ainda poderão ser registrados.</span><span class="sxs-lookup"><span data-stu-id="d8433-133">If you block personally owned Android devices from enrollment, Android for Work devices can still be enrolled.</span></span>

## <span data-ttu-id="d8433-134">Definir restrições de limite de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d8433-134">Set device limit restrictions</span></span>
<a id="set-device-limit-restrictions" class="xliff"></a>
<span data-ttu-id="d8433-135">As restrições de registro padrão se aplicam a todos os usuários que não receberam restrições de registro de prioridade mais altas.</span><span class="sxs-lookup"><span data-stu-id="d8433-135">The default enrollment restrictions apply to all users who aren't assigned higher priority enrollment restrictions.</span></span>  
1. <span data-ttu-id="d8433-136">No Portal do Intune, escolha **Registro de dispositivo** e **Restrições de registro**.</span><span class="sxs-lookup"><span data-stu-id="d8433-136">In the Intune portal, choose **Device enrollment**, choose **Enrollment restrictions**.</span></span>
2. <span data-ttu-id="d8433-137">Escolha **Restrições de registro** > **Restrições de limite de dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="d8433-137">Choose **Enrollment restrictions** > **Device Limit Restrictions**.</span></span>
3. <span data-ttu-id="d8433-138">Em **Todos os Usuários**, selecione **Limite de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="d8433-138">Under **All Users**, select **Device Limit**.</span></span> <span data-ttu-id="d8433-139">Especifique o número máximo de dispositivos registrados por usuário.</span><span class="sxs-lookup"><span data-stu-id="d8433-139">Specify the maximum number of enrolled devices per user.</span></span>  
<span data-ttu-id="d8433-140">![Captura de tela da folha de restrições de limite de dispositivo com as restrições de limite de dispositivo.](./media/device-restrictions-limit.png)</span><span class="sxs-lookup"><span data-stu-id="d8433-140">![Screenshot of the device limit restrictions blade with the device limit restrictions.](./media/device-restrictions-limit.png)</span></span>

  <span data-ttu-id="d8433-141">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8433-141">Click **Save**.</span></span>
