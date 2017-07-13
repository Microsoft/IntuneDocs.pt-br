---
title: "Restrições de dispositivo do Intune para Windows 10 Team"
titleSuffix: Intune on Azure
description: "Saiba mais sobre as restrições de dispositivo disponíveis para dispositivos Windows 10 Team."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7a5c3eaf3d2b1fc4383282473352124c793b666f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f4010-103">Configurações de restrição de dispositivo Windows 10 Team no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f4010-103">Windows 10 Team device restriction settings in Microsoft Intune</span></span>
<a id="windows-10-team-device-restriction-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

- <span data-ttu-id="f4010-104">**Ativar tela quando alguém estiver no recinto** – Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.</span><span class="sxs-lookup"><span data-stu-id="f4010-104">**Wake screen when someone in room** - Allows the device to wake automatically when its sensor detects someone in the room.</span></span>
- <span data-ttu-id="f4010-105">**PIN para projeção sem fio** – Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4010-105">**PIN for wireless projection** - Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>
- <span data-ttu-id="f4010-106">**Projeção sem fio Miracast** – Habilite esta opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.</span><span class="sxs-lookup"><span data-stu-id="f4010-106">**Miracast wireless projection** - Enable this option if you want to let the Windows 10 Team device use Miracast enabled devices to project.</span></span>
- <span data-ttu-id="f4010-107">**Informações de reunião exibidas na tela de Boas-Vindas** – Habilite essa opção para escolher as informações que serão exibidas no bloco Reuniões da tela de Boas-Vindas.</span><span class="sxs-lookup"><span data-stu-id="f4010-107">**Meeting information displayed on welcome screen** - Enable this option to choose the information that will be displayed on the Meetings tile of the Welcome screen.</span></span> <span data-ttu-id="f4010-108">Você pode:</span><span class="sxs-lookup"><span data-stu-id="f4010-108">You can:</span></span>
    - <span data-ttu-id="f4010-109">**Mostrar somente organizador e hora**</span><span class="sxs-lookup"><span data-stu-id="f4010-109">**Show organizer and time only**</span></span>
    - <span data-ttu-id="f4010-110">**Mostrar organizador, hora e assunto (o assunto é oculto para reuniões privadas)**</span><span class="sxs-lookup"><span data-stu-id="f4010-110">**Show organizer, time and subject (subject hidden for private meetings)**</span></span>
- <span data-ttu-id="f4010-111">**URL da imagem de fundo da tela de Boas-Vindas** – Habilite essa configuração para exibir uma tela de fundo personalizada na tela de **Boas-Vindas** dos dispositivos com Windows 10 Team da URL especificada.</span><span class="sxs-lookup"><span data-stu-id="f4010-111">**Welcome screen background image URL** - Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br><span data-ttu-id="f4010-112">A imagem deve estar no formato PNG e a URL deve começar com **https://**.</span><span class="sxs-lookup"><span data-stu-id="f4010-112">The image must be in PNG format and the URL must begin with **https://**.</span></span>
- <span data-ttu-id="f4010-113">**Janela de manutenção para atualizações** – Configura a o intervalo em que atualizações podem ocorrer no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4010-113">**Maintenance window for updates** - Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="f4010-114">Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).</span><span class="sxs-lookup"><span data-stu-id="f4010-114">You can configure the start time of the window and the duration (from 1-5 hours).</span></span>
- <span data-ttu-id="f4010-115">**Insights Operacionais do Azure** – O Insights Operacionais do Azure, que faz parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.</span><span class="sxs-lookup"><span data-stu-id="f4010-115">**Azure Operational Insights** - Azure Operational Insights , part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span><br><span data-ttu-id="f4010-116">Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f4010-116">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>
