---
title: Configurar e gerenciar certificados SCEP com o Intune
titleSuffix: Intune on Azure
description: Saiba como configurar sua infraestrutura e, depois, criar e atribuir perfis de certificado SCEP do Intune.
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d567d85f-e4ee-458e-bef7-6e275467efce
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e29e79b8598eddba951b3f8ee7a7bcd5c6271f83
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
<<<<<<< HEAD
# <span data-ttu-id="22f90-103">Configurar e gerenciar certificados SCEP com o Intune</span><span class="sxs-lookup"><span data-stu-id="22f90-103">Configure and manage SCEP certificates with Intune</span></span>
=======
# Configurar e gerenciar certificados SCEP com o Intune
>>>>>>> live
<a id="configure-and-manage-scep-certificates-with-intune" class="xliff"></a>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="22f90-104">Este tópico mostra como configurar sua infraestrutura e depois criar e atribuir perfis de certificado de protocolo SCEP (Simple Certificate Enrollment Protocol) com o Intune.</span><span class="sxs-lookup"><span data-stu-id="22f90-104">This topic shows how to configure your infrastructure, then create and assign Simple Certificate Enrollment Protocol (SCEP) certificate profiles with Intune.</span></span>

<<<<<<< HEAD
## <span data-ttu-id="22f90-105">Configurar a infraestrutura local</span><span class="sxs-lookup"><span data-stu-id="22f90-105">Configure on-premises infrastructure</span></span>
=======
## Configurar a infraestrutura local
>>>>>>> live
<a id="configure-on-premises-infrastructure" class="xliff"></a>

-    <span data-ttu-id="22f90-106">**Domínio do Active Directory**: todos os servidores listados nesta seção (exceto pelo Servidor Proxy de Aplicativo Web) devem ser ingressados em seu domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22f90-106">**Active Directory domain**: All servers listed in this section (except for the Web Application Proxy Server) must be joined to your Active Directory domain.</span></span>

-  <span data-ttu-id="22f90-107">**AC (Autoridade de Certificação)**: uma AC (Autoridade de Certificação) Corporativa que é executada em uma edição Enterprise do Windows Server 2008 R2 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="22f90-107">**Certification Authority** (CA): An Enterprise Certification Authority (CA) that runs on an Enterprise edition of Windows Server 2008 R2 or later.</span></span> <span data-ttu-id="22f90-108">Não há suporte para ACs autônomas.</span><span class="sxs-lookup"><span data-stu-id="22f90-108">A Standalone CA is not supported.</span></span> <span data-ttu-id="22f90-109">Para obter detalhes, confira [Instalar a Autoridade de Certificação](http://technet.microsoft.com/library/jj125375.aspx).</span><span class="sxs-lookup"><span data-stu-id="22f90-109">For details, see [Install the Certification Authority](http://technet.microsoft.com/library/jj125375.aspx).</span></span>
    <span data-ttu-id="22f90-110">Se a sua AC executar o Windows Server 2008 R2, você deve [instalar o hotfix de KB2483564](http://support.microsoft.com/kb/2483564/).</span><span class="sxs-lookup"><span data-stu-id="22f90-110">If your CA runs Windows Server 2008 R2, you must [install the hotfix from KB2483564](http://support.microsoft.com/kb/2483564/).</span></span>

-  <span data-ttu-id="22f90-111">**Servidor NDES**: em um servidor que executa o Windows Server 2012 R2 ou posterior, você deve configurar o NDES (Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="22f90-111">**NDES Server**: On a server that runs Windows Server 2012 R2 or later, you must setup up the Network Device Enrollment Service (NDES).</span></span> <span data-ttu-id="22f90-112">O Intune não dá suporte ao uso do NDES quando ele é executado em um servidor que também executa a AC Corporativa.</span><span class="sxs-lookup"><span data-stu-id="22f90-112">Intune does not support using NDES when it runs on a server that also runs the Enterprise CA.</span></span> <span data-ttu-id="22f90-113">Consulte [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) (Diretrizes de Serviço de Registro de Dispositivo de Rede) para obter instruções sobre como configurar o Windows Server 2012 R2 para hospedar o Serviço de Registro de Dispositivo de Rede.</span><span class="sxs-lookup"><span data-stu-id="22f90-113">See [Network Device Enrollment Service Guidance](http://technet.microsoft.com/library/hh831498.aspx) for instructions on how to configure Windows Server 2012 R2 to host the Network Device Enrollment Service.</span></span>
<span data-ttu-id="22f90-114">O servidor NDES deve ter ingressado no domínio que hospeda a AC e não estar no mesmo servidor que a AC.</span><span class="sxs-lookup"><span data-stu-id="22f90-114">The NDES server must be domain joined to the domain that hosts the CA, and not be on the same server as the CA.</span></span> <span data-ttu-id="22f90-115">Para obter mais informações sobre como implantar o servidor NDES em uma floresta separada, rede isolada ou domínio interno podem ser encontradas em [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx) (Usando um módulo de política com o Serviço de Registro de Dispositivo de Rede).</span><span class="sxs-lookup"><span data-stu-id="22f90-115">More information about deploying the NDES server in a separate forest, isolated network or internal domain can be found in [Using a Policy Module with the Network Device Enrollment Service](https://technet.microsoft.com/library/dn473016.aspx).</span></span>

-  <span data-ttu-id="22f90-116">**Conector de Certificado do Microsoft Intune**: use o portal do Intune para baixar o instalador do **Conector de Certificado** (**ndesconnectorssetup.exe**).</span><span class="sxs-lookup"><span data-stu-id="22f90-116">**Microsoft Intune Certificate Connector**: Use the Intune portal to download the **Certificate Connector** installer (**ndesconnectorssetup.exe**).</span></span> <span data-ttu-id="22f90-117">Em seguida, você pode executar **ndesconnectorssetup.exe** no computador em que deseja instalar o Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-117">Then you can run **ndesconnectorssetup.exe** on the computer where you want to install the Certificate Connector.</span></span> 
-  <span data-ttu-id="22f90-118">**Servidor Proxy de Aplicativos Web** (opcional): use um servidor que executa o Windows Server 2012 R2 ou posterior como servidor WAP (Proxy de Aplicativo Web).</span><span class="sxs-lookup"><span data-stu-id="22f90-118">**Web Application Proxy Server** (optional): Use a server that runs Windows Server 2012 R2  or later as a Web Application Proxy (WAP) server.</span></span> <span data-ttu-id="22f90-119">Essa configuração:</span><span class="sxs-lookup"><span data-stu-id="22f90-119">This configuration:</span></span>
    -  <span data-ttu-id="22f90-120">Permite que os dispositivos recebam certificados usando uma conexão com a Internet.</span><span class="sxs-lookup"><span data-stu-id="22f90-120">Allows devices to receive certificates using an Internet connection.</span></span>
    -  <span data-ttu-id="22f90-121">Trata-se de uma recomendação de segurança quando os dispositivos se conectam pela Internet para receber e renovar certificados.</span><span class="sxs-lookup"><span data-stu-id="22f90-121">Is a security recommendation when devices connect through the Internet to receive and renew certificates.</span></span>

 > [!NOTE]           
> -    <span data-ttu-id="22f90-122">O servidor que hospeda o WAP [deve instalar uma atualização](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) que habilita o suporte para as URLs longas que são usadas pelo Serviço de Registro de Dispositivo de Rede.</span><span class="sxs-lookup"><span data-stu-id="22f90-122">The server that hosts WAP [must install an update](http://blogs.technet.com/b/ems/archive/2014/12/11/hotfix-large-uri-request-in-web-application-proxy-on-windows-server-2012-r2.aspx) that enables support for the long URLs that are used by the Network Device Enrollment Service.</span></span> <span data-ttu-id="22f90-123">Essa atualização está incluída no [pacote cumulativo de atualizações de dezembro de 2014](http://support.microsoft.com/kb/3013769)ou individualmente no [KB3011135](http://support.microsoft.com/kb/3011135).</span><span class="sxs-lookup"><span data-stu-id="22f90-123">This update is included with the [December 2014 update rollup](http://support.microsoft.com/kb/3013769), or individually from [KB3011135](http://support.microsoft.com/kb/3011135).</span></span>
>-  <span data-ttu-id="22f90-124">Além disso, o servidor que hospeda o WAP deve ter um certificado SSL que corresponde ao nome que está sendo publicado para clientes externos, bem como confiar no certificado SSL que é usado no servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-124">Also, the server that hosts WAP must have a SSL certificate that matches the name being published to external clients as well as trust the SSL certificate that is used on the NDES server.</span></span> <span data-ttu-id="22f90-125">Esses certificados habilitam o servidor WAP a encerrar a conexão SSL de clientes e a criar uma nova conexão SSL com o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-125">These certificates enable the WAP server to terminate the SSL connection from clients, and create a new SSL connection to the NDES server.</span></span>
    <span data-ttu-id="22f90-126">Para obter mais informações sobre certificados de WAP, consulte a seção **Planejar certificados** de [Planejando Publicar Aplicativos Usando o Proxy de Aplicativo Web](https://technet.microsoft.com/library/dn383650.aspx).</span><span class="sxs-lookup"><span data-stu-id="22f90-126">For information about certificates for WAP, see the **Plan certificates** section of [Planning to Publish Applications Using Web Application Proxy](https://technet.microsoft.com/library/dn383650.aspx).</span></span> <span data-ttu-id="22f90-127">Para obter informações gerais sobre servidores WAP, consulte [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx) (Trabalhando com o Proxy de Aplicativo Web).|</span><span class="sxs-lookup"><span data-stu-id="22f90-127">For general information about WAP servers, see [Working with Web Application Proxy](http://technet.microsoft.com/library/dn584113.aspx).|</span></span>

<<<<<<< HEAD
### <span data-ttu-id="22f90-128">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="22f90-128">Network requirements</span></span>
=======
### Requisitos de rede
>>>>>>> live
<a id="network-requirements" class="xliff"></a>

<span data-ttu-id="22f90-129">Da Internet para a rede de perímetro, permitir a porta 443 de todos os endereços IP/ hosts na internet para o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-129">From the Internet to perimeter network, allow port 443 from all hosts/IP addresses on the internet to the NDES server.</span></span>

<span data-ttu-id="22f90-130">Da rede de perímetro para a rede confiável, permitir todas as portas e protocolos necessários para acesso ao domínio no servidor NDES associado por domínio.</span><span class="sxs-lookup"><span data-stu-id="22f90-130">From the perimeter network to trusted network, allow all ports and protocols needed for domain access on the domain-joined NDES server.</span></span> <span data-ttu-id="22f90-131">O servidor NDES precisa acessar servidores de certificados, servidores DNS, servidores do Configuration Manager e controladores de domínio.</span><span class="sxs-lookup"><span data-stu-id="22f90-131">The NDES server needs access to the certificate servers, DNS servers, Configuration Manager servers and domain controllers.</span></span>

<span data-ttu-id="22f90-132">É recomendável publicar o servidor NDES através de um proxy, como o [Proxy de aplicativo do Azure AD](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), o [Proxy do Web Access](https://technet.microsoft.com/library/dn584107.aspx) ou um proxy de terceiros.</span><span class="sxs-lookup"><span data-stu-id="22f90-132">We recommend publishing the NDES server through a proxy, such as the [Azure AD application proxy](https://azure.microsoft.com/documentation/articles/active-directory-application-proxy-publish/), [Web Access Proxy](https://technet.microsoft.com/library/dn584107.aspx), or a third-party proxy.</span></span>


<<<<<<< HEAD
### <span data-ttu-id="22f90-133">Certificados e modelos</span><span class="sxs-lookup"><span data-stu-id="22f90-133">Certificates and templates</span></span>
=======
### Certificados e modelos
>>>>>>> live
<a id="certificates-and-templates" class="xliff"></a>

|<span data-ttu-id="22f90-134">Objeto</span><span class="sxs-lookup"><span data-stu-id="22f90-134">Object</span></span>|<span data-ttu-id="22f90-135">Detalhes</span><span class="sxs-lookup"><span data-stu-id="22f90-135">Details</span></span>|
|----------|-----------|
|<span data-ttu-id="22f90-136">**Modelo de certificado**</span><span class="sxs-lookup"><span data-stu-id="22f90-136">**Certificate Template**</span></span>|<span data-ttu-id="22f90-137">Configure este modelo na AC emissora.</span><span class="sxs-lookup"><span data-stu-id="22f90-137">Configure this template on your issuing CA.</span></span>|
|<span data-ttu-id="22f90-138">**Certificado de autenticação de cliente**</span><span class="sxs-lookup"><span data-stu-id="22f90-138">**Client authentication certificate**</span></span>|<span data-ttu-id="22f90-139">Solicitado pela AC emissora ou pública, você instala este certificado no servidor de NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-139">Requested from your issuing CA or public CA; you install this certificate on the NDES Server.</span></span>|
|<span data-ttu-id="22f90-140">**Certificado de autenticação de servidor**</span><span class="sxs-lookup"><span data-stu-id="22f90-140">**Server authentication certificate**</span></span>|<span data-ttu-id="22f90-141">Solicitado da AC emissora pública, você instala e associa o certificado SSL no IIS no servidor de NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-141">Requested from your issuing CA or public CA; you install and bind this SSL certificate in IIS on the NDES server.</span></span>|
|<span data-ttu-id="22f90-142">**Certificado de AC raiz confiável**</span><span class="sxs-lookup"><span data-stu-id="22f90-142">**Trusted Root CA certificate**</span></span>|<span data-ttu-id="22f90-143">Você o exporta como um arquivo **.cer** da AC raiz ou de qualquer dispositivo que confie na AC raiz e a atribui aos dispositivos usando o perfil de certificado de AC Confiável.</span><span class="sxs-lookup"><span data-stu-id="22f90-143">You export this as a **.cer** file from the root CA or any device which trusts the root CA, and assign it to devices by using the Trusted CA certificate profile.</span></span><br /><br /><span data-ttu-id="22f90-144">Você usa um único certificado de AC raiz confiável por plataforma de sistema operacional e o associa a cada perfil de certificado de raiz confiável que criar.</span><span class="sxs-lookup"><span data-stu-id="22f90-144">You use a single Trusted Root CA certificate per operating system platform, and associate it with each Trusted Root Certificate profile you create.</span></span><br /><br /><span data-ttu-id="22f90-145">Você pode usar certificados de AC raiz confiável adicionais quando necessário.</span><span class="sxs-lookup"><span data-stu-id="22f90-145">You can use additional Trusted Root CA certificates when needed.</span></span> <span data-ttu-id="22f90-146">Por exemplo, você pode fazer isso para fornecer uma relação de confiança a uma AC que conecta os certificados de autenticação do servidor aos pontos de acesso Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="22f90-146">For example, you might do this to provide a trust to a CA that signs the server authentication certificates for your Wi-Fi access points.</span></span>|

<<<<<<< HEAD
### <span data-ttu-id="22f90-147">Contas</span><span class="sxs-lookup"><span data-stu-id="22f90-147">Accounts</span></span>
=======
### Contas
>>>>>>> live
<a id="accounts" class="xliff"></a>

|<span data-ttu-id="22f90-148">Nome</span><span class="sxs-lookup"><span data-stu-id="22f90-148">Name</span></span>|<span data-ttu-id="22f90-149">Detalhes</span><span class="sxs-lookup"><span data-stu-id="22f90-149">Details</span></span>|
|--------|-----------|
|<span data-ttu-id="22f90-150">**Conta de serviço de NDES**</span><span class="sxs-lookup"><span data-stu-id="22f90-150">**NDES service account**</span></span>|<span data-ttu-id="22f90-151">Especifique uma conta de usuário de domínio para usar como conta de serviço de NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-151">Specify a domain user account to use as the NDES Service account.</span></span>|

<<<<<<< HEAD
## <span data-ttu-id="22f90-152">Configure sua infraestrutura</span><span class="sxs-lookup"><span data-stu-id="22f90-152">Configure your infrastructure</span></span>
<a id="configure-your-infrastructure" class="xliff"></a>
<span data-ttu-id="22f90-153">Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):</span><span class="sxs-lookup"><span data-stu-id="22f90-153">Before you can configure certificate profiles you must complete the following tasks, which require knowledge of Windows Server 2012 R2 and Active Directory Certificate Services (ADCS):</span></span>
=======
## Configure sua infraestrutura
<a id="configure-your-infrastructure" class="xliff"></a>
Antes de configurar perfis de certificado, você deve concluir as seguintes tarefas que exigem conhecimento do Windows Server 2012 R2 e dos AD CS (Serviços de Certificados do Active Directory):
>>>>>>> live

<span data-ttu-id="22f90-154">**Etapa 1**: Criar uma conta de serviço de NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-154">**Step 1**: Create an NDES service account</span></span>

<span data-ttu-id="22f90-155">**Etapa 2**: Configurar modelos de certificado na autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="22f90-155">**Step 2**: Configure certificate templates on the certification authority</span></span>

<span data-ttu-id="22f90-156">**Etapa 3**: Configurar pré-requisitos no servidor NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-156">**Step 3**: Configure prerequisites on the NDES server</span></span>

<span data-ttu-id="22f90-157">**Etapa 4**: Configurar o NDES para uso com o Intune</span><span class="sxs-lookup"><span data-stu-id="22f90-157">**Step 4**: Configure NDES for use with Intune</span></span>

<span data-ttu-id="22f90-158">**Etapa 5**: Habilitar, instalar e configurar o Conector de Certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="22f90-158">**Step 5**: Enable, install, and configure the Intune Certificate Connector</span></span>

> [!NOTE]
<<<<<<< HEAD
> <span data-ttu-id="22f90-159">Devido a um problema conhecido, baixe, instale e configure o conector de certificado usando o procedimento a seguir: [Configurar a infraestrutura de certificado para SCEP -> Configurar a sua infraestrutura -> Tarefa 5](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)</span><span class="sxs-lookup"><span data-stu-id="22f90-159">Because of a known issue, download, install, and configure the certificate connector using the following procedure: [Configure certificate infrastructure for SCEP -> Configure your infrastructure -> Task 5](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)</span></span>


#### <span data-ttu-id="22f90-160">Etapa 1 - Criar uma conta de serviço de NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-160">Step 1 - Create an NDES service account</span></span>
<a id="step-1---create-an-ndes-service-account" class="xliff"></a>

<span data-ttu-id="22f90-161">Crie uma conta de usuário de domínio para usar como conta de serviço de NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-161">Create a domain user account to use as the NDES service account.</span></span> <span data-ttu-id="22f90-162">Especifique essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-162">You will specify this account when you configure templates on the issuing CA before you install and configure NDES.</span></span> <span data-ttu-id="22f90-163">Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como Serviço** e **Logon como um trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="22f90-163">Make sure the user has the default rights, **Logon Locally**, **Logon as a Service** and **Logon as a batch job** rights.</span></span> <span data-ttu-id="22f90-164">Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.</span><span class="sxs-lookup"><span data-stu-id="22f90-164">Some organizations have hardening policies that disable those rights.</span></span>

#### <span data-ttu-id="22f90-165">Etapa 2 - Configurar modelos de certificado na autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="22f90-165">Step 2 - Configure certificate templates on the certification authority</span></span>
<a id="step-2---configure-certificate-templates-on-the-certification-authority" class="xliff"></a>
<span data-ttu-id="22f90-166">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="22f90-166">In this task you will:</span></span>
=======
> Devido a um problema conhecido, baixe, instale e configure o conector de certificado usando o procedimento a seguir: [Configurar a infraestrutura de certificado para SCEP -> Configurar a sua infraestrutura -> Tarefa 5](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)


#### Etapa 1 - Criar uma conta de serviço de NDES
<a id="step-1---create-an-ndes-service-account" class="xliff"></a>

Crie uma conta de usuário de domínio para usar como conta de serviço de NDES. Especifique essa conta ao configurar modelos na AC emissora antes de instalar e configurar o NDES. Verifique se o usuário tem os direitos padrão, que são os direitos **Logon Localmente**, **Logon como Serviço** e **Logon como um trabalho em lotes**. Algumas organizações têm políticas de proteção que desabilitam esses direitos de proteção.

#### Etapa 2 - Configurar modelos de certificado na autoridade de certificação
<a id="step-2---configure-certificate-templates-on-the-certification-authority" class="xliff"></a>
Nesta tarefa, você vai:
>>>>>>> live

-   <span data-ttu-id="22f90-167">Configurar um modelo de certificado para o NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-167">Configure a certificate template for NDES</span></span>

-   <span data-ttu-id="22f90-168">Publicar o modelo de certificado para o NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-168">Publish the certificate template for NDES</span></span>

<<<<<<< HEAD
##### <span data-ttu-id="22f90-169">Para configurar a autoridade de certificação</span><span class="sxs-lookup"><span data-stu-id="22f90-169">To configure the certification authority</span></span>
=======
##### Para configurar a autoridade de certificação
>>>>>>> live
<a id="to-configure-the-certification-authority" class="xliff"></a>

1.  <span data-ttu-id="22f90-170">Faça logon como administrador corporativo.</span><span class="sxs-lookup"><span data-stu-id="22f90-170">Log on as an enterprise administrator.</span></span>

2.  <span data-ttu-id="22f90-171">Na AC emissora, use o snap-in de Modelos de Certificado para criar um novo modelo personalizado ou copie um modelo existente (como o modelo de Usuário) e o edite para uso com o NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-171">On the issuing CA, use the Certificate Templates snap-in to create a new custom template or copy an existing template and then edit an existing template (like the User template), for use with NDES.</span></span>

    >[!NOTE]
<<<<<<< HEAD
    > <span data-ttu-id="22f90-172">O modelo de certificado NDES deve ser baseado em um Modelo de Certificado v2 (com a compatibilidade para Windows 2003).</span><span class="sxs-lookup"><span data-stu-id="22f90-172">The NDES certificate template must be based off a v2 Certificate Template (with Windows 2003 compatibility).</span></span>
=======
    > O modelo de certificado NDES deve ser baseado em um Modelo de Certificado v2 (com a compatibilidade para Windows 2003).

    O modelo deve ter as seguintes configurações:
>>>>>>> live

    <span data-ttu-id="22f90-173">O modelo deve ter as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="22f90-173">The template must have the following configurations:</span></span>

    -   <span data-ttu-id="22f90-174">Especifique um **Nome amigável de exibição do modelo** para o modelo.</span><span class="sxs-lookup"><span data-stu-id="22f90-174">Specify a friendly **Template display name** for the template.</span></span>

    -   <span data-ttu-id="22f90-175">Na guia **Nome da Entidade** , selecione **Fornecer na solicitação**.</span><span class="sxs-lookup"><span data-stu-id="22f90-175">On the **Subject Name** tab, select **Supply in the request**.</span></span> <span data-ttu-id="22f90-176">(A segurança é imposta pelo módulo de política do Intune para o NDES).</span><span class="sxs-lookup"><span data-stu-id="22f90-176">(Security is enforced by the Intune policy module for NDES).</span></span>

    -   <span data-ttu-id="22f90-177">Na guia **Extensões** , verifique se a **Descrição das Políticas de Aplicativo** inclui **Autenticação de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="22f90-177">On the **Extensions** tab, ensure the **Description of Application Policies** includes **Client Authentication**.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="22f90-178">Para modelos de certificado do iOS e macOS, na guia **Extensões**, edite **Uso da Chave** e verifique se a opção **A assinatura é uma prova de origem** não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="22f90-178">For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure **Signature is proof of origin** is not selected.</span></span>

    -   <span data-ttu-id="22f90-179">Na guia **Segurança**, adicione a conta de serviço NDES e dê a ela permissões para **Registrar** no modelo.</span><span class="sxs-lookup"><span data-stu-id="22f90-179">On the **Security** tab, add the NDES service account, and give it **Enroll** permissions to the template.</span></span> <span data-ttu-id="22f90-180">Administradores do Intune que criarão perfis SCEP exigem direitos de **leitura** para que possam navegar no modelo durante a criação de perfis SCEP.</span><span class="sxs-lookup"><span data-stu-id="22f90-180">Intune admins who will create SCEP profiles require **Read** rights so that they can browse to the template when creating SCEP profiles.</span></span>

    > [!NOTE]
    > <span data-ttu-id="22f90-181">Para revogar certificados, a conta de serviço do NDES precisa de direitos de *Emitir e Gerenciar Certificados* para cada modelo de certificado usado por um perfil de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-181">To revoke certificates the NDES service account needs *Issue and Manage Certificates* rights for each certificate template used by a certificate profile.</span></span>

3.  <span data-ttu-id="22f90-182">Examine o **Período de validade** na guia **Geral** do modelo.</span><span class="sxs-lookup"><span data-stu-id="22f90-182">Review the **Validity period** on the **General** tab of the template.</span></span> <span data-ttu-id="22f90-183">Por padrão, o Intune usa o valor configurado no modelo.</span><span class="sxs-lookup"><span data-stu-id="22f90-183">By default, Intune uses the value configured in the template.</span></span> <span data-ttu-id="22f90-184">No entanto, você tem a opção de configurar a AC para permitir que o solicitante especifique um valor diferente, que você pode definir de dentro do Console do administrador do Intune.</span><span class="sxs-lookup"><span data-stu-id="22f90-184">However, you have the option to configure the CA to allow the requester to specify a different value, which you can then set from within the Intune Administrator console.</span></span> <span data-ttu-id="22f90-185">Se você quiser usar sempre o valor no modelo, ignore o restante desta etapa.</span><span class="sxs-lookup"><span data-stu-id="22f90-185">If you want to always use the value in the template, skip the remainder of this step.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="22f90-186">O iOS e o macOS sempre usam o valor definido no modelo, independentemente de outras configurações que você fizer.</span><span class="sxs-lookup"><span data-stu-id="22f90-186">iOS and macOS always use the value set in the template regardless of other configurations you make.</span></span>

<span data-ttu-id="22f90-187">Aqui estão as capturas de tela de um exemplo de configuração de modelo.</span><span class="sxs-lookup"><span data-stu-id="22f90-187">Here are screenshots of an example template configuration.</span></span>

![Modelo, guia de tratamento de solicitação](.\media\scep_ndes_request_handling.png)

![Modelo, guia de nome da entidade](.\media\scep_ndes_subject_name.jpg)

![Modelo, guia de segurança](.\media\scep_ndes_security.jpg)

![Modelo, guia de extensões](.\media\scep_ndes_extensions.jpg)

![Modelo, guia de requisitos de emissão](.\media\scep_ndes_issuance_reqs.jpg)

>   [!IMPORTANT]
    > <span data-ttu-id="22f90-193">Para Políticas de Aplicativo, adicione somente as políticas de aplicativo necessárias.</span><span class="sxs-lookup"><span data-stu-id="22f90-193">For Application Policies, only add the application policies required.</span></span> <span data-ttu-id="22f90-194">Confirme suas escolhas com seus administradores de segurança.</span><span class="sxs-lookup"><span data-stu-id="22f90-194">Confirm your choices with your security admins.</span></span>



<span data-ttu-id="22f90-195">Para configurar a AC para permitir que o solicitante especifique o período de validade:</span><span class="sxs-lookup"><span data-stu-id="22f90-195">To configure the CA to allow the requester to specify the validity period:</span></span>

1. <span data-ttu-id="22f90-196">Na AC, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="22f90-196">On the CA run the following commands:</span></span>
    - <span data-ttu-id="22f90-197">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span><span class="sxs-lookup"><span data-stu-id="22f90-197">**certutil -setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE**</span></span>
    - <span data-ttu-id="22f90-198">**net stop certsvc**</span><span class="sxs-lookup"><span data-stu-id="22f90-198">**net stop certsvc**</span></span>
    - <span data-ttu-id="22f90-199">**net start certsvc**</span><span class="sxs-lookup"><span data-stu-id="22f90-199">**net start certsvc**</span></span>
2. <span data-ttu-id="22f90-200">Na AC emissora, use o snap-in da Autoridade de Certificação para publicar o modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-200">On the issuing CA, use the Certification Authority snap-in to publish the certificate template.</span></span>
    <span data-ttu-id="22f90-201">Selecione o nó **Modelos de Certificado**, clique em **Ação**-&gt; **Novo** &gt; **Modelo de Certificado a Ser Emitido** e selecione o modelo que você criou na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="22f90-201">Select the **Certificate Templates** node, click **Action**-&gt; **New** &gt; **Certificate Template to Issue**, and then select the template you created in step 2.</span></span>
3. <span data-ttu-id="22f90-202">Valide a publicação do modelo exibindo-o na pasta **Modelos de Certificado** .</span><span class="sxs-lookup"><span data-stu-id="22f90-202">Validate that the template published by viewing it under the **Certificate Templates** folder.</span></span>


<<<<<<< HEAD
#### <span data-ttu-id="22f90-203">Etapa 3 - Configurar pré-requisitos no servidor NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-203">Step 3 - Configure prerequisites on the NDES server</span></span>
<a id="step-3---configure-prerequisites-on-the-ndes-server" class="xliff"></a>
<span data-ttu-id="22f90-204">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="22f90-204">In this task you will:</span></span>
=======
#### Etapa 3 - Configurar pré-requisitos no servidor NDES
<a id="step-3---configure-prerequisites-on-the-ndes-server" class="xliff"></a>
Nesta tarefa, você vai:
>>>>>>> live

-   <span data-ttu-id="22f90-205">Adicionar o NDES a um Windows Server e configurar o IIS para dar suporte ao NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-205">Add NDES to a Windows Server and configure IIS to support NDES</span></span>

-   <span data-ttu-id="22f90-206">Adicionar a conta de serviço de NDES ao grupo IIS_IUSR</span><span class="sxs-lookup"><span data-stu-id="22f90-206">Add the NDES Service account to the IIS_IUSR group</span></span>

-   <span data-ttu-id="22f90-207">Definir o SPN da conta de serviço de NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-207">Set the SPN for the NDES Service account</span></span>




   1.  <span data-ttu-id="22f90-208">No servidor que hospeda o NDES, você deve fazer logon como **Administrador Corporativo**e usar o [Assistente de Adição de Funções e Recursos](https://technet.microsoft.com/library/hh831809.aspx) para instalar o NDES:</span><span class="sxs-lookup"><span data-stu-id="22f90-208">On the server that will hosts NDES, you must log on as a an **Enterprise Administrator**, and then use the [Add Roles and Features Wizard](https://technet.microsoft.com/library/hh831809.aspx) to install NDES:</span></span>

    1.  <span data-ttu-id="22f90-209">No assistente, selecione **Serviços de Certificados do Active Directory** para acessar os Serviços de Função do AD CS.</span><span class="sxs-lookup"><span data-stu-id="22f90-209">In the Wizard, select **Active Directory Certificate Services** to gain access to the AD CS Role Services.</span></span> <span data-ttu-id="22f90-210">Selecione o **Serviço de Registro de Dispositivo de Rede**, desmarque **Autoridade de Certificação**e conclua o assistente.</span><span class="sxs-lookup"><span data-stu-id="22f90-210">Select the **Network Device Enrollment Service**, uncheck **Certification Authority**, and then complete the wizard.</span></span>

        > [!TIP]
        > <span data-ttu-id="22f90-211">Na página **Progresso da Instalação** do assistente, não clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="22f90-211">On the **Installation progress** page of the wizard, do not click **Close**.</span></span> <span data-ttu-id="22f90-212">Em vez disso, clique no link para **Configurar os Serviços de Certificados do Active Directory no servidor de destino**.</span><span class="sxs-lookup"><span data-stu-id="22f90-212">Instead, click the link for **Configure Active Directory Certificate Services on the destination server**.</span></span> <span data-ttu-id="22f90-213">Isso abre o assistente de **Configuração AD CS** que você usa para a próxima tarefa.</span><span class="sxs-lookup"><span data-stu-id="22f90-213">This opens the **AD CS Configuration** wizard that you use for the next task.</span></span> <span data-ttu-id="22f90-214">Após Configuração AD CS abrir, você pode fechar o Assistente de Adição de Funções e Recursos.</span><span class="sxs-lookup"><span data-stu-id="22f90-214">After AD CS Configuration opens, you can close the Add Roles and Features wizard.</span></span>

    2.  <span data-ttu-id="22f90-215">Quando o NDES é adicionado ao servidor, o assistente também instala o IIS.</span><span class="sxs-lookup"><span data-stu-id="22f90-215">When NDES is added to the server, the wizard also installs IIS.</span></span> <span data-ttu-id="22f90-216">Verifique se o IIS tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="22f90-216">Ensure IIS has the following configurations:</span></span>

        -   <span data-ttu-id="22f90-217">**Servidor Web** &gt; **Segurança** &gt; **Filtragem de Solicitações**</span><span class="sxs-lookup"><span data-stu-id="22f90-217">**Web Server** &gt; **Security** &gt; **Request Filtering**</span></span>

        -   <span data-ttu-id="22f90-218">**Servidor Web** &gt; **Desenvolvimento de Aplicativos** &gt; **ASP.NET 3.5**.</span><span class="sxs-lookup"><span data-stu-id="22f90-218">**Web Server** &gt; **Application Development** &gt; **ASP.NET 3.5**.</span></span> <span data-ttu-id="22f90-219">Instalar o ASP.NET 3.5 instalará o .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="22f90-219">Installing ASP.NET 3.5 will install .NET Framework 3.5.</span></span> <span data-ttu-id="22f90-220">Ao instalar o .NET Framework 3.5, instale o recurso **.NET Framework 3.5** principal e o **Ativação HTTP**.</span><span class="sxs-lookup"><span data-stu-id="22f90-220">When installing .NET Framework 3.5, install both the core **.NET Framework 3.5** feature and **HTTP Activation**.</span></span>

        -   <span data-ttu-id="22f90-221">**Servidor Web** &gt; **Desenvolvimento de Aplicativos** &gt; **ASP.NET 4.5**.</span><span class="sxs-lookup"><span data-stu-id="22f90-221">**Web Server** &gt; **Application Development** &gt; **ASP.NET 4.5**.</span></span> <span data-ttu-id="22f90-222">Instalar o ASP.NET 4,5 instalará o .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="22f90-222">Installing ASP.NET 4.5 will install .NET Framework 4.5.</span></span> <span data-ttu-id="22f90-223">Ao instalar o .NET Framework 4.5, instale o recurso principal do **.NET Framework 4.5**, o **ASP.NET 4.5** e o recurso **Serviços WCF** &gt; **Ativação HTTP**.</span><span class="sxs-lookup"><span data-stu-id="22f90-223">When installing .NET Framework 4.5, install the core **.NET Framework 4.5** feature, **ASP.NET 4.5**, and the **WCF Services** &gt; **HTTP Activation** feature.</span></span>

        -   <span data-ttu-id="22f90-224">**Ferramentas de gerenciamento** &gt; **Compatibilidade de gerenciamento do IIS 6** &gt; **Compatibilidade de metabase do IIS 6**</span><span class="sxs-lookup"><span data-stu-id="22f90-224">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 Metabase Compatibility**</span></span>

        -   <span data-ttu-id="22f90-225">**Ferramentas de gerenciamento** &gt; **Compatibilidade de gerenciamento do IIS 6** &gt; **Compatibilidade de WMI do IIS 6**</span><span class="sxs-lookup"><span data-stu-id="22f90-225">**Management Tools** &gt; **IIS 6 Management Compatibility** &gt; **IIS 6 WMI Compatibility**</span></span>

  2.  <span data-ttu-id="22f90-226">No servidor, adicione a conta de serviço de NDES como membro do grupo **IIS_IUSR**.</span><span class="sxs-lookup"><span data-stu-id="22f90-226">On the server, add the NDES service account as a member of the **IIS_IUSR** group.</span></span>

   3.  <span data-ttu-id="22f90-227">Em um prompt de comandos com privilégios elevados, execute o seguinte comando para definir o SPN da conta de serviço de NDES:</span><span class="sxs-lookup"><span data-stu-id="22f90-227">In an elevated command prompt, run the following command to set the SPN of the NDES Service account:</span></span>

`**setspn -s http/&lt;DNS name of NDES Server&gt; &lt;Domain name&gt;\&lt;NDES Service account name&gt;**`

   <span data-ttu-id="22f90-228">Por exemplo, se seu servidor de NDES se chamar **Server01**, seu domínio for **Contoso.com**e a conta de serviço for **NDESService**, use:</span><span class="sxs-lookup"><span data-stu-id="22f90-228">For example, if your NDES Server is named **Server01**, your domain is **Contoso.com**, and the service account is **NDESService**, use:</span></span>

`**setspn –s http/Server01.contoso.com contoso\NDESService**`

<<<<<<< HEAD
#### <span data-ttu-id="22f90-229">Etapa 4 - Configurar o NDES para uso com o Intune</span><span class="sxs-lookup"><span data-stu-id="22f90-229">Step 4 - Configure NDES for use with Intune</span></span>
<a id="step-4---configure-ndes-for-use-with-intune" class="xliff"></a>
<span data-ttu-id="22f90-230">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="22f90-230">In this task you will:</span></span>
=======
#### Etapa 4 - Configurar o NDES para uso com o Intune
<a id="step-4---configure-ndes-for-use-with-intune" class="xliff"></a>
Nesta tarefa, você vai:
>>>>>>> live

-   <span data-ttu-id="22f90-231">Configurar o NDES para uso com a AC emissora</span><span class="sxs-lookup"><span data-stu-id="22f90-231">Configure NDES for use with the issuing CA</span></span>

-   <span data-ttu-id="22f90-232">Associar o certificado de autenticação do servidor (SSL) no IIS</span><span class="sxs-lookup"><span data-stu-id="22f90-232">Bind the server authentication (SSL) certificate in IIS</span></span>

-   <span data-ttu-id="22f90-233">Configurar a filtragem de solicitações no IIS</span><span class="sxs-lookup"><span data-stu-id="22f90-233">Configure Request Filtering in IIS</span></span>


1.  <span data-ttu-id="22f90-234">No servidor de NDES, abra o Assistente de Configuração do AD CS e faça as seguintes configurações.</span><span class="sxs-lookup"><span data-stu-id="22f90-234">On the NDES Server, open the AD CS Configuration wizard and then make the following configurations.</span></span>

    > [!TIP]
    > <span data-ttu-id="22f90-235">Se você clicou no link na tarefa anterior, o assistente já está aberto.</span><span class="sxs-lookup"><span data-stu-id="22f90-235">If you clicked the link in the previous task, this wizard is already open.</span></span> <span data-ttu-id="22f90-236">Caso contrário, abra o Gerenciador do Servidor para acessar a configuração pós-implantação dos Serviços de Certificados do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22f90-236">Otherwise, open Server Manager to access the post-deployment configuration for Active Directory Certificate Services.</span></span>

    -   <span data-ttu-id="22f90-237">Na página **Serviços de Função** , selecione **Serviço de Registro de Dispositivo de Rede**.</span><span class="sxs-lookup"><span data-stu-id="22f90-237">On the **Role Services** Page, select the **Network Device Enrollment Service**.</span></span>

    -   <span data-ttu-id="22f90-238">Na página **Conta de Serviço para NDES** , especifique a Conta de Serviço de NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-238">On the **Service Account for NDES** page, specify the NDES Service Account.</span></span>

    -   <span data-ttu-id="22f90-239">Na página **AC para NDES** , clique em **Selecionar**e selecione a AC emissora em que você configurou o modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-239">On the **CA for NDES** page, click **Select**, and then select the issuing CA where you configured the certificate template.</span></span>

    -   <span data-ttu-id="22f90-240">Na página **Criptografia para NDES** , defina o comprimento de chave para atender aos requisitos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="22f90-240">On the **Cryptography for NDES** page, set the key length to meet your company requirements.</span></span>

    <span data-ttu-id="22f90-241">Na página **Confirmação** , clique em **Configurar** para concluir o assistente.</span><span class="sxs-lookup"><span data-stu-id="22f90-241">On the **Confirmation** page, click **Configure** to complete the wizard.</span></span>

2.  <span data-ttu-id="22f90-242">Após concluir o assistente, edite a seguinte chave do Registro no Servidor de NDES:</span><span class="sxs-lookup"><span data-stu-id="22f90-242">After the wizard completes, edit the following registry key on the NDES Server:</span></span>

    -   <span data-ttu-id="22f90-243">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span><span class="sxs-lookup"><span data-stu-id="22f90-243">**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Cryptography\MSCEP\**</span></span>

    <span data-ttu-id="22f90-244">Para editar essa chave, identifique a **Finalidade** do modelo de certificado, conforme encontrada na guia **Tratamento de Solicitação**, e edite a entrada correspondente no Registro substituindo os dados existentes pelo nome do modelo de certificado (não o nome de exibição do modelo) que você especificou na Tarefa 1.</span><span class="sxs-lookup"><span data-stu-id="22f90-244">To edit this key, identify the certificate template's **Purpose**, as found on its **Request Handling** tab, and then edit the corresponding entry in the registry by replacing the existing data with the name of the certificate template (not the display name of the template) that you specified in Task 1.</span></span> <span data-ttu-id="22f90-245">A tabela a seguir mapeia a finalidade do modelo de certificado de acordo com os valores do Registro:</span><span class="sxs-lookup"><span data-stu-id="22f90-245">The following table maps the certificate template purpose to the values in the registry:</span></span>

    |<span data-ttu-id="22f90-246">Finalidade do modelo de certificado (na guia Tratamento de Solicitação)</span><span class="sxs-lookup"><span data-stu-id="22f90-246">Certificate template Purpose (On the Request Handling tab)</span></span>|<span data-ttu-id="22f90-247">Valor de registro a ser editado</span><span class="sxs-lookup"><span data-stu-id="22f90-247">Registry value to edit</span></span>|<span data-ttu-id="22f90-248">O valor mostrado no console de administração do Intune para o perfil do protocolo SCEP</span><span class="sxs-lookup"><span data-stu-id="22f90-248">Value seen in the Intune admin console for the SCEP profile</span></span>|
    |--------------------------------------------------------------|--------------------------|------------------------------------------------------------------------------------------------------------|
    |<span data-ttu-id="22f90-249">Assinatura</span><span class="sxs-lookup"><span data-stu-id="22f90-249">Signature</span></span>|<span data-ttu-id="22f90-250">SignatureTemplate</span><span class="sxs-lookup"><span data-stu-id="22f90-250">SignatureTemplate</span></span>|<span data-ttu-id="22f90-251">Assinatura digital</span><span class="sxs-lookup"><span data-stu-id="22f90-251">Digital Signature</span></span>|
    |<span data-ttu-id="22f90-252">Criptografia</span><span class="sxs-lookup"><span data-stu-id="22f90-252">Encryption</span></span>|<span data-ttu-id="22f90-253">EncryptionTemplate</span><span class="sxs-lookup"><span data-stu-id="22f90-253">EncryptionTemplate</span></span>|<span data-ttu-id="22f90-254">Codificação de chave</span><span class="sxs-lookup"><span data-stu-id="22f90-254">Key Encipherment</span></span>|
    |<span data-ttu-id="22f90-255">Assinatura e criptografia</span><span class="sxs-lookup"><span data-stu-id="22f90-255">Signature and encryption</span></span>|<span data-ttu-id="22f90-256">GeneralPurposeTemplate</span><span class="sxs-lookup"><span data-stu-id="22f90-256">GeneralPurposeTemplate</span></span>|<span data-ttu-id="22f90-257">Codificação de chave</span><span class="sxs-lookup"><span data-stu-id="22f90-257">Key Encipherment</span></span><br /><br /><span data-ttu-id="22f90-258">Assinatura digital</span><span class="sxs-lookup"><span data-stu-id="22f90-258">Digital Signature</span></span>|
    <span data-ttu-id="22f90-259">Por exemplo, se a Finalidade do seu modelo de certificado for **Criptografia**, edite o valor de **EncryptionTemplate** como o nome do seu modelo de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-259">For example, if the Purpose of your certificate template is **Encryption**, then edit the **EncryptionTemplate** value to be the name of your certificate template.</span></span>

3. <span data-ttu-id="22f90-260">O servidor NDES receberá URLs muito longas (consultas), o que exige que você adicione duas entradas de Registro:</span><span class="sxs-lookup"><span data-stu-id="22f90-260">The NDES server will receive very long URL’s (queries), which require that you add two registry entries:</span></span>

    |<span data-ttu-id="22f90-261">Local</span><span class="sxs-lookup"><span data-stu-id="22f90-261">Location</span></span>|<span data-ttu-id="22f90-262">Valor</span><span class="sxs-lookup"><span data-stu-id="22f90-262">Value</span></span>|<span data-ttu-id="22f90-263">Tipo</span><span class="sxs-lookup"><span data-stu-id="22f90-263">Type</span></span>|<span data-ttu-id="22f90-264">Dados</span><span class="sxs-lookup"><span data-stu-id="22f90-264">Data</span></span>|
    |-------|-----|----|----|
    |<span data-ttu-id="22f90-265">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="22f90-265">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="22f90-266">MaxFieldLength</span><span class="sxs-lookup"><span data-stu-id="22f90-266">MaxFieldLength</span></span>|<span data-ttu-id="22f90-267">DWORD</span><span class="sxs-lookup"><span data-stu-id="22f90-267">DWORD</span></span>|<span data-ttu-id="22f90-268">65534 (decimal)</span><span class="sxs-lookup"><span data-stu-id="22f90-268">65534 (decimal)</span></span>|
    |<span data-ttu-id="22f90-269">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span><span class="sxs-lookup"><span data-stu-id="22f90-269">HKLM\SYSTEM\CurrentControlSet\Services\HTTP\Parameters</span></span>|<span data-ttu-id="22f90-270">MaxRequestBytes</span><span class="sxs-lookup"><span data-stu-id="22f90-270">MaxRequestBytes</span></span>|<span data-ttu-id="22f90-271">DWORD</span><span class="sxs-lookup"><span data-stu-id="22f90-271">DWORD</span></span>|<span data-ttu-id="22f90-272">65534 (decimal)</span><span class="sxs-lookup"><span data-stu-id="22f90-272">65534 (decimal)</span></span>|


4. <span data-ttu-id="22f90-273">No Gerenciador do IIS, escolha **Site Padrão** -> **Filtragem de Solicitações** -> **Editar Configuração do Recurso** e altere o **Comprimento máximo da URL** e **Cadeia de caracteres de consulta máxima** para *65534*, conforme mostrado.</span><span class="sxs-lookup"><span data-stu-id="22f90-273">In IIS manager, choose **Default Web Site** -> **Request Filtering** -> **Edit Feature Setting**, and change the **Maximum URL length** and **Maximum query string** to *65534*, as shown.</span></span>

    ![Comprimento máximo de URL e consulta do IIS](.\media\SCEP_IIS_max_URL.png)

5.  <span data-ttu-id="22f90-275">Reinicie o servidor.</span><span class="sxs-lookup"><span data-stu-id="22f90-275">Restart the server.</span></span> <span data-ttu-id="22f90-276">Executar **iisreset** no servidor não será suficiente para finalizar as alterações.</span><span class="sxs-lookup"><span data-stu-id="22f90-276">Running **iisreset** on the server will not be sufficient to finalize these changes.</span></span>
6. <span data-ttu-id="22f90-277">Navegue até http://*FQDN*/certsrv/mscep/mscep.dll.</span><span class="sxs-lookup"><span data-stu-id="22f90-277">Browse to http://*FQDN*/certsrv/mscep/mscep.dll.</span></span> <span data-ttu-id="22f90-278">Você deve ver uma página NDES semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="22f90-278">You should see an NDES page similar to this:</span></span>

    ![Testar NDES](.\media\SCEP_NDES_URL.png)

<<<<<<< HEAD
    <span data-ttu-id="22f90-280">Se você receber a mensagem **503 Serviço indisponível**, verifique o visualizador de eventos.</span><span class="sxs-lookup"><span data-stu-id="22f90-280">If you get a **503 Service unavailable**, check the event viewer.</span></span> <span data-ttu-id="22f90-281">É provável que o pool de aplicativos seja interrompido devido a um direito ausente para o usuário NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-281">It's likely that the application pool is stopped due to a missing right for the NDES user.</span></span> <span data-ttu-id="22f90-282">Esses direitos são descritos na Tarefa 1.</span><span class="sxs-lookup"><span data-stu-id="22f90-282">Those rights are described in Task 1.</span></span>

##### <span data-ttu-id="22f90-283">Para instalar e associar os certificados no Servidor de NDES</span><span class="sxs-lookup"><span data-stu-id="22f90-283">To Install and bind certificates on the NDES Server</span></span>
=======
    Se você receber a mensagem **503 Serviço indisponível**, verifique o visualizador de eventos. É provável que o pool de aplicativos seja interrompido devido a um direito ausente para o usuário NDES. Esses direitos são descritos na Tarefa 1.

##### Para instalar e associar os certificados no Servidor de NDES
>>>>>>> live
<a id="to-install-and-bind-certificates-on-the-ndes-server" class="xliff"></a>

1.  <span data-ttu-id="22f90-284">No seu Servidor de NDES, solicite e instale um certificado de **autenticação de servidor** por meio da sua AC interna ou pública.</span><span class="sxs-lookup"><span data-stu-id="22f90-284">On your NDES Server, request and install a **server authentication** certificate from your internal CA or public CA.</span></span> <span data-ttu-id="22f90-285">Em seguida, você associará esse certificado SSL no IIS.</span><span class="sxs-lookup"><span data-stu-id="22f90-285">You will then bind this SSL certificate in IIS.</span></span>

    > [!TIP]
    > <span data-ttu-id="22f90-286">Depois de associar o certificado SSL no IIS, você também instalará um certificado de autenticação de cliente.</span><span class="sxs-lookup"><span data-stu-id="22f90-286">After you bind the SSL certificate in IIS, you will also install a client authentication certificate.</span></span> <span data-ttu-id="22f90-287">Esse certificado pode ser emitido por qualquer AC em que o Servidor de NDES confie.</span><span class="sxs-lookup"><span data-stu-id="22f90-287">This certificate can be issued by any CA that is trusted by the NDES Server.</span></span> <span data-ttu-id="22f90-288">Embora não seja uma prática recomendada, você pode usar o mesmo certificado para autenticação de servidor e cliente, desde que o certificado tenha os dois EKUs (Usos Avançados de Chave).</span><span class="sxs-lookup"><span data-stu-id="22f90-288">Although it is not a best practice, you can use the same certificate for both server and client authentication as long as the certificate has both Enhance Key Usages (EKU’s).</span></span> <span data-ttu-id="22f90-289">Examine as etapas a seguir para obter informações sobre esses certificados de autenticação.</span><span class="sxs-lookup"><span data-stu-id="22f90-289">Review the following steps for information about these authentication certificates.</span></span>

    1.  <span data-ttu-id="22f90-290">Depois de obter o certificado de autenticação de servidor, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e clique em **Ligações** no painel **Ações** .</span><span class="sxs-lookup"><span data-stu-id="22f90-290">After you obtain the server authentication certificate, open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then click **Bindings** in the **Actions** pane.</span></span>

    2.  <span data-ttu-id="22f90-291">Clique em **Adicionar**, defina o **Tipo** como **https**e verifique se a porta é **443**.</span><span class="sxs-lookup"><span data-stu-id="22f90-291">Click **Add**, set **Type** to **https**, and then ensure the port is **443**.</span></span> <span data-ttu-id="22f90-292">(Somente a porta 443 tem suporte para o Intune autônomo).</span><span class="sxs-lookup"><span data-stu-id="22f90-292">(Only port 443 is supported for standalone Intune.</span></span>

    3.  <span data-ttu-id="22f90-293">Para **Certificado SSL**, especifique o certificado de autenticação de servidor.</span><span class="sxs-lookup"><span data-stu-id="22f90-293">For **SSL certificate**, specify the server authentication certificate.</span></span>

        > [!NOTE]
        > <span data-ttu-id="22f90-294">Se o servidor de NDES usar um nome interno e externo para um único endereço de rede, o certificado de autenticação de servidor deverá ter um **Nome da Entidade** com um nome de servidor público externo e um **Nome Alternativo da Entidade** que inclua o nome do servidor interno.</span><span class="sxs-lookup"><span data-stu-id="22f90-294">If the NDES server uses both an external and internal name for a single network address, the server authentication certificate must have a **Subject Name** with an external public server name, and a **Subject Alternative Name** that includes the internal server name.</span></span>

2.  <span data-ttu-id="22f90-295">No seu Servidor de NDES, solicite e instale um certificado de **autenticação de cliente** da sua AC interna ou uma AC pública.</span><span class="sxs-lookup"><span data-stu-id="22f90-295">On your NDES Server, request and install a **client authentication** certificate from your internal CA, or a public certificate authority.</span></span> <span data-ttu-id="22f90-296">Pode ser o mesmo certificado que o certificado de autenticação de servidor se o certificado tiver os dois recursos.</span><span class="sxs-lookup"><span data-stu-id="22f90-296">This can be the same certificate as the server authentication certificate if that certificate has both capabilities.</span></span>

    <span data-ttu-id="22f90-297">O certificado de autenticação de cliente deve ter as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="22f90-297">The client authentication certificate must have the following properties:</span></span>

    <span data-ttu-id="22f90-298">**Uso Avançado de Chave** - Isso deve incluir a **Autenticação de Cliente**.</span><span class="sxs-lookup"><span data-stu-id="22f90-298">**Enhanced Key Usage** - This must include **Client Authentication**.</span></span>

    <span data-ttu-id="22f90-299">**Nome da Entidade**: deve ser igual ao nome DNS do servidor em que você está instalando o certificado (o Servidor de NDES).</span><span class="sxs-lookup"><span data-stu-id="22f90-299">**Subject Name** - This must be equal to the DNS name of the server where you are installing the certificate (the NDES Server).</span></span>

<<<<<<< HEAD
##### <span data-ttu-id="22f90-300">Para configurar a filtragem de solicitações do IIS</span><span class="sxs-lookup"><span data-stu-id="22f90-300">To configure IIS request filtering</span></span>
=======
##### Para configurar a filtragem de solicitações do IIS
>>>>>>> live
<a id="to-configure-iis-request-filtering" class="xliff"></a>

1.  <span data-ttu-id="22f90-301">No Servidor de NDES, abra o **Gerenciador do IIS**, selecione o **Site Padrão** no painel **Conexões** e abra a **Filtragem de Solicitações**.</span><span class="sxs-lookup"><span data-stu-id="22f90-301">On the NDES Server open **IIS Manager**, select the **Default Web Site** in the **Connections** pane, and then open **Request Filtering**.</span></span>

2.  <span data-ttu-id="22f90-302">Clique em **Editar Configurações de Recurso**e defina o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22f90-302">Click **Edit Feature Settings**, and then set the following:</span></span>

    <span data-ttu-id="22f90-303">**cadeia de caracteres de consulta (Bytes)** = **65534**</span><span class="sxs-lookup"><span data-stu-id="22f90-303">**query string (Bytes)** = **65534**</span></span>

    <span data-ttu-id="22f90-304">**Tamanho máximo da URL (Bytes)** = **65534**</span><span class="sxs-lookup"><span data-stu-id="22f90-304">**Maximum URL length (Bytes)** = **65534**</span></span>

3.  <span data-ttu-id="22f90-305">Examine a seguinte chave do Registro:</span><span class="sxs-lookup"><span data-stu-id="22f90-305">Review the following registry key:</span></span>

    <span data-ttu-id="22f90-306">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span><span class="sxs-lookup"><span data-stu-id="22f90-306">**HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\HTTP\Parameters**</span></span>

    <span data-ttu-id="22f90-307">Certifique-se de que os seguintes valores sejam definidos como entradas DWORD:</span><span class="sxs-lookup"><span data-stu-id="22f90-307">Ensure the following values are set as DWORD entries:</span></span>

    <span data-ttu-id="22f90-308">Nome: **MaxFieldLength**, com um valor decimal de **65534**</span><span class="sxs-lookup"><span data-stu-id="22f90-308">Name: **MaxFieldLength**, with a decimal value of **65534**</span></span>

    <span data-ttu-id="22f90-309">Nome: **MaxRequestBytes**, com um valor decimal de **65534**</span><span class="sxs-lookup"><span data-stu-id="22f90-309">Name: **MaxRequestBytes**, with a decimal value of **65534**</span></span>

4.  <span data-ttu-id="22f90-310">Reinicialize o servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-310">Reboot the NDES server.</span></span> <span data-ttu-id="22f90-311">Agora, o servidor está pronto para dar suporte ao Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-311">The server is now ready to support the Certificate Connector.</span></span>

<<<<<<< HEAD
#### <span data-ttu-id="22f90-312">Etapa 5 - Habilitar, instalar e configurar o Conector de Certificado do Intune</span><span class="sxs-lookup"><span data-stu-id="22f90-312">Step 5 - Enable, install, and configure the Intune certificate connector</span></span>
<a id="step-5---enable-install-and-configure-the-intune-certificate-connector" class="xliff"></a>
<span data-ttu-id="22f90-313">Nesta tarefa, você vai:</span><span class="sxs-lookup"><span data-stu-id="22f90-313">In this task you will:</span></span>
=======
#### Etapa 5 - Habilitar, instalar e configurar o Conector de Certificado do Intune
<a id="step-5---enable-install-and-configure-the-intune-certificate-connector" class="xliff"></a>
Nesta tarefa, você vai:
>>>>>>> live

<span data-ttu-id="22f90-314">Habilitar o suporte para NDES no Intune.</span><span class="sxs-lookup"><span data-stu-id="22f90-314">Enable support for NDES in Intune.</span></span>

<span data-ttu-id="22f90-315">Baixar, instalar e configurar o Conector de Certificado no Servidor NDES.</span><span class="sxs-lookup"><span data-stu-id="22f90-315">Download, install, and configure the Certificate Connector on the NDES Server.</span></span>

<<<<<<< HEAD
##### <span data-ttu-id="22f90-316">Para habilitar o suporte ao Conector de Certificado</span><span class="sxs-lookup"><span data-stu-id="22f90-316">To enable support for the certificate connector</span></span>
<a id="to-enable-support-for-the-certificate-connector" class="xliff"></a>

1. <span data-ttu-id="22f90-317">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="22f90-317">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="22f90-318">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="22f90-318">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="22f90-319">Na folha **Intune**, escolha **Configurar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="22f90-319">On the **Intune** blade, choose **Configure devices**.</span></span>
4. <span data-ttu-id="22f90-320">Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="22f90-320">On the **Device Configuration** blade, choose **Certification Authority**.</span></span>
5.  <span data-ttu-id="22f90-321">Selecione **Habilitar Certificate Connector**.</span><span class="sxs-lookup"><span data-stu-id="22f90-321">Select **Enable Certificate Connector**.</span></span>

##### <span data-ttu-id="22f90-322">Para baixar, instalar e configurar o Conector de Certificado</span><span class="sxs-lookup"><span data-stu-id="22f90-322">To download, install and configure the certificate connector</span></span>
<a id="to-download-install-and-configure-the-certificate-connector" class="xliff"></a>

> [!NOTE]
> <span data-ttu-id="22f90-323">Devido a um problema conhecido, baixe, instale e configure o conector de certificado usando o procedimento a seguir: [Configurar a infraestrutura de certificado para SCEP -> Configurar a sua infraestrutura -> Tarefa 5](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)</span><span class="sxs-lookup"><span data-stu-id="22f90-323">Because of a known issue, download, install, and configure the certificate connector using the following procedure: [Configure certificate infrastructure for SCEP -> Configure your infrastructure -> Task 5](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)</span></span>

1. <span data-ttu-id="22f90-324">Entre no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="22f90-324">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="22f90-325">Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.</span><span class="sxs-lookup"><span data-stu-id="22f90-325">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="22f90-326">Na folha **Intune**, escolha **Configurar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="22f90-326">On the **Intune** blade, choose **Configure devices**.</span></span>
4. <span data-ttu-id="22f90-327">Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="22f90-327">On the **Device Configuration** blade, choose **Certification Authority**.</span></span>
5. <span data-ttu-id="22f90-328">Escolha **Baixar Certificate Connector**.</span><span class="sxs-lookup"><span data-stu-id="22f90-328">Choose **Download Certificate Connector**.</span></span>
6.  <span data-ttu-id="22f90-329">Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**) em um servidor Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="22f90-329">After the download completes, run the downloaded installer (**ndesconnectorssetup.exe**) on a Windows Server 2012 R2 server.</span></span> <span data-ttu-id="22f90-330">O instalador também instala o módulo de política para NDES e o Serviço Web de CRP.</span><span class="sxs-lookup"><span data-stu-id="22f90-330">The installer also installs the policy module for NDES and the CRP Web Service.</span></span> <span data-ttu-id="22f90-331">(O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).</span><span class="sxs-lookup"><span data-stu-id="22f90-331">(The CRP Web Service, CertificateRegistrationSvc, runs as an application in IIS.)</span></span>
=======
##### Para habilitar o suporte ao Conector de Certificado
<a id="to-enable-support-for-the-certificate-connector" class="xliff"></a>

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**.
5.  Selecione **Habilitar Certificate Connector**.

##### Para baixar, instalar e configurar o Conector de Certificado
<a id="to-download-install-and-configure-the-certificate-connector" class="xliff"></a>

> [!NOTE]
> Devido a um problema conhecido, baixe, instale e configure o conector de certificado usando o procedimento a seguir: [Configurar a infraestrutura de certificado para SCEP -> Configurar a sua infraestrutura -> Tarefa 5](/intune-classic/deploy-use/configure-certificate-infrastructure-for-scep)

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Configurar dispositivos**.
4. Na folha **Configurações do Dispositivo**, escolha **Autoridade de Certificação**.
5. Escolha **Baixar Certificate Connector**.
6.  Após a conclusão do download, execute o instalador baixado (**ndesconnectorssetup.exe**) em um servidor Windows Server 2012 R2. O instalador também instala o módulo de política para NDES e o Serviço Web de CRP. (O Serviço Web de CRP, CertificateRegistrationSvc, é executado como um aplicativo no IIS).
>>>>>>> live

    > [!NOTE]
    > <span data-ttu-id="22f90-332">Quando você instala o NDES para o Intune autônomo, o serviço de CRP é instalado automaticamente com o Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-332">When you install NDES for standalone Intune, the CRP service automatically installs with the Certificate Connector.</span></span> <span data-ttu-id="22f90-333">Quando você usa o Intune com o Configuration Manager, instala o Ponto de Registro de Certificado como uma função de sistema de site separada.</span><span class="sxs-lookup"><span data-stu-id="22f90-333">When you use Intune with Configuration Manager, you install the Certificate Registration Point as a separate site system role.</span></span>

3.  <span data-ttu-id="22f90-334">Quando for solicitado o certificado de cliente do Certificate Connector, escolha **Selecionar** e selecione o certificado de **autenticação de cliente** instalado no Servidor NDES na Tarefa 3.</span><span class="sxs-lookup"><span data-stu-id="22f90-334">When prompted for the client certificate for the Certificate Connector, choose **Select**, and select the **client authentication** certificate you installed on your NDES Server in Task 3.</span></span>

    <span data-ttu-id="22f90-335">Depois de selecionar o certificado de autenticação de cliente, você retornará para a superfície do **Certificado de Cliente para o Conector de Certificado do Microsoft Intune** .</span><span class="sxs-lookup"><span data-stu-id="22f90-335">After you select the client authentication certificate, you are returned to the **Client Certificate for Microsoft Intune Certificate Connector** surface.</span></span> <span data-ttu-id="22f90-336">Embora o certificado selecionado não seja exibido, clique em **Avançar** para ver as propriedades do certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-336">Although the certificate you selected is not shown, click **Next** to view the properties of that certificate.</span></span> <span data-ttu-id="22f90-337">Em seguida, clique em **Avançar**e clique em **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="22f90-337">Then click **Next**, and then click **Install**.</span></span>

4.  <span data-ttu-id="22f90-338">Após a conclusão do assistente, mas antes de fechá-lo, clique em **Iniciar a Interface do Usuário do Conector de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="22f90-338">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

    > [!TIP]
    > <span data-ttu-id="22f90-339">Se fechar o assistente antes de iniciar a interface do usuário do Conector de Certificado, você poderá reabri-la executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="22f90-339">If you close the wizard before launching the Certificate Connector UI, you can reopen it by running the following command:</span></span>
    >
<<<<<<< HEAD
    > <span data-ttu-id="22f90-340">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span><span class="sxs-lookup"><span data-stu-id="22f90-340">**&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**</span></span>

5.  <span data-ttu-id="22f90-341">Na interface do usuário do **Conector de Certificado** :</span><span class="sxs-lookup"><span data-stu-id="22f90-341">In the **Certificate Connector** UI:</span></span>

    <span data-ttu-id="22f90-342">Clique em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.</span><span class="sxs-lookup"><span data-stu-id="22f90-342">Click **Sign In** and enter your Intune service administrator credentials, or credentials for a tenant administrator with the global administration permission.</span></span>

    <span data-ttu-id="22f90-343">Se sua organização usa um servidor proxy e o proxy é necessário para o servidor NDES acessar a Internet, clique em **Usar servidor proxy** e informe o nome do servidor proxy, a porta e as credenciais de conta usadas para a conexão.</span><span class="sxs-lookup"><span data-stu-id="22f90-343">If your organization uses a proxy server and the proxy is needed for the NDES server to access the Internet, click **Use proxy server** and then provide the proxy server name, port, and account credentials to connect.</span></span>

    <span data-ttu-id="22f90-344">Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora e clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="22f90-344">Select the **Advanced** tab, and then provide credentials for an account that has the **Issue and Manage Certificates** permission on your issuing Certificate Authority, and then click **Apply**.</span></span>

    <span data-ttu-id="22f90-345">Agora você pode fechar a interface do usuário do Conector de Certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-345">You can now close the Certificate Connector UI.</span></span>

6.  <span data-ttu-id="22f90-346">Abra um prompt de comando e digite **services.msc**, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector do Intune** e clique em **Reiniciar**.</span><span class="sxs-lookup"><span data-stu-id="22f90-346">Open a command prompt and type **services.msc**, and then press **Enter**, right-click the **Intune Connector Service**, and then click **Restart**.</span></span>

<span data-ttu-id="22f90-347">Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :</span><span class="sxs-lookup"><span data-stu-id="22f90-347">To validate that the service is running, open a browser and enter the following URL, which should return a **403** error:</span></span>

<span data-ttu-id="22f90-348">**http:// &lt;FQDN_do_seu_servidor_NDES&gt;/certsrv/mscep/mscep.dll**</span><span class="sxs-lookup"><span data-stu-id="22f90-348">**http:// &lt;FQDN_of_your_NDES_server&gt;/certsrv/mscep/mscep.dll**</span></span>

## <span data-ttu-id="22f90-349">Como criar um perfil de certificado SCEP</span><span class="sxs-lookup"><span data-stu-id="22f90-349">How to create a SCEP certificate profile</span></span>
<a id="how-to-create-a-scep-certificate-profile" class="xliff"></a>

1. <span data-ttu-id="22f90-350">No Portal do Azure, selecione a carga de trabalho **Configurar dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="22f90-350">In the Azure Portal, select the **Configure devices** workload.</span></span>
2. <span data-ttu-id="22f90-351">Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="22f90-351">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="22f90-352">Na folha de perfis, escolha **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="22f90-352">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="22f90-353">Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.</span><span class="sxs-lookup"><span data-stu-id="22f90-353">On the **Create Profile** blade, enter a **Name** and **Description** for the SCEP certificate profile.</span></span>
5. <span data-ttu-id="22f90-354">Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado SCEP.</span><span class="sxs-lookup"><span data-stu-id="22f90-354">From the **Platform** drop-down list, select the device platform for this SCEP certificate.</span></span> <span data-ttu-id="22f90-355">No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:</span><span class="sxs-lookup"><span data-stu-id="22f90-355">Currently, you can choose one of the following platforms for device restriction settings:</span></span>
    - <span data-ttu-id="22f90-356">**Android**</span><span class="sxs-lookup"><span data-stu-id="22f90-356">**Android**</span></span>
    - <span data-ttu-id="22f90-357">**iOS**</span><span class="sxs-lookup"><span data-stu-id="22f90-357">**iOS**</span></span>
    - <span data-ttu-id="22f90-358">**macOS**</span><span class="sxs-lookup"><span data-stu-id="22f90-358">**macOS**</span></span>
    - <span data-ttu-id="22f90-359">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="22f90-359">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="22f90-360">**Windows 8.1 e posterior**</span><span class="sxs-lookup"><span data-stu-id="22f90-360">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="22f90-361">**Windows 10 e posterior**</span><span class="sxs-lookup"><span data-stu-id="22f90-361">**Windows 10 and later**</span></span>
6. <span data-ttu-id="22f90-362">Na lista suspensa de tipos de **Perfil**, escolha **Certificado SCEP**.</span><span class="sxs-lookup"><span data-stu-id="22f90-362">From the **Profile** type drop-down list, choose **SCEP certificate**.</span></span>
7. <span data-ttu-id="22f90-363">Na folha **Certificado SCEP**, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="22f90-363">On the **SCEP Certificate** blade, configure the following settings:</span></span>
    - <span data-ttu-id="22f90-364">**Período de validade do certificado** – Se você executar o comando **certutil – setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** na AC emissora, o que permite usar um período de validade personalizado, poderá especificar a quantidade de tempo restante antes que o certificado expire.</span><span class="sxs-lookup"><span data-stu-id="22f90-364">**Certificate validity period** - If you have run the **certutil - setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** command on the issuing CA, which allows a custom validity period, you can specify the amount of remaining time before the certificate expires.</span></span><br><span data-ttu-id="22f90-365">Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior.</span><span class="sxs-lookup"><span data-stu-id="22f90-365">You can specify a value that is lower than the validity period in the specified certificate template, but not higher.</span></span> <span data-ttu-id="22f90-366">Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos.</span><span class="sxs-lookup"><span data-stu-id="22f90-366">For example, if the certificate validity period in the certificate template is two years, you can specify a value of one year but not a value of five years.</span></span> <span data-ttu-id="22f90-367">O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora.</span><span class="sxs-lookup"><span data-stu-id="22f90-367">The value must also be lower than the remaining validity period of the issuing CA's certificate.</span></span> 
    - <span data-ttu-id="22f90-368">**KSP (provedor de armazenamento de chaves)** (Windows Phone 8.1, Windows 8.1 e Windows 10) – Especifique o local em que a chave do certificado será armazenada.</span><span class="sxs-lookup"><span data-stu-id="22f90-368">**Key storage provider (KSP)** (Windows Phone 8.1, Windows 8.1, Windows 10) - Specify where the key to the certificate will be stored.</span></span> <span data-ttu-id="22f90-369">Escolha um destes valores:</span><span class="sxs-lookup"><span data-stu-id="22f90-369">Choose from one of the following values:</span></span>
        - <span data-ttu-id="22f90-370">**Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**</span><span class="sxs-lookup"><span data-stu-id="22f90-370">**Enroll to Trusted Platform Module (TPM) KSP if present, otherwise Software KSP**</span></span>
        - <span data-ttu-id="22f90-371">**Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**</span><span class="sxs-lookup"><span data-stu-id="22f90-371">**Enroll to Trusted Platform Module (TPM) KSP, otherwise fail**</span></span>
        - <span data-ttu-id="22f90-372">**Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**</span><span class="sxs-lookup"><span data-stu-id="22f90-372">**Enroll to Passport, otherwise fail (Windows 10 and later)**</span></span>
        - <span data-ttu-id="22f90-373">**Registrar no Software KSP**</span><span class="sxs-lookup"><span data-stu-id="22f90-373">**Enroll to Software KSP**</span></span>
    - <span data-ttu-id="22f90-374">**Formato de nome da entidade** – Na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-374">**Subject name format** - From the list, select how Intune automatically creates the subject name in the certificate request.</span></span> <span data-ttu-id="22f90-375">Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade.</span><span class="sxs-lookup"><span data-stu-id="22f90-375">If the certificate is for a user, you can also include the user's email address in the subject name.</span></span> <span data-ttu-id="22f90-376">Escolha:</span><span class="sxs-lookup"><span data-stu-id="22f90-376">Choose from:</span></span>
        - <span data-ttu-id="22f90-377">**Não configurado**</span><span class="sxs-lookup"><span data-stu-id="22f90-377">**Not configured**</span></span>
        - <span data-ttu-id="22f90-378">**Nome comum**</span><span class="sxs-lookup"><span data-stu-id="22f90-378">**Common name**</span></span>
        - <span data-ttu-id="22f90-379">**Nome comum incluindo email**</span><span class="sxs-lookup"><span data-stu-id="22f90-379">**Common name including email**</span></span>
        - <span data-ttu-id="22f90-380">**Nome comum como email**</span><span class="sxs-lookup"><span data-stu-id="22f90-380">**Common name as email**</span></span>
        - <span data-ttu-id="22f90-381">**Personalizar** – ao selecionar essa opção, outro campo suspenso é exibido.</span><span class="sxs-lookup"><span data-stu-id="22f90-381">**Custom** - When you select this option, another drop-down field is displayed.</span></span> <span data-ttu-id="22f90-382">Use esse campo para inserir um formato de nome da entidade personalizado.</span><span class="sxs-lookup"><span data-stu-id="22f90-382">You use this field to enter a custom subject name format.</span></span> <span data-ttu-id="22f90-383">As duas variáveis com suporte para o formato personalizado são **Nome Comum (CN)** e **Email (E)**.</span><span class="sxs-lookup"><span data-stu-id="22f90-383">The two variables supported for the custom format are **Common Name (CN)** and **Email (E)**.</span></span> <span data-ttu-id="22f90-384">Usando uma combinação de uma ou muitas dessas variáveis e cadeias de caracteres estáticas, é possível criar um formato de nome da entidade personalizado, como este: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Nesse exemplo, você criou um formato de nome da entidade que, além das variáveis CN e E, usa cadeias de caracteres para os valores de Unidade Organizacional, Organização, Local, Estado e País.</span><span class="sxs-lookup"><span data-stu-id="22f90-384">By using a combination of one or many of these variables and static strings, you can create a custom subject name format, like this one: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** In this example, you created a subject name format that, in addition to the CN and E variables, uses strings for Organizational Unit, Organization, Location, State, and Country values.</span></span> <span data-ttu-id="22f90-385">[Este tópico](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) mostra a função **CertStrToName** e suas cadeias de caracteres com suporte.</span><span class="sxs-lookup"><span data-stu-id="22f90-385">[This topic](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) shows the **CertStrToName** function and its supported strings.</span></span>
        
    - <span data-ttu-id="22f90-386">**Nome alternativo da entidade** – Especifique como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-386">**Subject alternative name** - Specify how Intune automatically creates the values for the subject alternative name (SAN) in the certificate request.</span></span> <span data-ttu-id="22f90-387">Se tiver selecionado um tipo de certificado de usuário, por exemplo, você pode incluir o UPN no nome alternativo da entidade.</span><span class="sxs-lookup"><span data-stu-id="22f90-387">For example, if you selected a user certificate type, you can include the user principal name (UPN) in the subject alternative name.</span></span> <span data-ttu-id="22f90-388">Se o certificado do cliente for usado para autenticar em um Servidor de Políticas de Rede, você deve definir o nome alternativo da entidade como o UPN.</span><span class="sxs-lookup"><span data-stu-id="22f90-388">If the client certificate will be used to authenticate to a Network Policy Server, you must set the subject alternative name to the UPN.</span></span> 
    - <span data-ttu-id="22f90-389">**Uso de chave** – Especifique as opções de uso de chave para o certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-389">**Key usage** - Specify key usage options for the certificate.</span></span> <span data-ttu-id="22f90-390">Você pode escolher entre as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="22f90-390">You can choose from the following options:</span></span> 
        - <span data-ttu-id="22f90-391">**Codificação de chave:** permitir a troca de chaves apenas quando a chave for criptografada.</span><span class="sxs-lookup"><span data-stu-id="22f90-391">**Key encipherment:** Allow key exchange only when the key is encrypted.</span></span> 
        - <span data-ttu-id="22f90-392">**Assinatura digital:** permitir a troca de chaves apenas quando uma assinatura digital ajudar a proteger a chave.</span><span class="sxs-lookup"><span data-stu-id="22f90-392">**Digital signature:** Allow key exchange only when a digital signature helps protect the key.</span></span> 
    - <span data-ttu-id="22f90-393">**Tamanho da chave (bits)** – Selecione o número de bits que estão contidos na chave.</span><span class="sxs-lookup"><span data-stu-id="22f90-393">**Key size (bits)** - Select the number of bits that will be contained in the key.</span></span> 
    - <span data-ttu-id="22f90-394">**Algoritmo de hash:** (Android, Windows Phone 8.1, Windows 8.1 e Windows 10) – Selecione um dos tipos de algoritmo de hash disponíveis para ser usado com esse certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-394">**Hash algorithm** (Android, Windows Phone 8.1, Windows 8.1, Windows 10) - Select one of the available hash algorithm types to use with this certificate.</span></span> <span data-ttu-id="22f90-395">Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão.</span><span class="sxs-lookup"><span data-stu-id="22f90-395">Select the strongest level of security that the connecting devices support.</span></span> 
    - <span data-ttu-id="22f90-396">**Certificado Raiz** – Escolha um perfil de certificado de AC raiz configurado anteriormente e atribuído ao usuário ou dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22f90-396">**Root Certificate** - Choose a root CA certificate profile that you have previously configured and assigned to the user or device.</span></span> <span data-ttu-id="22f90-397">Esse certificado AC deve ser o certificado raiz da AC que emite o certificado que você está configurando nesse perfil de certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-397">This CA certificate must be the root certificate for the CA that will issue the certificate that you are configuring in this certificate profile.</span></span> 
    - <span data-ttu-id="22f90-398">**Uso estendido da chave** – Escolha **Adicionar** para adicionar valores para a finalidade desejada do certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-398">**Extended key usage** - Choose **Add** to add values for the certificate's intended purpose.</span></span> <span data-ttu-id="22f90-399">Na maioria dos casos, o certificado exigirá **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor.</span><span class="sxs-lookup"><span data-stu-id="22f90-399">In most cases, the certificate will require **Client Authentication** so that the user or device can authenticate to a server.</span></span> <span data-ttu-id="22f90-400">No entanto, você pode adicionar outros usos da chave conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="22f90-400">However, you can add any other key usages as required.</span></span> 
    - <span data-ttu-id="22f90-401">**Configurações de Registro**</span><span class="sxs-lookup"><span data-stu-id="22f90-401">**Enrollment Settings**</span></span>
        - <span data-ttu-id="22f90-402">**Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.</span><span class="sxs-lookup"><span data-stu-id="22f90-402">**Renewal threshold (%)** - Specify the percentage of the certificate lifetime that remains before the device requests renewal of the certificate.</span></span>
        - <span data-ttu-id="22f90-403">**URLs de servidor SCEP** – Especifique uma ou mais URLs para os servidores de NDES que emitirão certificados por meio do protocolo SCEP.</span><span class="sxs-lookup"><span data-stu-id="22f90-403">**SCEP Server URLs** - Specify one or more URLs for the NDES Servers that will issue certificates via SCEP.</span></span> 
8. <span data-ttu-id="22f90-404">Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="22f90-404">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="22f90-405">O perfil será criado e aparecerá na folha da lista de perfis.</span><span class="sxs-lookup"><span data-stu-id="22f90-405">The profile will be created and appears on the profiles list blade.</span></span>

## <span data-ttu-id="22f90-406">Como atribuir o perfil de certificado</span><span class="sxs-lookup"><span data-stu-id="22f90-406">How to assign the certificate profile</span></span>
<a id="how-to-assign-the-certificate-profile" class="xliff"></a>

<span data-ttu-id="22f90-407">Antes de atribuir perfis de certificado a grupos, considere o seguinte:</span><span class="sxs-lookup"><span data-stu-id="22f90-407">Consider the following before you assign certificate profiles to groups:</span></span>

- <span data-ttu-id="22f90-408">Quando você atribui perfis de certificado a grupos, o arquivo de certificado do perfil do Certificado de Autoridade de Certificação Confiável é instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22f90-408">When you assign certificate profiles to groups, the certificate file from the Trusted CA certificate profile is installed on the device.</span></span> <span data-ttu-id="22f90-409">O dispositivo usa o perfil de certificado SCEP para criar uma solicitação de certificado pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22f90-409">The device uses the SCEP certificate profile to create a certificate request by the device.</span></span>
- <span data-ttu-id="22f90-410">Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.</span><span class="sxs-lookup"><span data-stu-id="22f90-410">Certificate profiles install only on devices running the platform you use when you created the profile.</span></span>
- <span data-ttu-id="22f90-411">Você pode atribuir perfis de certificado para coleções de usuários ou coleções de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="22f90-411">You can assign certificate profiles to user collections or to device collections.</span></span>
- <span data-ttu-id="22f90-412">Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, atribua o perfil de certificado a um grupo de usuários em vez de um grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="22f90-412">To publish a certificate to a device quickly after the device enrolls, assign the certificate profile to a user group rather than to a device group.</span></span> <span data-ttu-id="22f90-413">Se você atribuir um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.</span><span class="sxs-lookup"><span data-stu-id="22f90-413">If you assign to a device group, a full device registration is required before the device receives policies.</span></span>
- <span data-ttu-id="22f90-414">Embora você atribuir cada perfil separadamente, também precisará atribuir a AC Raiz Confiável e o perfil SCEP ou PKCS.</span><span class="sxs-lookup"><span data-stu-id="22f90-414">Although you assign each profile separately, you also need to assign the Trusted Root CA and the SCEP or PKCS profile.</span></span> <span data-ttu-id="22f90-415">Caso contrário, a política de certificação SCEP ou PKCS falhará.</span><span class="sxs-lookup"><span data-stu-id="22f90-415">Otherwise, the SCEP or PKCS certificate policy will fail.</span></span>

<span data-ttu-id="22f90-416">Para saber mais sobre como atribuir perfis, confira [Como atribuir perfis de dispositivo](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="22f90-416">For information about how to assign profiles, see [How to assign device profiles](device-profile-assign.md).</span></span>
=======
    > **&lt;install_Path&gt;\NDESConnectorUI\NDESConnectorUI.exe**

5.  Na interface do usuário do **Conector de Certificado** :

    Clique em **Entrar** e insira suas credenciais de administrador de serviços do Intune ou as credenciais de um administrador de locatários com permissão de administração global.

    Se sua organização usa um servidor proxy e o proxy é necessário para o servidor NDES acessar a Internet, clique em **Usar servidor proxy** e informe o nome do servidor proxy, a porta e as credenciais de conta usadas para a conexão.

    Selecione a guia **Avançado** e forneça credenciais para uma conta que tenha a permissão **Emitir e Gerenciar Certificados** na sua Autoridade de Certificação emissora e clique em **Aplicar**.

    Agora você pode fechar a interface do usuário do Conector de Certificado.

6.  Abra um prompt de comando e digite **services.msc**, pressione **Enter**, clique com o botão direito do mouse em **Serviço de Conector do Intune** e clique em **Reiniciar**.

Para validar que o serviço está em execução, abra um navegador e digite a seguinte URL, que deve retornar um erro **403** :

**http:// &lt;FQDN_do_seu_servidor_NDES&gt;/certsrv/mscep/mscep.dll**

## Como criar um perfil de certificado SCEP
<a id="how-to-create-a-scep-certificate-profile" class="xliff"></a>

1. No Portal do Azure, selecione a carga de trabalho **Configurar dispositivos**.
2. Na folha **Configurações do Dispositivo**, escolha **Gerenciar** > **Perfis**.
3. Na folha de perfis, escolha **Criar Perfil**.
4. Na folha **Criar Perfil**, insira um **Nome** e uma **Descrição** para o perfil de certificado SCEP.
5. Na lista suspensa **Plataforma**, selecione a plataforma de dispositivo para esse certificado SCEP. No momento, é possível escolher uma das seguintes plataformas para as configurações de restrição de dispositivo:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 e posterior**
    - **Windows 10 e posterior**
6. Na lista suspensa de tipos de **Perfil**, escolha **Certificado SCEP**.
7. Na folha **Certificado SCEP**, defina as seguintes configurações:
    - **Período de validade do certificado** – Se você executar o comando **certutil – setreg Policy\EditFlags +EDITF_ATTRIBUTEENDDATE** na AC emissora, o que permite usar um período de validade personalizado, poderá especificar a quantidade de tempo restante antes que o certificado expire.<br>Você pode especificar um valor inferior ao período de validade do modelo de certificado especificado, mas não superior. Por exemplo, se o período de validade do certificado em um modelo de certificado for de dois anos, você pode especificar um valor de um ano, mas não de cinco anos. O valor também tem que ser inferior ao período de validade restante do certificado da AC emissora. 
    - **KSP (provedor de armazenamento de chaves)** (Windows Phone 8.1, Windows 8.1 e Windows 10) – Especifique o local em que a chave do certificado será armazenada. Escolha um destes valores:
        - **Registrar no KSP do TPM (Trusted Platform Module) se existir; caso contrário, no KSP de Software**
        - **Registrar no KSP do TPM (Trusted Platform Module); caso contrário, falha**
        - **Registrar no Passport; caso contrário, falha (Windows 10 e posterior)**
        - **Registrar no Software KSP**
    - **Formato de nome da entidade** – Na lista, selecione como o Intune cria automaticamente o nome da entidade na solicitação de certificado. Se o certificado for para um usuário, você também pode incluir o endereço de email do usuário no nome da entidade. Escolha:
        - **Não configurado**
        - **Nome comum**
        - **Nome comum incluindo email**
        - **Nome comum como email**
        - **Personalizar** – ao selecionar essa opção, outro campo suspenso é exibido. Use esse campo para inserir um formato de nome da entidade personalizado. As duas variáveis com suporte para o formato personalizado são **Nome Comum (CN)** e **Email (E)**. Usando uma combinação de uma ou muitas dessas variáveis e cadeias de caracteres estáticas, é possível criar um formato de nome da entidade personalizado, como este: **CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US** Nesse exemplo, você criou um formato de nome da entidade que, além das variáveis CN e E, usa cadeias de caracteres para os valores de Unidade Organizacional, Organização, Local, Estado e País. [Este tópico](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) mostra a função **CertStrToName** e suas cadeias de caracteres com suporte.
        
    - **Nome alternativo da entidade** – Especifique como o Intune criará automaticamente os valores para o SAN (nome alternativo da entidade) na solicitação de certificado. Se tiver selecionado um tipo de certificado de usuário, por exemplo, você pode incluir o UPN no nome alternativo da entidade. Se o certificado do cliente for usado para autenticar em um Servidor de Políticas de Rede, você deve definir o nome alternativo da entidade como o UPN. 
    - **Uso de chave** – Especifique as opções de uso de chave para o certificado. Você pode escolher entre as seguintes opções: 
        - **Codificação de chave:** permitir a troca de chaves apenas quando a chave for criptografada. 
        - **Assinatura digital:** permitir a troca de chaves apenas quando uma assinatura digital ajudar a proteger a chave. 
    - **Tamanho da chave (bits)** – Selecione o número de bits que estão contidos na chave. 
    - **Algoritmo de hash:** (Android, Windows Phone 8.1, Windows 8.1 e Windows 10) – Selecione um dos tipos de algoritmo de hash disponíveis para ser usado com esse certificado. Selecione o nível mais alto de segurança que dá suporte aos dispositivos de conexão. 
    - **Certificado Raiz** – Escolha um perfil de certificado de AC raiz configurado anteriormente e atribuído ao usuário ou dispositivo. Esse certificado AC deve ser o certificado raiz da AC que emite o certificado que você está configurando nesse perfil de certificado. 
    - **Uso estendido da chave** – Escolha **Adicionar** para adicionar valores para a finalidade desejada do certificado. Na maioria dos casos, o certificado exigirá **Autenticação de cliente** para que o usuário ou dispositivo possa autenticar-se em um servidor. No entanto, você pode adicionar outros usos da chave conforme necessário. 
    - **Configurações de Registro**
        - **Limite de renovação (%)** – Especifique o percentual do tempo de vida do certificado restante antes da renovação das solicitações de dispositivo do certificado.
        - **URLs de servidor SCEP** – Especifique uma ou mais URLs para os servidores de NDES que emitirão certificados por meio do protocolo SCEP. 
8. Após terminar, volte para a folha **Criar Perfil** e selecione **Criar**.

O perfil será criado e aparecerá na folha da lista de perfis.

## Como atribuir o perfil de certificado
<a id="how-to-assign-the-certificate-profile" class="xliff"></a>

Antes de atribuir perfis de certificado a grupos, considere o seguinte:

- Quando você atribui perfis de certificado a grupos, o arquivo de certificado do perfil do Certificado de Autoridade de Certificação Confiável é instalado no dispositivo. O dispositivo usa o perfil de certificado SCEP para criar uma solicitação de certificado pelo dispositivo.
- Os perfis de certificado são instalados somente em dispositivos que executam a plataforma que você usa ao criar o perfil.
- Você pode atribuir perfis de certificado para coleções de usuários ou coleções de dispositivos.
- Para publicar um certificado em um dispositivo rapidamente depois que o dispositivo for registrado, atribua o perfil de certificado a um grupo de usuários em vez de um grupo de dispositivos. Se você atribuir um grupo de dispositivos, um registro de dispositivo completo será necessário para que o dispositivo receba políticas.
- Embora você atribuir cada perfil separadamente, também precisará atribuir a AC Raiz Confiável e o perfil SCEP ou PKCS. Caso contrário, a política de certificação SCEP ou PKCS falhará.

Para saber mais sobre como atribuir perfis, confira [Como atribuir perfis de dispositivo](device-profile-assign.md).
>>>>>>> live

