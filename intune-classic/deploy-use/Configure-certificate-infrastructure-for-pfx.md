---
title: Configurar a infraestrutura de certificado para PFX
description: Criar e implantar perfis de certificado .PFX.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/17/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c543a02-44a5-4964-8000-a45e3bf2cc69
ms.reviewer: vinaybha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 868578d6c6c87a9e7459160ed89dfd50629bdb51
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f9d27-103">Configurar a infraestrutura de certificado</span><span class="sxs-lookup"><span data-stu-id="f9d27-103">Configure certificate infrastructure</span></span>
<a id="configure-certificate-infrastructure" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f9d27-104">Este tópico descreve o que você precisa para criar e implantar perfis de certificado .PFX.</span><span class="sxs-lookup"><span data-stu-id="f9d27-104">This topic describes what you need in order to create and deploy .PFX certificate profiles.</span></span>

<span data-ttu-id="f9d27-105">Para fazer qualquer autenticação baseada em certificado na sua organização, você precisa de uma Autoridade de Certificação Corporativa.</span><span class="sxs-lookup"><span data-stu-id="f9d27-105">To do any certificate-based authentication in your organization, you need an Enterprise Certification Authority.</span></span>

<span data-ttu-id="f9d27-106">Para usar perfis de certificado .PFX, além da Autoridade de Certificação Corporativa, você também precisa:</span><span class="sxs-lookup"><span data-stu-id="f9d27-106">To use .PFX Certificate profiles, in addition to the Enterprise Certification Authority, you  also need:</span></span>

-   <span data-ttu-id="f9d27-107">Um computador que pode se comunicar com a Autoridade de Certificação ou você pode usar o próprio computador da Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-107">A computer that can communicate with the Certification Authority, or you can use the Certification Authority computer itself.</span></span>

-  <span data-ttu-id="f9d27-108">O Conector de Certificado do Intune, que é executado no computador, que pode se comunicar com a Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-108">The Intune Certificate Connector, which runs on the computer that can communicate with the Certification Authority.</span></span>

## <span data-ttu-id="f9d27-109">Descrição da infraestrutura local</span><span class="sxs-lookup"><span data-stu-id="f9d27-109">On-premises infrastructure description</span></span>
<a id="on-premises-infrastructure-description" class="xliff"></a>


-    <span data-ttu-id="f9d27-110">**Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f9d27-110">**Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.</span></span>

-  <span data-ttu-id="f9d27-111">**Autoridade de Certificação**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="f9d27-111">**Certification Authority**: An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="f9d27-112">Não há suporte para ACs autônomas.</span><span class="sxs-lookup"><span data-stu-id="f9d27-112">A Standalone CA is not supported.</span></span> <span data-ttu-id="f9d27-113">Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx).</span><span class="sxs-lookup"><span data-stu-id="f9d27-113">For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).</span></span>
    <span data-ttu-id="f9d27-114">Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).</span><span class="sxs-lookup"><span data-stu-id="f9d27-114">If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).</span></span>

-  <span data-ttu-id="f9d27-115">**Computador capaz de se comunicar com a Autoridade de Certificação**: como alternativa, use o próprio computador da Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-115">**Computer that can communicate with Certification Authority**: Alternatively, use the Certification Authority computer itself.</span></span>
-  <span data-ttu-id="f9d27-116">**Conector de Certificado do Microsoft Intune**: você usa o console de administração do Intune para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**).</span><span class="sxs-lookup"><span data-stu-id="f9d27-116">**Microsoft Intune Certificate Connector**: You use the Intune admin console to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**).</span></span> <span data-ttu-id="f9d27-117">Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-117">Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector.</span></span> <span data-ttu-id="f9d27-118">Para os perfis de Certificado .PFX, instale o Conector de Certificado no computador que se comunica com a Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-118">For .PFX Certificate profiles, install the Certificate Connector on the computer that communicates with the Certification Authority.</span></span>
-  <span data-ttu-id="f9d27-119">**Servidor Proxy de Aplicativos Web** (opcional): você pode usar um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de aplicativo Web).</span><span class="sxs-lookup"><span data-stu-id="f9d27-119">**Web Application Proxy server** (optional): You can use a server that runs Windows Server 2012 R2 or later as a Web Application Proxy (WAP) server.</span></span> <span data-ttu-id="f9d27-120">Essa configuração:</span><span class="sxs-lookup"><span data-stu-id="f9d27-120">This configuration:</span></span>
    -  <span data-ttu-id="f9d27-121">Permite que os dispositivos recebam certificados usando uma conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="f9d27-121">Allows devices to receive certificates using an Internet connection.</span></span>
    -  <span data-ttu-id="f9d27-122">Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.</span><span class="sxs-lookup"><span data-stu-id="f9d27-122">Is a security recommendation when devices connect through the Internet to receive and renew certificates.</span></span>

 > [!NOTE]           
> -    <span data-ttu-id="f9d27-123">O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo NDES (Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="f9d27-123">The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service (NDES).</span></span> <span data-ttu-id="f9d27-124">Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).</span><span class="sxs-lookup"><span data-stu-id="f9d27-124">This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).</span></span>
>-  <span data-ttu-id="f9d27-125">Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="f9d27-125">Also, the server that hosts WAP must have an SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.</span></span> <span data-ttu-id="f9d27-126">Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="f9d27-126">These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.</span></span>
    <span data-ttu-id="f9d27-127">Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx).</span><span class="sxs-lookup"><span data-stu-id="f9d27-127">For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx).</span></span> <span data-ttu-id="f9d27-128">Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|</span><span class="sxs-lookup"><span data-stu-id="f9d27-128">For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|</span></span>


### <span data-ttu-id="f9d27-129">Certificados e modelos</span><span class="sxs-lookup"><span data-stu-id="f9d27-129">Certificates and Templates</span></span>
<a id="certificates-and-templates" class="xliff"></a>

|<span data-ttu-id="f9d27-130">Objeto</span><span class="sxs-lookup"><span data-stu-id="f9d27-130">Object</span></span>|<span data-ttu-id="f9d27-131">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f9d27-131">Details</span></span>|
|----------|-----------|
|<span data-ttu-id="f9d27-132">**Modelo de certificado**</span><span class="sxs-lookup"><span data-stu-id="f9d27-132">**Certificate Template**</span></span>|<span data-ttu-id="f9d27-133">Você configura este modelo na AC emissora.</span><span class="sxs-lookup"><span data-stu-id="f9d27-133">You configure this template on your issuing CA.</span></span>|
|<span data-ttu-id="f9d27-134">**Certificado de AC raiz confiável**</span><span class="sxs-lookup"><span data-stu-id="f9d27-134">**Trusted Root CA certificate**</span></span>|<span data-ttu-id="f9d27-135">Você o exporta como um arquivo **.cer** da AC emissora ou de qualquer dispositivo que confie na AC emissora e o implanta nos dispositivos usando o perfil de certificado de AC confiável.</span><span class="sxs-lookup"><span data-stu-id="f9d27-135">You export this as a **.cer** file from the issuing CA or any device which trusts the issuing CA, and deploy it to devices by using the Trusted CA certificate profile.</span></span><br /><br /><span data-ttu-id="f9d27-136">Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.</span><span class="sxs-lookup"><span data-stu-id="f9d27-136">You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.</span></span><br /><br /><span data-ttu-id="f9d27-137">Você pode usar certificados de AC raiz confiável adicionais quando necessário.</span><span class="sxs-lookup"><span data-stu-id="f9d27-137">You can use additional Trusted Root CA certificates when needed.</span></span> <span data-ttu-id="f9d27-138">Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="f9d27-138">For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.</span></span>|


## <span data-ttu-id="f9d27-139">Configure sua infraestrutura</span><span class="sxs-lookup"><span data-stu-id="f9d27-139">Configure your infrastructure</span></span>
<a id="configure-your-infrastructure" class="xliff"></a>
<span data-ttu-id="f9d27-140">Para poder configurar perfis de certificado, você deve concluir as tarefas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f9d27-140">Before you can configure certificate profiles, you must complete the following tasks.</span></span> <span data-ttu-id="f9d27-141">Essas tarefas exigem conhecimento do Windows Server 2012 R2 e do ADCS (Serviços de Certificados do Active Directory):</span><span class="sxs-lookup"><span data-stu-id="f9d27-141">These tasks require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):</span></span>

- <span data-ttu-id="f9d27-142">**Tarefa 1** – configurar modelos de certificado na autoridade de certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-142">**Task 1** - Configure certificate templates on the certification authority.</span></span>
- <span data-ttu-id="f9d27-143">**Tarefa 2** - habilitar, instalar e configurar o Conector de Certificado do Intune.</span><span class="sxs-lookup"><span data-stu-id="f9d27-143">**Task 2** - Enable, install, and configure the Intune Certificate Connector.</span></span>

### <span data-ttu-id="f9d27-144">Tarefa 1 – Configurar modelos de certificado na autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="f9d27-144">Task 1 - Configure certificate templates on the certification authority</span></span>
<a id="task-1---configure-certificate-templates-on-the-certification-authority" class="xliff"></a>
<span data-ttu-id="f9d27-145">Nesta tarefa, você publicará o modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-145">In this task, you will publish the certificate template.</span></span>

##### <span data-ttu-id="f9d27-146">Para configurar a autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="f9d27-146">To configure the certification authority</span></span>
<a id="to-configure-the-certification-authority" class="xliff"></a>

1.  <span data-ttu-id="f9d27-147">Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado ou copie e edite um modelo existente (como o modelo de Usuário) para uso com o .PFX.</span><span class="sxs-lookup"><span data-stu-id="f9d27-147">On the issuing CA, use the Certificate Templates snap-in to create a new custom template, or copy and edit an existing template (like the User template), for use with .PFX.</span></span>

    <span data-ttu-id="f9d27-148">O modelo deve incluir o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f9d27-148">The template must include the following:</span></span>

    -   <span data-ttu-id="f9d27-149">Especifique um **Nome amigável de exibição do modelo** para o modelo.</span><span class="sxs-lookup"><span data-stu-id="f9d27-149">Specify a friendly **Template display name** for the template.</span></span>

    -   <span data-ttu-id="f9d27-150">Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-150">On the **Subject Name** tab, select **Supply in the request**.</span></span> 

    -   <span data-ttu-id="f9d27-151">Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-151">On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="f9d27-152">Para modelos de certificado do iOS e Mac OS X, na guia **Extensões**, edite **Uso da Chave** e verifique se **A assinatura é uma prova de origem** não está selecionado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-152">For iOS and Mac OS X certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure that **Signature is proof of origin** is not selected.</span></span>

2.  <span data-ttu-id="f9d27-153">Examine o **Período de validade** na guia **Geral** do modelo.</span><span class="sxs-lookup"><span data-stu-id="f9d27-153">Review the **Validity period** on the **General** tab of the template.</span></span> <span data-ttu-id="f9d27-154">Por padrão, o Intune usa o valor configurado no modelo.</span><span class="sxs-lookup"><span data-stu-id="f9d27-154">By default, Intune uses the value configured in the template.</span></span> <span data-ttu-id="f9d27-155">No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="f9d27-155">However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console.</span></span> <span data-ttu-id="f9d27-156">Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.</span><span class="sxs-lookup"><span data-stu-id="f9d27-156">If you want to always use the value in the template, skip the remainder of this step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9d27-157">As plataformas do iOS e Mac OS X sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.</span><span class="sxs-lookup"><span data-stu-id="f9d27-157">The iOS and Mac OS X platforms always uses the value set in the template, regardless of other configurations you make.</span></span>

    <span data-ttu-id="f9d27-158">Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:</span><span class="sxs-lookup"><span data-stu-id="f9d27-158">To configure the CA to allow the requester to specify the validity period, run the following commands on the CA:</span></span>

    <span data-ttu-id="f9d27-159">a.</span><span class="sxs-lookup"><span data-stu-id="f9d27-159">a.</span></span>  <span data-ttu-id="f9d27-160">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span><span class="sxs-lookup"><span data-stu-id="f9d27-160">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span></span>

    <span data-ttu-id="f9d27-161">b.</span><span class="sxs-lookup"><span data-stu-id="f9d27-161">b.</span></span>  <span data-ttu-id="f9d27-162">**net stop certsvc**</span><span class="sxs-lookup"><span data-stu-id="f9d27-162">**net stop certsvc**</span></span>

    <span data-ttu-id="f9d27-163">c.</span><span class="sxs-lookup"><span data-stu-id="f9d27-163">c.</span></span>  <span data-ttu-id="f9d27-164">**net start certsvc**</span><span class="sxs-lookup"><span data-stu-id="f9d27-164">**net start certsvc**</span></span>

3.  <span data-ttu-id="f9d27-165">Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-165">On the issuing CA, use the Certification Authority snap-in to publish the certificate template.</span></span>

    <span data-ttu-id="f9d27-166">a.</span><span class="sxs-lookup"><span data-stu-id="f9d27-166">a.</span></span>  <span data-ttu-id="f9d27-167">Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f9d27-167">Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.</span></span>

    <span data-ttu-id="f9d27-168">b.</span><span class="sxs-lookup"><span data-stu-id="f9d27-168">b.</span></span>  <span data-ttu-id="f9d27-169">Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .</span><span class="sxs-lookup"><span data-stu-id="f9d27-169">Validate that the template published by viewing it under the **Certificate Templates** folder.</span></span>

4.  <span data-ttu-id="f9d27-170">No computador da AC, certifique-se de que o computador que hospeda o Conector de Certificado do Intune tenha a permissão de registro, para que ele possa acessar o modelo usado na criação do perfil .PFX.</span><span class="sxs-lookup"><span data-stu-id="f9d27-170">On the CA computer, ensure that the computer that hosts the Intune Certificate Connector has enroll permission, so that it can access the template used in creating the .PFX profile.</span></span> <span data-ttu-id="f9d27-171">Defina essa permissão na guia **Segurança** das propriedades do computador da Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-171">Set that permission on the **Security** tab of the CA computer properties.</span></span>

### <span data-ttu-id="f9d27-172">Tarefa 2 - Habilitar, instalar e configurar o Conector de Certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="f9d27-172">Task 2 - Enable, install, and configure the Intune Certificate Connector</span></span>
<a id="task-2---enable-install-and-configure-the-intune-certificate-connector" class="xliff"></a>
<span data-ttu-id="f9d27-173">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="f9d27-173">In this task you will:</span></span>

<span data-ttu-id="f9d27-174">Baixar, instalar e configurar o Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-174">Download, install, and configure the Certificate Connector.</span></span>

##### <span data-ttu-id="f9d27-175">Para habilitar o suporte ao Conector de Certificado</span><span class="sxs-lookup"><span data-stu-id="f9d27-175">To enable support for the Certificate Connector</span></span>
<a id="to-enable-support-for-the-certificate-connector" class="xliff"></a>

1.  <span data-ttu-id="f9d27-176">Abra o [Console de administração do Intune](https://manage.microsoft.com) e escolha **Administrador** &gt; **Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-176">Open the [Intune administration console](https://manage.microsoft.com), and choose **Admin** &gt; **Certificate Connector**.</span></span>

2.  <span data-ttu-id="f9d27-177">Escolha **Configurar Conector de Certificado Local**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-177">Choose **Configure On-Premises Certificate Connector**.</span></span>

3.  <span data-ttu-id="f9d27-178">Selecione **Habilitar Conector de Certificado**e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-178">Select **Enable Certificate Connector**, and then choose **OK**.</span></span>

##### <span data-ttu-id="f9d27-179">Para baixar, instalar e configurar o Conector de Certificado</span><span class="sxs-lookup"><span data-stu-id="f9d27-179">To download, install, and configure the Certificate Connector</span></span>
<a id="to-download-install-and-configure-the-certificate-connector" class="xliff"></a>

1.  <span data-ttu-id="f9d27-180">Abra o [Console de administração do Intune](https://manage.microsoft.com) e escolha **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Conector de Certificado** &gt; **Baixar Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-180">Open the [Intune administration console](https://manage.microsoft.com), and then choose **Admin** &gt; **Mobile Device Management** &gt; **Certificate Connector** &gt; **Download Certificate Connector**.</span></span>

2.  <span data-ttu-id="f9d27-181">Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**).</span><span class="sxs-lookup"><span data-stu-id="f9d27-181">After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**).</span></span>

  <span data-ttu-id="f9d27-182">Execute o instalador no computador que é capaz de se conectar à Autoridade de Certificação.</span><span class="sxs-lookup"><span data-stu-id="f9d27-182">Run the installer on the computer that is able to connect with the Certification Authority.</span></span> <span data-ttu-id="f9d27-183">Escolha a opção de Distribuição de .PFX e escolha **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-183">Choose the .PFX Distribution option, and then choose **Install**.</span></span> <span data-ttu-id="f9d27-184">Quando a instalação for concluída, continue criando um perfil de certificado conforme descrito em [Configure certificate profiles](configure-intune-certificate-profiles.md) (Configurar perfis de certificado).</span><span class="sxs-lookup"><span data-stu-id="f9d27-184">When the installation has completed, continue by creating a certificate profile as described in [Configure certificate profiles](configure-intune-certificate-profiles.md).</span></span>

   <!-- Not sure about step 3 below -->

3.  <span data-ttu-id="f9d27-185">Quando for solicitado o certificado de cliente do Conector de Certificado, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado na Tarefa 3.</span><span class="sxs-lookup"><span data-stu-id="f9d27-185">When prompted for the client certificate for the Certificate Connector, choose **Select**, and select the **client authentication** certificate you installed in Task 3.</span></span>

    <span data-ttu-id="f9d27-186">Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** .</span><span class="sxs-lookup"><span data-stu-id="f9d27-186">After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface.</span></span> <span data-ttu-id="f9d27-187">Embora o certificado selecionado não seja exibido, escolha **Avançar** para ver as propriedades do certificado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-187">Although the certificate you selected is not shown, choose **Next** to view the properties of that certificate.</span></span> <span data-ttu-id="f9d27-188">Escolha **Avançar** e **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-188">Then choose **Next**, and then **Install**.</span></span>

4.  <span data-ttu-id="f9d27-189">Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-189">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

    > [!TIP]
    > <span data-ttu-id="f9d27-190">Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f9d27-190">If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:</span></span>
    >
    > <span data-ttu-id="f9d27-191">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span><span class="sxs-lookup"><span data-stu-id="f9d27-191">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span></span>

5.  <span data-ttu-id="f9d27-192">Na interface do usuário do **Conector de Certificado** :</span><span class="sxs-lookup"><span data-stu-id="f9d27-192">In the **Certificate Connector** UI:</span></span>

    <span data-ttu-id="f9d27-193">a.</span><span class="sxs-lookup"><span data-stu-id="f9d27-193">a.</span></span> <span data-ttu-id="f9d27-194">Escolha **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.</span><span class="sxs-lookup"><span data-stu-id="f9d27-194">Choose **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.</span></span>

    <span data-ttu-id="f9d27-195">b.</span><span class="sxs-lookup"><span data-stu-id="f9d27-195">b.</span></span> <span data-ttu-id="f9d27-196">Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora.</span><span class="sxs-lookup"><span data-stu-id="f9d27-196">Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority.</span></span>

    <span data-ttu-id="f9d27-197">c.</span><span class="sxs-lookup"><span data-stu-id="f9d27-197">c.</span></span> <span data-ttu-id="f9d27-198">Escolha **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-198">Choose **Apply**.</span></span>

    <span data-ttu-id="f9d27-199">Agora você pode fechar a interface do usuário do Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="f9d27-199">You can now close the Certificate Connector UI.</span></span>

6.  <span data-ttu-id="f9d27-200">Abra um prompt de comando e digite **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-200">Open a command prompt and type **services.msc**.</span></span> <span data-ttu-id="f9d27-201">Em seguida, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector Intune** e escolha **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="f9d27-201">Then press **Enter**, right-click the **Intune Connector Service**, and choose **Restart**.</span></span>


### <span data-ttu-id="f9d27-202">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="f9d27-202">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="f9d27-203">Agora você está pronto para configurar perfis de certificado, conforme descrito em [Configure certificate profiles](Configure-Intune-certificate-profiles.md) (Configurar perfis de certificado).</span><span class="sxs-lookup"><span data-stu-id="f9d27-203">You are now ready to set up certificate profiles, as described in [Configure certificate profiles](Configure-Intune-certificate-profiles.md).</span></span>
