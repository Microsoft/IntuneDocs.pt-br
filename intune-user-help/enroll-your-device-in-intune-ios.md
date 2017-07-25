---
title: <span data-ttu-id="6aefd-101">Registrar seu dispositivo iOS no Intune | Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="6aefd-101">Enroll your iOS device in Intune | Microsoft Docs</span></span>
description: <span data-ttu-id="6aefd-102">Descreve como registrar um dispositivo iOS no Intune</span><span class="sxs-lookup"><span data-stu-id="6aefd-102">Describes how to enroll an iOS device in Intune</span></span>
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope: User help
ROBOTS: 
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 4d7ad138a8aa59ceeff00866469e59e2e1d19520
ms.sourcegitcommit: 2a6ad3c233d15a9fb441362105f64b2bdd550c34
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <a name="enroll-your-ios-device-in-intune"></a><span data-ttu-id="6aefd-103">Registrar seu dispositivo iOS no Intune</span><span class="sxs-lookup"><span data-stu-id="6aefd-103">Enroll your iOS device in Intune</span></span>

<span data-ttu-id="6aefd-104">Se sua empresa ou escola usa o Microsoft Intune, você pode registrar seu dispositivo iOS para obter acesso a email, arquivos e outros recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="6aefd-104">If your company or school uses Microsoft Intune, you can enroll your iOS device to get access to company email, files, and other resources.</span></span> <span data-ttu-id="6aefd-105">Quando você registra os dispositivos, o departamento de TI pode gerenciar recursos corporativos ou de estudante e mantê-los seguros, dando-lhe a liberdade de usar seu dispositivo preferido para realizar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="6aefd-105">When you enroll your devices, your IT department can manage those work or school resources, keep them secure, and give you the freedom to use your preferred device to get your work done.</span></span> <span data-ttu-id="6aefd-106">Para saber mais sobre registro, consulte [What happens if you install the Company Portal app and enroll your device in Intune? (O que acontece quando você instala o aplicativo Portal da Empresa e registra seu dispositivo no Intune?)](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)</span><span class="sxs-lookup"><span data-stu-id="6aefd-106">To learn more about enrollment, see [What happens if you install the Company Portal app and enroll your device in Intune?](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/iOS-Enrollment/player]

> [!NOTE]
<<<<<<< HEAD
> <span data-ttu-id="6aefd-107">Se você estiver tentando registrar um dispositivo macOS como um MacBook Pro ou iMac, [experimente em vez disso usar estas instruções](enroll-your-device-in-intune-macos.md).</span><span class="sxs-lookup"><span data-stu-id="6aefd-107">If you're trying to enroll a macOS device, such as a MacBook Pro or iMac, [try these instructions instead](enroll-your-device-in-intune-macos.md).</span></span>
=======
> Se você estiver tentando registrar um dispositivo macOS como um MacBook Pro ou iMac, [experimente em vez disso usar estas instruções](enroll-your-device-in-intune-macos.md).
>>>>>>> live

<span data-ttu-id="6aefd-108">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="6aefd-108">**Before you start:**</span></span>

<<<<<<< HEAD
- <span data-ttu-id="6aefd-109">Verifique se o registro foi concluído após o início das etapas.</span><span class="sxs-lookup"><span data-stu-id="6aefd-109">Make sure that you finish enrolling after you start the steps.</span></span> <span data-ttu-id="6aefd-110">Pausa por mais de alguns minutos geralmente interrompe o processo e exige reinicialização.</span><span class="sxs-lookup"><span data-stu-id="6aefd-110">Pausing for more than a few minutes usually stops the process, and  requires you to restart.</span></span>
- <span data-ttu-id="6aefd-111">Se o registro falhar por algum motivo, você precisará retornar para o aplicativo de Portal da Empresa para tentar novamente.</span><span class="sxs-lookup"><span data-stu-id="6aefd-111">If your enrollment fails for any reason, you need to return to the Company Portal app to try again.</span></span>
- <span data-ttu-id="6aefd-112">Verifique se o Wi-Fi está funcionando.</span><span class="sxs-lookup"><span data-stu-id="6aefd-112">Make sure that your Wi-Fi is working.</span></span> <span data-ttu-id="6aefd-113">Caso contrário, o registro falhará.</span><span class="sxs-lookup"><span data-stu-id="6aefd-113">Otherwise, enrollment fails.</span></span>
- <span data-ttu-id="6aefd-114">Se você bloqueou o Safari no dispositivo, desbloqueie-o.</span><span class="sxs-lookup"><span data-stu-id="6aefd-114">If you blocked Safari on your device, unblock it.</span></span> <span data-ttu-id="6aefd-115">O Safari é usado como parte do processo de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6aefd-115">Safari is used as part the device enrollment process.</span></span>
=======
- Verifique se o registro foi concluído após o início das etapas. Pausa por mais de alguns minutos geralmente interrompe o processo e exige reinicialização.
- Se o registro falhar por algum motivo, você precisará retornar para o aplicativo de Portal da Empresa para tentar novamente.
- Verifique se o Wi-Fi está funcionando. Caso contrário, o registro falhará.
- Se você bloqueou o Safari no dispositivo, desbloqueie-o. O Safari é usado como parte do processo de registro do dispositivo.
>>>>>>> live


<span data-ttu-id="6aefd-116">**Para registrar seu dispositivo iOS:**</span><span class="sxs-lookup"><span data-stu-id="6aefd-116">**To enroll your iOS device:**</span></span>

1.  <span data-ttu-id="6aefd-117">Siga as etapas em [Install and sign in to the Intune Company Portal app](install-and-sign-in-to-the-intune-company-portal-app-ios.md) (Instalar e entrar no aplicativo Portal da Empresa no Intune).</span><span class="sxs-lookup"><span data-stu-id="6aefd-117">Follow the steps in [Install and sign in to the Intune Company Portal app](install-and-sign-in-to-the-intune-company-portal-app-ios.md).</span></span>

2. <span data-ttu-id="6aefd-118">Na tela **Configuração de Acesso da Empresa**, toque em **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-118">On the **Company Access Setup** page, tap **Begin**.</span></span>

    ![ios-enroll-comp-access-setup-begin](./media/ios-enroll-1a-comp-access-setup.png)

3. <span data-ttu-id="6aefd-120">Na tela **Por que registrar seu dispositivo?** leia sobre o que você pode fazer ao registrar o dispositivo e, em seguida, toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-120">On the **Why enroll your device?** screen, read about what you can do when you enroll your device, and then tap **Continue**.</span></span>

    ![ios-enroll-why-enroll](./media/ios-enroll-1b-why-enroll.png)

  > [!NOTE]
<<<<<<< HEAD
  > <span data-ttu-id="6aefd-122">Os triângulos amarelos não significam que você já tem um erro.</span><span class="sxs-lookup"><span data-stu-id="6aefd-122">The yellow triangles don't mean you've already got an error.</span></span> <span data-ttu-id="6aefd-123">Esses ícones indicam que ainda há etapas a serem concluídas no processo de registro.</span><span class="sxs-lookup"><span data-stu-id="6aefd-123">Those icons indicate that there are still steps to be completed in the enrollment process.</span></span>
=======
  > Os triângulos amarelos não significam que você já tem um erro. Esses ícones indicam que ainda há etapas a serem concluídas no processo de registro.
>>>>>>> live

4. <span data-ttu-id="6aefd-124">Examine uma lista do que o administrador de TI pode ou não pode ver no dispositivo registrado e toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-124">Review a list of what your IT admin can and can’t see on your enrolled device, and then tap **Continue**.</span></span>

    ![ios-enroll-what-it-can-see](./media/ios-enroll-1c-we-care-privacy.png)

5.  <span data-ttu-id="6aefd-126">Na tela **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-126">On the **What comes next** screen, read about what happens during enrollment, and then tap **Enroll**.</span></span>

    ![ios-enroll-what-comes-next](./media/ios-enroll-1d-what-comes-next.png)

6.  <span data-ttu-id="6aefd-128">Na tela **Instalar Perfil**, toque em **Instalar** e insira sua senha, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="6aefd-128">On the **Install Profile** screen, tap **Install**, and enter your passcode, if prompted.</span></span>

    ![ios-enroll-install-profile](./media/ios-enroll-2-mgt-profile-install.png)

7.  <span data-ttu-id="6aefd-130">Toque em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-130">Tap **Install**.</span></span>

    ![ios-enroll-tap-install](./media/ios-enroll-3-mgt-profile-install-2.png)    

8.  <span data-ttu-id="6aefd-132">Toque em **Instalar** para indicar que você leu o aviso.</span><span class="sxs-lookup"><span data-stu-id="6aefd-132">Tap **Install** to indicate that you've read the warning.</span></span>

    ![ios-enroll-tap-install-after-warning](./media/ios-enroll-4-warning.png)

9.  <span data-ttu-id="6aefd-134">Toque em **Confiar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-134">Tap **Trust**.</span></span>

    ![ios-enroll-tap-trust](./media/ios-enroll-5-trust.png)

10.  <span data-ttu-id="6aefd-136">Quando a tela for alterada para mostrar que o perfil terminou de instalar, toque em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-136">When the screen changes to show that the profile has finished installing, Tap **Done**.</span></span>

    ![ios-enroll-tap-done](./media/ios-enroll-6-done.png)

    <span data-ttu-id="6aefd-138">Uma mensagem com os dizeres “Registrando dispositivo” é exibida na tela.</span><span class="sxs-lookup"><span data-stu-id="6aefd-138">An “Enrolling device” message shows on the screen.</span></span>

11.  <span data-ttu-id="6aefd-139">Quando uma mensagem perguntando se você deseja abrir a página no Portal da Empresa for exibida, toque em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-139">When a message asks if you want to open the page in the Company Portal, tap **Open**.</span></span>

    ![ios-enroll-open-comp-portal](./media/ios-enroll-7-open-cp.png)

<<<<<<< HEAD
12. <span data-ttu-id="6aefd-141">Na tela **Configuração de Acesso da Empresa**, toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-141">On the **Company Access Setup** screen, tap **Continue**.</span></span> <span data-ttu-id="6aefd-142">Esta tela mostra quais outros requisitos você talvez precise fazer para que o dispositivo esteja em conformidade, por exemplo, definir uma senha.</span><span class="sxs-lookup"><span data-stu-id="6aefd-142">This screen shows you what other requirements you may have to do to make your device compliant, like setting a password.</span></span> <span data-ttu-id="6aefd-143">Siga as instruções na tela até que você atenda a todos os requisitos de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6aefd-143">Follow the on-screen instructions until you meet all the compliance requirements.</span></span> <span data-ttu-id="6aefd-144">Depois de concluir, você retornará para a tela Configuração de Acesso da Empresa.</span><span class="sxs-lookup"><span data-stu-id="6aefd-144">Once you finish, you are returned to the Company Access Setup screen.</span></span> <span data-ttu-id="6aefd-145">Toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-145">Tap **Continue**.</span></span>
=======
12. Na tela **Configuração de Acesso da Empresa**, toque em **Continuar**. Esta tela mostra quais outros requisitos você talvez precise fazer para que o dispositivo esteja em conformidade, por exemplo, definir uma senha. Siga as instruções na tela até que você atenda a todos os requisitos de conformidade. Depois de concluir, você retornará para a tela Configuração de Acesso da Empresa. Toque em **Continuar**.
>>>>>>> live

    ![ios-enroll-comp-access-tap-continue](./media/ios-enroll-8-comp-access-setup-compliance.png)

13. <span data-ttu-id="6aefd-147">Toque em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="6aefd-147">Tap **Done**.</span></span>

    ![ios-enroll-tap-done](./media/ios-enroll-9-comp-access-setup-complete.png)

<span data-ttu-id="6aefd-149">O dispositivo agora está registrado no Intune, e você é levado de volta ao aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="6aefd-149">Your device is now enrolled in Intune, and you are taken back to the Company Portal app.</span></span>

> [!Note]
<<<<<<< HEAD
> <span data-ttu-id="6aefd-150">Você tem mais algumas etapas para concluir antes que o dispositivo esteja totalmente inscrito.</span><span class="sxs-lookup"><span data-stu-id="6aefd-150">You have a few more steps to complete before your device is fully enrolled.</span></span> <span data-ttu-id="6aefd-151">Saiba mais sobre como [registrar seu dispositivo usando o gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md).</span><span class="sxs-lookup"><span data-stu-id="6aefd-151">Find out more about [enrolling your device using telecom expense management](enroll-your-device-with-telecom-expense-management-ios.md).</span></span> <span data-ttu-id="6aefd-152">Se sua organização estiver usando o Programa de registro de dispositivos da Apple, descubra mais [aqui](enroll-your-device-dep-ios.md).</span><span class="sxs-lookup"><span data-stu-id="6aefd-152">If your organization is using Apple's Device Enrollment Program, find out more [here](enroll-your-device-dep-ios.md).</span></span>
=======
> Você tem mais algumas etapas para concluir antes que o dispositivo esteja totalmente inscrito. Saiba mais sobre como [registrar seu dispositivo usando o gerenciamento de despesas de telecomunicações](enroll-your-device-with-telecom-expense-management-ios.md). Se sua organização estiver usando o Programa de registro de dispositivos da Apple, descubra mais [aqui](enroll-your-device-dep-ios.md).
>>>>>>> live

<span data-ttu-id="6aefd-153">Ainda precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="6aefd-153">Still need help?</span></span> <span data-ttu-id="6aefd-154">Entre em contato com o administrador de TI.</span><span class="sxs-lookup"><span data-stu-id="6aefd-154">Contact your IT admin.</span></span> <span data-ttu-id="6aefd-155">Para obter as informações de contato, consulte o [site do Portal da Empresa](http://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6aefd-155">For contact information, check the [Company Portal website](http://portal.manage.microsoft.com).</span></span>
