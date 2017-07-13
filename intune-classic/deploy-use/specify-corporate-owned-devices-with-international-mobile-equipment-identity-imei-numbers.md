---
title: "Especificar números IMEI"
description: "O Microsoft Intune permite aos administradores importar números IMEI para plataformas de dispositivos móveis para ajudar a identificar dispositivos móveis corporativos"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d1ecc65dac893740b152aa743e6b32c5de5a3ec9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="6e062-103">Especificar dispositivos corporativos com números IMEI (Identidade de Equipamentos Móveis Internacional)</span><span class="sxs-lookup"><span data-stu-id="6e062-103">Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers</span></span>
<a id="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6e062-104">O Microsoft Intune permite aos administradores importar números IMEI (identidade de equipamentos móveis internacionais) para plataformas de dispositivos móveis usando números IMEI para ajudar a identificar dispositivos móveis corporativos.</span><span class="sxs-lookup"><span data-stu-id="6e062-104">Microsoft Intune lets admins import international mobile equipment identity (IMEI) numbers for mobile device platforms by using IMEI numbers to help identify corporate-owned mobile devices.</span></span> <span data-ttu-id="6e062-105">Depois que os dispositivos forem registrados no Intune, você poderá ver os dispositivos que importaram números IMEI em **Grupos** > **Visão Geral** > **Todos os Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6e062-105">After devices are enrolled in Intune, you can see devices that have imported IMEI numbers under **Groups** > **Overview** > **All Devices**.</span></span> <span data-ttu-id="6e062-106">**Grupo de dispositivos** exibe os dispositivos que importaram números IMEI como **Corporativo** na coluna **Propriedade**.</span><span class="sxs-lookup"><span data-stu-id="6e062-106">**Device group** lists devices that have imported IMEI numbers as **Corporate** in the **Ownership** column.</span></span>

1. <span data-ttu-id="6e062-107">No [Console de administração do Microsoft Intune](https://manage.microsoft.com), escolha **Grupos** &gt; **Todos os Dispositivos** &gt; **Todos os Dispositivos da Pré-registrados da Empresa** &gt; **Por IMEI (todas as plataformas)** e escolha **Adicionar Dispositivos…**.</span><span class="sxs-lookup"><span data-stu-id="6e062-107">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate Pre-enrolled Devices** &gt; **By IMEI (All platforms)**, and then choose **Add devices…**.</span></span> <span data-ttu-id="6e062-108">Você pode adicionar dispositivos de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="6e062-108">You can add devices in two ways:</span></span>

    -   <span data-ttu-id="6e062-109">**Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="6e062-109">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span> <span data-ttu-id="6e062-110">O campo de detalhes é limitado a 128 caracteres.</span><span class="sxs-lookup"><span data-stu-id="6e062-110">The details field is limited to 128 characters.</span></span> 

        |||
        |-|-|
        |<span data-ttu-id="6e062-111">&lt;IMEI nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="6e062-111">&lt;IMEI #1&gt;</span></span>|<span data-ttu-id="6e062-112">&lt;Detalhes do dispositivo nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="6e062-112">&lt;Device #1 Details&gt;</span></span>|
        |<span data-ttu-id="6e062-113">&lt;IMEI nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="6e062-113">&lt;IMEI #2&gt;</span></span>|<span data-ttu-id="6e062-114">&lt;Detalhes do dispositivo nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="6e062-114">&lt;Device #2 Details&gt;</span></span>|
        <span data-ttu-id="6e062-115">Quando visualizado em um editor de texto, esse arquivo .csv aparece como:</span><span class="sxs-lookup"><span data-stu-id="6e062-115">This .csv file when viewed in a text editor appears as:</span></span>

        ```
        01234567890123,device details
        02234567890123,device details
        ```

    -   <span data-ttu-id="6e062-116">**Adicionar manualmente os detalhes do dispositivo** – insira o número IMEI e detalhes de até 15 dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6e062-116">**Manually add device details** - Enter the IMEI number and device details of up to 15 devices.</span></span>

   <span data-ttu-id="6e062-117">O campo *Detalhes* é para uso administrativo.</span><span class="sxs-lookup"><span data-stu-id="6e062-117">The *Details* field is for administrative use.</span></span> <span data-ttu-id="6e062-118">É possível especificar detalhes para ajudar a identificar o dispositivo na lista de dispositivos corporativos listados por ID de hardware.</span><span class="sxs-lookup"><span data-stu-id="6e062-118">You can specify details to help identify the device in the list of Corporate-owned devices listed by hardware ID.</span></span> <span data-ttu-id="6e062-119">Essas informações não são enviadas para o dispositivo, mas serão exibidas no console do Intune.</span><span class="sxs-lookup"><span data-stu-id="6e062-119">This information is not sent to the device, but it will appear in the Intune console.</span></span>

2.   <span data-ttu-id="6e062-120">Escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6e062-120">Choose **Next**.</span></span>
3.  <span data-ttu-id="6e062-121">No painel **Examinar Dispositivos**, você pode confirmar os números IMEI dos dispositivos importados.</span><span class="sxs-lookup"><span data-stu-id="6e062-121">On the **Review Devices** pane, you can confirm the imported device IMEI numbers.</span></span> <span data-ttu-id="6e062-122">Você também pode decidir se deseja substituir **Detalhes** por números IMEI que estão sendo importados novamente.</span><span class="sxs-lookup"><span data-stu-id="6e062-122">You can also decide whether to overwrite the **Details** for IMEI numbers that are being imported again.</span></span> <span data-ttu-id="6e062-123">Você pode desmarcar a caixa de seleção **Substituir** para preservar os detalhes atuais.</span><span class="sxs-lookup"><span data-stu-id="6e062-123">You can uncheck the **Overwrite** box to preserve the Current details.</span></span> <span data-ttu-id="6e062-124">Escolha **Concluir** para importar os números IMEI.</span><span class="sxs-lookup"><span data-stu-id="6e062-124">Choose **Finish** to import the IMEI numbers.</span></span>
4.  <span data-ttu-id="6e062-125">Os números IMEI importados e descrições são adicionados à lista **Por IMEI (todas as plataformas)**.</span><span class="sxs-lookup"><span data-stu-id="6e062-125">The imported IMEI numbers and descriptions are added to the **By IMEI (All platforms)** list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e062-126">Se você estiver importando números IMEI para dispositivos Android, lembre-se de que alguns dispositivos Android podem ter vários números IMEI.</span><span class="sxs-lookup"><span data-stu-id="6e062-126">If you are importing IMEI numbers for Android devices, be aware that some Android devices can have multiple IMEI numbers.</span></span> <span data-ttu-id="6e062-127">Se você importar um número IMEI, mas não for o IMEI relatado para o Intune pelo dispositivo, o dispositivo será classificado como um dispositivo pessoal em vez de um dispositivo da empresa.</span><span class="sxs-lookup"><span data-stu-id="6e062-127">If you import an IMEI number but it is not the IMEI reported to Intune by the device, the device will be classifed as a personal device instead of a company-owned device.</span></span>

<span data-ttu-id="6e062-128">Quando o dispositivo com esse número IMEI é registrado no Intune, normalmente quando um usuário instala o aplicativo Portal da Empresa e conclui o processo de registro, o dispositivo é marcado como corporativo e aparece como registrado no grupo **Dispositivos IMEI**.</span><span class="sxs-lookup"><span data-stu-id="6e062-128">When a device that has IMEI number enrolls in Intune, usually when a user installs the Company Portal app and completes the enrollment process, the device will be tagged as corporate-owned and appear as enrolled in the **IMEI Devices** group.</span></span>

>[!NOTE]
> <span data-ttu-id="6e062-129">Quando sua organização tiver migrado para o novo Portal do Azure em um futuro próximo, você verá uma alteração nesse recurso.</span><span class="sxs-lookup"><span data-stu-id="6e062-129">When your organization is migrated to the new Azure portal in the near future, you will see a change to this feature.</span></span> <span data-ttu-id="6e062-130">No console do administrador do Intune existente, os administradores podem aceitar detalhes associados de um CSV carregado e substituir os detalhes existentes para identificadores de hardware individuais.</span><span class="sxs-lookup"><span data-stu-id="6e062-130">In the existing Intune administrator console, admins can accept associated details from an uploaded CSV and overwrite the existing details for individual hardware identifiers.</span></span> <span data-ttu-id="6e062-131">No novo Portal do Azure, você poderá substituir automaticamente os detalhes para todos os identificadores de hardware ou ignorar todos os novos detalhes para identificadores existentes.</span><span class="sxs-lookup"><span data-stu-id="6e062-131">In the new Azure portal, you’ll be able to automatically overwrite the details for all hardware identifiers or to ignore all new details for existing identifiers.</span></span>

<span data-ttu-id="6e062-132">Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span><span class="sxs-lookup"><span data-stu-id="6e062-132">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>
