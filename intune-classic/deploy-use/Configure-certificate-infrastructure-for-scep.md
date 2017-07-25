---
title: Configurar a infraestrutura de certificado para SCEP
description: Infraestrutura para criar e implantar perfis de certificado SCEP.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 11/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ae137ae-34e5-4a45-950c-983de831270f
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9b62e03d88055c19a04c3968a1f060e20ae4fc65
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="eb06c-103">Configurar a infraestrutura de certificado para SCEP</span><span class="sxs-lookup"><span data-stu-id="eb06c-103">Configure certificate infrastructure for SCEP</span></span>
<a id="configure-certificate-infrastructure-for-scep" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="eb06c-104">Este tópico descreve qual infraestrutura é necessária para criar e implantar perfis de certificado SCEP.</span><span class="sxs-lookup"><span data-stu-id="eb06c-104">This topic describes what infrastructure you need in order to create and deploy SCEP certificate profiles.</span></span>

### <span data-ttu-id="eb06c-105">Infraestrutura local</span><span class="sxs-lookup"><span data-stu-id="eb06c-105">On-premises infrastructure</span></span>
<a id="on-premises-infrastructure" class="xliff"></a>

-    <span data-ttu-id="eb06c-106">**Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eb06c-106">**Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.</span></span>

-  <span data-ttu-id="eb06c-107">**AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="eb06c-107">**Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="eb06c-108">Não há suporte para ACs autônomas.</span><span class="sxs-lookup"><span data-stu-id="eb06c-108">A Standalone CA is not supported.</span></span> <span data-ttu-id="eb06c-109">Para ver instruções sobre como configurar uma autoridade de certificação, consulte [Instalar a autoridade de certificação](http://technet.microsoft.com/library/jj125375.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb06c-109">For instructions on how to set up a Certification Authority, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).</span></span>
    <span data-ttu-id="eb06c-110">Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).</span><span class="sxs-lookup"><span data-stu-id="eb06c-110">If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).</span></span>
<span data-ttu-id="eb06c-111">I</span><span class="sxs-lookup"><span data-stu-id="eb06c-111">I</span></span>
-  <span data-ttu-id="eb06c-112">**Servidor NDES**: em um servidor que executa o Windows Server 2012 R2 ou posterior, você deve configurar o NDES (Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="eb06c-112">**NDES Server**: On a server that runs Windows Server 2012 R2 or later, you must set up the Network Device Enrollment Service (NDES).</span></span> <span data-ttu-id="eb06c-113">O Intune não dá suporte ao uso do NDES quando ele é executado em um servidor que também executa a AC Corporativa.</span><span class="sxs-lookup"><span data-stu-id="eb06c-113">Intune does not support using NDES when it runs on a server that also runs the Enterprise CA.</span></span> <span data-ttu-id="eb06c-114">Consulte [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) (Diretrizes de Serviço de Registro de Dispositivo de Rede) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o Serviço de Registro de Dispositivo de Rede.</span><span class="sxs-lookup"><span data-stu-id="eb06c-114">See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure Windows Server 2012 R2 to host the Network Device Enrollment Service.</span></span> <span data-ttu-id="eb06c-115">O servidor NDES deve ter ingressado no domínio que hospeda a AC e não estar no mesmo servidor que a AC.</span><span class="sxs-lookup"><span data-stu-id="eb06c-115">The NDES server must be domain joined to the domain that hosts the CA, and not be on the same server as the CA.</span></span> <span data-ttu-id="eb06c-116">Para obter mais informações sobre como implantar o servidor NDES em uma floresta separada, rede isolada ou domínio interno podem ser encontradas em [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx) (Usando um módulo de política com o Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="eb06c-116">More information about deploying the NDES server in a separate forest, isolated network or internal domain can be found in [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx).</span></span>

-  <span data-ttu-id="eb06c-117">**Conector de Certificado do Microsoft Intune**: você usa o console de administração do Intune para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**).</span><span class="sxs-lookup"><span data-stu-id="eb06c-117">**Microsoft Intune Certificate Connector**: You use the Intune admin console to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**).</span></span> <span data-ttu-id="eb06c-118">Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-118">Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector.</span></span>
-  <span data-ttu-id="eb06c-119">**Servidor Proxy de Aplicativos Web** (opcional): você pode usar um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de Aplicativo Web).</span><span class="sxs-lookup"><span data-stu-id="eb06c-119">**Web Application Proxy Server** (optional): You can use a server that runs Windows Server 2012 R2  or later as a Web Application Proxy (WAP) server.</span></span> <span data-ttu-id="eb06c-120">Essa configuração:</span><span class="sxs-lookup"><span data-stu-id="eb06c-120">This configuration:</span></span>
    -  <span data-ttu-id="eb06c-121">Permite que os dispositivos recebam certificados usando uma conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="eb06c-121">Allows devices to receive certificates using an Internet connection.</span></span>
    -  <span data-ttu-id="eb06c-122">Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.</span><span class="sxs-lookup"><span data-stu-id="eb06c-122">Is a security recommendation when devices connect through the Internet to receive and renew certificates.</span></span>

 > [!NOTE]           
> -    <span data-ttu-id="eb06c-123">O servidor que hospeda o WAP [deve instalar uma atualização](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede.</span><span class="sxs-lookup"><span data-stu-id="eb06c-123">The server that hosts WAP [must install an update](https://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service.</span></span> <span data-ttu-id="eb06c-124">Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](https://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](https://support.microsoft.com/kb/3011135).</span><span class="sxs-lookup"><span data-stu-id="eb06c-124">This update is included with the [December 2014 update rollup](https://support.microsoft.com/kb/3013769), or individually from [KB3011135](https://support.microsoft.com/kb/3011135).</span></span>
>-  <span data-ttu-id="eb06c-125">Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-125">Also, the server that hosts WAP must have a SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.</span></span> <span data-ttu-id="eb06c-126">Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-126">These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.</span></span>
    <span data-ttu-id="eb06c-127">Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx).</span><span class="sxs-lookup"><span data-stu-id="eb06c-127">For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx).</span></span> <span data-ttu-id="eb06c-128">Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|</span><span class="sxs-lookup"><span data-stu-id="eb06c-128">For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|</span></span>

### <span data-ttu-id="eb06c-129">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="eb06c-129">Network requirements</span></span>
<a id="network-requirements" class="xliff"></a>

<span data-ttu-id="eb06c-130">Da Internet para a rede de perímetro, permitir a porta 443 de todos os endereços IP/ hosts na internet para o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-130">From the Internet to perimeter network, allow port 443 from all hosts/IP addresses on the internet to the NDES server.</span></span>

<span data-ttu-id="eb06c-131">Da rede de perímetro para a rede confiável, permitir todas as portas e protocolos necessários para acesso ao domínio no servidor NDES associado por domínio.</span><span class="sxs-lookup"><span data-stu-id="eb06c-131">From the perimeter network to trusted network, allow all ports and protocols needed for domain access on the domain-joined NDES server.</span></span> <span data-ttu-id="eb06c-132">O servidor NDES precisa acessar servidores de certificados, servidores DNS, servidores do Configuration Manager e controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="eb06c-132">The NDES server needs access to the certificate servers, DNS servers, Configuration Manager servers and domain controllers.</span></span>

<span data-ttu-id="eb06c-133">É recomendável publicar o servidor NDES através de um proxy, como o [Proxy de aplicativo do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), o [Proxy do Web Access](https://technet.microsoft.com/library/dn584107.aspx) ou um proxy de terceiros.</span><span class="sxs-lookup"><span data-stu-id="eb06c-133">We recommend publishing the NDES server through a proxy, such as the [Azure AD application proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx), or a third-party proxy.</span></span>


### <span data-ttu-id="eb06c-134"><a name="BKMK_CertsAndTemplates"></a>Certificados e modelos</span><span class="sxs-lookup"><span data-stu-id="eb06c-134"><a name="BKMK_CertsAndTemplates"></a>Certificates and Templates</span></span>

|<span data-ttu-id="eb06c-135">Objeto</span><span class="sxs-lookup"><span data-stu-id="eb06c-135">Object</span></span>|<span data-ttu-id="eb06c-136">Detalhes</span><span class="sxs-lookup"><span data-stu-id="eb06c-136">Details</span></span>|
|----------|-----------|
|<span data-ttu-id="eb06c-137">**Modelo de certificado**</span><span class="sxs-lookup"><span data-stu-id="eb06c-137">**Certificate Template**</span></span>|<span data-ttu-id="eb06c-138">Você configura este modelo na AC emissora.</span><span class="sxs-lookup"><span data-stu-id="eb06c-138">You configure this template on your issuing CA.</span></span>|
|<span data-ttu-id="eb06c-139">**Certificado de autenticação de cliente**</span><span class="sxs-lookup"><span data-stu-id="eb06c-139">**Client authentication certificate**</span></span>|<span data-ttu-id="eb06c-140">Solicitado pela AC emissora ou pública, você instala este certificado no servidor de NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-140">Requested from your issuing CA or public CA, you install this certificate on the NDES Server.</span></span>|
|<span data-ttu-id="eb06c-141">**Certificado de autenticação de servidor**</span><span class="sxs-lookup"><span data-stu-id="eb06c-141">**Server authentication certificate**</span></span>|<span data-ttu-id="eb06c-142">Solicitado da AC emissora pública, você instala e associa o certificado SSL no IIS no servidor de NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-142">Requested from your issuing CA or public CA, you install and bind this SSL certificate in IIS on the NDES server.</span></span>|
|<span data-ttu-id="eb06c-143">**Certificado de AC raiz confiável**</span><span class="sxs-lookup"><span data-stu-id="eb06c-143">**Trusted Root CA certificate**</span></span>|<span data-ttu-id="eb06c-144">Você o exporta como um arquivo **.cer** da AC raiz ou de qualquer dispositivo que confie na AC raiz e a implante nos dispositivos usando o perfil de certificado de autoridade de certificação confiável.</span><span class="sxs-lookup"><span data-stu-id="eb06c-144">You export this as a **.cer** file from the root CA or any device which trusts the root CA, and deploy it to devices by using the Trusted CA certificate profile.</span></span><br /><br /><span data-ttu-id="eb06c-145">Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.</span><span class="sxs-lookup"><span data-stu-id="eb06c-145">You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.</span></span><br /><br /><span data-ttu-id="eb06c-146">Você pode usar certificados de AC raiz confiável adicionais quando necessário.</span><span class="sxs-lookup"><span data-stu-id="eb06c-146">You can use additional Trusted Root CA certificates when needed.</span></span> <span data-ttu-id="eb06c-147">Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="eb06c-147">For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.</span></span>|

### <span data-ttu-id="eb06c-148"><a name="BKMK_Accounts"></a>Contas</span><span class="sxs-lookup"><span data-stu-id="eb06c-148"><a name="BKMK_Accounts"></a>Accounts</span></span>

|<span data-ttu-id="eb06c-149">Nome</span><span class="sxs-lookup"><span data-stu-id="eb06c-149">Name</span></span>|<span data-ttu-id="eb06c-150">Detalhes</span><span class="sxs-lookup"><span data-stu-id="eb06c-150">Details</span></span>|
|--------|-----------|
|<span data-ttu-id="eb06c-151">**Conta de serviço de NDES**</span><span class="sxs-lookup"><span data-stu-id="eb06c-151">**NDES service account**</span></span>|<span data-ttu-id="eb06c-152">Especifique uma conta de usuário de domínio para usar como conta de serviço de NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-152">You specify a domain user account to use as the NDES Service account.</span></span>|

## <span data-ttu-id="eb06c-153"><a name="BKMK_ConfigureInfrastructure"></a>Configure sua infraestrutura</span><span class="sxs-lookup"><span data-stu-id="eb06c-153"><a name="BKMK_ConfigureInfrastructure"></a>Configure your infrastructure</span></span>
<span data-ttu-id="eb06c-154">Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):</span><span class="sxs-lookup"><span data-stu-id="eb06c-154">Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):</span></span>

<span data-ttu-id="eb06c-155">**Tarefa 1**: criar uma conta de serviço de NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-155">**Task 1**: Create an NDES service account</span></span>

<span data-ttu-id="eb06c-156">**Tarefa 2**: configurar modelos de certificado na autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="eb06c-156">**Task 2**: Configure certificate templates on the certification authority</span></span>

<span data-ttu-id="eb06c-157">**Tarefa 3**: configurar pré-requisitos no servidor NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-157">**Task 3**: Configure prerequisites on the NDES server</span></span>

<span data-ttu-id="eb06c-158">**Tarefa 4**: configurar o NDES para uso com o Intune</span><span class="sxs-lookup"><span data-stu-id="eb06c-158">**Task 4**: Configure NDES for use with Intune</span></span>

<span data-ttu-id="eb06c-159">**Tarefa 5**: habilitar, instalar e configurar o Conector de Certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="eb06c-159">**Task 5**: Enable, install, and configure the Intune Certificate Connector</span></span>

### <span data-ttu-id="eb06c-160">Tarefa 1 - Criar uma conta de serviço de NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-160">Task 1 - Create an NDES service account</span></span>
<a id="task-1---create-an-ndes-service-account" class="xliff"></a>

<span data-ttu-id="eb06c-161">Crie uma conta de usuário de domínio para usar como conta de serviço de NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-161">Create a domain user account to use as the NDES service account.</span></span> <span data-ttu-id="eb06c-162">Especifique essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-162">You will specify this account when you configure templates on the issuing CA before you install and configure NDES.</span></span> <span data-ttu-id="eb06c-163">Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como um Serviço** e **Logon como um trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-163">Make sure the user has the default rights, **Logon Localy**, **Logon as a Service** and **Logon as a batch job** rights.</span></span> <span data-ttu-id="eb06c-164">Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.</span><span class="sxs-lookup"><span data-stu-id="eb06c-164">Some organizations have hardening policies that disable those rights.</span></span>




### <span data-ttu-id="eb06c-165">Tarefa 2 – Configurar modelos de certificado na autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="eb06c-165">Task 2 - Configure certificate templates on the certification authority</span></span>
<a id="task-2---configure-certificate-templates-on-the-certification-authority" class="xliff"></a>
<span data-ttu-id="eb06c-166">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="eb06c-166">In this task you will:</span></span>

-   <span data-ttu-id="eb06c-167">Configurar um modelo de certificado para o NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-167">Configure a certificate template for NDES</span></span>

-   <span data-ttu-id="eb06c-168">Publicar o modelo de certificado para o NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-168">Publish the certificate template for NDES</span></span>

##### <span data-ttu-id="eb06c-169">Para configurar a autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="eb06c-169">To configure the certification authority</span></span>
<a id="to-configure-the-certification-authority" class="xliff"></a>

1.  <span data-ttu-id="eb06c-170">Faça logon como administrador corporativo.</span><span class="sxs-lookup"><span data-stu-id="eb06c-170">Log on as an enterprise administrator.</span></span>

2.  <span data-ttu-id="eb06c-171">Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado ou copie um modelo existente (como o modelo de Usuário) e o edite para uso com o NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-171">On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with NDES.</span></span>

    <span data-ttu-id="eb06c-172">O modelo deve ter as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="eb06c-172">The template must have the following configurations:</span></span>

    -   <span data-ttu-id="eb06c-173">Especifique um **Nome amigável de exibição do modelo** para o modelo.</span><span class="sxs-lookup"><span data-stu-id="eb06c-173">Specify a friendly **Template display name** for the template.</span></span>

    -   <span data-ttu-id="eb06c-174">Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-174">On the **Subject Name** tab, select **Supply in the request**.</span></span> <span data-ttu-id="eb06c-175">(A segurança é imposta pelo módulo de política do Intune para o NDES).</span><span class="sxs-lookup"><span data-stu-id="eb06c-175">(Security is enforced by the Intune policy module for NDES).</span></span>

    -   <span data-ttu-id="eb06c-176">Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-176">On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="eb06c-177">Para modelos de certificado do iOS e Mac OS X, na guia **Extensões**, edite **Uso da Chave** e verifique se **A assinatura é uma prova de origem** não está selecionado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-177">For iOS and Mac OS X certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.</span></span>

    -   <span data-ttu-id="eb06c-178">Na guia **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo.</span><span class="sxs-lookup"><span data-stu-id="eb06c-178">On the **Security** tab, add the NDES service account, and give it **Enroll** permissions to the template.</span></span> <span data-ttu-id="eb06c-179">Administradores do Intune que criarão perfis SCEP exigem direitos de **leitura** para que possam navegar no modelo durante a criação de perfis SCEP.</span><span class="sxs-lookup"><span data-stu-id="eb06c-179">Intune admins who will create SCEP profiles require **Read** rights so that they can browse to the template when creating SCEP profiles.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb06c-180">Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-180">To revoke certificates the NDES service account needs *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.</span></span>

3.  <span data-ttu-id="eb06c-181">Examine o **Período de validade** na guia **Geral** do modelo.</span><span class="sxs-lookup"><span data-stu-id="eb06c-181">Review the **Validity period** on the **General** tab of the template.</span></span> <span data-ttu-id="eb06c-182">Por padrão, o Intune usa o valor configurado no modelo.</span><span class="sxs-lookup"><span data-stu-id="eb06c-182">By default, Intune uses the value configured in the template.</span></span> <span data-ttu-id="eb06c-183">No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="eb06c-183">However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console.</span></span> <span data-ttu-id="eb06c-184">Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.</span><span class="sxs-lookup"><span data-stu-id="eb06c-184">If you want to always use the value in the template, skip the remainder of this step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eb06c-185">As plataformas do iOS e Mac OS X sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.</span><span class="sxs-lookup"><span data-stu-id="eb06c-185">The iOS and Mac OS X platforms always uses the value set in the template regardless of other configurations you make.</span></span>

<span data-ttu-id="eb06c-186">Aqui estão as capturas de tela de um exemplo de configuração de modelo.</span><span class="sxs-lookup"><span data-stu-id="eb06c-186">Here are screenshots of an example template configuration.</span></span>

![Modelo, guia de tratamento de solicitação](..\media\scep_ndes_request_handling.png)

![Modelo, guia de nome da entidade](..\media\scep_ndes_subject_name.jpg)

![Modelo, guia de segurança](..\media\scep_ndes_security.jpg)

![Modelo, guia de extensões](..\media\scep_ndes_extensions.jpg)

![Modelo, guia de requisitos de emissão](..\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > <span data-ttu-id="eb06c-192">Para Políticas de Aplicativo (na captura de tela 4), adicione somente as políticas de aplicativo necessárias.</span><span class="sxs-lookup"><span data-stu-id="eb06c-192">For Application Policies (in the 4th screenshot), only add the application policies required.</span></span> <span data-ttu-id="eb06c-193">Confirme suas escolhas com seus administradores de segurança.</span><span class="sxs-lookup"><span data-stu-id="eb06c-193">Confirm your choices with your security admins.</span></span>



<span data-ttu-id="eb06c-194">Para configurar a AC para permitir que o solicitante especifique o período de validade, execute os seguintes comandos na AC:</span><span class="sxs-lookup"><span data-stu-id="eb06c-194">To configure the CA to allow the requester to specify the validity period, on the CA run the following commands:</span></span>

   1.  <span data-ttu-id="eb06c-195">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span><span class="sxs-lookup"><span data-stu-id="eb06c-195">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span></span>
   2.  <span data-ttu-id="eb06c-196">**net stop certsvc**</span><span class="sxs-lookup"><span data-stu-id="eb06c-196">**net stop certsvc**</span></span>

   3.  <span data-ttu-id="eb06c-197">**net start certsvc**</span><span class="sxs-lookup"><span data-stu-id="eb06c-197">**net start certsvc**</span></span>

4.  <span data-ttu-id="eb06c-198">Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-198">On the issuing CA, use the Certification Authority snap-in to publish the certificate template.</span></span>

    1.  <span data-ttu-id="eb06c-199">Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="eb06c-199">Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.</span></span>

    2.  <span data-ttu-id="eb06c-200">Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .</span><span class="sxs-lookup"><span data-stu-id="eb06c-200">Validate that the template published by viewing it under the **Certificate Templates** folder.</span></span>


### <span data-ttu-id="eb06c-201">Tarefa 3 - Configurar pré-requisitos no servidor NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-201">Task 3 - Configure prerequisites on the NDES server</span></span>
<a id="task-3---configure-prerequisites-on-the-ndes-server" class="xliff"></a>
<span data-ttu-id="eb06c-202">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="eb06c-202">In this task you will:</span></span>

-   <span data-ttu-id="eb06c-203">Adicionar o NDES a um Windows Server e configurar o IIS para dar suporte ao NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-203">Add NDES to a Windows Server and configure IIS to support NDES</span></span>

-   <span data-ttu-id="eb06c-204">Adicionar a conta de serviço de NDES ao grupo IIS_IUSR</span><span class="sxs-lookup"><span data-stu-id="eb06c-204">Add the NDES Service account to the IIS_IUSR group</span></span>

-   <span data-ttu-id="eb06c-205">Definir o SPN da conta de serviço de NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-205">Set the SPN for the NDES Service account</span></span>




   1.  <span data-ttu-id="eb06c-206">No servidor que hospeda o NDES, você deve fazer logon como **Administrador Corporativo**e usar o [Assistente de Adição de Funções e Recursos](https://technet.microsoft.com/library/hh831809.aspx) para instalar o NDES:</span><span class="sxs-lookup"><span data-stu-id="eb06c-206">On the server that will hosts NDES, you must log on as a an **Enterprise Administrator**, and then use the [Add Roles and Features Wizard](https://technet.microsoft.com/library/hh831809.aspx) to install NDES:</span></span>

    1.  <span data-ttu-id="eb06c-207">No assistente, selecione **Serviços de Certificados do Active Directory** para acessar os Serviços de Função do AD CS.</span><span class="sxs-lookup"><span data-stu-id="eb06c-207">In the Wizard, select **Active Directory Certificate Services** to gain access to the AD CS Role Services.</span></span> <span data-ttu-id="eb06c-208">Selecione o **Serviço de Registro de Dispositivo de Rede**, desmarque **Autoridade de Certificação**e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="eb06c-208">Select the **Network Device Enrollment Service**, uncheck **Certification Authority**, and then complete the wizard.</span></span>

        > [!TIP]
        > <span data-ttu-id="eb06c-209">Na página **Progresso da Instalação** do assistente, não clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-209">On the **Installation progress** page of the wizard, do not click **Close**.</span></span> <span data-ttu-id="eb06c-210">Em vez disso, clique no link para **Configurar os Serviços de Certificados do Active Directory no servidor de destino**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-210">Instead, click the link for **Configure Active Directory Certificate Services on the destination server**.</span></span> <span data-ttu-id="eb06c-211">Isso abre o assistente de **Configuração AD CS** que você usa para a próxima tarefa.</span><span class="sxs-lookup"><span data-stu-id="eb06c-211">This opens the **AD CS Configuration** wizard that you use for the next task.</span></span> <span data-ttu-id="eb06c-212">Após Configuração AD CS abrir, você pode fechar o Assistente de Adição de Funções e Recursos.</span><span class="sxs-lookup"><span data-stu-id="eb06c-212">After AD CS Configuration opens, you can close the Add Roles and Features wizard.</span></span>

    2.  <span data-ttu-id="eb06c-213">Quando o NDES é adicionado ao servidor, o assistente também instala o IIS.</span><span class="sxs-lookup"><span data-stu-id="eb06c-213">When NDES is added to the server, the wizard also installs IIS.</span></span> <span data-ttu-id="eb06c-214">Verifique se o IIS tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="eb06c-214">Ensure IIS has the following configurations:</span></span>

        -   <span data-ttu-id="eb06c-215">**Servidor Web** &gt; **Segurança** &gt; **Filtragem de Solicitações**</span><span class="sxs-lookup"><span data-stu-id="eb06c-215">**Web Server** &gt; **Security** &gt; **Request Filtering**</span></span>

        -   <span data-ttu-id="eb06c-216">**Servidor Web** &gt; **Desenvolvimento de Aplicativos** &gt; **ASP.NET 3.5**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-216">**Web Server** &gt; **Application Development** &gt; **ASP.NET 3.5**.</span></span> <span data-ttu-id="eb06c-217">Instalar o ASP.NET 3.5 instalará o .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="eb06c-217">Installing ASP.NET 3.5 will install .NET Framework 3.5.</span></span> <span data-ttu-id="eb06c-218">Ao instalar o .NET Framework 3.5, instale o recurso **.NET Framework 3.5** principal e o **Ativação HTTP**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-218">When installing .NET Framework 3.5, install both the core **.NET Framework 3.5** feature and **HTTP Activation**.</span></span>

        -   <span data-ttu-id="eb06c-219">**Servidor Web** &gt; **Desenvolvimento de Aplicativos** &gt; **ASP.NET 4.5**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-219">**Web Server** &gt; **Application Development** &gt; **ASP.NET 4.5**.</span></span> <span data-ttu-id="eb06c-220">Instalar o ASP.NET 4,5 instalará o .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="eb06c-220">Installing ASP.NET 4.5 will install .NET Framework 4.5.</span></span> <span data-ttu-id="eb06c-221">Ao instalar o .NET Framework 4.5, instale o recurso principal do **.NET Framework 4.5**, o **ASP.NET 4.5** e o recurso **Serviços WCF** &gt; **Ativação HTTP**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-221">When installing .NET Framework 4.5, install the core **.NET Framework 4.5** feature, **ASP.NET 4.5**, and the **WCF Services** &gt; **HTTP Activation** feature.</span></span>

        -   <span data-ttu-id="eb06c-222">**Ferramentas de gerenciamento** &gt; **Compatibilidade de gerenciamento do IIS 6** &gt; **Compatibilidade de metabase do IIS 6**</span><span class="sxs-lookup"><span data-stu-id="eb06c-222">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 Metabase Compatibility**</span></span>

        -   <span data-ttu-id="eb06c-223">**Ferramentas de gerenciamento** &gt; **Compatibilidade de gerenciamento do IIS 6** &gt; **Compatibilidade de WMI do IIS 6**</span><span class="sxs-lookup"><span data-stu-id="eb06c-223">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 WMI Compatibility**</span></span>

  2.  <span data-ttu-id="eb06c-224">No servidor, adicione a conta de serviço de NDES como membro do grupo **IIS_IUSR**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-224">On the server, add the NDES service account as a member of the **IIS_IUSR** group.</span></span>

   3.  <span data-ttu-id="eb06c-225">Em um prompt de comandos com privilégios elevados, execute o seguinte comando para definir o SPN da conta de serviço de NDES:</span><span class="sxs-lookup"><span data-stu-id="eb06c-225">In an elevated command prompt, run the following command to set the SPN of the NDES Service account:</span></span>

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   <span data-ttu-id="eb06c-226">Por exemplo, se seu servidor de NDES se chamar **Server01**, seu domínio for **Contoso.com**e a conta de serviço for **NDESService**, use:</span><span class="sxs-lookup"><span data-stu-id="eb06c-226">For example, if your NDES Server is named **Server01**, your domain is **Contoso.com**, and the service account is **NDESService**, use:</span></span>

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

### <span data-ttu-id="eb06c-227">Tarefa 4 - Configurar o NDES para uso com o Intune</span><span class="sxs-lookup"><span data-stu-id="eb06c-227">Task 4 - Configure NDES for use with Intune</span></span>
<a id="task-4---configure-ndes-for-use-with-intune" class="xliff"></a>
<span data-ttu-id="eb06c-228">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="eb06c-228">In this task you will:</span></span>

-   <span data-ttu-id="eb06c-229">Configurar o NDES para uso com a AC emissora</span><span class="sxs-lookup"><span data-stu-id="eb06c-229">Configure NDES for use with the issuing CA</span></span>

-   <span data-ttu-id="eb06c-230">Associar o certificado de autenticação do servidor (SSL) no IIS</span><span class="sxs-lookup"><span data-stu-id="eb06c-230">Bind the server authentication (SSL) certificate in IIS</span></span>

-   <span data-ttu-id="eb06c-231">Configurar a Filtragem de Solicitações no IIS</span><span class="sxs-lookup"><span data-stu-id="eb06c-231">Configure Request Filtering in IIS</span></span>

##### <span data-ttu-id="eb06c-232">Para configurar o NDES para uso com o Intune</span><span class="sxs-lookup"><span data-stu-id="eb06c-232">To configure NDES for use with Intune</span></span>
<a id="to-configure-ndes-for-use-with-intune" class="xliff"></a>

1.  <span data-ttu-id="eb06c-233">No servidor de NDES, abra o Assistente de Configuração do AD CS e faça as seguintes configurações.</span><span class="sxs-lookup"><span data-stu-id="eb06c-233">On the NDES Server, open the AD CS Configuration wizard and then make the following configurations.</span></span>

    > [!TIP]
    > <span data-ttu-id="eb06c-234">Se você clicou no link na tarefa anterior, o assistente já está aberto.</span><span class="sxs-lookup"><span data-stu-id="eb06c-234">If you clicked the link in the previous task, this wizard is already open.</span></span> <span data-ttu-id="eb06c-235">Caso contrário, abra o Gerenciador do Servidor para acessar a configuração pós-implantação dos Serviços de Certificados do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eb06c-235">Otherwise, open Server Manager to access the post-deployment configuration for Active Directory Certificate Services.</span></span>

    -   <span data-ttu-id="eb06c-236">Na página **Serviços de Função** , selecione **Serviço de Registro de Dispositivo de Rede**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-236">On the **Role Services** Page, select the **Network Device Enrollment Service**.</span></span>

    -   <span data-ttu-id="eb06c-237">Na página **Conta de Serviço para NDES** , especifique a Conta de Serviço de NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-237">On the **Service Account for NDES** page, specify the NDES Service Account.</span></span>

    -   <span data-ttu-id="eb06c-238">Na página **AC para NDES** , clique em **Selecionar**e selecione a AC emissora em que você configurou o modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-238">On the **CA for NDES** page, click **Select**, and then select the issuing CA where you configured the certificate template.</span></span>

    -   <span data-ttu-id="eb06c-239">Na página **Criptografia para NDES** , defina o comprimento de chave para atender aos requisitos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="eb06c-239">On the **Cryptography for NDES** page, set the key length to meet your company requirements.</span></span>

    <span data-ttu-id="eb06c-240">Na página **Confirmação** , clique em **Configurar** para concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="eb06c-240">On the **Confirmation** page, click **Configure** to complete the wizard.</span></span>

2.  <span data-ttu-id="eb06c-241">Após concluir o assistente, edite a seguinte chave do Registro no Servidor de NDES:</span><span class="sxs-lookup"><span data-stu-id="eb06c-241">After the wizard completes, edit the following registry key on the NDES Server:</span></span>

    -   <span data-ttu-id="eb06c-242">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span><span class="sxs-lookup"><span data-stu-id="eb06c-242">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span></span>

    <span data-ttu-id="eb06c-243">Para editar essa chave, identifique a **Finalidade** do modelo de certificado, conforme encontrada na guia **Tratamento de Solicitação**, e edite a entrada correspondente no Registro substituindo os dados existentes pelo nome do modelo de certificado (não o nome de exibição do modelo) que você especificou na Tarefa 1.</span><span class="sxs-lookup"><span data-stu-id="eb06c-243">To edit this key, identify the certificate template's **Purpose**, as found on its **Request Handling** tab, and then edit the corresponding entry in the registry by replacing the existing data with the name of the certificate template (not the display name of the template) that you specified in Task 1.</span></span> <span data-ttu-id="eb06c-244">A tabela a seguir mapeia a finalidade do modelo de certificado de acordo com os valores do Registro:</span><span class="sxs-lookup"><span data-stu-id="eb06c-244">The following table maps the certificate template purpose to the values in the registry:</span></span>

    |<span data-ttu-id="eb06c-245">Finalidade do modelo de certificado (na guia Tratamento de Solicitação)</span><span class="sxs-lookup"><span data-stu-id="eb06c-245">Certificate template Purpose (On the Request Handling tab)</span></span>|<span data-ttu-id="eb06c-246">Valor de registro a ser editado</span><span class="sxs-lookup"><span data-stu-id="eb06c-246">Registry value to edit</span></span>|<span data-ttu-id="eb06c-247">O valor mostrado no console de administração do Intune para o perfil do protocolo SCEP</span><span class="sxs-lookup"><span data-stu-id="eb06c-247">Value seen in the Intune admin console for the SCEP profile</span></span>|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |<span data-ttu-id="eb06c-248">Assinatura</span><span class="sxs-lookup"><span data-stu-id="eb06c-248">Signature</span></span>|<span data-ttu-id="eb06c-249">SignatureTemplate</span><span class="sxs-lookup"><span data-stu-id="eb06c-249">SignatureTemplate</span></span>|<span data-ttu-id="eb06c-250">Assinatura digital</span><span class="sxs-lookup"><span data-stu-id="eb06c-250">Digital Signature</span></span>|
    |<span data-ttu-id="eb06c-251">Criptografia</span><span class="sxs-lookup"><span data-stu-id="eb06c-251">Encryption</span></span>|<span data-ttu-id="eb06c-252">EncryptionTemplate</span><span class="sxs-lookup"><span data-stu-id="eb06c-252">EncryptionTemplate</span></span>|<span data-ttu-id="eb06c-253">Codificação de chave</span><span class="sxs-lookup"><span data-stu-id="eb06c-253">Key Encipherment</span></span>|
    |<span data-ttu-id="eb06c-254">Assinatura e criptografia</span><span class="sxs-lookup"><span data-stu-id="eb06c-254">Signature and encryption</span></span>|<span data-ttu-id="eb06c-255">GeneralPurposeTemplate</span><span class="sxs-lookup"><span data-stu-id="eb06c-255">GeneralPurposeTemplate</span></span>|<span data-ttu-id="eb06c-256">Codificação de chave</span><span class="sxs-lookup"><span data-stu-id="eb06c-256">Key Encipherment</span></span><br /><br /><span data-ttu-id="eb06c-257">Assinatura digital</span><span class="sxs-lookup"><span data-stu-id="eb06c-257">Digital Signature</span></span>|
    <span data-ttu-id="eb06c-258">Por exemplo, se a Finalidade do seu modelo de certificado for **Criptografia**, edite o valor de **EncryptionTemplate** como o nome do seu modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-258">For example, if the Purpose of your certificate template is **Encryption**, then edit the **EncryptionTemplate** value to be the name of your certificate template.</span></span>

3. <span data-ttu-id="eb06c-259">O servidor NDES receberá URLs muito longas (consultas), o que exige que você adicione duas entradas de Registro:</span><span class="sxs-lookup"><span data-stu-id="eb06c-259">The NDES server will receive very long URL’s (queries), which require that you add two registry entries:</span></span>

    |<span data-ttu-id="eb06c-260">Local</span><span class="sxs-lookup"><span data-stu-id="eb06c-260">Location</span></span>|<span data-ttu-id="eb06c-261">Valor</span><span class="sxs-lookup"><span data-stu-id="eb06c-261">Value</span></span>|<span data-ttu-id="eb06c-262">Tipo</span><span class="sxs-lookup"><span data-stu-id="eb06c-262">Type</span></span>|<span data-ttu-id="eb06c-263">Dados</span><span class="sxs-lookup"><span data-stu-id="eb06c-263">Data</span></span>|
    |-------|-----|----|----|
    |<span data-ttu-id="eb06c-264">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="eb06c-264">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="eb06c-265">MaxFieldLength</span><span class="sxs-lookup"><span data-stu-id="eb06c-265">MaxFieldLength</span></span>|<span data-ttu-id="eb06c-266">DWORD</span><span class="sxs-lookup"><span data-stu-id="eb06c-266">DWORD</span></span>|<span data-ttu-id="eb06c-267">65534 (decimal)</span><span class="sxs-lookup"><span data-stu-id="eb06c-267">65534 (decimal)</span></span>|
    |<span data-ttu-id="eb06c-268">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="eb06c-268">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="eb06c-269">MaxRequestBytes</span><span class="sxs-lookup"><span data-stu-id="eb06c-269">MaxRequestBytes</span></span>|<span data-ttu-id="eb06c-270">DWORD</span><span class="sxs-lookup"><span data-stu-id="eb06c-270">DWORD</span></span>|<span data-ttu-id="eb06c-271">65534 (decimal)</span><span class="sxs-lookup"><span data-stu-id="eb06c-271">65534 (decimal)</span></span>|


4. <span data-ttu-id="eb06c-272">No Gerenciador do IIS, escolha **Site Padrão** -> **Filtragem de Solicitações** -> **Editar Configuração do Recurso** e altere o **Comprimento máximo da URL** e **Cadeia de caracteres de consulta máxima** para *65534*, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-272">In IIS manager, choose **Default Web Site** -> **Request Filtering** -> **Edit Feature Setting**, and change the **Maximum URL length** and **Maximum query string** to *65534*, as shown.</span></span>

    ![Comprimento máximo de URL e consulta do IIS](..\media\SCEP_IIS_max_URL.png)

5.  <span data-ttu-id="eb06c-274">Reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="eb06c-274">Restart the server.</span></span> <span data-ttu-id="eb06c-275">Executar **iisreset** no servidor não será suficiente para finalizar as alterações.</span><span class="sxs-lookup"><span data-stu-id="eb06c-275">Running **iisreset** on the server will not be sufficient to finalize these changes.</span></span>
6. <span data-ttu-id="eb06c-276">Navegue até http://*FQDN*/certsrv/mscep/mscep.dll.</span><span class="sxs-lookup"><span data-stu-id="eb06c-276">Browse to http://*FQDN*/certsrv/mscep/mscep.dll.</span></span> <span data-ttu-id="eb06c-277">Você deve ver uma página NDES semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="eb06c-277">You should see an NDES page similar to this:</span></span>

    ![Testar NDES](..\media\SCEP_NDES_URL.png)

    <span data-ttu-id="eb06c-279">Se você receber **503 Serviço indisponível**, verifique o Visualizador de Eventos.</span><span class="sxs-lookup"><span data-stu-id="eb06c-279">If you get a **503 Service unavailable**, check the eventviewer.</span></span> <span data-ttu-id="eb06c-280">É provável que o pool de aplicativos seja interrompido devido a um direito ausente para o usuário NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-280">It's likely that the application pool is stopped due to a missing right for the NDES user.</span></span> <span data-ttu-id="eb06c-281">Esses direitos são descritos na Tarefa 1.</span><span class="sxs-lookup"><span data-stu-id="eb06c-281">Those rights are described in Task 1.</span></span>

##### <span data-ttu-id="eb06c-282">Para instalar e associar os certificados no Servidor de NDES</span><span class="sxs-lookup"><span data-stu-id="eb06c-282">To Install and bind certificates on the NDES Server</span></span>
<a id="to-install-and-bind-certificates-on-the-ndes-server" class="xliff"></a>

1.  <span data-ttu-id="eb06c-283">No seu Servidor de NDES, solicite e instale um certificado de **autenticação de servidor** por meio da sua AC interna ou pública.</span><span class="sxs-lookup"><span data-stu-id="eb06c-283">On your NDES Server, request and install a **server authentication** certificate from your internal CA or public CA.</span></span> <span data-ttu-id="eb06c-284">Em seguida, você associará esse certificado SSL no IIS.</span><span class="sxs-lookup"><span data-stu-id="eb06c-284">You will then bind this SSL certificate in IIS.</span></span>

    > [!TIP]
    > <span data-ttu-id="eb06c-285">Depois de associar o certificado SSL no IIS, você também instalará um certificado de autenticação de cliente.</span><span class="sxs-lookup"><span data-stu-id="eb06c-285">After you bind the SSL certificate in IIS, you will also install a client authentication certificate.</span></span> <span data-ttu-id="eb06c-286">Esse certificado pode ser emitido por qualquer AC em que o Servidor de NDES confie.</span><span class="sxs-lookup"><span data-stu-id="eb06c-286">This certificate can be issued by any CA that is trusted by the NDES Server.</span></span> <span data-ttu-id="eb06c-287">Embora não seja uma prática recomendada, você pode usar o mesmo certificado para autenticação de servidor e cliente, desde que o certificado tenha os dois EKUs (Usos Avançados de Chave).</span><span class="sxs-lookup"><span data-stu-id="eb06c-287">Although it is not a best practice, you can use the same certificate for both server and client authentication as long as the certificate has both Enhance Key Usages (EKU’s).</span></span> <span data-ttu-id="eb06c-288">Examine as etapas a seguir para obter informações sobre esses certificados de autenticação.</span><span class="sxs-lookup"><span data-stu-id="eb06c-288">Review the following steps for information about these authentication certificates.</span></span>

    1.  <span data-ttu-id="eb06c-289">Depois de obter o certificado de autenticação de servidor, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e clique em **Ligações** no painel **Ações** .</span><span class="sxs-lookup"><span data-stu-id="eb06c-289">After you obtain the server authentication certificate, open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then click **Bindings** in the **Actions** pane.</span></span>

    2.  <span data-ttu-id="eb06c-290">Clique em **Adicionar**, defina o **Tipo** como **https**e verifique se a porta é **443**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-290">Click **Add**, set **Type** to **https**, and then ensure the port is **443**.</span></span> <span data-ttu-id="eb06c-291">(Somente a porta 443 tem suporte para o Intune autônomo).</span><span class="sxs-lookup"><span data-stu-id="eb06c-291">(Only port 443 is supported for standalone Intune.</span></span>

    3.  <span data-ttu-id="eb06c-292">Para **Certificado SSL**, especifique o certificado de autenticação de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb06c-292">For **SSL certificate**, specify the server authentication certificate.</span></span>

        > [!NOTE]
        > <span data-ttu-id="eb06c-293">Se o servidor de NDES usar um nome interno e externo para um único endereço de rede, o certificado de autenticação de servidor deverá ter um **Nome da Entidade** com um nome de servidor público externo e um **Nome Alternativo da Entidade** que inclua o nome do servidor interno.</span><span class="sxs-lookup"><span data-stu-id="eb06c-293">If the NDES server uses both an external and internal name for a single network address, the server authentication certificate must have a **Subject Name** with an external public server name, and a **Subject Alternative Name** that includes the internal server name.</span></span>

2.  <span data-ttu-id="eb06c-294">No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública.</span><span class="sxs-lookup"><span data-stu-id="eb06c-294">On your NDES Server, request and install a **client authentication** certificate from your internal CA, or a public certificate authority.</span></span> <span data-ttu-id="eb06c-295">Pode ser o mesmo certificado que o certificado de autenticação de servidor se o certificado tiver os dois recursos.</span><span class="sxs-lookup"><span data-stu-id="eb06c-295">This can be the same certificate as the server authentication certificate if that certificate has both capabilities.</span></span>

    <span data-ttu-id="eb06c-296">O certificado de autenticação de cliente deve ter as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="eb06c-296">The client authentication certificate must have the following properties:</span></span>

    <span data-ttu-id="eb06c-297">**Uso Avançado de Chave** - Isso deve incluir a **Autenticação de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-297">**Enhanced Key Usage** - This must include **Client Authentication**.</span></span>

    <span data-ttu-id="eb06c-298">**Nome da Entidade**: deve ser igual ao nome DNS do servidor em que você está instalando o certificado (o Servidor de NDES).</span><span class="sxs-lookup"><span data-stu-id="eb06c-298">**Subject Name** - This must be equal to the DNS name of the server where you are installing the certificate (the NDES Server).</span></span>

##### <span data-ttu-id="eb06c-299">Para configurar a Filtragem de Solicitações do IIS</span><span class="sxs-lookup"><span data-stu-id="eb06c-299">To configure IIS Request Filtering</span></span>
<a id="to-configure-iis-request-filtering" class="xliff"></a>

1.  <span data-ttu-id="eb06c-300">No Servidor de NDES, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e abra a **Filtragem de Solicitações**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-300">On the NDES Server open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then open **Request Filtering**.</span></span>

2.  <span data-ttu-id="eb06c-301">Clique em **Editar Configurações de Recurso**e defina o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eb06c-301">Click **Edit Feature Settings**, and then set the following:</span></span>

    <span data-ttu-id="eb06c-302">**cadeia de caracteres de consulta (Bytes)** = **65534**</span><span class="sxs-lookup"><span data-stu-id="eb06c-302">**query string (Bytes)** = **65534**</span></span>

    <span data-ttu-id="eb06c-303">**Tamanho máximo da URL (Bytes)** = **65534**</span><span class="sxs-lookup"><span data-stu-id="eb06c-303">**Maximum URL length (Bytes)** = **65534**</span></span>

3.  <span data-ttu-id="eb06c-304">Examine a seguinte chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="eb06c-304">Review the following registry key:</span></span>

    <span data-ttu-id="eb06c-305">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span><span class="sxs-lookup"><span data-stu-id="eb06c-305">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span></span>

    <span data-ttu-id="eb06c-306">Certifique-se de que os seguintes valores sejam definidos como entradas DWORD:</span><span class="sxs-lookup"><span data-stu-id="eb06c-306">Ensure the following values are set as DWORD entries:</span></span>

    <span data-ttu-id="eb06c-307">Nome: **MaxFieldLength**, com um valor decimal de **65534**</span><span class="sxs-lookup"><span data-stu-id="eb06c-307">Name: **MaxFieldLength**, with a decimal value of **65534**</span></span>

    <span data-ttu-id="eb06c-308">Nome: **MaxRequestBytes**, com um valor decimal de **65534**</span><span class="sxs-lookup"><span data-stu-id="eb06c-308">Name: **MaxRequestBytes**, with a decimal value of **65534**</span></span>

4.  <span data-ttu-id="eb06c-309">Reinicialize o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-309">Reboot the NDES server.</span></span> <span data-ttu-id="eb06c-310">Agora, o servidor está pronto para dar suporte ao Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-310">The server is now ready to support the Certificate Connector.</span></span>

### <span data-ttu-id="eb06c-311">Tarefa 5 - Habilitar, instalar e configurar o Conector de Certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="eb06c-311">Task 5 - Enable, install, and configure the Intune Certificate Connector</span></span>
<a id="task-5---enable-install-and-configure-the-intune-certificate-connector" class="xliff"></a>
<span data-ttu-id="eb06c-312">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="eb06c-312">In this task you will:</span></span>

<span data-ttu-id="eb06c-313">Habilitar o suporte para NDES no Intune.</span><span class="sxs-lookup"><span data-stu-id="eb06c-313">Enable support for NDES in Intune.</span></span>

<span data-ttu-id="eb06c-314">Baixar, instalar e configurar o Conector de Certificado no Servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="eb06c-314">Download, install, and configure the Certificate Connector on the NDES Server.</span></span>

##### <span data-ttu-id="eb06c-315">Para habilitar o suporte ao Conector de Certificado</span><span class="sxs-lookup"><span data-stu-id="eb06c-315">To enable support for the Certificate Connector</span></span>
<a id="to-enable-support-for-the-certificate-connector" class="xliff"></a>

1.  <span data-ttu-id="eb06c-316">Abra o [Console de administração do Intune](https://manage.microsoft.com), clique em **Administrador** &gt; **Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-316">Open the [Intune administration console](https://manage.microsoft.com), click **Admin** &gt; **Certificate Connector**.</span></span>

2.  <span data-ttu-id="eb06c-317">Clique em **Configurar Conector de Certificado Local**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-317">Click **Configure On-Premises Certificate Connector**.</span></span>

3.  <span data-ttu-id="eb06c-318">Selecione **Habilitar Conector de Certificado**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-318">Select **Enable Certificate Connector**, and then click **OK**.</span></span>

##### <span data-ttu-id="eb06c-319">Para baixar, instalar e configurar o Conector de Certificado</span><span class="sxs-lookup"><span data-stu-id="eb06c-319">To download, install and configure the Certificate Connector</span></span>
<a id="to-download-install-and-configure-the-certificate-connector" class="xliff"></a>

1.  <span data-ttu-id="eb06c-320">Abra o [Console de administração do Intune](https://manage.microsoft.com) e, em seguida, clique em **Administrador** &gt; **Gerenciamento de Dispositivo Móvel** &gt; **Conector de Certificado** &gt; **Baixar Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-320">Open the [Intune administration console](https://manage.microsoft.com), and then click **Admin** &gt; **Mobile Device Management** &gt; **Certificate Connector** &gt; **Download Certificate Connector**.</span></span>

2.  <span data-ttu-id="eb06c-321">Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**) em um servidor Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="eb06c-321">After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**) on a Windows Server 2012 R2 server.</span></span> <span data-ttu-id="eb06c-322">O instalador também instala o módulo de política para NDES e o Serviço Web de CRP.</span><span class="sxs-lookup"><span data-stu-id="eb06c-322">The installer also installs the policy module for NDES and the CRP Web Service.</span></span> <span data-ttu-id="eb06c-323">(O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).</span><span class="sxs-lookup"><span data-stu-id="eb06c-323">(The CRP Web Service, CertificateRegistrationSvc, runs as an application in IIS.)</span></span>

    > [!NOTE]
    > <span data-ttu-id="eb06c-324">Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-324">When you install NDES for standalone Intune, the CRP service automatically installs with the Certificate Connector.</span></span> <span data-ttu-id="eb06c-325">Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.</span><span class="sxs-lookup"><span data-stu-id="eb06c-325">When you use Intune with Configuration Manager, you install the Certificate Registration Point as a separate site system role.</span></span>

3.  <span data-ttu-id="eb06c-326">Quando for solicitado o certificado de cliente do Conector de Certificado, clique em **Selecionar**e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Tarefa 3.</span><span class="sxs-lookup"><span data-stu-id="eb06c-326">When prompted for the client certificate for the Certificate Connector, click **Select**, and select the **client authentication** certificate you installed on your NDES Server in Task 3.</span></span>

    <span data-ttu-id="eb06c-327">Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** .</span><span class="sxs-lookup"><span data-stu-id="eb06c-327">After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface.</span></span> <span data-ttu-id="eb06c-328">Embora o certificado selecionado não seja exibido, clique em **Avançar** para ver as propriedades do certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-328">Although the certificate you selected is not shown, click **Next** to view the properties of that certificate.</span></span> <span data-ttu-id="eb06c-329">Em seguida, clique em **Avançar**e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-329">Then click **Next**, and then click **Install**.</span></span>

4.  <span data-ttu-id="eb06c-330">Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-330">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

    > [!TIP]
    > <span data-ttu-id="eb06c-331">Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="eb06c-331">If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:</span></span>
    >
    > <span data-ttu-id="eb06c-332">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span><span class="sxs-lookup"><span data-stu-id="eb06c-332">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span></span>

5.  <span data-ttu-id="eb06c-333">Na interface do usuário do **Conector de Certificado** :</span><span class="sxs-lookup"><span data-stu-id="eb06c-333">In the **Certificate Connector** UI:</span></span>

    <span data-ttu-id="eb06c-334">Clique em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.</span><span class="sxs-lookup"><span data-stu-id="eb06c-334">Click **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.</span></span>

    <span data-ttu-id="eb06c-335">Se sua organização usa um servidor proxy e o proxy é necessário para o servidor NDES acessar a Internet, clique em **Usar servidor proxy** e informe o nome do servidor proxy, a porta e as credenciais de conta usadas para a conexão.</span><span class="sxs-lookup"><span data-stu-id="eb06c-335">If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.</span></span>

    <span data-ttu-id="eb06c-336">Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-336">Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.</span></span>

    <span data-ttu-id="eb06c-337">Agora você pode fechar a interface do usuário do Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="eb06c-337">You can now close the Certificate Connector UI.</span></span>

6.  <span data-ttu-id="eb06c-338">Abra um prompt de comando e digite **services.msc**, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector do Intune** e clique em **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="eb06c-338">Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Intune Connector Service**, and then click **Restart**.</span></span>

<span data-ttu-id="eb06c-339">Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :</span><span class="sxs-lookup"><span data-stu-id="eb06c-339">To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:</span></span>

<span data-ttu-id="eb06c-340">**https:// &lt;FQDN_do_seu_servidor_NDES&gt;/certsrv/mscep/mscep.dll**</span><span class="sxs-lookup"><span data-stu-id="eb06c-340">**https:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**</span></span>

## <span data-ttu-id="eb06c-341">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="eb06c-341">Next steps</span></span>
<a id="next-steps" class="xliff"></a>
<span data-ttu-id="eb06c-342">Agora você está pronto para configurar perfis de certificado, conforme descrito em [Configure certificate profiles](Configure-Intune-certificate-profiles.md) (Configurar perfis de certificado).</span><span class="sxs-lookup"><span data-stu-id="eb06c-342">You are now ready to configure certificate profiles, as described in [Configure certificate profiles](Configure-Intune-certificate-profiles.md).</span></span>
