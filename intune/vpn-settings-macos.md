---
title: "Configurações de VPN do Intune para dispositivos macOS"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos macOS."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 83e3776aacbddc37e5e7586d8fd7580143dead64
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="fca52-103">Configurações de VPN para dispositivos macOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fca52-103">VPN settings for macOS devices in Microsoft Intune</span></span>
<a id="vpn-settings-for-macos-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="fca52-104">Dependendo das configurações escolhidas, nem todos os valores na lista abaixo serão configuráveis.</span><span class="sxs-lookup"><span data-stu-id="fca52-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <span data-ttu-id="fca52-105">**Configurações de VPN de base**</span><span class="sxs-lookup"><span data-stu-id="fca52-105">**Base VPN settings**</span></span>
<a id="base-vpn-settings" class="xliff"></a>

<span data-ttu-id="fca52-106">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="fca52-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="fca52-107">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="fca52-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="fca52-108">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="fca52-108">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="fca52-109">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="fca52-109">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="fca52-110">**Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:</span><span class="sxs-lookup"><span data-stu-id="fca52-110">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="fca52-111">**Certificados** – Em **Certificado de autenticação**, escolha um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="fca52-111">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="fca52-112">Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="fca52-112">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="fca52-113">**Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="fca52-113">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="fca52-114">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="fca52-114">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="fca52-115">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="fca52-115">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="fca52-116">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="fca52-116">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="fca52-117">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="fca52-117">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="fca52-118">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="fca52-118">**F5 Edge Client**</span></span>
    - <span data-ttu-id="fca52-119">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="fca52-119">**Pulse Secure**</span></span>
    - <span data-ttu-id="fca52-120">**VPN personalizado**</span><span class="sxs-lookup"><span data-stu-id="fca52-120">**Custom VPN**</span></span>
- <span data-ttu-id="fca52-121">**Túnel dividido** - **Habilitar** ou **Desabilitar** essa opção que permite que os dispositivos decidam qual conexão usar dependendo do tráfego.</span><span class="sxs-lookup"><span data-stu-id="fca52-121">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="fca52-122">Por exemplo, um usuário em um hotel usará a conexão VPN para acessar arquivos de trabalho, porém usará a rede padrão do hotel para navegação regular na Web.</span><span class="sxs-lookup"><span data-stu-id="fca52-122">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <span data-ttu-id="fca52-123">Configurações de VPN personalizado</span><span class="sxs-lookup"><span data-stu-id="fca52-123">Custom VPN settings</span></span>
<a id="custom-vpn-settings" class="xliff"></a>

<span data-ttu-id="fca52-124">Se você selecionou **VPN Personalizada**, defina essas configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="fca52-124">If you selected **Custom VPN**, configure these further settings:</span></span>

- <span data-ttu-id="fca52-125">**Identificador de VPN** Este é um identificador para o aplicativo VPN que você está usando e é fornecido pelo seu provedor VPN.</span><span class="sxs-lookup"><span data-stu-id="fca52-125">**VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.</span></span>
- <span data-ttu-id="fca52-126">**Digite os pares de chave-valor para os atributos personalizados de VPN** Adicione ou importe as **Chaves** e os **Valores** que personalizam sua conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="fca52-126">**Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection.</span></span> <span data-ttu-id="fca52-127">Novamente, esses valores geralmente são fornecidos pelo seu provedor de VPN.</span><span class="sxs-lookup"><span data-stu-id="fca52-127">Again, these values are typically supplied by your VPN provider.</span></span>


## <span data-ttu-id="fca52-128">Configurações de proxy</span><span class="sxs-lookup"><span data-stu-id="fca52-128">Proxy settings</span></span>
<a id="proxy-settings" class="xliff"></a>

- <span data-ttu-id="fca52-129">**Automático** – Use um arquivo de configuração para definir o servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="fca52-129">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="fca52-130">Digite a **URL do servidor proxy** (por exemplo **http://proxy.contoso.com**) que contém o arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="fca52-130">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="fca52-131">**Endereço** – Insira o endereço do servidor proxy (como um endereço IP).</span><span class="sxs-lookup"><span data-stu-id="fca52-131">**Address** - Enter the proxy server address (as an IP address).</span></span>
- <span data-ttu-id="fca52-132">**Número da porta** – Insira o número de porta associado ao servidor proxy.</span><span class="sxs-lookup"><span data-stu-id="fca52-132">**Port number** - Enter the port number associated with the proxy server.</span></span>
