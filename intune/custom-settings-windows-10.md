---
title: "Configurações personalizadas do Intune para dispositivos Windows 10"
titleSuffix: Intune on Azure
description: "Conheça as configurações que você pode usar em um perfil personalizado do Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bda9e939e2d4aba4c4d005ea55ba65bec9c6e217
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="010de-103">Configurações personalizadas do dispositivo para dispositivos Windows 10 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="010de-103">Custom device settings for Windows 10 devices in Microsoft Intune</span></span>
<a id="custom-device-settings-for-windows-10-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 <span data-ttu-id="010de-104">Use o perfil **personalizado** do Microsoft Intune para Windows 10 e Windows 10 Mobile para implantar configurações de OMA-URI (Open Mobile Alliance Uniform Resource Identifier), que podem ser usadas para controlar recursos em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="010de-104">Use the Microsoft Intune **custom** profile for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on devices.</span></span> <span data-ttu-id="010de-105">O Windows 10 disponibiliza várias configurações de CSP, por exemplo o [CSP de Política (Provedor de Serviço de Configuração de Política)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).</span><span class="sxs-lookup"><span data-stu-id="010de-105">Windows 10 makes many CSP settings available, for example, the [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).</span></span>
<span data-ttu-id="010de-106">Se você estiver procurando uma determinada configuração, lembre-se de que o [perfil de restrição de dispositivo do Windows 10](device-restrictions-windows-10.md) contém várias configurações que são integradas ao Intune e não exigem que você especifique valores personalizados.</span><span class="sxs-lookup"><span data-stu-id="010de-106">If you are looking for a particular setting, remember that the [Windows 10 device restriction profile](device-restrictions-windows-10.md) contains many settings that are built-in to Intune and do not require you to specify custom values.</span></span>

1. <span data-ttu-id="010de-107">Use as instruções em [Como definir configurações personalizadas do dispositivo no Microsoft Intune](custom-settings-configure.md) para começar.</span><span class="sxs-lookup"><span data-stu-id="010de-107">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="010de-108">Na folha **Criar Perfil**, escolha **Configurações** para adicionar uma ou mais configurações OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="010de-108">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="010de-109">Na folha **Configurações personalizadas do OMA-URI**, clique em **Adicionar** para adicionar um novo valor.</span><span class="sxs-lookup"><span data-stu-id="010de-109">On the **Custom OMA-URI Settings** blade, click **Add** to add a new value.</span></span> <span data-ttu-id="010de-110">Você também pode clicar em **Exportar** para criar uma lista de todos os valores configurados em um arquivo de valores separados por vírgulas (.csv).</span><span class="sxs-lookup"><span data-stu-id="010de-110">You can also click **Export** to create a list of all the values you configured in a comma-separated values (.csv) file.</span></span>
4. <span data-ttu-id="010de-111">Para cada configuração de OMA-URI que você desejar adicionar, insira as informações a seguir.</span><span class="sxs-lookup"><span data-stu-id="010de-111">For each OMA-URI setting you want to add, enter the following information.</span></span> <span data-ttu-id="010de-112">Use a lista neste tópico para saber mais sobre as configurações que você pode usar:</span><span class="sxs-lookup"><span data-stu-id="010de-112">Use the list in this topic to learn about the settings you can use:</span></span>
    - <span data-ttu-id="010de-113">**Nome da configuração** - insira um nome exclusivo para a configuração de OMA-URI para ajudar a identificá-la na lista de configurações.</span><span class="sxs-lookup"><span data-stu-id="010de-113">**Setting name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="010de-114">**Descrição da configuração** - opcionalmente, insira uma descrição para a configuração.</span><span class="sxs-lookup"><span data-stu-id="010de-114">**Setting description** - Optionally, enter a description for the setting.</span></span>
    - <span data-ttu-id="010de-115">**Tipo de dados** - escolha dentre:</span><span class="sxs-lookup"><span data-stu-id="010de-115">**Data type** - Choose from:</span></span>
        - <span data-ttu-id="010de-116">**Cadeia de caracteres**</span><span class="sxs-lookup"><span data-stu-id="010de-116">**String**</span></span>
        - <span data-ttu-id="010de-117">**Cadeia de caracteres (XML)**</span><span class="sxs-lookup"><span data-stu-id="010de-117">**String (XML)**</span></span>
        - <span data-ttu-id="010de-118">**Data e hora**</span><span class="sxs-lookup"><span data-stu-id="010de-118">**Date and time**</span></span>
        - <span data-ttu-id="010de-119">**Inteiro**</span><span class="sxs-lookup"><span data-stu-id="010de-119">**Integer**</span></span>
        - <span data-ttu-id="010de-120">**Ponto flutuante**</span><span class="sxs-lookup"><span data-stu-id="010de-120">**Floating point**</span></span>
        - <span data-ttu-id="010de-121">**Booliano**</span><span class="sxs-lookup"><span data-stu-id="010de-121">**Boolean**</span></span>
    - <span data-ttu-id="010de-122">**OMA-URI (com distinção entre maiúsculas e minúsculas)** - especifique o OMA-URI para o qual você deseja fornecer uma configuração.</span><span class="sxs-lookup"><span data-stu-id="010de-122">**OMA-URI (case sensitive)** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="010de-123">**Valor** - especifique o valor para associar ao OMA-URI que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="010de-123">**Value** - Specify the value to associate with the OMA-URI you entered.</span></span>
5. <span data-ttu-id="010de-124">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="010de-124">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>
<span data-ttu-id="010de-125">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="010de-125">The profile will be created and appears on the profiles list blade.</span></span>

## <span data-ttu-id="010de-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="010de-126">Example</span></span>
<a id="example" class="xliff"></a>
<span data-ttu-id="010de-127">Na captura de tela abaixo, a configuração **Connectivity/AllowVPNOverCellular** foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="010de-127">In the screenshot below, the setting **Connectivity/AllowVPNOverCellular** has been enabled.</span></span> <span data-ttu-id="010de-128">Isso permite que um dispositivo Windows 10 abra uma conexão VPN quando estiver em uma rede de celular.</span><span class="sxs-lookup"><span data-stu-id="010de-128">This lets a Windows 10 device open a VPN connection when on a cellular network.</span></span>

> ![Exemplo de política personalizada que contém as configurações de VPN](./media/custom-policy-example.png)


## <span data-ttu-id="010de-130">Como localizar as políticas que você pode configurar</span><span class="sxs-lookup"><span data-stu-id="010de-130">How to find the policies you can configure</span></span>
<a id="how-to-find-the-policies-you-can-configure" class="xliff"></a>

<span data-ttu-id="010de-131">Você encontrará uma lista completa de todos os provedores de serviço de configuração (CSP) a que o Windows 10 dá suporte na [Referência do provedor do serviço de configuração](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) na biblioteca de documentação do Windows.</span><span class="sxs-lookup"><span data-stu-id="010de-131">You’ll find a complete list of all configuration service providers (CSPs) that Windows 10 supports in the [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in the Windows documentation library.</span></span>

<span data-ttu-id="010de-132">Nem todas as configurações são compatíveis com todas as versões do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="010de-132">Not all settings are compatible with all Windows 10 versions.</span></span> <span data-ttu-id="010de-133">A tabela no tópico do Windows informa quais versões têm suporte para cada CSP.</span><span class="sxs-lookup"><span data-stu-id="010de-133">The table in the Windows topic tells you which versions are supported for each CSP.</span></span>

<span data-ttu-id="010de-134">Além disso, o Intune não dá suporte a todas as configurações listadas no tópico.</span><span class="sxs-lookup"><span data-stu-id="010de-134">Additionally, Intune does not support all of the settings listed in the topic.</span></span> <span data-ttu-id="010de-135">Para saber se o Intune oferece suporte à configuração desejada, abra o tópico para essa configuração.</span><span class="sxs-lookup"><span data-stu-id="010de-135">To find out if Intune supports the setting you want, open the topic for that setting.</span></span> <span data-ttu-id="010de-136">Cada página de configuração mostra a operação de suporte correspondente.</span><span class="sxs-lookup"><span data-stu-id="010de-136">Each setting page shows it’s supported operation.</span></span> <span data-ttu-id="010de-137">Para trabalhar com o Intune, a configuração deve oferecer suporte às operações **Adicionar** ou **Substituir**.</span><span class="sxs-lookup"><span data-stu-id="010de-137">To work with Intune, the setting must support the **Add** or **Replace** operations.</span></span>


