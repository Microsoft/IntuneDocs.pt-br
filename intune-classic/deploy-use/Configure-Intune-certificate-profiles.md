---
title: Configurar perfis de certificado
description: Saiba como criar um perfil de certificado do Intune.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: aaf7bf3cb05708457c57070f4a300ece987421c3
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="42194-103">Configurar perfis de certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="42194-103">Configure Intune certificate profiles</span></span>
<a id="configure-intune-certificate-profiles" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="42194-104">Depois de configurar a infraestrutura e os certificados conforme descrito em [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) (Configurar infraestrutura de certificado para SCEP) ou [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md) (Configurar a infraestrutura de certificado para PFX), você pode criar perfis de certificado.</span><span class="sxs-lookup"><span data-stu-id="42194-104">After you've configured your infrastructure and certificates as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md), you can create certificate profiles.</span></span> <span data-ttu-id="42194-105">Este é o processo:</span><span class="sxs-lookup"><span data-stu-id="42194-105">Here's the process:</span></span>

- <span data-ttu-id="42194-106">**Tarefa 1**: exportar o certificado de AC Raiz Confiável</span><span class="sxs-lookup"><span data-stu-id="42194-106">**Task 1**: Export the Trusted Root CA certificate</span></span>
- <span data-ttu-id="42194-107">**Tarefa 2**: criar perfis de certificado Confiável</span><span class="sxs-lookup"><span data-stu-id="42194-107">**Task 2**: Create Trusted certificate profiles</span></span>
- <span data-ttu-id="42194-108">**Tarefa 3**: criar um dos dois tipos de perfil de certificado:</span><span class="sxs-lookup"><span data-stu-id="42194-108">**Task 3**: Create one of two certificate profile types:</span></span>
  - <span data-ttu-id="42194-109">Perfis de certificado SCEP</span><span class="sxs-lookup"><span data-stu-id="42194-109">SCEP certificate profiles</span></span>
  - <span data-ttu-id="42194-110">Perfis de certificado .PFX</span><span class="sxs-lookup"><span data-stu-id="42194-110">.PFX certificate profiles</span></span>

## <span data-ttu-id="42194-111">**Tarefa 1**: exportar o certificado de AC Raiz Confiável</span><span class="sxs-lookup"><span data-stu-id="42194-111">**Task 1**: Export the Trusted Root CA certificate</span></span>
<a id="task-1-export-the-trusted-root-ca-certificate" class="xliff"></a>
<span data-ttu-id="42194-112">Exporte o certificado de AC (Autoridade de Certificação) Raiz Confiável como um arquivo **.cer** da autoridade de certificação emissora ou de qualquer dispositivo que confie em sua autoridade de certificação emissora.</span><span class="sxs-lookup"><span data-stu-id="42194-112">Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA.</span></span> <span data-ttu-id="42194-113">Não exporte a chave privada.</span><span class="sxs-lookup"><span data-stu-id="42194-113">Do not export the private key.</span></span>

<span data-ttu-id="42194-114">Ao configurar um perfil de certificado confiável, você importará esse certificado.</span><span class="sxs-lookup"><span data-stu-id="42194-114">You'll import this certificate when you set up a Trusted certificate profile.</span></span>

## <span data-ttu-id="42194-115">**Tarefa 2**: criar perfis de certificado Confiável</span><span class="sxs-lookup"><span data-stu-id="42194-115">**Task 2**: Create Trusted certificate profiles</span></span>
<a id="task-2-create-trusted-certificate-profiles" class="xliff"></a>
<span data-ttu-id="42194-116">Você deve criar um perfil de certificado Confiável para poder criar um protocolo de registro de certificado simples (SCEP) ou um perfil de certificado PKCS #12 (.PFX).</span><span class="sxs-lookup"><span data-stu-id="42194-116">You must create a Trusted certificate profile before you can create a Simple Certificate Enrollment Protocol (SCEP) or a PKCS #12 (.PFX) certificate profile.</span></span> <span data-ttu-id="42194-117">Você precisa de um perfil de certificado confiável e um perfil SCEP ou .PFX para cada plataforma de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="42194-117">You need a Trusted certificate profile and an SCEP or .PFX profile for each mobile device platform.</span></span>

### <span data-ttu-id="42194-118">Para criar um perfil de certificado Confiável</span><span class="sxs-lookup"><span data-stu-id="42194-118">To create a Trusted certificate profile</span></span>
<a id="to-create-a-trusted-certificate-profile" class="xliff"></a>

1.  <span data-ttu-id="42194-119">No [Console de administração do Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política** e selecione uma plataforma de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42194-119">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**, and choose a device platform.</span></span> <span data-ttu-id="42194-120">É possível criar um perfil de certificado confiável para os seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="42194-120">You can create a trusted certificate profile for these devices:</span></span>

-  <span data-ttu-id="42194-121">Android 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-121">Android 4 and later</span></span>

-  <span data-ttu-id="42194-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="42194-122">Android for Work</span></span>

-  <span data-ttu-id="42194-123">iOS 7.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-123">iOS 7.1 and later</span></span>

-  <span data-ttu-id="42194-124">Mac OS X 10.9 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-124">Mac OS X 10.9 and later</span></span>

-  <span data-ttu-id="42194-125">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-125">Windows 8.1 and later</span></span>

-  <span data-ttu-id="42194-126">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-126">Windows Phone 8.1 and later</span></span>

2.  <span data-ttu-id="42194-127">Adicione uma política de **Perfil de Certificado Confiável**.</span><span class="sxs-lookup"><span data-stu-id="42194-127">Add a **Trusted Certificate Profile** policy.</span></span>

    <span data-ttu-id="42194-128">Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="42194-128">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

3.  <span data-ttu-id="42194-129">Insira as informações solicitadas para definir as configurações de perfil de certificado Confiável para Android, iOS, Mac OS X, Windows 8.1 ou Windows Phone 8.1.</span><span class="sxs-lookup"><span data-stu-id="42194-129">Enter the requested information to configure the Trusted certificate profile settings for Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1.</span></span>
4.  <span data-ttu-id="42194-130">Na configuração **Arquivo de certificado**, importe o Certificado de AC raiz confiável (arquivo .cer) que você exportou da AC emissora.</span><span class="sxs-lookup"><span data-stu-id="42194-130">In the **Certificate file** setting, import the Trusted Root CA certificate (.cer file) that you exported from your issuing CA.</span></span> <span data-ttu-id="42194-131">A configuração **Repositório de destino** se aplica apenas aos dispositivos que executam o Windows 8.1 e posterior e apenas se o dispositivo tiver mais de um repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="42194-131">The **Destination store** setting applies only to devices running Windows 8.1 and later, and only if the device has more than one certificate store.</span></span>

4.  <span data-ttu-id="42194-132">Escolha **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="42194-132">Choose **Save Policy**.</span></span>

<span data-ttu-id="42194-133">A nova política é mostrada no espaço de trabalho **Política**.</span><span class="sxs-lookup"><span data-stu-id="42194-133">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="42194-134">Agora você pode implantá-la.</span><span class="sxs-lookup"><span data-stu-id="42194-134">Now you can deploy it.</span></span>

> [!NOTE]
>
> <span data-ttu-id="42194-135">Dispositivos Android e Android for Work exibirão um aviso de que terceiros instalaram um certificado confiável.</span><span class="sxs-lookup"><span data-stu-id="42194-135">Android and Android for Work devices will display a notice that a third party has installed a trusted certificate.</span></span>


## <span data-ttu-id="42194-136">**Tarefa 3**: criar perfis de certificado SCEP ou .PFX</span><span class="sxs-lookup"><span data-stu-id="42194-136">**Task 3**: Create SCEP or .PFX certificate profiles</span></span>
<a id="task-3-create-scep-or-pfx-certificate-profiles" class="xliff"></a>
<span data-ttu-id="42194-137">Depois de criar um perfil de certificado de Autoridade de Certificação confiável, crie perfis de certificado SCEP ou .PFX para cada plataforma que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="42194-137">After you create a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use.</span></span> <span data-ttu-id="42194-138">Quando você cria um perfil de certificado SCEP, deve especificar um perfil de certificado confiável para essa mesma plataforma.</span><span class="sxs-lookup"><span data-stu-id="42194-138">When you create an SCEP certificate profile, you must specify a Trusted certificate profile for that same platform.</span></span> <span data-ttu-id="42194-139">Isso vincula os dois perfis de certificado, mas você ainda deve implantar cada perfil separadamente.</span><span class="sxs-lookup"><span data-stu-id="42194-139">This links the two certificate profiles, but you still must deploy each profile separately.</span></span>

### <span data-ttu-id="42194-140">Para criar um perfil de certificado SCEP</span><span class="sxs-lookup"><span data-stu-id="42194-140">To create an SCEP certificate profile</span></span>
<a id="to-create-an-scep-certificate-profile" class="xliff"></a>

1.  <span data-ttu-id="42194-141">No [Console de administração do Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política** e selecione uma plataforma de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42194-141">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy** and choose a device platform.</span></span>  <span data-ttu-id="42194-142">É possível criar um perfil de certificado SCEP para os seguintes dispositivos:</span><span class="sxs-lookup"><span data-stu-id="42194-142">You can create a SCEP certificate profile for these devices:</span></span>

-  <span data-ttu-id="42194-143">Android 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-143">Android 4 and later</span></span>

-  <span data-ttu-id="42194-144">Android for Work</span><span class="sxs-lookup"><span data-stu-id="42194-144">Android for Work</span></span>

-  <span data-ttu-id="42194-145">iOS 7.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-145">iOS 7.1 and later</span></span>

-  <span data-ttu-id="42194-146">Mac OS X 10.9 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-146">Mac OS X 10.9 and later</span></span>

-  <span data-ttu-id="42194-147">Windows 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-147">Windows 8.1 and later</span></span>

-  <span data-ttu-id="42194-148">Windows Phone 8.1 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-148">Windows Phone 8.1 and later</span></span>

2.  <span data-ttu-id="42194-149">Adicione uma política de **Perfil de Certificado SCEP**</span><span class="sxs-lookup"><span data-stu-id="42194-149">Add a **SCEP Certificate Profile** policy</span></span>

    <span data-ttu-id="42194-150">Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="42194-150">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

3.  <span data-ttu-id="42194-151">Siga as instruções na página de configuração do perfil para definir as configurações de perfil de certificado SCEP.</span><span class="sxs-lookup"><span data-stu-id="42194-151">Follow the instructions on the profile configuration page to configure the SCEP certificate profile settings.</span></span>
    > [!NOTE]
    >
    > <span data-ttu-id="42194-152">Em **Formato de nome da entidade**, selecione **Personalizado** para inserir um formato de nome da entidade personalizado (somente em perfis do iOS).</span><span class="sxs-lookup"><span data-stu-id="42194-152">Under **Subject name format**, select **Custom** to enter a custom subject name format (in iOS profiles, only).</span></span>
    >
    > <span data-ttu-id="42194-153">As duas variáveis que atualmente têm suporte para o formato personalizado são `Common Name (CN)` e `Email (E)`.</span><span class="sxs-lookup"><span data-stu-id="42194-153">The two variables currently supported for the custom format are `Common Name (CN)` and `Email (E)`.</span></span> <span data-ttu-id="42194-154">Usando uma combinação dessas variáveis e cadeias de caracteres estáticas, você pode criar um formato de nome de entidade personalizado, como este:</span><span class="sxs-lookup"><span data-stu-id="42194-154">By using a combination of these variables and static strings, you can create a custom subject name format, like this one:</span></span>

    >     <span data-ttu-id="42194-155">CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US</span><span class="sxs-lookup"><span data-stu-id="42194-155">CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US</span></span>

    > <span data-ttu-id="42194-156">No exemplo, o administrador criou um formato de nome de entidade que, além das variáveis `CN` e `E`, usa cadeias de caracteres para os valores de Unidade Organizacional, Organização, Local, Estado e País.</span><span class="sxs-lookup"><span data-stu-id="42194-156">In this example, the admin created a subject name format that, in addition to the `CN` and `E` variables, uses strings for Organizational Unit, Organization, Location, State, and Country values.</span></span> <span data-ttu-id="42194-157">[Função CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) listas cadeias de caracteres com suporte.</span><span class="sxs-lookup"><span data-stu-id="42194-157">[CertStrToName function](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) lists supported strings.</span></span>

4.  <span data-ttu-id="42194-158">Escolha **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="42194-158">Choose **Save Policy**.</span></span>

<span data-ttu-id="42194-159">A nova política é mostrada no espaço de trabalho **Política**.</span><span class="sxs-lookup"><span data-stu-id="42194-159">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="42194-160">Agora você pode implantá-la.</span><span class="sxs-lookup"><span data-stu-id="42194-160">Now you can deploy it.</span></span>

### <span data-ttu-id="42194-161">Para criar um perfil de certificado .PFX</span><span class="sxs-lookup"><span data-stu-id="42194-161">To create a .PFX certificate profile</span></span>
<a id="to-create-a-pfx-certificate-profile" class="xliff"></a>

1.  <span data-ttu-id="42194-162">No [Console de administração do Intune](https://manage.microsoft.com), escolha **Política** &gt; **Adicionar Política** e selecione uma plataforma de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42194-162">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**, and choose a device platform.</span></span> <span data-ttu-id="42194-163">Há suporte para os certificados .PFX nos seguintes sistemas operacionais:</span><span class="sxs-lookup"><span data-stu-id="42194-163">.PFX certificates are supported for:</span></span>
  - <span data-ttu-id="42194-164">Android 4 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-164">Android 4 and later</span></span>
  - <span data-ttu-id="42194-165">Android for Work</span><span class="sxs-lookup"><span data-stu-id="42194-165">Android for Work</span></span>
  - <span data-ttu-id="42194-166">Windows 10 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-166">Windows 10 and later</span></span>
  - <span data-ttu-id="42194-167">Windows Phone 10 e posterior</span><span class="sxs-lookup"><span data-stu-id="42194-167">Windows Phone 10 and later</span></span>
  - <span data-ttu-id="42194-168">iOS 8.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="42194-168">iOS 8.0 and later)</span></span>    


2.  <span data-ttu-id="42194-169">Adicione uma política de **Perfil de Certificado .PFX**.</span><span class="sxs-lookup"><span data-stu-id="42194-169">Add a **.PFX Certificate Profile** policy.</span></span>
      <span data-ttu-id="42194-170">Saiba mais: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md) (Gerenciar configurações e funcionalidades em seus dispositivos com políticas do Microsoft Intune).</span><span class="sxs-lookup"><span data-stu-id="42194-170">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>
3.  <span data-ttu-id="42194-171">Insira as informações solicitadas no formulário de política.</span><span class="sxs-lookup"><span data-stu-id="42194-171">Enter the information requested on the policy form.</span></span>
4.  <span data-ttu-id="42194-172">Escolha **Salvar Política**.</span><span class="sxs-lookup"><span data-stu-id="42194-172">Choose **Save Policy**.</span></span>

<span data-ttu-id="42194-173">A nova política é mostrada no espaço de trabalho **Política**.</span><span class="sxs-lookup"><span data-stu-id="42194-173">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="42194-174">Agora você pode implantá-la.</span><span class="sxs-lookup"><span data-stu-id="42194-174">Now you can deploy it.</span></span>

## <span data-ttu-id="42194-175">Implantar perfis de certificado</span><span class="sxs-lookup"><span data-stu-id="42194-175">Deploy certificate profiles</span></span>
<a id="deploy-certificate-profiles" class="xliff"></a>
<span data-ttu-id="42194-176">Quando você implanta perfis de certificado, o arquivo de certificado do perfil de certificado de Autoridade de Certificação Confiável é instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42194-176">When you deploy certificate profiles, the certificate file from the Trusted CA certificate profile is installed on the device.</span></span> <span data-ttu-id="42194-177">O dispositivo usa o protocolo SCEP ou. o perfil de certificado .PFX para criar uma solicitação de certificado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="42194-177">The device uses the SCEP or .PFX certificate profile to create a certificate request by the device.</span></span>

<span data-ttu-id="42194-178">Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.</span><span class="sxs-lookup"><span data-stu-id="42194-178">Certificate profiles install only on devices running the platform you use when you create the profile.</span></span>

-   <span data-ttu-id="42194-179">Você pode implantar perfis de certificado para coleções de usuários ou coleções de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="42194-179">You can deploy certificate profiles to user collections or to device collections.</span></span>

    > [!TIP]
    > <span data-ttu-id="42194-180">Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, implante o perfil de certificado para um grupo de usuários em vez de um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="42194-180">To publish a certificate to a device quickly after the device enrolls, deploy the certificate profile to a user group rather than to a device group.</span></span> <span data-ttu-id="42194-181">Se você implantar um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.</span><span class="sxs-lookup"><span data-stu-id="42194-181">If you deploy to a device group, a full device registration is required before the device receives policies.</span></span>

-   <span data-ttu-id="42194-182">Embora você implante cada perfil separadamente, também precisa implantar a Autoridade de Certificação Raiz Confiável e o protocolo SCEP ou o perfil .PFX.</span><span class="sxs-lookup"><span data-stu-id="42194-182">Although you deploy each profile separately, you also need to deploy the Trusted Root CA and the SCEP or .PFX profile.</span></span> <span data-ttu-id="42194-183">Caso contrário, a política de certificado SCEP ou .PFX falhará.</span><span class="sxs-lookup"><span data-stu-id="42194-183">Otherwise, the SCEP or .PFX certificate policy will fail.</span></span>

<span data-ttu-id="42194-184">Implante os perfis de certificado da mesma maneira que implanta outras políticas para o Intune:</span><span class="sxs-lookup"><span data-stu-id="42194-184">Deploy certificate profiles the same way you deploy other policies for Intune:</span></span>

1.  <span data-ttu-id="42194-185">No espaço de trabalho **Política**, selecione a política que deseja implantar e selecione **Gerenciar Implantação**.</span><span class="sxs-lookup"><span data-stu-id="42194-185">In the **Policy** workspace, select the policy you want to deploy, and then choose **Manage Deployment**.</span></span>
2.  <span data-ttu-id="42194-186">Na caixa de diálogo **Gerenciar implantação**:</span><span class="sxs-lookup"><span data-stu-id="42194-186">In the **Manage Deployment** dialog box:</span></span>
    -   <span data-ttu-id="42194-187">**Para implantar a política**, selecione um ou mais grupos nos quais implantar a política e escolha **Adicionar** &gt; **OK**.</span><span class="sxs-lookup"><span data-stu-id="42194-187">**To deploy the policy**, select one or more groups to deploy the policy to, and then choose **Add** &gt; **OK**.</span></span>
    -   <span data-ttu-id="42194-188">**Para fechar a caixa de diálogo sem implantá-la**, escolha **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="42194-188">**To close the dialog box without deploying it**, choose **Cancel**.</span></span>

<span data-ttu-id="42194-189">Ao selecionar uma política implantada, você pode ver mais informações sobre a implantação na parte inferior da lista de políticas.</span><span class="sxs-lookup"><span data-stu-id="42194-189">When you select a deployed policy, you can see more information about the deployment in the lower part of the list of policies.</span></span>

### <span data-ttu-id="42194-190">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="42194-190">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

<span data-ttu-id="42194-191">Em seguida, saiba como usar certificados para proteger emails, Wi-Fi e perfis de VPN.</span><span class="sxs-lookup"><span data-stu-id="42194-191">Next, learn how to use certificates to help secure email, Wi-Fi, and VPN profiles.</span></span>

-  [<span data-ttu-id="42194-192">Configurar o acesso a email corporativo usando perfis de email</span><span class="sxs-lookup"><span data-stu-id="42194-192">Configure access to corporate email using email profiles</span></span>](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [<span data-ttu-id="42194-193">Conexões Wi-Fi no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="42194-193">Wi-Fi connections in Microsoft Intune</span></span>](wi-fi-connections-in-microsoft-intune.md)
-  [<span data-ttu-id="42194-194">Conexões VPN no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="42194-194">VPN connections in Microsoft Intune</span></span>](vpn-connections-in-microsoft-intune.md)
