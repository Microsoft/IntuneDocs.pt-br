---
title: "Configurações de VPN do Intune para dispositivos Windows 10"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos Windows 10."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6f112983a33c1af24d288f19140114084575f36d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="8cd33-103">Configurações de VPN para dispositivos Windows 10 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8cd33-103">VPN settings for Windows 10 devices in Microsoft Intune</span></span>
<a id="vpn-settings-for-windows-10-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="8cd33-104">Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.</span><span class="sxs-lookup"><span data-stu-id="8cd33-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>


## <span data-ttu-id="8cd33-105">Configurações de VPN de base</span><span class="sxs-lookup"><span data-stu-id="8cd33-105">Base VPN settings</span></span>
<a id="base-vpn-settings" class="xliff"></a>


- <span data-ttu-id="8cd33-106">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="8cd33-107">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8cd33-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="8cd33-108">**Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-108">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="8cd33-109">**Adicionar** – Abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="8cd33-109">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="8cd33-110">**Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.</span><span class="sxs-lookup"><span data-stu-id="8cd33-110">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="8cd33-111">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-111">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="8cd33-112">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="8cd33-112">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="8cd33-113">**Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usarão para estabelecer a conexão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-113">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="8cd33-114">Verifique se você definiu apenas um servidor como padrão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-114">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="8cd33-115">**Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-115">**Import** - Browse to a file containing a comma-separated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="8cd33-116">Escolha **OK** para importá-los para a lista **Servidores**.</span><span class="sxs-lookup"><span data-stu-id="8cd33-116">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="8cd33-117">**Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).</span><span class="sxs-lookup"><span data-stu-id="8cd33-117">**Export** - Exports the list of servers to a comma-separated-values (csv) file.</span></span>

<span data-ttu-id="8cd33-118">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="8cd33-118">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
- <span data-ttu-id="8cd33-119">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="8cd33-119">**Pulse Secure**</span></span>
- <span data-ttu-id="8cd33-120">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="8cd33-120">**F5 Edge Client**</span></span>
- <span data-ttu-id="8cd33-121">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="8cd33-121">**Dell SonicWALL Mobile Connect**</span></span>
- <span data-ttu-id="8cd33-122">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="8cd33-122">**Check Point Capsule VPN**</span></span>
- <span data-ttu-id="8cd33-123">**Automático**</span><span class="sxs-lookup"><span data-stu-id="8cd33-123">**Automatic**</span></span>
- <span data-ttu-id="8cd33-124">**IKEv2**</span><span class="sxs-lookup"><span data-stu-id="8cd33-124">**IKEv2**</span></span>
- <span data-ttu-id="8cd33-125">**L2TP**</span><span class="sxs-lookup"><span data-stu-id="8cd33-125">**L2TP**</span></span>
- <span data-ttu-id="8cd33-126">**PPTP**</span><span class="sxs-lookup"><span data-stu-id="8cd33-126">**PPTP**</span></span>

<span data-ttu-id="8cd33-127">**Grupo de logon ou domínio** (somente Dell SonicWALL Mobile Connect) – Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="8cd33-127">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>

<span data-ttu-id="8cd33-128">**XML Personalizado**/**XML EAP** – Especifique os comandos XML personalizados para configurar a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="8cd33-128">**Custom XML**/**EAP XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

<span data-ttu-id="8cd33-129">**Exemplo do Pulse Secure:**</span><span class="sxs-lookup"><span data-stu-id="8cd33-129">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

<span data-ttu-id="8cd33-130">**Exemplo do CheckPoint Mobile VPN:**</span><span class="sxs-lookup"><span data-stu-id="8cd33-130">**Example for CheckPoint Mobile VPN:**</span></span>

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="8cd33-131">**Exemplo do Dell SonicWALL Mobile Connect:**</span><span class="sxs-lookup"><span data-stu-id="8cd33-131">**Example for Dell SonicWALL Mobile Connect:**</span></span>

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

<span data-ttu-id="8cd33-132">**Exemplo do F5 Edge Client:**</span><span class="sxs-lookup"><span data-stu-id="8cd33-132">**Example for F5 Edge Client:**</span></span>

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

<span data-ttu-id="8cd33-133">Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.</span><span class="sxs-lookup"><span data-stu-id="8cd33-133">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>

<span data-ttu-id="8cd33-134">**Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego.</span><span class="sxs-lookup"><span data-stu-id="8cd33-134">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="8cd33-135">Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.</span><span class="sxs-lookup"><span data-stu-id="8cd33-135">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>
- <span data-ttu-id="8cd33-136">**Rotas de túnel dividido para essa conexão VPN** – Adicionar rotas opcionais para provedores VPN de terceiros.</span><span class="sxs-lookup"><span data-stu-id="8cd33-136">**Split tunneling routes for this VPN connection** - Add optional routes for third-party VPN providers.</span></span> <span data-ttu-id="8cd33-137">Especifique um prefixo de destino e um tamanho de prefixo para cada um.</span><span class="sxs-lookup"><span data-stu-id="8cd33-137">Specify a destination prefix, and a prefix size for each.</span></span>

## <span data-ttu-id="8cd33-138">Regras de Aplicativos e Tráfego</span><span class="sxs-lookup"><span data-stu-id="8cd33-138">Apps and Traffic Rules</span></span>
<a id="apps-and-traffic-rules" class="xliff"></a>

<span data-ttu-id="8cd33-139">**Restringir a conexão VPN para esses aplicativos** – Habilite esta opção se você quiser apenas que os aplicativos que você especificar usem a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="8cd33-139">**Restrict VPN connection to these apps** - Enable this option if you only want apps you specify to use the VPN connection.</span></span>
<span data-ttu-id="8cd33-140">**Aplicativos associados** – Forneça uma lista de aplicativos que usarão automaticamente a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="8cd33-140">**Associated Apps** - Provide a list of apps that will automatically use the VPN connection.</span></span> <span data-ttu-id="8cd33-141">O tipo de aplicativo determinará o identificador do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8cd33-141">The type of app will determine the app identifier.</span></span> <span data-ttu-id="8cd33-142">Para um aplicativo universal, forneça o nome da família de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8cd33-142">For a universal app, provide the package family name.</span></span> <span data-ttu-id="8cd33-143">Para um aplicativo da área de trabalho, forneça o caminho do arquivo do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8cd33-143">For a desktop app, provide the file path of the app.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8cd33-144">É recomendável que você proteja todas as listas de aplicativos compiladas para uso na configuração de VPN por aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8cd33-144">We recommend that you secure all lists of apps that you compile for use in configuration of per-app VPN.</span></span> <span data-ttu-id="8cd33-145">Se um usuário não autorizado modificar sua lista e você o importar para a lista de aplicativo VPN por aplicativo, você potencialmente autorizará o acesso VPN para aplicativos que não deveriam ter acesso.</span><span class="sxs-lookup"><span data-stu-id="8cd33-145">If an unauthorized user modifies your list and you import it into the per-app VPN app list, you will potentially authorize VPN access to apps that should not have access.</span></span> <span data-ttu-id="8cd33-146">É uma maneira de proteger as listas de aplicativo usando uma ACL (lista de controle de acesso).</span><span class="sxs-lookup"><span data-stu-id="8cd33-146">One way you can secure app lists is by using an access control list (ACL).</span></span>

<span data-ttu-id="8cd33-147">**Regras de tráfego de rede para esta conexão VPN** – Selecione quais protocolos e quais intervalos de endereços e de portas locais e remotas serão habilitados para a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="8cd33-147">**Network traffic rules for this VPN connection** - Select which protocols, and which local and remote port and address ranges, will be enabled for the VPN connection.</span></span> <span data-ttu-id="8cd33-148">Se você não criar uma regra de tráfego de rede, todos os protocolos, portas e intervalos de endereços serão habilitados.</span><span class="sxs-lookup"><span data-stu-id="8cd33-148">If you do not create a network traffic rule, all protocols, ports, and address ranges are enabled.</span></span> <span data-ttu-id="8cd33-149">Após você criar uma regra, a conexão VPN usará somente os protocolos, portas e intervalos de endereços que você especificar na regra.</span><span class="sxs-lookup"><span data-stu-id="8cd33-149">After you create a rule, the VPN connection will use only the protocols, ports, and address ranges that you specify in that rule.</span></span>


## <span data-ttu-id="8cd33-150">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="8cd33-150">Conditional Access</span></span>
<a id="conditional-access" class="xliff"></a>

<span data-ttu-id="8cd33-151">**Acesso condicional para essa conexão VPN** -
**SSO (logon único) com certificado alternativo** -
**Uso estendido de chave** -
**Hash do emissor** -</span><span class="sxs-lookup"><span data-stu-id="8cd33-151">**Conditional access for this VPN connection** -
**Single sign-on (SSO) with alternate certificate** -
**Extended key usage** -
**Issuer hash** -</span></span>

## <span data-ttu-id="8cd33-152">Configurações de DNS</span><span class="sxs-lookup"><span data-stu-id="8cd33-152">DNS Settings</span></span>
<a id="dns-settings" class="xliff"></a>

<span data-ttu-id="8cd33-153">**Nomes e servidores DNS para esta conexão VPN** – Selecione quais servidores DNS a conexão VPN usará depois que a conexão for estabelecida.</span><span class="sxs-lookup"><span data-stu-id="8cd33-153">**DNS names and servers for this VPN connection** - Select which DNS servers the VPN connection will use after the connection is established.</span></span>
<span data-ttu-id="8cd33-154">Para cada servidor.</span><span class="sxs-lookup"><span data-stu-id="8cd33-154">For each server.</span></span> <span data-ttu-id="8cd33-155">especifique:</span><span class="sxs-lookup"><span data-stu-id="8cd33-155">specify:</span></span>
- <span data-ttu-id="8cd33-156">**Nome DNS**</span><span class="sxs-lookup"><span data-stu-id="8cd33-156">**DNS Name**</span></span>
- <span data-ttu-id="8cd33-157">**Servidor DNS**</span><span class="sxs-lookup"><span data-stu-id="8cd33-157">**DNS Server**</span></span>
- <span data-ttu-id="8cd33-158">**Proxy**</span><span class="sxs-lookup"><span data-stu-id="8cd33-158">**Proxy**</span></span>

## <span data-ttu-id="8cd33-159">Configurações de proxy</span><span class="sxs-lookup"><span data-stu-id="8cd33-159">Proxy settings</span></span>
<a id="proxy-settings" class="xliff"></a>

- <span data-ttu-id="8cd33-160">**Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="8cd33-160">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="8cd33-161">Para obter mais informações, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8cd33-161">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="8cd33-162">**Automático** – Use um arquivo de configuração para definir o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="8cd33-162">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="8cd33-163">Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8cd33-163">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="8cd33-164">**Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="8cd33-164">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="8cd33-165">**Endereço** – Insira o endereço do servidor proxy (como um endereço IP).</span><span class="sxs-lookup"><span data-stu-id="8cd33-165">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="8cd33-166">**Número da porta** – Insira o número de porta associado ao servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="8cd33-166">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="8cd33-167">**Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar.</span><span class="sxs-lookup"><span data-stu-id="8cd33-167">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="8cd33-168">Para obter mais informações, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="8cd33-168">For more information, see your Windows Server documentation.</span></span>
