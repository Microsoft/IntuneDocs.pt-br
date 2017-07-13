---
title: Como administrar dispositivos Android remotamente usando o TeamViewer
titleSuffix: Intune on Azure
description: Saiba como administrar dispositivos Android remotamente usando o TeamViewer.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 15a005ae2b84c7bd4f913f892089965c10f3b23e
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="93d29-103">Fornecer assistência remota para dispositivos Android gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="93d29-103">Provide remote assistance for Intune managed Android devices</span></span>
<a id="provide-remote-assistance-for-intune-managed-android-devices" class="xliff"></a>

<span data-ttu-id="93d29-104">O Intune pode usar o software [TeamViewer](https://www.teamviewer.com), comprado separadamente, para que você possa fornecer assistência remota aos usuários que executam dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="93d29-104">Intune can use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running Android devices.</span></span> <span data-ttu-id="93d29-105">Use as informações deste tópico para configurar tudo e começar a trabalhar.</span><span class="sxs-lookup"><span data-stu-id="93d29-105">Use the information in this topic to set things up and get started.</span></span>

## <span data-ttu-id="93d29-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="93d29-106">Before you start</span></span>
<a id="before-you-start" class="xliff"></a>

### <span data-ttu-id="93d29-107">Permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="93d29-107">Required permissions</span></span>
<a id="required-permissions" class="xliff"></a>

<span data-ttu-id="93d29-108">Verifique se o usuário do portal do Azure tem as seguintes permissões atribuídas a ele como uma [função do Intune](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):</span><span class="sxs-lookup"><span data-stu-id="93d29-108">Ensure that the user of the Azure portal has the following permissions assigned to them as an [Intune role](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):</span></span>
- <span data-ttu-id="93d29-109">Para permitir que o administrador modifique as configurações de conector do TeamViewer, conceda a permissão **Atualizar Assistência Remota**.</span><span class="sxs-lookup"><span data-stu-id="93d29-109">To let the admin modify the TeamViewer connector settings, grant the **Update Remote Assistance** permission.</span></span>
- <span data-ttu-id="93d29-110">Para permitir que o administrador inicie novas configurações de assistência remota, conceda a permissão **Solicitar Assistência Remota**.</span><span class="sxs-lookup"><span data-stu-id="93d29-110">To let the admin initiate a new remote assistance settings, grant the **Request Remote Assistance** permission.</span></span> <span data-ttu-id="93d29-111">Os usuários com essa permissão podem solicitar o início de uma sessão para qualquer usuário; isso não é limitado por nenhum escopo de atribuição de função do Intune.</span><span class="sxs-lookup"><span data-stu-id="93d29-111">Users with this permission can request to initiate a session for any user; this is not limited by any Intune role assignment scope.</span></span> <span data-ttu-id="93d29-112">Os escopos de atribuição de função do Intune não limitam os dispositivos ou os usuários para os quais as solicitações de Assistência Remota podem ser iniciadas.</span><span class="sxs-lookup"><span data-stu-id="93d29-112">Intune role assignment scopes do not limit the devices or users for which Remote Assistance requests can be initiated.</span></span>

>[!NOTE]
><span data-ttu-id="93d29-113">Ao habilitar o TeamViewer, você permite que o Conector do TeamViewer para o Intune crie sessões do TeamViewer, leia dados do Active Directory e salve o token de acesso de conta do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="93d29-113">By enabling TeamViewer, you are allowing the TeamViewer for Intune Connector to create TeamViewer sessions, read Active Directory data, and save the TeamViewer account access token.</span></span>

### <span data-ttu-id="93d29-114">Configurar o conector do TeamViewer para o Intune</span><span class="sxs-lookup"><span data-stu-id="93d29-114">Configure the Intune TeamViewer connector</span></span>
<a id="configure-the-intune-teamviewer-connector" class="xliff"></a>

<span data-ttu-id="93d29-115">Antes de poder fornecer assistência remota a dispositivos Android, você precisará configurar o conector do TeamViewer para o Intune usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="93d29-115">Before you can provide remote assistance to Android devices, you'll need to configure the Intune TeamViewer connector, using the following steps:</span></span>


1. <span data-ttu-id="93d29-116">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="93d29-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="93d29-117">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="93d29-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="93d29-118">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="93d29-118">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="93d29-119">Na folha **Dispositivos e grupos**, escolha **Instalação** > **Conector do TeamViewer**.</span><span class="sxs-lookup"><span data-stu-id="93d29-119">On the **Devices and groups** blade, choose **Setup** > **TeamViewer Connector**.</span></span>
5. <span data-ttu-id="93d29-120">Na folha **Conector do TeamViewer**, clique em **Habilitar** e, em seguida, exiba e aceite o contrato de licença de serviço do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="93d29-120">On the **TeamViewer Connector** blade, click **Enable**, then view and accept the TeamViewer service license agreement.</span></span>
6. <span data-ttu-id="93d29-121">Escolha **Fazer Logon no TeamViewer e Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="93d29-121">Choose **Log in to TeamViewer & Authorize**.</span></span>
7. <span data-ttu-id="93d29-122">Uma página da Web é aberta no site do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="93d29-122">A web page opens to the TeamViewer site.</span></span> <span data-ttu-id="93d29-123">Insira suas credenciais de licença do TeamViewer e, em seguida, clique em **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="93d29-123">Enter your TeamViewer license credentials, and then click **Sign In**.</span></span>


## <span data-ttu-id="93d29-124">Como administrar um dispositivo Android remotamente</span><span class="sxs-lookup"><span data-stu-id="93d29-124">How to remotely administer an Android device</span></span>
<a id="how-to-remotely-administer-an-android-device" class="xliff"></a>

1. <span data-ttu-id="93d29-125">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="93d29-125">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="93d29-126">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="93d29-126">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="93d29-127">Na folha **Intune**, escolha **Dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="93d29-127">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="93d29-128">Na folha **Dispositivos**, escolha **Gerenciar** > **Todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="93d29-128">On the **Devices** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="93d29-129">Selecione o dispositivo que você deseja administrar remotamente e, em seguida, na folha de propriedades do dispositivo, escolha **Mais** > **Nova Sessão de Assistência Remota**.</span><span class="sxs-lookup"><span data-stu-id="93d29-129">Select the device that you want to remotely administer, and then, on the device properties blade, choose **More** > **New Remote Assistance Session**.</span></span>
6. <span data-ttu-id="93d29-130">Depois que o Intune se conectar ao serviço do TeamViewer, você verá algumas informações sobre o dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="93d29-130">After Intune connects to the TeamViewer service, you'll see some information about the Android device.</span></span> <span data-ttu-id="93d29-131">Escolha **Conectar** para iniciar a sessão remota.</span><span class="sxs-lookup"><span data-stu-id="93d29-131">Choose **Connect** to start the remote session.</span></span>

![Janelas do TeamViewer no Android](./media/android-teamviewer.png)

<span data-ttu-id="93d29-133">Na janela do TeamViewer, você pode realizar uma variedade de ações remotas no dispositivo Android, incluindo o controle remoto do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="93d29-133">In the TeamViewer window, you can perform a range of remote actions on the Android device, including remote control of the device.</span></span> <span data-ttu-id="93d29-134">Para obter detalhes completos das ações que podem ser realizadas, consulte a [documentação do TeamViewer](https://www.teamviewer.com/support/documents/).</span><span class="sxs-lookup"><span data-stu-id="93d29-134">For full details of the actions you can perform, see the [TeamViewer documentation](https://www.teamviewer.com/support/documents/).</span></span>

<span data-ttu-id="93d29-135">Quando terminar,</span><span class="sxs-lookup"><span data-stu-id="93d29-135">When you are finished.</span></span> <span data-ttu-id="93d29-136">feche a janela do TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="93d29-136">close the TeamViewer window.</span></span>

## <span data-ttu-id="93d29-137">Notificações do usuário final</span><span class="sxs-lookup"><span data-stu-id="93d29-137">End user notifications</span></span>
<a id="end-user-notifications" class="xliff"></a>

<span data-ttu-id="93d29-138">Um usuário final verá um sinalizador de notificação no ícone do aplicativo do Portal da Empresa em seu dispositivo e também verá uma notificação quando o aplicativo for aberto.</span><span class="sxs-lookup"><span data-stu-id="93d29-138">An end user will see a notification flag on the Company Portal app icon on their device, and also see a notification when they open the app.</span></span> <span data-ttu-id="93d29-139">Em seguida, ele poderá aceitar a solicitação de assistência remota.</span><span class="sxs-lookup"><span data-stu-id="93d29-139">They can then accept the remote assistance request.</span></span>

