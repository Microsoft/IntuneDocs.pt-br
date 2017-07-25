---
title: "Integração de controle de acesso de rede com o Intune"
titleSuffix: Intune on Azure
description: "Integração de NAC (controle de acesso de rede) com o Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6037ec4638b487c0bae8fcecf2d9bd010e3bc59a
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2017
---
<<<<<<< HEAD
# <span data-ttu-id="185bd-103">Integração de NAC (controle de acesso de rede) com o Intune</span><span class="sxs-lookup"><span data-stu-id="185bd-103">Network access control (NAC) integration with Intune</span></span>
<a id="network-access-control-nac-integration-with-intune" class="xliff"></a>

<span data-ttu-id="185bd-104">O Intune se integra com os parceiros de controle de acesso de rede para ajudar as organizações a proteger dados corporativos quando os dispositivos tentam acessar os recursos locais.</span><span class="sxs-lookup"><span data-stu-id="185bd-104">Intune integrates with network access control partners to help organizations secure corporate data when devices try to access on-premises resources.</span></span>

## <span data-ttu-id="185bd-105">Como soluções do Intune e de NAC ajudam a proteger os recursos de sua organização?</span><span class="sxs-lookup"><span data-stu-id="185bd-105">How do Intune and NAC solutions help protect your organization resources?</span></span>
<a id="how-do-intune-and-nac-solutions-help-protect-your-organization-resources" class="xliff"></a>

<span data-ttu-id="185bd-106">Soluções NAC serão responsáveis por verificar o estado de conformidade e de registro do dispositivo com o Intune para tomar decisões de controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="185bd-106">NAC solutions are responsible for checking the device enrollment and compliance state with Intune to make access control decisions.</span></span> <span data-ttu-id="185bd-107">Se o dispositivo não estiver registrado ou se estiver registrado e não for compatível com políticas de conformidade do dispositivo do Intune, o dispositivo deve ser redirecionado para o Intune para registro e/ou verificação de conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="185bd-107">If the device is not enrolled or is enrolled and not compliant with Intune device compliance policies, the device should be redirected to Intune for enrollment and/or for a device compliance check.</span></span>

### <span data-ttu-id="185bd-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="185bd-108">Example</span></span>
<a id="example" class="xliff"></a>

<span data-ttu-id="185bd-109">Se o dispositivo for registrado e estiver em conformidade com o Intune, a solução NAC deverá permitir que o dispositivo acesse os recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="185bd-109">If the device is enrolled and compliant with Intune, the NAC solution should allow the device access to corporate resources.</span></span> <span data-ttu-id="185bd-110">Por exemplo, o acesso dos usuários pode ser permitido ou negado ao tentar acessar os recursos de VPN ou Wi-Fi corporativo.</span><span class="sxs-lookup"><span data-stu-id="185bd-110">For example, users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources.</span></span>

## <span data-ttu-id="185bd-111">NAC e acesso condicional</span><span class="sxs-lookup"><span data-stu-id="185bd-111">NAC and conditional access</span></span>
<a id="nac-and-conditional-access" class="xliff"></a>

<span data-ttu-id="185bd-112">O NAC trabalha junto com o acesso condicional para fornecer as decisões de controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="185bd-112">NAC works with with conditional access to provide access control decisions.</span></span>

- <span data-ttu-id="185bd-113">Consulte [maneiras de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="185bd-113">See [common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md) for more details.</span></span>

## <span data-ttu-id="185bd-114">Como funciona a integração de NAC</span><span class="sxs-lookup"><span data-stu-id="185bd-114">How the NAC integration works</span></span>
<a id="how-the-nac-integration-works" class="xliff"></a>

<span data-ttu-id="185bd-115">Veja essa visão geral de como a integração de NAC funciona quando integrado com o Intune, as três primeiras etapas explicam o processo de integração.</span><span class="sxs-lookup"><span data-stu-id="185bd-115">Here’s an overview on how the NAC integration works when integrated with Intune, the first three steps explain the onboarding process.</span></span> <span data-ttu-id="185bd-116">Depois que a solução de NAC é integrada com o Intune, as etapas 4 a 9 descrevem a operação em andamento.</span><span class="sxs-lookup"><span data-stu-id="185bd-116">Once the NAC solution is integrated with Intune, steps 4-9 describe the on-going operation.</span></span>

![Como o NAC funciona com o Intune](./media/ca-intune-common-ways-2.png)

1.  <span data-ttu-id="185bd-118">Registre a solução de parceiro NAC com o AAD (Azure Active Directory) e conceda permissões delegadas para a API de NAC do Intune.</span><span class="sxs-lookup"><span data-stu-id="185bd-118">Register the NAC partner solution with Azure Active Directory (AAD), and grant delegated permissions to the Intune NAC API.</span></span>

2.  <span data-ttu-id="185bd-119">Configure a solução de parceiro NAC com as configurações adequadas, incluindo a URL de descoberta do Intune.</span><span class="sxs-lookup"><span data-stu-id="185bd-119">Configure the NAC partner solution with the appropriate settings including the Intune discovery URL.</span></span>

3.  <span data-ttu-id="185bd-120">Configure a solução de parceiro NAC para autenticação de certificado.</span><span class="sxs-lookup"><span data-stu-id="185bd-120">Configure the NAC partner solution for certificate authentication.</span></span>

4.  <span data-ttu-id="185bd-121">O usuário se conecta ao ponto de acesso Wi-Fi corporativo ou faz uma solicitação de conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="185bd-121">User connects to corporate Wi-Fi access point or makes a VPN connection request.</span></span>

5.  <span data-ttu-id="185bd-122">A solução de parceiro NAC encaminha as informações do dispositivo para o Intune e pergunta ao Intune quais são os estados de conformidade e de registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="185bd-122">NAC partner solution forwards the device information to Intune, and asks Intune about the device enrollment and compliance state.</span></span>

6.  <span data-ttu-id="185bd-123">Se o dispositivo não estiver em conformidade ou não estiver registrado, a solução de parceiro NAC instrui o usuário a registrá-lo ou corrigir a conformidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="185bd-123">If the device is not compliant or not enrolled, the NAC partner solution instructs the user to enroll or fix the device compliance.</span></span>

7.  <span data-ttu-id="185bd-124">O dispositivo tenta verificar novamente a conformidade e/ou o estado do registro.</span><span class="sxs-lookup"><span data-stu-id="185bd-124">The device attempts to re-verify its compliance and/or the enrollment state.</span></span>

8.  <span data-ttu-id="185bd-125">Quando o dispositivo estiver registrado e em conformidade, a solução de parceiro NAC obtém o estado do Intune.</span><span class="sxs-lookup"><span data-stu-id="185bd-125">Once the device is enrolled and compliant, NAC partner solution gets the state from Intune.</span></span>

9.  <span data-ttu-id="185bd-126">A conexão é estabelecida com êxito, permitindo que o dispositivo acesse os recursos corporativos.</span><span class="sxs-lookup"><span data-stu-id="185bd-126">Connection is successfully established which allows the device access to corporate resources.</span></span>

## <span data-ttu-id="185bd-127">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="185bd-127">Next steps</span></span>
<a id="next-steps" class="xliff"></a>

-   [<span data-ttu-id="185bd-128">Integrar o Cisco ISE com o Intune</span><span class="sxs-lookup"><span data-stu-id="185bd-128">Integrate Cisco ISE with Intune</span></span>](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [<span data-ttu-id="185bd-129">Integrar o Citrix NetScaler com o Intune</span><span class="sxs-lookup"><span data-stu-id="185bd-129">Integrate Citrix NetScaler with Intune</span></span>](https://docs.citrix.com/netscaler-gateway/11-1/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [<span data-ttu-id="185bd-130">Integrar o HP Aruba Clear Pass com o Intune</span><span class="sxs-lookup"><span data-stu-id="185bd-130">Integrate HP Aruba Clear Pass with Intune</span></span>](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
=======
# Integração de NAC (controle de acesso de rede) com o Intune
<a id="network-access-control-nac-integration-with-intune" class="xliff"></a>

O Intune se integra com os parceiros de controle de acesso de rede para ajudar as organizações a proteger dados corporativos quando os dispositivos tentam acessar os recursos locais.

## Como soluções do Intune e de NAC ajudam a proteger os recursos de sua organização?
<a id="how-do-intune-and-nac-solutions-help-protect-your-organization-resources" class="xliff"></a>

Soluções NAC serão responsáveis por verificar o estado de conformidade e de registro do dispositivo com o Intune para tomar decisões de controle de acesso. Se o dispositivo não estiver registrado ou se estiver registrado e não for compatível com políticas de conformidade do dispositivo do Intune, o dispositivo deve ser redirecionado para o Intune para registro e/ou verificação de conformidade do dispositivo.

### Exemplo
<a id="example" class="xliff"></a>

Se o dispositivo for registrado e estiver em conformidade com o Intune, a solução NAC deverá permitir que o dispositivo acesse os recursos corporativos. Por exemplo, o acesso dos usuários pode ser permitido ou negado ao tentar acessar os recursos de VPN ou Wi-Fi corporativo.

## NAC e acesso condicional
<a id="nac-and-conditional-access" class="xliff"></a>

O NAC trabalha junto com o acesso condicional para fornecer as decisões de controle de acesso.

- Consulte [maneiras de usar o acesso condicional com o Intune](conditional-access-intune-common-ways-use.md) para obter mais detalhes.

## Como funciona a integração de NAC
<a id="how-the-nac-integration-works" class="xliff"></a>

Veja essa visão geral de como a integração de NAC funciona quando integrado com o Intune, as três primeiras etapas explicam o processo de integração. Depois que a solução de NAC é integrada com o Intune, as etapas 4 a 9 descrevem a operação em andamento.

![Como o NAC funciona com o Intune](./media/ca-intune-common-ways-2.png)

1.  Registre a solução de parceiro NAC com o AAD (Azure Active Directory) e conceda permissões delegadas para a API de NAC do Intune.

2.  Configure a solução de parceiro NAC com as configurações adequadas, incluindo a URL de descoberta do Intune.

3.  Configure a solução de parceiro NAC para autenticação de certificado.

4.  O usuário se conecta ao ponto de acesso Wi-Fi corporativo ou faz uma solicitação de conexão VPN.

5.  A solução de parceiro NAC encaminha as informações do dispositivo para o Intune e pergunta ao Intune quais são os estados de conformidade e de registro do dispositivo.

6.  Se o dispositivo não estiver em conformidade ou não estiver registrado, a solução de parceiro NAC instrui o usuário a registrá-lo ou corrigir a conformidade do dispositivo.

7.  O dispositivo tenta verificar novamente a conformidade e/ou o estado do registro.

8.  Quando o dispositivo estiver registrado e em conformidade, a solução de parceiro NAC obtém o estado do Intune.

9.  A conexão é estabelecida com êxito, permitindo que o dispositivo acesse os recursos corporativos.

## Próximas etapas
<a id="next-steps" class="xliff"></a>

-   [Integrar o Cisco ISE com o Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Integrar o Citrix NetScaler com o Intune](https://docs.citrix.com/netscaler-gateway/11-1/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Integrar o HP Aruba Clear Pass com o Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
>>>>>>> live
