---
title: Novidades do Microsoft Intune nos meses anteriores
titleSuffix: Intune on Azure
description: "Veja comunicados mais antigos da página de novidades do Intune"
keywords: 
author: mtillman
ms.author: mtillman
manager: angrobe
ms.date: 06/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ba01d60-4a03-4e3e-9aba-8be905c0054c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cf2322a4009310e5dd561693ea6b3cdb97ab6e28
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="ecec0-103">Novidades do Microsoft Intune – meses anteriores</span><span class="sxs-lookup"><span data-stu-id="ecec0-103">What's new in the Microsoft Intune - previous months</span></span>
=======
# Novidades do Microsoft Intune – meses anteriores
>>>>>>> live
<a id="whats-new-in-the-microsoft-intune---previous-months" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
## <span data-ttu-id="ecec0-104">Abril de 2017</span><span class="sxs-lookup"><span data-stu-id="ecec0-104">April 2017</span></span>
<a id="april-2017" class="xliff"></a>

### <span data-ttu-id="ecec0-105">Suporte para gerenciamento do aplicativo Sala de Aula da Apple</span><span class="sxs-lookup"><span data-stu-id="ecec0-105">Support for managing the Apple Classroom app</span></span>
<a id="support-for-managing-the-apple-classroom-app" class="xliff"></a>

<span data-ttu-id="ecec0-106">Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads.</span><span class="sxs-lookup"><span data-stu-id="ecec0-106">You can now manage the iOS Classroom app on iPad devices.</span></span> <span data-ttu-id="ecec0-107">Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-107">Set up the Classroom app on the teachers iPad with the correct class and student data, then configure student iPads registered to a class, so that you can control them using the app.</span></span>
<span data-ttu-id="ecec0-108">Para obter detalhes, confira [Definir as configurações de educação do iOS](education-settings-configure-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-108">For details, see [Configure iOS education settings](education-settings-configure-ios.md).</span></span>

### <span data-ttu-id="ecec0-109">Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-109">Support for managed configuration options for Android apps <!-- 621621 --></span></span>
<a id="support-for-managed-configuration-options-for-android-apps----621621---" class="xliff"></a>

<span data-ttu-id="ecec0-110">Agora, os aplicativos Android na Play Store que oferecem suporte a opções de configuração gerenciada podem ser configurados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-110">Android apps in the Play store that support managed configuration options can now be configure by Intune.</span></span>  <span data-ttu-id="ecec0-111">Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.</span><span class="sxs-lookup"><span data-stu-id="ecec0-111">This feature lets IT view the list of configuration values supported by an app, and provides a guided, first-class UI to allow them to configure those values.</span></span>

### <span data-ttu-id="ecec0-112">Nova política de Android para PINs complexos <!-- 722069 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-112">New Android policy for complex PINs <!-- 722069 --></span></span>
<a id="new-android-policy-for-complex-pins----722069---" class="xliff"></a>

<span data-ttu-id="ecec0-113">Agora, você pode definir um tipo de [senha](device-restrictions-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.</span><span class="sxs-lookup"><span data-stu-id="ecec0-113">You can now set a required [password](device-restrictions-android.md#password) type of Numeric complex in an Android device profile for devices that run Android 5.0 and above.</span></span>  <span data-ttu-id="ecec0-114">Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.</span><span class="sxs-lookup"><span data-stu-id="ecec0-114">Use this setting to prevent device users from creating a PIN that contains repeating, or consecutive numbers, like 1111, or 1234.</span></span>

### <span data-ttu-id="ecec0-115">Suporte adicional para dispositivos Android for Work</span><span class="sxs-lookup"><span data-stu-id="ecec0-115">Additional support for Android for Work devices</span></span>
<a id="additional-support-for-android-for-work-devices" class="xliff"></a>

- <span data-ttu-id="ecec0-116">**Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-116">**Manage password and work profile settings** <!-- 612808 --></span></span>

  <span data-ttu-id="ecec0-117">Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.</span><span class="sxs-lookup"><span data-stu-id="ecec0-117">This new Android for Work device restriction policy now lets you manage password and work profile settings on Android for Work devices you manage.</span></span>

- <span data-ttu-id="ecec0-118">**Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-118">**Allow data sharing between work and personal profiles** <!-- 1045102 --></span></span>

<span data-ttu-id="ecec0-119">Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ecec0-119">This Android for Work device restriction profile now has new options to help you configure data sharing between work and personal profiles.</span></span>

- <span data-ttu-id="ecec0-120">**Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-120">**Restrict copy and paste between work and personal profiles** <!-- 1046094 --></span></span>

  <span data-ttu-id="ecec0-121">Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ecec0-121">A new custom device profile for Android for Work devices now lets you restrict whether copy and paste actions between work and personal apps are allowed.</span></span>

<span data-ttu-id="ecec0-122">Para saber mais, confira [Restrições de dispositivo para Android for Work](device-restrictions-android-for-work.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-122">For more information, see [Device restrictions for Android for Work](device-restrictions-android-for-work.md).</span></span>

### <span data-ttu-id="ecec0-123">Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-123">Assign LOB apps to iOS and Android devices <!-- 1057568 --></span></span>
<a id="assign-lob-apps-to-ios-and-android-devices----1057568---" class="xliff"></a>

<span data-ttu-id="ecec0-124">Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](lob-apps-ios.md) (arquivos .ipa) e [Android](lob-apps-android.md) (arquivos .apk) a usuários ou dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-124">You can now assign line of business (LOB) apps for [iOS](lob-apps-ios.md) (.ipa files) and [Android](lob-apps-android.md) (.apk files) to users or devices.</span></span>

###  <span data-ttu-id="ecec0-125">Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-125">New device policies for iOS <!-- 723774, 723815, 723826, 723830 --></span></span>
<a id="new-device-policies-for-ios----723774-723815-723826-723830---" class="xliff"></a>

- <span data-ttu-id="ecec0-126">**Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](home-screen-settings-ios.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-126">**Apps on Home screen** - Controls which apps users see on the [Home screen of their iOS device](home-screen-settings-ios.md).</span></span> <span data-ttu-id="ecec0-127">Essa política altera o layout da Tela inicial, mas não implanta nenhum aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-127">This policy changes the layout of the Home screen, but does not deploy any apps.</span></span>

- <span data-ttu-id="ecec0-128">**Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](air-print-settings-ios-macos.md) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.</span><span class="sxs-lookup"><span data-stu-id="ecec0-128">**Connections to AirPrint devices** - Controls which [AirPrint devices](air-print-settings-ios-macos.md) (network printers) that end users of iOS device can connect to.</span></span>

- <span data-ttu-id="ecec0-129">**Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](airplay-settings-ios.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.</span><span class="sxs-lookup"><span data-stu-id="ecec0-129">**Connections to AirPlay devices** - Controls which [AirPlay devices](airplay-settings-ios.md) (like Apple TV) that end users of iOS device can connect to.</span></span>

- <span data-ttu-id="ecec0-130">**Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão.</span><span class="sxs-lookup"><span data-stu-id="ecec0-130">**Custom lock screen message** - Configures a custom message that users will see on the lock screen of their iOS device, that replaces the default lock screen message.</span></span> <span data-ttu-id="ecec0-131">Para obter mais informações, consulte [Ativar o modo perdido em dispositivos iOS](device-lost-mode.md)</span><span class="sxs-lookup"><span data-stu-id="ecec0-131">For more information, see [Activate lost mode on iOS devices](device-lost-mode.md)</span></span>

### <span data-ttu-id="ecec0-132">Restrinja as notificações por push para aplicativos iOS <!-- 723767 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-132">Restrict push notifications for iOS apps <!-- 723767 --></span></span>
<a id="restrict-push-notifications-for-ios-apps----723767---" class="xliff"></a>

<span data-ttu-id="ecec0-133">Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](app-notification-settings-ios.md) para dispositivos iOS:</span><span class="sxs-lookup"><span data-stu-id="ecec0-133">In an Intune device restriction profile, you can now configure the following [notification settings](app-notification-settings-ios.md) for iOS devices:</span></span>

- <span data-ttu-id="ecec0-134">Ative ou desative completamente a notificação de um aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="ecec0-134">Fully turn on or off notification for a specified app.</span></span>
- <span data-ttu-id="ecec0-135">Ative ou desative a notificação no centro de notificações para um aplicativo especificado.</span><span class="sxs-lookup"><span data-stu-id="ecec0-135">Turn on or off, the notification in the notification center for a specified app.</span></span>
- <span data-ttu-id="ecec0-136">Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.</span><span class="sxs-lookup"><span data-stu-id="ecec0-136">Specify the alert type, either **None**, **Banner**, or **Modal Alert**.</span></span>
- <span data-ttu-id="ecec0-137">Especifique se são permitidos selos para esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-137">Specify whether badges are allowed for this app.</span></span>
- <span data-ttu-id="ecec0-138">Especifique se são permitidos sons de notificação.</span><span class="sxs-lookup"><span data-stu-id="ecec0-138">Specify whether notification sounds are allowed.</span></span>

### <span data-ttu-id="ecec0-139">Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-139">Configure iOS apps to run in single app mode autonomously <!-- 737837 --></span></span>
<a id="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---" class="xliff"></a>

<span data-ttu-id="ecec0-140">Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only).</span><span class="sxs-lookup"><span data-stu-id="ecec0-140">You can now use an Intune device profile to configure iOS devices to run specified apps in [autonomous single app mode](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only).</span></span> <span data-ttu-id="ecec0-141">Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-141">When this mode is configured, and the app is run, the device is locked so that it can only run that app.</span></span> <span data-ttu-id="ecec0-142">Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-142">An example of this is when you configure an app that lets users take a test on the device.</span></span> <span data-ttu-id="ecec0-143">Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.</span><span class="sxs-lookup"><span data-stu-id="ecec0-143">When the app's actions are complete, or you remove this policy, the device returns to its normal state.</span></span>

### <span data-ttu-id="ecec0-144">Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-144">Configure trusted domains for email and web browsing on iOS devices <!-- 723765 --></span></span>
<a id="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---" class="xliff"></a>

<span data-ttu-id="ecec0-145">Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](device-restrictions-ios.md#domains):</span><span class="sxs-lookup"><span data-stu-id="ecec0-145">From an iOS device restriction profile, you can now configure the following [domain settings](device-restrictions-ios.md#domains):</span></span>

- <span data-ttu-id="ecec0-146">**Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ecec0-146">**Unmarked email domains** - Emails that the user sends or receives which don't match the domains you specify here will be marked as untrusted.</span></span>

- <span data-ttu-id="ecec0-147">**Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).</span><span class="sxs-lookup"><span data-stu-id="ecec0-147">**Managed web domains** - Documents downloaded from the URLs you specify here will be considered managed (Safari only).</span></span>  

- <span data-ttu-id="ecec0-148">**Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui.</span><span class="sxs-lookup"><span data-stu-id="ecec0-148">**Safari password auto-fill domains** - Users can save passwords in Safari only from URLs matching the patterns you specify here.</span></span> <span data-ttu-id="ecec0-149">Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários.</span><span class="sxs-lookup"><span data-stu-id="ecec0-149">To use this setting, the device must be in supervised mode and not configured for multiple users.</span></span> <span data-ttu-id="ecec0-150">(iOS 9.3+)</span><span class="sxs-lookup"><span data-stu-id="ecec0-150">(iOS 9.3+)</span></span>


### <span data-ttu-id="ecec0-151">Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-151">VPP apps available in iOS Company Portal <!-- 748782 --></span></span>
<a id="vpp-apps-available-in-ios-company-portal----748782---" class="xliff"></a>

<span data-ttu-id="ecec0-152">Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="ecec0-152">You can now assign iOS volume-purchased (VPP) apps as **Available** installs to end users.</span></span> <span data-ttu-id="ecec0-153">Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-153">End users will need an Apple Store account to install the app.</span></span>

### <span data-ttu-id="ecec0-154">Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-154">Synchronize eBooks from Apple VPP Store <!-- 800878 --></span></span>
<a id="synchronize-ebooks-from-apple-vpp-store----800878---" class="xliff"></a>

<span data-ttu-id="ecec0-155">Agora você pode [sincronizar os livros](vpp-apps-ios.md) adquiridos na loja de programa adquirido por volume da Apple com o Intune e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="ecec0-155">You can now [synchronize books](vpp-apps-ios.md) you purchased from the Apple volume-purchase program store with Intune, and assign the books to users.</span></span>

### <span data-ttu-id="ecec0-156">Gerenciamento de vários usuários para dispositivos Samsung KNOX Standard <!-- 971988 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-156">Multi-user management for Samsung KNOX Standard devices <!-- 971988 --></span></span>
<a id="multi-user-management-for-samsung-knox-standard-devices----971988---" class="xliff"></a>

<span data-ttu-id="ecec0-157">Agora há suporte para dispositivos que executam o Samsung KNOX Standard para o [gerenciamento de vários usuários](android-enroll.md) pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-157">Devices that run Samsung KNOX Standard are now supported for [multi-user management](android-enroll.md) by Intune.</span></span> <span data-ttu-id="ecec0-158">Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.</span><span class="sxs-lookup"><span data-stu-id="ecec0-158">This means that end users can sign in and out of the device with their Azure Active Directory credentials, and the device is centrally managed whether it’s in use or not.</span></span>  <span data-ttu-id="ecec0-159">Quando os usuários finais entram, eles têm acesso a aplicativos e obtêm as políticas aplicadas a eles.</span><span class="sxs-lookup"><span data-stu-id="ecec0-159">When end-users sign-in, they have access to apps and get any policies applied to them.</span></span> <span data-ttu-id="ecec0-160">Quando os usuários saem, todos os dados do aplicativo são removidos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-160">When users sign out, all app data is cleared.</span></span>

### <span data-ttu-id="ecec0-161">Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-161">Additional Windows device restriction settings <!-- 818566 --></span></span>
<a id="additional-windows-device-restriction-settings----818566---" class="xliff"></a>

<span data-ttu-id="ecec0-162">Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](device-restrictions-windows-10.md), como suporte adicional ao navegador Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.</span><span class="sxs-lookup"><span data-stu-id="ecec0-162">We've added support for additional [Windows device restriction settings](device-restrictions-windows-10.md) like additional Edge browser support, device lock screen customization, start menu customizations, Windows Spotlight search set wallpaper, and proxy setting.</span></span>

### <span data-ttu-id="ecec0-163">Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-163">Multi-user support for Windows 10 Creators Update <!-- 822547 --></span></span>
<a id="multi-user-support-for-windows-10-creators-update----822547---" class="xliff"></a>

<span data-ttu-id="ecec0-164">Adicionamos suporte para o [gerenciamento de vários usuários](windows-enroll.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ecec0-164">We've added support for [multi-user management](windows-enroll.md) for devices that run the Windows 10 Creators Update and are Azure Active Directory domain-joined.</span></span> <span data-ttu-id="ecec0-165">Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="ecec0-165">This means that when different standard users log into the device with their Azure AD credentials, they will receive any apps and policies that were assigned to their user name.</span></span> <span data-ttu-id="ecec0-166">No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-166">Users cannot currently use the Company Portal for self-service scenarios like installing apps.</span></span>

### <span data-ttu-id="ecec0-167">Começar do zero para PCs com Windows 10<!-- 1004830 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-167">Fresh Start for Windows 10 PCs<!-- 1004830 --></span></span>
<a id="fresh-start-for-windows-10-pcs---1004830---" class="xliff"></a>

<span data-ttu-id="ecec0-168">Agora há uma [nova ação de dispositivo para começar do zero](device-fresh-start.md) disponível em PCs com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ecec0-168">A new [Fresh Start device action](device-fresh-start.md) for Windows 10 PCs is now available.</span></span>  <span data-ttu-id="ecec0-169">Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows.</span><span class="sxs-lookup"><span data-stu-id="ecec0-169">When you issue this action, any apps that were installed on the PC are removed, and the PC is automatically updated to the latest version of Windows.</span></span> <span data-ttu-id="ecec0-170">Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador.</span><span class="sxs-lookup"><span data-stu-id="ecec0-170">This can be used to help remove pre-installed OEM apps that are often delivered with a new PC.</span></span> <span data-ttu-id="ecec0-171">Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.</span><span class="sxs-lookup"><span data-stu-id="ecec0-171">You can configure if user data is retained when this device action is issued.</span></span>

### <span data-ttu-id="ecec0-172">Caminhos de atualização adicionais do Windows 10 <!-- 903672 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-172">Additional Windows 10 upgrade paths <!-- 903672 --></span></span>
<a id="additional-windows-10-upgrade-paths----903672---" class="xliff"></a>

<span data-ttu-id="ecec0-173">Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](edition-upgrade-configure-windows-10.md) para as seguintes edições adicionais do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="ecec0-173">You can now create an [edition upgrade policy to upgrade devices](edition-upgrade-configure-windows-10.md) to the following additional Windows 10 editions:</span></span>

- <span data-ttu-id="ecec0-174">Windows 10 Professional</span><span class="sxs-lookup"><span data-stu-id="ecec0-174">Windows 10 Professional</span></span>
- <span data-ttu-id="ecec0-175">Windows 10 Professional N</span><span class="sxs-lookup"><span data-stu-id="ecec0-175">Windows 10 Professional N</span></span>
- <span data-ttu-id="ecec0-176">Windows 10 Professional Education</span><span class="sxs-lookup"><span data-stu-id="ecec0-176">Windows 10 Professional Education</span></span>
- <span data-ttu-id="ecec0-177">Windows 10 Professional Education N</span><span class="sxs-lookup"><span data-stu-id="ecec0-177">Windows 10 Professional Education N</span></span>

### <span data-ttu-id="ecec0-178">Registro em massa de dispositivos com Windows 10 <!-- 747607 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-178">Bulk Enroll Windows 10 devices <!-- 747607 --></span></span>
<a id="bulk-enroll-windows-10-devices----747607---" class="xliff"></a>

<span data-ttu-id="ecec0-179">Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer).</span><span class="sxs-lookup"><span data-stu-id="ecec0-179">You can now join large numbers of devices that run the Windows 10 Creators update to Azure Active Directory and Intune with Windows Configuration Designer (WCD).</span></span> <span data-ttu-id="ecec0-180">Para habilitar o [registro em massa do MDM](windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa.</span><span class="sxs-lookup"><span data-stu-id="ecec0-180">To enable [bulk MDM enrollment](windows-bulk-enroll.md) for your Azure AD tenant, create a provisioning package that joins devices to your Azure AD tenant using Windows Configuration Designer, and apply the package to corporate-owned devices you'd like to bulk enroll and manage.</span></span> <span data-ttu-id="ecec0-181">Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ecec0-181">Once the package is applied to your devices, they will Azure AD join, enroll in Intune, and be ready for your Azure AD users to log on.</span></span>  <span data-ttu-id="ecec0-182">Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários.</span><span class="sxs-lookup"><span data-stu-id="ecec0-182">Azure AD users are standard users on these devices and receive assigned policies and required apps.</span></span> <span data-ttu-id="ecec0-183">Não há suporte para cenários de autoatendimento e de Portal da Empresa no momento.</span><span class="sxs-lookup"><span data-stu-id="ecec0-183">Self-service and Company Portal scenarios are not supported currently.</span></span>

### <span data-ttu-id="ecec0-184">Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-184">New MAM settings for PIN and managed storage locations <!-- 581122, 736644 --></span></span>
<a id="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---" class="xliff"></a>

<span data-ttu-id="ecec0-185">Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):</span><span class="sxs-lookup"><span data-stu-id="ecec0-185">Two new app settings are now available to help you with mobile application management (MAM) scenarios:</span></span>

- <span data-ttu-id="ecec0-186">**Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-186">**Disable app PIN when device PIN is managed** - Detects if a device PIN is present on the enrolled device, and if so, bypasses the app PIN triggered by the app protection policies.</span></span> <span data-ttu-id="ecec0-187">Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="ecec0-187">This setting will allow for a reduction in the number of times a PIN prompt is displayed to users opening a MAM-enabled application on an enrolled device.</span></span> <span data-ttu-id="ecec0-188">Esse recurso está disponível para Android e iOS.</span><span class="sxs-lookup"><span data-stu-id="ecec0-188">This feature is available for both Android and iOS.</span></span>

- <span data-ttu-id="ecec0-189">**Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-189">**Select which storage services corporate data can be saved to** -Allows you to specify which storage locations in which to save corporate data.</span></span> <span data-ttu-id="ecec0-190">Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.</span><span class="sxs-lookup"><span data-stu-id="ecec0-190">Users can save to the selected storage location services, which means all other storage location services not listed will be blocked.</span></span>

  <span data-ttu-id="ecec0-191">Lista de serviços de localização de armazenamento com suporte:</span><span class="sxs-lookup"><span data-stu-id="ecec0-191">List of supported storage location services:</span></span>

  - <span data-ttu-id="ecec0-192">OneDrive</span><span class="sxs-lookup"><span data-stu-id="ecec0-192">OneDrive</span></span>
  - <span data-ttu-id="ecec0-193">Business SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ecec0-193">Business SharePoint Online</span></span>
  - <span data-ttu-id="ecec0-194">Armazenamento local</span><span class="sxs-lookup"><span data-stu-id="ecec0-194">Local storage</span></span>

### <span data-ttu-id="ecec0-195">Portal de solução de problemas de suporte técnico <!-- 907448 --></span><span class="sxs-lookup"><span data-stu-id="ecec0-195">Help desk troubleshooting portal <!-- 907448 --></span></span>
<a id="help-desk-troubleshooting-portal----907448---" class="xliff"></a>

<span data-ttu-id="ecec0-196">O novo [portal de solução de problemas](help-desk-operators.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-196">The new [troubleshooting portal](help-desk-operators.md) lets help desk operators and Intune administrators view users and their devices, and perform tasks to resolve Intune technical problems.</span></span>

## <span data-ttu-id="ecec0-197">Março de 2017</span><span class="sxs-lookup"><span data-stu-id="ecec0-197">March 2017</span></span>
<a id="march-2017" class="xliff"></a>

### <span data-ttu-id="ecec0-198">Suporte para o Modo Perdido do iOS<!--431695--></span><span class="sxs-lookup"><span data-stu-id="ecec0-198">Support for iOS Lost Mode <!--431695--></span></span>
<a id="support-for-ios-lost-mode---431695--" class="xliff"></a>

<span data-ttu-id="ecec0-199">Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**.</span><span class="sxs-lookup"><span data-stu-id="ecec0-199">For iOS 9.3 and later devices, Intune added support for **Lost Mode**.</span></span> <span data-ttu-id="ecec0-200">Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-200">You can now lock down a device to prevent all use and display a message and contact phone number of the device lock screen.</span></span>

<span data-ttu-id="ecec0-201">O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido.</span><span class="sxs-lookup"><span data-stu-id="ecec0-201">The end user will not be able to unlock the device until an admin disables Lost Mode.</span></span> <span data-ttu-id="ecec0-202">Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-202">When Lost Mode is enabled, you can use the **Locate device** action to display the geographical location of the device on a map in the Intune console.</span></span>

<span data-ttu-id="ecec0-203">O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.</span><span class="sxs-lookup"><span data-stu-id="ecec0-203">The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.</span></span>

<span data-ttu-id="ecec0-204">Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](device-management.md)?</span><span class="sxs-lookup"><span data-stu-id="ecec0-204">For more information, see [What is Microsoft Intune device management](device-management.md)?</span></span>

### <span data-ttu-id="ecec0-205">Aprimoramentos para o relatório de Ações de Dispositivo <!--677150--></span><span class="sxs-lookup"><span data-stu-id="ecec0-205">Improvements to Device Actions report <!--677150--></span></span>
<a id="improvements-to-device-actions-report---677150--" class="xliff"></a>

<span data-ttu-id="ecec0-206">Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="ecec0-206">We’ve made improvements to the Device Actions report to improve performance.</span></span> <span data-ttu-id="ecec0-207">Além disso, agora você pode filtrar o relatório por estado.</span><span class="sxs-lookup"><span data-stu-id="ecec0-207">Additionally, you can now filter the report by state.</span></span> <span data-ttu-id="ecec0-208">Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.</span><span class="sxs-lookup"><span data-stu-id="ecec0-208">For example, you could filter the report to show only device actions that were completed.”</span></span>

### <span data-ttu-id="ecec0-209">Categorias de aplicativo personalizadas <!--748805--></span><span class="sxs-lookup"><span data-stu-id="ecec0-209">Custom app categories <!--748805--></span></span>
<a id="custom-app-categories---748805--" class="xliff"></a>

<span data-ttu-id="ecec0-210">Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-210">You can now create, edit, and assign categories for apps you add to Intune.</span></span> <span data-ttu-id="ecec0-211">Atualmente, as categorias podem ser especificadas apenas em inglês.</span><span class="sxs-lookup"><span data-stu-id="ecec0-211">Currently, categories can only be specified in English.</span></span>
<span data-ttu-id="ecec0-212">Consulte [como adicionar um aplicativo ao Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-212">See [How to add an app to Intune](apps-add.md).</span></span>

### <span data-ttu-id="ecec0-213">Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823--></span><span class="sxs-lookup"><span data-stu-id="ecec0-213">Assign LOB apps to users with unenrolled devices <!--748823--></span></span>
<a id="assign-lob-apps-to-users-with-unenrolled-devices---748823--" class="xliff"></a>

<span data-ttu-id="ecec0-214">Agora você pode atribuir aplicativos de linhas de negócios da loja para os usuários, independentemente de seus dispositivos estarem registrados ou não no Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-214">You can now assign line-of-business apps from the store to users whether or not their devices are enrolled with Intune.</span></span> <span data-ttu-id="ecec0-215">Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ecec0-215">If the user's device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.</span></span>

### <span data-ttu-id="ecec0-216">Novos relatórios de conformidade <!--846671--></span><span class="sxs-lookup"><span data-stu-id="ecec0-216">New compliance reports <!--846671--></span></span>
<a id="new-compliance-reports---846671--" class="xliff"></a>

<span data-ttu-id="ecec0-217">Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="ecec0-217">You now have compliance reports that give you the compliance posture of devices in your company and allow you to quickly troubleshoot compliance-related issues encountered by your users.</span></span> <span data-ttu-id="ecec0-218">Você pode exibir informações sobre</span><span class="sxs-lookup"><span data-stu-id="ecec0-218">You can view information about</span></span>

- <span data-ttu-id="ecec0-219">Estado de conformidade geral de dispositivos</span><span class="sxs-lookup"><span data-stu-id="ecec0-219">Overall compliance state of devices</span></span>
- <span data-ttu-id="ecec0-220">Estado de conformidade para uma configuração individual</span><span class="sxs-lookup"><span data-stu-id="ecec0-220">Compliance state for an individual setting</span></span>
- <span data-ttu-id="ecec0-221">Estado de conformidade para uma política individual</span><span class="sxs-lookup"><span data-stu-id="ecec0-221">Compliance state for an individual policy</span></span>

<span data-ttu-id="ecec0-222">Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as políticas que afetam esse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-222">You can also use these reports to drill down into an individual device to view specific settings and policies that affect that device.</span></span>
=======
## Abril de 2017
<a id="april-2017" class="xliff"></a>

### Suporte para gerenciamento do aplicativo Sala de Aula da Apple
<a id="support-for-managing-the-apple-classroom-app" class="xliff"></a>

Agora você pode gerenciar o aplicativo Sala de Aula de iOS em iPads. Configure o aplicativo Sala de Aula no iPad dos professores com os dados corretos de sala e de aluno, e configure os iPads do aluno registrados para uma sala, para que você possa controlá-los usando o aplicativo.
Para obter detalhes, confira [Definir as configurações de educação do iOS](education-settings-configure-ios.md).

### Suporte para opções de configuração gerenciada para aplicativos Android <!-- 621621 -->
<a id="support-for-managed-configuration-options-for-android-apps----621621---" class="xliff"></a>

Agora, os aplicativos Android na Play Store que oferecem suporte a opções de configuração gerenciada podem ser configurados pelo Intune.  Esse recurso permite que a TI exiba a lista de valores de configuração que têm suporte por um aplicativo e fornece uma interface do usuário interativa, de primeira classe para permitir que esses valores sejam configurados.

### Nova política de Android para PINs complexos <!-- 722069 -->
<a id="new-android-policy-for-complex-pins----722069---" class="xliff"></a>

Agora, você pode definir um tipo de [senha](device-restrictions-android.md#password) obrigatória como Numérico complexo em um perfil de dispositivo Android para dispositivos que executam o Android 5.0 e posterior.  Use essa configuração para impedir que os usuários dos dispositivos criem um PIN que contenha números consecutivos ou repetições, como 1111 ou 1234.

### Suporte adicional para dispositivos Android for Work
<a id="additional-support-for-android-for-work-devices" class="xliff"></a>

- **Gerencie as configurações de perfil de trabalho e senha**<!-- 612808 -->

  Agora, essa nova política de restrição para dispositivo Android for Work lhe permite gerenciar as configurações de perfil de trabalho e senha nos dispositivos Android for Work que você gerencia.

- **Permita o compartilhamento de dados entre perfis pessoais e de trabalho** <!-- 1045102 -->

Agora, essa política de restrição de dispositivo do Android for Work possui novas opções para ajudar você a configurar o compartilhamento de dados entre perfis pessoais e de trabalho.

- **Restrinja “copiar e colar” entre perfis de trabalho e pessoais**<!-- 1046094 -->

  Agora, um novo perfil de dispositivo personalizado para dispositivos Android for Work lhe permite restringir se são permitidas ações de copiar e colar entre aplicativos pessoais e de trabalho.

Para saber mais, confira [Restrições de dispositivo para Android for Work](device-restrictions-android-for-work.md).

### Atribua aplicativos LOB a dispositivos iOS e Android <!-- 1057568 -->
<a id="assign-lob-apps-to-ios-and-android-devices----1057568---" class="xliff"></a>

Agora, você pode atribuir aplicativos LOB (linha de negócios) para [iOS](lob-apps-ios.md) (arquivos .ipa) e [Android](lob-apps-android.md) (arquivos .apk) a usuários ou dispositivos.

###  Novas políticas de dispositivos para iOS <!-- 723774, 723815, 723826, 723830 -->
<a id="new-device-policies-for-ios----723774-723815-723826-723830---" class="xliff"></a>

- **Aplicativos na Tela inicial** – controla quais aplicativos os usuários veem na [Tela inicial de seus dispositivos iOS](home-screen-settings-ios.md). Essa política altera o layout da Tela inicial, mas não implanta nenhum aplicativo.

- **Conexões com dispositivos AirPrint** – controla a quais [dispositivos AirPrint](air-print-settings-ios-macos.md) (impressoras de rede) os usuários finais do dispositivo iOS podem se conectar.

- **Conexões com dispositivos AirPlay** – controla a quais [dispositivos AirPlay](airplay-settings-ios.md) (como a Apple TV) os usuários finais do dispositivo iOS podem se conectar.

- **Mensagem de tela de bloqueio personalizado** – configura uma mensagem personalizada que os usuários verão na tela de bloqueio de seu dispositivo iOS, que substitui a mensagem de tela de bloqueio padrão. Para obter mais informações, consulte [Ativar o modo perdido em dispositivos iOS](device-lost-mode.md)

### Restrinja as notificações por push para aplicativos iOS <!-- 723767 -->
<a id="restrict-push-notifications-for-ios-apps----723767---" class="xliff"></a>

Agora, em um perfil de restrição de dispositivo do Intune, você pode configurar os seguintes [ajustes de notificação](app-notification-settings-ios.md) para dispositivos iOS:

- Ative ou desative completamente a notificação de um aplicativo especificado.
- Ative ou desative a notificação no centro de notificações para um aplicativo especificado.
- Especifique o tipo de alerta, **nenhum**, **faixa** ou **alerta modal**.
- Especifique se são permitidos selos para esse aplicativo.
- Especifique se são permitidos sons de notificação.

### Configure aplicativos iOS para serem executados de forma independente no modo de aplicativo único <!-- 737837 -->
<a id="configure-ios-apps-to-run-in-single-app-mode-autonomously----737837---" class="xliff"></a>

Agora você pode usar um perfil de dispositivo do Intune para configurar dispositivos iOS para executar aplicativos especificados no [modo autônomo de aplicativo único](device-restrictions-ios.md#autonomous-single-app-mode-supervised-only). Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### Configure domínios confiáveis para email e navegação em dispositivos iOS <!-- 723765 -->
<a id="configure-trusted-domains-for-email-and-web-browsing-on-ios-devices----723765---" class="xliff"></a>

Agora, em um perfil de restrição de dispositivo iOS, você pode configurar os seguintes [ajustes de domínio](device-restrictions-ios.md#domains):

- **Domínios de email desmarcados** – Emails que o usuário envia ou recebe que não coincidam com os domínios que você especificar aqui serão marcados como não confiáveis.

- **Domínios da web gerenciados** – Documentos baixados de URLs que você especificar aqui serão considerados gerenciados (somente Safari).  

- **Domínios de preenchimento automático de senha do Safari** – Os usuários podem salvar senhas no Safari somente de URLs que correspondam aos padrões que você especificar aqui. Para usar essa configuração, o dispositivo deve estar no modo supervisionado e não configurado para vários usuários. (iOS 9.3+)


### Aplicativos VPP disponíveis no Portal da empresa iOS <!-- 748782 -->
<a id="vpp-apps-available-in-ios-company-portal----748782---" class="xliff"></a>

Agora você pode atribuir aplicativos iOS adquiridos com base em volume (VPP) como instalações **Disponíveis** para usuários finais. Os usuários finais precisarão de uma conta na Apple Store para instalar o aplicativo.

### Sincronize livros eletrônicos da Apple VPP Store <!-- 800878 -->
<a id="synchronize-ebooks-from-apple-vpp-store----800878---" class="xliff"></a>

Agora você pode [sincronizar os livros](vpp-apps-ios.md) adquiridos na loja de programa adquirido por volume da Apple com o Intune e atribuí-los aos usuários.

### Gerenciamento de vários usuários para dispositivos Samsung KNOX Standard <!-- 971988 -->
<a id="multi-user-management-for-samsung-knox-standard-devices----971988---" class="xliff"></a>

Agora há suporte para dispositivos que executam o Samsung KNOX Standard para o [gerenciamento de vários usuários](android-enroll.md) pelo Intune. Isso significa que os usuários finais podem entrar ou sair do dispositivo com suas credenciais do Azure Active Directory e o dispositivo é gerenciado centralmente independentemente de estar ou não em uso.  Quando os usuários finais entram, eles têm acesso a aplicativos e obtêm as políticas aplicadas a eles. Quando os usuários saem, todos os dados do aplicativo são removidos.

### Configurações adicionais de restrição de dispositivos no Windows <!-- 818566 -->
<a id="additional-windows-device-restriction-settings----818566---" class="xliff"></a>

Adicionamos suporte para outras [configurações de restrição de dispositivos no Windows](device-restrictions-windows-10.md), como suporte adicional ao navegador Edge, personalização da tela de bloqueio de dispositivo, personalizações do menu Iniciar, papel de parede definido por pesquisa do Windows Spotlight e configuração do proxy.

### Suporte a vários usuários para atualização do Windows 10 para criadores <!-- 822547 -->
<a id="multi-user-support-for-windows-10-creators-update----822547---" class="xliff"></a>

Adicionamos suporte para o [gerenciamento de vários usuários](windows-enroll.md) para dispositivos que executam a atualização do Windows 10 para criadores e estão ingressados no domínio do Azure Active Directory. Isso significa que, quando usuários padrão diferentes fizerem logon no dispositivo com suas credenciais do Azure AD, eles receberão quaisquer aplicativos e políticas que foram atribuídos ao seu nome de usuário. No momento, os usuários não podem usar o Portal da Empresa para cenários de autoatendimento, como a instalação de aplicativos.

### Começar do zero para PCs com Windows 10<!-- 1004830 -->
<a id="fresh-start-for-windows-10-pcs---1004830---" class="xliff"></a>

Agora há uma [nova ação de dispositivo para começar do zero](device-fresh-start.md) disponível em PCs com Windows 10.  Quando você executa esta ação, quaisquer aplicativos que foram instalados no computador são removidos e o PC é atualizado automaticamente para a versão mais recente do Windows. Isso pode ser usado para ajudar a remover aplicativos de OEM pré-instalados que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.

### Caminhos de atualização adicionais do Windows 10 <!-- 903672 -->
<a id="additional-windows-10-upgrade-paths----903672---" class="xliff"></a>

Agora você pode criar uma [política de atualização de edição para atualizar os dispositivos](edition-upgrade-configure-windows-10.md) para as seguintes edições adicionais do Windows 10:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N

### Registro em massa de dispositivos com Windows 10 <!-- 747607 -->
<a id="bulk-enroll-windows-10-devices----747607---" class="xliff"></a>

Ingresse uma quantidade grande de dispositivos que executam a atualização do Windows 10 para Criadores no Azure Active Directory e no Intune com o WCD (Windows Configuration Designer). Para habilitar o [registro em massa do MDM](windows-bulk-enroll.md) para seu locatário do Azure AD, crie um pacote de provisionamento que ingressa dispositivos ao seu locatário do Azure AD usando o Windows Configuration Designer e aplique o pacote aos dispositivos corporativos que você gostaria de registrar e gerenciar em massa. Quando o pacote for aplicado aos seus dispositivos, eles ingressarão no Azure AD, se registrarão no Intune e estarão prontos para logon de seus usuários do Azure AD.  Os usuários do Azure AD são usuários padrão nesses dispositivos e recebem políticas atribuídas e os aplicativos necessários. Não há suporte para cenários de autoatendimento e de Portal da Empresa no momento.

### Novas configurações de MAM para PIN e locais de armazenamento gerenciado <!-- 581122, 736644 -->
<a id="new-mam-settings-for-pin-and-managed-storage-locations----581122-736644---" class="xliff"></a>

Agora, duas novas configurações do aplicativo estão disponíveis para ajudá-lo com cenários de gerenciamento do aplicativo móvel (MAM):

- **Desabilite o PIN do aplicativo quando o PIN do dispositivo é gerenciado** – Detecta se um PIN do dispositivo está presente no dispositivo registrado e, nesse caso, ignora o PIN do aplicativo disparado pelas políticas de proteção de aplicativo. Essa configuração permitirá uma redução no número de vezes que uma solicitação de PIN é exibida para os usuários que abrem um aplicativo habilitado para MAM em um dispositivo registrado. Esse recurso está disponível para Android e iOS.

- **Selecione quais dados corporativos de serviços de armazenamento pode ser salvos em** – Permite-lhe especificar em quais locais de armazenamento deseja salvar os dados corporativos. Os usuários podem salvar nos serviços de localização de armazenamento selecionados, o que significa que todos os outros serviços de localização de armazenamento não listados serão bloqueados.

  Lista de serviços de localização de armazenamento com suporte:

  - OneDrive
  - Business SharePoint Online
  - Armazenamento local

### Portal de solução de problemas de suporte técnico <!-- 907448 -->
<a id="help-desk-troubleshooting-portal----907448---" class="xliff"></a>

O novo [portal de solução de problemas](help-desk-operators.md) permite que operadores de suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

## Março de 2017
<a id="march-2017" class="xliff"></a>

### Suporte para o Modo Perdido do iOS<!--431695-->
<a id="support-for-ios-lost-mode---431695--" class="xliff"></a>

Para o iOS 9.3 e dispositivos posteriores, o Intune adicionou suporte para o **Modo Perdido**. Agora, você pode bloquear um dispositivo para impedir o uso e exibir uma mensagem e número de telefone de contato da tela de bloqueio do dispositivo.

O usuário final não conseguirá desbloquear o dispositivo até que um administrador desative o Modo Perdido. Quando o Modo Perdido é habilitado, você pode usar a ação **Localizar dispositivo** para exibir a localização geográfica do dispositivo em um mapa no console do Intune.

O dispositivo deve ser um dispositivo iOS corporativo, inscrito pelo DEP e estar no modo supervisionado.

Para obter mais informações, consulte [O que é gerenciamento de dispositivos do Microsoft Intune](device-management.md)?

### Aprimoramentos para o relatório de Ações de Dispositivo <!--677150-->
<a id="improvements-to-device-actions-report---677150--" class="xliff"></a>

Fizemos aprimoramentos no relatório de Ações de Dispositivo para melhorar o desempenho. Além disso, agora você pode filtrar o relatório por estado. Por exemplo, você pode filtrar o relatório para mostrar somente as ações do dispositivo que foram concluídas.

### Categorias de aplicativo personalizadas <!--748805-->
<a id="custom-app-categories---748805--" class="xliff"></a>

Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### Atribuir aplicativos LOB para usuários com dispositivos não registrados <!--748823-->
<a id="assign-lob-apps-to-users-with-unenrolled-devices---748823--" class="xliff"></a>

Agora você pode atribuir aplicativos de linhas de negócios da loja para os usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo do usuário não estiver registrado no Intune, ele deverá ir para o site Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.

### Novos relatórios de conformidade <!--846671-->
<a id="new-compliance-reports---846671--" class="xliff"></a>

Agora você tem relatórios de conformidade que dão a postura de conformidade de dispositivos na sua empresa e permitem que você solucione rapidamente problemas relacionados à conformidade encontrados pelos usuários. Você pode exibir informações sobre

- Estado de conformidade geral de dispositivos
- Estado de conformidade para uma configuração individual
- Estado de conformidade para uma política individual

Você também pode usar esses relatórios para uma busca detalhada em um dispositivo individual para exibir as configurações específicas e as políticas que afetam esse dispositivo.
>>>>>>> live

<!--- You can now create an edition upgrade policy to upgrade devices to the following additional Windows 10 editions:

- Windows 10 Professional
- Windows 10 Professional N
- Windows 10 Professional Education
- Windows 10 Professional Education N --->

<<<<<<< HEAD
### <span data-ttu-id="ecec0-223">Acesso direto aos cenários de registro da Apple <!--951869--></span><span class="sxs-lookup"><span data-stu-id="ecec0-223">Direct access to Apple enrollment scenarios <!--951869--></span></span>
<a id="direct-access-to-apple-enrollment-scenarios---951869--" class="xliff"></a>

<span data-ttu-id="ecec0-224">Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="ecec0-224">For Intune accounts created after January 2017, Intune has enabled direct access to Apple enrollment scenarios using the Enroll Devices workload in the Azure portal.</span></span> <span data-ttu-id="ecec0-225">Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-225">Previously, the Apple enrollment preview was only accessible from links in the classic Intune portal.</span></span> <span data-ttu-id="ecec0-226">As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure.</span><span class="sxs-lookup"><span data-stu-id="ecec0-226">Intune accounts created before January 2017 will require a one-time migration before these features are available in Azure.</span></span> <span data-ttu-id="ecec0-227">A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível.</span><span class="sxs-lookup"><span data-stu-id="ecec0-227">The schedule for migration has not been announced yet, but details will be made available as soon as possible.</span></span> <span data-ttu-id="ecec0-228">É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.</span><span class="sxs-lookup"><span data-stu-id="ecec0-228">We strongly recommend creating a trial account to test out the new experience if your existing account cannot access the preview.</span></span>


## <span data-ttu-id="ecec0-229">Fevereiro de 2017</span><span class="sxs-lookup"><span data-stu-id="ecec0-229">February 2017</span></span>
<a id="february-2017" class="xliff"></a>

### <span data-ttu-id="ecec0-230">Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782--></span><span class="sxs-lookup"><span data-stu-id="ecec0-230">Ability to restrict mobile device enrollment <!--747600, 795782--></span></span>
<a id="ability-to-restrict-mobile-device-enrollment---747600-795782--" class="xliff"></a>
<span data-ttu-id="ecec0-231">O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar.</span><span class="sxs-lookup"><span data-stu-id="ecec0-231">Intune is adding new enrollment restrictions that control which mobile device platforms are allowed to enroll.</span></span> <span data-ttu-id="ecec0-232">O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.</span><span class="sxs-lookup"><span data-stu-id="ecec0-232">Intune separates mobile device platforms as iOS, macOS, Android, Windows and Windows Mobile.</span></span>

* <span data-ttu-id="ecec0-233">Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.</span><span class="sxs-lookup"><span data-stu-id="ecec0-233">Restricting mobile device enrollment does not restrict PC client enrollment.</span></span>  
* <span data-ttu-id="ecec0-234">Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.</span><span class="sxs-lookup"><span data-stu-id="ecec0-234">For iOS and Android only, there is one additional option to block the enrollment of personally owned devices.</span></span>

<span data-ttu-id="ecec0-235">O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).</span><span class="sxs-lookup"><span data-stu-id="ecec0-235">Intune marks all new devices as personal unless the IT admin takes action to mark them as corporate owned, as explained in [this article](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).</span></span>

### <span data-ttu-id="ecec0-236">Exibir todas as ações em dispositivos gerenciados <!--677150--></span><span class="sxs-lookup"><span data-stu-id="ecec0-236">View all actions on managed devices <!--677150--></span></span>
<a id="view-all-actions-on-managed-devices---677150--" class="xliff"></a>
<span data-ttu-id="ecec0-237">Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações.</span><span class="sxs-lookup"><span data-stu-id="ecec0-237">A new __Device Actions__ report shows who has performed remote actions like factory reset on devices, and additionally shows the status of that action.</span></span> <span data-ttu-id="ecec0-238">Consulte [O que é o gerenciamento de dispositivos?](device-management.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-238">See [What is device management?](device-management.md).</span></span>

### <span data-ttu-id="ecec0-239">Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691--></span><span class="sxs-lookup"><span data-stu-id="ecec0-239">Non-managed devices can access assigned apps <!--664691--></span></span>
<a id="non-managed-devices-can-access-assigned-apps---664691--" class="xliff"></a>
<span data-ttu-id="ecec0-240">Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados.</span><span class="sxs-lookup"><span data-stu-id="ecec0-240">As part of the design changes on the Company Portal website, iOS and Android users will be able to install apps assigned to them as "available without enrollment" on their non-managed devices.</span></span> <span data-ttu-id="ecec0-241">Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles.</span><span class="sxs-lookup"><span data-stu-id="ecec0-241">Using their Intune credentials, users will be able to log into the Company Portal website and see the list of apps assigned to them.</span></span> <span data-ttu-id="ecec0-242">Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ecec0-242">The app packages of the "available without enrollment" apps are made available for download via the Company Portal website.</span></span> <span data-ttu-id="ecec0-243">Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-243">Apps which require enrollment for installation are not affected by this change, as users will be prompted to enroll their device if they wish to install those apps.</span></span>

### <span data-ttu-id="ecec0-244">Categorias de aplicativo personalizadas <!--748805--></span><span class="sxs-lookup"><span data-stu-id="ecec0-244">Custom app categories <!--748805--></span></span>
<a id="custom-app-categories---748805--" class="xliff"></a>
<span data-ttu-id="ecec0-245">Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-245">You can now create, edit, and assign categories for apps you add to Intune.</span></span> <span data-ttu-id="ecec0-246">Atualmente, as categorias podem ser especificadas apenas em inglês.</span><span class="sxs-lookup"><span data-stu-id="ecec0-246">Currently, categories can only be specified in English.</span></span>
<span data-ttu-id="ecec0-247">Consulte [como adicionar um aplicativo ao Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-247">See [How to add an app to Intune](apps-add.md).</span></span>

### <span data-ttu-id="ecec0-248">Exibir categorias de dispositivos <!--814654--></span><span class="sxs-lookup"><span data-stu-id="ecec0-248">Display device categories <!--814654--></span></span>
<a id="display-device-categories---814654--" class="xliff"></a>
<span data-ttu-id="ecec0-249">Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-249">You can now view the device category as a column in the device list.</span></span> <span data-ttu-id="ecec0-250">Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-250">You can also edit the category from the properties section of the device properties blade.</span></span> <span data-ttu-id="ecec0-251">Consulte [como adicionar um aplicativo ao Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-251">See [How to add an app to Intune](apps-add.md).</span></span>

### <span data-ttu-id="ecec0-252">Definir as configurações do Windows Update para Empresas <!--776716--></span><span class="sxs-lookup"><span data-stu-id="ecec0-252">Configure Windows Update for Business settings <!--776716--></span></span>
<a id="configure-windows-update-for-business-settings---776716--" class="xliff"></a>

<span data-ttu-id="ecec0-253">O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="ecec0-253">Windows as a Service is the new way of providing updates for Windows 10.</span></span> <span data-ttu-id="ecec0-254">Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores.</span><span class="sxs-lookup"><span data-stu-id="ecec0-254">Starting with Windows 10, any new Feature Updates and Quality Updates will contain the contents of all previous updates.</span></span> <span data-ttu-id="ecec0-255">Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados.</span><span class="sxs-lookup"><span data-stu-id="ecec0-255">This means that as long as you've installed the latest update, you know that your Windows 10 devices are completely up-to-date.</span></span> <span data-ttu-id="ecec0-256">Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.</span><span class="sxs-lookup"><span data-stu-id="ecec0-256">Unlike with previous versions of Windows, you now must install the entire update instead of part of an update.</span></span>

<span data-ttu-id="ecec0-257">Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ecec0-257">By using Windows Update for Business, you can simplify the update management experience so that you don’t need to approve individual updates for groups of devices.</span></span> <span data-ttu-id="ecec0-258">Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo.</span><span class="sxs-lookup"><span data-stu-id="ecec0-258">You can still manage risk in your environments by configuring an update rollout strategy and Windows Update will make sure that updates are installed at right time.</span></span> <span data-ttu-id="ecec0-259">O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização.</span><span class="sxs-lookup"><span data-stu-id="ecec0-259">Microsoft Intune provides the ability to configure update settings on devices and gives you the ability to defer update installation.</span></span> <span data-ttu-id="ecec0-260">O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização.</span><span class="sxs-lookup"><span data-stu-id="ecec0-260">Intune doesn’t store the updates, but only the update policy assignment.</span></span> <span data-ttu-id="ecec0-261">Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="ecec0-261">Devices access Windows Update directly for the updates.Use Intune to configure and manage **Windows 10 update rings**.</span></span> <span data-ttu-id="ecec0-262">Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas.</span><span class="sxs-lookup"><span data-stu-id="ecec0-262">An update ring contains a group of settings that configure when and how Windows 10 updates get installed.</span></span> <span data-ttu-id="ecec0-263">Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](windows-update-for-business-configure.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-263">For details, see [Configure Windows Update for Business settings](windows-update-for-business-configure.md).</span></span>

## <span data-ttu-id="ecec0-264">Janeiro de 2017</span><span class="sxs-lookup"><span data-stu-id="ecec0-264">January 2017</span></span>
<a id="january-2017" class="xliff"></a>

### <span data-ttu-id="ecec0-265">Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748823--></span><span class="sxs-lookup"><span data-stu-id="ecec0-265">Assign line of business apps whether or not devices are enrolled <!--748823--></span></span>
<a id="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--" class="xliff"></a>
<span data-ttu-id="ecec0-266">Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune.</span><span class="sxs-lookup"><span data-stu-id="ecec0-266">You can now assign line of business and apps from the store to users whether or not their devices are enrolled with Intune.</span></span> <span data-ttu-id="ecec0-267">Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="ecec0-267">If the users device is not enrolled with Intune, they must go to the Company Portal website to install it, instead of the Company Portal app.</span></span> <span data-ttu-id="ecec0-268">Consulte [O que é o gerenciamento de aplicativo](app-management.md).</span><span class="sxs-lookup"><span data-stu-id="ecec0-268">See [What is app management](app-management.md).</span></span>

### <span data-ttu-id="ecec0-269">Resolva o problema em que os dispositivos iOS estão inativos ou o console de administração não pode se comunicar com eles</span><span class="sxs-lookup"><span data-stu-id="ecec0-269">Resolve issue where iOS devices are inactive, or the admin console cannot communicate with them</span></span>
<a id="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them" class="xliff"></a>
<span data-ttu-id="ecec0-270">Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa.</span><span class="sxs-lookup"><span data-stu-id="ecec0-270">When users’ devices lose contact with Intune, you can give them new troubleshooting steps to help them regain access to company resources.</span></span> <span data-ttu-id="ecec0-271">Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).</span><span class="sxs-lookup"><span data-stu-id="ecec0-271">See [Devices are inactive, or the admin console cannot communicate with them](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).</span></span>

## <span data-ttu-id="ecec0-272">Dezembro de 2016 (versão inicial)</span><span class="sxs-lookup"><span data-stu-id="ecec0-272">December 2016 (initial release)</span></span>
<a id="december-2016-initial-release" class="xliff"></a>

### <span data-ttu-id="ecec0-273">Integração do gerenciamento de despesas de telecomunicações no portal do Azure<!--747605--></span><span class="sxs-lookup"><span data-stu-id="ecec0-273">Telecom expense management integration in Azure portal<!--747605--></span></span>
<a id="telecom-expense-management-integration-in-azure-portal--747605--" class="xliff"></a>
<span data-ttu-id="ecec0-274">Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="ecec0-274">We are now beginning to preview integration with third-party telecom expense management (TEM) services within the Azure portal.</span></span> <span data-ttu-id="ecec0-275">Você pode usar o Intune para impor limites de uso de dados locais e móveis.</span><span class="sxs-lookup"><span data-stu-id="ecec0-275">You can use Intune to enforce limits on domestic and roaming data usage.</span></span> <span data-ttu-id="ecec0-276">Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com).</span><span class="sxs-lookup"><span data-stu-id="ecec0-276">We are beginning these integrations with [Saaswedo](http://www.saaswedo.com).</span></span> <span data-ttu-id="ecec0-277">Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).</span><span class="sxs-lookup"><span data-stu-id="ecec0-277">To enable this feature in your trial tenant, please [contact Microsoft support](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).</span></span>

- <span data-ttu-id="ecec0-278">Implantar e gerenciar aplicativos de um repositório para dispositivos iOS, Android e Windows</span><span class="sxs-lookup"><span data-stu-id="ecec0-278">Deploy and manage apps from a store to iOS, Android, and Windows devices</span></span>
- <span data-ttu-id="ecec0-279">Implantar e gerenciar aplicativos LOB (linha de negócios) para dispositivos iOS, Android e Windows</span><span class="sxs-lookup"><span data-stu-id="ecec0-279">Deploy and manage line of business (LOB) apps to iOS, Android, and Windows devices</span></span>
- <span data-ttu-id="ecec0-280">Implantar e gerenciar aplicativos adquiridos de volume para dispositivos iOS e Windows</span><span class="sxs-lookup"><span data-stu-id="ecec0-280">Deploy and manage volume-purchased apps to iOS, and Windows devices</span></span>
- <span data-ttu-id="ecec0-281">Implantar e gerenciar aplicativos Web para dispositivos Android, iOS e Windows</span><span class="sxs-lookup"><span data-stu-id="ecec0-281">Deploy and manage web apps for Android, iOS, and Windows devices</span></span>
- <span data-ttu-id="ecec0-282">Perfis de configuração do aplicativo gerenciado por iOS</span><span class="sxs-lookup"><span data-stu-id="ecec0-282">iOS managed app configuration profiles</span></span>
- <span data-ttu-id="ecec0-283">Configurar políticas de proteção de aplicativo e implantar aplicativos de linha de negócios em dispositivos que não são registrados com o Intune</span><span class="sxs-lookup"><span data-stu-id="ecec0-283">Configure app protection policies, and deploy line of business apps to devices that are not enrolled with Intune</span></span>
- <span data-ttu-id="ecec0-284">Perfis VPN, VPN por aplicativo, Wi-Fi, email e perfis de certificado</span><span class="sxs-lookup"><span data-stu-id="ecec0-284">VPN profiles, per-app VPN, Wi-Fi, email, and certificate profiles</span></span>
- <span data-ttu-id="ecec0-285">Políticas de conformidade</span><span class="sxs-lookup"><span data-stu-id="ecec0-285">Compliance policies</span></span>
- <span data-ttu-id="ecec0-286">Acesso condicional para Azure AD</span><span class="sxs-lookup"><span data-stu-id="ecec0-286">Conditional access for Azure AD</span></span>
- <span data-ttu-id="ecec0-287">Acesso condicional para Exchange Local</span><span class="sxs-lookup"><span data-stu-id="ecec0-287">Conditional access for On-Premises Exchange</span></span>
- <span data-ttu-id="ecec0-288">Registro de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ecec0-288">Device enrollment</span></span>
- <span data-ttu-id="ecec0-289">Controle de acesso baseado em função</span><span class="sxs-lookup"><span data-stu-id="ecec0-289">Role-based access control</span></span>

## <span data-ttu-id="ecec0-290">Recursos preteridos no Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="ecec0-290">Deprecated features in the Azure portal</span></span>
<a id="deprecated-features-in-the-azure-portal" class="xliff"></a>

### <span data-ttu-id="ecec0-291">Suporte para examinar de linha por linha dos identificadores de hardware</span><span class="sxs-lookup"><span data-stu-id="ecec0-291">Support for row-by-row review of hardware identifiers</span></span>
<a id="support-for-row-by-row-review-of-hardware-identifiers" class="xliff"></a>
<span data-ttu-id="ecec0-292">O Portal do Azure não dá suporte à analise de linha por linha de identificadores de hardware para números IMEI e números de série da Apple.</span><span class="sxs-lookup"><span data-stu-id="ecec0-292">The Azure portal does not support row-by-row review of hardware identifiers for IMEI numbers and Apple serial numbers.</span></span> <span data-ttu-id="ecec0-293">No console do Intune clássico, você pode importar detalhes de um arquivo valores separados por vírgulas (.csv) e substituir os detalhes existentes pelos identificadores de hardware individuais.</span><span class="sxs-lookup"><span data-stu-id="ecec0-293">In the classic Intune console, you can import details from a comma-separated-values (.csv) file and overwrite the existing details for individual hardware identifiers.</span></span> <span data-ttu-id="ecec0-294">O Portal do Azure apresenta uma única opção simplificada que automaticamente substitui detalhes para todos os identificadores de hardware ou ignora detalhes novos para identificadores existentes.</span><span class="sxs-lookup"><span data-stu-id="ecec0-294">The Azure portal features a single, streamlined option that automatically overwrites details for all hardware identifiers or ignores new details for existing identifiers.</span></span>

#### <span data-ttu-id="ecec0-295">Como isso afeta você</span><span class="sxs-lookup"><span data-stu-id="ecec0-295">How this affects you</span></span>
<a id="how-this-affects-you" class="xliff"></a>
<span data-ttu-id="ecec0-296">No Portal do Azure, você não poderá decidir, linha por linha, os dispositivos de identidade de equipamentos de móveis internacional (IMEI) para atualizar.</span><span class="sxs-lookup"><span data-stu-id="ecec0-296">In the Azure portal, you will not be able to decide, row by row, which International Mobile Equipment Identity (IMEI) devices to update.</span></span> <span data-ttu-id="ecec0-297">O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ecec0-297">The classic Intune console will continue to support this functionality.</span></span>

#### <span data-ttu-id="ecec0-298">Como se preparar para essa alteração</span><span class="sxs-lookup"><span data-stu-id="ecec0-298">How to get ready for this change</span></span>
<a id="how-to-get-ready-for-this-change" class="xliff"></a>
<span data-ttu-id="ecec0-299">Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração.</span><span class="sxs-lookup"><span data-stu-id="ecec0-299">We are providing this information in advance so, if it affects you, you can make your support admins aware of this change.</span></span> <span data-ttu-id="ecec0-300">Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.</span><span class="sxs-lookup"><span data-stu-id="ecec0-300">This change will coincide with the move to the Azure portal, anticipated for the first half of 2017.</span></span>


### <span data-ttu-id="ecec0-301">Suporte para o padrão perfis de registro de dispositivo corporativo em Apple DEP</span><span class="sxs-lookup"><span data-stu-id="ecec0-301">Support for default Corporate Device Enrollment profiles in Apple DEP</span></span>
<a id="support-for-default-corporate-device-enrollment-profiles-in-apple-dep" class="xliff"></a>
<span data-ttu-id="ecec0-302">O Portal do Azure não dá suporte para o perfil de registro de dispositivo corporativo "padrão" para números de série do dispositivo do DEP (Programa de registro de dispositivos) da Apple.</span><span class="sxs-lookup"><span data-stu-id="ecec0-302">The Azure portal does not support the “default” Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) device serial numbers.</span></span> <span data-ttu-id="ecec0-303">Essa funcionalidade, disponível no console do Intune clássico, está sendo descontinuada para impedir que os perfis atribuídos acidentalmente.</span><span class="sxs-lookup"><span data-stu-id="ecec0-303">This functionality, available in the classic Intune console, is being discontinued to prevent unintentionally assigned profiles.</span></span> <span data-ttu-id="ecec0-304">No Portal do Azure, os números de série sincronizados com base em uma conta de DEP da Apple inicialmente não terá nenhum perfil de registro de dispositivo corporativo atribuído.</span><span class="sxs-lookup"><span data-stu-id="ecec0-304">In the Azure portal, serial numbers synchronized from an Apple DEP account will initially have no Corporate Device Enrollment profile assigned.</span></span>

#### <span data-ttu-id="ecec0-305">Como isso afeta você</span><span class="sxs-lookup"><span data-stu-id="ecec0-305">How this affects you</span></span>
<a id="how-this-affects-you" class="xliff"></a>
<span data-ttu-id="ecec0-306">No Portal do Azure, você não poderá definir uma política de perfil padrão em todos os dispositivos da Apple.</span><span class="sxs-lookup"><span data-stu-id="ecec0-306">In the Azure portal, you will not be able to set a default profile policy across all Apple devices.</span></span> <span data-ttu-id="ecec0-307">O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ecec0-307">The classic Intune console will continue to support this functionality.</span></span>

#### <span data-ttu-id="ecec0-308">Como se preparar para essa alteração</span><span class="sxs-lookup"><span data-stu-id="ecec0-308">How to get ready for this change</span></span>
<a id="how-to-get-ready-for-this-change" class="xliff"></a>
<span data-ttu-id="ecec0-309">Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração.</span><span class="sxs-lookup"><span data-stu-id="ecec0-309">We are providing this information in advance so, if it affects you, you can make your support admins aware of this change.</span></span> <span data-ttu-id="ecec0-310">Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.</span><span class="sxs-lookup"><span data-stu-id="ecec0-310">This will coincide with the move to the Azure portal, anticipated for the first half of 2017.</span></span>

### <span data-ttu-id="ecec0-311">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ecec0-311">See also</span></span>
<a id="see-also" class="xliff"></a>
<span data-ttu-id="ecec0-312">Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.</span><span class="sxs-lookup"><span data-stu-id="ecec0-312">See [What’s New in Microsoft Intune](whats-new.md) for details on recent developments.</span></span>
=======
### Acesso direto aos cenários de registro da Apple <!--951869-->
<a id="direct-access-to-apple-enrollment-scenarios---951869--" class="xliff"></a>

Para contas do Intune criadas após janeiro de 2017, o Intune habilitou o acesso direto aos cenários de registro da Apple usando a carga de trabalho Registrar Dispositivos no portal do Azure. Anteriormente, a visualização de registro da Apple só estava acessível a partir de links no portal clássico do Intune. As contas do Intune criadas antes de janeiro de 2017 exigirão uma migração única antes de esses recursos estarem disponíveis no Azure. A agenda de migração ainda não foi anunciada, mas os detalhes serão disponibilizados assim que possível. É altamente recomendável criar uma conta de avaliação para testar a nova experiência se sua conta existente não puder acessar a visualização.


## Fevereiro de 2017
<a id="february-2017" class="xliff"></a>

### Capacidade de restringir o registro de dispositivos móveis <!--747600, 795782-->
<a id="ability-to-restrict-mobile-device-enrollment---747600-795782--" class="xliff"></a>
O Intune está adicionando novas restrições de registro que controlam quais plataformas de dispositivos móveis têm permissão para registrar. O Intune separa plataformas de dispositivos móveis como iOS, macOS, Android, Windows e Windows Mobile.

* Restringir o registro do dispositivo móvel não restringe o registro de cliente do computador.  
* Apenas para iOS e Android, há uma opção adicional para bloquear o registro de dispositivos de propriedade pessoal.

O Intune marca todos os novos dispositivos como pessoais, a menos que o administrador de TI marque-os como de propriedade corporativa, conforme explicado [neste artigo](https://docs.microsoft.com/intune-classic/deploy-use/manage-corporate-owned-devices).

### Exibir todas as ações em dispositivos gerenciados <!--677150-->
<a id="view-all-actions-on-managed-devices---677150--" class="xliff"></a>
Um novo relatório __Ações de Dispositivo__ mostra quem realizou ações remotas como redefinição de fábrica em dispositivos e, além disso, mostra o status dessas ações. Consulte [O que é o gerenciamento de dispositivos?](device-management.md).

### Dispositivos não gerenciados podem acessar aplicativos atribuídos <!--664691-->
<a id="non-managed-devices-can-access-assigned-apps---664691--" class="xliff"></a>
Como parte das alterações de design no site do Portal da Empresa, usuários de iOS e Android serão capazes de instalar os aplicativos atribuídos a eles como "disponíveis sem registro" em seus dispositivos não gerenciados. Usando suas credenciais do Intune, os usuários poderão fazer logon no site do Portal da Empresa e ver a lista de aplicativos atribuídos a eles. Os pacotes de aplicativo dos aplicativos "disponíveis sem registro" são disponibilizados para download por meio do site do Portal da Empresa. Aplicativos que exigem o registro para a instalação não são afetados por essa alteração, já que será solicitado que os usuários registrem seus dispositivos se quiserem instalar esses aplicativos.

### Categorias de aplicativo personalizadas <!--748805-->
<a id="custom-app-categories---748805--" class="xliff"></a>
Agora você pode criar, editar e atribuir categorias aos aplicativos adicionados ao Intune. Atualmente, as categorias podem ser especificadas apenas em inglês.
Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### Exibir categorias de dispositivos <!--814654-->
<a id="display-device-categories---814654--" class="xliff"></a>
Agora você pode exibir a categoria de dispositivo como uma coluna na lista de dispositivos. Você também pode editar a categoria da seção de propriedades da folha de propriedades do dispositivo. Consulte [como adicionar um aplicativo ao Intune](apps-add.md).

### Definir as configurações do Windows Update para Empresas <!--776716-->
<a id="configure-windows-update-for-business-settings---776716--" class="xliff"></a>

O Windows como um Serviço é a nova maneira de fornecer atualizações para o Windows 10. Começando no Windows 10, quaisquer novas Atualizações de Recursos e Atualizações de Qualidade terão o conteúdo de todas as atualizações anteriores. Isso significa que contanto que você tenha instalado a atualização mais recente, sabe que seus dispositivos do Windows 10 estão completamente atualizados. Ao contrário das versões anteriores do Windows, agora você deve instalar a atualização inteira, em vez de parte de uma.

Usando o Windows Update para Empresas, você pode simplificar a experiência de gerenciamento da atualização para que não precise aprovar as atualizações individuais para os grupos de dispositivos. Você ainda pode gerenciar os riscos em seus ambientes configurando uma estratégia de distribuição de atualização e o Windows Update irá assegurar que as atualizações sejam instaladas no momento certo. O Microsoft Intune fornece a capacidade de definir as configurações da atualização nos dispositivos e oferece a capacidade de adiar a instalação da atualização. O Intune não armazena as atualizações, mas apenas a atribuição da política de atualização. Os dispositivos acessam o Windows Update diretamente para as atualizações. Use o Intune para configurar e gerenciar os **anéis de atualização do Windows 10**. Um anel de atualização contém um grupo de configurações que definem quando e como as atualizações do Windows 10 são instaladas. Para obter detalhes, consulte [Definir as configurações do Windows Update para Empresas](windows-update-for-business-configure.md).

## Janeiro de 2017
<a id="january-2017" class="xliff"></a>

### Atribuir aplicativos de linha de negócios independentemente de os dispositivos estarem registrados ou não <!--748823-->
<a id="assign-line-of-business-apps-whether-or-not-devices-are-enrolled---748823--" class="xliff"></a>
Agora você pode atribuir aplicativos de linhas de negócios e aplicativos da loja aos usuários, independentemente de seus dispositivos estarem registrados ou não no Intune. Se o dispositivo dos usuários não estiver registrado no Intune, eles deverão acessar o site do Portal da Empresa para instalá-lo, em vez do aplicativo Portal da Empresa. Consulte [O que é o gerenciamento de aplicativo](app-management.md).

### Resolva o problema em que os dispositivos iOS estão inativos ou o console de administração não pode se comunicar com eles
<a id="resolve-issue-where-ios-devices-are-inactive-or-the-admin-console-cannot-communicate-with-them" class="xliff"></a>
Quando os dispositivos dos usuários perdem contato com o Intune, você pode fornecer novas etapas de solução de problemas para ajudá-los a recuperar o acesso aos recursos da empresa. Consulte [Os dispositivos estão inativos ou o console de administração não pode se comunicar com eles](enrollment-troubleshoot.md#devices-are-inactive-or-the-admin-console-cannot-communicate-with-them).

## Dezembro de 2016 (versão inicial)
<a id="december-2016-initial-release" class="xliff"></a>

### Integração do gerenciamento de despesas de telecomunicações no portal do Azure<!--747605-->
<a id="telecom-expense-management-integration-in-azure-portal--747605--" class="xliff"></a>
Agora estamos começando a visualizar a integração com serviços de gerenciamento de despesas de telecomunicações de terceiros (TEM) no portal do Azure. Você pode usar o Intune para impor limites de uso de dados locais e móveis. Estamos começando essas integrações com o [Saaswedo](http://www.saaswedo.com). Para habilitar esse recurso no locatário de teste, [contate o Suporte da Microsoft](https://docs.microsoft.com/intune-classic/troubleshoot/get-support).

- Implantar e gerenciar aplicativos de um repositório para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos LOB (linha de negócios) para dispositivos iOS, Android e Windows
- Implantar e gerenciar aplicativos adquiridos de volume para dispositivos iOS e Windows
- Implantar e gerenciar aplicativos Web para dispositivos Android, iOS e Windows
- Perfis de configuração do aplicativo gerenciado por iOS
- Configurar políticas de proteção de aplicativo e implantar aplicativos de linha de negócios em dispositivos que não são registrados com o Intune
- Perfis VPN, VPN por aplicativo, Wi-Fi, email e perfis de certificado
- Políticas de conformidade
- Acesso condicional para Azure AD
- Acesso condicional para Exchange Local
- Registro de dispositivo
- Controle de acesso baseado em função

## Recursos preteridos no Portal do Azure
<a id="deprecated-features-in-the-azure-portal" class="xliff"></a>

### Suporte para examinar de linha por linha dos identificadores de hardware
<a id="support-for-row-by-row-review-of-hardware-identifiers" class="xliff"></a>
O Portal do Azure não dá suporte à analise de linha por linha de identificadores de hardware para números IMEI e números de série da Apple. No console do Intune clássico, você pode importar detalhes de um arquivo valores separados por vírgulas (.csv) e substituir os detalhes existentes pelos identificadores de hardware individuais. O Portal do Azure apresenta uma única opção simplificada que automaticamente substitui detalhes para todos os identificadores de hardware ou ignora detalhes novos para identificadores existentes.

#### Como isso afeta você
<a id="how-this-affects-you" class="xliff"></a>
No Portal do Azure, você não poderá decidir, linha por linha, os dispositivos de identidade de equipamentos de móveis internacional (IMEI) para atualizar. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### Como se preparar para essa alteração
<a id="how-to-get-ready-for-this-change" class="xliff"></a>
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.


### Suporte para o padrão perfis de registro de dispositivo corporativo em Apple DEP
<a id="support-for-default-corporate-device-enrollment-profiles-in-apple-dep" class="xliff"></a>
O Portal do Azure não dá suporte para o perfil de registro de dispositivo corporativo "padrão" para números de série do dispositivo do DEP (Programa de registro de dispositivos) da Apple. Essa funcionalidade, disponível no console do Intune clássico, está sendo descontinuada para impedir que os perfis atribuídos acidentalmente. No Portal do Azure, os números de série sincronizados com base em uma conta de DEP da Apple inicialmente não terá nenhum perfil de registro de dispositivo corporativo atribuído.

#### Como isso afeta você
<a id="how-this-affects-you" class="xliff"></a>
No Portal do Azure, você não poderá definir uma política de perfil padrão em todos os dispositivos da Apple. O Console Clássico do Intune continuará a dar suporte a essa funcionalidade.

#### Como se preparar para essa alteração
<a id="how-to-get-ready-for-this-change" class="xliff"></a>
Estamos fornecendo essas informações com antecedência para que, se afetar você, você pode deixar seus administradores de suporte a par dessa alteração. Essa alteração coincidirá com a mudança para o Portal do Azure, prevista para o primeiro semestre de 2017.

### Consulte também
<a id="see-also" class="xliff"></a>
Veja [Novidades do Microsoft Intune](whats-new.md) para saber detalhes sobre os desenvolvimentos mais recentes.
>>>>>>> live
