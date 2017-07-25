---
title: Como configurar certificados com o Intune
titleSuffix: Intune on Azure
description: "Saiba como usar o Intune para criar e atribuir certificados que ajudam você a proteger conexões Wi-Fi, VPN e outras."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da23a0c79c5e0e178e52e956561e2764268d09df
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="304ee-103">Como configurar certificados no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-103">How to configure certificates in Microsoft Intune</span></span>
<a id="how-to-configure-certificates-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="304ee-104">Ao conceder aos usuários acesso a recursos corporativos por meio de VPN, Wi-Fi ou perfis de email, você pode autenticar essas conexões usando certificados.</span><span class="sxs-lookup"><span data-stu-id="304ee-104">When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can authenticate these connections by using certificates.</span></span> <span data-ttu-id="304ee-105">Eles eliminam a necessidade para inserir nomes de usuário e senhas para autenticar conexões.</span><span class="sxs-lookup"><span data-stu-id="304ee-105">These remove the need to enter user names and passwords to authenticate connections.</span></span>

<span data-ttu-id="304ee-106">Use o Intune para atribuir esses certificados aos dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="304ee-106">You can use Intune to assign these certificates to devices you manage.</span></span> <span data-ttu-id="304ee-107">O Intune dá suporte à atribuição e gerenciamento desses tipos de certificados:</span><span class="sxs-lookup"><span data-stu-id="304ee-107">Intune supports assigning and managing these certificate types:</span></span>

- <span data-ttu-id="304ee-108">Protocolo SCEP</span><span class="sxs-lookup"><span data-stu-id="304ee-108">Simple Certificate Enrollment Protocol (SCEP)</span></span>
- <span data-ttu-id="304ee-109">PKCS#12 (ou PFX)</span><span class="sxs-lookup"><span data-stu-id="304ee-109">PKCS#12 (or PFX)</span></span>

<span data-ttu-id="304ee-110">Cada um desses tipos de certificado tem seus próprios pré-requisitos e requisitos de infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="304ee-110">Each of these certificate types has it's own prerequisites, and infrastructure requirements.</span></span>

## <span data-ttu-id="304ee-111">Fluxo de trabalho geral</span><span class="sxs-lookup"><span data-stu-id="304ee-111">General workflow</span></span>
<a id="general-workflow" class="xliff"></a>

1. <span data-ttu-id="304ee-112">Verifique se você tem a infraestrutura de certificado correta em vigor.</span><span class="sxs-lookup"><span data-stu-id="304ee-112">Ensure you have the right certificate infrastructure in place.</span></span> <span data-ttu-id="304ee-113">Você pode usar os [Certificados SCEP](certificates-scep-configure.md) e os [Certificados PKCS](certficates-pfx-configure.md).</span><span class="sxs-lookup"><span data-stu-id="304ee-113">You can use [SCEP certificates](certificates-scep-configure.md), and [PKCS certificates](certficates-pfx-configure.md).</span></span>
2. <span data-ttu-id="304ee-114">Instale um certificado raiz ou um certificado de CA (Autoridade de Certificação) intermediário em cada dispositivo para que o dispositivo reconheça a legitimidade da autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="304ee-114">Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA.</span></span> <span data-ttu-id="304ee-115">Para fazer isso, crie e atribua um **perfil de certificado confiável**.</span><span class="sxs-lookup"><span data-stu-id="304ee-115">To do this, create and assign a **trusted certificate profile**.</span></span> <span data-ttu-id="304ee-116">Quando você atribui esse perfil, os dispositivos que você gerencia com o Intune solicitarão e receberão o certificado raiz.</span><span class="sxs-lookup"><span data-stu-id="304ee-116">When you assign this profile, the devices that you manage with Intune will request and receive the root certificate.</span></span> <span data-ttu-id="304ee-117">Você precisa criar um perfil separado para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="304ee-117">You have to create a separate profile for each platform.</span></span> <span data-ttu-id="304ee-118">Perfis de certificado confiável estão disponíveis para as seguintes plataformas:</span><span class="sxs-lookup"><span data-stu-id="304ee-118">Trusted certificate profiles are available for these platforms:</span></span>
    - <span data-ttu-id="304ee-119">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-119">iOS 8.0 and later</span></span>
    - <span data-ttu-id="304ee-120">macOS 10.9 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-120">macOS 10.9 and later</span></span>
    - <span data-ttu-id="304ee-121">Android 4.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-121">Android 4.0 and later</span></span>
    - <span data-ttu-id="304ee-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="304ee-122">Android for Work</span></span>
    - <span data-ttu-id="304ee-123">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-123">Windows 8.1 and later</span></span>
    - <span data-ttu-id="304ee-124">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-124">Windows Phone 8.1 and later</span></span>
    - <span data-ttu-id="304ee-125">Windows 10 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-125">Windows 10 and later</span></span>
3. <span data-ttu-id="304ee-126">Crie perfis de certificado para que os dispositivos solicitem um certificado a ser usado para autenticação de VPN, Wi-Fi e acesso por email.</span><span class="sxs-lookup"><span data-stu-id="304ee-126">Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access.</span></span> <span data-ttu-id="304ee-127">Você pode criar e atribuir um perfil de certificado **PKCS** ou **SCEP** para dispositivos em execução nestas plataformas:</span><span class="sxs-lookup"><span data-stu-id="304ee-127">You can create and assign a **PKCS** or a **SCEP** certificate profile for devices running these platforms:</span></span>
    - <span data-ttu-id="304ee-128">iOS 8.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-128">iOS 8.0 and later</span></span>
    - <span data-ttu-id="304ee-129">Android 4.0 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-129">Android 4.0 and later</span></span>
    - <span data-ttu-id="304ee-130">Android for Work</span><span class="sxs-lookup"><span data-stu-id="304ee-130">Android for Work</span></span>
    - <span data-ttu-id="304ee-131">Windows 10 (Desktop e Mobile) e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-131">Windows 10 (desktop and mobile) and later</span></span>

    <span data-ttu-id="304ee-132">Somente é possível usar um perfil de certificado SCEP nestas plataformas:</span><span class="sxs-lookup"><span data-stu-id="304ee-132">You can only use a SCEP certificate profile with these platforms:</span></span>

-   <span data-ttu-id="304ee-133">macOS 10.9 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-133">macOS 10.9 and later</span></span>
-   <span data-ttu-id="304ee-134">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="304ee-134">Windows Phone 8.1 and later</span></span>

<span data-ttu-id="304ee-135">Você deve criar um perfil separado para cada plataforma de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="304ee-135">You must create a separate profile for each device platform.</span></span> <span data-ttu-id="304ee-136">Ao criar o perfil, associe-o ao perfil de certificado raiz confiável já criado.</span><span class="sxs-lookup"><span data-stu-id="304ee-136">When you create the profile, associate it with the trusted root certificate profile that you've already created.</span></span>

### <span data-ttu-id="304ee-137">Considerações adicionais</span><span class="sxs-lookup"><span data-stu-id="304ee-137">Further considerations</span></span>
<a id="further-considerations" class="xliff"></a>

- <span data-ttu-id="304ee-138">Se não tiver uma Autoridade de Certificação Corporativa, você precisará criar uma.</span><span class="sxs-lookup"><span data-stu-id="304ee-138">If you don't have an Enterprise Certification Authority, you must create one.</span></span>
- <span data-ttu-id="304ee-139">Com base em suas plataformas de dispositivo, se decidir usar o perfil de SCEP (Protocolo de Registro de Certificado Simplificado), você também precisará configurar um NDES (Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="304ee-139">If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.</span></span>
- <span data-ttu-id="304ee-140">Se você planeja usar perfis SCEP ou PKCS, precisará baixar e configurar o Microsoft Intune Certificate Connector.</span><span class="sxs-lookup"><span data-stu-id="304ee-140">Whether you plan to use SCEP or PKCS profiles, you must download and configure the Microsoft Intune Certificate Connector.</span></span>


## <span data-ttu-id="304ee-141">Etapa 1 - configurar a infraestrutura de certificado</span><span class="sxs-lookup"><span data-stu-id="304ee-141">Step 1- Configure your certificate infrastructure</span></span>
<a id="step-1--configure-your-certificate-infrastructure" class="xliff"></a>

<span data-ttu-id="304ee-142">Consulte um dos tópicos a seguir para ajudar a configurar a infraestrutura para cada tipo de perfil de certificado:</span><span class="sxs-lookup"><span data-stu-id="304ee-142">See one of the following topics for help configuring the infrastructure for each type of certificate profile:</span></span>

- [<span data-ttu-id="304ee-143">Configurar e gerenciar certificados SCEP com o Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-143">Configure and manage SCEP certificates with Intune</span></span>](certificates-scep-configure.md)
- [<span data-ttu-id="304ee-144">Configurar e gerenciar certificados PKCS com o Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-144">Configure and manage PKCS certificates with Intune</span></span>](certficates-pfx-configure.md)


## <span data-ttu-id="304ee-145">Etapa 2 - exportar o certificado de AC raiz confiável</span><span class="sxs-lookup"><span data-stu-id="304ee-145">Step 2 - Export your trusted root CA certificate</span></span>
<a id="step-2---export-your-trusted-root-ca-certificate" class="xliff"></a>

<span data-ttu-id="304ee-146">Exporte o certificado de AC (Autoridade de Certificação) Raiz Confiável como um arquivo **.cer** da autoridade de certificação emissora ou de qualquer dispositivo que confie em sua autoridade de certificação emissora.</span><span class="sxs-lookup"><span data-stu-id="304ee-146">Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA.</span></span> <span data-ttu-id="304ee-147">Não exporte a chave privada.</span><span class="sxs-lookup"><span data-stu-id="304ee-147">Do not export the private key.</span></span>

<span data-ttu-id="304ee-148">Ao configurar um perfil de certificado confiável, você importará esse certificado.</span><span class="sxs-lookup"><span data-stu-id="304ee-148">You'll import this certificate when you set up a trusted certificate profile.</span></span>

## <span data-ttu-id="304ee-149">Etapa 3: criar perfis de certificado confiável</span><span class="sxs-lookup"><span data-stu-id="304ee-149">Step 3: Create trusted certificate profiles</span></span>
<a id="step-3-create-trusted-certificate-profiles" class="xliff"></a>
<span data-ttu-id="304ee-150">Você deverá criar um perfil de certificado confiável antes de criar um perfil de certificado SCEP ou PKCS.</span><span class="sxs-lookup"><span data-stu-id="304ee-150">You must create a trusted certificate profile before you can create a SCEP or PKCS certificate profile.</span></span> <span data-ttu-id="304ee-151">Você precisa de um perfil de certificado confiável e um perfil SCEP ou PKCS para cada plataforma de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="304ee-151">You need a trusted certificate profile and a SCEP or PKCS profile for each device platform.</span></span> <span data-ttu-id="304ee-152">O fluxo para a criação de certificados confiáveis é semelhante para cada plataforma de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="304ee-152">The flow for creating trusted certificates is similar for each device platform.</span></span>

### <span data-ttu-id="304ee-153">Para criar um perfil de certificado confiável</span><span class="sxs-lookup"><span data-stu-id="304ee-153">To create a trusted certificate profile</span></span>
<a id="to-create-a-trusted-certificate-profile" class="xliff"></a>

1. <span data-ttu-id="304ee-154">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="304ee-154">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="304ee-155">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="304ee-155">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="304ee-156">Na folha **Intune**, escolha **Configuração do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="304ee-156">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="304ee-157">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="304ee-157">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="304ee-158">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="304ee-158">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="304ee-159">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado confiável.</span><span class="sxs-lookup"><span data-stu-id="304ee-159">On the **Create Profile** blade, enter a **Name** and **Description** for the trusted certificate profile.</span></span>
5. <span data-ttu-id="304ee-160">Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado confiável.</span><span class="sxs-lookup"><span data-stu-id="304ee-160">From the **Platform** drop-down list, select the device platform for this trusted certificate.</span></span> <span data-ttu-id="304ee-161">No momento, é possível escolher uma das seguintes plataformas para as configurações de certificado:</span><span class="sxs-lookup"><span data-stu-id="304ee-161">Currently, you can choose one of the following platforms for certificate settings:</span></span>
    - <span data-ttu-id="304ee-162">**Android**</span><span class="sxs-lookup"><span data-stu-id="304ee-162">**Android**</span></span>
    - <span data-ttu-id="304ee-163">**iOS**</span><span class="sxs-lookup"><span data-stu-id="304ee-163">**iOS**</span></span>
    - <span data-ttu-id="304ee-164">**macOS**</span><span class="sxs-lookup"><span data-stu-id="304ee-164">**macOS**</span></span>
    - <span data-ttu-id="304ee-165">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="304ee-165">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="304ee-166">**Windows 8.1 e posterior**</span><span class="sxs-lookup"><span data-stu-id="304ee-166">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="304ee-167">**Windows 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="304ee-167">**Windows 10 and later**</span></span>
6. <span data-ttu-id="304ee-168">Na lista suspensa de **Tipo de perfil**, escolha **Certificado confiável**.</span><span class="sxs-lookup"><span data-stu-id="304ee-168">From the **Profile type** type drop-down list, choose **Trusted certificate**.</span></span>
7. <span data-ttu-id="304ee-169">Navegue até o certificado salvo na tarefa 1 e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="304ee-169">Browse to the certificate you saved in task 1, then click **OK**.</span></span>
8. <span data-ttu-id="304ee-170">Somente para dispositivos Windows 8.1 e Windows 10, selecione o **Repositório de Destino** para o certificado confiável de:</span><span class="sxs-lookup"><span data-stu-id="304ee-170">For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate from:</span></span>
    - <span data-ttu-id="304ee-171">**Repositório de certificados do computador – Raiz**</span><span class="sxs-lookup"><span data-stu-id="304ee-171">**Computer certificate store - Root**</span></span>
    - <span data-ttu-id="304ee-172">**Repositório de certificados do computador – Intermediário**</span><span class="sxs-lookup"><span data-stu-id="304ee-172">**Computer certificate store - Intermediate**</span></span>
    - <span data-ttu-id="304ee-173">**Repositório de certificados do usuário – Intermediário**</span><span class="sxs-lookup"><span data-stu-id="304ee-173">**User certificate store - Intermediate**</span></span>
8. <span data-ttu-id="304ee-174">Após terminar, escolha **OK**, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="304ee-174">When you're done, choose **OK**, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="304ee-175">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="304ee-175">The profile will be created and appears on the profiles list blade.</span></span>

<span data-ttu-id="304ee-176">Se você desejar atribuir esse perfil aos grupos, consulte [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="304ee-176">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>


> [!Note]
> <span data-ttu-id="304ee-177">Dispositivos Android exibirão um aviso de que terceiros instalaram um certificado confiável.</span><span class="sxs-lookup"><span data-stu-id="304ee-177">Android devices will display a notice that a third party has installed a trusted certificate.</span></span>

## <span data-ttu-id="304ee-178">Etapa 4: criar perfis de certificado SCEP ou PKCS</span><span class="sxs-lookup"><span data-stu-id="304ee-178">Step 4: Create SCEP or PKCS certificate profiles</span></span>
<a id="step-4-create-scep-or-pkcs-certificate-profiles" class="xliff"></a>

<span data-ttu-id="304ee-179">Consulte um dos tópicos a seguir para ajudar a configurar e atribuir cada tipo de perfil de certificado:</span><span class="sxs-lookup"><span data-stu-id="304ee-179">See one of the following topics for help configuring and assigning each type of certificate profile:</span></span>

- [<span data-ttu-id="304ee-180">Configurar e gerenciar certificados SCEP com o Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-180">Configure and manage SCEP certificates with Intune</span></span>](certificates-scep-configure.md)
- [<span data-ttu-id="304ee-181">Configurar e gerenciar certificados PKCS com o Intune</span><span class="sxs-lookup"><span data-stu-id="304ee-181">Configure and manage PKCS certificates with Intune</span></span>](certficates-pfx-configure.md)

<span data-ttu-id="304ee-182">Depois de criar um perfil de certificado confiável, crie perfis de certificado SCEP ou PKCS para cada plataforma que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="304ee-182">After you create a trusted certificate profile, create SCEP or PKCS certificate profiles for each platform you want to use.</span></span> <span data-ttu-id="304ee-183">Quando você cria um perfil de certificado SCEP, deverá especificar um perfil de certificado confiável para essa mesma plataforma.</span><span class="sxs-lookup"><span data-stu-id="304ee-183">When you create a SCEP certificate profile, you must specify a trusted certificate profile for that same platform.</span></span> <span data-ttu-id="304ee-184">Isso vincula os dois perfis de certificado, mas você ainda deve atribuir cada perfil separadamente.</span><span class="sxs-lookup"><span data-stu-id="304ee-184">This links the two certificate profiles, but you still must assign each profile separately.</span></span>


## <span data-ttu-id="304ee-185">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="304ee-185">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="304ee-186">Consulte [Como atribuir perfis de dispositivo](device-profile-assign.md) para obter informações gerais sobre como atribuir perfis de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="304ee-186">See [How to assign device profiles](device-profile-assign.md) for general information about how to assign device profiles.</span></span>
