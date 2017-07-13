---
title: "Configurações de VPN do Intune para dispositivos iOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos iOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1447c123-ea33-4ea0-aab4-69577cdb8d00
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a6cc079b05037cc18b7d27dd0d2674e87e1d54d0
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="f5adb-103">Configurações de VPN para dispositivos iOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f5adb-103">VPN settings for iOS devices in Microsoft Intune</span></span>
<a id="vpn-settings-for-ios-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f5adb-104">Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.</span><span class="sxs-lookup"><span data-stu-id="f5adb-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <span data-ttu-id="f5adb-105">Configurações de VPN de base</span><span class="sxs-lookup"><span data-stu-id="f5adb-105">Base VPN settings</span></span>
<a id="base-vpn-settings" class="xliff"></a>


<span data-ttu-id="f5adb-106">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="f5adb-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="f5adb-107">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f5adb-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="f5adb-108">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="f5adb-108">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="f5adb-109">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="f5adb-109">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="f5adb-110">**Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:</span><span class="sxs-lookup"><span data-stu-id="f5adb-110">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="f5adb-111">**Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="f5adb-111">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="f5adb-112">Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="f5adb-112">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="f5adb-113">**Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="f5adb-113">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="f5adb-114">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="f5adb-114">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="f5adb-115">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="f5adb-115">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="f5adb-116">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="f5adb-116">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="f5adb-117">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="f5adb-117">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="f5adb-118">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="f5adb-118">**F5 Edge Client**</span></span>
    - <span data-ttu-id="f5adb-119">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="f5adb-119">**Pulse Secure**</span></span>
    - <span data-ttu-id="f5adb-120">**Cisco (IPsec)**</span><span class="sxs-lookup"><span data-stu-id="f5adb-120">**Cisco (IPSec)**</span></span>
    - <span data-ttu-id="f5adb-121">**Citrix**</span><span class="sxs-lookup"><span data-stu-id="f5adb-121">**Citrix**</span></span>
    - <span data-ttu-id="f5adb-122">**VPN personalizado**</span><span class="sxs-lookup"><span data-stu-id="f5adb-122">**Custom VPN**</span></span>
- <span data-ttu-id="f5adb-123">**Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego.</span><span class="sxs-lookup"><span data-stu-id="f5adb-123">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="f5adb-124">Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.</span><span class="sxs-lookup"><span data-stu-id="f5adb-124">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>


## <span data-ttu-id="f5adb-125">Configurações de VPN personalizado</span><span class="sxs-lookup"><span data-stu-id="f5adb-125">Custom VPN settings</span></span>
<a id="custom-vpn-settings" class="xliff"></a>

<span data-ttu-id="f5adb-126">Se você selecionou **VPN Personalizada**, como o tipo de conexão, defina essas configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="f5adb-126">If you selected **Custom VPN** as the connection type, configure these further settings:</span></span>

- <span data-ttu-id="f5adb-127">**Identificador de VPN** Este é um identificador para o aplicativo VPN que você está usando e é fornecido pelo seu provedor VPN.</span><span class="sxs-lookup"><span data-stu-id="f5adb-127">**VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.</span></span>
- <span data-ttu-id="f5adb-128">**Digite os pares de chave-valor para os atributos personalizados de VPN** Adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="f5adb-128">**Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection.</span></span> <span data-ttu-id="f5adb-129">Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="f5adb-129">Again, these values are typically supplied by your VPN provider.</span></span>

## <span data-ttu-id="f5adb-130">Configurações de aplicativos (VPN por aplicativo)</span><span class="sxs-lookup"><span data-stu-id="f5adb-130">Apps (per-app VPN) settings</span></span>
<a id="apps-per-app-vpn-settings" class="xliff"></a>

- <span data-ttu-id="f5adb-131">**VPN por aplicativo** – Habilite essa opção se você quiser que as URLs habilitem a conexão VPN quando eles forem acessadas de um navegador Safari.</span><span class="sxs-lookup"><span data-stu-id="f5adb-131">**Per-app VPN** - Enable this option if you want to URLs that will enable the VPN connection when they are visited from the Safari browser.</span></span> <span data-ttu-id="f5adb-132">Para configurar isso, você deve selecionar **Certificados** como o método de autenticação nas configurações de VPN de base.</span><span class="sxs-lookup"><span data-stu-id="f5adb-132">To configure this, you must have selected **Certificates** as the authentication method in the base VPN settings.</span></span>
- <span data-ttu-id="f5adb-133">**URLs que habilitam a conexão VPN ao usar o navegador Safari** – clique em Adicionar para adicionar uma ou mais URLs de site da web.</span><span class="sxs-lookup"><span data-stu-id="f5adb-133">**URLs that will enable the VPN connection while using the Safari browser** - Click add to add one or more web site URLs.</span></span> <span data-ttu-id="f5adb-134">Quando essas URLs forem acessadas, a conexão VPN será habilitada.</span><span class="sxs-lookup"><span data-stu-id="f5adb-134">When these URL's are visited, the VPN connection will be enabled.</span></span>

- <span data-ttu-id="f5adb-135">**Regras de sob demanda** – Isso permite configurar regras condicionais que controlam quando a conexão VPN é iniciada.</span><span class="sxs-lookup"><span data-stu-id="f5adb-135">**On-demand rules** - This lets you configure conditional rules that control when the VPN connection is initiated.</span></span> <span data-ttu-id="f5adb-136">Por exemplo, você pode criar uma condição em que a conexão VPN é usada somente quando um dispositivo não está conectado a uma das redes Wi-Fi da empresa.</span><span class="sxs-lookup"><span data-stu-id="f5adb-136">For example, you could create a condition where the VPN connection is only used when a device is not connected to one of your company Wi-Fi networks.</span></span> <span data-ttu-id="f5adb-137">Como alternativa, você poderia criar uma condição em que, se um dispositivo não puder acessar um domínio de pesquisa DNS especificado, a conexão VPN não será iniciada.</span><span class="sxs-lookup"><span data-stu-id="f5adb-137">Alternatively, you could create a condition where, if a device cannot access a DNS search domain you specify, then the VPN connection is not initiated.</span></span>

    - <span data-ttu-id="f5adb-138">**Domínios de pesquisa de DNS ou SSIDs** – Selecione se essa condição usará a rede sem fio **SSIDs** ou os **domínios de pesquisa de DNS**.</span><span class="sxs-lookup"><span data-stu-id="f5adb-138">**SSIDs or DNS search domains** - Select whether this condition will use wireless network **SSIDs**, or **DNS search domains**.</span></span> <span data-ttu-id="f5adb-139">Escolha Adicionar para configurar um ou mais SSIDs ou pesquisar domínios.</span><span class="sxs-lookup"><span data-stu-id="f5adb-139">Choose Add to configure one or more SSIDs or search domains.</span></span>
    - <span data-ttu-id="f5adb-140">**Teste de cadeia de caracteres de URL** – opcionalmente, forneça uma URL que usa a regra como um teste.</span><span class="sxs-lookup"><span data-stu-id="f5adb-140">**URL string probe** - Optionally, provide a URL that the rule uses as a test.</span></span> <span data-ttu-id="f5adb-141">Se o dispositivo no qual esse perfil está instalado puder acessar essa URL sem redirecionamento, a conexão da VPN será estabelecida e o dispositivo se conectará à URL de destino.</span><span class="sxs-lookup"><span data-stu-id="f5adb-141">If the device on which this profile is installed is able to access this URL without redirection, the VPN connection will be initiated and the device will connect to the target URL.</span></span> <span data-ttu-id="f5adb-142">O usuário não verá o site da investigação de cadeia de caracteres de URL.</span><span class="sxs-lookup"><span data-stu-id="f5adb-142">The user will not see the URL string probe site.</span></span> <span data-ttu-id="f5adb-143">Um exemplo de uma investigação de cadeia de caracteres de URL é o endereço de um servidor Web de auditoria que verifica a conformidade do dispositivo antes da conexão com a VPN.</span><span class="sxs-lookup"><span data-stu-id="f5adb-143">An example of a URL string probe is the address of an auditing Web server that checks device compliance before connecting the VPN.</span></span> <span data-ttu-id="f5adb-144">Outra possibilidade é que a URL teste a capacidade da VPN de se conectar a um site, antes de conectar o dispositivo à URL de destino por meio da VPN.</span><span class="sxs-lookup"><span data-stu-id="f5adb-144">Another possibility is that the URL tests the ability of the VPN to connect to a site, before connecting the device to the target URL through the VPN.</span></span>
    - <span data-ttu-id="f5adb-145">**Ação de domínio** – Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f5adb-145">**Domain action** - Choose one of the following:</span></span>
        - <span data-ttu-id="f5adb-146">Conectar se necessário –</span><span class="sxs-lookup"><span data-stu-id="f5adb-146">Connect if needed -</span></span> 
        - <span data-ttu-id="f5adb-147">Nunca conectar –</span><span class="sxs-lookup"><span data-stu-id="f5adb-147">Never connect -</span></span> 
    - <span data-ttu-id="f5adb-148">**Ação** – Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f5adb-148">**Action** - Choose one of the following:</span></span>
        - <span data-ttu-id="f5adb-149">Conectar –</span><span class="sxs-lookup"><span data-stu-id="f5adb-149">Connect -</span></span> 
        - <span data-ttu-id="f5adb-150">Avaliar conexão –</span><span class="sxs-lookup"><span data-stu-id="f5adb-150">Evaluate connection -</span></span> 
        - <span data-ttu-id="f5adb-151">Ignorar –</span><span class="sxs-lookup"><span data-stu-id="f5adb-151">Ignore -</span></span> 
        - <span data-ttu-id="f5adb-152">Desconectar –</span><span class="sxs-lookup"><span data-stu-id="f5adb-152">Disconnect -</span></span> 


## <span data-ttu-id="f5adb-153">Configurações de proxy</span><span class="sxs-lookup"><span data-stu-id="f5adb-153">Proxy settings</span></span>
<a id="proxy-settings" class="xliff"></a>

- <span data-ttu-id="f5adb-154">**Automático** – Use um arquivo de configuração para definir o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f5adb-154">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="f5adb-155">Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="f5adb-155">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="f5adb-156">**Endereço** – Insira o endereço do servidor proxy (como um endereço IP).</span><span class="sxs-lookup"><span data-stu-id="f5adb-156">**Address** - Enter the proxy server address (as an IP address).</span></span>
- <span data-ttu-id="f5adb-157">**Número da porta** – Insira o número de porta associado ao servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="f5adb-157">**Port number** - Enter the port number associated with the proxy server.</span></span>
