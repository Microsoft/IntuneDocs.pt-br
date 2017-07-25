---
title: "Configurações de restrição de dispositivo do Intune para Windows 8.1"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para controlar as configurações e as funcionalidades do dispositivo em dispositivos Windows 8.1."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da190ddeda62ce3385aab4308595b473c3059ed6
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
# <span data-ttu-id="6e0d2-103">Configurações de restrição de dispositivo do Windows 8.1 e posterior no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6e0d2-103">Windows 8.1 and later device restriction settings in Microsoft Intune</span></span>
<a id="windows-81-and-later-device-restriction-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <span data-ttu-id="6e0d2-104">Geral</span><span class="sxs-lookup"><span data-stu-id="6e0d2-104">General</span></span>
<a id="general" class="xliff"></a>
-   <span data-ttu-id="6e0d2-105">**Aplicar todas as configurações ao Windows 10** – Permite que as configurações desta política sejam aplicadas a dispositivos Windows 10 além de dispositivos Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-105">**Apply all configurations to Windows 10** - Enables settings in this policy to be applied to Windows 10 devices, in addition to Windows 8.1 devices.</span></span>
-   <span data-ttu-id="6e0d2-106">**Envio de dados de diagnóstico** – Permite que o dispositivo envie informações de diagnóstico à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-106">**Diagnostic data submission** - Enables the device to submit diagnostic information to Microsoft.</span></span>
-   <span data-ttu-id="6e0d2-107">**Firewall** – Exige que o Firewall do Windows esteja ativado.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-107">**Firewall** - Requires that the Windows Firewall is turned on.</span></span>
-   <span data-ttu-id="6e0d2-108">**Controle de Conta de Usuário** – Exige o uso de UAC (Controle de Conta de Usuário) nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-108">**User Account Control** - Requires the use of User Account Control (UAC) on devices.</span></span>
## <span data-ttu-id="6e0d2-109">Senha</span><span class="sxs-lookup"><span data-stu-id="6e0d2-109">Password</span></span>
<a id="password" class="xliff"></a>
-   <span data-ttu-id="6e0d2-110">**Tipo de senha exigida** – Exigir que o usuário final insira uma senha para acessar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-110">**Required password type** - Require the end user to enter a password to access the device.</span></span>
-   <span data-ttu-id="6e0d2-111">**Tamanho mínimo de senha** – Define o tamanho mínimo necessário (em caracteres) para a senha.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-111">**Minimum password length** - Configures the minimum required length (in characters) for the password.</span></span>
-   <span data-ttu-id="6e0d2-112">**Número de falhas de entrada antes de apagar o dispositivo** – Apaga o dispositivo se as tentativas de entrada falharem esse número de vezes.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-112">**Number of sign-in failures before wiping device** - Wipes the device if the sign-in attempts fail this number of times.</span></span>
-   <span data-ttu-id="6e0d2-113">**Máximo de minutos de inatividade para bloquear a tela** – Especifica o número de minutos que um dispositivo deve permanecer ocioso antes que uma senha seja necessária para desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-113">**Maximum minutes of inactivity until screen locks** - Specifies the number of minutes a device must be idle before a password is required to unlock it.</span></span>
-   <span data-ttu-id="6e0d2-114">**Expiração da senha (dias)** – Especifica o número de dias antes que a senha do dispositivo precise ser alterada.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-114">**Password expiration (days)** - Specifies the number of days before the device password must be changed.</span></span>
-   <span data-ttu-id="6e0d2-115">**Impedir a reutilização de senhas anteriores** – Especifica se o usuário pode definir senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-115">**Prevent reuse of previous passwords** - Specifies whether the user can configure previously used passwords.</span></span>
-   <span data-ttu-id="6e0d2-116">**Senha com imagem e PIN** – Habilita o uso de uma senha com imagem e PIN.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-116">**Picture password and PIN** - Enables the use of a picture password and PIN.</span></span> <span data-ttu-id="6e0d2-117">Uma senha com imagem permite que o usuário entre fazendo gestos em uma imagem.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-117">A picture password lets the user sign in with gestures on a picture.</span></span> <span data-ttu-id="6e0d2-118">Um PIN permite que os usuários entrem rapidamente com um código de quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-118">A PIN lets users quickly sign in with a four-digit code.</span></span>
-   <span data-ttu-id="6e0d2-119">**Criptografia** – Exige que os arquivos no dispositivo sejam criptografados.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-119">**Encryption** - Requires that files on the device are encrypted.</span></span><br><span data-ttu-id="6e0d2-120">Para impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](https://support.microsoft.com/kb/3013816) em cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-120">To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/kb/3013816) on each device.</span></span>
<span data-ttu-id="6e0d2-121">Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-121">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>
<span data-ttu-id="6e0d2-122">Para a criptografia funcionar, o dispositivo deve atender aos requisitos de certificação de hardware [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97).</span><span class="sxs-lookup"><span data-stu-id="6e0d2-122">For encryption to work, the device must meet the [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) hardware certification requirements.</span></span>
<span data-ttu-id="6e0d2-123">Quando você impõe a criptografia em um dispositivo, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-123">When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account.</span></span> <span data-ttu-id="6e0d2-124">Não é possível recuperar essa chave em nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-124">You cannot recover this key on behalf of a user.</span></span>     



## <span data-ttu-id="6e0d2-125">Navegador</span><span class="sxs-lookup"><span data-stu-id="6e0d2-125">Browser</span></span>
<a id="browser" class="xliff"></a>
-   <span data-ttu-id="6e0d2-126">**Preenchimento automático** – Habilita os usuários a alterarem as configurações de preenchimento automático no navegador.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-126">**Autofill** - Enables users to change autocomplete settings in the browser.</span></span>
-   <span data-ttu-id="6e0d2-127">**Aviso de fraude** – Habilita ou desabilita avisos de sites fraudulentos potenciais.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-127">**Fraud warnings** - Enables or disables warnings for potential fraudulent websites.</span></span>
-   <span data-ttu-id="6e0d2-128">**SmartScreen** – Habilita ou desabilita avisos de sites fraudulentos potenciais.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-128">**SmartScreen** - Enables or disables warnings for potential fraudulent websites.</span></span>
-   <span data-ttu-id="6e0d2-129">**JavaScript** – Habilita o navegador a executar scripts, como scripts Java.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-129">**JavaScript** - Enables the browser to run scripts, such as Java script.</span></span>
-   <span data-ttu-id="6e0d2-130">**Pop-ups** – Habilita ou desabilita o bloqueador de pop-ups do navegador.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-130">**Pop-ups** - Enables or disables the browser pop-up blocker.</span></span>
-   <span data-ttu-id="6e0d2-131">**Enviar cabeçalhos Do Not Track** – Envia um cabeçalho Do Not Track para os sites visitados no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-131">**Send do-not-track headers** - Sends a do not track header to visited sites in Internet Explorer.</span></span>
-   <span data-ttu-id="6e0d2-132">**Plug-ins** – Habilita os usuários a adicionar plug-ins ao Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-132">**Plugins** - Enables users to add plug-ins to Internet Explorer.</span></span>
-   <span data-ttu-id="6e0d2-133">**Entrada de palavra única no site da intranet** – Habilita o uso de uma única palavra para direcionar o Internet Explorer a um site, como o Bing.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-133">**Single word entry on intranet site** - Enables use of a single word to direct Internet Explorer to a web site, such as Bing.</span></span>
-   <span data-ttu-id="6e0d2-134">**Detectar site da intranet automaticamente** – Permite configurar a segurança para sites de intranet no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-134">**Auto detect of intranet site** - Helps configure security for intranet sites in Internet Explorer.</span></span>
-   <span data-ttu-id="6e0d2-135">**Nível de segurança da Internet** – Define o nível de segurança do Internet Explorer para sites da Internet.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-135">**Internet security level** - Sets the Internet Explorer security level for Internet sites.</span></span>
-   <span data-ttu-id="6e0d2-136">**Nível de segurança da Intranet** – Define o nível de segurança do Internet Explorer para sites da Intranet.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-136">**Intranet security level** - Sets the Internet Explorer security level for intranet sites.</span></span>
-   <span data-ttu-id="6e0d2-137">**Nível de segurança de sites confiáveis** – Configura o nível de segurança para a zona de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-137">**Trusted sites security level** - Configures the security level for the trusted sites zone.</span></span>
-   <span data-ttu-id="6e0d2-138">**Segurança alta para sites restritos** – Configura o nível de segurança para a zona de sites restritos.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-138">**High security for restricted sites** - Configures the security level for the restricted sites zone.</span></span>
-   <span data-ttu-id="6e0d2-139">**Acesso ao menu no modo Empresarial** – Permite aos usuários acessar as opções de menu do modo Empresarial do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-139">**Enterprise mode menu access** - Lets users access the Enterprise Mode menu options from Internet Explorer.</span></span>
<span data-ttu-id="6e0d2-140">Se selecionar essa configuração, você também poderá especificar um **Local de relatório de log**, que contém uma URL para um relatório que mostra os sites para os quais os usuários ativaram o acesso do modo Empresarial.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-140">If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.</span></span>
-   <span data-ttu-id="6e0d2-141">**Local da lista de site do modo Empresarial** – Especifica o local da lista de sites que usarão o modo Empresarial quando ele estiver ativo.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-141">**Enterprise mode site list location** - Specifies the location of the list of websites that will use Enterprise Mode when it is active.</span></span>
## <span data-ttu-id="6e0d2-142">Celular</span><span class="sxs-lookup"><span data-stu-id="6e0d2-142">Cellular</span></span>
<a id="cellular" class="xliff"></a>
-   <span data-ttu-id="6e0d2-143">**Roaming de dados** – Habilita o roaming de dados quando o dispositivo estiver em uma rede de celular.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-143">**Data roaming** - Enables data roaming when the device is on a cellular network.</span></span>
## <span data-ttu-id="6e0d2-144">Nuvem e Armazenamento</span><span class="sxs-lookup"><span data-stu-id="6e0d2-144">Cloud and Storage</span></span>
<a id="cloud-and-storage" class="xliff"></a>
-   <span data-ttu-id="6e0d2-145">**URL de pastas de trabalho** – Define a URL da pasta de trabalho para permitir que os documentos sejam sincronizados em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-145">**Work folders URL** - Sets the URL of the work folder to allow documents to be synchronized across devices.</span></span>
-   <span data-ttu-id="6e0d2-146">**Acesso ao aplicativo Windows Mail sem uma conta da Microsoft** – Habilita o acesso ao aplicativo Windows Mail sem uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6e0d2-146">**Access to Windows Mail app without a Microsoft account** - Enables access to the Windows Mail application without a Microsoft account.</span></span>    
