---
title: Redefinir dispositivos Windows 10 com o Intune
titleSuffix: Intune on Azure
description: "Saiba como usar o Novo Início para redefinir computadores Windows 10 que executam o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 590472c0ab9f0103d72730b8ab01dc324c852a7a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="8c7af-103">Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune</span><span class="sxs-lookup"><span data-stu-id="8c7af-103">Use Fresh Start to reset Windows 10 devices with Intune</span></span>
<a id="use-fresh-start-to-reset-windows-10-devices-with-intune" class="xliff"></a>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="8c7af-104">A ação de dispositivo **Novo Início** remove todos os aplicativos que foram instalados em um computador Windows 10 que executa a Atualização para Criadores e, em seguida, atualiza automaticamente o computador para a versão mais recente do Windows.</span><span class="sxs-lookup"><span data-stu-id="8c7af-104">The **Fresh Start** device action removes any apps that were installed on a Windows 10 PC running the Creators Update, then automatically updates the PC to the latest version of Windows.</span></span>
<span data-ttu-id="8c7af-105">Isso pode ser usado para ajudar a remover aplicativos pré-instalados (OEM) que geralmente são fornecidos com um novo computador.</span><span class="sxs-lookup"><span data-stu-id="8c7af-105">This can be used to help remove pre-installed (OEM) apps that are often delivered with a new PC.</span></span> <span data-ttu-id="8c7af-106">Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada.</span><span class="sxs-lookup"><span data-stu-id="8c7af-106">You can configure if user data is retained when this device action is issued.</span></span> <span data-ttu-id="8c7af-107">Nesse caso, os aplicativos e as configurações são removidas, mas o conteúdo da pasta base dos usuários é mantido.</span><span class="sxs-lookup"><span data-stu-id="8c7af-107">In this case, apps and settings are removed, but the contents of the users Home folder are retained.</span></span>

1. <span data-ttu-id="8c7af-108">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="8c7af-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="8c7af-109">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="8c7af-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="8c7af-110">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8c7af-110">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="8c7af-111">Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="8c7af-111">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="8c7af-112">Na lista de dispositivos gerenciados, escolha um dispositivo do Windows 10 Desktop e, em seguida, escolha a ação remota de dispositivo **Novo Início**.</span><span class="sxs-lookup"><span data-stu-id="8c7af-112">From the list of devices you manage, choose a Windows 10 desktop device, and then choose the **Fresh Start** device remote action.</span></span>

<span data-ttu-id="8c7af-113">Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="8c7af-113">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>

