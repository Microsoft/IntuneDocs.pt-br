---
title: "<span data-ttu-id=\"629b2-101\">Restrições de dispositivo do Intune para Windows 10 Team</span><span class=\"sxs-lookup\"><span data-stu-id=\"629b2-101\">Intune device restrictions for Windows 10 Team</span></span>"
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"629b2-102\">Saiba mais sobre as restrições de dispositivo disponíveis para dispositivos Windows 10 Team.</span><span class=\"sxs-lookup\"><span data-stu-id=\"629b2-102\">Learn about the device restrictions available for Windows 10 Team devices.\"</span></span>"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e7e6e5093b09d7a221083cd36a8d3e5ecbbb8c2
ms.sourcegitcommit: f100c943a635f5a08254ba7cf30f1aaebb7e810e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="629b2-103">Configurações de restrição de dispositivo Windows 10 Team no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="629b2-103">Windows 10 Team device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
- <span data-ttu-id="629b2-104">**Ativar tela quando alguém estiver no recinto** – Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.</span><span class="sxs-lookup"><span data-stu-id="629b2-104">**Wake screen when someone in room** - Allows the device to wake automatically when its sensor detects someone in the room.</span></span>
- <span data-ttu-id="629b2-105">**PIN para projeção sem fio** – Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="629b2-105">**PIN for wireless projection** - Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>
- <span data-ttu-id="629b2-106">**Projeção sem fio Miracast** – selecione essa opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.</span><span class="sxs-lookup"><span data-stu-id="629b2-106">**Miracast wireless projection** - If you want to let the Windows 10 Team device use Miracast enabled devices to project, select this option.</span></span>
- <span data-ttu-id="629b2-107">**Informações de reunião exibidas na tela de Boas-Vindas** – habilite essa opção para escolher as informações que serão exibidas no bloco Reuniões da tela de Boas-Vindas.</span><span class="sxs-lookup"><span data-stu-id="629b2-107">**Meeting information displayed on welcome screen** - Enable this option to choose the information that is displayed on the Meetings tile of the Welcome screen.</span></span> <span data-ttu-id="629b2-108">Você pode:</span><span class="sxs-lookup"><span data-stu-id="629b2-108">You can:</span></span>
    - <span data-ttu-id="629b2-109">**Mostrar somente organizador e hora**</span><span class="sxs-lookup"><span data-stu-id="629b2-109">**Show organizer and time only**</span></span>
    - <span data-ttu-id="629b2-110">**Mostrar organizador, hora e assunto (o assunto é oculto para reuniões privadas)**</span><span class="sxs-lookup"><span data-stu-id="629b2-110">**Show organizer, time, and subject (subject hidden for private meetings)**</span></span>
- <span data-ttu-id="629b2-111">**URL da imagem de fundo da tela de Boas-Vindas** – Habilite essa configuração para exibir uma tela de fundo personalizada na tela de **Boas-Vindas** dos dispositivos com Windows 10 Team da URL especificada.</span><span class="sxs-lookup"><span data-stu-id="629b2-111">**Welcome screen background image URL** - Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br><span data-ttu-id="629b2-112">A imagem deve estar no formato PNG e a URL deve começar com **https://**.</span><span class="sxs-lookup"><span data-stu-id="629b2-112">The image must be in PNG format and the URL must begin with **https://**.</span></span>
- <span data-ttu-id="629b2-113">**Janela de manutenção para atualizações** – Configura a o intervalo em que atualizações podem ocorrer no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="629b2-113">**Maintenance window for updates** - Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="629b2-114">Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).</span><span class="sxs-lookup"><span data-stu-id="629b2-114">You can configure the start time of the window and the duration (from 1-5 hours).</span></span>
- <span data-ttu-id="629b2-115">**Insights Operacionais do Azure** – O Insights Operacionais do Azure, que faz parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.</span><span class="sxs-lookup"><span data-stu-id="629b2-115">**Azure Operational Insights** - Azure Operational Insights, part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span><br><span data-ttu-id="629b2-116">Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="629b2-116">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="629b2-117">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="629b2-117">Next steps</span></span>

<span data-ttu-id="629b2-118">Use as informações em [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md) para salvar e atribuir o perfil a usuários e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="629b2-118">Use the information in [How to configure device restriction settings](device-restrictions-configure.md) to save, and assign the profile to users and devices.</span></span>
=======
- **Ativar tela quando alguém estiver no recinto** – Permite que o dispositivo seja ativado automaticamente quando o sensor detectar a alguém na sala.
- **PIN para projeção sem fio** – Especifica se você deve inserir um PIN antes de poder usar os recursos de projeção sem fio do dispositivo.
- **Projeção sem fio Miracast** – selecione essa opção se você quiser permitir que o dispositivo Windows 10 Team use dispositivos habilitados do Miracast para o projeto.
- **Informações de reunião exibidas na tela de Boas-Vindas** – habilite essa opção para escolher as informações que serão exibidas no bloco Reuniões da tela de Boas-Vindas. Você pode:
    - **Mostrar somente organizador e hora**
    - **Mostrar organizador, hora e assunto (o assunto é oculto para reuniões privadas)**
- **URL da imagem de fundo da tela de Boas-Vindas** – Habilite essa configuração para exibir uma tela de fundo personalizada na tela de **Boas-Vindas** dos dispositivos com Windows 10 Team da URL especificada.<br>A imagem deve estar no formato PNG e a URL deve começar com **https://**.
- **Janela de manutenção para atualizações** – Configura a o intervalo em que atualizações podem ocorrer no dispositivo. Você pode configurar a hora de início do intervalo e sua duração (de 1 a 5 horas).
- **Insights Operacionais do Azure** – O Insights Operacionais do Azure, que faz parte do pacote do Microsoft Operations Manager, coleta, armazena e analisa os dados de arquivo de log de dispositivos Windows 10 Team.<br>Para se conectar aos Insights Operacionais do Azure, você deve especificar uma **ID do Espaço de Trabalho** e uma **Chave do Espaço de Trabalho**.

## <a name="next-steps"></a>Próximas etapas

Use as informações em [Como definir as configurações de restrição de dispositivo](device-restrictions-configure.md) para salvar e atribuir o perfil a usuários e dispositivos.
>>>>>>> live
