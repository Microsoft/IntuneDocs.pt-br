---
title: Adicionar identificadores IMEI ao Intune
titleSuffix: Intune on Azure
description: "Saiba como adicionar identificadores corporativos (números IMEI) ao Microsoft Intune. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 57ab3b79ad53a4b195fac426d211a114f054602f
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="b992d-104">Adicionar identificadores corporativos</span><span class="sxs-lookup"><span data-stu-id="b992d-104">Add corporate identifiers</span></span>
<a id="add-corporate-identifiers" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b992d-105">Como administrador de TI, você pode criar e importar um arquivo de valores separados por vírgulas (.csv) que lista os números IMEI (identificador de equipamento móvel internacional) ou de série para identificar dispositivos corporativos.</span><span class="sxs-lookup"><span data-stu-id="b992d-105">As an IT admin, you can create and import a comma-separated value (.csv) file that lists international mobile equipment identifier (IMEI) numbers or serial numbers to identify corporate-owned devices.</span></span> <span data-ttu-id="b992d-106">Somente é possível declarar o número de série para dispositivos iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="b992d-106">You can only declare serial number for iOS and Android devices.</span></span> <span data-ttu-id="b992d-107">Cada número IMEI ou de série pode ter detalhes especificados na lista para fins administrativos.</span><span class="sxs-lookup"><span data-stu-id="b992d-107">Each IMEI or serial number can have details specified in the list for administrative purposes.</span></span>

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

<span data-ttu-id="b992d-108">[Saiba como localizar o número de série de um dispositivo Apple](https://support.apple.com/HT204308).</span><span class="sxs-lookup"><span data-stu-id="b992d-108">[Learn how to find an Apple device serial number](https://support.apple.com/HT204308).</span></span>
<span data-ttu-id="b992d-109">[Saiba como localizar o número de série do seu dispositivo Android](https://support.google.com/store/answer/3333000).</span><span class="sxs-lookup"><span data-stu-id="b992d-109">[Learn how to find your Android device serial number](https://support.google.com/store/answer/3333000).</span></span>

## <span data-ttu-id="b992d-110">Adicionar identificadores corporativos</span><span class="sxs-lookup"><span data-stu-id="b992d-110">Add corporate identifiers</span></span>
<a id="add-corporate-identifiers" class="xliff"></a>
<span data-ttu-id="b992d-111">Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="b992d-111">To create the list, create a two-column, comma-separated value (.csv) list without a header.</span></span> <span data-ttu-id="b992d-112">Adicione os números de série ou IMEI à coluna esquerda e os detalhes à coluna direita.</span><span class="sxs-lookup"><span data-stu-id="b992d-112">Add the IMEI or serial numbers in the left column, and the details in the right column.</span></span> <span data-ttu-id="b992d-113">Apenas um tipo de ID, IMEI ou número de série, pode ser importado para o mesmo arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="b992d-113">Only one type of ID, IMEI or serial number, can be imported in a single .csv file.</span></span> <span data-ttu-id="b992d-114">Os detalhes limitam-se a 128 caracteres e são exclusivamente para uso administrativo.</span><span class="sxs-lookup"><span data-stu-id="b992d-114">Details are limited to 128 characters and are for administrative use only.</span></span> <span data-ttu-id="b992d-115">O dispositivo não exibe detalhes.</span><span class="sxs-lookup"><span data-stu-id="b992d-115">Details aren't displayed on the device.</span></span> <span data-ttu-id="b992d-116">O limite atual é de 500 linhas por arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="b992d-116">The current limit is 500 rows per .csv file.</span></span>

<span data-ttu-id="b992d-117">**Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="b992d-117">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span>

|||
|-|-|
|<span data-ttu-id="b992d-118">&lt;ID nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="b992d-118">&lt;ID #1&gt;</span></span>|<span data-ttu-id="b992d-119">&lt;Detalhes do dispositivo nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="b992d-119">&lt;Device #1 Details&gt;</span></span>|
|<span data-ttu-id="b992d-120">&lt;ID nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="b992d-120">&lt;ID #2&gt;</span></span>|<span data-ttu-id="b992d-121">&lt;Detalhes do dispositivo nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="b992d-121">&lt;Device #2 Details&gt;</span></span>|

<span data-ttu-id="b992d-122">Quando visualizado em um editor de texto, esse arquivo .csv aparece como:</span><span class="sxs-lookup"><span data-stu-id="b992d-122">This .csv file when viewed in a text editor appears as:</span></span>

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> <span data-ttu-id="b992d-123">Alguns dispositivos com Android possuem vários números IMEI.</span><span class="sxs-lookup"><span data-stu-id="b992d-123">Some Android devices have multiple IMEI numbers.</span></span> <span data-ttu-id="b992d-124">O Intune lê somente um número IMEI por dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="b992d-124">Intune only reads one IMEI number per enrolled device.</span></span> <span data-ttu-id="b992d-125">Se você importar um número IMEI, mas não for o IMEI armazenado pelo Intune, o dispositivo será classificado como um dispositivo pessoal em vez de um dispositivo da empresa.</span><span class="sxs-lookup"><span data-stu-id="b992d-125">If you import an IMEI number but it is not the IMEI inventoried by Intune, the device will be classified as a personal device instead of a company-owned device.</span></span> <span data-ttu-id="b992d-126">Se você importar vários números IMEI para um dispositivo, os números não armazenados exibirão **Desconhecido** como o status do registro.</span><span class="sxs-lookup"><span data-stu-id="b992d-126">If you import multiple IMEI numbers for a device, uninventoried numbers will display **Unknown** for enrollment status.</span></span>

<span data-ttu-id="b992d-127">**Para adicionar uma lista .csv de identificadores corporativos**</span><span class="sxs-lookup"><span data-stu-id="b992d-127">**To add a .csv list of corporate identifiers**</span></span>

1. <span data-ttu-id="b992d-128">No portal do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b992d-128">In the Intune portal, choose **Device enrollment** > **Enrollment Restrictions**, choose **Corporate Device Identifiers**, and then click **Add**.</span></span>

 ![Captura de tela de espaço de trabalho do identificador de dispositivo corporativo com o botão Adicionar realçado.](./media/add-corp-id.png)

2. <span data-ttu-id="b992d-130">Na folha **Adicionar Identificadores**, especifique o tipo de identificador, **IMEI** ou **Número de Série**.</span><span class="sxs-lookup"><span data-stu-id="b992d-130">In the **Add Identifiers** blade, specify the identifier type, **IMEI** or **Serial**.</span></span> <span data-ttu-id="b992d-131">Você pode especificar se números importados anteriormente devem **substituir os detalhes para os identificadores existentes**.</span><span class="sxs-lookup"><span data-stu-id="b992d-131">You can specify whether previously imported numbers should **Overwrite details for existing identifiers**.</span></span>

3. <span data-ttu-id="b992d-132">Clique no ícone de pasta e especifique o caminho para a lista que quer importar.</span><span class="sxs-lookup"><span data-stu-id="b992d-132">Click the folder icon and specify the path to the list you want to import.</span></span> <span data-ttu-id="b992d-133">Navegue para o arquivo .csv e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b992d-133">Navigate to the .csv file, and select **Add**.</span></span> <span data-ttu-id="b992d-134">Clique em **Atualizar** para ver os novos identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b992d-134">You can click **Refresh** to see new device identifiers.</span></span>

<span data-ttu-id="b992d-135">Depois de importados, esses dispositivos podem ou não ser registrados, e têm um estado de **Registrado** ou**Não contatado**.</span><span class="sxs-lookup"><span data-stu-id="b992d-135">Once imported, these devices might or might not be enrolled, and can have a state of either **Enrolled** or **Not contacted**.</span></span> <span data-ttu-id="b992d-136">**Não contatado** significa que o dispositivo nunca se comunicou com o serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="b992d-136">**Not contacted** means that the device has never communicated in with the Intune service.</span></span>

## <span data-ttu-id="b992d-137">Excluir identificadores corporativos</span><span class="sxs-lookup"><span data-stu-id="b992d-137">Delete  corporate identifiers</span></span>
<a id="delete--corporate-identifiers" class="xliff"></a>

1. <span data-ttu-id="b992d-138">No portal do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b992d-138">In the Intune portal, choose **Device enrollment** > **Enrollment Restrictions**, choose **Corporate Device Identifiers**, and choose **Delete**.</span></span>

3. <span data-ttu-id="b992d-139">Na folha **Excluir Identificadores**, navegue para o arquivo .csv de IDs de dispositivo para excluir e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="b992d-139">In the **Delete Identifiers** blade, brows to the .csv file of device IDs to delete, and then click **Delete**.</span></span>

## <span data-ttu-id="b992d-140">Especificações do IMEI</span><span class="sxs-lookup"><span data-stu-id="b992d-140">IMEI specifications</span></span>
<a id="imei-specifications" class="xliff"></a>
<span data-ttu-id="b992d-141">Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span><span class="sxs-lookup"><span data-stu-id="b992d-141">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>
