---
title: "Configurações de VPN do Intune para dispositivos Windows 8.1"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos Windows 8.1."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d851a8900ae1e164cb22f1878b352c3e90096f73
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="086c3-103">Configurações VPN para dispositivos Windows 8.1 no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="086c3-103">VPN settings for Windows 8.1 devices in Microsoft Intune</span></span>
<a id="vpn-settings-for-windows-81-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="086c3-104">Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.</span><span class="sxs-lookup"><span data-stu-id="086c3-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <span data-ttu-id="086c3-105">Configurações de VPN de base</span><span class="sxs-lookup"><span data-stu-id="086c3-105">Base VPN settings</span></span>
<a id="base-vpn-settings" class="xliff"></a>


- <span data-ttu-id="086c3-106">**Aplicar todas as configurações somente ao Windows 8.1** – Essa é uma configuração de pode ser definida no Portal Clássico do Intune.</span><span class="sxs-lookup"><span data-stu-id="086c3-106">**Apply all settings to Windows 8.1 only** - This is a setting you can configure in the classic Intune portal.</span></span> <span data-ttu-id="086c3-107">Não é possível alterar essa configuração no Portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="086c3-107">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="086c3-108">Se definido como **Configurado**, as configurações serão aplicadas somente aos dispositivos com Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="086c3-108">If this is set to **Configured**, any settings will only be applied to Windows 8.1 devices.</span></span> <span data-ttu-id="086c3-109">Se definido como **Não Configurado**, essas configurações também serão aplicadas aos dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="086c3-109">If set to **Not Configured**, these settings will also apply to Windows 10 devices.</span></span>
- <span data-ttu-id="086c3-110">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="086c3-110">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="086c3-111">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="086c3-111">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="086c3-112">**Servidores** – Adicionar um ou mais servidores VPN aos quais os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="086c3-112">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="086c3-113">**Adicionar** – Abre a folha **Adicionar linha**, na qual você pode especificar as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="086c3-113">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="086c3-114">**Descrição** – Especifique um nome descritivo para o servidor como **Servidor VPN Contoso**.</span><span class="sxs-lookup"><span data-stu-id="086c3-114">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="086c3-115">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="086c3-115">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="086c3-116">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="086c3-116">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="086c3-117">**Servidor padrão** – Habilita esse servidor como o servidor padrão que os dispositivos usarão para estabelecer a conexão.</span><span class="sxs-lookup"><span data-stu-id="086c3-117">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="086c3-118">Verifique se você definiu apenas um servidor como padrão.</span><span class="sxs-lookup"><span data-stu-id="086c3-118">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="086c3-119">**Importar** – Navegue até um arquivo que contém uma lista separada por vírgulas de servidores no formato descrição, endereço IP ou FQDN, servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="086c3-119">**Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="086c3-120">Escolha **OK** para importá-los para a lista **Servidores**.</span><span class="sxs-lookup"><span data-stu-id="086c3-120">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="086c3-121">**Exportar** – Exporta a lista de servidores para um arquivo de valores separados por vírgula (csv).</span><span class="sxs-lookup"><span data-stu-id="086c3-121">**Export** - Exports the list of servers to a comma-seperated-values (csv) file.</span></span>

- <span data-ttu-id="086c3-122">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="086c3-122">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
- <span data-ttu-id="086c3-123">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="086c3-123">**Check Point Capsule VPN**</span></span>
- <span data-ttu-id="086c3-124">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="086c3-124">**Dell SonicWALL Mobile Connect**</span></span>
- <span data-ttu-id="086c3-125">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="086c3-125">**F5 Edge Client**</span></span>
- <span data-ttu-id="086c3-126">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="086c3-126">**Pulse Secure**</span></span>

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- <span data-ttu-id="086c3-127">**Grupo de logon ou domínio** (somente Dell SonicWALL Mobile Connect) – Especifique o nome do grupo de logon ou domínio ao qual você deseja se conectar.</span><span class="sxs-lookup"><span data-stu-id="086c3-127">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>

- <span data-ttu-id="086c3-128">**Função** (somente Pulse Secure) – Especifique o nome da função do usuário que tem acesso a essa conexão.</span><span class="sxs-lookup"><span data-stu-id="086c3-128">**Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection.</span></span> <span data-ttu-id="086c3-129">Uma função de usuário define configurações e opções pessoais e habilita ou desabilita determinados recursos de acesso.</span><span class="sxs-lookup"><span data-stu-id="086c3-129">A user role defines personal settings and options, and it enables or disables certain access features.</span></span>

- <span data-ttu-id="086c3-130">**Realm** (somente Pulse Secure) – Especifique o nome do realm de autenticação que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="086c3-130">**Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use.</span></span> <span data-ttu-id="086c3-131">Um realm de autenticação é um agrupamento de recursos de autenticação usado pelo tipo de conexão Pulse Secure.</span><span class="sxs-lookup"><span data-stu-id="086c3-131">An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.</span></span>


- <span data-ttu-id="086c3-132">**XML Personalizado** – Especifique os comandos XML personalizados para configurar a conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="086c3-132">**Custom XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

<span data-ttu-id="086c3-133">**Exemplo do Pulse Secure:**</span><span class="sxs-lookup"><span data-stu-id="086c3-133">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

<span data-ttu-id="086c3-134">**Exemplo do CheckPoint Mobile VPN:**</span><span class="sxs-lookup"><span data-stu-id="086c3-134">**Example for CheckPoint Mobile VPN:**</span></span>
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

<span data-ttu-id="086c3-135">**Exemplo do Dell SonicWALL Mobile Connect:**</span><span class="sxs-lookup"><span data-stu-id="086c3-135">**Example for Dell SonicWALL Mobile Connect:**</span></span>
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

<span data-ttu-id="086c3-136">**Exemplo do F5 Edge Client:**</span><span class="sxs-lookup"><span data-stu-id="086c3-136">**Example for F5 Edge Client:**</span></span>

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

<span data-ttu-id="086c3-137">Consulte a documentação do VPN de cada fabricante para obter mais informações sobre como escrever comandos XML personalizados.</span><span class="sxs-lookup"><span data-stu-id="086c3-137">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>


## <span data-ttu-id="086c3-138">Configurações de proxy</span><span class="sxs-lookup"><span data-stu-id="086c3-138">Proxy settings</span></span>
<a id="proxy-settings" class="xliff"></a>

- <span data-ttu-id="086c3-139">**Detectar automaticamente as configurações de proxy** – Se o servidor VPN exigir um servidor proxy para a conexão, especifique se deseja que os dispositivos detectem automaticamente as configurações de conexão.</span><span class="sxs-lookup"><span data-stu-id="086c3-139">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="086c3-140">Para obter mais informações, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="086c3-140">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="086c3-141">**Automático** – Use um arquivo de configuração para definir o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="086c3-141">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="086c3-142">Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="086c3-142">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="086c3-143">**Usar servidor proxy** – Habilite essa opção se você quiser inserir manualmente as configurações do servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="086c3-143">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="086c3-144">**Endereço** – Insira o endereço do servidor proxy (como um endereço IP).</span><span class="sxs-lookup"><span data-stu-id="086c3-144">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="086c3-145">**Número da porta** – Insira o número de porta associado ao servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="086c3-145">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="086c3-146">**Bypass de proxy para endereços locais** – Se o servidor VPN exigir um servidor proxy para a conexão, selecione essa opção se não quiser usar o servidor proxy para endereços locais que você especificar.</span><span class="sxs-lookup"><span data-stu-id="086c3-146">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="086c3-147">Para obter mais informações, consulte a documentação do Windows Server.</span><span class="sxs-lookup"><span data-stu-id="086c3-147">For more information, see your Windows Server documentation.</span></span>
