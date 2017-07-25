---
title: Coletar logs do dispositivo
description: Saiba como coletar logs de seus dispositivos gerenciados.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b15e4b7fa0c650a85a080c42d00cd75cb8783c62
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="96064-103">Logs de dispositivo</span><span class="sxs-lookup"><span data-stu-id="96064-103">Device logs</span></span>
<a id="device-logs" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="96064-104">Como parte dos esforços de solução de problemas, convém coletar logs de dispositivos de usuário.</span><span class="sxs-lookup"><span data-stu-id="96064-104">As part of your troubleshooting efforts you might want to collect logs from user devices.</span></span> <span data-ttu-id="96064-105">As instruções para coletar os logs são descritas aqui.</span><span class="sxs-lookup"><span data-stu-id="96064-105">Instructions for collecting those logs are described here.</span></span> <span data-ttu-id="96064-106">Normalmente, você precisará de acesso ao dispositivo para obter esses logs ou solicitar do usuário que ele colete os logs e envie para você.</span><span class="sxs-lookup"><span data-stu-id="96064-106">Typically you need to access to the device to get these logs or request from the user that they collect the logs and send them to you.</span></span>

### <span data-ttu-id="96064-107">Logs do Android</span><span class="sxs-lookup"><span data-stu-id="96064-107">Android logs</span></span>
<a id="android-logs" class="xliff"></a>
<span data-ttu-id="96064-108">Logs do Android estão localizados em *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.</span><span class="sxs-lookup"><span data-stu-id="96064-108">Android logs are located in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.</span></span>

<span data-ttu-id="96064-109">Ocasionalmente, os arquivos não aparecem, especialmente em dispositivos Android mais novos.</span><span class="sxs-lookup"><span data-stu-id="96064-109">Sometimes the files don't appear, especially on newer Android devices.</span></span> <span data-ttu-id="96064-110">Se isso acontecer, os usuários deverão abrir o aplicativo do Portal da Empresa para Android.</span><span class="sxs-lookup"><span data-stu-id="96064-110">If this happens, have your users open the Company Portal app for Android.</span></span> <span data-ttu-id="96064-111">Em seguida, eles deverão escolher **Configurações**>**Logs de cópia** e reinicializar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="96064-111">Then they should choose **Settings**>**Copy Logs** and reboot their device.</span></span>

<span data-ttu-id="96064-112">Para obter mais informações sobre como os usuários podem enviar logs de dados, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="96064-112">For more information about how your users can send you data logs, see the following articles:</span></span>

- <span data-ttu-id="96064-113">[Use o Log Detalhado para ajudar o administrador de TI a corrigir problemas do dispositivo](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): descreve como ativar o Log Detalhado, que envia todos os logs de dados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="96064-113">[Use Verbose Logging to help your IT admin fix device issues](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Describes how users turn on Verbose Logging, which sends you all of their data logs automatically.</span></span> <span data-ttu-id="96064-114">O Log Detalhado está ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="96064-114">By default, Verbose Logging is turned on.</span></span>

- [<span data-ttu-id="96064-115">Enviar logs de dados de diagnóstico do Android para o administrador de TI por email</span><span class="sxs-lookup"><span data-stu-id="96064-115">Send Android diagnostic data logs to your IT admin using email</span></span>](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [<span data-ttu-id="96064-116">Enviar logs de dados de diagnóstico para o administrador de TI usando um cabo USB</span><span class="sxs-lookup"><span data-stu-id="96064-116">Send diagnostic data logs to your IT admin using a USB cable</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <span data-ttu-id="96064-117">Logs do iOS</span><span class="sxs-lookup"><span data-stu-id="96064-117">iOS logs</span></span>
<a id="ios-logs" class="xliff"></a>

<span data-ttu-id="96064-118">Os usuários podem enviar erros de registro, conforme descrito em [Enviar erros de registro do iOS para o administrador de TI](/intune-user-help/send-errors-to-your-it-admin-ios).</span><span class="sxs-lookup"><span data-stu-id="96064-118">Users can send you enrollment errors, as described in [Send iOS enrollment errors to your IT administrator](/intune-user-help/send-errors-to-your-it-admin-ios).</span></span>

<span data-ttu-id="96064-119">Os usuários podem enviar logs de dispositivo, conforme descrito em [Enviar logs de dispositivo iOS](/intune-user-help/send-logs-to-microsoft-ios).</span><span class="sxs-lookup"><span data-stu-id="96064-119">Users can send device logs, as described in [Send iOS Device Logs](/intune-user-help/send-logs-to-microsoft-ios).</span></span>

### <span data-ttu-id="96064-120">Logs do Mac OS X</span><span class="sxs-lookup"><span data-stu-id="96064-120">Mac OS X logs</span></span>
<a id="mac-os-x-logs" class="xliff"></a>

1. <span data-ttu-id="96064-121">Abra o aplicativo **Console**.</span><span class="sxs-lookup"><span data-stu-id="96064-121">Open the **Console** app.</span></span>
2. <span data-ttu-id="96064-122">Em **ARQUIVOS**, escolha **system.log**.</span><span class="sxs-lookup"><span data-stu-id="96064-122">Under **FILES**, choose **system.log**.</span></span>
3. <span data-ttu-id="96064-123">Na barra de menus na parte superior, escolha **Arquivo** > **Salvar uma Cópia como...**.</span><span class="sxs-lookup"><span data-stu-id="96064-123">On the menu bar on the top, choose **File** > **Save a Copy As…**.</span></span> <span data-ttu-id="96064-124">Em seguida, salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="96064-124">Then save the file.</span></span>

### <span data-ttu-id="96064-125">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="96064-125">Windows Phone</span></span>
<a id="windows-phone" class="xliff"></a>

<span data-ttu-id="96064-126">No aplicativo do Portal da Empresa do Windows Phone, os usuários escolhem três pontos (**...**) para acessar o menu e escolhem **Enviar Logs**.</span><span class="sxs-lookup"><span data-stu-id="96064-126">In the Windows Phone Company Portal app, users choose the three dots (**…**) to access the menu, and then choose **Send Logs**.</span></span> <span data-ttu-id="96064-127">Essa opção está disponível antes e depois de entrar no aplicativo do Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="96064-127">This option is available both before and after signing in to the Company Portal app.</span></span>

### <span data-ttu-id="96064-128">Windows</span><span class="sxs-lookup"><span data-stu-id="96064-128">Windows</span></span>
<a id="windows" class="xliff"></a>

<span data-ttu-id="96064-129">Para o Portal da Empresa do Windows, os logs estão localizados em *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.</span><span class="sxs-lookup"><span data-stu-id="96064-129">For the Windows Company Portal, the logs are located in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.</span></span>
