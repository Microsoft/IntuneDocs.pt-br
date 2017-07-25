---
title: "Configurações de política do Windows"
description: "Use a Política de configuração geral do Windows (Windows 8.1 e posterior) do Intune para definir as configurações para dispositivos Windows 8.1 e Windows 8 registrados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6982a2bc-aafa-475a-9236-4840b709e5a1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ab39a1847dbba495b4946d12b96b6f8c724f38d8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="ba2e1-103">Configurações de política do Windows no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2e1-103">Windows policy settings in Microsoft Intune</span></span>
<a id="windows-policy-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ba2e1-104">Use a **Política de configuração geral do Windows (Windows 8.1 e posterior)** do Microsoft Intune para definir as seguintes configurações para dispositivos Windows 8, Windows 8.1 e Windows RT 8.1 registrados:</span><span class="sxs-lookup"><span data-stu-id="ba2e1-104">Use the Microsoft Intune **Windows general configuration policy (Windows 8.1 and later)** to configure the following settings for enrolled Windows 8, Windows 8.1, and Windows RT 8.1 devices:</span></span>

## <span data-ttu-id="ba2e1-105">Configurações de aplicabilidade</span><span class="sxs-lookup"><span data-stu-id="ba2e1-105">Applicability settings</span></span>
<a id="applicability-settings" class="xliff"></a>

|<span data-ttu-id="ba2e1-106">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-106">Setting name</span></span>|<span data-ttu-id="ba2e1-107">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-107">Details</span></span>|
|----------------|----------------------------------|
|<span data-ttu-id="ba2e1-108">**Aplicar todas as configurações ao Windows 10**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-108">**Apply all configurations to Windows 10**</span></span>|<span data-ttu-id="ba2e1-109">Permite que as configurações desta política sejam aplicadas a dispositivos Windows 10 além de dispositivos Windows 8 e Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-109">Enables settings in this policy to be applied to Windows 10 devices, in addition to Windows 8 and Windows 8.1 devices.</span></span>|

## <span data-ttu-id="ba2e1-110">Configurações de segurança</span><span class="sxs-lookup"><span data-stu-id="ba2e1-110">Security settings</span></span>
<a id="security-settings" class="xliff"></a>

|<span data-ttu-id="ba2e1-111">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-111">Setting name</span></span>|<span data-ttu-id="ba2e1-112">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-112">Details</span></span>|
|----------------|------|
|<span data-ttu-id="ba2e1-113">**Tipo de senha necessária**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-113">**Required password type**</span></span>|<span data-ttu-id="ba2e1-114">Especifica o tipo de senha necessário, como apenas com caracteres numéricos ou alfanuméricos.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-114">Specifies the type of password that's required, such as alphanumeric or numeric only.</span></span>|
|<span data-ttu-id="ba2e1-115">**Tipo de senha necessária – número mínimo de conjuntos de caracteres**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-115">**Required password type – Minimum number of character sets**</span></span>|<span data-ttu-id="ba2e1-116">Especifica quantos conjuntos de caracteres diferentes devem ser incluídos na senha.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-116">Specifies how many different character sets must be included in the password.</span></span> <span data-ttu-id="ba2e1-117">Há quatro conjuntos de caracteres: letras minúsculas, letras maiúsculas, símbolos e números.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-117">There are four character sets: lowercase letters, uppercase letters, numbers, and symbols.</span></span> <span data-ttu-id="ba2e1-118">No entanto, para dispositivos iOS, essa configuração especifica o número de símbolos que devem ser incluídos na senha.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-118">However, for iOS devices, this setting specifies the number of symbols that must be included in the password.</span></span>|
|<span data-ttu-id="ba2e1-119">**Comprimento mínimo da senha**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-119">**Minimum password length**</span></span>|<span data-ttu-id="ba2e1-120">Define o tamanho mínimo necessário (em caracteres) para a senha.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-120">Configures the minimum required length (in characters) for the password.</span></span>|
|<span data-ttu-id="ba2e1-121">**Número de falhas de entrada repetidas permitidas antes que o dispositivo seja apagado**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-121">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="ba2e1-122">Apagará o dispositivo se houver falha neste número de tentativas de entrada.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-122">Wipes the device if the sign-in attempts fail this number of times.</span></span>|
|<span data-ttu-id="ba2e1-123">**Minutos de inatividade antes que a tela se apague**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-123">**Minutes of inactivity before screen turns off**</span></span>|<span data-ttu-id="ba2e1-124">Especifica o número de minutos que um dispositivo deve permanecer ocioso antes que uma senha seja necessária para desbloqueá-lo.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-124">Specifies the number of minutes a device must be idle before a password is required to unlock it.</span></span>|
|<span data-ttu-id="ba2e1-125">**Expiração da senha (dias)**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-125">**Password expiration (days)**</span></span>|<span data-ttu-id="ba2e1-126">Especifica o número de dias antes que a senha do dispositivo precise ser alterada.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-126">Specifies the number of days before the device password must be changed.</span></span>|
|<span data-ttu-id="ba2e1-127">**Lembrar histórico de senha**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-127">**Remember password history**</span></span>|<span data-ttu-id="ba2e1-128">Especifica se o usuário pode definir senhas usadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-128">Specifies whether the user can configure previously used passwords.</span></span>|
|<span data-ttu-id="ba2e1-129">**Lembrar histórico de senha** – **Evitar a reutilização de senhas anteriores**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-129">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="ba2e1-130">Especifica o número de senhas usadas anteriormente que são lembradas pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-130">Specifies the number of previously used passwords that are remembered by the device.</span></span>|
|<span data-ttu-id="ba2e1-131">**Permitir senha de imagem e PIN**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-131">**Allow picture password and PIN**</span></span>|<span data-ttu-id="ba2e1-132">Habilita o uso de uma senha com imagem e PIN.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-132">Enables the use of a picture password and PIN.</span></span> <span data-ttu-id="ba2e1-133">Uma senha com imagem permite que o usuário entre fazendo gestos em uma imagem.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-133">A picture password lets the user sign in with gestures on a picture.</span></span> <span data-ttu-id="ba2e1-134">Um PIN permite que os usuários entrem rapidamente com um código de quatro dígitos.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-134">A PIN lets users quickly sign in with a four-digit code.</span></span>|

## <span data-ttu-id="ba2e1-135">Configurações de criptografia</span><span class="sxs-lookup"><span data-stu-id="ba2e1-135">Encryption settings</span></span>
<a id="encryption-settings" class="xliff"></a>

|<span data-ttu-id="ba2e1-136">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-136">Setting name</span></span>|<span data-ttu-id="ba2e1-137">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-137">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ba2e1-138">**Exigir criptografia no dispositivo móvel**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ba2e1-138">**Require encryption on mobile device**<sup>1</sup></span></span>|<span data-ttu-id="ba2e1-139">Exige que os arquivos no dispositivo sejam criptografados.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-139">Requires that files on the device are encrypted.</span></span>|
<span data-ttu-id="ba2e1-140"><sup>1</sup> Mais informações sobre dispositivos que executam o Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="ba2e1-140"><sup>1</sup> Additional information for devices that run Windows 8.1</span></span>

-   <span data-ttu-id="ba2e1-141">Para impor a criptografia em dispositivos que executam o Windows 8.1, você deve instalar a [Atualização do cliente do MDM de dezembro de 2014 para Windows](http://support.microsoft.com/kb/3013816) em cada dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-141">To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](http://support.microsoft.com/kb/3013816) on each device.</span></span>

-   <span data-ttu-id="ba2e1-142">Se você habilitar essa configuração para dispositivos Windows 8.1, todos os usuários do dispositivo precisarão ter uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-142">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>

-   <span data-ttu-id="ba2e1-143">Para a criptografia funcionar, o dispositivo deve atender aos requisitos de certificação de hardware [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-143">For encryption to work, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.</span></span>

-   <span data-ttu-id="ba2e1-144">Quando você impõe a criptografia em um dispositivo, a chave de recuperação fica acessível apenas da conta da Microsoft do usuário, que é acessada de sua conta do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-144">When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account.</span></span> <span data-ttu-id="ba2e1-145">Não é possível recuperar essa chave em nome de um usuário.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-145">You cannot recover this key on behalf of a user.</span></span>

## <span data-ttu-id="ba2e1-146">Configurações de malware</span><span class="sxs-lookup"><span data-stu-id="ba2e1-146">Malware settings</span></span>
<a id="malware-settings" class="xliff"></a>

|<span data-ttu-id="ba2e1-147">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-147">Setting name</span></span>|<span data-ttu-id="ba2e1-148">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-148">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ba2e1-149">**Exigir firewall de rede**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-149">**Require network firewall**</span></span>|<span data-ttu-id="ba2e1-150">Exige que o Firewall do Windows esteja ativado.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-150">Requires that the Windows Firewall is turned on.</span></span>|
|<span data-ttu-id="ba2e1-151">**Habilitar SmartScreen**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-151">**Enable SmartScreen**</span></span>|<span data-ttu-id="ba2e1-152">Exige o uso do Windows SmartScreen.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-152">Requires the use of Windows SmartScreen.</span></span>|

## <span data-ttu-id="ba2e1-153">Configurações de sistema</span><span class="sxs-lookup"><span data-stu-id="ba2e1-153">System settings</span></span>
<a id="system-settings" class="xliff"></a>

|<span data-ttu-id="ba2e1-154">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-154">Setting name</span></span>|<span data-ttu-id="ba2e1-155">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-155">Details</span></span>|
|----------------|-------|
|<span data-ttu-id="ba2e1-156">**Exigir atualizações automáticas**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-156">**Require automatic updates**</span></span>|<span data-ttu-id="ba2e1-157">Ativa a configuração de atualizações automáticas em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-157">Turns on the automatic updates setting on devices.</span></span>|
|<span data-ttu-id="ba2e1-158">**Exigir atualizações automáticas – Classificação mínima das atualizações a serem instaladas automaticamente**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-158">**Require automatic updates – Minimum classification of updates to install automatically**</span></span>|<span data-ttu-id="ba2e1-159">Escolhe a classificação das atualizações que serão instaladas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="ba2e1-159">Chooses the classification of updates that will be installed automatically:</span></span><br /><br /><span data-ttu-id="ba2e1-160">-   **Importante** – instala todas as atualizações classificadas como importantes.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-160">-   **Important** – Installs all updates that are classified as important.</span></span><br /><span data-ttu-id="ba2e1-161">-   **Recomendado** – instala todas as atualizações classificadas como importantes ou recomendadas.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-161">-   **Recommended** – Installs all updates that are classified as important or recommended.</span></span>|
|<span data-ttu-id="ba2e1-162">**Controle de conta de usuário**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-162">**User Account Control**</span></span>|<span data-ttu-id="ba2e1-163">Exige o uso de UAC (Controle de Conta de Usuário ) em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-163">Requires the use of User Account Control (UAC) on devices.</span></span>|
|<span data-ttu-id="ba2e1-164">**Permitir envio de dados de diagnóstico**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-164">**Allow diagnostic data submission**</span></span>|<span data-ttu-id="ba2e1-165">Permite que o dispositivo envie informações de diagnóstico à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-165">Enables the device to submit diagnostic information to Microsoft.</span></span>|


## <span data-ttu-id="ba2e1-166">Configurações de nuvem – documentos e dados</span><span class="sxs-lookup"><span data-stu-id="ba2e1-166">Cloud settings – documents and data</span></span>
<a id="cloud-settings--documents-and-data" class="xliff"></a>

|<span data-ttu-id="ba2e1-167">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-167">Setting name</span></span>|<span data-ttu-id="ba2e1-168">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-168">Details</span></span>|
|----------------|------|
|<span data-ttu-id="ba2e1-169">**URL de pastas de trabalho**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-169">**Work Folders URL**</span></span>|<span data-ttu-id="ba2e1-170">Define a URL da pasta de trabalho para permitir que os documentos sejam sincronizados em todos os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-170">Sets the URL of the work folder to allow documents to be synchronized across devices.</span></span>|

## <span data-ttu-id="ba2e1-171">Configurações de email</span><span class="sxs-lookup"><span data-stu-id="ba2e1-171">Email settings</span></span>
<a id="email-settings" class="xliff"></a>

|<span data-ttu-id="ba2e1-172">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-172">Setting name</span></span>|<span data-ttu-id="ba2e1-173">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-173">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ba2e1-174">**Tornar a conta da Microsoft opcional em um aplicativo Windows Mail**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-174">**Make Microsoft account optional in Windows Mail application**</span></span>|<span data-ttu-id="ba2e1-175">Habilita o acesso ao aplicativo de Email do Windows sem uma conta da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-175">Enables access to the Windows Mail application without a Microsoft account.</span></span>|

## <span data-ttu-id="ba2e1-176">Configurações de aplicativo - navegador</span><span class="sxs-lookup"><span data-stu-id="ba2e1-176">Application settings - browser</span></span>
<a id="application-settings---browser" class="xliff"></a>

|<span data-ttu-id="ba2e1-177">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-177">Setting name</span></span>|<span data-ttu-id="ba2e1-178">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-178">Details</span></span>|
|----------------|-----|
|<span data-ttu-id="ba2e1-179">**Permitir preenchimento automático**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-179">**Allow autofill**</span></span>|<span data-ttu-id="ba2e1-180">Habilita os usuários a alterarem as configurações de preenchimento automático no navegador.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-180">Enables users to change autocomplete settings in the browser.</span></span>|
|<span data-ttu-id="ba2e1-181">**Permitir bloqueador de pop-up**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-181">**Allow pop-up blocker**</span></span>|<span data-ttu-id="ba2e1-182">Habilita ou desabilita o bloqueador de pop-ups do navegador.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-182">Enables or disables the browser pop-up blocker.</span></span>|
|<span data-ttu-id="ba2e1-183">**Permitir plug-ins**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-183">**Allow plug-ins**</span></span>|<span data-ttu-id="ba2e1-184">Habilita os usuários a adicionar plug-ins ao Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-184">Enables users to add plug-ins to Internet Explorer.</span></span>|
|<span data-ttu-id="ba2e1-185">**Permitir scripts ativos**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-185">**Allow active scripting**</span></span>|<span data-ttu-id="ba2e1-186">Habilita o navegador a executar scripts, como scripts do ActiveX.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-186">Enables the browser to run scripts, such as Active X scripts.</span></span>|
|<span data-ttu-id="ba2e1-187">**Permitir aviso de fraude**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-187">**Allow fraud warning**</span></span>|<span data-ttu-id="ba2e1-188">Habilita ou desabilita avisos de sites fraudulentos potenciais.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-188">Enables or disables warnings for potential fraudulent websites.</span></span>|
|<span data-ttu-id="ba2e1-189">**Permitir site de intranet para entrada de palavra única**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-189">**Allow intranet site for single word entry**</span></span>|<span data-ttu-id="ba2e1-190">Habilita o uso de uma única palavra para direcionar o Internet Explorer a um site, como o Bing.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-190">Enables use of a single word to direct Internet Explorer to a web site, such as Bing.</span></span>|
|<span data-ttu-id="ba2e1-191">**Permitir detecção automática de rede intranet**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-191">**Allow automatic detection of intranet network**</span></span>|<span data-ttu-id="ba2e1-192">Permite configurar a segurança para sites de intranet no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-192">Helps configure security for intranet sites in Internet Explorer.</span></span>|
|<span data-ttu-id="ba2e1-193">**Nível de segurança para Internet**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-193">**Security level for Internet**</span></span>|<span data-ttu-id="ba2e1-194">Define o nível de segurança do Internet Explorer para sites da Internet.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-194">Sets the Internet Explorer security level for Internet sites.</span></span>|
|<span data-ttu-id="ba2e1-195">**Nível de segurança para a intranet**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-195">**Security level for intranet**</span></span>|<span data-ttu-id="ba2e1-196">Define o nível de segurança do Internet Explorer para sites da intranet.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-196">Sets the Internet Explorer security level for intranet sites.</span></span>|
|<span data-ttu-id="ba2e1-197">**Nível de segurança para sites confiáveis**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-197">**Security level for trusted sites**</span></span>|<span data-ttu-id="ba2e1-198">Configura o nível de segurança para a zona de sites confiáveis.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-198">Configures the security level for the trusted sites zone.</span></span>|
|<span data-ttu-id="ba2e1-199">**Nível de segurança para sites restritos**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-199">**Security level for restricted sites**</span></span>|<span data-ttu-id="ba2e1-200">Configura o nível de segurança para a zona de sites restritos.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-200">Configures the security level for the restricted sites zone.</span></span>|
|<span data-ttu-id="ba2e1-201">**Enviar cabeçalho Não Rastrear**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-201">**Send Do Not Track header**</span></span>|<span data-ttu-id="ba2e1-202">Envia um cabeçalho Não Rastrear para os sites visitados no Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-202">Sends  a do not track header to visited sites in Internet Explorer.</span></span>|
|<span data-ttu-id="ba2e1-203">**Permitir o acesso ao menu em Modo Empresarial**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-203">**Allow Enterprise Mode menu access**</span></span>|<span data-ttu-id="ba2e1-204">Permite aos usuários acessar as opções de menu do modo Empresarial do Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-204">Lets users access the Enterprise Mode menu options from Internet Explorer.</span></span><br><span data-ttu-id="ba2e1-205">Se selecionar essa configuração, você também poderá especificar um **Local de relatório de log**, que contém uma URL para um relatório que mostra os sites para os quais os usuários ativaram o acesso do modo Empresarial.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-205">If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.</span></span>|
|<span data-ttu-id="ba2e1-206">**Local do Enterprise Mode Site List**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-206">**Enterprise Mode site list location**</span></span>|<span data-ttu-id="ba2e1-207">Especifica o local da lista de sites que usarão o modo Empresarial quando ele estiver ativo.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-207">Specifies the location of the list of websites that will use Enterprise Mode when it is active.</span></span>|

## <span data-ttu-id="ba2e1-208">Configurações de recursos do dispositivo - celular</span><span class="sxs-lookup"><span data-stu-id="ba2e1-208">Device capabilities settings - cellular</span></span>
<a id="device-capabilities-settings---cellular" class="xliff"></a>

|<span data-ttu-id="ba2e1-209">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="ba2e1-209">Setting name</span></span>|<span data-ttu-id="ba2e1-210">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ba2e1-210">Details</span></span>|
|----------------|----|
|<span data-ttu-id="ba2e1-211">**Permitir roaming de dados**</span><span class="sxs-lookup"><span data-stu-id="ba2e1-211">**Allow data roaming**</span></span>|<span data-ttu-id="ba2e1-212">Habilita o roaming de dados quando o dispositivo estiver em uma rede de celular.</span><span class="sxs-lookup"><span data-stu-id="ba2e1-212">Enables data roaming when the device is on a cellular network.</span></span>|



### <span data-ttu-id="ba2e1-213">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ba2e1-213">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="ba2e1-214">Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ba2e1-214">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
