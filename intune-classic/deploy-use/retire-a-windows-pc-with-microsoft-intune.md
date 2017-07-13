---
title: Desativar um computador Windows
description: Como desativar um computador Windows gerenciado pelo Intune.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 09bba1ea199b51fdd1503cb1f0a3beeb97b6aa47
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1d4eb-103">Desativar um computador Windows</span><span class="sxs-lookup"><span data-stu-id="1d4eb-103">Retire a Windows PC</span></span>
<a id="retire-a-windows-pc" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1d4eb-104">Use as etapas a seguir para desativar áreas de trabalho gerenciadas como computadores executando o cliente de software do Intune nelas.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-104">Use the following steps to retire desktops that you are managing as PCs by running the Intune software client on them.</span></span> <span data-ttu-id="1d4eb-105">Ao desativar um computador, ele é removido do gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-105">When you retire a PC, it removes it from Intune management.</span></span> <span data-ttu-id="1d4eb-106">Não é possível redefinir um computador do Intune para as configurações originais de fábrica.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-106">You cannot factory reset a PC from Intune to set it back to its original factory settings.</span></span>

1.  <span data-ttu-id="1d4eb-107">No [console de administração do Microsoft Intune](https://manage.microsoft.com/), escolha **Grupos** &gt; **Todos os Dispositivos** (ou outro grupo que contém o computador que você deseja desativar).</span><span class="sxs-lookup"><span data-stu-id="1d4eb-107">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to retire).</span></span>

2.  <span data-ttu-id="1d4eb-108">Selecione os dispositivos que deseja desativar e escolha **Desativar/Apagar**.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-108">Select the devices you want to retire, and then choose **Retire/Wipe**.</span></span>

<span data-ttu-id="1d4eb-109">Para registrar um computador novamente no Intune, reinstale o cliente de software no computador usando as diretrizes em [Instalar o cliente de computador Windows com o Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="1d4eb-109">To re-enroll a PC into Intune, reinstall the software client on the PC using guidance in [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).</span></span>

<span data-ttu-id="1d4eb-110">Se um computador não conseguir se conectar ao Intune, será exibida uma mensagem no espaço de trabalho **Painel**.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-110">If a PC cannot connect to Intune, a message is displayed in the **Dashboard** workspace.</span></span>

<span data-ttu-id="1d4eb-111">Ao desativar um computador:</span><span class="sxs-lookup"><span data-stu-id="1d4eb-111">When you retire a PC:</span></span>

-   <span data-ttu-id="1d4eb-112">Ele é removido do inventário e gerenciamento do Intune e a licença associada ao computador é disponibilizada para reutilização.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-112">It is removed from the Intune management and inventory, and the license associated with the PC is made available for re-use.</span></span> <span data-ttu-id="1d4eb-113">O recurso Desativar/Apagar remove o cliente de software do Intune, mas não remove aplicativos nem dados do computador.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-113">Retire/Wipe removes the Intune software client but does not remove apps or data from the PC.</span></span> <span data-ttu-id="1d4eb-114">Essa desativação não executa um apagamento completo no computador.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-114">This retirement does not perform a full wipe on the PC.</span></span>

-   <span data-ttu-id="1d4eb-115">Seu status não é mais exibido no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-115">Its status no longer displays in the Intune console.</span></span>

-   <span data-ttu-id="1d4eb-116">O Intune remove o cliente de software do computador.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-116">Intune removes the software client from the PC.</span></span> <span data-ttu-id="1d4eb-117">Se o computador não estiver conectado ao serviço Intune, o cliente de software será removido na próxima conexão.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-117">If the PC is not connected to the Intune service, the software client will be removed next time it connects.</span></span>

-   <span data-ttu-id="1d4eb-118">O Microsoft Intune Endpoint Protection é removido do computador.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-118">Microsoft Intune Endpoint Protection is removed from the PC.</span></span> <span data-ttu-id="1d4eb-119">Se o computador tiver outro aplicativo de ponto de extremidade instalado e ele estiver desabilitado, o aplicativo poderá ser habilitado novamente depois que o Microsoft Intune Endpoint Protection for removido, a fim de garantir que o computador está protegido.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-119">If the PC has another endpoint application installed and it is disabled, that application can be re-enabled after Microsoft Intune Endpoint Protection is removed to ensure that your PC are protected.</span></span>

-   <span data-ttu-id="1d4eb-120">Todas as políticas são removidas do computador e os valores definidos pela política serão alterados.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-120">Any policies are removed from the PC and the values that were set by the policy will be changed.</span></span>

-   <span data-ttu-id="1d4eb-121">O computador não receberá mais atualizações de software nem atualizações de definições de malware do serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-121">The PC no longer receives software updates or malware definition updates from the Intune service.</span></span>

-   <span data-ttu-id="1d4eb-122">Dependendo de como estiverem configurados, os computadores desativados poderão continuar recebendo atualizações usando o Windows Server Update Services, Windows Update ou Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-122">Depending on how they are configured, retired PC can continue to receive updates by using Windows Server Update Services, Windows Update, or Microsoft Update.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1d4eb-123">Se o software cliente tiver sido instalado com o uso de um GPO (Objeto de Política de Grupo), antes de remover o software cliente você deve remover o GPO para evitar que o software seja reinstalado.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-123">If the client software was installed by using a Group Policy Object (GPO), you must remove the Group Policy Object (GPO) before you can remove the client software to prevent the software from being reinstalled.</span></span>

    <span data-ttu-id="1d4eb-124">Se a desinstalação do cliente Endpoint Protection falhar, leia [Troubleshoot Endpoint Protection in Microsoft Intune](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) (Solucionar problemas do Endpoint Protection no Intune) para obter mais ajuda.</span><span class="sxs-lookup"><span data-stu-id="1d4eb-124">If the Endpoint Protection client fails to uninstall, read [Troubleshoot Endpoint Protection](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) for more help.</span></span>

### <span data-ttu-id="1d4eb-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1d4eb-125">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="1d4eb-126">Tarefas comuns de gerenciamento de computadores Windows com o cliente de software do Intune</span><span class="sxs-lookup"><span data-stu-id="1d4eb-126">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)