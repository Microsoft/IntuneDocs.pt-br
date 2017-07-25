---
title: "Configurações de restrições de dispositivo do Intune para iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73590192-54ca-4833-9f1d-83e1b654399f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7ec66c3864aae3d680c006ada95859df0e7f0e84
ms.sourcegitcommit: fb17b59f4aa2b994b149fcc6d32520f74b0de6a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
<<<<<<< HEAD
# <span data-ttu-id="069b2-103">Configurações de restrição de dispositivo iOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="069b2-103">iOS device restriction settings in Microsoft Intune</span></span>
=======
# Configurações de restrição de dispositivo iOS no Microsoft Intune
>>>>>>> live
<a id="ios-device-restriction-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
## <span data-ttu-id="069b2-104">Geral</span><span class="sxs-lookup"><span data-stu-id="069b2-104">General</span></span>
<a id="general" class="xliff"></a>
-   <span data-ttu-id="069b2-105">**Câmera** – Especifica se a câmera no dispositivo pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="069b2-105">**Camera** - Select whether the camera on the device can be used.</span></span>   
-   <span data-ttu-id="069b2-106">**Envio de dados de diagnóstico** – Permitir ou bloquear a habilidade do dispositivo enviar dados de diagnóstico para a Apple.</span><span class="sxs-lookup"><span data-stu-id="069b2-106">**Diagnostic data submission** - Allow or block the device from submitting diagnostic data to Apple.</span></span>
-   <span data-ttu-id="069b2-107">**FaceTime** – Permitir que o aplicativo FaceTime seja usado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-107">**FaceTime** - Allow the FaceTime app to be used on the device.</span></span>
-   <span data-ttu-id="069b2-108">**Captura de tela** – Permitir ao usuário capturar os conteúdos da tela como uma imagem.</span><span class="sxs-lookup"><span data-stu-id="069b2-108">**Screen capture** - Allow the user to capture the contents of the screen as an image.</span></span>
-   <span data-ttu-id="069b2-109">**Siri** – Permitir o uso da assistente de voz Siri no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-109">**Siri** - Allow use of the Siri voice assistant on the device.</span></span>
    -   <span data-ttu-id="069b2-110">**Siri quando o dispositivo estiver bloqueado** – Permitir o uso da Assistente de voz Siri no dispositivo enquanto ele estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="069b2-110">**Siri while device is locked** - Allow use of the Siri voice assistant on the device while it is locked.</span></span>
    -   <span data-ttu-id="069b2-111">**Filtro de profanação da Siri (somente supervisionado)** – Impede que a Siri dite ou use linguagem ofensiva.</span><span class="sxs-lookup"><span data-stu-id="069b2-111">**Siri profanity filter (supervised only)** - Prevents Siri from dictating, or speaking profane language.</span></span>
    -   <span data-ttu-id="069b2-112">**Siri deve consultar o conteúdo gerado pelo usuário da Internet (somente supervisionado)** – Permitir que Siri acesse sites da Web para responder a perguntas.</span><span class="sxs-lookup"><span data-stu-id="069b2-112">**Siri to query user-generated content from the internet (supervised only)** - Allow Siri to access websites to answer questions.</span></span>
-   <span data-ttu-id="069b2-113">**Certificados TLS não confiáveis** – Permitir certificados do protocolo TLS não confiáveis no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-113">**Untrusted TLS certificates** - Allow untrusted Transport Layer Security certificates on the device.</span></span>
-   <span data-ttu-id="069b2-114">**Controlar acesso à central quando o dispositivo está bloqueado** – Permitir ao usuário acessar o aplicativo de Central de Controle quando o dispositivo estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="069b2-114">**Control Center access while device locked** - Allow the user to access the control center app when the device is locked.</span></span>
-   <span data-ttu-id="069b2-115">**Notificações enquanto o dispositivo está bloqueado** – Permitir ao usuário acessar a exibição de notificações sem desbloquear o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-115">**Notifications while device locked** - Allow the user to access the notifications view without unlocking the device.</span></span>
-   <span data-ttu-id="069b2-116">**Passbook enquanto o dispositivo está bloqueado** – Permitir ao usuário acessar o aplicativo Passbook enquanto o dispositivo estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="069b2-116">**Passbook while device locked** - Allow the user to access the Passbook app while the device is locked.</span></span>
-   <span data-ttu-id="069b2-117">**Exibição Hoje enquanto o dispositivo está bloqueado** – Permitir que o usuário veja o a exibição Hoje quando o dispositivo estiver bloqueado.</span><span class="sxs-lookup"><span data-stu-id="069b2-117">**Today view while device locked** - Allow the user to see the Today view when the device is locked.</span></span>
-   <span data-ttu-id="069b2-118">**Aplicativos de confiança da empresa** – Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-118">**Enterprise app trust** - Lets the user select to trust apps that were not downloaded from the app store.</span></span>
-   <span data-ttu-id="069b2-119">**AirDrop (somente supervisionado)** – Permitir o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.</span><span class="sxs-lookup"><span data-stu-id="069b2-119">**AirDrop (supervised only)** - Allow use of the AirDrop feature to exchange content with nearby devices.</span></span>
-   <span data-ttu-id="069b2-120">**Pesquisa de destaque retorna resultados da internet (somente supervisionado)** – Permitir que a pesquisa de Destaque se conecte à Internet para fornecer mais resultados.</span><span class="sxs-lookup"><span data-stu-id="069b2-120">**Spotlight search to return results from internet (supervised only)** - Let Spotlight search connect to the Internet to provide further results.</span></span>
-   <span data-ttu-id="069b2-121">**Pesquisa por definição de palavra (somente supervisionado)** – Permitir o recurso do iOS que permite realçar uma palavra e pesquisar sua definição.</span><span class="sxs-lookup"><span data-stu-id="069b2-121">**Word definition lookup (supervised only)** - Allow the iOS feature that lets you highlight a word and look up it's definition.</span></span>
-   <span data-ttu-id="069b2-122">**Teclados preditivos (somente supervisionado)** – Permitir o uso de teclados preditivos que sugerem palavras que o usuário pode querer.</span><span class="sxs-lookup"><span data-stu-id="069b2-122">**Predictive keyboards (supervised only)** - Allow the use of predictive keyboards that suggest words the user might want.</span></span>
-   <span data-ttu-id="069b2-123">**Correção automática (somente supervisionado)** – Permite que o dispositivo corrija automaticamente palavras incorretas.</span><span class="sxs-lookup"><span data-stu-id="069b2-123">**Auto-correction (supervised only)** - Lets the device automatically correct misspelled words.</span></span>
-   <span data-ttu-id="069b2-124">**Verificação ortográfica do teclado (somente supervisionada)**  – Permite usar o verificador de ortografia do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-124">**Keyboard spell-check (supervised only)** - Allows the device spell checker.</span></span>
-   <span data-ttu-id="069b2-125">**Atalhos de teclado (somente supervisionado)** – Permite o uso de atalhos de teclado.</span><span class="sxs-lookup"><span data-stu-id="069b2-125">**Keyboard shortcuts (supervised only)** - Allows use of keyboard shortcuts.</span></span>
-   <span data-ttu-id="069b2-126">**Detecção de pulso para Apple Watch emparelhado** – Quando habilitada, o Apple Watch não exibirá notificações quando não estiver sendo usado.</span><span class="sxs-lookup"><span data-stu-id="069b2-126">**Wrist detection for paired Apple watch** - When enabled, the Apple Watch won't display notifications when it is not being worn.</span></span>
- <span data-ttu-id="069b2-127">**Exigir uma senha de emparelhamento de solicitações de saída do AirPlay** – Exigir uma senha emparelhamento quando o usuário usar AirPlay para transmitir o conteúdo para outros dispositivos da Apple.</span><span class="sxs-lookup"><span data-stu-id="069b2-127">**Require AirPlay outgoing requests pairing password** - Require a pairing password when the user uses AirPlay to stream content to other Apple devices.</span></span>
- <span data-ttu-id="069b2-128">**Modificação de conta (somente com supervisão)** - Quando é bloqueada, impede que o usuário modifique as configurações específicas do dispositivo no aplicativo de configurações do iOS, como a criação de novas contas de dispositivo e alteração do nome de usuário ou senha.</span><span class="sxs-lookup"><span data-stu-id="069b2-128">**Account modification (supervised only)** - When blocked, this prevents the user from modifying device-specific settings from the iOS settings app, like creating new device accounts, and changing the user name or password.</span></span>
<span data-ttu-id="069b2-129">Isso também se aplica às configurações acessadas no aplicativo de configurações do iOS, como Mail, Contatos, Calendário, Facebook e Twitter.</span><span class="sxs-lookup"><span data-stu-id="069b2-129">This also applies to settings accessible from the iOS settings app like Mail, Contacts, Calendar, Facebook, and Twitter.</span></span> <span data-ttu-id="069b2-130">Isso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo de configurações do iOS, por exemplo, o aplicativo Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="069b2-130">This does not apply to apps with account settings that are not configurable from the iOS settings app, for example, the Microsoft Outlook app.</span></span>
- <span data-ttu-id="069b2-131">**Emparelhamento de Apple Watch (somente supervisionado)** – Permite que o dispositivo seja emparelhado com um Apple Watch.</span><span class="sxs-lookup"><span data-stu-id="069b2-131">**Apple Watch pairing (supervised only)** - Allow the device to pair with an Apple Watch.</span></span>
- <span data-ttu-id="069b2-132">**Modificação de Bluetooth (somente supervisionado)** – Impede o usuário final de alterar as configurações de Bluetooth no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-132">**Bluetooth modification (supervised only)** - Block the end user from changing Bluetooth settings on the device.</span></span>
- <span data-ttu-id="069b2-133">**Observação de tela remota pelo aplicativo Classroom (somente supervisionado)** – Permitir ou bloquear que o aplicativo Classroom observe a tela em dispositivos remotos.</span><span class="sxs-lookup"><span data-stu-id="069b2-133">**Remote screen observation by Classroom app (supervised only)** - Allow or block the Classroom app from observing the screen on remote devices.</span></span>
- <span data-ttu-id="069b2-134">**Habilitar restrições nas configurações do dispositivo (somente supervisionado)** – Permitir que o usuário configure restrições de dispositivo (controles dos pais) no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-134">**Enabling restrictions in the device settings (supervised only)** - Allow the user to configure device restrictions (parental controls) on the device.</span></span>
- <span data-ttu-id="069b2-135">**Usar o apagamento total do conteúdo e das opções de configurações no dispositivo (somente supervisionado)** – Permitir que o usuário utilize a opção de apagar todo o conteúdo e as configurações no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-135">**Use of the erase all content and settings option on the device (supervised only)** - Allow the user to use the option of erasing all content and settings on the device.</span></span>
- <span data-ttu-id="069b2-136">**Modificação do nome de dispositivo (somente supervisionado)** – Permitir que o usuário altere o nome do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-136">**Device name modification (supervised only)** - Allow the user to change the name of the device.</span></span>
- <span data-ttu-id="069b2-137">**Modificação de configurações de envio de diagnóstico (somente supervisionado)** – Permitir ou bloquear que o dispositivo envie dados de diagnóstico para a Apple.</span><span class="sxs-lookup"><span data-stu-id="069b2-137">**Diagnostics submission settings modification (supervised only)** - Allow or block the device from submitting diagnostic data to Apple.</span></span>
- <span data-ttu-id="069b2-138">**Emparelhamento de host para controlar os dispositivos aos quais um dispositivo iOS pode ser emparelhado (somente supervisionado)** – Permitir emparelhamento de host para que o administrador controle com quais dispositivos um dispositivo iOS pode ser emparelhado.</span><span class="sxs-lookup"><span data-stu-id="069b2-138">**Host pairing to control the devices an iOS device can pair with (supervised only)** - Allow host pairing to let the administrator control which devices an iOS device can pair with.</span></span>
- <span data-ttu-id="069b2-139">**Modificação das configurações de notificação (somente supervisionado)** – Permitir que o usuário altere as configurações de notificação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-139">**Notification settings modification (supervised only)** - Allow the user to change the device notification settings.</span></span>
- <span data-ttu-id="069b2-140">**Modificação da senha (somente supervisionado)** – Permitir que a senha do dispositivo seja adicionada, alterada ou removida.</span><span class="sxs-lookup"><span data-stu-id="069b2-140">**Passcode modification (supervised only)** - Allow the device password to be added, changed, or removed.</span></span>
- <span data-ttu-id="069b2-141">**Modificação do papel de parede (somente supervisionado)** – Permitir que o usuário altere o papel de parede do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-141">**Wallpaper modification (supervised only)** - Allow the user to change the device wallpaper.</span></span>
- <span data-ttu-id="069b2-142">**Modificação das configurações de aplicativo de confiança da empresa** – Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-142">**Enterprise app trust settings modification (supervised only)** - Lets the user select to trust apps that were not downloaded from the app store.</span></span>
- <span data-ttu-id="069b2-143">**Instalar aplicativos da App Store (apenas no modo supervisionado)** – Permitir que o dispositivo acesse a loja de aplicativos e instale aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-143">**Installing apps from App Store (supervised only)** - Allow the device to access the app store and install apps.</span></span>
- <span data-ttu-id="069b2-144">**Alterações nas configurações de aplicativo de Find My Friends (somente supervisionados)** – Permitir que o usuário altere as configurações para o aplicativo Find My Friends.</span><span class="sxs-lookup"><span data-stu-id="069b2-144">**Changes to the Find My Friends app settings (supervised only)** - Allow the user to change settings for the Find My Friends app.</span></span>
- <span data-ttu-id="069b2-145">**iBooks Store (somente supervisionado)** – Permitir que o usuário procure e compre livros da iBooks Store.</span><span class="sxs-lookup"><span data-stu-id="069b2-145">**iBooks store (supervised only)** - Allow the user to browse and purchase books from the iBooks store.</span></span>
- <span data-ttu-id="069b2-146">**Aplicativo de mensagens no dispositivo (somente supervisionado)** – Permite usar o aplicativo de Mensagens para enviar e ler mensagens de texto.</span><span class="sxs-lookup"><span data-stu-id="069b2-146">**Messages app on the device (supervised only)** - Allow use of the Messages app to send and read text messages.</span></span>
- <span data-ttu-id="069b2-147">**Podcasts (somente supervisionado)** – Permitir o uso do aplicativo Podcasts.</span><span class="sxs-lookup"><span data-stu-id="069b2-147">**Podcasts (supervised only)** - Allow use of the Podcasts app.</span></span>
- <span data-ttu-id="069b2-148">**Serviço de Música (somente supervisionado)** – Permitir o uso do aplicativo Apple Music.</span><span class="sxs-lookup"><span data-stu-id="069b2-148">**Music service (supervised only)** - Allow use of the Apple Music app.</span></span>
- <span data-ttu-id="069b2-149">**Serviço do iTunes Radio (somente supervisionado)** – Permitir o uso do aplicativo iTunes Radio.</span><span class="sxs-lookup"><span data-stu-id="069b2-149">**iTunes Radio service (supervised only)** - Allow use of the iTunes Radio app.</span></span>
- <span data-ttu-id="069b2-150">**Apple News (somente supervisionado)** – Permitir o uso do aplicativo Apple News.</span><span class="sxs-lookup"><span data-stu-id="069b2-150">**Apple News (supervised only)** - Allow use of the Apple News app.</span></span>
- <span data-ttu-id="069b2-151">**Alterações de perfil de configuração** – Permitir que o usuário instale perfis de configuração.</span><span class="sxs-lookup"><span data-stu-id="069b2-151">**Configuration profile changes** - Allow the user to install configuration profiles.</span></span>

## <span data-ttu-id="069b2-152">Senha</span><span class="sxs-lookup"><span data-stu-id="069b2-152">Password</span></span>
<a id="password" class="xliff"></a>
-   <span data-ttu-id="069b2-153">**Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-153">**Password required** - Require the end user to enter a password to access the device.</span></span>
-   <span data-ttu-id="069b2-154">**Senhas simples** – Permitir senhas simples como 0000 e 1234.</span><span class="sxs-lookup"><span data-stu-id="069b2-154">**Simple passwords** - Allow simple passwords like 0000 and 1234.</span></span>
-   <span data-ttu-id="069b2-155">**Tipo de senha exigida** – Especificar o tipo de senha necessária, como apenas numérica ou alfanumérica.</span><span class="sxs-lookup"><span data-stu-id="069b2-155">**Required password type** - Specify the type of password that will be required, such as numeric only or alphanumeric.</span></span>
-   <span data-ttu-id="069b2-156">**Número de caracteres não alfanuméricos na senha** – Especifique o número de caracteres de símbolo (como **#** ou **@**) que devem ser incluídos na senha.</span><span class="sxs-lookup"><span data-stu-id="069b2-156">**Number of non-alphanumeric characters in password** - Specify the number of symbol characters (like **#** or **@**) that must be included in the password.</span></span>
-   <span data-ttu-id="069b2-157">**Tamanho mínimo de senha** – Especificar o número mínimo de caracteres na senha.</span><span class="sxs-lookup"><span data-stu-id="069b2-157">**Minimum password length** - Specify the minimum number of characters in the password.</span></span>
-   <span data-ttu-id="069b2-158">**Número de falhas de entrada antes de apagar o dispositivo** – Especificar o número de tentativas de logon antes de essa configuração apagar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-158">**Number of sign-in failures before wiping device** - Specify the number of failed login attempts before this setting wipes the device.</span></span>
-   <span data-ttu-id="069b2-159">**Máximo de minutos após o bloqueio de tela antes da senha ser necessária**<sup>1</sup> – Especifique quanto tempo o dispositivo pode permanecer ocioso antes que o usuário precise digitar novamente sua senha.</span><span class="sxs-lookup"><span data-stu-id="069b2-159">**Maximum minutes after screen lock before password is required**<sup>1</sup> - Specify how long the device can remain idle before the user must re-enter their password.</span></span>
-   <span data-ttu-id="069b2-160">**Máximo de minutos de inatividade até o bloqueio de tela**<sup>1</sup> – Especifique o número de minutos antes que a tela do dispositivo seja desativada.</span><span class="sxs-lookup"><span data-stu-id="069b2-160">**Maximum minutes of inactivity until screen locks**<sup>1</sup> - Specify the number of minutes before the device display is turned off.</span></span>
-   <span data-ttu-id="069b2-161">**Expiração da senha (dias)** – Especifique o número de dias antes que a senha do dispositivo precise ser alterada.</span><span class="sxs-lookup"><span data-stu-id="069b2-161">**Password expiration (days)** - Specify the number of days before the device password must be changed.</span></span>
-   <span data-ttu-id="069b2-162">**Impedir a reutilização de senhas anteriores** – Especifique o número de senhas usadas anteriormente que o dispositivo lembra.</span><span class="sxs-lookup"><span data-stu-id="069b2-162">**Prevent reuse of previous passwords** - Specify the number of previously used passwords that the device remembers.</span></span>
-   <span data-ttu-id="069b2-163">**Desbloqueio por impressão digital** – Permite usar uma impressão digital para desbloquear dispositivos compatíveis.</span><span class="sxs-lookup"><span data-stu-id="069b2-163">**Fingerprint unlock** - Allow using a fingerprint to unlock compatible devices.</span></span>

<span data-ttu-id="069b2-164"><sup>1</sup>Quando você configura as definições **Máximo de minutos inatividade até o bloqueio de tela** e **Máximo de minutos após o bloqueio de tela antes da senha ser necessária**, eles são aplicados em sequência.</span><span class="sxs-lookup"><span data-stu-id="069b2-164"><sup>1</sup>When you configure the settings **Maximum minutes of inactivity until screen locks** and **Maximum minutes after screen lock before password is required**, they are applied in sequence.</span></span> <span data-ttu-id="069b2-165">Por exemplo, se você define o valor de ambas as configurações para **5** minutos, a tela desliga automaticamente após 5 minutos e o dispositivo é bloqueado após outros 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="069b2-165">For example, if you set the value for both settings to **5** minutes, the screen will turn off automatically after 5 minutes, and the device will be locked after an additional 5 minutes.</span></span> <span data-ttu-id="069b2-166">No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="069b2-166">However, if the user turns off the screen manually, the second setting is immediately applied.</span></span> <span data-ttu-id="069b2-167">No mesmo exemplo, o dispositivo é bloqueado 5 minutos depois de o usuário desligar a tela.</span><span class="sxs-lookup"><span data-stu-id="069b2-167">In the same example, after the user turns off the screen, the device will lock 5 minutes later.</span></span>

## <span data-ttu-id="069b2-168">Loja de Aplicativos, Exibição de Documentos, Jogos</span><span class="sxs-lookup"><span data-stu-id="069b2-168">App Store, Doc Viewing, Gaming</span></span>
<a id="app-store-doc-viewing-gaming" class="xliff"></a>


-   <span data-ttu-id="069b2-169">**Loja de aplicativos (somente supervisionado)** – Bloquear o acesso à loja de aplicativos em dispositivos supervisionados.</span><span class="sxs-lookup"><span data-stu-id="069b2-169">**App store (supervised only)** - Block access to the app store on supervised devices.</span></span>
-   <span data-ttu-id="069b2-170">**Senha para acessar a loja de aplicativos** – Exigir que o usuário insira uma senha antes de visitar a loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-170">**Password to access app store** - Require the user to enter a password before they can visit the app store.</span></span>
-   <span data-ttu-id="069b2-171">**Compras no aplicativo** – Permitir que compras da loja sejam feitas de um aplicativo em execução.</span><span class="sxs-lookup"><span data-stu-id="069b2-171">**In-app purchases** - Allow store purchases to be made from within a running app.</span></span>
-   <span data-ttu-id="069b2-172">**Downloads automáticos de aplicativo (somente supervisionados)** -</span><span class="sxs-lookup"><span data-stu-id="069b2-172">**Automatic app downloads (supervised only)** -</span></span>
-   <span data-ttu-id="069b2-173">**Conteúdo explícito de música, podcast ou notícias do iTunes (somente supervisionado)** – Permitir que o dispositivo acesse conteúdo classificado como adulto na loja.</span><span class="sxs-lookup"><span data-stu-id="069b2-173">**Explicit iTunes music, podcast, or news content (supervised only)** - Allow the device to access content rated as adult from the store.</span></span>
-   <span data-ttu-id="069b2-174">**Baixar o conteúdo do iBook Store marcado como “Erótico”** – Permitir que o usuário baixe livros da categoria “Erótico”.</span><span class="sxs-lookup"><span data-stu-id="069b2-174">**Download content from iBook store flagged as 'Erotica'** - Allow the user to download books with the "Erotica" category.</span></span>
-   <span data-ttu-id="069b2-175">**Exibir documentos corporativos em aplicativos não gerenciados** – Permitir que documentos corporativos sejam exibidos em qualquer aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-175">**Viewing corporate documents in unmanaged apps** - Allow corporate documents to be viewed in any app.</span></span><br><span data-ttu-id="069b2-176">**Exemplo:** você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox.</span><span class="sxs-lookup"><span data-stu-id="069b2-176">**Example:** You want to prevent users from saving files from the OneDrive app to Dropbox.</span></span> <span data-ttu-id="069b2-177">Defina essa configuração como não.</span><span class="sxs-lookup"><span data-stu-id="069b2-177">Configure this setting as no.</span></span> <span data-ttu-id="069b2-178">Depois que o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permitirá mais salvar.</span><span class="sxs-lookup"><span data-stu-id="069b2-178">After the device receives the policy (for example, after a restart), it will no longer allow saving.</span></span>
-   <span data-ttu-id="069b2-179">**Exibir documentos não corporativos em aplicativos corporativos** – Permitir que qualquer documento seja exibido nos aplicativos corporativos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="069b2-179">**Viewing non-corporate documents in corporate apps** - Allow any document to be viewed in corporate managed apps.</span></span>
-   <span data-ttu-id="069b2-180">**Tratar o AirDrop como um destino não gerenciado** – Impede que aplicativos gerenciados possam enviar dados por meio dele.</span><span class="sxs-lookup"><span data-stu-id="069b2-180">**Treat AirDrop as an unmanaged destination** - Stops managed apps from being able to send data via.</span></span> <span data-ttu-id="069b2-181">Airdrop.</span><span class="sxs-lookup"><span data-stu-id="069b2-181">Airdrop.</span></span>
-   <span data-ttu-id="069b2-182">**Adicionar amigos no Game Center (somente supervisionado)** – Permitir que o usuário adicione amigos no Game Center.</span><span class="sxs-lookup"><span data-stu-id="069b2-182">**Adding Game Center friends (supervised only)** - Allow the user to add friends in Game Center.</span></span>
-   <span data-ttu-id="069b2-183">**Game Center (somente supervisionado)** – Bloquear ou habilitar o uso do aplicativo Game Center.</span><span class="sxs-lookup"><span data-stu-id="069b2-183">**Game Center (supervised only)** - Block or enable the use of the Game Center app.</span></span>
-   <span data-ttu-id="069b2-184">**Jogos multijogador (somente supervisionado)** – Permitir que o usuário execute jogos com vários participantes no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-184">**Multiplayer gaming (supervised only)** - Allow the user to play multiplayer games on the device.</span></span>
-   <span data-ttu-id="069b2-185">**Região das classificações** – Escolha a região de classificações para o qual você deseja configurar os downloads permitidos, e escolha as classificações permitidas para **Filmes** e **Programas de TV**.</span><span class="sxs-lookup"><span data-stu-id="069b2-185">**Ratings region** - Choose the ratings region for which you want to configure allowed downloads, then choose the allowed ratings for **Movies** and **TV Shows**.</span></span>
-   <span data-ttu-id="069b2-186">**Aplicativos** – Escolha a classificação de idade dos aplicativos que os usuários poderão baixar, ou então escolha **Permitir todos os aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="069b2-186">**Apps** - Choose the allowed age rating of apps that users will be able to download, or you can choose **Allow All Apps**.</span></span>

## <span data-ttu-id="069b2-187">Aplicativos restritos</span><span class="sxs-lookup"><span data-stu-id="069b2-187">Restricted apps</span></span>
<a id="restricted-apps" class="xliff"></a>

<span data-ttu-id="069b2-188">Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:</span><span class="sxs-lookup"><span data-stu-id="069b2-188">In the restricted apps list, you can configure one of the following lists:</span></span>

<span data-ttu-id="069b2-189">Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.</span><span class="sxs-lookup"><span data-stu-id="069b2-189">A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span>
<span data-ttu-id="069b2-190">Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar.</span><span class="sxs-lookup"><span data-stu-id="069b2-190">An **Approved apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="069b2-191">Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados.</span><span class="sxs-lookup"><span data-stu-id="069b2-191">To remain compliant, users must not install apps that are not listed.</span></span> <span data-ttu-id="069b2-192">Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="069b2-192">Apps that are managed by Intune are automatically allowed.</span></span>

<span data-ttu-id="069b2-193">Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-193">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

### <span data-ttu-id="069b2-194">Como especificar a URL de um aplicativo na loja</span><span class="sxs-lookup"><span data-stu-id="069b2-194">How to specify the URL to an app in the store</span></span>
<a id="how-to-specify-the-url-to-an-app-in-the-store" class="xliff"></a>

<span data-ttu-id="069b2-195">Para especificar uma URL de aplicativo na lista de aplicativos, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="069b2-195">To specify an app URL in the apps list, use the following format:</span></span>

<span data-ttu-id="069b2-196">Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-196">Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.</span></span>
<span data-ttu-id="069b2-197">Copie a URL da página e use-a como a URL para configurar a lista de aplicativos permitidos ou proibidos ou o aplicativo que você deseja executar no modo de quiosque.</span><span class="sxs-lookup"><span data-stu-id="069b2-197">Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.</span></span>
<span data-ttu-id="069b2-198">Os perfis de dispositivo que contêm configurações de aplicativo restrito devem ser atribuídos para grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="069b2-198">Device profiles that contain restricted app settings must be assigned to groups of users.</span></span>

<span data-ttu-id="069b2-199">Exemplo: pesquisar por Microsoft Word para iPad.</span><span class="sxs-lookup"><span data-stu-id="069b2-199">Example: Search for Microsoft Word for iPad.</span></span> <span data-ttu-id="069b2-200">A URL que você usará será https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.</span><span class="sxs-lookup"><span data-stu-id="069b2-200">The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.</span></span>
=======
## Geral
<a id="general" class="xliff"></a>
-   **Câmera** – Especifica se a câmera no dispositivo pode ser usada.   
-   **Envio de dados de diagnóstico** – Permitir ou bloquear a habilidade do dispositivo enviar dados de diagnóstico para a Apple.
-   **FaceTime** – Permitir que o aplicativo FaceTime seja usado no dispositivo.
-   **Captura de tela** – Permitir ao usuário capturar os conteúdos da tela como uma imagem.
-   **Siri** – Permitir o uso da assistente de voz Siri no dispositivo.
    -   **Siri quando o dispositivo estiver bloqueado** – Permitir o uso da Assistente de voz Siri no dispositivo enquanto ele estiver bloqueado.
    -   **Filtro de profanação da Siri (somente supervisionado)** – Impede que a Siri dite ou use linguagem ofensiva.
    -   **Siri deve consultar o conteúdo gerado pelo usuário da Internet (somente supervisionado)** – Permitir que Siri acesse sites da Web para responder a perguntas.
-   **Certificados TLS não confiáveis** – Permitir certificados do protocolo TLS não confiáveis no dispositivo.
-   **Controlar acesso à central quando o dispositivo está bloqueado** – Permitir ao usuário acessar o aplicativo de Central de Controle quando o dispositivo estiver bloqueado.
-   **Notificações enquanto o dispositivo está bloqueado** – Permitir ao usuário acessar a exibição de notificações sem desbloquear o dispositivo.
-   **Passbook enquanto o dispositivo está bloqueado** – Permitir ao usuário acessar o aplicativo Passbook enquanto o dispositivo estiver bloqueado.
-   **Exibição Hoje enquanto o dispositivo está bloqueado** – Permitir que o usuário veja o a exibição Hoje quando o dispositivo estiver bloqueado.
-   **Aplicativos de confiança da empresa** – Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
-   **AirDrop (somente supervisionado)** – Permitir o uso do recurso AirDrop para trocar conteúdo com dispositivos próximos.
-   **Pesquisa de destaque retorna resultados da internet (somente supervisionado)** – Permitir que a pesquisa de Destaque se conecte à Internet para fornecer mais resultados.
-   **Pesquisa por definição de palavra (somente supervisionado)** – Permitir o recurso do iOS que permite realçar uma palavra e pesquisar sua definição.
-   **Teclados preditivos (somente supervisionado)** – Permitir o uso de teclados preditivos que sugerem palavras que o usuário pode querer.
-   **Correção automática (somente supervisionado)** – Permite que o dispositivo corrija automaticamente palavras incorretas.
-   **Verificação ortográfica do teclado (somente supervisionada)**  – Permite usar o verificador de ortografia do dispositivo.
-   **Atalhos de teclado (somente supervisionado)** – Permite o uso de atalhos de teclado.
-   **Detecção de pulso para Apple Watch emparelhado** – Quando habilitada, o Apple Watch não exibirá notificações quando não estiver sendo usado.
- **Exigir uma senha de emparelhamento de solicitações de saída do AirPlay** – Exigir uma senha emparelhamento quando o usuário usar AirPlay para transmitir o conteúdo para outros dispositivos da Apple.
- **Modificação de conta (somente com supervisão)** - Quando é bloqueada, impede que o usuário modifique as configurações específicas do dispositivo no aplicativo de configurações do iOS, como a criação de novas contas de dispositivo e alteração do nome de usuário ou senha.
Isso também se aplica às configurações acessadas no aplicativo de configurações do iOS, como Mail, Contatos, Calendário, Facebook e Twitter. Isso não se aplica a aplicativos com configurações de conta que não podem ser definidas no aplicativo de configurações do iOS, por exemplo, o aplicativo Microsoft Outlook.
- **Emparelhamento de Apple Watch (somente supervisionado)** – Permite que o dispositivo seja emparelhado com um Apple Watch.
- **Modificação de Bluetooth (somente supervisionado)** – Impede o usuário final de alterar as configurações de Bluetooth no dispositivo.
- **Observação de tela remota pelo aplicativo Classroom (somente supervisionado)** – Permitir ou bloquear que o aplicativo Classroom observe a tela em dispositivos remotos.
- **Habilitar restrições nas configurações do dispositivo (somente supervisionado)** – Permitir que o usuário configure restrições de dispositivo (controles dos pais) no dispositivo.
- **Usar o apagamento total do conteúdo e das opções de configurações no dispositivo (somente supervisionado)** – Permitir que o usuário utilize a opção de apagar todo o conteúdo e as configurações no dispositivo.
- **Modificação do nome de dispositivo (somente supervisionado)** – Permitir que o usuário altere o nome do dispositivo.
- **Modificação de configurações de envio de diagnóstico (somente supervisionado)** – Permitir ou bloquear que o dispositivo envie dados de diagnóstico para a Apple.
- **Emparelhamento de host para controlar os dispositivos aos quais um dispositivo iOS pode ser emparelhado (somente supervisionado)** – Permitir emparelhamento de host para que o administrador controle com quais dispositivos um dispositivo iOS pode ser emparelhado.
- **Modificação das configurações de notificação (somente supervisionado)** – Permitir que o usuário altere as configurações de notificação do dispositivo.
- **Modificação da senha (somente supervisionado)** – Permitir que a senha do dispositivo seja adicionada, alterada ou removida.
- **Modificação do papel de parede (somente supervisionado)** – Permitir que o usuário altere o papel de parede do dispositivo.
- **Modificação das configurações de aplicativo de confiança da empresa** – Permitir que o usuário opte por confiar em aplicativos que não foram baixados da loja de aplicativos.
- **Instalar aplicativos da App Store (apenas no modo supervisionado)** – Permitir que o dispositivo acesse a loja de aplicativos e instale aplicativos.
- **Alterações nas configurações de aplicativo de Find My Friends (somente supervisionados)** – Permitir que o usuário altere as configurações para o aplicativo Find My Friends.
- **iBooks Store (somente supervisionado)** – Permitir que o usuário procure e compre livros da iBooks Store.
- **Aplicativo de mensagens no dispositivo (somente supervisionado)** – Permite usar o aplicativo de Mensagens para enviar e ler mensagens de texto.
- **Podcasts (somente supervisionado)** – Permitir o uso do aplicativo Podcasts.
- **Serviço de Música (somente supervisionado)** – Permitir o uso do aplicativo Apple Music.
- **Serviço do iTunes Radio (somente supervisionado)** – Permitir o uso do aplicativo iTunes Radio.
- **Apple News (somente supervisionado)** – Permitir o uso do aplicativo Apple News.
- **Alterações de perfil de configuração** – Permitir que o usuário instale perfis de configuração.

## Senha
<a id="password" class="xliff"></a>
-   **Senha obrigatória** – Exigir que o usuário final insira uma senha para acessar o dispositivo.
-   **Senhas simples** – Permitir senhas simples como 0000 e 1234.
-   **Tipo de senha exigida** – Especificar o tipo de senha necessária, como apenas numérica ou alfanumérica.
-   **Número de caracteres não alfanuméricos na senha** – Especifique o número de caracteres de símbolo (como **#** ou **@**) que devem ser incluídos na senha.
-   **Tamanho mínimo de senha** – Especificar o número mínimo de caracteres na senha.
-   **Número de falhas de entrada antes de apagar o dispositivo** – Especificar o número de tentativas de logon antes de essa configuração apagar o dispositivo.
-   **Máximo de minutos após o bloqueio de tela antes da senha ser necessária**<sup>1</sup> – Especifique quanto tempo o dispositivo pode permanecer ocioso antes que o usuário precise digitar novamente sua senha.
-   **Máximo de minutos de inatividade até o bloqueio de tela**<sup>1</sup> – Especifique o número de minutos antes que a tela do dispositivo seja desativada.
-   **Expiração da senha (dias)** – Especifique o número de dias antes que a senha do dispositivo precise ser alterada.
-   **Impedir a reutilização de senhas anteriores** – Especifique o número de senhas usadas anteriormente que o dispositivo lembra.
-   **Desbloqueio por impressão digital** – Permite usar uma impressão digital para desbloquear dispositivos compatíveis.

<sup>1</sup>Quando você configura as definições **Máximo de minutos inatividade até o bloqueio de tela** e **Máximo de minutos após o bloqueio de tela antes da senha ser necessária**, eles são aplicados em sequência. Por exemplo, se você define o valor de ambas as configurações para **5** minutos, a tela desliga automaticamente após 5 minutos e o dispositivo é bloqueado após outros 5 minutos. No entanto, se o usuário desliga a tela manualmente, a segunda configuração é aplicada imediatamente. No mesmo exemplo, o dispositivo é bloqueado 5 minutos depois de o usuário desligar a tela.

## Loja de Aplicativos, Exibição de Documentos, Jogos
<a id="app-store-doc-viewing-gaming" class="xliff"></a>


-   **Loja de aplicativos (somente supervisionado)** – Bloquear o acesso à loja de aplicativos em dispositivos supervisionados.
-   **Senha para acessar a loja de aplicativos** – Exigir que o usuário insira uma senha antes de visitar a loja de aplicativos.
-   **Compras no aplicativo** – Permitir que compras da loja sejam feitas de um aplicativo em execução.
-   **Downloads automáticos de aplicativo (somente supervisionados)** -
-   **Conteúdo explícito de música, podcast ou notícias do iTunes (somente supervisionado)** – Permitir que o dispositivo acesse conteúdo classificado como adulto na loja.
-   **Baixar o conteúdo do iBook Store marcado como “Erótico”** – Permitir que o usuário baixe livros da categoria “Erótico”.
-   **Exibir documentos corporativos em aplicativos não gerenciados** – Permitir que documentos corporativos sejam exibidos em qualquer aplicativo.<br>**Exemplo:** você deseja impedir que os usuários salvem arquivos do aplicativo OneDrive no Dropbox. Defina essa configuração como não. Depois que o dispositivo receber a política (por exemplo, após uma reinicialização), ele não permitirá mais salvar.
-   **Exibir documentos não corporativos em aplicativos corporativos** – Permitir que qualquer documento seja exibido nos aplicativos corporativos gerenciados.
-   **Tratar o AirDrop como um destino não gerenciado** – Impede que aplicativos gerenciados possam enviar dados por meio dele. Airdrop.
-   **Adicionar amigos no Game Center (somente supervisionado)** – Permitir que o usuário adicione amigos no Game Center.
-   **Game Center (somente supervisionado)** – Bloquear ou habilitar o uso do aplicativo Game Center.
-   **Jogos multijogador (somente supervisionado)** – Permitir que o usuário execute jogos com vários participantes no dispositivo.
-   **Região das classificações** – Escolha a região de classificações para o qual você deseja configurar os downloads permitidos, e escolha as classificações permitidas para **Filmes** e **Programas de TV**.
-   **Aplicativos** – Escolha a classificação de idade dos aplicativos que os usuários poderão baixar, ou então escolha **Permitir todos os aplicativos**.

## Aplicativos restritos
<a id="restricted-apps" class="xliff"></a>

Na lista de aplicativos restritos, você pode configurar uma das seguintes listas:

Uma lista de **Aplicativos proibidos** – Listar os aplicativos (não gerenciados pelo Intune) que os usuários não têm permissão para instalar e executar.
Uma lista de **Aplicativos aprovados** – Listar os aplicativos que os usuários têm permissão para instalar. Para permanecer compatível, os usuários não devem instalar aplicativos que não estão listados. Aplicativos que são gerenciados pelo Intune são permitidos automaticamente.

Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.

### Como especificar a URL de um aplicativo na loja
<a id="how-to-specify-the-url-to-an-app-in-the-store" class="xliff"></a>

Para especificar uma URL de aplicativo na lista de aplicativos, use o seguinte formato:

Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.
Copie a URL da página e use-a como a URL para configurar a lista de aplicativos permitidos ou proibidos ou o aplicativo que você deseja executar no modo de quiosque.
Os perfis de dispositivo que contêm configurações de aplicativo restrito devem ser atribuídos para grupos de usuários.

Exemplo: pesquisar por Microsoft Word para iPad. A URL que você usará será https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.
>>>>>>> live

> [!Note]
> <span data-ttu-id="069b2-201">Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-201">You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.</span></span>



<<<<<<< HEAD
### <span data-ttu-id="069b2-202">Opções adicionais</span><span class="sxs-lookup"><span data-stu-id="069b2-202">Additional options</span></span>
=======
### Opções adicionais
>>>>>>> live
<a id="additional-options" class="xliff"></a>

<span data-ttu-id="069b2-203">Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos restritos no mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="069b2-203">You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="069b2-204">Mostrar ou ocultar aplicativos</span><span class="sxs-lookup"><span data-stu-id="069b2-204">Show or hide apps</span></span>
=======
## Mostrar ou ocultar aplicativos
>>>>>>> live
<a id="show-or-hide-apps" class="xliff"></a>

<span data-ttu-id="069b2-205">Na lista de aplicativos Mostrar ou ocultar, você pode configurar uma destas listas (requer dispositivos supervisionados com iOS 9.3 ou posterior).</span><span class="sxs-lookup"><span data-stu-id="069b2-205">In the show or hide apps list, you can configure one of the following lists (requires supervised devices running iOS 9.3 or later).</span></span>

<span data-ttu-id="069b2-206">Uma lista de **Aplicativos ocultos** – Especifique uma lista de aplicativos que serão ocultados dos usuários.</span><span class="sxs-lookup"><span data-stu-id="069b2-206">A **Hidden apps** list - Specify a list of apps that will be hidden from users.</span></span> <span data-ttu-id="069b2-207">Os usuários não podem exibir nem iniciar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-207">Users cannot view, or launch these apps.</span></span>
<span data-ttu-id="069b2-208">Uma lista de **Aplicativos visíveis** – Especifique uma lista de aplicativos que os usuários podem exibir e iniciar.</span><span class="sxs-lookup"><span data-stu-id="069b2-208">An **Visible apps** list - Specify a list of apps that users can view and launch.</span></span> <span data-ttu-id="069b2-209">Nenhum outro aplicativo pode ser exibido ou iniciado.</span><span class="sxs-lookup"><span data-stu-id="069b2-209">No other apps can be viewed or launched.</span></span>

<span data-ttu-id="069b2-210">Para configurar a lista, clique em **Adicionar**, especifique um nome de sua preferência, o editor do aplicativo (opcional) e a URL para o aplicativo na loja de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="069b2-210">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

<<<<<<< HEAD
### <span data-ttu-id="069b2-211">Como especificar a URL de um aplicativo na loja</span><span class="sxs-lookup"><span data-stu-id="069b2-211">How to specify the URL to an app in the store</span></span>
=======
### Como especificar a URL de um aplicativo na loja
>>>>>>> live
<a id="how-to-specify-the-url-to-an-app-in-the-store" class="xliff"></a>

<span data-ttu-id="069b2-212">Para especificar uma URL de aplicativo na lista de aplicativos, use o seguinte formato:</span><span class="sxs-lookup"><span data-stu-id="069b2-212">To specify an app URL in the apps list, use the following format:</span></span>

<span data-ttu-id="069b2-213">Usando um mecanismo de pesquisa, encontre o aplicativo que você deseja usar na iTunes App Store e abra a página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-213">Using a search engine, find the app that you want to use in the iTunes App Store and open the page for the app.</span></span>
<span data-ttu-id="069b2-214">Copie a URL da página e use-a como a URL para configurar a lista de aplicativos permitidos ou proibidos ou o aplicativo que você deseja executar no modo de quiosque.</span><span class="sxs-lookup"><span data-stu-id="069b2-214">Copy the URL of the page and use this as the URL to configure the allowed or prohibited apps list or an app that you want to run in kiosk mode.</span></span>

<span data-ttu-id="069b2-215">Exemplo: pesquisar por Microsoft Word para iPad.</span><span class="sxs-lookup"><span data-stu-id="069b2-215">Example: Search for Microsoft Word for iPad.</span></span> <span data-ttu-id="069b2-216">A URL que você usará será https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.</span><span class="sxs-lookup"><span data-stu-id="069b2-216">The URL that you use will be https://itunes.apple.com/us/app/microsoft-word-for-ipad/id586447913?mt=8.</span></span>

> [!Note]
<<<<<<< HEAD
> <span data-ttu-id="069b2-217">Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-217">You can also use the iTunes software to find the app and then use the **Copy Link** command to get the app URL.</span></span>

### <span data-ttu-id="069b2-218">Opções adicionais</span><span class="sxs-lookup"><span data-stu-id="069b2-218">Additional options</span></span>
<a id="additional-options" class="xliff"></a>

<span data-ttu-id="069b2-219">Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos ocultos e visíveis no mesmo formato.</span><span class="sxs-lookup"><span data-stu-id="069b2-219">You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the hidden or visible apps list in the same format.</span></span>


## <span data-ttu-id="069b2-220">Celular</span><span class="sxs-lookup"><span data-stu-id="069b2-220">Cellular</span></span>
<a id="cellular" class="xliff"></a>
-   <span data-ttu-id="069b2-221">**Roaming de dados** – Permitir roaming de dados quando o dispositivo estiver em uma rede de celular.</span><span class="sxs-lookup"><span data-stu-id="069b2-221">**Data roaming** - Allow data roaming when the device is on a cellular network.</span></span>
-   <span data-ttu-id="069b2-222">**Obtenção de tela de fundo global durante o roaming** – Permite ao dispositivo buscar dados, como emails, durante roaming na rede celular.</span><span class="sxs-lookup"><span data-stu-id="069b2-222">**Global background fetch while roaming** - Allow the device to fetch data such as email while it is roaming on a cellular network.</span></span>
-   <span data-ttu-id="069b2-223">**Discagem por voz** – Permitir o uso do recurso de discagem por voz no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-223">**Voice dialing** - Allow use of the voice dialing feature on the device.</span></span>
-   <span data-ttu-id="069b2-224">**Roaming de voz** – Permitir roaming de voz quando o dispositivo estiver em uma rede de celular.</span><span class="sxs-lookup"><span data-stu-id="069b2-224">**Voice roaming** - Allow voice roaming when the device is on a cellular network.</span></span>
-   <span data-ttu-id="069b2-225">**Alterações nas configurações de uso de dados de celular da rede celular do aplicativo (somente supervisionado)** – Permite ao usuário controlar quais aplicativos podem usar dados da rede celular.</span><span class="sxs-lookup"><span data-stu-id="069b2-225">**Changes to app cellular data usage settings (supervised only)** - Allow the user to control which apps are allowed to use cellular data.</span></span>

## <span data-ttu-id="069b2-226">Nuvem e Armazenamento</span><span class="sxs-lookup"><span data-stu-id="069b2-226">Cloud and Storage</span></span>
<a id="cloud-and-storage" class="xliff"></a>
-   <span data-ttu-id="069b2-227">**Backup para iCloud** – Permitir ao usuário fazer backup do dispositivo no iCloud.</span><span class="sxs-lookup"><span data-stu-id="069b2-227">**Backup to iCloud** - Allow the user to back up the device to iCloud.</span></span>
-   <span data-ttu-id="069b2-228">**Sincronização de documentos para iCloud (somente supervisado)** – Permitir a sincronização de documento e chave-valor para o espaço de armazenamento no iCloud.</span><span class="sxs-lookup"><span data-stu-id="069b2-228">**Document sync to iCloud (supervised only)** - Allow document and key-value synchronization to your iCloud storage space.</span></span>
-   <span data-ttu-id="069b2-229">**Sincronização de fluxo de fotografias para iCloud** – Permite que os usuários habilitem o **Meu Fluxo de Fotos** em seus dispositivos, o que permite que as fotos sejam sincronizadas com o iCloud e fiquem disponíveis em todos os dispositivos dos usuários.</span><span class="sxs-lookup"><span data-stu-id="069b2-229">**Photo stream syncing to iCloud** - Lets users enable **My Photo Stream** on their device which allow photos to sync to iCloud and be available on all the users devices.</span></span>
-   <span data-ttu-id="069b2-230">**Backup criptografado** – Exigir que quaisquer backups de dispositivo sejam criptografados.</span><span class="sxs-lookup"><span data-stu-id="069b2-230">**Encrypted backup** - Require any device backups to be encrypted.</span></span>
-   <span data-ttu-id="069b2-231">**Biblioteca de Fotos do iCloud** – Se for definido como **Não**, desabilitará o uso da biblioteca de fotos do iCloud, o que permite aos usuários armazenar fotos e vídeos na nuvem.</span><span class="sxs-lookup"><span data-stu-id="069b2-231">**iCloud Photo Library** - If set to **No**, disables the use of iCloud photo library which lets users store photos and videos in the cloud.</span></span>    <span data-ttu-id="069b2-232">As fotos que não forem totalmente baixadas na biblioteca de fotos do iCloud para o dispositivo serão removidas do dispositivo se essa opção for definida como **Não**.</span><span class="sxs-lookup"><span data-stu-id="069b2-232">Any photos not fully downloaded from iCloud Photo Library to the device will be removed from the device if this is set to **No**.</span></span>
-   <span data-ttu-id="069b2-233">**Sincronizar aplicativos gerenciados com a nuvem** – Permitir que os aplicativos que você gerencia com o Intune sincronizem dados com a conta do iCloud do usuário.</span><span class="sxs-lookup"><span data-stu-id="069b2-233">**Managed apps sync to cloud** - Allow apps that you manage with Intune to sync data to the user's iCloud account.</span></span>
-   <span data-ttu-id="069b2-234">**Fluxo de fotos compartilhado** – Defina como **Não** para desabilitar o **Compartilhamento de Fotos do iCloud** no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-234">**Shared photo stream** - Set to **No** to disable **iCloud Photo Sharing** on the device..</span></span>
-   <span data-ttu-id="069b2-235">**Continuação da atividade** – Permitir que o usuário continue, em outro dispositivo iOS ou macOS, o trabalho iniciado em um dispositivo iOS (Handoff).</span><span class="sxs-lookup"><span data-stu-id="069b2-235">**Activity continuation** - Allow the user to continue work that they started on an iOS device on another iOS or macOS device (Handoff).</span></span>

## <span data-ttu-id="069b2-236">Modo autônomo de único aplicativo (somente supervisionado)</span><span class="sxs-lookup"><span data-stu-id="069b2-236">Autonomous single app mode (supervised only)</span></span>
<a id="autonomous-single-app-mode-supervised-only" class="xliff"></a>

<span data-ttu-id="069b2-237">Use estas configurações para configurar dispositivos iOS para executar aplicativos especificados no modo autônomo de aplicativo único.</span><span class="sxs-lookup"><span data-stu-id="069b2-237">Use these settings to configure iOS devices to run specified apps in autonomous single app mode.</span></span> <span data-ttu-id="069b2-238">Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-238">When this mode is configured, and the app is run, the device is locked so that it can only run that app.</span></span> <span data-ttu-id="069b2-239">Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-239">An example of this is when you configure an app that lets users take a test on the device.</span></span> <span data-ttu-id="069b2-240">Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.</span><span class="sxs-lookup"><span data-stu-id="069b2-240">When the apps actions are complete, or you remove this policy, the device returns to its normal state.</span></span>

### <span data-ttu-id="069b2-241">Configurações</span><span class="sxs-lookup"><span data-stu-id="069b2-241">Settings</span></span>
<a id="settings" class="xliff"></a>

- <span data-ttu-id="069b2-242">**Nome do aplicativo** - insira o nome do aplicativo como ele aparecerá na lista de aplicativos desta folha.</span><span class="sxs-lookup"><span data-stu-id="069b2-242">**App name** - Enter the name of the app as it will appear in the apps list on this blade.</span></span>
- <span data-ttu-id="069b2-243">**ID do Pacote de Aplicativos** - insira a ID do pacote de aplicativos do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="069b2-243">**App Bundle ID** - Enter the bundle ID of the app.</span></span> <span data-ttu-id="069b2-244">Para obter ajuda, veja **Referência da ID de Pacote para aplicativos iOS internos** neste tópico.</span><span class="sxs-lookup"><span data-stu-id="069b2-244">For help, see **Bundle ID reference for built-in iOS apps** in this topic.</span></span>

<span data-ttu-id="069b2-245">Depois de especificar o nome de cada aplicativo e a ID de pacote, escolha **Adicionar** para acrescentá-los à lista.</span><span class="sxs-lookup"><span data-stu-id="069b2-245">After you specify each app name and bundle ID, choose **Add** to append it to the list.</span></span>

- <span data-ttu-id="069b2-246">**Importar** - importe um arquivo .csv (valores separados por vírgulas) contendo uma lista de nomes de aplicativo e suas IDs de pacote associadas.</span><span class="sxs-lookup"><span data-stu-id="069b2-246">**Import** - Import a comma-separated values (.csv) file containing a list of app names, and their associated bundle IDs.</span></span>
- <span data-ttu-id="069b2-247">**Exportar** - exporte os nomes de aplicativo e as IDs de pacote associadas configuradas para um arquivo .csv (valores separados por vírgulas).</span><span class="sxs-lookup"><span data-stu-id="069b2-247">**Export** - Export the app names, and associated bundle IDs you have configured to a comma-separated values (.csv) file.</span></span>

### <span data-ttu-id="069b2-248">Referência de ID de Pacote para aplicativos iOS internos</span><span class="sxs-lookup"><span data-stu-id="069b2-248">Bundle ID reference for built-in iOS apps</span></span>
<a id="bundle-id-reference-for-built-in-ios-apps" class="xliff"></a>

<span data-ttu-id="069b2-249">Esta lista mostra a ID de pacote de alguns aplicativos iOS internos comuns.</span><span class="sxs-lookup"><span data-stu-id="069b2-249">This list shows the bundle ID of some common built-in iOS apps.</span></span> <span data-ttu-id="069b2-250">Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software.</span><span class="sxs-lookup"><span data-stu-id="069b2-250">To find the bundle ID of other apps, contact your software vendor.</span></span>
=======
> Você também pode usar o software iTunes para encontrar o aplicativo e usar o comando **Copiar Link** para obter a URL do aplicativo.

### Opções adicionais
<a id="additional-options" class="xliff"></a>

Você também pode clicar em **Importar** para popular a lista de um arquivo csv no formato <*url do aplicativo*>, <*nome do aplicativo*>, <*editor do aplicativo*>, ou clique em **Exportar** para criar um arquivo csv que inclui o conteúdo da lista de aplicativos ocultos e visíveis no mesmo formato.


## Celular
<a id="cellular" class="xliff"></a>
-   **Roaming de dados** – Permitir roaming de dados quando o dispositivo estiver em uma rede de celular.
-   **Obtenção de tela de fundo global durante o roaming** – Permite ao dispositivo buscar dados, como emails, durante roaming na rede celular.
-   **Discagem por voz** – Permitir o uso do recurso de discagem por voz no dispositivo.
-   **Roaming de voz** – Permitir roaming de voz quando o dispositivo estiver em uma rede de celular.
-   **Alterações nas configurações de uso de dados de celular da rede celular do aplicativo (somente supervisionado)** – Permite ao usuário controlar quais aplicativos podem usar dados da rede celular.

## Nuvem e Armazenamento
<a id="cloud-and-storage" class="xliff"></a>
-   **Backup para iCloud** – Permitir ao usuário fazer backup do dispositivo no iCloud.
-   **Sincronização de documentos para iCloud (somente supervisado)** – Permitir a sincronização de documento e chave-valor para o espaço de armazenamento no iCloud.
-   **Sincronização de fluxo de fotografias para iCloud** – Permite que os usuários habilitem o **Meu Fluxo de Fotos** em seus dispositivos, o que permite que as fotos sejam sincronizadas com o iCloud e fiquem disponíveis em todos os dispositivos dos usuários.
-   **Backup criptografado** – Exigir que quaisquer backups de dispositivo sejam criptografados.
-   **Biblioteca de Fotos do iCloud** – Se for definido como **Não**, desabilitará o uso da biblioteca de fotos do iCloud, o que permite aos usuários armazenar fotos e vídeos na nuvem.    As fotos que não forem totalmente baixadas na biblioteca de fotos do iCloud para o dispositivo serão removidas do dispositivo se essa opção for definida como **Não**.
-   **Sincronizar aplicativos gerenciados com a nuvem** – Permitir que os aplicativos que você gerencia com o Intune sincronizem dados com a conta do iCloud do usuário.
-   **Fluxo de fotos compartilhado** – Defina como **Não** para desabilitar o **Compartilhamento de Fotos do iCloud** no dispositivo.
-   **Continuação da atividade** – Permitir que o usuário continue, em outro dispositivo iOS ou macOS, o trabalho iniciado em um dispositivo iOS (Handoff).

## Modo autônomo de único aplicativo (somente supervisionado)
<a id="autonomous-single-app-mode-supervised-only" class="xliff"></a>

Use estas configurações para configurar dispositivos iOS para executar aplicativos especificados no modo autônomo de aplicativo único. Quando esse modo está configurado e o aplicativo é executado, o dispositivo é bloqueado para que ele só possa executar esse aplicativo. Um exemplo disso é quando você configura um aplicativo que permite aos usuários fazer um teste no dispositivo. Quando as ações do aplicativo forem concluídas ou quando você remover essa política, o dispositivo retornará ao seu estado normal.

### Configurações
<a id="settings" class="xliff"></a>

- **Nome do aplicativo** - insira o nome do aplicativo como ele aparecerá na lista de aplicativos desta folha.
- **ID do Pacote de Aplicativos** - insira a ID do pacote de aplicativos do aplicativo. Para obter ajuda, veja **Referência da ID de Pacote para aplicativos iOS internos** neste tópico.

Depois de especificar o nome de cada aplicativo e a ID de pacote, escolha **Adicionar** para acrescentá-los à lista.

- **Importar** - importe um arquivo .csv (valores separados por vírgulas) contendo uma lista de nomes de aplicativo e suas IDs de pacote associadas.
- **Exportar** - exporte os nomes de aplicativo e as IDs de pacote associadas configuradas para um arquivo .csv (valores separados por vírgulas).

### Referência de ID de Pacote para aplicativos iOS internos
<a id="bundle-id-reference-for-built-in-ios-apps" class="xliff"></a>

Esta lista mostra a ID de pacote de alguns aplicativos iOS internos comuns. Para localizar a ID do pacote de outros aplicativos, entre em contato com seu fornecedor de software.
>>>>>>> live

```
,com.apple.AppStore,App Store,Apple
,com.apple.calculator,Calculator,Apple
,com.apple.mobilecal,Calendar,Apple
,com.apple.camera,Camera,Apple
,com.apple.mobiletimer,Clock,Apple
,com.apple.compass,Compass,Apple
,com.apple.MobileAddressBook,Contacts,Apple
,com.apple.facetime,FaceTime,Apple
,com.apple.mobileme.fmf1,Find Friends,Apple
,com.apple.mobileme.fmip1,Find iPhone,Apple
,com.apple.gamecenter,Game Center,Apple
,com.apple.mobilegarageband,GarageBand,Apple
,com.apple.Health,Health,Apple
,com.apple.iBooks,iBooks,Apple
,com.apple.MobileStore,iTunes Store,Apple
,com.apple.itunesu,iTunes U,Apple
,com.apple.Keynote,Keynote,Apple
,com.apple.mobilemail,Mail,Apple
,com.apple.MapsMaps,Apple
,com.apple.MobileSMS,Messages,Apple
,com.apple.Music,Music,Apple
,com.apple.news,News,Apple
,com.apple.mobilenotes,Notes,Apple
,com.apple.Numbers,Numbers,Apple
,com.apple.Pages,Pages,Apple
,com.apple.Photo-Booth,Photo Booth,Apple
,com.apple.mobileslideshow,Photos,Apple
,com.apple.podcasts,Podcasts,Apple
,com.apple.reminders,Reminders,Apple
,com.apple.mobilesafariSafari,Apple
,com.apple.Preferences,Settings,Apple
,com.apple.stocks,Stocks,Apple
,com.apple.tips,Tips,Apple
,com.apple.videos,Videos,Apple
,com.apple.VoiceMemos,VoiceMemos,Apple
,com.apple.Passbook,Wallet,Apple
,com.apple.Bridge,Watch,Apple
,com.apple.weather,Weather,Apple


```


<<<<<<< HEAD
## <span data-ttu-id="069b2-251">Quiosque</span><span class="sxs-lookup"><span data-stu-id="069b2-251">Kiosk</span></span>
<a id="kiosk" class="xliff"></a>
-   <span data-ttu-id="069b2-252">**Bloqueio de Ativação** – Habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados.</span><span class="sxs-lookup"><span data-stu-id="069b2-252">**Activation Lock** - Enable Activation Lock on supervised iOS devices.</span></span>
-   <span data-ttu-id="069b2-253">**Aplicativo que é executado no modo de quiosque** – Escolha **Aplicativo Gerenciado** para selecionar um aplicativo que você adicionou ao Intune, ou **Aplicativo da Loja** para especificar a URL para um aplicativo na loja.</span><span class="sxs-lookup"><span data-stu-id="069b2-253">**App that runs in kiosk mode** - Choose **Managed App** to select an app you've added to Intune, or **Store App** to specify the URL to an app in the store.</span></span> <span data-ttu-id="069b2-254">Nenhum outro aplicativo poderá ser executado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-254">No other apps will be allowed to run on the device.</span></span> <span data-ttu-id="069b2-255">Para obter mais ajuda, consulte "How to specify URLs to app stores" (Como especificar URLs para lojas de aplicativos) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="069b2-255">For more help, see "How to specify URLs to app stores" later in this topic.</span></span>
-   <span data-ttu-id="069b2-256">**Toque auxiliar** – Habilitar ou desabilitar a configuração de acessibilidade **Toque auxiliar**, que ajuda o usuário a executar gestos na tela que podem ser difíceis de executar.</span><span class="sxs-lookup"><span data-stu-id="069b2-256">**Assistive touch** - Enable or disable the **Assistive Touch** accessibility setting, which helps the user perform on-screen gestures that might be difficult for them to perform.</span></span>
-   <span data-ttu-id="069b2-257">**Inverter cores** – Habilitar ou desabilitar a configuração de acessibilidade Inverter Cores que ajusta a exibição para ajudar os usuários com deficiências visuais.</span><span class="sxs-lookup"><span data-stu-id="069b2-257">**Invert colors** - Enable or disable the Invert Colors accessibility setting, which adjusts the display to help users with visual impairments.</span></span>
-   <span data-ttu-id="069b2-258">**Áudio mono** – Habilitar ou desabilitar a configuração de acessibilidade Áudio mono.</span><span class="sxs-lookup"><span data-stu-id="069b2-258">**Mono audio** - Enable or disable the accessibility setting Mono audio.</span></span>
-   <span data-ttu-id="069b2-259">**VoiceOver** – Habilitar ou desabilitar a configuração de acessibilidade **VoiceOver**, que lê em voz alta o texto na tela do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-259">**VoiceOver** - Enable or disable the accessibility setting **VoiceOver**, which reads aloud text on the device display.</span></span>
-   <span data-ttu-id="069b2-260">**Zoom** – Habilitar ou desabilitar a configuração de acessibilidade de **Zoom** que permite ao usuário usar o toque para ampliar a tela do dispositivo de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="069b2-260">**Zoom** - Enable or disable the **Zoom** accessibility setting, which lets the user use touch to zoom in to the device display.</span></span>
-   <span data-ttu-id="069b2-261">**Bloqueio automático**- Habilitar ou desabilitar o bloqueio automático do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-261">**Auto lock** - Enable or disable automatic locking of the device.</span></span>
-   <span data-ttu-id="069b2-262">**Botão de toque** – Habilitar ou desabilitar a opção de botão de toque (mudo) no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-262">**Ringer switch** - Enable or disable the ringer (mute) switch on the device.</span></span>
-   <span data-ttu-id="069b2-263">**Rotação da tela** – Habilitar ou desabilitar a alteração da orientação da tela quando o usuário gira o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-263">**Screen rotation** - Enable or disable changing the screen orientation when the user rotates the device.</span></span>
-   <span data-ttu-id="069b2-264">**Botão de suspensão da tela** – Habilitar ou desabilitar o botão de suspensão e ativação da tela no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-264">**Screen sleep button** - Enable or disable the screen sleep wake button on the device.</span></span>
-   <span data-ttu-id="069b2-265">**Toque** – Habilitar ou desabilitar a tela touch no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-265">**Touch** - Enable or disable the touchscreen on the device.</span></span>
-   <span data-ttu-id="069b2-266">**Botões de volume** – Habilitar ou desabilitar o uso dos botões de volume no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-266">**Volume buttons** - Enable or disable the use of the volume buttons on the device.</span></span>
-   <span data-ttu-id="069b2-267">**Controle de toque auxiliar** – Habilitar ou desabilitar os ajustes de toque auxiliar que permitem ao usuário ajustar a função de toque auxiliar.</span><span class="sxs-lookup"><span data-stu-id="069b2-267">**Assistive touch control** - Enable or disable assistive touch adjustments, which let the user adjust the assistive touch function.</span></span>
-   <span data-ttu-id="069b2-268">**Controle de inversão e cores** – Habilitar ou desabilitar ajustes de inverter ajustes que permite ao usuário ajustar a função inverter cores.</span><span class="sxs-lookup"><span data-stu-id="069b2-268">**Invert colors control** - Enable or disable invert colors adjustments, which let the user adjust the invert colors function.</span></span>
-   <span data-ttu-id="069b2-269">**Falar texto selecionado** – Habilitar ou desabilitar as configurações de acessibilidade Seleção de fala que podem ler em voz alta o texto que o usuário selecionar.</span><span class="sxs-lookup"><span data-stu-id="069b2-269">**Speak on selected text** - Enable or disable the Speak Selection accessibility settings, which can read aloud the text that the user selects.</span></span>
-   <span data-ttu-id="069b2-270">**Controle VoiceOver** – Habilitar ou desabilitar os ajustes de narração que permitem que o usuário ajuste a função VoiceOver (por exemplo, a rapidez que o texto na tela é lido em voz alta).</span><span class="sxs-lookup"><span data-stu-id="069b2-270">**VoiceOver control** - Enable or disable voiceover adjustments, which let the user adjust the VoiceOver function (for example, how fast on-screen text is read aloud).</span></span>
-   <span data-ttu-id="069b2-271">**Controle de Zoom** – Habilitar ou desabilitar os ajustes de zoom que permitem ao usuário ajustar a função de zoom.</span><span class="sxs-lookup"><span data-stu-id="069b2-271">**Zoom control** - Enable or disable zoom adjustments, which let the user adjust the zoom function.</span></span>
=======
## Quiosque
<a id="kiosk" class="xliff"></a>
-   **Bloqueio de Ativação** – Habilitar o Bloqueio de Ativação em dispositivos iOS supervisionados.
-   **Aplicativo que é executado no modo de quiosque** – Escolha **Aplicativo Gerenciado** para selecionar um aplicativo que você adicionou ao Intune, ou **Aplicativo da Loja** para especificar a URL para um aplicativo na loja. Nenhum outro aplicativo poderá ser executado no dispositivo. Para obter mais ajuda, consulte "How to specify URLs to app stores" (Como especificar URLs para lojas de aplicativos) mais adiante neste tópico.
-   **Toque auxiliar** – Habilitar ou desabilitar a configuração de acessibilidade **Toque auxiliar**, que ajuda o usuário a executar gestos na tela que podem ser difíceis de executar.
-   **Inverter cores** – Habilitar ou desabilitar a configuração de acessibilidade Inverter Cores que ajusta a exibição para ajudar os usuários com deficiências visuais.
-   **Áudio mono** – Habilitar ou desabilitar a configuração de acessibilidade Áudio mono.
-   **VoiceOver** – Habilitar ou desabilitar a configuração de acessibilidade **VoiceOver**, que lê em voz alta o texto na tela do dispositivo.
-   **Zoom** – Habilitar ou desabilitar a configuração de acessibilidade de **Zoom** que permite ao usuário usar o toque para ampliar a tela do dispositivo de acessibilidade.
-   **Bloqueio automático**- Habilitar ou desabilitar o bloqueio automático do dispositivo.
-   **Botão de toque** – Habilitar ou desabilitar a opção de botão de toque (mudo) no dispositivo.
-   **Rotação da tela** – Habilitar ou desabilitar a alteração da orientação da tela quando o usuário gira o dispositivo.
-   **Botão de suspensão da tela** – Habilitar ou desabilitar o botão de suspensão e ativação da tela no dispositivo.
-   **Toque** – Habilitar ou desabilitar a tela touch no dispositivo.
-   **Botões de volume** – Habilitar ou desabilitar o uso dos botões de volume no dispositivo.
-   **Controle de toque auxiliar** – Habilitar ou desabilitar os ajustes de toque auxiliar que permitem ao usuário ajustar a função de toque auxiliar.
-   **Controle de inversão e cores** – Habilitar ou desabilitar ajustes de inverter ajustes que permite ao usuário ajustar a função inverter cores.
-   **Falar texto selecionado** – Habilitar ou desabilitar as configurações de acessibilidade Seleção de fala que podem ler em voz alta o texto que o usuário selecionar.
-   **Controle VoiceOver** – Habilitar ou desabilitar os ajustes de narração que permitem que o usuário ajuste a função VoiceOver (por exemplo, a rapidez que o texto na tela é lido em voz alta).
-   **Controle de Zoom** – Habilitar ou desabilitar os ajustes de zoom que permitem ao usuário ajustar a função de zoom.
>>>>>>> live

>[!NOTE]
> <span data-ttu-id="069b2-272">Antes de configurar um dispositivo iOS para o modo de quiosque, você deve usar a ferramenta Apple Configurator ou o Programa de registro de dispositivos da Apple para colocar o dispositivo no modo supervisionado.</span><span class="sxs-lookup"><span data-stu-id="069b2-272">Before you can configure an iOS device for kiosk mode, you must use the Apple Configurator tool or the Apple Device Enrollment Program to put the device into supervised mode.</span></span> <span data-ttu-id="069b2-273">Para obter mais informações sobre a ferramenta Apple Configurator, consulte sua documentação da Apple.</span><span class="sxs-lookup"><span data-stu-id="069b2-273">For more information about the Apple Configurator tool, see your Apple documentation.</span></span>
><span data-ttu-id="069b2-274">Se o aplicativo iOS que você especificar for instalado após a atribuição do perfil, o dispositivo só entrará no modo de quiosque depois de ser reiniciado.</span><span class="sxs-lookup"><span data-stu-id="069b2-274">If the iOS app that you specify is installed after you assign the profile, the device will not enter kiosk mode until after it is restarted.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="069b2-275">Safari</span><span class="sxs-lookup"><span data-stu-id="069b2-275">Safari</span></span>
<a id="safari" class="xliff"></a>
-   <span data-ttu-id="069b2-276">**Safari (somente supervisado)** – Especifique se o navegador Safari pode ser usado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="069b2-276">**Safari (supervised only)** - Specify whether the Safari browser can be used on the device.</span></span>
-   <span data-ttu-id="069b2-277">**Preenchimento automático** – Permite que o usuário possa alterar as configurações de preenchimento automático no navegador.</span><span class="sxs-lookup"><span data-stu-id="069b2-277">**Autofill** - Allow the user to change autocomplete settings in the browser.</span></span>
-   <span data-ttu-id="069b2-278">**Cookies** – Permitir que o navegador use cookies.</span><span class="sxs-lookup"><span data-stu-id="069b2-278">**Cookies** - Allow the browser to use cookies.</span></span>
-   <span data-ttu-id="069b2-279">**JavaScript** – Permitir a execução de scripts Java no navegador.</span><span class="sxs-lookup"><span data-stu-id="069b2-279">**JavaScript** - Allow Java scripts to run in the browser.</span></span>
-   <span data-ttu-id="069b2-280">**Avisos de fraude** – Permitir avisos de fraude no navegador.</span><span class="sxs-lookup"><span data-stu-id="069b2-280">**Fraud warnings** - Allow fraud warnings in the browser.</span></span>
-   <span data-ttu-id="069b2-281">**Pop-ups** – Habilitar ou desabilitar o bloqueador de pop-ups do navegador.</span><span class="sxs-lookup"><span data-stu-id="069b2-281">**Pop-ups** - Enable or disable the browser pop-up blocker.</span></span>


## <span data-ttu-id="069b2-282">Domínios</span><span class="sxs-lookup"><span data-stu-id="069b2-282">Domains</span></span>
<a id="domains" class="xliff"></a>

### <span data-ttu-id="069b2-283">Domínios de email desmarcados</span><span class="sxs-lookup"><span data-stu-id="069b2-283">Unmarked email domains</span></span>
=======
## Safari
<a id="safari" class="xliff"></a>
-   **Safari (somente supervisado)** – Especifique se o navegador Safari pode ser usado no dispositivo.
-   **Preenchimento automático** – Permite que o usuário possa alterar as configurações de preenchimento automático no navegador.
-   **Cookies** – Permitir que o navegador use cookies.
-   **JavaScript** – Permitir a execução de scripts Java no navegador.
-   **Avisos de fraude** – Permitir avisos de fraude no navegador.
-   **Pop-ups** – Habilitar ou desabilitar o bloqueador de pop-ups do navegador.


## Domínios
<a id="domains" class="xliff"></a>

### Domínios de email desmarcados
>>>>>>> live
<a id="unmarked-email-domains" class="xliff"></a>

<span data-ttu-id="069b2-284">No campo **URL do Domínio de Email**, adicione uma ou mais URLs à lista.</span><span class="sxs-lookup"><span data-stu-id="069b2-284">In the **Email Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="069b2-285">Quando os usuários finais receberem um email de um domínio diferente daqueles configurados por você, o email será marcado como não confiável no aplicativo Mail do iOS.</span><span class="sxs-lookup"><span data-stu-id="069b2-285">When end users receive an email from a domain other than those you configured, the email will be marked as untrusted in the iOS Mail app.</span></span>


<<<<<<< HEAD
### <span data-ttu-id="069b2-286">Domínios da web gerenciados</span><span class="sxs-lookup"><span data-stu-id="069b2-286">Managed web domains</span></span>
=======
### Domínios da web gerenciados
>>>>>>> live
<a id="managed-web-domains" class="xliff"></a>

<span data-ttu-id="069b2-287">No campo **URL do Domínio da Web**, adicione uma ou mais URLs à lista.</span><span class="sxs-lookup"><span data-stu-id="069b2-287">In the **Web Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="069b2-288">Quando os documentos forem baixados dos domínios especificados, eles serão considerados gerenciados.</span><span class="sxs-lookup"><span data-stu-id="069b2-288">When documents are downloaded from the domains you specify, they will be considered managed.</span></span> <span data-ttu-id="069b2-289">Essa configuração só se aplica a documentos baixados usando o navegador Safari.</span><span class="sxs-lookup"><span data-stu-id="069b2-289">This setting applies only to documents downloaded using the Safari browser.</span></span>


<<<<<<< HEAD
### <span data-ttu-id="069b2-290">Domínios de preenchimento automático de senha do Safari</span><span class="sxs-lookup"><span data-stu-id="069b2-290">Safari password auto fill domains</span></span>
=======
### Domínios de preenchimento automático de senha do Safari
>>>>>>> live
<a id="safari-password-auto-fill-domains" class="xliff"></a>

<span data-ttu-id="069b2-291">No campo **URL do Domínio**, adicione uma ou mais URLs à lista.</span><span class="sxs-lookup"><span data-stu-id="069b2-291">In the **Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="069b2-292">Os usuários só podem salvar senhas da Web das URLs nesta lista.</span><span class="sxs-lookup"><span data-stu-id="069b2-292">Users can only save web passwords from URLs in this list.</span></span> <span data-ttu-id="069b2-293">Essa configuração se aplica somente ao navegador Safari e aos dispositivos com iOS 9.3 e posteriores no modo supervisionado.</span><span class="sxs-lookup"><span data-stu-id="069b2-293">This setting applies only to the Safari browser, and to iOS 9.3 and later devices in supervised mode.</span></span> <span data-ttu-id="069b2-294">Se você não especificar URLs, será possível salvar senhas de todos os sites.</span><span class="sxs-lookup"><span data-stu-id="069b2-294">If you don't specify any URLs, then passwords can be saved from all web sites.</span></span>
