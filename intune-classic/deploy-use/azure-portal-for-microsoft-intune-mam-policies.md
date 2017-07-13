---
title: "Portal do Azure para políticas de MAM"
description: "Crie políticas de gerenciamento de aplicativo móvel usando o Portal do Azure. As políticas que você criar aqui podem ser aplicadas a dispositivos com ou sem registro no Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 00328885d7fb5e75ffe894326591c0225f4b07ab
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="de8ee-104">Portal do Azure para as políticas de proteção do aplicativo Intune</span><span class="sxs-lookup"><span data-stu-id="de8ee-104">Azure portal for Intune app protection policies</span></span>
<a id="azure-portal-for-intune-app-protection-policies" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="de8ee-105">O Portal do Azure é usado para criar e gerenciar políticas de proteção de aplicativo para:</span><span class="sxs-lookup"><span data-stu-id="de8ee-105">The Azure portal is used to create and manage app protection policies for:</span></span>

- <span data-ttu-id="de8ee-106">Aplicativos executados em dispositivos **registrados e gerenciados no Intune**.</span><span class="sxs-lookup"><span data-stu-id="de8ee-106">Apps running on devices that are **enrolled and managed in Intune**.</span></span>

- <span data-ttu-id="de8ee-107">Aplicativos que são executados em dispositivos que **não são registrados** em nenhuma solução de MDM.</span><span class="sxs-lookup"><span data-stu-id="de8ee-107">Apps running on devices that are **not enrolled** in any MDM solution.</span></span>
- <span data-ttu-id="de8ee-108">Aplicativos executados em dispositivos que são **registrados em uma solução de MDM de terceiros**.</span><span class="sxs-lookup"><span data-stu-id="de8ee-108">Apps running on devices that are **enrolled in a third-party MDM solution**.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="de8ee-109">O Portal do Azure é o novo console de administração para criar políticas de proteção de aplicativo, mas você também pode criar uma política de proteção de aplicativo que dá suporte a aplicativos para dispositivos registrados no Intune usando o [console do administrador do Intune](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) para cenários de MDM.</span><span class="sxs-lookup"><span data-stu-id="de8ee-109">The Azure portal is the new admin console for creating app protection policies, but you can also create an app protection policy that supports apps for devices enrolled into Intune by using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) for MDM scenarios.</span></span>

> <span data-ttu-id="de8ee-110">Você poderá não ver todas as configurações de política de proteção de aplicativo disponíveis no console de administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="de8ee-110">You might not see all the app protection policy settings available on the Intune admin console.</span></span> <span data-ttu-id="de8ee-111">Além disso, se você criar políticas de proteção de aplicativo no console do administrador do Intune e no portal do Azure, as políticas criadas no Portal do Azure substituirão aquelas criadas no console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="de8ee-111">Additionally, if you create app protection policies both on the Intune admin console and in the Azure portal, the policies created in the Azure portal will override the ones created on the Intune admin console.</span></span> <span data-ttu-id="de8ee-112">Nesse cenário, as políticas de proteção de aplicativo do Portal do Azure serão aplicadas aos aplicativos e implantadas para os usuários.</span><span class="sxs-lookup"><span data-stu-id="de8ee-112">In this scenario, the Azure portal app protection policies will be applied to the apps and deployed to users.</span></span>


## <span data-ttu-id="de8ee-113">Entre no portal do Azure e personalize sua página inicial</span><span class="sxs-lookup"><span data-stu-id="de8ee-113">Sign in to the Azure portal and customize your start page</span></span>
<a id="sign-in-to-the-azure-portal-and-customize-your-start-page" class="xliff"></a>

1.  <span data-ttu-id="de8ee-114">Vá para o [Portal do Azure](https://portal.azure.com) e entre com suas credenciais do Intune.</span><span class="sxs-lookup"><span data-stu-id="de8ee-114">Go to the [Azure portal](https://portal.azure.com) and sign in with your Intune credentials.</span></span>

    ![Captura de tela da página de credenciais do portal do Azure](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  <span data-ttu-id="de8ee-116">Quando entrar com êxito, você verá o **Painel**.</span><span class="sxs-lookup"><span data-stu-id="de8ee-116">After you've successfully signed in, you see the **Dashboard**.</span></span> <span data-ttu-id="de8ee-117">A página **Painel** pode ser personalizada.</span><span class="sxs-lookup"><span data-stu-id="de8ee-117">The **Dashboard** page can be customized.</span></span>

    ![Captura de tela do painel do portal do Azure](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  <span data-ttu-id="de8ee-119">Escolha **Mais serviços** no menu à esquerda e digite **Intune** no filtro da caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="de8ee-119">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

    ![Captura de tela do menu Procurar com o Intune realçado](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  <span data-ttu-id="de8ee-121">Escolha **Intune App Protection** > **Gerenciamento de aplicativos móveis do Intune** > **Todas as Configurações**.</span><span class="sxs-lookup"><span data-stu-id="de8ee-121">Choose **Intune App Protection** > **Intune mobile application management** > **All Settings**.</span></span>

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune](../media/AppManagement/MAM-Azure-Portal-2.png)

5. <span data-ttu-id="de8ee-123">(Opcional): para fixar uma folha **Página Inicial**, você pode usar a opção **fixar** na folha.</span><span class="sxs-lookup"><span data-stu-id="de8ee-123">(Optional): To pin a blade to the **Start** page, you can use the **pin** option on the blade.</span></span> <span data-ttu-id="de8ee-124">Clique no ícone de alfinete na **folha de gerenciamento de aplicativo móvel do Intune** para fixá-la à página **Inicial**.</span><span class="sxs-lookup"><span data-stu-id="de8ee-124">Click the pin icon on the **Intune mobile application management blade** to pin that blade to the **Start** page.</span></span>

    ![Captura de tela da folha de gerenciamento de aplicativos móveis do Intune com o ícone de pino realçado](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Captura de tela do painel com o bloco Intune fixado](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <span data-ttu-id="de8ee-127">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="de8ee-127">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
[<span data-ttu-id="de8ee-128">Prepare-se para configurar as políticas de proteção do aplicativo</span><span class="sxs-lookup"><span data-stu-id="de8ee-128">Get ready to configure app protection policies</span></span>](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
