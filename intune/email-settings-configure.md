---
title: "Como definir configurações de email do Intune"
titleSuffix: Intune on Azure
description: "Saiba como configurar o Intune para criar conexões com o email corporativo nos dispositivos gerenciados."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2ae3e8ec9f9c791d536fe311bc4d30cae41b9482
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="3a199-103">Como definir configurações de email no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3a199-103">How to configure email settings in Microsoft Intune</span></span>
<a id="how-to-configure-email-settings-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="3a199-104">Os perfis de email podem ser usados para configurar dispositivos gerenciados com as configurações necessárias para se conectar e sincronizar o email da empresa.</span><span class="sxs-lookup"><span data-stu-id="3a199-104">Email profiles can be used to configure devices you manage with the settings necessary to connect to , and synchronize with company email.</span></span> <span data-ttu-id="3a199-105">Isso pode ajudar a garantir que as configurações sejam padronizadas em todos os seus dispositivos, bem como ajudar a reduzir as chamadas de suporte dos usuários finais que não conhecem as configurações de email corretas.</span><span class="sxs-lookup"><span data-stu-id="3a199-105">This can help ensure that settings are standard across all of your devices, and also help to reduce support calls from end users who do not know the correct email settings.</span></span>

<span data-ttu-id="3a199-106">Há suporte para o cliente de email interno na maioria das plataformas.</span><span class="sxs-lookup"><span data-stu-id="3a199-106">The built-in mail client is supported for most platforms.</span></span> <span data-ttu-id="3a199-107">Atualmente, não há suporte para a maioria dos aplicativos de email de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3a199-107">Most third-party email apps are not currently supported.</span></span>

<span data-ttu-id="3a199-108">Você pode usar perfis de email para configurar o cliente de email nativo nos seguintes tipos de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3a199-108">You can use email profiles to configure the native email client on the following device types:</span></span>

- <span data-ttu-id="3a199-109">Android Samsung KNOX Standard 4.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="3a199-109">Android Samsung KNOX Standard 4.0 and later</span></span>
- <span data-ttu-id="3a199-110">Android for Work</span><span class="sxs-lookup"><span data-stu-id="3a199-110">Android for Work</span></span>
- <span data-ttu-id="3a199-111">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="3a199-111">iOS 8.0 and later</span></span>
- <span data-ttu-id="3a199-112">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="3a199-112">Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="3a199-113">Windows 10 (desktop) e Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="3a199-113">Windows 10 (desktop) and Windows 10 Mobile</span></span>

<span data-ttu-id="3a199-114">Use as informações neste tópico para aprender as noções básicas sobre a configuração de um perfil de email e leia mais tópicos para cada plataforma para saber mais sobre as especificações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a199-114">Use the information in this topic to learn the basics about configuring an email profile, and then read further topics for each platform to learn about device specifics.</span></span>

## <span data-ttu-id="3a199-115">Criar um perfil de dispositivo que contém configurações de email</span><span class="sxs-lookup"><span data-stu-id="3a199-115">Create a device profile containing email settings</span></span>
<a id="create-a-device-profile-containing-email-settings" class="xliff"></a>

1. <span data-ttu-id="3a199-116">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3a199-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="3a199-117">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="3a199-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="3a199-118">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="3a199-118">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="3a199-119">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="3a199-119">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="3a199-120">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="3a199-120">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="3a199-121">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de email.</span><span class="sxs-lookup"><span data-stu-id="3a199-121">On the **Create Profile** blade, enter a **Name** and **Description** for the email profile.</span></span>
5. <span data-ttu-id="3a199-122">Na lista suspensa **Plataforma**, selecione a plataforma do dispositivo ao qual você deseja aplicar as configurações de email.</span><span class="sxs-lookup"><span data-stu-id="3a199-122">From the **Platform** drop-down list, select the device platform to which you want to apply email settings.</span></span> <span data-ttu-id="3a199-123">No momento, é possível escolher uma das seguintes plataformas para as configurações de dispositivo de email:</span><span class="sxs-lookup"><span data-stu-id="3a199-123">Currently, you can choose one of the following platforms for email device settings:</span></span>
    - <span data-ttu-id="3a199-124">**Android** (somente Samsung Android KNOX Standard)</span><span class="sxs-lookup"><span data-stu-id="3a199-124">**Android** (Samsung Android KNOX Standard only)</span></span>
    - <span data-ttu-id="3a199-125">**Android for Work**</span><span class="sxs-lookup"><span data-stu-id="3a199-125">**Android for Work**</span></span>
    - <span data-ttu-id="3a199-126">**iOS**</span><span class="sxs-lookup"><span data-stu-id="3a199-126">**iOS**</span></span>
    - <span data-ttu-id="3a199-127">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="3a199-127">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="3a199-128">**Windows 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="3a199-128">**Windows 10 and later**</span></span>
6. <span data-ttu-id="3a199-129">Na lista suspensa de tipos de **Perfil**, escolha **Email**.</span><span class="sxs-lookup"><span data-stu-id="3a199-129">From the **Profile** type drop-down list, choose **Email**.</span></span>
7. <span data-ttu-id="3a199-130">Dependendo da plataforma escolhida, as configurações que podem ser definidas serão diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a199-130">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="3a199-131">Acesse um dos tópicos a seguir para ver as configurações detalhadas de cada plataforma:</span><span class="sxs-lookup"><span data-stu-id="3a199-131">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="3a199-132">Configurações do Android for Work e Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="3a199-132">Android for Work and Samsung KNOX Standard settings</span></span>](email-settings-android.md)
    - [<span data-ttu-id="3a199-133">Configurações do iOS</span><span class="sxs-lookup"><span data-stu-id="3a199-133">iOS settings</span></span>](email-settings-ios.md)
    - [<span data-ttu-id="3a199-134">Configurações do Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="3a199-134">Windows Phone 8.1 settings</span></span>](email-settings-windows-phone-8-1.md)
    - [<span data-ttu-id="3a199-135">Configurações do Windows 10</span><span class="sxs-lookup"><span data-stu-id="3a199-135">Windows 10 settings</span></span>](email-settings-windows-10.md)
8. <span data-ttu-id="3a199-136">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="3a199-136">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="3a199-137">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="3a199-137">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="3a199-138">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="3a199-138">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

## <span data-ttu-id="3a199-139">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="3a199-139">Further information</span></span>
<a id="further-information" class="xliff"></a>

### <span data-ttu-id="3a199-140">Remover um perfil de email</span><span class="sxs-lookup"><span data-stu-id="3a199-140">Remove an email profile</span></span>
<a id="remove-an-email-profile" class="xliff"></a>

<span data-ttu-id="3a199-141">Se você quiser remover um perfil de email de um dispositivo, edite a atribuição e remova todos os grupos dos quais o dispositivo é membro.</span><span class="sxs-lookup"><span data-stu-id="3a199-141">If you want to remove an email profile from a device, edit the assignment and remove any groups of which the device is a member.</span></span> <span data-ttu-id="3a199-142">Observe que você não poderá remover um perfil de email dessa forma se este for o único perfil de email em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a199-142">Note that you cannot remove an email profile in this way if it is the only email profile on a device.</span></span>

### <span data-ttu-id="3a199-143">Proteger o acesso ao email</span><span class="sxs-lookup"><span data-stu-id="3a199-143">Securing email access</span></span>
<a id="securing-email-access" class="xliff"></a>

<span data-ttu-id="3a199-144">Você pode ajudar a proteger os perfis de email usando um destes dois métodos:</span><span class="sxs-lookup"><span data-stu-id="3a199-144">You can help secure email profiles using one of two methods:</span></span>

1. <span data-ttu-id="3a199-145">**Certificados** – Ao criar o perfil de email, escolha um perfil de certificado criado anteriormente no Intune.</span><span class="sxs-lookup"><span data-stu-id="3a199-145">**Certificates** - When you create the email profile, you choose a certificate profile that you have previously created in Intune.</span></span> <span data-ttu-id="3a199-146">Ele é conhecido como certificado de identidade e é usado para autenticar em relação a um perfil de certificado confiável (ou um certificado raiz) para estabelecer que o dispositivo do usuário tem permissão para se conectar.</span><span class="sxs-lookup"><span data-stu-id="3a199-146">This is known as the identity certificate, and is used to authenticate against a trusted certificate profile (or a root certificate) to establish that the user’s device is allowed to connect.</span></span> <span data-ttu-id="3a199-147">O certificado confiável é atribuído no computador que autentica a conexão de email, em geral, o servidor de email nativo.</span><span class="sxs-lookup"><span data-stu-id="3a199-147">The trusted certificate is assigned to the computer that authenticates the email connection, typically, the native mail server.</span></span>
<span data-ttu-id="3a199-148">Para obter mais informações sobre como criar e usar perfis de certificado no Intune, consulte [Como configurar certificados com o Intune](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="3a199-148">For more information about how to create and use certificate profiles in Intune, see [How to configure certificates with Intune](certificates-configure.md).</span></span>
2. <span data-ttu-id="3a199-149">**Nome de usuário e senha** – O usuário se autentica no servidor de email nativo fornecendo seu nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="3a199-149">**User name and password** - The user authenticates to the native mail server by providing their user name and password.</span></span>
<span data-ttu-id="3a199-150">A senha não está contida no perfil do email, portanto o usuário deve fornecê-la ao se conectar ao email.</span><span class="sxs-lookup"><span data-stu-id="3a199-150">The password is not contained in the email profile, so the user needs to supply this when they connect to email.</span></span>


### <span data-ttu-id="3a199-151">Como o Intune lida com contas de email existentes</span><span class="sxs-lookup"><span data-stu-id="3a199-151">How Intune handles existing email accounts</span></span>
<a id="how-intune-handles-existing-email-accounts" class="xliff"></a>

<span data-ttu-id="3a199-152">Se o usuário já tiver configurado uma conta de email, o resultado da atribuição de perfil de email do Intune dependerá da plataforma do dispositivo:</span><span class="sxs-lookup"><span data-stu-id="3a199-152">If the user has already configured an email account, the result of the Intune email profile assignment depends on the device platform:</span></span>

- <span data-ttu-id="3a199-153">**iOS**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email.</span><span class="sxs-lookup"><span data-stu-id="3a199-153">**iOS:** An existing, duplicate email profile is detected based on host name and email address.</span></span> <span data-ttu-id="3a199-154">O perfil de email duplicado bloqueará a atribuição de um perfil do Intune.</span><span class="sxs-lookup"><span data-stu-id="3a199-154">The duplicate email profile will blocks the assignment of an Intune profile.</span></span> <span data-ttu-id="3a199-155">Nesse caso, o Portal da Empresa informa ao usuário que ele não está em conformidade e solicita que ele remova o perfil configurado manualmente.</span><span class="sxs-lookup"><span data-stu-id="3a199-155">In this case, the Company Portal informs the user that they are not compliant and prompts the user to remove the manually configured profile.</span></span> <span data-ttu-id="3a199-156">Para ajudar a evitar esse problema, instrua os usuários a se registrarem antes de instalar um perfil de email, permitindo que o Intune configure o perfil.</span><span class="sxs-lookup"><span data-stu-id="3a199-156">To help prevent this problem, instruct your users to enroll before installing an email profile, which allows Intune to set up the profile.</span></span>
- <span data-ttu-id="3a199-157">**Windows**: um perfil de email existente e duplicado é detectado com base no nome do host e no endereço de email.</span><span class="sxs-lookup"><span data-stu-id="3a199-157">**Windows:** An existing, duplicate email profile is detected based on host name and email address.</span></span> <span data-ttu-id="3a199-158">O Intune substitui o perfil de email existente criado pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="3a199-158">Intune overwrites the existing email profile created by the user.</span></span>
- <span data-ttu-id="3a199-159">**Android Samsung KNOX Standard** Um perfil de email existente e duplicado é detectado com base no endereço de email e é substituído pelo perfil do Intune.</span><span class="sxs-lookup"><span data-stu-id="3a199-159">**Android Samsung KNOX Standard** An existing, duplicate email profile is detected based on the email address, and overwrites it with the Intune profile.</span></span>
<span data-ttu-id="3a199-160">Como o Android não usa o nome do host para identificar o perfil, é recomendável que você não crie vários perfis de email para usar com o mesmo endereço de email em hosts diferentes, pois eles substituirão uns aos outros.</span><span class="sxs-lookup"><span data-stu-id="3a199-160">Since Android does not use host name to identify the profile, we recommend that you not create multiple email profiles to use on the same email address on different hosts, as these overwrite each other.</span></span>
- <span data-ttu-id="3a199-161">**Android for Work** O Intune fornece dois perfis de email do Android for Work, um para o aplicativo Gmail e outro para o Nine Work.</span><span class="sxs-lookup"><span data-stu-id="3a199-161">**Android for Work** Intune provides two Android for Work email profiles, one for each of the Gmail and Nine Work email apps.</span></span> <span data-ttu-id="3a199-162">Esses aplicativos estão disponíveis na Google Play Store e são instalados no perfil de trabalho do dispositivo, portanto não podem resultar em perfis duplicados.</span><span class="sxs-lookup"><span data-stu-id="3a199-162">These apps are available in the Google Play Store, and install in the device work profile, so they can't result in duplicate profiles.</span></span> <span data-ttu-id="3a199-163">Os dois aplicativos oferecem suporte a conexões com o Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a199-163">Both apps support connections to Exchange.</span></span> <span data-ttu-id="3a199-164">Para habilitar a conectividade de email, implante um desses aplicativos de email nos dispositivos dos usuários e crie e implante o perfil de email apropriado.</span><span class="sxs-lookup"><span data-stu-id="3a199-164">To enable the email connectivity, deploy one of these email apps to your users' devices, and then create and deploy the appropriate email profile.</span></span> <span data-ttu-id="3a199-165">Aplicativos de email, como o Nine Work podem não ser gratuitos.</span><span class="sxs-lookup"><span data-stu-id="3a199-165">Email apps such as Nine Work might not be free.</span></span> <span data-ttu-id="3a199-166">Examine os detalhes de licenciamento do aplicativo ou entre em contato com a empresa do aplicativo com quaisquer perguntas.</span><span class="sxs-lookup"><span data-stu-id="3a199-166">Review the app’s licensing details or contact the app company with any questions.</span></span>

### <span data-ttu-id="3a199-167">Atualizar um perfil de email</span><span class="sxs-lookup"><span data-stu-id="3a199-167">Update an email profile</span></span>
<a id="update-an-email-profile" class="xliff"></a>

<span data-ttu-id="3a199-168">Se você fizer alterações em um perfil de email atribuído anteriormente, os usuários finais poderão ver uma mensagem solicitando a aprovação da reconfiguração de suas configurações de email.</span><span class="sxs-lookup"><span data-stu-id="3a199-168">If you make changes to an email profile you previously assigned, end users might see a message asking them to approve the reconfiguration of their email settings.</span></span>
