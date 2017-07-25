---
title: "Introdução às políticas"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 232ec25c34df5e71f70737ca5f0f8a2ef12a05f0
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="b4cff-102">Introdução às políticas</span><span class="sxs-lookup"><span data-stu-id="b4cff-102">Getting started with policies</span></span>
<a id="getting-started-with-policies" class="xliff"></a>

<span data-ttu-id="b4cff-103">Uma das principais metas do guia de introdução do Intune é registrar dispositivos para verificar se eles estão em conformidade com as políticas corporativas.</span><span class="sxs-lookup"><span data-stu-id="b4cff-103">One of the main goals of getting started with Intune is enrolling devices to make sure that they are compliant with corporate policies.</span></span> <span data-ttu-id="b4cff-104">Políticas de conformidade não apenas ajudam a gerenciar os tipos de dispositivos especializados, como quiosques corporativos, mas também dispositivos pessoais (Traga seu próprio), tablets e dispositivos sem usuário.</span><span class="sxs-lookup"><span data-stu-id="b4cff-104">Compliance policies not only help you to manage specialized device types, such as corporate-owned kiosks, but also personal (Bring Your Own) devices, tablets, and user-less devices.</span></span>

![Painel de conformidade com pouquíssimos dados](/intune/media/generic-compliance-dashboard.png)

<span data-ttu-id="b4cff-106">As políticas de conformidade oferecem os seguintes recursos de gerenciamento para dispositivos móveis:</span><span class="sxs-lookup"><span data-stu-id="b4cff-106">Compliance policies provide the following management capabilities for mobile devices:</span></span>

* <span data-ttu-id="b4cff-107">Regule os números de dispositivos que cada usuário registra</span><span class="sxs-lookup"><span data-stu-id="b4cff-107">Regulate numbers of devices each user enrolls</span></span>
* <span data-ttu-id="b4cff-108">Gerenciar configurações de dispositivos (como por exemplo criptografia no nível do dispositivo, tamanho da senha e uso de câmera)</span><span class="sxs-lookup"><span data-stu-id="b4cff-108">Manage devices settings (e.g. device-level encryption, password length, camera usage)</span></span>
* <span data-ttu-id="b4cff-109">Entrega de aplicativos, perfis de email, perfis de VPN etc.</span><span class="sxs-lookup"><span data-stu-id="b4cff-109">Deliver apps, email profiles, VPN profiles, etc.</span></span>
* <span data-ttu-id="b4cff-110">Avaliar critérios no nível do dispositivo para as políticas de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="b4cff-110">Evaluate device-level criteria for security compliance policies</span></span>

<span data-ttu-id="b4cff-111">Crie políticas de conformidade para cada plataforma separadamente.</span><span class="sxs-lookup"><span data-stu-id="b4cff-111">You create compliance policies for each platform separately.</span></span> <span data-ttu-id="b4cff-112">Para este exercício, continuaremos com o iOS.</span><span class="sxs-lookup"><span data-stu-id="b4cff-112">For this exercise, we’ll stick to iOS.</span></span> <span data-ttu-id="b4cff-113">As seguintes políticas estão disponíveis para dispositivos iOS:</span><span class="sxs-lookup"><span data-stu-id="b4cff-113">The following policies are available for iOS devices:</span></span>

* <span data-ttu-id="b4cff-114">Configuração de senha ou PIN</span><span class="sxs-lookup"><span data-stu-id="b4cff-114">PIN or password configuration</span></span>
* <span data-ttu-id="b4cff-115">Criptografia de dispositivo</span><span class="sxs-lookup"><span data-stu-id="b4cff-115">Device encryption</span></span>
* <span data-ttu-id="b4cff-116">Dispositivo com jailbreak</span><span class="sxs-lookup"><span data-stu-id="b4cff-116">Jailbroken device</span></span>
* <span data-ttu-id="b4cff-117">Perfil de email</span><span class="sxs-lookup"><span data-stu-id="b4cff-117">Email profile</span></span>
* <span data-ttu-id="b4cff-118">Versão mínima do SO</span><span class="sxs-lookup"><span data-stu-id="b4cff-118">Minimum OS version</span></span>
* <span data-ttu-id="b4cff-119">Versão máxima do SO</span><span class="sxs-lookup"><span data-stu-id="b4cff-119">Maximum OS version</span></span>

<span data-ttu-id="b4cff-120">__Como crio uma política?__</span><span class="sxs-lookup"><span data-stu-id="b4cff-120">__How do I create a policy?__</span></span>

1. <span data-ttu-id="b4cff-121">Entre no [Portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b4cff-121">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="b4cff-122">**Pesquisar recursos**, pesquise por **Intune**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-122">**Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="b4cff-123">Selecione **Conformidade do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-123">Select **Device compliance**.</span></span>
4. <span data-ttu-id="b4cff-124">Na folha **Conformidade do dispositivo**, selecione **Políticas**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-124">On the **Device compliance** blade, select **Policies**.</span></span>
5. <span data-ttu-id="b4cff-125">Selecione **Criar Política** e preencha os detalhes como **Nome** e **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-125">Select **Create Policy**, then fill in the details, like **Name** and **Description**.</span></span> <span data-ttu-id="b4cff-126">Escolha **iOS** como a **Plataforma**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-126">Choose **iOS** as the **Platform**.</span></span>
6. <span data-ttu-id="b4cff-127">Em **Configurações**, selecione **Segurança do Sistema** e alterne **Exigir uma senha para desbloquear os dispositivos móveis** para **Exigir**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-127">In **Settings**, select **System Security**, then toggle **Require a password to unlock mobile devices** to **Require**.</span></span> <span data-ttu-id="b4cff-128">Também é possível definir outras regras, como **Tamanho mínimo da senha**, **Tipo de senha exigido** e **Número de caracteres não alfanuméricos na senha**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-128">You can also set other rules, such as **Minimum password length**, **Required password type**, and **Number of non-alphanumeric characters in password**.</span></span> <span data-ttu-id="b4cff-129">Após terminar de configurar a política, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-129">When you’ve finished setting up your policy, select **OK**.</span></span>
7. <span data-ttu-id="b4cff-130">Volte para a folha **Criar política** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-130">Return to the **Create policy** blade, then select **Create**.</span></span>
8. <span data-ttu-id="b4cff-131">Depois de criar a política, selecione **Atribuições** para atribuí-la ao seu grupo de teste.</span><span class="sxs-lookup"><span data-stu-id="b4cff-131">Once the policy is created, select **Assignments** to assign it to your test group.</span></span> <span data-ttu-id="b4cff-132">Selecione o grupo de teste – que deve conter seu usuário de teste – e atribua a política a esse grupo clicando em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-132">Select your test group – which should have your test user in it – then assign the policy to that group by clicking **Save**.</span></span>
9. <span data-ttu-id="b4cff-133">Aguarde alguns minutos e seu dispositivo registrado deverá solicitar uma senha atualizada para permanecer em conformidade com as políticas corporativas.</span><span class="sxs-lookup"><span data-stu-id="b4cff-133">Wait a few minutes, then your enrolled device should prompt you that it needs an updated password in order to remain compliant with corporate policy.</span></span> <span data-ttu-id="b4cff-134">Você pode verificar manualmente isso no **aplicativo de Portal da Empresa para iOS** tocando no nome do dispositivo e no botão **Sincronizar**.</span><span class="sxs-lookup"><span data-stu-id="b4cff-134">You can also manually check for this in the **Company Portal app for iOS** by tapping on the device name, then the **Sync** button.</span></span>
=======
# Introdução às políticas
<a id="getting-started-with-policies" class="xliff"></a>

Uma das principais metas do guia de introdução do Intune é registrar dispositivos para verificar se eles estão em conformidade com as políticas corporativas. Políticas de conformidade não apenas ajudam a gerenciar os tipos de dispositivos especializados, como quiosques corporativos, mas também dispositivos pessoais (Traga seu próprio), tablets e dispositivos sem usuário.

![Painel de conformidade com pouquíssimos dados](/intune/media/generic-compliance-dashboard.png)

As políticas de conformidade oferecem os seguintes recursos de gerenciamento para dispositivos móveis:

* Regule os números de dispositivos que cada usuário registra
* Gerenciar configurações de dispositivos (como por exemplo criptografia no nível do dispositivo, tamanho da senha e uso de câmera)
* Entrega de aplicativos, perfis de email, perfis de VPN etc.
* Avaliar critérios no nível do dispositivo para as políticas de conformidade de segurança

Crie políticas de conformidade para cada plataforma separadamente. Para este exercício, continuaremos com o iOS. As seguintes políticas estão disponíveis para dispositivos iOS:

* Configuração de senha ou PIN
* Criptografia de dispositivo
* Dispositivo com jailbreak
* Perfil de email
* Versão mínima do SO
* Versão máxima do SO

__Como crio uma política?__

1. Entre no [Portal do Azure](https://portal.azure.com).
2. **Pesquisar recursos**, pesquise por **Intune**.
3. Selecione **Conformidade do dispositivo**.
4. Na folha **Conformidade do dispositivo**, selecione **Políticas**.
5. Selecione **Criar Política** e preencha os detalhes como **Nome** e **Descrição**. Escolha **iOS** como a **Plataforma**.
6. Em **Configurações**, selecione **Segurança do Sistema** e alterne **Exigir uma senha para desbloquear os dispositivos móveis** para **Exigir**. Também é possível definir outras regras, como **Tamanho mínimo da senha**, **Tipo de senha exigido** e **Número de caracteres não alfanuméricos na senha**. Após terminar de configurar a política, selecione **OK**.
7. Volte para a folha **Criar política** e selecione **Criar**.
8. Depois de criar a política, selecione **Atribuições** para atribuí-la ao seu grupo de teste. Selecione o grupo de teste – que deve conter seu usuário de teste – e atribua a política a esse grupo clicando em **Salvar**.
9. Aguarde alguns minutos e seu dispositivo registrado deverá solicitar uma senha atualizada para permanecer em conformidade com as políticas corporativas. Você pode verificar manualmente isso no **aplicativo de Portal da Empresa para iOS** tocando no nome do dispositivo e no botão **Sincronizar**.
>>>>>>> live
