---
title: "Importar configurações de Wi-Fi para Windows 8.1 e posterior"
titleSuffix: Intune on Azure
description: "Como importar configurações de Wi-Fi do Windows para um perfil de Wi-Fi do Intune."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c4ef9bf6ed3f731afada55d2af71d56367f4638d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="dc1d2-103">Como importar configurações de Wi-Fi para dispositivos Windows 8.1 e posteriores no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc1d2-103">How to import Wi-Fi settings for Windows 8.1 and later devices in Microsoft Intune</span></span>
<a id="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="dc1d2-104">Para dispositivos que executam o Windows 8.1 ou o Windows 10 Desktop ou Mobile, você pode importar um perfil de configuração de Wi-Fi que já foi exportado em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-104">For devices that run Windows 8.1 or Windows 10 desktop or mobile, you can import a Wi-Fi configuration profile that was previously exported to a file.</span></span>

## <span data-ttu-id="dc1d2-105">Exportar configurações Wi-Fi de um dispositivo do Windows</span><span class="sxs-lookup"><span data-stu-id="dc1d2-105">Export Wi-Fi settings from a Windows device</span></span>
<a id="export-wi-fi-settings-from-a-windows-device" class="xliff"></a>

<span data-ttu-id="dc1d2-106">No Windows, você pode usar o utilitário **netsh wlan** para exportar um perfil de Wi-Fi existente para um arquivo XML legível pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-106">In Windows, use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by Intune.</span></span> <span data-ttu-id="dc1d2-107">Em um computador Windows que já tenha o perfil de WiFi necessário instalado, siga o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-107">On a Windows computer that already has the required WiFi profile installed, follow this following procedure.</span></span>
1. <span data-ttu-id="dc1d2-108">Crie uma pasta local para os perfis Wi-Fi exportados, como **c:\WiFi**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-108">Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.</span></span>
1. <span data-ttu-id="dc1d2-109">Abra um Prompt de Comando como Administrador.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-109">Open up a Command Prompt as an administrator.</span></span>
1. <span data-ttu-id="dc1d2-110">Execute o comando **netsh wlan show profiles**, e observe o nome do perfil que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-110">Run the command **netsh wlan show profiles**, and note the name of the profile you'd like to export.</span></span> <span data-ttu-id="dc1d2-111">Neste exemplo, o nome do perfil é **WiFiName**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-111">In this example, the profile name is **WiFiName**.</span></span>
1. <span data-ttu-id="dc1d2-112">Execute este comando: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**. Isso criará um arquivo de perfil de Wi-Fi chamado **Wi-Fi-WiFiName.xml** na sua pasta de destino.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-112">Run this command: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**.This will create a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.</span></span>

## <span data-ttu-id="dc1d2-113">Importar as configurações de Wi-Fi para o Intune</span><span class="sxs-lookup"><span data-stu-id="dc1d2-113">Import the Wi-Fi settings into Intune</span></span>
<a id="import-the-wi-fi-settings-into-intune" class="xliff"></a>

1. <span data-ttu-id="dc1d2-114">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="dc1d2-115">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="dc1d2-116">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-116">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="dc1d2-117">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-117">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="dc1d2-118">Na folha de perfis, clique em **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-118">On the profiles blade, click **Create Profile**.</span></span>
4. <span data-ttu-id="dc1d2-119">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-119">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="dc1d2-120">Na lista suspensa **Plataforma**, escolha **Windows 8.1 e posterior**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-120">From the **Platform** drop-down list, choose **Windows 8.1 and later**.</span></span>
6. <span data-ttu-id="dc1d2-121">Na lista suspensa de tipos de **Perfil**, escolha **Importar Wi-Fi**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-121">From the **Profile** type drop-down list, choose **Wi-Fi import**.</span></span>
7. <span data-ttu-id="dc1d2-122">Na folha **Wi-Fi básico**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dc1d2-122">On the **Wi-Fi Basic** blade, configure the following:</span></span>
    - <span data-ttu-id="dc1d2-123">**Nome da Conexão** insira o nome da conexão de Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-123">**Connection name** Enter the name of the Wi-Fi connection.</span></span> <span data-ttu-id="dc1d2-124">Esse nome será exibido aos usuários finais que acessam redes Wi-Fi disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-124">This name will be displayed to end users when they browse available Wi-Fi networks.</span></span>
    - <span data-ttu-id="dc1d2-125">**Perfil XML** Clique no botão Procurar para selecionar o arquivo XML que contém as configurações de perfil de Wi-Fi que você deseja importar para o Intune.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-125">**Profile XML** Click the browse button to select the XML file containing the Wi-Fi profile settings that you want to import into Intune.</span></span>
    - <span data-ttu-id="dc1d2-126">**Conteúdo do arquivo** Exibe o código XML para o perfil de configuração selecionado.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-126">**File contents** Displays the XML code for the configuration profile you selected.</span></span>
8. <span data-ttu-id="dc1d2-127">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-127">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="dc1d2-128">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="dc1d2-128">The profile will be created and appears on the profiles list blade.</span></span>
