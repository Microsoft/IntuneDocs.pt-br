---
title: "Configurações de VPN do Intune para dispositivos Windows Phone 8.1"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos Windows Phone 8.1."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a009a16c7c475864f665f6ad0ab8fe1853c801b4
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="bc0c2-103">Configurações de VPN para dispositivos Windows Phone 8.1 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bc0c2-103">VPN settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>
<a id="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="bc0c2-104">Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <span data-ttu-id="bc0c2-105">Configurações de VPN de base</span><span class="sxs-lookup"><span data-stu-id="bc0c2-105">Base VPN settings</span></span>
<a id="base-vpn-settings" class="xliff"></a>

- <span data-ttu-id="bc0c2-106">**Aplicar todas as configurações somente ao Windows Phone 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-106">**Apply all settings to Windows Phone 8.1 only** - This is a setting you can configure in the classic Intune portal.</span></span> <span data-ttu-id="bc0c2-107">Não é possível alterar essa configuração no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-107">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="bc0c2-108">Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows Phone 8.1.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-108">If this is set to **Configured**, any settings will only be applied to Windows Phone 8.1 devices.</span></span> <span data-ttu-id="bc0c2-109">Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos Windows 10 Mobile.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-109">If set to **Not Configured**, these settings will also apply to Windows 10 Mobile devices.</span></span>
- <span data-ttu-id="bc0c2-110">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-110">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="bc0c2-111">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-111">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="bc0c2-112">**Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:</span><span class="sxs-lookup"><span data-stu-id="bc0c2-112">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="bc0c2-113">**Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-113">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="bc0c2-114">Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="bc0c2-114">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="bc0c2-115">**Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-115">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="bc0c2-116">**Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-116">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="bc0c2-117">**Adicionar** – Abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="bc0c2-117">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="bc0c2-118">**Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-118">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="bc0c2-119">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-119">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="bc0c2-120">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-120">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="bc0c2-121">**Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usarão para estabelecer a conexão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-121">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="bc0c2-122">Verifique se você definiu apenas um servidor como padrão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-122">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="bc0c2-123">**Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-123">**Import** - Browse to a file containing a comma-separated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="bc0c2-124">Escolha **OK** para importá-los para a lista **Servidores**.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-124">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="bc0c2-125">**Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).</span><span class="sxs-lookup"><span data-stu-id="bc0c2-125">**Export** - Exports the list of servers to a comma-separated-values (csv) file.</span></span>

- <span data-ttu-id="bc0c2-126">**Bypass de VPN na rede Wi-Fi corporativa** – Habilite esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado à rede Wi-Fi da empresa.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-126">**Bypass VPN on company Wi-Fi network** - Enable this option to specify that the VPN connection will not be used when the device is connected to the company Wi-Fi network.</span></span>
- <span data-ttu-id="bc0c2-127">**Bypass de VPN na rede Wi-Fi doméstica** – Habilite esta opção para especificar que a conexão VPN não será usada quando o dispositivo estiver conectado a uma rede Wi-Fi doméstica.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-127">**Bypass VPN on home Wi-Fi network** - Enable this option to specify that the VPN connection will not be used when the device is connected to a home Wi-Fi network.</span></span>

- <span data-ttu-id="bc0c2-128">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="bc0c2-128">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="bc0c2-129">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-129">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="bc0c2-130">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-130">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="bc0c2-131">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-131">**F5 Edge Client**</span></span>
    - <span data-ttu-id="bc0c2-132">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-132">**Pulse Secure**</span></span>

- <span data-ttu-id="bc0c2-133">**Grupo de logon ou domínio** (somente Dell SonicWALL Mobile Connect) – Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-133">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>
- <span data-ttu-id="bc0c2-134">**Função** (somente Pulse Secure) – Especifique o nome da função do usuário que tem acesso a essa conexão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-134">**Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection.</span></span> <span data-ttu-id="bc0c2-135">Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-135">A user role defines personal settings and options, and it enables or disables certain access features.</span></span>
- <span data-ttu-id="bc0c2-136">**Realm** (somente Pulse Secure) – Especifique o nome do realm de autenticação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-136">**Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use.</span></span> <span data-ttu-id="bc0c2-137">Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-137">An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.</span></span>

- <span data-ttu-id="bc0c2-138">**Lista de pesquisa de sufixos DNS** - **Adicionar** um ou mais sufixos de DNS.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-138">**DNS suffix search list** - **Add** one or more DNS suffices.</span></span> <span data-ttu-id="bc0c2-139">Cada sufixo DNS que você especificar será pesquisado durante a conexão com um site usando um nome curto.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-139">Each DNS suffix that you specify will be searched when connecting to a website by using a short name.</span></span> <span data-ttu-id="bc0c2-140">Por exemplo, especifique sufixos DNS **domain1.contoso.com** e **domain2.contoso.com**, visite a URL **http://mywebsite** e as URLs **http://mywebsite.domain1.contoso.com** e **http://mywebsite.domain2.contoso.com serão pesquisadas**.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-140">For example, specify the DNS suffixes **domain1.contoso.com** and **domain2.contoso.com**, visit the URL **http://mywebsite**, and the URLs **http://mywebsite.domain1.contoso.com** and **http://mywebsite.domain2.contoso.com will be searched**.</span></span>

- <span data-ttu-id="bc0c2-141">**XML Personalizado** – Especifique os comandos XML personalizados para configurar a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-141">**Custom XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

    <span data-ttu-id="bc0c2-142">**Exemplo do Pulse Secure:**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-142">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

<span data-ttu-id="bc0c2-143">**Exemplo do CheckPoint Mobile VPN:**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-143">**Example for CheckPoint Mobile VPN:**</span></span>

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="bc0c2-144">**Exemplo do Dell SonicWALL Mobile Connect:**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-144">**Example for Dell SonicWALL Mobile Connect:**</span></span>
```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

<span data-ttu-id="bc0c2-145">**Exemplo do F5 Edge Client:**</span><span class="sxs-lookup"><span data-stu-id="bc0c2-145">**Example for F5 Edge Client:**</span></span>
```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

<span data-ttu-id="bc0c2-146">Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-146">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>

- <span data-ttu-id="bc0c2-147">**Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-147">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="bc0c2-148">Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-148">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>




## <span data-ttu-id="bc0c2-149">Configurações de proxy</span><span class="sxs-lookup"><span data-stu-id="bc0c2-149">Proxy settings</span></span>
<a id="proxy-settings" class="xliff"></a>

- <span data-ttu-id="bc0c2-150">**Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-150">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="bc0c2-151">Para obter mais informações, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-151">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="bc0c2-152">**Automático** – Use um arquivo de configuração para definir o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-152">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="bc0c2-153">Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-153">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="bc0c2-154">**Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-154">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="bc0c2-155">**Endereço** – Insira o endereço do servidor proxy (como um endereço IP).</span><span class="sxs-lookup"><span data-stu-id="bc0c2-155">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="bc0c2-156">**Número da porta** – Insira o número de porta associado ao servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-156">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="bc0c2-157">**Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-157">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="bc0c2-158">Para obter mais informações, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bc0c2-158">For more information, see your Windows Server documentation.</span></span>
