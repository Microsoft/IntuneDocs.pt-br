---
title: "Definições de configuração de dispositivo compartilhado do Intune para iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para exibir informações na tela de bloqueio de dispositivos iOS."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 61bb1f8c7a9b6c92c128f32910f2ad8d390b6c64
ms.sourcegitcommit: c9b3a95bf529b6cb2a2bdacbc49127dfa0c233e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
# <span data-ttu-id="7678a-103">Definições de configuração de dispositivo compartilhado para exibir mensagens na tela de bloqueio do dispositivo iOS</span><span class="sxs-lookup"><span data-stu-id="7678a-103">Shared device configuration settings to display messages on the iOS device lock screen</span></span>
<a id="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7678a-104">As definições de configuração de dispositivo compartilhado permitem que você especifique um texto opcional que será exibido na janela de logon e na tela de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="7678a-104">Shared device configuration settings let you specify optional text displayed on the login window and lock screen.</span></span> <span data-ttu-id="7678a-105">Por exemplo, uma mensagem “Se perdido, devolver a” e Informações de Etiqueta do Ativo.</span><span class="sxs-lookup"><span data-stu-id="7678a-105">For example, you can enter an "If Lost, Return to" message and Asset Tag Information.</span></span> 

>[!IMPORTANT]
> <span data-ttu-id="7678a-106">Esse recurso tem suporte em dispositivos supervisionados executando o iOS 9.3 e posterior.</span><span class="sxs-lookup"><span data-stu-id="7678a-106">This capability is supported on supervised devices running iOS 9.3 and later.</span></span>

## <span data-ttu-id="7678a-107">Criar configurações de dispositivo compartilhado</span><span class="sxs-lookup"><span data-stu-id="7678a-107">Create shared device settings</span></span>
<a id="create-shared-device-settings" class="xliff"></a>

1. <span data-ttu-id="7678a-108">Na folha **Recursos do dispositivo**, escolha **Configuração do dispositivo compartilhado (somente supervisionado)**.</span><span class="sxs-lookup"><span data-stu-id="7678a-108">On the **Device features** blade, choose **Shared Device Configuration (supervised only)**.</span></span>
2. <span data-ttu-id="7678a-109">Na folha **Configuração de dispositivo compartilhado (somente supervisionado)**, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7678a-109">On the **Shared Device Configuration (supervised only)** blade, configure the following settings:</span></span>
    - <span data-ttu-id="7678a-110">**Informações de marca do ativo** - insira informações sobre a marca do ativo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7678a-110">**Asset tag information** - Enter information about the asset tag of the device.</span></span> <span data-ttu-id="7678a-111">Por exemplo: **Pertencente a Contoso Corp**. As informações inseridas são aplicadas a todos os dispositivos aos quais você atribui esse perfil.</span><span class="sxs-lookup"><span data-stu-id="7678a-111">For example: **Owned by Contoso Corp**. The information you enter is applied to all devices you assign this profile to.</span></span>
    - <span data-ttu-id="7678a-112">**Nota de rodapé de tela de bloqueio** – Se o dispositivo for perdido ou roubado, insira uma observação que pode ajudar a reaver o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7678a-112">**Lock screen footnote** - If the device is lost or stolen, enter a note that might help get the device returned.</span></span> <span data-ttu-id="7678a-113">Por exemplo: **Se encontrado, entre em contato com ‘número’**.</span><span class="sxs-lookup"><span data-stu-id="7678a-113">For example: **If found, call 'number'**.</span></span>
3. <span data-ttu-id="7678a-114">Quando terminar, escolha **OK** em até voltar à folha **Criar Perfil**, depois escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="7678a-114">When you are finished, choose **OK** until you return to the **Create Profile** blade, then choose **Create**.</span></span> 


## <span data-ttu-id="7678a-115">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7678a-115">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="7678a-116">Agora você pode atribuir o perfil de dispositivo aos grupos escolhidos.</span><span class="sxs-lookup"><span data-stu-id="7678a-116">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="7678a-117">Para ver mais detalhes, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="7678a-117">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
