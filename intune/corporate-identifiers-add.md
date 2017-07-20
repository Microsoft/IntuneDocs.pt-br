---
title: <span data-ttu-id="de457-101">Adicionar identificadores IMEI ao Intune</span><span class="sxs-lookup"><span data-stu-id="de457-101">Add IMEI identifiers to Intune</span></span>
titleSuffix: Intune on Azure
description: "<span data-ttu-id=\"de457-102\">Saiba como adicionar identificadores corporativos (números IMEI) ao Microsoft Intune.</span><span class=\"sxs-lookup\"><span data-stu-id=\"de457-102\">Learn how to add corporate identifiers (IMEI numbers) to Microsoft Intune.</span></span> <span data-ttu-id=\"de457-103\">\"</span><span class=\"sxs-lookup\"><span data-stu-id=\"de457-103\">\"</span></span>"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a9852759983a4bc68c596146e2f5691893376cfd
ms.sourcegitcommit: 388c5f59bc992375ac63968fd7330af5d84a1348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2017
---
# <a name="add-corporate-identifiers"></a><span data-ttu-id="de457-104">Adicionar identificadores corporativos</span><span class="sxs-lookup"><span data-stu-id="de457-104">Add corporate identifiers</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="de457-105">Como administrador do Intune, você pode criar e importar um arquivo de valores separados por vírgulas (.csv) que relaciona números IMEI (International Mobile Equipment Identifier) ou números de série.</span><span class="sxs-lookup"><span data-stu-id="de457-105">As an Intune admin, you can create and import a comma-separated value (.csv) file that lists international mobile equipment identifier (IMEI) numbers or serial numbers.</span></span> <span data-ttu-id="de457-106">O Intune usa esses identificadores para especificar a propriedade dos dispositivos como corporativos.</span><span class="sxs-lookup"><span data-stu-id="de457-106">Intune uses these identifiers to specify device ownership as corporate.</span></span> <span data-ttu-id="de457-107">Você pode declarar apenas números IMEI em todas as plataformas com suporte.</span><span class="sxs-lookup"><span data-stu-id="de457-107">You can only declare IMEI numbers for all supported platforms.</span></span> <span data-ttu-id="de457-108">Somente é possível declarar o número de série para dispositivos iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="de457-108">You can only declare serial number for iOS and Android devices.</span></span> <span data-ttu-id="de457-109">Cada número IMEI ou de série pode ter detalhes especificados na lista para fins administrativos.</span><span class="sxs-lookup"><span data-stu-id="de457-109">Each IMEI or serial number can have details specified in the list for administrative purposes.</span></span>

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

<span data-ttu-id="de457-110">[Saiba como localizar o número de série de um dispositivo Apple](https://support.apple.com/HT204308).</span><span class="sxs-lookup"><span data-stu-id="de457-110">[Learn how to find an Apple device serial number](https://support.apple.com/HT204308).</span></span><br><span data-ttu-id="de457-111">
[Saiba como localizar o número de série do dispositivo Android](https://support.google.com/store/answer/3333000).</span><span class="sxs-lookup"><span data-stu-id="de457-111">
[Learn how to find your Android device serial number](https://support.google.com/store/answer/3333000).</span></span>

## <a name="add-corporate-identifiers"></a><span data-ttu-id="de457-112">Adicionar identificadores corporativos</span><span class="sxs-lookup"><span data-stu-id="de457-112">Add corporate identifiers</span></span>
<span data-ttu-id="de457-113">Para criar a lista, crie uma lista de duas colunas de valores separados por vírgula (.csv) sem um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="de457-113">To create the list, create a two-column, comma-separated value (.csv) list without a header.</span></span> <span data-ttu-id="de457-114">Adicione os números de série ou IMEI à coluna esquerda e os detalhes à coluna direita.</span><span class="sxs-lookup"><span data-stu-id="de457-114">Add the IMEI or serial numbers in the left column, and the details in the right column.</span></span> <span data-ttu-id="de457-115">Apenas um tipo de ID, IMEI ou número de série, pode ser importado para o mesmo arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="de457-115">Only one type of ID, IMEI or serial number, can be imported in a single .csv file.</span></span> <span data-ttu-id="de457-116">Os detalhes limitam-se a 128 caracteres e são exclusivamente para uso administrativo.</span><span class="sxs-lookup"><span data-stu-id="de457-116">Details are limited to 128 characters and are for administrative use only.</span></span> <span data-ttu-id="de457-117">O dispositivo não exibe detalhes.</span><span class="sxs-lookup"><span data-stu-id="de457-117">Details aren't displayed on the device.</span></span> <span data-ttu-id="de457-118">O limite atual é de 500 linhas por arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="de457-118">The current limit is 500 rows per .csv file.</span></span>

<span data-ttu-id="de457-119">**Carregar um arquivo .csv contendo números de série** – crie uma lista de valores separados por vírgula (.csv) de duas colunas, sem cabeçalho, e limite a lista a 5.000 dispositivos ou 5 MB por arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="de457-119">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span>

|||
|-|-|
|<span data-ttu-id="de457-120">&lt;ID nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="de457-120">&lt;ID #1&gt;</span></span>|<span data-ttu-id="de457-121">&lt;Detalhes do dispositivo nº 1&gt;</span><span class="sxs-lookup"><span data-stu-id="de457-121">&lt;Device #1 Details&gt;</span></span>|
|<span data-ttu-id="de457-122">&lt;ID nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="de457-122">&lt;ID #2&gt;</span></span>|<span data-ttu-id="de457-123">&lt;Detalhes do dispositivo nº 2&gt;</span><span class="sxs-lookup"><span data-stu-id="de457-123">&lt;Device #2 Details&gt;</span></span>|

<span data-ttu-id="de457-124">Quando visualizado em um editor de texto, esse arquivo .csv aparece como:</span><span class="sxs-lookup"><span data-stu-id="de457-124">This .csv file when viewed in a text editor appears as:</span></span>

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> <span data-ttu-id="de457-125">Alguns dispositivos com Android possuem vários números IMEI.</span><span class="sxs-lookup"><span data-stu-id="de457-125">Some Android devices have multiple IMEI numbers.</span></span> <span data-ttu-id="de457-126">O Intune lê somente um número IMEI por dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="de457-126">Intune only reads one IMEI number per enrolled device.</span></span> <span data-ttu-id="de457-127">Quando você importa um número IMEI, mas ele não está inventariado pelo Intune, o dispositivo é classificado como pessoal em vez de um dispositivo de propriedade da empresa.</span><span class="sxs-lookup"><span data-stu-id="de457-127">If you import an IMEI number but it is not the IMEI inventoried by Intune, the device is classified as a personal device instead of a company-owned device.</span></span> <span data-ttu-id="de457-128">Se importar vários números IMEI para um dispositivo, os números não inventariados exibirão **Desconhecido** como status do registro.</span><span class="sxs-lookup"><span data-stu-id="de457-128">If you import multiple IMEI numbers for a device, uninventoried numbers display **Unknown** for enrollment status.</span></span><br>
><span data-ttu-id="de457-129">Observe também: não há garantia de que os números de série para Android sejam exclusivos ou estejam presentes.</span><span class="sxs-lookup"><span data-stu-id="de457-129">Also note: Android Serial numbers are not guaranteed to be unique or present.</span></span> <span data-ttu-id="de457-130">Verifique junto ao fornecedor do dispositivo para saber se o número de série é uma ID de dispositivo confiável.</span><span class="sxs-lookup"><span data-stu-id="de457-130">Check with your device supplier to understand if serial number is a reliable device ID.</span></span>
><span data-ttu-id="de457-131">Os números de série informados pelo dispositivo no Intune podem não corresponder à ID exibida nos menus Configurações ou Sobre do dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="de457-131">Serial numbers reported by the device to Intune might not match the displayed ID in the Android Settings/About menus on the device.</span></span> <span data-ttu-id="de457-132">Verifique o tipo de número de série informado pelo fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de457-132">Verify the type of serial number reported by the device manufacturer.</span></span>


<span data-ttu-id="de457-133">**Para adicionar uma lista .csv de identificadores corporativos**</span><span class="sxs-lookup"><span data-stu-id="de457-133">**To add a .csv list of corporate identifiers**</span></span>

1. <span data-ttu-id="de457-134">No portal do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de457-134">In the Intune portal, choose **Device enrollment** > **Enrollment Restrictions**, choose **Corporate Device Identifiers**, and then click **Add**.</span></span>

 ![Captura de tela de espaço de trabalho do identificador de dispositivo corporativo com o botão Adicionar realçado.](./media/add-corp-id.png)

2. <span data-ttu-id="de457-136">Na folha **Adicionar identificadores**, especifique o tipo de identificador: **IMEI** ou **Número de série**.</span><span class="sxs-lookup"><span data-stu-id="de457-136">In the **Add Identifiers** blade, specify the identifier type: **IMEI** or **Serial**.</span></span> <span data-ttu-id="de457-137">Você pode especificar se números importados anteriormente devem **substituir os detalhes para os identificadores existentes**.</span><span class="sxs-lookup"><span data-stu-id="de457-137">You can specify whether previously imported numbers should **Overwrite details for existing identifiers**.</span></span>

3. <span data-ttu-id="de457-138">Clique no ícone de pasta e especifique o caminho para a lista que quer importar.</span><span class="sxs-lookup"><span data-stu-id="de457-138">Click the folder icon and specify the path to the list you want to import.</span></span> <span data-ttu-id="de457-139">Navegue para o arquivo .csv e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="de457-139">Navigate to the .csv file, and select **Add**.</span></span> <span data-ttu-id="de457-140">Clique em **Atualizar** para ver os novos identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="de457-140">You can click **Refresh** to see new device identifiers.</span></span>

<span data-ttu-id="de457-141">Os dispositivos importados não são necessariamente registrados.</span><span class="sxs-lookup"><span data-stu-id="de457-141">Imported devices are not necessarily enrolled.</span></span> <span data-ttu-id="de457-142">Os dispositivos podem apresentar o estado de **Registrado** ou **Não contatado**.</span><span class="sxs-lookup"><span data-stu-id="de457-142">Devices can have a state of either **Enrolled** or **Not contacted**.</span></span> <span data-ttu-id="de457-143">**Não contatado** significa que o dispositivo nunca se comunicou com o serviço do Intune.</span><span class="sxs-lookup"><span data-stu-id="de457-143">**Not contacted** means that the device has never communicated in with the Intune service.</span></span>

## <a name="delete-corporate-identifiers"></a><span data-ttu-id="de457-144">Excluir identificadores corporativos</span><span class="sxs-lookup"><span data-stu-id="de457-144">Delete corporate identifiers</span></span>

1. <span data-ttu-id="de457-145">No portal do Intune, escolha **Registro de dispositivo** > **Restrições de Registro**, escolha **Identificadores de Dispositivo Corporativo** e escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="de457-145">In the Intune portal, choose **Device enrollment** > **Enrollment Restrictions**, choose **Corporate Device Identifiers**, and choose **Delete**.</span></span>

3. <span data-ttu-id="de457-146">Na folha **Excluir Identificadores**, navegue para o arquivo .csv de IDs de dispositivo para excluir e, em seguida, clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="de457-146">In the **Delete Identifiers** blade, brows to the .csv file of device IDs to delete, and then click **Delete**.</span></span>

## <a name="imei-specifications"></a><span data-ttu-id="de457-147">Especificações do IMEI</span><span class="sxs-lookup"><span data-stu-id="de457-147">IMEI specifications</span></span>
<span data-ttu-id="de457-148">Para obter especificações detalhadas sobre Identificadores de equipamentos móveis internacionais, veja [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span><span class="sxs-lookup"><span data-stu-id="de457-148">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>
