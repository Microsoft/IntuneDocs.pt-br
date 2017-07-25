---
title: "Configurações de VPN do Intune para dispositivos Android"
titleSuffix: Intune on Azure
description: "Conheça as configurações do Intune que você pode usar para configurar as conexões VPN em dispositivos Android"
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 69def564b145e58c2d5b58183e4044ae1997091d
ms.sourcegitcommit: d1ad84edf4f03cb4c11fe55131556b43fc3a4500
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/05/2017
---
<<<<<<< HEAD
# <span data-ttu-id="c38d1-103">Configurações de VPN para dispositivos Android no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c38d1-103">VPN settings for Android devices in Microsoft Intune</span></span>
=======
# Configurações de VPN para dispositivos Android no Microsoft Intune
>>>>>>> live
<a id="vpn-settings-for-android-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<<<<<<< HEAD
<span data-ttu-id="c38d1-104">Como administrador do Intune, você pode definir as configurações de VPN para as seguintes plataformas:</span><span class="sxs-lookup"><span data-stu-id="c38d1-104">As an Intune admin, you can configure VPN settings for the following platforms:</span></span>

- [<span data-ttu-id="c38d1-105">Android</span><span class="sxs-lookup"><span data-stu-id="c38d1-105">Android</span></span>](#android-vpn-settings)
- [<span data-ttu-id="c38d1-106">Android for Work</span><span class="sxs-lookup"><span data-stu-id="c38d1-106">Android for Work</span></span>](#android-for-work-vpn-settings)

<span data-ttu-id="c38d1-107">Dependendo das configurações escolhidas, nem todos os valores listados abaixo serão configuráveis.</span><span class="sxs-lookup"><span data-stu-id="c38d1-107">Depending on the settings you choose, not all values listed below are configurable.</span></span>

## <span data-ttu-id="c38d1-108">Configurações de VPN no Android</span><span class="sxs-lookup"><span data-stu-id="c38d1-108">Android VPN settings</span></span>
<a id="android-vpn-settings" class="xliff"></a>
<span data-ttu-id="c38d1-109">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-109">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="c38d1-110">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c38d1-110">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="c38d1-111">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-111">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="c38d1-112">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="c38d1-112">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="c38d1-113">**Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:</span><span class="sxs-lookup"><span data-stu-id="c38d1-113">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="c38d1-114">**Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-114">**Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="c38d1-115">Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c38d1-115">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="c38d1-116">**Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="c38d1-116">**Username and password** - End users must supply a user name and password to log into the VPN server.</span></span>
- <span data-ttu-id="c38d1-117">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c38d1-117">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="c38d1-118">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="c38d1-118">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="c38d1-119">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="c38d1-119">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="c38d1-120">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="c38d1-120">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="c38d1-121">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="c38d1-121">**F5 Edge Client**</span></span>
    - <span data-ttu-id="c38d1-122">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="c38d1-122">**Pulse Secure**</span></span>
    - <span data-ttu-id="c38d1-123">**Citrix**</span><span class="sxs-lookup"><span data-stu-id="c38d1-123">**Citrix**</span></span>

- <span data-ttu-id="c38d1-124">**Impressão digital** (somente Check Point Capsule VPN) – Especifique uma cadeia de caracteres, (por exemplo "Código de impressões digitais da Contoso") que será usado para verificar se o servidor VPN é confiável.</span><span class="sxs-lookup"><span data-stu-id="c38d1-124">**Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted.</span></span> <span data-ttu-id="c38d1-125">Uma impressão digital pode ser enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que apresentar essa impressão digital durante a conexão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-125">A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting.</span></span> <span data-ttu-id="c38d1-126">Se o dispositivo ainda não tiver a impressão digital, ele solicitará ao usuário que confie no servidor VPN ao qual ele está se conectando enquanto mostra a impressão digital (o usuário verifica a impressão digital manualmente e clica em confiar para se conectar).</span><span class="sxs-lookup"><span data-stu-id="c38d1-126">If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint (The user manually verifies the fingerprint and chooses trust to connect).</span></span>
- <span data-ttu-id="c38d1-127">**Insira os pares chave-valor para os atributos de VPN Citrix** (somente Citrix) – Insira os pares chave-valor fornecidos pela Citrix para configurar as propriedades de conexão de VPN.</span><span class="sxs-lookup"><span data-stu-id="c38d1-127">**Enter key and value pairs for the Citrix VPN attributes** (Citrix only) - Enter key and value pairs, provided by Citrix, to configure the properties of the VPN connection.</span></span>

## <span data-ttu-id="c38d1-128">Configurações de VPN do Android for Work</span><span class="sxs-lookup"><span data-stu-id="c38d1-128">Android for Work VPN settings</span></span>
<a id="android-for-work-vpn-settings" class="xliff"></a>

<span data-ttu-id="c38d1-129">**Nome da conexão** – Insira um nome para esta conexão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-129">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="c38d1-130">Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c38d1-130">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="c38d1-131">**Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-131">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="c38d1-132">Exemplos: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="c38d1-132">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="c38d1-133">**Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:</span><span class="sxs-lookup"><span data-stu-id="c38d1-133">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="c38d1-134">**Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="c38d1-134">**Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="c38d1-135">Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="c38d1-135">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="c38d1-136">**Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.</span><span class="sxs-lookup"><span data-stu-id="c38d1-136">**Username and password** - End users must supply a user name and password to log into the VPN server.</span></span>
- <span data-ttu-id="c38d1-137">**Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c38d1-137">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="c38d1-138">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="c38d1-138">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="c38d1-139">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="c38d1-139">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="c38d1-140">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="c38d1-140">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="c38d1-141">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="c38d1-141">**F5 Edge Client**</span></span>
    - <span data-ttu-id="c38d1-142">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="c38d1-142">**Pulse Secure**</span></span>

- <span data-ttu-id="c38d1-143">**Túnel dividido** – habilite essa opção para permitir que alguns tráfegos da Web usem a conexão VPN quando a VPN, enquanto outros tráfegos usam a Internet.</span><span class="sxs-lookup"><span data-stu-id="c38d1-143">**Split tunneling** - Enable to let certain web traffic use the VPN connection when the VPN while other traffic uses the internet.</span></span> <span data-ttu-id="c38d1-144">Desabilite essa configuração se desejar que todo o tráfego use a VPN quando ela estiver ativa.</span><span class="sxs-lookup"><span data-stu-id="c38d1-144">Disable this setting if you want all traffic to use the VPN when active.</span></span>
=======
Como administrador do Intune, você pode definir as configurações de VPN para as seguintes plataformas:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Dependendo das configurações escolhidas, nem todos os valores listados abaixo serão configuráveis.

## Configurações de VPN no Android
<a id="android-vpn-settings" class="xliff"></a>
**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Impressão digital** (somente Check Point Capsule VPN) – Especifique uma cadeia de caracteres, (por exemplo "Código de impressões digitais da Contoso") que será usado para verificar se o servidor VPN é confiável. Uma impressão digital pode ser enviada ao cliente para que ele saiba que pode confiar em qualquer servidor que apresentar essa impressão digital durante a conexão. Se o dispositivo ainda não tiver a impressão digital, ele solicitará ao usuário que confie no servidor VPN ao qual ele está se conectando enquanto mostra a impressão digital (o usuário verifica a impressão digital manualmente e clica em confiar para se conectar).
- **Insira os pares chave-valor para os atributos de VPN Citrix** (somente Citrix) – Insira os pares chave-valor fornecidos pela Citrix para configurar as propriedades de conexão de VPN.

## Configurações de VPN do Android for Work
<a id="android-for-work-vpn-settings" class="xliff"></a>

**Nome da conexão** – Insira um nome para esta conexão. Usuários finais verão esse nome quando navegarem pela lista de conexões VPN disponíveis em seus dispositivos.
- **Endereço IP ou FQDN** – Forneça o endereço IP ou o nome de domínio totalmente qualificado do servidor VPN ao qual os dispositivos se conectarão. Exemplos: **192.168.1.1**, **vpn.contoso.com**.
- **Método de autenticação** – Escolha como os dispositivos se autenticarão do servidor VPN:
    - **Certificados** – Selecione um perfil de certificado SCEP ou PKCS criado anteriormente para autenticar a conexão. Para obter mais detalhes sobre os perfis de certificado, consulte [Como configurar certificados](certificates-configure.md).
    - **Nome de usuário e senha** – Os usuários finais deverão fornecer um nome de usuário e senha para fazer logon no servidor VPN.
- **Tipo de Conexão** – Selecione o tipo de conexão VPN na lista de fornecedores a seguir:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Túnel dividido** – habilite essa opção para permitir que alguns tráfegos da Web usem a conexão VPN quando a VPN, enquanto outros tráfegos usam a Internet. Desabilite essa configuração se desejar que todo o tráfego use a VPN quando ela estiver ativa.
>>>>>>> live
