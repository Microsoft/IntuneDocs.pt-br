---
title: "Definições da política de configuração do Windows Team"
description: "Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6e0f0ea969ed78f2daf482438b056c8b4eb1a316
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="4b04d-103">Definições de política de configuração do Windows Team no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4b04d-103">Windows Team configuration policy settings in Microsoft Intune</span></span>
<a id="windows-team-configuration-policy-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4b04d-104">Use a **Política de configuração geral do Windows 10 Team** do Microsoft Intune para definir configurações para dispositivos Windows 10 Team registrados, como o Microsoft Surface Hub.</span><span class="sxs-lookup"><span data-stu-id="4b04d-104">Use the Microsoft Intune **Windows 10 Team general configuration policy** to configure settings for enrolled Windows 10 Team devices such as the Microsoft Surface Hub.</span></span>

|<span data-ttu-id="4b04d-105">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="4b04d-105">Setting name</span></span>|<span data-ttu-id="4b04d-106">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4b04d-106">Details</span></span>|
|----------------|-----------|
|<span data-ttu-id="4b04d-107">**Permitir que a tela seja ativada automaticamente quando alguém estiver na sala**</span><span class="sxs-lookup"><span data-stu-id="4b04d-107">**Allow screen to wake automatically when someone in the room**</span></span>|<span data-ttu-id="4b04d-108">Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.</span><span class="sxs-lookup"><span data-stu-id="4b04d-108">Allows the device to wake automatically when its sensor detects someone in the room.</span></span>|
|<span data-ttu-id="4b04d-109">**Exigir PIN para projeção sem fio**</span><span class="sxs-lookup"><span data-stu-id="4b04d-109">**Require PIN for wireless projection**</span></span>|<span data-ttu-id="4b04d-110">Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b04d-110">Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>|
|<span data-ttu-id="4b04d-111">**Configurar uma janela de manutenção para atualizações do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="4b04d-111">**Set a maintenance window for device updates**</span></span>|<span data-ttu-id="4b04d-112">Configura a o intervalo em que atualizações podem ocorrer no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4b04d-112">Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="4b04d-113">Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).</span><span class="sxs-lookup"><span data-stu-id="4b04d-113">You can configure the start time of the window and the duration (from 1-5 hours).</span></span>|
|<span data-ttu-id="4b04d-114">**Habilitar Azure Operational Insights**</span><span class="sxs-lookup"><span data-stu-id="4b04d-114">**Enable Azure Operational Insights**</span></span>|<span data-ttu-id="4b04d-115">Os Insights Operacionais do Azure, parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.</span><span class="sxs-lookup"><span data-stu-id="4b04d-115">Azure Operational Insights , part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span><br /><br /><span data-ttu-id="4b04d-116">Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="4b04d-116">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>|
|<span data-ttu-id="4b04d-117">**Habilitar projeção sem fio Miracast**</span><span class="sxs-lookup"><span data-stu-id="4b04d-117">**Enable Miracast wireless projection**</span></span>|<span data-ttu-id="4b04d-118">Habilite esta opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.</span><span class="sxs-lookup"><span data-stu-id="4b04d-118">Enable this option if you want to let the Windows 10 Team device use Miracast enabled devices to project.</span></span><br /><br /><span data-ttu-id="4b04d-119">Se você habilitar essa opção, em **Escolher Canal do Miracast**, selecione o canal do Miracast usado para o conteúdo do projeto.</span><span class="sxs-lookup"><span data-stu-id="4b04d-119">If you enable this option, from **Choose Miracast channel** select the Miracast channel used to project content.</span></span>|
|<span data-ttu-id="4b04d-120">**Escolher as informações da reunião exibidas na tela de boas-vindas**</span><span class="sxs-lookup"><span data-stu-id="4b04d-120">**Choose the meeting information displayed on the welcome screen**</span></span>|<span data-ttu-id="4b04d-121">Se você habilitar essa opção, você poderá escolher as informações que serão exibidas no bloco **Reuniões** da tela **Bem-vindo**.</span><span class="sxs-lookup"><span data-stu-id="4b04d-121">If you enable this option, you can choose the information that will be displayed on the **Meetings** tile of the **Welcome** screen.</span></span> <span data-ttu-id="4b04d-122">Você pode:</span><span class="sxs-lookup"><span data-stu-id="4b04d-122">You can:</span></span><br /><br /><span data-ttu-id="4b04d-123">-   **Mostrar somente organizador e hora**</span><span class="sxs-lookup"><span data-stu-id="4b04d-123">-   **Show organizer and time only**</span></span><br /><span data-ttu-id="4b04d-124">-   **Mostrar organizador, hora e entidade (a entidade é oculta para reuniões particulares)**</span><span class="sxs-lookup"><span data-stu-id="4b04d-124">-   **Show organizer, time and subject (subject hidden for private meetings)**</span></span>|
|<span data-ttu-id="4b04d-125">**URL da imagem de tela de fundo da tela de bloqueio**</span><span class="sxs-lookup"><span data-stu-id="4b04d-125">**Lockscreen background image URL**</span></span>|<span data-ttu-id="4b04d-126">Habilite essa configuração para exibir um plano de fundo personalizado na tela **Boas-Vindas** dos dispositivos com Windows 10 Team a partir da URL especificada.</span><span class="sxs-lookup"><span data-stu-id="4b04d-126">Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br /><br /><span data-ttu-id="4b04d-127">A imagem deve estar no formato PNG e a URL deve começar com **https://**.</span><span class="sxs-lookup"><span data-stu-id="4b04d-127">The image must be in PNG format and the URL must begin with **https://**.</span></span>|


### <span data-ttu-id="4b04d-128">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4b04d-128">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="4b04d-129">Gerenciar configurações e recursos em seus dispositivos com políticas do Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4b04d-129">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

