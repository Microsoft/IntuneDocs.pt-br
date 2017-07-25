---
title: Monitorar a conformidade de acesso condicional para o Exchange local e o Exchange Online
titleSuffix: Intune on Azure
description: Monitorar a conformidade de acesso condicional para o Exchange local e o Exchange Online por meio do Portal do Azure no Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2ec9bcc605486258203f49f9f7631bd2a04cdf22
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="22795-103">Monitorar a conformidade de acesso condicional do Exchange Local e do Exchange Online no Intune</span><span class="sxs-lookup"><span data-stu-id="22795-103">Monitor conditional access compliance for on-premises Exchange and Exchange Online in Intune</span></span>
<a id="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune" class="xliff"></a>

<span data-ttu-id="22795-104">A partir da versão 1704 do Intune, os administradores podem ver informações de relatório relacionadas aos registros de dispositivos do Exchange ActiveSync que estão sincronizados com o Intune através do Exchange Connector local ou o Service to Service Connector do Intune (conector do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="22795-104">Beginning with Intune 1704 release, admins can see reporting information related to Exchange ActiveSync device records that are synchronized with Intune through either the on-premises Exchange Connector or the Intune service-to-service connector (Exchange Online connector).</span></span> <span data-ttu-id="22795-105">Os relatórios de conformidade de acesso condicional fornecem um resumo dos dispositivos com estados de sincronização diferentes:</span><span class="sxs-lookup"><span data-stu-id="22795-105">The conditional access compliance reporting provides a summary of devices with different synchronization states:</span></span>

-   <span data-ttu-id="22795-106">**Permitir**</span><span class="sxs-lookup"><span data-stu-id="22795-106">**Allow**</span></span>

-   <span data-ttu-id="22795-107">**Bloquear**</span><span class="sxs-lookup"><span data-stu-id="22795-107">**Block**</span></span>

-   <span data-ttu-id="22795-108">**Quarentena**</span><span class="sxs-lookup"><span data-stu-id="22795-108">**Quarantine**</span></span>

## <span data-ttu-id="22795-109">Para monitorar a conformidade de acesso condicional</span><span class="sxs-lookup"><span data-stu-id="22795-109">To monitor conditional access compliance</span></span>
<a id="to-monitor-conditional-access-compliance" class="xliff"></a>

1.  <span data-ttu-id="22795-110">Vá para o [Portal do Azure](https://portal.azure.com/) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="22795-110">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="22795-111">Quando entrar com êxito, você verá o **Painel do Azure**.</span><span class="sxs-lookup"><span data-stu-id="22795-111">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

3.  <span data-ttu-id="22795-112">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="22795-112">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4.  <span data-ttu-id="22795-113">Escolha **Intune** e você verá o **Painel do Intune**.</span><span class="sxs-lookup"><span data-stu-id="22795-113">Choose **Intune**, you see the **Intune Dashboard**.</span></span>

5.  <span data-ttu-id="22795-114">Escolha **Acesso Condicional**, em seguida, escolha **Visão Geral**.</span><span class="sxs-lookup"><span data-stu-id="22795-114">Choose **Conditional Access**, then choose **Overview**.</span></span>

6.  <span data-ttu-id="22795-115">Escolha uma das três áreas (**Bloqueado**, **Quarentena** ou **Permitido**) no gráfico para exibir o relatório de conformidade de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="22795-115">Choose one of the three areas (**Blocked**, **Quarantine** or **Allowed**) on the chart to view your conditional access compliance reporting.</span></span>

    ![Painel de acesso condicional](./media/CA-reporting-intune-1.png)

<span data-ttu-id="22795-117">Depois de escolher uma das três áreas, você poderá ver mais detalhes sobre os dispositivos que estão sendo permitidos, bloqueados ou colocados em quarentena.</span><span class="sxs-lookup"><span data-stu-id="22795-117">Once you choose one of three areas, you can see more details about devices being allowed, blocked or quarantined.</span></span>

<span data-ttu-id="22795-118">Você também poderá analisar em dispositivos específicos para ver mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="22795-118">You can also drill down in specific devices to see more details.</span></span> <span data-ttu-id="22795-119">Por exemplo, o dispositivo escolhido na imagem abaixo está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="22795-119">For example, the device chosen on the image below is blocked.</span></span> <span data-ttu-id="22795-120">O Intune dá a opção de remover dados corporativos da folha de relatórios de conformidade de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="22795-120">Intune gives you the option of removing corporate data from the conditional access compliance report blade.</span></span>

![Relatório de detalhes do dispositivo de acesso condicional](./media/CA-reporting-intune-3.png)

<span data-ttu-id="22795-122">Na folha detalhes do dispositivo, você pode ver mais informações:</span><span class="sxs-lookup"><span data-stu-id="22795-122">At the device details blade, you can see more information:</span></span>

-   <span data-ttu-id="22795-123">**Visão geral:** você pode ver as propriedades do dispositivo como: versão do sistema operacional, modelo do dispositivo, propriedade, número de série, fabricante do dispositivo, número de telefone e última vez que o dispositivo fez check-in.</span><span class="sxs-lookup"><span data-stu-id="22795-123">**Overview:** You can see device properties like: OS version, device model, ownership, serial number, device manufacturer, phone number and last time the device checked in.</span></span>

-   <span data-ttu-id="22795-124">**Propriedades:** você pode definir a propriedade do dispositivo (pessoal ou corporativa).</span><span class="sxs-lookup"><span data-stu-id="22795-124">**Properties:** You can set the device ownership (Personal or Corporate).</span></span>

-   <span data-ttu-id="22795-125">**Hardware:** fornece as informações que você vê na Visão Geral e também os detalhes de armazenamento (espaço total e livre), compartimento do sistema, detalhes da rede, serviço de rede e mais detalhes de bloqueio de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="22795-125">**Hardware:** It provides the information you see on the Overview, and also storage details (total space and free space), system enclosure, network details, network service, and more conditional access blocking details.</span></span>

-   <span data-ttu-id="22795-126">**Aplicativos descobertos:** mostra todos os aplicativos instalados no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22795-126">**Discovered Apps:** It shows all applications installed at your device.</span></span> <span data-ttu-id="22795-127">Você também pode exportar a lista de aplicativos instalados para o formato .CSV.</span><span class="sxs-lookup"><span data-stu-id="22795-127">You can also export the list of installed apps to .CSV format.</span></span>

-   <span data-ttu-id="22795-128">**Conformidade:** mostra todos os detalhes da política de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22795-128">**Compliance:** It shows all device compliance policy details.</span></span>

-   <span data-ttu-id="22795-129">**Configuração do dispositivo:** mostra todos os detalhes de configuração do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22795-129">**Device Configuration:** It shows all device configuration details.</span></span>

-   <span data-ttu-id="22795-130">**Acesso do Exchange:** aqui você pode aprender mais sobre o estado do dispositivo após a aplicação de políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="22795-130">**Exchange Access:** Here you can learn more about the device state after applying conditional access policies.</span></span>
