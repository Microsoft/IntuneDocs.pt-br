---
title: "Configurações de Wi-Fi do Intune para dispositivos Android"
titleSuffix: Intune on Azure
description: "Saiba mais sobre como o Intune define as configurações de conexão Wi-Fi em dispositivos Android e Android for Work."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8e1c64730dc8bb91a0fe5e7936ed963d67be1feb
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d2eaf-103">Configurações de Wi-Fi para dispositivos Android e Android for Work no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d2eaf-103">Wi-Fi settings for Android and Android for Work devices in Microsoft Intune</span></span>
<a id="wi-fi-settings-for-android-and-android-for-work-devices-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <span data-ttu-id="d2eaf-104">Configurações Wi-Fi para perfis básico e empresarial</span><span class="sxs-lookup"><span data-stu-id="d2eaf-104">Wi-Fi settings for basic and enterprise profiles</span></span>
<a id="wi-fi-settings-for-basic-and-enterprise-profiles" class="xliff"></a>

<span data-ttu-id="d2eaf-105">As seguintes configurações de Wi-Fi estão disponíveis para dispositivos Android e Android for Work:</span><span class="sxs-lookup"><span data-stu-id="d2eaf-105">The following Wi-Fi settings are available for both Android and Android for Work devices:</span></span>

- <span data-ttu-id="d2eaf-106">**Nome da rede** – Insira um nome para esta conexão Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-106">**Network name** - Enter a name for this Wi-Fi connection.</span></span> <span data-ttu-id="d2eaf-107">Esse é o nome que os usuários verão ao navegarem pela lista de conexões disponíveis no seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-107">This is the name that users will see when they browse the list of available connections on their device.</span></span>
- <span data-ttu-id="d2eaf-108">**SSID** – Abreviação de identificador de conjunto de serviço (service set identifier em inglês).</span><span class="sxs-lookup"><span data-stu-id="d2eaf-108">**SSID** - Short for service set identifier.</span></span> <span data-ttu-id="d2eaf-109">Esse é o nome real da rede sem fio à qual os dispositivos se conectarão.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-109">This is the real name of the wireless network that devices will connect to.</span></span> <span data-ttu-id="d2eaf-110">No entanto, os usuários veem apenas o nome de rede criado anteriormente ao escolher a conexão.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-110">However, users only see the network name you created above when they choose the connection.</span></span>
- <span data-ttu-id="d2eaf-111">**Conectar-se automaticamente** – Faz com que o dispositivo se conecte sempre que estiver no intervalo da rede.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-111">**Connect automatically** - Makes the device connect whenever it is in the range of this network.</span></span>
- <span data-ttu-id="d2eaf-112">**Rede oculta** – Impede que essa rede seja exibida na lista de redes disponíveis no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-112">**Hidden network** - Prevents this network from being shown in the list of available networks on the device.</span></span>


## <span data-ttu-id="d2eaf-113">Configurações Wi-Fi para apenas para perfis empresariais</span><span class="sxs-lookup"><span data-stu-id="d2eaf-113">Wi-Fi settings for enterprise profiles only</span></span>
<a id="wi-fi-settings-for-enterprise-profiles-only" class="xliff"></a>

- <span data-ttu-id="d2eaf-114">**Tipo de EAP** – Escolha o tipo de Protocolo EAP (Extensible Authentication Protocol) usado para autenticar as conexões sem fio seguras:</span><span class="sxs-lookup"><span data-stu-id="d2eaf-114">**EAP type** - Choose the Extensible Authentication Protocol (EAP) type used to authenticate secured wireless connections from:</span></span>
    - <span data-ttu-id="d2eaf-115">**EAP-TLS**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-115">**EAP-TLS**</span></span>
    - <span data-ttu-id="d2eaf-116">**EAP-TTLS**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-116">**EAP-TTLS**</span></span>
    - <span data-ttu-id="d2eaf-117">**PEAP**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-117">**PEAP**</span></span>

### <span data-ttu-id="d2eaf-118">Opções adicionais ao escolher um tipo de EAP</span><span class="sxs-lookup"><span data-stu-id="d2eaf-118">Further options when you choose an EAP type</span></span>
<a id="further-options-when-you-choose-an-eap-type" class="xliff"></a>

#### <span data-ttu-id="d2eaf-119">Confiança do Servidor</span><span class="sxs-lookup"><span data-stu-id="d2eaf-119">Server Trust</span></span>
<a id="server-trust" class="xliff"></a>



|<span data-ttu-id="d2eaf-120">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="d2eaf-120">Setting name</span></span>|<span data-ttu-id="d2eaf-121">Mais informações</span><span class="sxs-lookup"><span data-stu-id="d2eaf-121">More information</span></span>|<span data-ttu-id="d2eaf-122">Usar quando</span><span class="sxs-lookup"><span data-stu-id="d2eaf-122">Use when</span></span>|
|-------------|---------------|-----------|
|<span data-ttu-id="d2eaf-123">**Nomes de servidor de certificados**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-123">**Certificate server names**</span></span>|<span data-ttu-id="d2eaf-124">Especifique um ou mais nomes comuns usados nos certificados emitidos pela sua AC (autoridade de certificação) confiável.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-124">Specify one or more common names used in the certificates issued by your trusted certificate authority (CA).</span></span> <span data-ttu-id="d2eaf-125">Se você fornecer essas informações, poderá fazer o bypass da caixa de diálogo de confiança dinâmica que é exibida em dispositivos de usuários finais quando eles se conectam à rede Wi-Fi.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-125">If you provide this information, you can bypass the dynamic trust dialog that is displayed on end users devices when they connect to this Wi-Fi network.</span></span>|<span data-ttu-id="d2eaf-126">O tipo EAP é **EAP-TLS** ou **EAP-TTLS**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-126">EAP type is **EAP-TLS** or **EAP-TTLS**</span></span>|
|<span data-ttu-id="d2eaf-127">**Certificado raiz para validação do servidor**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-127">**Root certificate for server validation**</span></span>|<span data-ttu-id="d2eaf-128">Escolha o perfil de certificado raiz confiável usado para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-128">Choose the trusted root certificate profile used to authenticate the connection.</span></span> |<span data-ttu-id="d2eaf-129">O tipo de EAP é **EAP-TLS**, **EAP-TTLS** ou **PEAP**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-129">EAP type is **EAP-TLS**, **EAP-TTLS**, or **PEAP**</span></span>|
|<span data-ttu-id="d2eaf-130">**Privacidade de identidade (identidade externa)**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-130">**Identity privacy (outer identity)**</span></span>|<span data-ttu-id="d2eaf-131">Especifique o texto enviado em resposta a uma solicitação de identidade de EAP.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-131">Specify the text sent in response to an EAP identity request.</span></span> <span data-ttu-id="d2eaf-132">Esse texto pode ser qualquer valor.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-132">This text can be any value.</span></span> <span data-ttu-id="d2eaf-133">Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-133">During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.</span></span>|<span data-ttu-id="d2eaf-134">O tipo de EAP é **PEAP**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-134">EAP type is **PEAP**</span></span>|


#### <span data-ttu-id="d2eaf-135">Autenticação do Cliente</span><span class="sxs-lookup"><span data-stu-id="d2eaf-135">Client Authentication</span></span>
<a id="client-authentication" class="xliff"></a>


|<span data-ttu-id="d2eaf-136">Nome da configuração</span><span class="sxs-lookup"><span data-stu-id="d2eaf-136">Setting name</span></span>|<span data-ttu-id="d2eaf-137">Mais informações</span><span class="sxs-lookup"><span data-stu-id="d2eaf-137">More information</span></span>|<span data-ttu-id="d2eaf-138">Usar quando</span><span class="sxs-lookup"><span data-stu-id="d2eaf-138">Use when</span></span>|
|----------|--------------|----------|
|<span data-ttu-id="d2eaf-139">**Certificado de cliente para autenticação de cliente (Certificado de identidade)**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-139">**Client certificate for client authentication (Identity certificate)**</span></span>|<span data-ttu-id="d2eaf-140">Escolha o perfil de certificado SCEP ou PKCS usado para autenticar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-140">Choose the SCEP or PKCS certificate profile used to authenticate the connection.</span></span>|<span data-ttu-id="d2eaf-141">O tipo de EAP é **EAP-TLS**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-141">EAP type is **EAP-TLS**</span></span>|
|<span data-ttu-id="d2eaf-142">**Método de autenticação**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-142">**Authentication method**</span></span>|<span data-ttu-id="d2eaf-143">Selecione o método de autenticação para a conexão:</span><span class="sxs-lookup"><span data-stu-id="d2eaf-143">Select the authentication method for the connection:</span></span><br><span data-ttu-id="d2eaf-144">- **Certificados** para selecionar o certificado cliente SCEP ou PKCS que é o certificado de identidade apresentado ao servidor.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-144">- **Certificates** to select the SCEP or PKCS the client certificate that is the identity certificate presented to the server.</span></span><br><br><span data-ttu-id="d2eaf-145">- **Nome de Usuário e Senha** para especificar um método de autenticação diferente.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-145">- **Username and Password** to specify a different method for authentication.</span></span> <br><br><span data-ttu-id="d2eaf-146">Se você selecionou **Nome de Usuário e Senha**, configure:</span><span class="sxs-lookup"><span data-stu-id="d2eaf-146">If you selected **Username and Password**, configure:</span></span><br><br><span data-ttu-id="d2eaf-147">-  **Método não EAP (identidade interna)**, em seguida, selecione como você autenticará a conexão de:</span><span class="sxs-lookup"><span data-stu-id="d2eaf-147">-  **Non-EAP method (inner identity)**, then select how you will authenticate the connection from:</span></span><br><span data-ttu-id="d2eaf-148">- **Nenhum**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-148">- **None**</span></span><br><span data-ttu-id="d2eaf-149">- **Senha não criptografada (PAP)**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-149">- **Unencrypted password (PAP)**</span></span><br><span data-ttu-id="d2eaf-150">- **Protocolo CHAP**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-150">- **Challenge Handshake Authentication Protocol (CHAP)**</span></span><br><span data-ttu-id="d2eaf-151">- **Microsoft CHAP (MS-CHAP)**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-151">- **Microsoft CHAP (MS-CHAP)**</span></span><br><span data-ttu-id="d2eaf-152">- **Microsoft CHAP Versão 2 (MS-CHAP v2)**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-152">- **Microsoft CHAP Version 2 (MS-CHAP v2)**</span></span><br><span data-ttu-id="d2eaf-153">As opções disponíveis dependem do tipo de EAP selecionado.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-153">The available options depend on the EAP type you selected.</span></span><br><br><span data-ttu-id="d2eaf-154">**e**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-154">**and**</span></span><br><br><span data-ttu-id="d2eaf-155">- **Privacidade de identidade (identidade externa)** – Especifique o texto enviado em resposta a uma solicitação de identidade de EAP.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-155">- **Identity privacy (outer identity)** - Specify the text sent in response to an EAP identity request.</span></span> <span data-ttu-id="d2eaf-156">Esse texto pode ser qualquer valor.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-156">This text can be any value.</span></span> <span data-ttu-id="d2eaf-157">Durante a autenticação, essa identidade anônima é enviada inicialmente e seguida pela identificação real enviada em um túnel seguro.</span><span class="sxs-lookup"><span data-stu-id="d2eaf-157">During authentication, this anonymous identity is initially sent, and then followed by the real identification sent in a secure tunnel.</span></span>|<span data-ttu-id="d2eaf-158">O tipo de EAP é **EAP-TTLS** ou **PEAP**</span><span class="sxs-lookup"><span data-stu-id="d2eaf-158">EAP type is **EAP-TTLS** or **PEAP**</span></span>|
