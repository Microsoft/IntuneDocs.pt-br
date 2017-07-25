---
title: Restaurar dispositivos iOS gerenciados pelo Intune por meio do backup
description: "Orientar usuários finais sobre como registrar novamente seus dispositivos após a restauração por meio do backup."
keywords: restaurar, gerenciado, iOS
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7fc99a944000a8d5ecfc09ebc2e956e7c0f201c9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="29156-104">Restaurar dispositivos iOS gerenciados pelo Intune por meio do backup</span><span class="sxs-lookup"><span data-stu-id="29156-104">Restore Intune managed iOS devices from backup</span></span>
<a id="restore-intune-managed-ios-devices-from-backup" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="29156-105">Haverá casos em que você ou seus usuários precisarão restaurar um dispositivo iOS por meio do backup, por exemplo, quando um usuário compra um novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29156-105">There will be cases when you or your users will need to restore an iOS device from a backup, such as when a user gets a new device.</span></span> <span data-ttu-id="29156-106">Este tópico explica as etapas adicionais que você precisará executar para configurar o gerenciamento do Intune depois de restaurar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29156-106">This topic explains additional steps that you might have to take to set up Intune management after restoring the device.</span></span>

## <span data-ttu-id="29156-107">Restaurar backups no mesmo dispositivo</span><span class="sxs-lookup"><span data-stu-id="29156-107">Restoring backups onto the same device</span></span>
<a id="restoring-backups-onto-the-same-device" class="xliff"></a>

<span data-ttu-id="29156-108">Se o backup está sendo restaurado no mesmo dispositivo, o estado do registro nesse dispositivo também será restaurado.</span><span class="sxs-lookup"><span data-stu-id="29156-108">If the backup is being restored onto the same device, then the enrollment state on that device will also be restored.</span></span> <span data-ttu-id="29156-109">Não é preciso fazer mais nada.</span><span class="sxs-lookup"><span data-stu-id="29156-109">There is no need for additional action.</span></span>

## <span data-ttu-id="29156-110">Restaurar backups em dispositivos diferentes</span><span class="sxs-lookup"><span data-stu-id="29156-110">Restoring backups onto different devices</span></span>
<a id="restoring-backups-onto-different-devices" class="xliff"></a>

<span data-ttu-id="29156-111">Se o backup está sendo restaurado em um dispositivo diferente, o estado do registro não será automaticamente restaurado no novo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="29156-111">If the backup is being restored onto a different device, then the enrollment state is not automatically restored on the new device.</span></span> <span data-ttu-id="29156-112">É necessário que os usuários sigam as etapas de registro padrão no aplicativo do Portal da Empresa na versão 2.1.22 ou posterior do aplicativo para [registrar seu dispositivo iOS no Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="29156-112">Users need to follow standard enrollment steps in the Company Portal app on app version 2.1.22 or later to [enroll their iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

> [!NOTE]
> <span data-ttu-id="29156-113">Se você estiver direcionando os usuários finais com políticas de acesso condicional, eles não poderão acessar o email corporativo até concluírem o novo registro.</span><span class="sxs-lookup"><span data-stu-id="29156-113">If you’re targeting your end users with conditional access policies, they will not be able to access corporate email until after they re-enroll.</span></span>

> [!TIP]
> <span data-ttu-id="29156-114">Um exemplo de comunicação para os usuários pode ser a seguinte: para se registrar no novo dispositivo, verifique se a versão do aplicativo do Portal da Empresa é a 2.1.22 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="29156-114">An example communication for your users could be as follows: To enroll on your new device, make sure that the Company Portal app is on version 2.1.22 or later.</span></span> <span data-ttu-id="29156-115">Para verificar a versão, abra o aplicativo do Portal da Empresa, toque no botão de Menu no canto superior direito e, em seguida, toque em Sobre.</span><span class="sxs-lookup"><span data-stu-id="29156-115">To check the version, open the Company Portal app, tap the Menu button in the upper right, and then tap About.</span></span> <span data-ttu-id="29156-116">Se você tiver uma versão anterior, saia do aplicativo do Portal da Empresa e abra a App Store.</span><span class="sxs-lookup"><span data-stu-id="29156-116">If you are on an earlier version, exit the Company Portal app and open the App Store.</span></span> <span data-ttu-id="29156-117">Toque no botão Atualizações no canto inferior direito; em seguida, toque no botão Atualizar ao lado do item do Portal da Empresa na lista.</span><span class="sxs-lookup"><span data-stu-id="29156-117">Tap the Updates button in the bottom right corner, then tap the Update button next to the Company Portal item in the list.</span></span> <span data-ttu-id="29156-118">Quando a atualização for concluída, inicie o aplicativo do Portal da Empresa e [registre seu dispositivo iOS no Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="29156-118">Once the update completes, launch the Company Portal app and [enroll your iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

## <span data-ttu-id="29156-119">Resolvendo problemas conhecidos com restaurações</span><span class="sxs-lookup"><span data-stu-id="29156-119">Resolving known issues with restores</span></span>
<a id="resolving-known-issues-with-restores" class="xliff"></a>

<span data-ttu-id="29156-120">Os usuários podem enfrentar algumas dificuldades se tiverem restaurado seu dispositivo e iniciado o aplicativo de Portal da Empresa quando ainda tinham o Portal da Empresa na versão 2.1.21 ou anteriores.</span><span class="sxs-lookup"><span data-stu-id="29156-120">Users may experience some difficulty if they restored their device and launched the Company Portal app when they still had Company Portal version 2.1.21 or earlier.</span></span> <span data-ttu-id="29156-121">Esses problemas podem ser solucionados executando as etapas adequadas à situação do usuário.</span><span class="sxs-lookup"><span data-stu-id="29156-121">These difficulties can be addressed by taking the appropriate steps for the user’s situation.</span></span>

### <span data-ttu-id="29156-122">Para usuários que usarão somente seu novo dispositivo</span><span class="sxs-lookup"><span data-stu-id="29156-122">For users who will only use their new device</span></span>
<a id="for-users-who-will-only-use-their-new-device" class="xliff"></a>
<span data-ttu-id="29156-123">Inicie o aplicativo de Portal da Empresa e cancele o registro selecionando o bloco do dispositivo atual e tocando no botão __Remover__.</span><span class="sxs-lookup"><span data-stu-id="29156-123">Launch the Company Portal app and unenroll by selecting the current device tile and tapping the __Remove__ button.</span></span> <span data-ttu-id="29156-124">Depois de remover, siga as etapas de registro padrão para [registrar um dispositivo iOS no Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="29156-124">After removing, follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

### <span data-ttu-id="29156-125">Para usuários que usarão tanto seus dispositivos novos quanto os antigos</span><span class="sxs-lookup"><span data-stu-id="29156-125">For users who will use both their old and new devices</span></span>
<a id="for-users-who-will-use-both-their-old-and-new-devices" class="xliff"></a>
<span data-ttu-id="29156-126">Limpe os cookies do Safari tocando em __Ajustes__ > __Safari__ > __Limpar Histórico e Dados do Site__.</span><span class="sxs-lookup"><span data-stu-id="29156-126">Clear cookies from Safari by tapping __Settings__ > __Safari__ > __Clear History and Website Data__.</span></span> <span data-ttu-id="29156-127">Após a limpar, desinstalar e reinstalar o aplicativo de Portal da Empresa, siga as etapas de registro padrão para [registrar um dispositivo iOS no Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="29156-127">After clearing,  uninstall and reinstall the Company Portal app, then follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>
