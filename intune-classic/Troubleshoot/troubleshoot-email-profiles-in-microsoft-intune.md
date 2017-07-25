---
title: Solucionar problemas de perfis de email
description: "Problemas com o perfil de email e como resolvê-los."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f79ebec4dea17bd03b88d97aa1d7b30a58e35cdb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="53077-103">Solucionar problemas de perfis de email no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="53077-103">Troubleshoot email profiles in Microsoft Intune</span></span>
<a id="troubleshoot-email-profiles-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="53077-104">Aqui estão relacionados alguns problemas com o perfil de email e como resolvê-los.</span><span class="sxs-lookup"><span data-stu-id="53077-104">Listed here are some email profile issues and how to troubleshoot and resolve them.</span></span>

<span data-ttu-id="53077-105">Se essas informações não resolverem seu problema, confira [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune) para encontrar outras formas de obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="53077-105">If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.</span></span>


## <span data-ttu-id="53077-106">Não é possível enviar imagens da conta de email</span><span class="sxs-lookup"><span data-stu-id="53077-106">Unable to send images from  email account</span></span>
<a id="unable-to-send-images-from--email-account" class="xliff"></a>
<span data-ttu-id="53077-107">Os usuários que têm contas de email configuradas automaticamente não podem enviar imagens de seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="53077-107">Users who have email accounts automatically configured are unable to send pictures or images from their devices.</span></span>
<span data-ttu-id="53077-108">Isso ocorre quando a opção **Permitir que o email seja enviado de aplicativos de terceiros** não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="53077-108">This occurs when the option **Allow e-mail to be sent from third-party applications** is not enabled.</span></span>

### <span data-ttu-id="53077-109">Solução do Intune</span><span class="sxs-lookup"><span data-stu-id="53077-109">Intune solution</span></span>
<a id="intune-solution" class="xliff"></a>

1.  <span data-ttu-id="53077-110">Abra o Console de administração do Microsoft Intune, selecione **Política** Carga de trabalho &gt;**Política de configuração**.</span><span class="sxs-lookup"><span data-stu-id="53077-110">Open the Microsoft Intune Administration Console, select **Policy** workload &gt; **Configuration Policy**.</span></span>

2.  <span data-ttu-id="53077-111">Selecione o perfil de email e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="53077-111">Select the email profile and choose **Edit**.</span></span>

3.  <span data-ttu-id="53077-112">Selecione a opção **Permitir que o email seja enviado de aplicativos de terceiros.**</span><span class="sxs-lookup"><span data-stu-id="53077-112">Select **Allow e-mail to be sent from third-party applications.**</span></span>

### <span data-ttu-id="53077-113">Configuration Manager integrado à solução Intune</span><span class="sxs-lookup"><span data-stu-id="53077-113">Configuration Manager integrated with Intune solution</span></span>
<a id="configuration-manager-integrated-with-intune-solution" class="xliff"></a>

1.  <span data-ttu-id="53077-114">Abra o console do Configuration Manager &gt; **Ativos e Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="53077-114">Open the Configuration Manager console &gt; **Assets and Compliance**.</span></span>

2.  <span data-ttu-id="53077-115">Expanda **Visão Geral** -&gt; **Configurações de Conformidade** -&gt; **Acesso aos Recursos da Empresa** e selecione **Perfis de Email**.</span><span class="sxs-lookup"><span data-stu-id="53077-115">Expand **Overview** -&gt; **Compliance Settings** -&gt; **Company Resource Access**, and select **Email Profiles**.</span></span>

3.  <span data-ttu-id="53077-116">Clique com o botão direito do mouse no perfil de email e abra as **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="53077-116">Right-click the e-mail profile, and open **Properties**.</span></span>

4.  <span data-ttu-id="53077-117">Na guia **Configurações de Sincronização**, selecione **Permitir que o email seja enviado de aplicativos de terceiros**.</span><span class="sxs-lookup"><span data-stu-id="53077-117">On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.</span></span>


## <span data-ttu-id="53077-118">O dispositivo já tem um perfil de email instalado</span><span class="sxs-lookup"><span data-stu-id="53077-118">Device already has an email profile installed</span></span>
<a id="device-already-has-an-email-profile-installed" class="xliff"></a>

<span data-ttu-id="53077-119">Se o usuário instalou um perfil de email antes de provisionar um perfil pelo Intune, o resultado da implantação do perfil de email Intune depende da plataforma de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="53077-119">If the user has installed an email profile prior to provision of a profile by Intune, the result of the Intune email profile deployment depends on the device platform:</span></span>

<span data-ttu-id="53077-120">-**iOS**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e no endereço de email.</span><span class="sxs-lookup"><span data-stu-id="53077-120">-**iOS**: Intune detects an existing, duplicate email profile based on hostname and email address.</span></span> <span data-ttu-id="53077-121">O perfil de email duplicado criado pelo usuário bloqueia a implantação de um perfil criado pelo administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="53077-121">The duplicate email profile created by the user will block the deployment of an Intune admin-created profile.</span></span> <span data-ttu-id="53077-122">Isso é um problema comum, pois usuários do iOS normalmente vão criar um perfil de email e, depois, se registrar.</span><span class="sxs-lookup"><span data-stu-id="53077-122">This is a common problem as iOS users will typically create an email profile, then enroll.</span></span> <span data-ttu-id="53077-123">O portal da empresa informará ao usuário que ele não é compatível devido ao seu perfil de email configurado manualmente e solicitará que o usuário remova esse perfil. O usuário deve remover seu perfil de email para que o perfil do Intune possa ser implantado.</span><span class="sxs-lookup"><span data-stu-id="53077-123">The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed.</span></span> <span data-ttu-id="53077-124">Para evitar o problema, instrua os usuários a se registrar antes de instalar um perfil de email e permitir que o Intune implante o perfil.</span><span class="sxs-lookup"><span data-stu-id="53077-124">To prevent the problem instruct your users to enroll before installing an email profile and to allow Intune to deploy the profile.</span></span>

<span data-ttu-id="53077-125">-**Windows**: o Intune detecta um perfil de email existente e duplicado com base no nome do host e no endereço de email.</span><span class="sxs-lookup"><span data-stu-id="53077-125">-**Windows**: Intune detects an existing, duplicate email profile based on hostname and email address.</span></span> <span data-ttu-id="53077-126">O Intune substituirá o perfil de email existente criado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="53077-126">Intune will overwrite the existing email profile created by the user.</span></span>

<span data-ttu-id="53077-127">-**Samsung KNOX Standard**: o Intune identifica uma conta de email duplicada com base no endereço de email e depois a substitui pelo perfil do Intune.</span><span class="sxs-lookup"><span data-stu-id="53077-127">-**Samsung KNOX Standard**: Intune identifies a duplicate email account based on the email address, and will overwrite it with the Intune profile.</span></span> <span data-ttu-id="53077-128">Se o usuário configurar essa conta, ela será substituída novamente pelo perfil do Intune.</span><span class="sxs-lookup"><span data-stu-id="53077-128">If the user configures that account, it will be overwritten again by the Intune profile.</span></span> <span data-ttu-id="53077-129">Observe que isso pode causar alguma confusão ao usuário cuja configuração de conta for substituída.</span><span class="sxs-lookup"><span data-stu-id="53077-129">Note that this may cause some confusion to the user whose account configuration gets overwritten.</span></span>

<span data-ttu-id="53077-130">Como o Samsung KNOX não usa o nome do host para identificar o perfil, é recomendável que você não crie vários perfis de email para implantar o mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="53077-130">Since Samsung KNOX does not use hostname to identify the profile, we recommend that you not create multiple email profiles to deploy to the same email address on different hosts, as these will overwrite each other.</span></span>

## <span data-ttu-id="53077-131">Erro 0x87D1FDE8 para dispositivo KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="53077-131">Error  0x87D1FDE8 for KNOX Standard device</span></span>
<a id="error--0x87d1fde8-for-knox-standard-device" class="xliff"></a>
<span data-ttu-id="53077-132">**Problema**: depois de criar e implantar um perfil de email do Exchange Active Sync para Samsung KNOX Standard para vários dispositivos Android, o erro **0x87D1FDE8** ou **falha na correção** é reportado na guia da política &gt; das propriedades do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="53077-132">**Issue**: After creating and deploying an Exchange Active Sync email profile for Samsung KNOX Standard for various Android devices, the error **0x87D1FDE8** or **remediation failed** is reported in the device's properties &gt; policy tab.</span></span>

<span data-ttu-id="53077-133">Examine a configuração do seu perfil de EAS para Samsung KNOX e a política de origem.</span><span class="sxs-lookup"><span data-stu-id="53077-133">Review the configuration of your EAS profile for Samsung KNOX and source policy.</span></span> <span data-ttu-id="53077-134">Não há suporte para a opção de sincronização das Samsung Notes e essa opção não deve estar selecionada em seu perfil.</span><span class="sxs-lookup"><span data-stu-id="53077-134">The Samsung Notes sync option is no longer supported and that option should not be selected in your profile.</span></span> <span data-ttu-id="53077-135">Certifique-se de que os dispositivos tiveram tempo suficiente, se até 24 horas, para processar a política.</span><span class="sxs-lookup"><span data-stu-id="53077-135">Be sure devices have had enough time to process the policy, up to 24 hours.</span></span>

## <span data-ttu-id="53077-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="53077-136">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="53077-137">Se essas informações para solução de problemas não ajudarem, entre em contato com o Suporte da Microsoft, conforme descrito em [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Como obter suporte para o Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="53077-137">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
