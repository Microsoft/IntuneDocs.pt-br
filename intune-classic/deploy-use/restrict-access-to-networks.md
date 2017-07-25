---
title: Proteger o acesso a redes com o Cisco ISE
description: "Use o Cisco ISE com o Intune para que os dispositivos sejam registrados no Intune e compatíveis com a política antes de acessarem redes Wi-Fi e VPN controladas pelo Cisco ISE."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 958108c4fbeb52803bf900a1a0f9f633716cddb8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="c421d-103">Usando o Cisco ISE com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c421d-103">Using Cisco ISE with Microsoft Intune</span></span>
<a id="using-cisco-ise-with-microsoft-intune" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c421d-104">A integração do Intune com o Cisco ISE (Mecanismo de serviços de identidade) permite criar políticas de rede em seu ambiente de ISE usando o estado de conformidade e de registro do dispositivo do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-104">Intune integration with Cisco Identity Services Engine (ISE) allows you to author network policies in your ISE environment by using the Intune device-enrollment and compliance state.</span></span> <span data-ttu-id="c421d-105">Você pode usar essas políticas para garantir que o acesso à rede da empresa seja restrito aos dispositivos gerenciados pelo Intune e em conformidade com as políticas do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-105">You can use these policies to ensure that access to your company network is restricted to devices that are managed by Intune and compliant with Intune policies.</span></span>

## <span data-ttu-id="c421d-106">Etapas de configuração</span><span class="sxs-lookup"><span data-stu-id="c421d-106">Configuration steps</span></span>
<a id="configuration-steps" class="xliff"></a>

<span data-ttu-id="c421d-107">Para habilitar essa integração, você não precisa fazer nenhuma configuração no seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-107">To enable this integration, you don’t need to do any setup in your Intune tenant.</span></span> <span data-ttu-id="c421d-108">Você precisará fornecer permissões para seu servidor do Cisco ISE acessar o locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-108">You will need to provide permissions to your Cisco ISE server to access your Intune tenant.</span></span> <span data-ttu-id="c421d-109">Quando isso for concluído, o restante da configuração acontecerá em seu servidor do Cisco ISE.</span><span class="sxs-lookup"><span data-stu-id="c421d-109">After that's done, the rest of the setup happens in your Cisco ISE server.</span></span> <span data-ttu-id="c421d-110">Este artigo fornece instruções sobre como fornecer a seu servidor do ISE as permissões para acessar seu locatário do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-110">This article gives you instructions on providing your ISE server with permissions to access your Intune tenant.</span></span>

### <span data-ttu-id="c421d-111">Etapa 1: Gerenciar os certificados</span><span class="sxs-lookup"><span data-stu-id="c421d-111">Step 1: Manage the certificates</span></span>
<a id="step-1-manage-the-certificates" class="xliff"></a>
<span data-ttu-id="c421d-112">Exporte o certificado do console do Azure AD (Azure Active Directory) e importe-o para o repositório de Certificados confiáveis do console do ISE:</span><span class="sxs-lookup"><span data-stu-id="c421d-112">Export the certificate from the Azure Active Directory (Azure AD) console, then import it into the Trusted Certificates store of the ISE console:</span></span>

#### <span data-ttu-id="c421d-113">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="c421d-113">Internet Explorer 11</span></span>
<a id="internet-explorer-11" class="xliff"></a>


   <span data-ttu-id="c421d-114">a.</span><span class="sxs-lookup"><span data-stu-id="c421d-114">a.</span></span> <span data-ttu-id="c421d-115">Execute o Internet Explorer como administrador e entre no console do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c421d-115">Run Internet Explorer as an administrator, and sign in to the Azure AD console.</span></span>

   <span data-ttu-id="c421d-116">b.</span><span class="sxs-lookup"><span data-stu-id="c421d-116">b.</span></span> <span data-ttu-id="c421d-117">Escolha o ícone de cadeado na barra de endereços e escolha **Exibir certificados**.</span><span class="sxs-lookup"><span data-stu-id="c421d-117">Choose the lock icon in the address bar and choose **View certificates**.</span></span>

   <span data-ttu-id="c421d-118">c.</span><span class="sxs-lookup"><span data-stu-id="c421d-118">c.</span></span> <span data-ttu-id="c421d-119">Na guia **Detalhes** das propriedades do certificado, escolha **Copiar para arquivo**.</span><span class="sxs-lookup"><span data-stu-id="c421d-119">On the **Details** tab of the certificate properties, choose **Copy to file**.</span></span>

   <span data-ttu-id="c421d-120">d.</span><span class="sxs-lookup"><span data-stu-id="c421d-120">d.</span></span> <span data-ttu-id="c421d-121">Na página de boas-vindas **Assistente para Exportação de Certificados**, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c421d-121">In the **Certificate export wizard** welcome page, choose **Next**.</span></span>

   <span data-ttu-id="c421d-122">e.</span><span class="sxs-lookup"><span data-stu-id="c421d-122">e.</span></span> <span data-ttu-id="c421d-123">Na pagina **Formato do arquivo de exportação**, deixe o padrão **x.509 binário codificado por DER (.CER)** e escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c421d-123">On the **Export file format** page, leave the default, **DER encoded binary x.509 (.CER)**, and choose **Next**.</span></span>  

   <span data-ttu-id="c421d-124">f.</span><span class="sxs-lookup"><span data-stu-id="c421d-124">f.</span></span> <span data-ttu-id="c421d-125">Na página **Arquivo a ser exportado**, escolha **Procurar** para escolher um local no qual salvar o arquivo e forneça um nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-125">On the **File to export** page, choose **Browse** to pick a location in which to save the file, and provide a file name.</span></span> <span data-ttu-id="c421d-126">Embora pareça que você está escolhendo um arquivo para ser exportado, na verdade você está nomeando o arquivo no qual o certificado exportado será salvo.</span><span class="sxs-lookup"><span data-stu-id="c421d-126">Though it seems like you’re picking a file to export, you’re actually naming the file that the exported certificate will be saved to.</span></span> <span data-ttu-id="c421d-127">Escolha **Avançar** &gt; **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c421d-127">Choose **Next** &gt; **Finish**.</span></span>

   <span data-ttu-id="c421d-128">g.</span><span class="sxs-lookup"><span data-stu-id="c421d-128">g.</span></span> <span data-ttu-id="c421d-129">De dentro do console do ISE, importe o certificado do Intune (o arquivo exportado) para o repositório **Certificados Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="c421d-129">From within the ISE console, import the Intune certificate (the file you exported) into the  **Trusted Certificates** store.</span></span>

#### <span data-ttu-id="c421d-130">Safari</span><span class="sxs-lookup"><span data-stu-id="c421d-130">Safari</span></span>
<a id="safari" class="xliff"></a>

 <span data-ttu-id="c421d-131">a.</span><span class="sxs-lookup"><span data-stu-id="c421d-131">a.</span></span> <span data-ttu-id="c421d-132">Entre no console do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c421d-132">Sign in to the Azure AD console.</span></span>

<span data-ttu-id="c421d-133">b.</span><span class="sxs-lookup"><span data-stu-id="c421d-133">b.</span></span> <span data-ttu-id="c421d-134">Escolha o ícone de cadeado &gt;  **Mais informações**.</span><span class="sxs-lookup"><span data-stu-id="c421d-134">Choose the lock icon &gt;  **More information**.</span></span>

   <span data-ttu-id="c421d-135">c.</span><span class="sxs-lookup"><span data-stu-id="c421d-135">c.</span></span> <span data-ttu-id="c421d-136">Escolha **Exibir certificado** &gt; **Detalhes**.</span><span class="sxs-lookup"><span data-stu-id="c421d-136">Choose **View certificate** &gt; **Details**.</span></span>

   <span data-ttu-id="c421d-137">d.</span><span class="sxs-lookup"><span data-stu-id="c421d-137">d.</span></span> <span data-ttu-id="c421d-138">Escolha o certificado e, em seguida, escolha **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="c421d-138">Choose the certificate, and then choose **Export**.</span></span> 

   <span data-ttu-id="c421d-139">e.</span><span class="sxs-lookup"><span data-stu-id="c421d-139">e.</span></span> <span data-ttu-id="c421d-140">De dentro do console do ISE, importe o certificado do Intune (o arquivo exportado) para o repositório **Certificados Confiáveis**.</span><span class="sxs-lookup"><span data-stu-id="c421d-140">From within the ISE console, import the Intune certificate (the file you exported) into the  **Trusted Certificates** store.</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="c421d-141">Verifique a data de validade do certificado, pois você terá que exportar e importar um novo certificado quando este expirar.</span><span class="sxs-lookup"><span data-stu-id="c421d-141">Check the expiration date of the certificate, as you will have to export and import a new certificate when this one expires.</span></span>


### <span data-ttu-id="c421d-142">Obtenha um certificado autoassinado do ISE</span><span class="sxs-lookup"><span data-stu-id="c421d-142">Obtain a self-signed cert from ISE</span></span>
<a id="obtain-a-self-signed-cert-from-ise" class="xliff"></a> 

1.  <span data-ttu-id="c421d-143">No console do ISE, vá para **Administração** > **Certificados** > **Certificados do Sistema** > **Gerar certificado Autoassinado**.</span><span class="sxs-lookup"><span data-stu-id="c421d-143">In the ISE console, go to **Administration** > **Certificates** > **System Certificates** > **Generate Self Signed Certificate**.</span></span>  
2.       <span data-ttu-id="c421d-144">Exporte o certificado autoassinado.</span><span class="sxs-lookup"><span data-stu-id="c421d-144">Export the self-signed certificate.</span></span>
3. <span data-ttu-id="c421d-145">Em um editor de texto, edite o certificado exportado:</span><span class="sxs-lookup"><span data-stu-id="c421d-145">In a text editor, edit the exported certificate:</span></span>

 - <span data-ttu-id="c421d-146">Excluir  **-----INICIAR CERTIFICADO-----**</span><span class="sxs-lookup"><span data-stu-id="c421d-146">Delete **-----BEGIN CERTIFICATE-----**</span></span>
 - <span data-ttu-id="c421d-147">Excluir  **-----CONCLUIR CERTIFICADO-----**</span><span class="sxs-lookup"><span data-stu-id="c421d-147">Delete **-----END CERTIFICATE-----**</span></span>
 
<span data-ttu-id="c421d-148">Verifique se todo o texto está em uma única linha</span><span class="sxs-lookup"><span data-stu-id="c421d-148">Ensure all of the text is a single line</span></span>


### <span data-ttu-id="c421d-149">Etapa 2: Criar um aplicativo para o ISE em seu locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c421d-149">Step 2: Create an app for ISE in your Azure AD tenant</span></span>
<a id="step-2-create-an-app-for-ise-in-your-azure-ad-tenant" class="xliff"></a>
1. <span data-ttu-id="c421d-150">No console do Azure AD, escolha **Aplicativos** > **Adicionar um Aplicativo** > **Adicionar um aplicativo que minha organização esteja desenvolvendo**.</span><span class="sxs-lookup"><span data-stu-id="c421d-150">In the Azure AD console, choose **Applications** > **Add an Application** > **Add an application my organization is developing**.</span></span>
2. <span data-ttu-id="c421d-151">Forneça um nome e uma URL para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c421d-151">Provide a name and a URL for the app.</span></span> <span data-ttu-id="c421d-152">A URL pode ser o site da empresa.</span><span class="sxs-lookup"><span data-stu-id="c421d-152">The URL could be your company website.</span></span>
3. <span data-ttu-id="c421d-153">Baixe o manifesto do aplicativo (um arquivo JSON).</span><span class="sxs-lookup"><span data-stu-id="c421d-153">Download the app manifest (a JSON file).</span></span>
4. <span data-ttu-id="c421d-154">Edite o arquivo JSON de manifesto.</span><span class="sxs-lookup"><span data-stu-id="c421d-154">Edit the manifest JSON file.</span></span> <span data-ttu-id="c421d-155">Na configuração da chamada **keyCredentials**, forneça o texto do certificado editado na Etapa 1 como valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="c421d-155">In the setting called **keyCredentials**, provide the edited certificate text from Step 1 as the setting value.</span></span>
5. <span data-ttu-id="c421d-156">Salve o arquivo sem alterar seu nome.</span><span class="sxs-lookup"><span data-stu-id="c421d-156">Save the file without changing its name.</span></span>
6. <span data-ttu-id="c421d-157">Forneça a seu aplicativo permissões para o Microsoft Graph e a API do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-157">Provide your app with permissions to Microsoft Graph and the Microsoft Intune API.</span></span>

 <span data-ttu-id="c421d-158">a.</span><span class="sxs-lookup"><span data-stu-id="c421d-158">a.</span></span> <span data-ttu-id="c421d-159">Para o Microsoft Graph, escolha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c421d-159">For Microsoft Graph, choose the following:</span></span>
    - <span data-ttu-id="c421d-160">**Permissões do aplicativo**: ler dados do diretório</span><span class="sxs-lookup"><span data-stu-id="c421d-160">**Application permissions**: Read directory data</span></span>
    - <span data-ttu-id="c421d-161">**Permissões delegadas**:</span><span class="sxs-lookup"><span data-stu-id="c421d-161">**Delegated permissions**:</span></span>
        - <span data-ttu-id="c421d-162">Acessar dados do usuário a qualquer momento</span><span class="sxs-lookup"><span data-stu-id="c421d-162">Access user’s data anytime</span></span>
        - <span data-ttu-id="c421d-163">Conectar usuários</span><span class="sxs-lookup"><span data-stu-id="c421d-163">Sign users in</span></span>

 <span data-ttu-id="c421d-164">b.</span><span class="sxs-lookup"><span data-stu-id="c421d-164">b.</span></span> <span data-ttu-id="c421d-165">Para a API do Microsoft Intune, em **Permissões do aplicativo**, escolha **Obter estado do dispositivo e conformidade do Intune**.</span><span class="sxs-lookup"><span data-stu-id="c421d-165">For the Microsoft Intune API, in **Application permissions**, choose **Get device state and compliance from Intune**.</span></span>

7. <span data-ttu-id="c421d-166">Escolha **Exibir pontos de extremidade** e copie os seguintes valores para uso nas configurações do ISE:</span><span class="sxs-lookup"><span data-stu-id="c421d-166">Choose **View Endpoints** and copy the following values for use in configuring ISE settings:</span></span>

|<span data-ttu-id="c421d-167">Valor no portal do Azure AD</span><span class="sxs-lookup"><span data-stu-id="c421d-167">Value in Azure AD portal</span></span>|<span data-ttu-id="c421d-168">Campo correspondente no portal do ISE</span><span class="sxs-lookup"><span data-stu-id="c421d-168">Corresponding field in ISE portal</span></span>|
|-------------------|---------------------------------|
|<span data-ttu-id="c421d-169">Ponto de extremidade da API do Microsoft Azure AD Graph</span><span class="sxs-lookup"><span data-stu-id="c421d-169">Microsoft Azure AD Graph API endpoint</span></span>|<span data-ttu-id="c421d-170">URL de descoberta automática</span><span class="sxs-lookup"><span data-stu-id="c421d-170">Auto Discovery URL</span></span>|
|<span data-ttu-id="c421d-171">Ponto de Extremidade do Token OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="c421d-171">Oauth 2.0 Token endpoint</span></span>|<span data-ttu-id="c421d-172">URL de emissão de token</span><span class="sxs-lookup"><span data-stu-id="c421d-172">Token Issuing URL</span></span>|
|<span data-ttu-id="c421d-173">Atualizar seu código com sua ID de cliente</span><span class="sxs-lookup"><span data-stu-id="c421d-173">Update your code with your Client ID</span></span>|<span data-ttu-id="c421d-174">ID do Cliente</span><span class="sxs-lookup"><span data-stu-id="c421d-174">Client ID</span></span>|

### <span data-ttu-id="c421d-175">Etapa 4: Carregar o certificado autoassinado do ISE no aplicativo do ISE criado no Azure AD</span><span class="sxs-lookup"><span data-stu-id="c421d-175">Step 4: Upload the self-signed certificate from ISE into the ISE app you created in Azure AD</span></span>
<a id="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad" class="xliff"></a>
1.     <span data-ttu-id="c421d-176">Obtenha o valor do certificado codificado em base64 e a impressão digital de um arquivo de certificado público .cer X509.</span><span class="sxs-lookup"><span data-stu-id="c421d-176">Get the base64 encoded cert value and thumbprint from a .cer X509 public cert file.</span></span> <span data-ttu-id="c421d-177">Este exemplo usa o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c421d-177">This example uses PowerShell:</span></span>
   
      
      <span data-ttu-id="c421d-178">$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()</span><span class="sxs-lookup"><span data-stu-id="c421d-178">$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()</span></span>
 
    <span data-ttu-id="c421d-179">Armazene os valores de $base64Thumbprint, $base64Value e $keyid que serão usados na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="c421d-179">Store the values for $base64Thumbprint, $base64Value and $keyid, to be used in the next step.</span></span>
2.       <span data-ttu-id="c421d-180">Carregue o certificado por meio do arquivo de manifesto.</span><span class="sxs-lookup"><span data-stu-id="c421d-180">Upload the certificate through the manifest file.</span></span> <span data-ttu-id="c421d-181">Faça logon no [Portal de Gerenciamento do Azure](https://manage.windowsazure.com)</span><span class="sxs-lookup"><span data-stu-id="c421d-181">Log in to the [Azure Management Portal](https://manage.windowsazure.com)</span></span>
2.      <span data-ttu-id="c421d-182">No snap-in do Azure AD, encontre o aplicativo que deseja configurar com um certificado x.509.</span><span class="sxs-lookup"><span data-stu-id="c421d-182">In to the Azure AD snap-in find the application that you want to configure with an X.509 certificate.</span></span>
3.      <span data-ttu-id="c421d-183">Baixe o arquivo de manifesto de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c421d-183">Download the application manifest file.</span></span> 
5.      <span data-ttu-id="c421d-184">Substitua a propriedade vazia “KeyCredentials”: [] pelo JSON a seguir.</span><span class="sxs-lookup"><span data-stu-id="c421d-184">Replace the empty “KeyCredentials”: [], property with the following JSON.</span></span>  <span data-ttu-id="c421d-185">O tipo complexo KeyCredentials é documentado na [Referência de entidades e tipos complexos](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType).</span><span class="sxs-lookup"><span data-stu-id="c421d-185">The KeyCredentials complex type is documented in[Entity and complex type reference](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType).</span></span>

 
    <span data-ttu-id="c421d-186">“keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2.</span><span class="sxs-lookup"><span data-stu-id="c421d-186">“keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2.</span></span> 
     <span data-ttu-id="c421d-187">],</span><span class="sxs-lookup"><span data-stu-id="c421d-187">],</span></span> 
 
<span data-ttu-id="c421d-188">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c421d-188">For example:</span></span>
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      <span data-ttu-id="c421d-189">Salve a alteração no arquivo de manifesto de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c421d-189">Save the change to the application manifest file.</span></span>
7.      <span data-ttu-id="c421d-190">Carregue o arquivo de manifesto do aplicativo editado por meio do portal de gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="c421d-190">Upload the edited application manifest file through the Azure management mortal.</span></span>
8.      <span data-ttu-id="c421d-191">Opcional: baixe o manifesto novamente para verificar se o certificado x.509 está presente no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c421d-191">Optional:  Download the manifest again, to check that your X.509 cert is present on the application.</span></span>

>[!NOTE]
>
> <span data-ttu-id="c421d-192">KeyCredentials é uma coleção, portanto, você pode carregar vários certificados x.509 para cenários de sobreposição ou excluir certificados em cenários de comprometimento.</span><span class="sxs-lookup"><span data-stu-id="c421d-192">KeyCredentials is a collection, so you can upload multiple X.509 certificates for rollover scenarios, or delete certficates in compromise scenarios.</span></span>


### <span data-ttu-id="c421d-193">Etapa 4: Definir configurações do ISE</span><span class="sxs-lookup"><span data-stu-id="c421d-193">Step 4: Configure ISE Settings</span></span>
<a id="step-4-configure-ise-settings" class="xliff"></a>
<span data-ttu-id="c421d-194">No console de administração do ISE, forneça estes valores de configuração:</span><span class="sxs-lookup"><span data-stu-id="c421d-194">In the ISE admin console, provide these setting values:</span></span>
  - <span data-ttu-id="c421d-195">**Tipo de servidor**: Gerenciador de Dispositivos Móveis</span><span class="sxs-lookup"><span data-stu-id="c421d-195">**Server Type**: Mobile Device Manager</span></span>
  - <span data-ttu-id="c421d-196">**Tipo de autenticação**: OAuth – Credenciais do cliente</span><span class="sxs-lookup"><span data-stu-id="c421d-196">**Authentication type**: OAuth – Client Credentials</span></span>
  - <span data-ttu-id="c421d-197">**Descoberta automática**: sim</span><span class="sxs-lookup"><span data-stu-id="c421d-197">**Auto Discovery**: Yes</span></span>
  - <span data-ttu-id="c421d-198">**URL de descoberta automática**: *insira o valor da Etapa 1.*</span><span class="sxs-lookup"><span data-stu-id="c421d-198">**Auto Discover URL**: *Enter the value from Step 1.*</span></span>
  - <span data-ttu-id="c421d-199">**ID do cliente**: *insira o valor da Etapa 1.*</span><span class="sxs-lookup"><span data-stu-id="c421d-199">**Client ID**: *Enter the value from Step 1.*</span></span>
  - <span data-ttu-id="c421d-200">**URL de emissão de token**: *insira o valor da Etapa 1.*</span><span class="sxs-lookup"><span data-stu-id="c421d-200">**Token issuing URL**: *Enter the value from Step 1.*</span></span>



## <span data-ttu-id="c421d-201">Informações compartilhadas entre seu locatário do Intune e seu servidor Cisco ISE</span><span class="sxs-lookup"><span data-stu-id="c421d-201">Information shared between your Intune tenant and your Cisco ISE server</span></span>
<a id="information-shared-between-your-intune-tenant-and-your-cisco-ise-server" class="xliff"></a>
<span data-ttu-id="c421d-202">Esta tabela lista as informações compartilhadas entre seu locatário do Intune e seu servidor Cisco ISE para dispositivos gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-202">This table lists the information that is shared between your Intune tenant and your Cisco ISE server for devices that are managed by Intune.</span></span>

|<span data-ttu-id="c421d-203">Propriedade</span><span class="sxs-lookup"><span data-stu-id="c421d-203">Property</span></span>|  <span data-ttu-id="c421d-204">Descrição</span><span class="sxs-lookup"><span data-stu-id="c421d-204">Description</span></span>|
|---------------|------------------------------------------------------------|
|<span data-ttu-id="c421d-205">complianceState</span><span class="sxs-lookup"><span data-stu-id="c421d-205">complianceState</span></span>|<span data-ttu-id="c421d-206">A cadeia de caracteres verdadeiro ou falso, que indica se o dispositivo é compatível ou incompatível.</span><span class="sxs-lookup"><span data-stu-id="c421d-206">The true or false string that indicates whether the device is compliant or noncompliant.</span></span>|
|<span data-ttu-id="c421d-207">isManaged</span><span class="sxs-lookup"><span data-stu-id="c421d-207">isManaged</span></span>|<span data-ttu-id="c421d-208">A cadeia de caracteres verdadeiro ou falso, que indica se o cliente é gerenciado pelo Intune ou não.</span><span class="sxs-lookup"><span data-stu-id="c421d-208">The true or false string that indicates whether the client is managed by Intune or not.</span></span>|
|<span data-ttu-id="c421d-209">macAddress</span><span class="sxs-lookup"><span data-stu-id="c421d-209">macAddress</span></span>|<span data-ttu-id="c421d-210">O endereço MAC do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-210">The MAC address of the device.</span></span>|
|<span data-ttu-id="c421d-211">serialNumber</span><span class="sxs-lookup"><span data-stu-id="c421d-211">serialNumber</span></span>|<span data-ttu-id="c421d-212">O número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-212">The serial number of the device.</span></span> <span data-ttu-id="c421d-213">Aplica-se somente a dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="c421d-213">It applies only to iOS devices.</span></span>|
|<span data-ttu-id="c421d-214">imei</span><span class="sxs-lookup"><span data-stu-id="c421d-214">imei</span></span>|<span data-ttu-id="c421d-215">O número do IMEI (15 dígitos decimais: 14 dígitos mais um dígito de verificação) ou IMEISV (16 dígitos) inclui informações sobre a origem, o modelo e o número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-215">The IMEI (15 decimal digits: 14 digits plus a check digit) or IMEISV (16 digits) number includes information on the origin, model, and serial number of the device.</span></span> <span data-ttu-id="c421d-216">A estrutura desse número é especificada em 3GPP TS 23.003.</span><span class="sxs-lookup"><span data-stu-id="c421d-216">The structure of this number is specified in 3GPP TS 23.003.</span></span> <span data-ttu-id="c421d-217">Aplica-se apenas aos dispositivos com cartões SIM.</span><span class="sxs-lookup"><span data-stu-id="c421d-217">It applies only to devices with SIM cards.</span></span>|
|<span data-ttu-id="c421d-218">udid</span><span class="sxs-lookup"><span data-stu-id="c421d-218">udid</span></span>|<span data-ttu-id="c421d-219">O Identificador de dispositivo exclusivo, que é uma sequência de 40 letras e números.</span><span class="sxs-lookup"><span data-stu-id="c421d-219">The Unique Device Identifier, which is a sequence of 40 letters and numbers.</span></span> <span data-ttu-id="c421d-220">Ele é específico para dispositivos iOS.</span><span class="sxs-lookup"><span data-stu-id="c421d-220">It is specific to iOS devices.</span></span>|
|<span data-ttu-id="c421d-221">meid</span><span class="sxs-lookup"><span data-stu-id="c421d-221">meid</span></span>|<span data-ttu-id="c421d-222">O identificador de equipamentos móveis, que é um número exclusivo globalmente que identifica uma peça física de equipamentos de estação móvel CDMA.</span><span class="sxs-lookup"><span data-stu-id="c421d-222">The mobile equipment identifier, which is a globally unique number that identifies a physical piece of CDMA mobile station equipment.</span></span> <span data-ttu-id="c421d-223">O formato do número é definido pelo relatório 3GPP2 S. R0048.</span><span class="sxs-lookup"><span data-stu-id="c421d-223">The number format is defined by the 3GPP2 report S. R0048.</span></span> <span data-ttu-id="c421d-224">No entanto, em termos práticos, ele pode ser visto como um IMEI, mas com dígitos hexadecimais.</span><span class="sxs-lookup"><span data-stu-id="c421d-224">However, in practical terms, it can be seen as an IMEI, but with hexadecimal digits.</span></span> <span data-ttu-id="c421d-225">Um MEID tem 56 bits (14 dígitos hexadecimais).</span><span class="sxs-lookup"><span data-stu-id="c421d-225">An MEID is 56 bits long (14 hex digits).</span></span> <span data-ttu-id="c421d-226">Ele consiste em três campos, incluindo um código regional de 8 bits (RR), um código do fabricante de 24 bits e um número de série atribuído pelo fabricante de 24 bits.</span><span class="sxs-lookup"><span data-stu-id="c421d-226">It consists of three fields, including an 8-bit regional code (RR), a 24-bit manufacturer code, and a 24-bit manufacturer-assigned serial number.</span></span>|
|<span data-ttu-id="c421d-227">osVersion</span><span class="sxs-lookup"><span data-stu-id="c421d-227">osVersion</span></span>|<span data-ttu-id="c421d-228">A versão do sistema operacional do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-228">The operating system version for the device.</span></span>
|<span data-ttu-id="c421d-229">modelo</span><span class="sxs-lookup"><span data-stu-id="c421d-229">model</span></span>|<span data-ttu-id="c421d-230">O modelo do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-230">The device model.</span></span>
|<span data-ttu-id="c421d-231">fabricante</span><span class="sxs-lookup"><span data-stu-id="c421d-231">manufacturer</span></span>|<span data-ttu-id="c421d-232">O fabricante do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c421d-232">The device manufacturer.</span></span>
|<span data-ttu-id="c421d-233">azureDeviceId</span><span class="sxs-lookup"><span data-stu-id="c421d-233">azureDeviceId</span></span>|<span data-ttu-id="c421d-234">A ID do dispositivo após ele ter o local de trabalho associado ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c421d-234">The device ID after it has workplace joined with Azure AD.</span></span> <span data-ttu-id="c421d-235">Ele é um GUID vazio para dispositivos que não estão associados.</span><span class="sxs-lookup"><span data-stu-id="c421d-235">It is an empty GUID for devices that are not joined.</span></span>|
|<span data-ttu-id="c421d-236">lastContactTimeUtc</span><span class="sxs-lookup"><span data-stu-id="c421d-236">lastContactTimeUtc</span></span>|<span data-ttu-id="c421d-237">A data e hora quando o dispositivo fez a última verificação no serviço de gerenciamento do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-237">The date and time when the device last checked in with the Intune management service.</span></span>


## <span data-ttu-id="c421d-238">Experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="c421d-238">User experience</span></span>
<a id="user-experience" class="xliff"></a>

<span data-ttu-id="c421d-239">Quando um usuário tentar acessar recursos usando um dispositivo não registrado, ele receberá uma solicitação para se registrar, como mostrado aqui:</span><span class="sxs-lookup"><span data-stu-id="c421d-239">When a user attempts to access resources by using an unenrolled device, they receive a prompt to enroll, such as the one shown here:</span></span>

![Exemplo da solicitação de registro](../media/cisco-ise-user-iphone.png)

<span data-ttu-id="c421d-241">Quando um usuário optar por se registrar, ele será redirecionado para o processo de registro do Intune.</span><span class="sxs-lookup"><span data-stu-id="c421d-241">When a user chooses to enroll, they are redirected to the Intune enrollment process.</span></span> <span data-ttu-id="c421d-242">A experiência de registro do usuário para o Intune é descrita nestes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c421d-242">The user enrollment experience for Intune is described in these topics:</span></span>

- [<span data-ttu-id="c421d-243">Registrar seu dispositivo Android no Intune</span><span class="sxs-lookup"><span data-stu-id="c421d-243">Enroll your Android device in Intune</span></span>](/intune-user-help/enroll-your-device-in-Intune-android)</br>
- [<span data-ttu-id="c421d-244">Registrar seu dispositivo iOS no Intune</span><span class="sxs-lookup"><span data-stu-id="c421d-244">Enroll your iOS device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-ios)</br>
- [<span data-ttu-id="c421d-245">Registrar seu dispositivo Mac OS X no Intune</span><span class="sxs-lookup"><span data-stu-id="c421d-245">Enroll your Mac OS X device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-mac-os-x)</br>
- [<span data-ttu-id="c421d-246">Registrar seu dispositivo Windows no Intune</span><span class="sxs-lookup"><span data-stu-id="c421d-246">Enroll your Windows device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-windows)</br>

<span data-ttu-id="c421d-247">Também há um [conjunto baixável de instruções de registro](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) que você pode usar para criar orientação personalizada para sua experiência de usuário.</span><span class="sxs-lookup"><span data-stu-id="c421d-247">There is also a [downloadable set of enrollment instructions](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) that you can use to create customized guidance for your user experience.</span></span>


### <span data-ttu-id="c421d-248">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c421d-248">See also</span></span>
<a id="see-also" class="xliff"></a>

[<span data-ttu-id="c421d-249">Guia do Administrador do Mecanismo de Serviços de Identidade da Cisco, versão 2.1</span><span class="sxs-lookup"><span data-stu-id="c421d-249">Cisco Identity Services Engine Administrator Guide, Release 2.1</span></span>](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)
