---
title: Registrar seu dispositivo Windows 10 no Intune | Microsoft Docs
description: Registrar um dispositivo Windows 10 1607 ou superior no Intune
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: aa12a88cfd80f62e2f7b249b52333bd16cbb6533
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="af263-103">Registrar seu dispositivo Windows 10 no Intune</span><span class="sxs-lookup"><span data-stu-id="af263-103">Enroll your Windows 10 device in Intune</span></span>
<a id="enroll-your-windows-10-device-in-intune" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="af263-104">O Windows 10 opera em todos os tipos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="af263-104">Windows 10 works across all types of devices.</span></span> <span data-ttu-id="af263-105">Esteja você usando uma área de trabalho, um telefone ou tablet, as etapas a seguir serão as mesmas – mesmo se elas parecerem um pouco diferentes das imagens nesta página.</span><span class="sxs-lookup"><span data-stu-id="af263-105">Whether you're using a desktop, phone, or tablet, the steps you follow are the same - even if they look slightly different from the images on this page.</span></span>

<iframe src="https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player" width="960" height="540" allowFullScreen frameBorder="0"></iframe>

1. <span data-ttu-id="af263-106">Vá até **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="af263-106">Go to **Start**.</span></span>

  - <span data-ttu-id="af263-107">Se você estiver usando um dispositivo **Windows 10 Desktop**, acesse o **Menu Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="af263-107">If you are on a **Windows 10 desktop** device, go to the **Start menu**.</span></span>
  - <span data-ttu-id="af263-108">Se você estiver usando um dispositivo **Windows 10 Mobile**, acesse a **Tela inicial** e, em seguida, passe para a lista **Todos os aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="af263-108">If you are on a **Windows 10 Mobile** device, go to the **Start screen**, then swipe to the **All Apps** list.</span></span>

2.  <span data-ttu-id="af263-109">Abra o aplicativo **Configurações** do Windows, pesquisando por "configurações" na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="af263-109">Open the Windows **Settings** app by searching for "settings" in the search bar.</span></span>

3. <span data-ttu-id="af263-110">Selecione **Contas** > **Acessar trabalho ou escola** > **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="af263-110">Select **Accounts** > **Access work or school** > **Connect**.</span></span>

    ![Selecione Acessar conta corporativa ou de estudante](./media/w10-enroll-rs1-connect-to-work-or-school.png)

3.  <span data-ttu-id="af263-112">Insira seu endereço de email corporativo ou de estudante e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="af263-112">Enter your work or school email address, and then select **Next**.</span></span>

    ![Insira sua conta corporativa ou de estudante](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

4. <span data-ttu-id="af263-114">Entre no Intune com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="af263-114">Sign in to Intune with your work or school account.</span></span>

    ![Adicionar uma conta corporativa ou de estudante](./media/w10-enroll-rs1-enter-your-credentials.png)

    <span data-ttu-id="af263-116">Você verá uma mensagem que indica que sua empresa ou escola está registrando o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="af263-116">You’ll see a message indicating that your company or school is registering your device.</span></span>

5. <span data-ttu-id="af263-117">Quando você vir a página **Tudo pronto!**,</span><span class="sxs-lookup"><span data-stu-id="af263-117">When you see the **You’re all set!**</span></span> <span data-ttu-id="af263-118">selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="af263-118">screen, select **Close**.</span></span> <span data-ttu-id="af263-119">Você terminou.</span><span class="sxs-lookup"><span data-stu-id="af263-119">You’re done.</span></span>

  ![Selecione Fechar na tela “Você está pronto!”](./media/w10-enroll-rs1-youre-all-set.png)

6. <span data-ttu-id="af263-122">Se você quiser verificar que a conexão tenha a aparência correta, vá até **Configurações**, onde você deve ver agora sua conta corporativa ou de estudante listada.</span><span class="sxs-lookup"><span data-stu-id="af263-122">If you want to double-check that your connection looks right, go back to **Settings**, where you should now see your work or school account listed.</span></span>

    ![Valide se a conexão foi configurada corretamente](./media/w10-enroll-rs1-validate-successful-enrollment.png)

<span data-ttu-id="af263-124">Se você seguiu as etapas anteriores, mas ainda não consegue acessar sua conta de email e seus arquivos corporativos ou de estudante, siga as etapas em [As etapas a serem seguidas se você vir Acessar conta corporativa ou de estudante](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span><span class="sxs-lookup"><span data-stu-id="af263-124">If you followed the previous steps, but still can’t access your work or school email account and files, follow the steps in [Troubleshooting steps to follow if you see Access work or school](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span></span>
