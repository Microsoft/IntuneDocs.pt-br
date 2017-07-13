---
title: Registrar seu dispositivo macOS no Intune | Microsoft Docs
description: Descreve como registrar um dispositivo macOS no Intune
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 02/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 16f7f06d02a56b4887c0d29ffcaed111185652a9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c1cc3-104">Registrar seu dispositivo macOS no Intune</span><span class="sxs-lookup"><span data-stu-id="c1cc3-104">Enroll your macOS device in Intune</span></span>
<a id="enroll-your-macos-device-in-intune" class="xliff"></a>

<span data-ttu-id="c1cc3-105">Obter acesso a aplicativos, dados e recursos da sua organização possibilita fazer seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-105">Getting access to your organization’s apps, data, and resources makes it possible for you to do your job.</span></span> <span data-ttu-id="c1cc3-106">Se estiver usando um dispositivo macOS no trabalho, isso significa instalar um __Perfil de Gerenciamento__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-106">If you're using a macOS device at work, this means installing a __Management Profile__.</span></span> <span data-ttu-id="c1cc3-107">Esse é simplesmente um arquivo configurado pelo seu administrador de TI que carrega as configurações e informações de acesso para seu Mac.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-107">This is simply a file set up by your IT admin that loads settings and access information onto your Mac.</span></span> <span data-ttu-id="c1cc3-108">Quer saber mais?</span><span class="sxs-lookup"><span data-stu-id="c1cc3-108">Want to know more?</span></span> <span data-ttu-id="c1cc3-109">Descubra [o que acontece quando você instala o aplicativo do Portal da Empresa e registra o dispositivo no Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)</span><span class="sxs-lookup"><span data-stu-id="c1cc3-109">Find out [what happens when you install the Company Portal app and enroll your device in Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)</span></span>

  > [!NOTE]
  > <span data-ttu-id="c1cc3-110">Se estiver, de fato, tentando registrar um dispositivo iOS, como um iPhone ou iPad, [tente estas instruções em vez disso](enroll-your-device-in-intune-ios.md).</span><span class="sxs-lookup"><span data-stu-id="c1cc3-110">If you're actually trying to enroll an iOS device, such as an iPhone or iPad, [try these instructions instead](enroll-your-device-in-intune-ios.md).</span></span>

1. <span data-ttu-id="c1cc3-111">Em seu __Encaixe__, localize __Safari__ e abra uma nova janela, em seguida abra o [site de Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c1cc3-111">On your __Dock__, find __Safari__ and open a new window, then open the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
2. <span data-ttu-id="c1cc3-112">Faça logon no Portal da Empresa com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-112">Log into the Company Portal website with your work or school account.</span></span>

  [!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. <span data-ttu-id="c1cc3-113">Ao fazer logon, você verá todas as guias __Início__, __Aplicativos__ e __Categorias__ disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-113">When you log in, you will see any available __Home__, __Apps__, and __Categories__ tabs.</span></span> <span data-ttu-id="c1cc3-114">Essa página mostrará todos os aplicativos disponíveis para instalação.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-114">This page will show whatever apps are available for you to install.</span></span> <span data-ttu-id="c1cc3-115">Se você ainda não tiver dispositivos registrados, verá um aviso que informa **Não é possível mostrar nenhum aplicativo.**</span><span class="sxs-lookup"><span data-stu-id="c1cc3-115">If you do not have any devices enrolled yet, you'll see a notice that says **We can't show you any apps.**</span></span> <span data-ttu-id="c1cc3-116">É possível continuar selecionando __Meus Dispositivos__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-116">You can proceed by selecting __My Devices__.</span></span>

 ![Uma captura de tela da página de aterrissagem do portal da Web com o portal da Web mostrando que nenhum aplicativo pode ser instalado ainda, com um botão Meus Dispositivos abaixo.](./media/macOS_enroll_001_landing_page.png)

4. <span data-ttu-id="c1cc3-118">Na página __Meus Dispositivos__, você verá uma lista de dispositivos registrados ou apenas uma barra de notificação.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-118">On the __My Devices__ page, you will either see a list of enrolled devices or simply a banner.</span></span> <span data-ttu-id="c1cc3-119">Isso depende se você já tiver um dispositivo registrado, macOS ou de outra forma.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-119">This depends on if you already have a device enrolled, macOS or otherwise.</span></span> <span data-ttu-id="c1cc3-120">Para registrar um dispositivo que não está listado, selecione a barra de notificação que informa __Caso seu dispositivo esteja listado, toque aqui para identificá-lo. Também é possível tocar aqui para registrar seu dispositivo se ele não estiver listado__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-120">To enroll a device that is not listed, select the banner that says __If your device is listed, tap here to identify it. You can also tap here to enroll your device if it is not listed__.</span></span>

  ![Uma captura de tela da página Meu Dispositivo, com alguns dispositivos não identificados acima do prompt da barra de notificação para registrar dispositivos não listados ou identificar aqueles não identificados.](./media/macOS_enroll_002_tap_here_banner.png)

5. <span data-ttu-id="c1cc3-122">Uma janela pop-up será exibida com uma breve explicação sobre por que vocês vão __Identificar ou registrar este dispositivo__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-122">A popup window will appear with a brief explanation of why you are going to __Identify or enroll this device__.</span></span> <span data-ttu-id="c1cc3-123">Examine isso, clique em __Registrar__ para continuar.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-123">Review this, then click __Enroll__ to proceed.</span></span>

 ![Identifique ou registre este dispositivo macOS](./media/macOS_enroll_003_IDenroll_popup.png)

6. <span data-ttu-id="c1cc3-125">Uma segunda janela pop-up será exibida com uma breve explicação sobre o que vai acontecer quando __Registrar este dispositivo__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-125">A second popup window will appear with a brief explanation of what will happen when you __Enroll this device__.</span></span> <span data-ttu-id="c1cc3-126">Examine isso, clique em __Instalar__ para continuar.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-126">Review this, then click __Install__ to proceed.</span></span>

 ![Registrar este dispositivo macOS](./media/macOS_enroll_004_enroll_popup.png)

  > [!NOTE]
  > <span data-ttu-id="c1cc3-128">O Intune precisa de acesso ao seu computador para certificar-se de que o dispositivo é seguro o suficiente para acessar recursos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-128">Intune needs access to your computer to make sure that your device is secure enough to access your organization's resources.</span></span> <span data-ttu-id="c1cc3-129">Descubra [o que acontece quando você registra seu dispositivo no Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).</span><span class="sxs-lookup"><span data-stu-id="c1cc3-129">Find out [what happens when you enroll your device in Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).</span></span>

7. <span data-ttu-id="c1cc3-130">As __Preferências do Sistema__ serão abertas e perguntarão se deseja __Instalar "Perfil de Gerenciamento"?__</span><span class="sxs-lookup"><span data-stu-id="c1cc3-130">__System Preferences__ will open, and ask you if you want to __Install "Management Profile"?__</span></span> <span data-ttu-id="c1cc3-131">Clique em __Instalar__ para continuar ou obtenha mais detalhes clicando __Mostrar Perfil__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-131">Click __Install__ to proceed, or get more details by clicking __Show Profile__.</span></span>

 ![Instalar o Perfil de Gerenciamento](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. <span data-ttu-id="c1cc3-133">Será exibida uma janela pop-up do macOS.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-133">A macOS popup window will appear.</span></span> <span data-ttu-id="c1cc3-134">Confirme que deseja fazer alterações, fornecendo o __nome de usuário__ e __senha__ do computador, em seguida, clicando em __OK__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-134">Confirm that you want to make changes by providing your computer's __User Name__ and __Password__, then clicking __OK__.</span></span> <span data-ttu-id="c1cc3-135">Isso instalará o perfil de gerenciamento em seu Mac.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-135">This will install the management profile onto your Mac.</span></span>

 ![Janela pop-up de Instalação do Perfil macOS](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. <span data-ttu-id="c1cc3-137">Você pode ver algumas mensagens adicionais do seu Mac com mais detalhes sobre o perfil ou se tem certeza de que deseja __Instalar__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-137">You may see some additional messages from your Mac with more details about the profile, or whether you're sure that you want to __Install__.</span></span> <span data-ttu-id="c1cc3-138">Clique em __Continuar__ e __Instalar__ por meio desses para continuar.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-138">Click __Continue__ and __Install__ through these to proceed.</span></span> <span data-ttu-id="c1cc3-139">Depois que a instalação for concluída, você poderá exibir seu recém-instalado __Perfil de Gerenciamento__ na lista de __Perfis de Dispositivo__.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-139">Once the installation finishes, you will be able to view your newly-installed __Management Profile__ in the list of __Device Profiles__.</span></span>

 ![Perfil macOS Instalado](./media/macOS_enroll_007_sysprefs_installed_profile.png)

<span data-ttu-id="c1cc3-141">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="c1cc3-141">Still need help?</span></span> <span data-ttu-id="c1cc3-142">Faça o check-in com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="c1cc3-142">Check in with your IT administrator.</span></span> <span data-ttu-id="c1cc3-143">Você pode encontrar as informações de contato deles no [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c1cc3-143">You can find their contact information on the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
