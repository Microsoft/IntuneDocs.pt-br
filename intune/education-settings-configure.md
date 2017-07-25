---
title: "Definir as configurações de educação do Intune para Windows 10"
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para definir as configurações de educação do Windows 10 nos dispositivos gerenciados."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39aa668794280adc612122e9b2c3c4e7737b65e9
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="76576-103">Como definir configurações de educação do Windows 10 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="76576-103">How to configure Windows 10 education settings in Microsoft Intune</span></span>
<a id="how-to-configure-windows-10-education-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="76576-104">Os perfis de educação permitem que você especifique os detalhes de configuração do aplicativo Windows Take a Test, incluindo detalhes da conta e a URL do teste.</span><span class="sxs-lookup"><span data-stu-id="76576-104">Education profiles let you specify details that configure the Windows Take a Test app including account details, and the test URL.</span></span> <span data-ttu-id="76576-105">Ao configurar isso, o aplicativo Take a Testa é aberto com o teste especificado, e nenhum outro aplicativo pode ser executado no dispositivo até que o teste seja concluído.</span><span class="sxs-lookup"><span data-stu-id="76576-105">When you configure this, the Take a Test app opens with the test you specify, and no other apps can be run on the device until the test is complete.</span></span>

<span data-ttu-id="76576-106">Use as informações neste tópico para aprender as noções básicas sobre a configuração de perfis de restrição de dispositivo e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76576-106">Use the information in this topic to learn the basics about configuring device restriction profiles, and then read further topics for each platform to learn about device specifics.</span></span>

## <span data-ttu-id="76576-107">Criar um perfil de dispositivo que contém as configurações do perfil de educação</span><span class="sxs-lookup"><span data-stu-id="76576-107">Create a device profile containing education profile settings</span></span>
<a id="create-a-device-profile-containing-education-profile-settings" class="xliff"></a>

1. <span data-ttu-id="76576-108">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="76576-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="76576-109">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="76576-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="76576-110">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="76576-110">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="76576-111">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="76576-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="76576-112">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="76576-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="76576-113">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de restrição do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="76576-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="76576-114">Na lista suspensa **Plataforma**, escolha **Windows 10 e posterior**.</span><span class="sxs-lookup"><span data-stu-id="76576-114">From the **Platform** drop-down list, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="76576-115">Na lista suspensa **Tipos de perfil**, escolha **Perfil de educação**.</span><span class="sxs-lookup"><span data-stu-id="76576-115">From the **Profile type** type drop-down list, choose **Education profile**.</span></span> 
7. <span data-ttu-id="76576-116">Escolha Configurações > Configurar, em seguida, na folha **Take a Test**, configure o seguinte:</span><span class="sxs-lookup"><span data-stu-id="76576-116">Choose Settings > Configure, then, on the **Take a Test** blade, configure the following:</span></span>
    - <span data-ttu-id="76576-117">**Nome da conta de usuário** - Insira o nome de usuário da conta usada com Take a Test.</span><span class="sxs-lookup"><span data-stu-id="76576-117">**Account user name** - Enter the user name of the account used with Take a Test.</span></span> <span data-ttu-id="76576-118">Pode ser uma conta de domínio, uma conta do Azure Active Directory (AAD) ou uma conta de computador local.</span><span class="sxs-lookup"><span data-stu-id="76576-118">This can be a domain account, an Azure Active Directory (AAD) account, or a local computer account.</span></span>
    - <span data-ttu-id="76576-119">**URL de avaliação** - Forneça a URL do teste o qual você deseja que os usuários realizem.</span><span class="sxs-lookup"><span data-stu-id="76576-119">**Assessment URL** - Provide the URL of the test you want users to take.</span></span> <span data-ttu-id="76576-120">Para saber mais, veja a documentação do Take a Test.</span><span class="sxs-lookup"><span data-stu-id="76576-120">For more information, see the Take a Test documentation.</span></span>
    - <span data-ttu-id="76576-121">**Monitoramento de tela** - Especifique se você deseja ser capaz de monitorar a atividade da tela enquanto os usuários realizam um teste.</span><span class="sxs-lookup"><span data-stu-id="76576-121">**Screen monitoring** - Specify whether you want to be able to monitor screen activity while users are taking a test.</span></span>
    - <span data-ttu-id="76576-122">**Sugestão de texto** - Permita ou bloqueie sugestões de texto enquanto os usuários realizam um teste.</span><span class="sxs-lookup"><span data-stu-id="76576-122">**Text suggestion** - Allow or block text suggestions while users are taking a test.</span></span>
8. <span data-ttu-id="76576-123">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="76576-123">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="76576-124">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="76576-124">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="76576-125">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="76576-125">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>



