---
title: "A otimização de energia está impedindo o acesso ao email | Microsoft Docs"
description: "Saiba como desligar a otimização de energia para o Android a fim de assegurar o recebimento de seu email."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d94e3a79af1951debc4dd04413efff8f4c716545
ms.sourcegitcommit: d2a4f4477b3bf90aac6a9db77d41747e64ad7df4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/10/2017
---
<<<<<<< HEAD
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a><span data-ttu-id="85f36-103">O Outlook não sincroniza email gerenciado quando a otimização da bateria para Android está ativada</span><span class="sxs-lookup"><span data-stu-id="85f36-103">Outlook won't sync managed email when battery optimization for Android is turned on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85f36-104">Esse problema é documentado aqui porque temos recebido um maior número de relatórios de cliente sobre ele.</span><span class="sxs-lookup"><span data-stu-id="85f36-104">This issue is documented here because we have been receiving an increased number of customer reports about it.</span></span> <span data-ttu-id="85f36-105">Se depois de executar essas etapas você continuar a experimentar esse problema, entre em contato com [seu administrador de TI](https://portal.manage.microsoft.com) para obter ajuda adicional.</span><span class="sxs-lookup"><span data-stu-id="85f36-105">If you continue to experience this issue after you have taken these steps, contact [your IT admin](https://portal.manage.microsoft.com) for additional help.</span></span>

<span data-ttu-id="85f36-106">Registrar seu dispositivo no Intune permite que você obtenha acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="85f36-106">Enrolling your device in Intune lets you get access to company resources.</span></span> <span data-ttu-id="85f36-107">Um dos recursos mais comuns é o acesso a email.</span><span class="sxs-lookup"><span data-stu-id="85f36-107">One of the most common resources is email access.</span></span> <span data-ttu-id="85f36-108">Um problema que vimos no acesso a email por meio do Outlook para dispositivos Android foi a quando a otimização da bateria é ativada.</span><span class="sxs-lookup"><span data-stu-id="85f36-108">An issue that we have seen with accessing email through Outlook for Android devices has been when battery optimization is turned on.</span></span> <span data-ttu-id="85f36-109">A otimização da bateria pode ser ativada automaticamente para tentar ajudar o seu dispositivo a permanecer ligado pelo máximo de tempo possível.</span><span class="sxs-lookup"><span data-stu-id="85f36-109">Battery optimization may turn on automatically to try to help your device stay powered on for as long as possible.</span></span> <span data-ttu-id="85f36-110">A otimização da bateria é parcialmente capaz de ajudá-lo desse modo, porque ela tenta interromper downloads de email automáticos.</span><span class="sxs-lookup"><span data-stu-id="85f36-110">Battery optimization is partially able to help you this way because it tries to stop automatic email downloads.</span></span>

<span data-ttu-id="85f36-111">A equipe do Microsoft Intune está trabalhando ativamente em uma solução para esse problema.</span><span class="sxs-lookup"><span data-stu-id="85f36-111">The Microsoft Intune team is actively working on a solution for this issue.</span></span> <span data-ttu-id="85f36-112">Uma maneira de impedir que o dispositivo entre no modo de baixa energia é assegurar que a bateria mantenha uma carga maior que 30%.</span><span class="sxs-lookup"><span data-stu-id="85f36-112">One way to prevent the device from entering low power mode is by making sure the battery maintains a charge of greater than 30%.</span></span> <span data-ttu-id="85f36-113">Para impedir que o problema ocorra quando você entra no modo de baixa energia, você deve remover o Portal da Empresa e o Outlook da lista de aplicativos que são afetados pelas configurações de economia de energia e de otimização da bateria.</span><span class="sxs-lookup"><span data-stu-id="85f36-113">To stop the issue from happening when you enter low power mode, you must remove the Company Portal and Outlook from the list of apps that are affected by battery optimization and power saving settings.</span></span>

<span data-ttu-id="85f36-114">Há muitos dispositivos Android, os quais são feitos por vários fabricantes.</span><span class="sxs-lookup"><span data-stu-id="85f36-114">There are many Android devices that are made by many manufacturers.</span></span> <span data-ttu-id="85f36-115">Não é possível documentar as etapas exatas necessárias para cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="85f36-115">We cannot document the exact steps you need to take for every device.</span></span> <span data-ttu-id="85f36-116">Talvez seja necessário executar esta ação apenas em suas configurações de sistema ou também em determinadas configurações específicas do fabricante.</span><span class="sxs-lookup"><span data-stu-id="85f36-116">You may need to take this action in just your system settings or also in certain manufacturer-specific settings.</span></span> <span data-ttu-id="85f36-117">Fornecemos alguns exemplos comuns de como você pode resolver esse problema em dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="85f36-117">We have provided some common examples of how you can resolve this issue on Android devices.</span></span>

## <a name="unmodified-android-devices"></a><span data-ttu-id="85f36-118">Dispositivos Android não modificados</span><span class="sxs-lookup"><span data-stu-id="85f36-118">Unmodified Android devices</span></span>

<span data-ttu-id="85f36-119">Muitos fabricantes adicionam modificações em seus dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="85f36-119">Many manufacturers add modifications to their Android devices.</span></span> <span data-ttu-id="85f36-120">Isso pode alterar determinadas maneiras em que você interage com o dispositivo, assim como os temas e notificações.</span><span class="sxs-lookup"><span data-stu-id="85f36-120">This can change certain ways you interact with the device, like themes and notifications.</span></span> <span data-ttu-id="85f36-121">A Google geralmente não faz esses tipos de modificações nos telefones deles.</span><span class="sxs-lookup"><span data-stu-id="85f36-121">Google generally does not make these types of modifications to their phones.</span></span> <span data-ttu-id="85f36-122">Por exemplo, em um dispositivo Google Pixel com Android 7.0 ou superior, você seguiria estas etapas para remover esses aplicativos de otimização da bateria:</span><span class="sxs-lookup"><span data-stu-id="85f36-122">For example, on a Google Pixel device with Android 7.0 or higher, you would follow these steps to remove these apps from battery optimization:</span></span>

1. <span data-ttu-id="85f36-123">Abra **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="85f36-123">Open **Settings**.</span></span>
2. <span data-ttu-id="85f36-124">Toque em **Bateria** > **Mais** > **Otimização da bateria**.</span><span class="sxs-lookup"><span data-stu-id="85f36-124">Tap **Battery** > **More** > **Battery optimization**.</span></span>
3. <span data-ttu-id="85f36-125">Toque na seta para baixo e, em seguida, em **Não otimizada**.</span><span class="sxs-lookup"><span data-stu-id="85f36-125">Tap the down arrow, then **Not optimized**.</span></span>
4. <span data-ttu-id="85f36-126">Selecione os aplicativos do Portal da Empresa e do Outlook e desligue a otimização da bateria.</span><span class="sxs-lookup"><span data-stu-id="85f36-126">Select the Company Portal and Outlook apps, and turn off battery optimization.</span></span>

## <a name="samsung-devices"></a><span data-ttu-id="85f36-127">Dispositivos Samsung</span><span class="sxs-lookup"><span data-stu-id="85f36-127">Samsung devices</span></span>

<span data-ttu-id="85f36-128">Para outros tipos de dispositivos Android, como dispositivos Samsung com Android 7.0 ou superior, você teria que seguir etapas diferentes para que os aplicativos do Portal da Empresa e do Outlook sejam removidos da otimização da bateria.</span><span class="sxs-lookup"><span data-stu-id="85f36-128">For other types of Android devices, such as Samsung devices with Android 7.0 or higher, you would have to follow different steps to remove the Outlook and Company Portal apps from battery optimization.</span></span>

1. <span data-ttu-id="85f36-129">Abra **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="85f36-129">Open **Settings**.</span></span>
2. <span data-ttu-id="85f36-130">Toque em **Menu (...)** > **Acesso especial** > **Otimizar o uso da bateria**.</span><span class="sxs-lookup"><span data-stu-id="85f36-130">Tap **Menu (…)** > **Special access** > **Optimize battery usage**.</span></span>
3. <span data-ttu-id="85f36-131">Selecione **Todos os aplicativos** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="85f36-131">Select **All apps** from the dropdown.</span></span>
4. <span data-ttu-id="85f36-132">**Desligue** a tecla de alternância ao lado dos aplicativos do Portal da Empresa e do Outlook para desligar a otimização da bateria.</span><span class="sxs-lookup"><span data-stu-id="85f36-132">Turn **Off** the toggle next to the Company Portal and Outlook apps to turn off battery optimization.</span></span>

<span data-ttu-id="85f36-133">Além disso, se você estiver usando um dispositivo Samsung que tem uma versão inferior do Android, você precisará seguir estas etapas para remover esses aplicativos do modo de economia de energia.</span><span class="sxs-lookup"><span data-stu-id="85f36-133">In addition, if you are using a Samsung device that has a lower version of Android, you would need to follow these steps to remove these apps from power saving mode.</span></span>

1. <span data-ttu-id="85f36-134">Abra **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="85f36-134">Open **Settings**.</span></span>
2. <span data-ttu-id="85f36-135">Toque em **Manutenção do dispositivo** > **Bateria** > **Aplicativos sem monitoramento**.</span><span class="sxs-lookup"><span data-stu-id="85f36-135">Tap **Device maintenance** > **Battery** > **Unmonitored apps**.</span></span>
3. <span data-ttu-id="85f36-136">Toque em **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="85f36-136">Tap **Add apps**.</span></span>
4. <span data-ttu-id="85f36-137">Selecione os aplicativos do Portal da Empresa e do Outlook e toque em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="85f36-137">Select the Company Portal and Outlook apps, and tap **Done**.</span></span>

## <a name="oneplus-devices"></a><span data-ttu-id="85f36-138">Dispositivos OnePlus</span><span class="sxs-lookup"><span data-stu-id="85f36-138">OnePlus devices</span></span>

<span data-ttu-id="85f36-139">Outro exemplo de maneira diferente de localizar essas configurações é por meio de pesquisa nas configurações do sistema.</span><span class="sxs-lookup"><span data-stu-id="85f36-139">Another example of a different way to locate these settings is through searching in the system settings.</span></span> <span data-ttu-id="85f36-140">Por exemplo, em um OnePlus 3 com Android 7.1.1, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="85f36-140">For example, on a OnePlus 3 with Android 7.1.1, you would follow these steps:</span></span> 

1. <span data-ttu-id="85f36-141">Abra **Configurações do Sistema**.</span><span class="sxs-lookup"><span data-stu-id="85f36-141">Open **System Settings**.</span></span> 
2. <span data-ttu-id="85f36-142">Toque no botão **Pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="85f36-142">Tap the **Search** button.</span></span> <span data-ttu-id="85f36-143">Isso parece uma lente de aumento na parte superior direita da tela.</span><span class="sxs-lookup"><span data-stu-id="85f36-143">This looks like a magnifying glass at the top right of the screen.</span></span> 
3. <span data-ttu-id="85f36-144">Digite **otimização da bateria** na pesquisa, selecione a opção **Otimização da Bateria** na tela **Configurações** que é exibida.</span><span class="sxs-lookup"><span data-stu-id="85f36-144">Type **battery optimization** into search, then select the **Battery Optimization** option on the **Settings** screen that appears.</span></span> 
4. <span data-ttu-id="85f36-145">Toque em **Bateria** > **Otimização da bateria**.</span><span class="sxs-lookup"><span data-stu-id="85f36-145">Tap **Battery** > **Battery optimization**.</span></span>
5. <span data-ttu-id="85f36-146">Selecione os aplicativos do Portal da Empresa e do Outlook e toque em **Não otimizar**.</span><span class="sxs-lookup"><span data-stu-id="85f36-146">Select the Company Portal and Outlook apps, then select **Don't optimize**.</span></span> <span data-ttu-id="85f36-147">Toque em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="85f36-147">Tap **Done**.</span></span>
=======
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a>O Outlook não sincroniza email gerenciado quando a otimização da bateria para Android está ativada

> [!IMPORTANT]
> Esse problema é documentado aqui porque temos recebido um maior número de relatórios de cliente sobre ele. Se depois de executar essas etapas você continuar a experimentar esse problema, entre em contato com [seu administrador de TI](https://portal.manage.microsoft.com) para obter ajuda adicional.

Registrar seu dispositivo no Intune permite que você obtenha acesso aos recursos da empresa. Um dos recursos mais comuns é o acesso a email. Um problema que vimos no acesso a email por meio do Outlook para dispositivos Android foi a quando a otimização da bateria é ativada. A otimização da bateria pode ser ativada automaticamente para tentar ajudar o seu dispositivo a permanecer ligado pelo máximo de tempo possível. A otimização da bateria é parcialmente capaz de ajudá-lo desse modo, porque ela tenta interromper downloads de email automáticos.

A equipe do Microsoft Intune está trabalhando ativamente em uma solução para esse problema. Uma maneira de impedir que o dispositivo entre no modo de baixa energia é assegurar que a bateria mantenha uma carga maior que 30%. Para impedir que o problema ocorra quando você entra no modo de baixa energia, você deve remover o Portal da Empresa e o Outlook da lista de aplicativos que são afetados pelas configurações de economia de energia e de otimização da bateria.

Há muitos dispositivos Android, os quais são feitos por vários fabricantes. Não é possível documentar as etapas exatas necessárias para cada dispositivo. Talvez seja necessário executar esta ação apenas em suas configurações de sistema ou também em determinadas configurações específicas do fabricante. Fornecemos alguns exemplos comuns de como você pode resolver esse problema em dispositivos Android.

## <a name="unmodified-android-devices"></a>Dispositivos Android não modificados

Muitos fabricantes adicionam modificações em seus dispositivos Android. Isso pode alterar determinadas maneiras em que você interage com o dispositivo, assim como os temas e notificações. A Google geralmente não faz esses tipos de modificações nos telefones deles. Por exemplo, em um dispositivo Google Pixel com Android 7.0 ou superior, você seguiria estas etapas para remover esses aplicativos de otimização da bateria:

1. Abra **Configurações**.
2. Toque em **Bateria** > **Mais** > **Otimização da bateria**.
3. Toque na seta para baixo e, em seguida, em **Não otimizada**.
4. Selecione os aplicativos do Portal da Empresa e do Outlook e desligue a otimização da bateria.

## <a name="samsung-devices"></a>Dispositivos Samsung

Para outros tipos de dispositivos Android, como dispositivos Samsung com Android 7.0 ou superior, você teria que seguir etapas diferentes para que os aplicativos do Portal da Empresa e do Outlook sejam removidos da otimização da bateria.

1. Abra **Configurações**.
2. Toque em **Menu (...)** > **Acesso especial** > **Otimizar o uso da bateria**.
3. Selecione **Todos os aplicativos** na lista suspensa.
4. **Desligue** a tecla de alternância ao lado dos aplicativos do Portal da Empresa e do Outlook para desligar a otimização da bateria.

Além disso, se você estiver usando um dispositivo Samsung que tem uma versão inferior do Android, você precisará seguir estas etapas para remover esses aplicativos do modo de economia de energia.

1. Abra **Configurações**.
2. Toque em **Manutenção do dispositivo** > **Bateria** > **Aplicativos sem monitoramento**.
3. Toque em **Adicionar aplicativos**.
4. Selecione os aplicativos do Portal da Empresa e do Outlook e toque em **Concluído**.

## <a name="oneplus-devices"></a>Dispositivos OnePlus

Outro exemplo de maneira diferente de localizar essas configurações é por meio de pesquisa nas configurações do sistema. Por exemplo, em um OnePlus 3 com Android 7.1.1, siga estas etapas: 

1. Abra **Configurações do Sistema**. 
2. Toque no botão **Pesquisa**. Isso parece uma lente de aumento na parte superior direita da tela. 
3. Digite **otimização da bateria** na pesquisa, selecione a opção **Otimização da Bateria** na tela **Configurações** que é exibida. 
4. Toque em **Bateria** > **Otimização da bateria**.
5. Selecione os aplicativos do Portal da Empresa e do Outlook e toque em **Não otimizar**. Toque em **Concluído**.
>>>>>>> live

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

<<<<<<< HEAD
<span data-ttu-id="85f36-148">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="85f36-148">Still need help?</span></span> <span data-ttu-id="85f36-149">Entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="85f36-149">Contact your IT admin.</span></span> <span data-ttu-id="85f36-150">Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="85f36-150">For their contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
=======
Ainda precisa de ajuda? Entre em contato com o administrador de TI. Para obter suas informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).
>>>>>>> live
