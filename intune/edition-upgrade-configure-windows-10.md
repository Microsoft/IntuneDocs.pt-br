---
title: "Configurar atualizações da edição do Windows 10 com o Intune"
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para fazer atualização dos dispositivos Windows 10 gerenciados para outra edição."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 30cea0ecfa62e9bbc0200d15eff94782d48a81fa
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="cdf8b-103">Como configurar as atualizações de edição do Windows 10 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cdf8b-103">How to configure Windows 10 edition upgrades in Microsoft Intune</span></span>
<a id="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="cdf8b-104">Use as informações neste tópico para aprender a configurar um perfil de atualização da edição do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-104">Use the information in this topic to learn how to configure a Windows 10 edition upgrade profile.</span></span> <span data-ttu-id="cdf8b-105">Este perfil permite atualizar automaticamente os dispositivos que executam uma das seguintes versões do Windows 10 para uma edição diferente:</span><span class="sxs-lookup"><span data-stu-id="cdf8b-105">This profile lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:</span></span>

- <span data-ttu-id="cdf8b-106">Windows 10 Home</span><span class="sxs-lookup"><span data-stu-id="cdf8b-106">Windows 10 Home</span></span>
- <span data-ttu-id="cdf8b-107">Windows 10 Holographic</span><span class="sxs-lookup"><span data-stu-id="cdf8b-107">Windows 10 Holographic</span></span>
- <span data-ttu-id="cdf8b-108">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="cdf8b-108">Windows 10 Mobile</span></span>


<span data-ttu-id="cdf8b-109">Há suporte para os seguintes caminhos de atualização:</span><span class="sxs-lookup"><span data-stu-id="cdf8b-109">The following upgrade paths are supported:</span></span>

- <span data-ttu-id="cdf8b-110">Do Windows 10 Pro para Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="cdf8b-110">From Windows 10 Pro to Windows 10 Enterprise</span></span>
- <span data-ttu-id="cdf8b-111">Do Windows 10 Home para Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="cdf8b-111">From Windows 10 Home to Windows 10 Education</span></span>
- <span data-ttu-id="cdf8b-112">Do Windows 10 Mobile para Windows 10 Mobile Enterprise</span><span class="sxs-lookup"><span data-stu-id="cdf8b-112">From Windows 10 Mobile to Windows 10 Mobile Enterprise</span></span>
- <span data-ttu-id="cdf8b-113">Do Windows 10 Holographic Pro para o Windows 10 Holographic Enterprise</span><span class="sxs-lookup"><span data-stu-id="cdf8b-113">From Windows 10 Holographic Pro to Windows 10 Holographic Enterprise</span></span>


## <span data-ttu-id="cdf8b-114">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="cdf8b-114">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>
<span data-ttu-id="cdf8b-115">Antes de começar a atualizar os dispositivos para a versão mais recente, será necessário o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cdf8b-115">Before you begin to upgrade devices to the latest version, you will need one of the following:</span></span>

- <span data-ttu-id="cdf8b-116">Uma chave do produto (Product Key) que é válida para instalar a nova versão do Windows em todos os dispositivos de destino com a política (para edições do Windows 10 Desktop).</span><span class="sxs-lookup"><span data-stu-id="cdf8b-116">A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions).</span></span> <span data-ttu-id="cdf8b-117">Você pode usar chaves MAK (Chaves de Ativação Múltipla) ou KMS (Servidor de Gerenciamento de Chaves).</span><span class="sxs-lookup"><span data-stu-id="cdf8b-117">You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys.</span></span> <span data-ttu-id="cdf8b-118">ou Um arquivo de licença da Microsoft que contém as informações de licenciamento para instalar a nova versão do Windows em todos os dispositivos de destino da política (para as edições Windows 10 Mobile e Windows 10 Holographic).</span><span class="sxs-lookup"><span data-stu-id="cdf8b-118">or A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).</span></span>
- <span data-ttu-id="cdf8b-119">Os dispositivos Windows 10 de destino devem ser registrados no Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-119">The Windows 10 devices that you target must be enrolled in Microsoft Intune.</span></span> <span data-ttu-id="cdf8b-120">Você não pode usar a política de atualização de edição com computadores que executam o software cliente do Intune PC.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-120">You cannot use the edition upgrade policy with PCs that run the Intune PC client software.</span></span>

## <span data-ttu-id="cdf8b-121">Criar um perfil de dispositivo que contém as configurações de restrição de dispositivo</span><span class="sxs-lookup"><span data-stu-id="cdf8b-121">Create a device profile containing device restriction settings</span></span>
<a id="create-a-device-profile-containing-device-restriction-settings" class="xliff"></a>

1. <span data-ttu-id="cdf8b-122">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-122">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="cdf8b-123">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-123">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="cdf8b-124">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-124">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="cdf8b-125">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-125">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="cdf8b-126">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-126">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="cdf8b-127">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de atualização de edição.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-127">On the **Create Profile** blade, enter a **Name** and **Description** for the edition upgrade profile.</span></span>
5. <span data-ttu-id="cdf8b-128">Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-128">From the **Platform** drop-down list, choose **Windows 10 and later**.</span></span>
6. <span data-ttu-id="cdf8b-129">Na lista suspensa **Tipo de perfil**, escolha **Atualização de edição**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-129">From the **Profile type** drop-down list, choose **Edition upgrade**.</span></span>
7. <span data-ttu-id="cdf8b-130">Na folha **Atualização de edição**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="cdf8b-130">On the **Edition Upgrade** blade, configure the following:</span></span>
    - <span data-ttu-id="cdf8b-131">**Edição de partida da atualização** – Na lista suspensa, selecione a versão do Windows 10 que você deseja atualizar nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-131">**Edition to upgrade from** - From the drop-down list, select the Windows 10 version that you want to upgrade on devices.</span></span>
    - <span data-ttu-id="cdf8b-132">**Edição de destino da atualização** – Na lista suspensa, selecione a versão do Windows 10 Desktop, Windows 10 Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-132">**Edition to upgrade to** - From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.</span></span>
    - <span data-ttu-id="cdf8b-133">**Chave do Produto (Product Key)** – Especifique a chave do produto (Product Key) que você obteve da Microsoft, a qual pode ser usada para atualizar todos os dispositivos de destino do Windows 10 Desktop.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-133">**Product Key** - Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.</span></span><br><span data-ttu-id="cdf8b-134">Depois de criar uma política que contém uma chave do produto (Product Key), não será possível editar essa chave mais tarde.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-134">.After you create a policy that contains a product key, you cannot edit the product key later.</span></span> <span data-ttu-id="cdf8b-135">Isso ocorre porque a chave é obscurecida por motivos de segurança.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-135">This is because the key is obscured for security reasons.</span></span> <span data-ttu-id="cdf8b-136">Para alterar a chave do produto (Product Key), você deve inserir a chave inteira novamente.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-136">To change the product key, you must enter the entire key again.</span></span>
    - <span data-ttu-id="cdf8b-137">**Arquivo de Licença** – Escolha **Navegar** para selecionar o arquivo de licença que você obteve da Microsoft com as informações de licença para a edição do Windows Holographic ou Windows 10 Mobile para a qual você deseja atualizar os dispositivos de destino.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-137">**License File** - Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.</span></span>
8. <span data-ttu-id="cdf8b-138">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-138">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="cdf8b-139">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="cdf8b-139">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="cdf8b-140">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="cdf8b-140">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

