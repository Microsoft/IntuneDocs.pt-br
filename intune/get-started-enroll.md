---
title: "Introdução ao registro de dispositivos"
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
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 36e658cebdfd23547e3c376124289046f81acc1f
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="9d01c-102">Introdução ao registro de dispositivos</span><span class="sxs-lookup"><span data-stu-id="9d01c-102">Getting started enrolling devices</span></span>
=======
# Introdução ao registro de dispositivos
>>>>>>> live
<a id="getting-started-enrolling-devices" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
![Dispositivo iOS mostrando o aplicativo de portal da empresa.](/intune-user-help/media/ios-enroll-1a-comp-access-setup.png)

<span data-ttu-id="9d01c-105">O Microsoft Intune ajuda você a capacitar sua força de trabalho com dispositivos móveis, ao mesmo tempo que mantém seus dados corporativos protegidos.</span><span class="sxs-lookup"><span data-stu-id="9d01c-105">Microsoft Intune helps you enable your workforce with mobile devices while keeping your corporate data protected.</span></span> <span data-ttu-id="9d01c-106">Como os usuários finais interagem com o Intune em seus dispositivos, em vez de no console do administrador, você deve estar familiarizado com a experiência de registro.</span><span class="sxs-lookup"><span data-stu-id="9d01c-106">Since your end users will interact with Intune on their devices rather than in the admin console, you want to make sure that you are fluent with the enrollment experience.</span></span> <span data-ttu-id="9d01c-107">Dessa forma, você pode combinar as políticas de conformidade bem elaboradas com sua experiência para demonstrar empatia pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="9d01c-107">This way, you can combine well-crafted compliance policies with your experience to show empathy for your users.</span></span> <span data-ttu-id="9d01c-108">Isso é especialmente importante porque os usuários saberão exatamente quais informações que você pode ver como um administrador:</span><span class="sxs-lookup"><span data-stu-id="9d01c-108">This is especially important because your users will know exactly what information that you as an admin can see:</span></span>

## <span data-ttu-id="9d01c-109">O que a equipe de TI não pode ver</span><span class="sxs-lookup"><span data-stu-id="9d01c-109">What IT cannot see</span></span>
<a id="what-it-cannot-see" class="xliff"></a>
* <span data-ttu-id="9d01c-110">Histórico de chamadas e de navegação na Web</span><span class="sxs-lookup"><span data-stu-id="9d01c-110">Calling and web browsing history</span></span>
* <span data-ttu-id="9d01c-111">Local</span><span class="sxs-lookup"><span data-stu-id="9d01c-111">Location</span></span>
* <span data-ttu-id="9d01c-112">Email pessoal</span><span class="sxs-lookup"><span data-stu-id="9d01c-112">Personal email</span></span>
* <span data-ttu-id="9d01c-113">Mensagens de texto</span><span class="sxs-lookup"><span data-stu-id="9d01c-113">Text messages</span></span>
* <span data-ttu-id="9d01c-114">Contatos</span><span class="sxs-lookup"><span data-stu-id="9d01c-114">Contacts</span></span>
* <span data-ttu-id="9d01c-115">Senhas de suas contas pessoais</span><span class="sxs-lookup"><span data-stu-id="9d01c-115">Passwords to your personal accounts</span></span>
* <span data-ttu-id="9d01c-116">Eventos do calendário</span><span class="sxs-lookup"><span data-stu-id="9d01c-116">Calendar events</span></span>
* <span data-ttu-id="9d01c-117">Imagens, incluindo o conteúdo do aplicativo de fotos ou as imagens da câmera</span><span class="sxs-lookup"><span data-stu-id="9d01c-117">Pictures, including what's in the photos app or camera roll</span></span>

## <span data-ttu-id="9d01c-118">O que a equipe de TI pode ver</span><span class="sxs-lookup"><span data-stu-id="9d01c-118">What IT can see</span></span>
<a id="what-it-can-see" class="xliff"></a>
* <span data-ttu-id="9d01c-119">Modelo</span><span class="sxs-lookup"><span data-stu-id="9d01c-119">Model</span></span>
* <span data-ttu-id="9d01c-120">Número de série</span><span class="sxs-lookup"><span data-stu-id="9d01c-120">Serial number</span></span>
* <span data-ttu-id="9d01c-121">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="9d01c-121">Operating system version</span></span>
* <span data-ttu-id="9d01c-122">Nomes de aplicativo</span><span class="sxs-lookup"><span data-stu-id="9d01c-122">App names</span></span>
* <span data-ttu-id="9d01c-123">Proprietário</span><span class="sxs-lookup"><span data-stu-id="9d01c-123">Owner</span></span>
* <span data-ttu-id="9d01c-124">Nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="9d01c-124">Device name</span></span>
* <span data-ttu-id="9d01c-125">Fabricante (para dispositivos não fabricados pela Apple)</span><span class="sxs-lookup"><span data-stu-id="9d01c-125">Manufacturer (for devices not made by Apple)</span></span>
* <span data-ttu-id="9d01c-126">Número de telefone (para dispositivos corporativos, o número completo.</span><span class="sxs-lookup"><span data-stu-id="9d01c-126">Phone number (for work devices, the whole number.</span></span> <span data-ttu-id="9d01c-127">Para dispositivos pessoais, apenas os últimos quatro dígitos.)</span><span class="sxs-lookup"><span data-stu-id="9d01c-127">For personal devices, just the last four digits.)</span></span>

## <span data-ttu-id="9d01c-128">Como registro um dispositivo?</span><span class="sxs-lookup"><span data-stu-id="9d01c-128">How do I enroll a device?</span></span>
<a id="how-do-i-enroll-a-device" class="xliff"></a>

<span data-ttu-id="9d01c-129">Registrar um dispositivo é a primeira experiência que muitos usuários finais terão ao acessar recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="9d01c-129">Enrolling a device is the first experience that many end users will have with accessing corporate resources.</span></span> <span data-ttu-id="9d01c-130">[Entender essa experiência](end-user-educate.md) pode ajudar a tornar uma experiência possivelmente desagradável em uma melhor.</span><span class="sxs-lookup"><span data-stu-id="9d01c-130">[Understanding that experience](end-user-educate.md) can help make a potentially unpleasant experience into a better one.</span></span>

1. <span data-ttu-id="9d01c-131">Abra a **Loja de Aplicativos** e pesquise por **Portal da Empresa do Intune**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-131">Open the **App Store** and search for **Intune Company Portal**.</span></span>
2. <span data-ttu-id="9d01c-132">Baixe o aplicativo **Portal da Empresa do Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-132">Download the **Microsoft Intune Company Portal** app.</span></span>
3. <span data-ttu-id="9d01c-133">Abra o aplicativo **Portal da Empresa**, digite seu endereço de email e a senha do usuário de teste e toque em **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-133">Open the **Company Portal** app, enter your test user’s email address and password, then tap **Sign in**.</span></span>
4. <span data-ttu-id="9d01c-134">Atualize a senha temporária para uma nova.</span><span class="sxs-lookup"><span data-stu-id="9d01c-134">Update the temporary password to a new one.</span></span>
5. <span data-ttu-id="9d01c-135">Na página **Configuração de Acesso da Empresa**, toque em **Registro de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-135">On the **Company Access Setup** page, tap **Device Enrollment**.</span></span>
6. <span data-ttu-id="9d01c-136">Na página **Por que registrar seu dispositivo?** leia sobre o que um usuário pode fazer ao registrar o dispositivo e, em seguida, toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-136">On the **Why enroll your device?** page, read about what a user can do when they enroll their device, then tap **Continue**.</span></span>
7. <span data-ttu-id="9d01c-137">Examine uma lista de qual acesso um usuário recebe ao registrar-se e toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-137">Review a list of what access a user gets when they enroll, then tap **Continue**.</span></span>
8. <span data-ttu-id="9d01c-138">Examine o que os administradores de TI podem ou não podem ver em um dispositivo e toque em **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-138">Review what IT admins can and can’t see on a device, then tap **Continue**.</span></span>
9. <span data-ttu-id="9d01c-139">Na página **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-139">On the **What comes next** page, read about what happens during enrollment, then tap **Enroll**.</span></span>
10. <span data-ttu-id="9d01c-140">Na página **Instalar Perfil**, toque em **Instalar** e insira a senha do dispositivo se solicitado.</span><span class="sxs-lookup"><span data-stu-id="9d01c-140">On the **Install Profile** page, tap **Install**, then enter the device passcode if prompted.</span></span>
11. <span data-ttu-id="9d01c-141">Toque em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-141">Tap **Install**.</span></span>
12. <span data-ttu-id="9d01c-142">Toque em **Instalar** novamente para indicar que você leu o aviso.</span><span class="sxs-lookup"><span data-stu-id="9d01c-142">Tap **Install** again to indicate that you’ve read the warning.</span></span>
13. <span data-ttu-id="9d01c-143">No pop-up **Aviso**, toque em **Confiar**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-143">On the **Warning** popup, tap **Trust**.</span></span>
14. <span data-ttu-id="9d01c-144">Quando a tela for alterada para mostrar que o perfil terminou de instalar, toque em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-144">When the screen changes to show that the profile has finished installing, tap **Done**.</span></span>
15. <span data-ttu-id="9d01c-145">Uma mensagem de “Registrando dispositivo” é mostrada na tela e, em seguida, mostra que o dispositivo foi registrado com êxito.</span><span class="sxs-lookup"><span data-stu-id="9d01c-145">An “Enrolling device” message shows on the screen, then shows that the device has successfully enrolled.</span></span> <span data-ttu-id="9d01c-146">Um pop-up será exibido perguntando se a página deve ser aberta no Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="9d01c-146">A popup will appear asking to open the page in the Company Portal.</span></span> <span data-ttu-id="9d01c-147">Toque em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-147">Tap **Open**.</span></span>
16. <span data-ttu-id="9d01c-148">Você voltará para a tela **Configuração de Acesso da Empresa**.</span><span class="sxs-lookup"><span data-stu-id="9d01c-148">You return to the **Company Access Setup** screen.</span></span> <span data-ttu-id="9d01c-149">Se você não tiver nenhuma política de teste configurada, então o dispositivo deverá aparecer em conformidade.</span><span class="sxs-lookup"><span data-stu-id="9d01c-149">If you have no test policies set up, then the device should appear compliant.</span></span> <span data-ttu-id="9d01c-150">Se você tiver alguma política de teste, tocar em **Conformidade do Dispositivo** mostrará que há coisas que precisam ser feitas para proteger o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="9d01c-150">If you have any test policies, then tapping **Device Compliance** will show that there are things that need to be done to make the device secure.</span></span>
=======
![Dispositivo iOS mostrando o aplicativo de portal da empresa. a primeira tela apresentada ao usuário para o processo de registro é mostrada.](/intune-user-help/media/ios-enroll-1a-comp-access-setup.png)

O Microsoft Intune ajuda você a capacitar sua força de trabalho com dispositivos móveis, ao mesmo tempo que mantém seus dados corporativos protegidos. Como os usuários finais interagem com o Intune em seus dispositivos, em vez de no console do administrador, você deve estar familiarizado com a experiência de registro. Dessa forma, você pode combinar as políticas de conformidade bem elaboradas com sua experiência para demonstrar empatia pelos usuários. Isso é especialmente importante porque os usuários saberão exatamente quais informações que você pode ver como um administrador:

## O que a equipe de TI não pode ver
<a id="what-it-cannot-see" class="xliff"></a>
* Histórico de chamadas e de navegação na Web
* Local
* Email pessoal
* Mensagens de texto
* Contatos
* Senhas de suas contas pessoais
* Eventos do calendário
* Imagens, incluindo o conteúdo do aplicativo de fotos ou as imagens da câmera

## O que a equipe de TI pode ver
<a id="what-it-can-see" class="xliff"></a>
* Modelo
* Número de série
* Versão do sistema operacional
* Nomes de aplicativo
* Proprietário
* Nome do dispositivo
* Fabricante (para dispositivos não fabricados pela Apple)
* Número de telefone (para dispositivos corporativos, o número completo. Para dispositivos pessoais, apenas os últimos quatro dígitos.)

## Como registro um dispositivo?
<a id="how-do-i-enroll-a-device" class="xliff"></a>

Registrar um dispositivo é a primeira experiência que muitos usuários finais terão ao acessar recursos corporativos. [Entender essa experiência](end-user-educate.md) pode ajudar a tornar uma experiência possivelmente desagradável em uma melhor.

1. Abra a **Loja de Aplicativos** e pesquise por **Portal da Empresa do Intune**.
2. Baixe o aplicativo **Portal da Empresa do Microsoft Intune**.
3. Abra o aplicativo **Portal da Empresa**, digite seu endereço de email e a senha do usuário de teste e toque em **Entrar**.
4. Atualize a senha temporária para uma nova.
5. Na página **Configuração de Acesso da Empresa**, toque em **Registro de Dispositivo**.
6. Na página **Por que registrar seu dispositivo?** leia sobre o que um usuário pode fazer ao registrar o dispositivo e, em seguida, toque em **Continuar**.
7. Examine uma lista de qual acesso um usuário recebe ao registrar-se e toque em **Continuar**.
8. Examine o que os administradores de TI podem ou não podem ver em um dispositivo e toque em **Continuar**.
9. Na página **O que vem em seguida**, leia sobre o que acontece durante o registro e, em seguida, toque em **Registrar**.
10. Na página **Instalar Perfil**, toque em **Instalar** e insira a senha do dispositivo se solicitado.
11. Toque em **Instalar**.
12. Toque em **Instalar** novamente para indicar que você leu o aviso.
13. No pop-up **Aviso**, toque em **Confiar**.
14. Quando a tela for alterada para mostrar que o perfil terminou de instalar, toque em **Concluído**.
15. Uma mensagem de “Registrando dispositivo” é mostrada na tela e, em seguida, mostra que o dispositivo foi registrado com êxito. Um pop-up será exibido perguntando se a página deve ser aberta no Portal da Empresa. Toque em **Abrir**.
16. Você voltará para a tela **Configuração de Acesso da Empresa**. Se você não tiver nenhuma política de teste configurada, então o dispositivo deverá aparecer em conformidade. Se você tiver alguma política de teste, tocar em **Conformidade do Dispositivo** mostrará que há coisas que precisam ser feitas para proteger o dispositivo.
>>>>>>> live
