---
title: "Defesa contra Ameaças Móveis com o Intune"
titleSuffix: Intune Azure preview
description: Proteger o acesso a recursos da empresa com base nos riscos do dispositivo
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec45b9445f2737ad99852ebf46cc40c03537a2e5
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="0f4ad-103">Integração da Defesa contra Ameaças Móveis com o Intune</span><span class="sxs-lookup"><span data-stu-id="0f4ad-103">Mobile Threat Defense integration with Intune</span></span>
<a id="mobile-threat-defense-integration-with-intune" class="xliff"></a>


<span data-ttu-id="0f4ad-104">Os conectores de Defesa Contra Ameaças Móveis do Intune permitem que você utilize o fornecedor de Defesa Contra Ameaças Móveis escolhido como uma fonte de informações para suas políticas de conformidade e regras de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-104">Intune Mobile Threat Defense connectors allow you to leverage your chosen Mobile Threat Defense vendor as a source of information for your compliance policies and conditional access rules.</span></span> <span data-ttu-id="0f4ad-105">Isso permite que os administradores de TI adicionem uma camada de proteção aos seus recursos corporativos como Exchange e Sharepoint, especificamente de dispositivos móveis comprometidos.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-105">This allows IT Administrators to add a layer of protection to their corporate resources such as Exchange and Sharepoint, specifically from compromised mobile devices.</span></span>

## <span data-ttu-id="0f4ad-106">Que problema isso resolve?</span><span class="sxs-lookup"><span data-stu-id="0f4ad-106">What problem does this solve?</span></span>
<a id="what-problem-does-this-solve" class="xliff"></a>

<span data-ttu-id="0f4ad-107">As empresas precisam proteger dados confidenciais contra ameaças emergentes, incluindo ameaças físicas, baseadas em aplicativo e em rede, bem como vulnerabilidades do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-107">Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.</span></span>
<span data-ttu-id="0f4ad-108">Historicamente, as empresas têm sido proativas ao proteger computadores contra ataques, enquanto os dispositivos móveis ficam sem monitoramento e sem proteção.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-108">Historically, companies have been proactive when protecting PCs from attack, while mobile devices go un-monitored and unprotected.</span></span> <span data-ttu-id="0f4ad-109">Plataformas móveis têm proteção interna, como isolamento de aplicativo e lojas de aplicativos de consumidor verificadas, mas permanecerão vulneráveis a ataques sofisticados.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-109">Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks.</span></span> <span data-ttu-id="0f4ad-110">Hoje, um número maior de funcionários usa dispositivos para o trabalho e precisam ter acesso a informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-110">Today, more employees use devices for work and need access to sensitive information.</span></span> <span data-ttu-id="0f4ad-111">Os dispositivos precisam ser protegidos contra ataques cada vez mais sofisticados.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-111">Devices need to be protected from increasingly sophisticated attacks.</span></span>

## <span data-ttu-id="0f4ad-112">Como os conectores de Defesa Contra Ameaças Móveis do Intune funciona?</span><span class="sxs-lookup"><span data-stu-id="0f4ad-112">How the Intune Mobile Threat Defense connectors work?</span></span>
<a id="how-the-intune-mobile-threat-defense-connectors-work" class="xliff"></a>

<span data-ttu-id="0f4ad-113">O conector protege os recursos da empresa criando um canal de comunicação entre o Intune e seu fornecedor de Defesa Contra Ameaças Móveis escolhido.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-113">The connector protects company resources by creating a channel of communication between Intune and your chosen Mobile Threat Defense vendor.</span></span> <span data-ttu-id="0f4ad-114">Os parceiros de Defesa Contra Ameaças Móveis do Intune oferecem aplicativos intuitivos e fáceis de implantar para dispositivos móveis que ativamente examinam e analisam as informações sobre ameaças para compartilhar com o Intune, para fins de relatório ou imposição.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-114">Intune Mobile Threat Defense partners offer intuitive, easy to deploy applications for mobile devices which actively scan and analyze threat information to share with Intune, for either reporting or enforcement purposes.</span></span> <span data-ttu-id="0f4ad-115">Por exemplo, se um aplicativo de Defesa Contra Ameaças Móveis relata para o fornecedor de Defesa Contra Ameaças Móveis que um telefone em sua rede atualmente está conectado a uma rede vulnerável a ataques Man in the Middle, essas informações são compartilhadas e categorizadas em um nível de risco adequado (baixo/médio/alto), que pode então ser comparado às tolerâncias de nível de risco configuradas no Intune para determinar se o acesso a determinados recursos de sua escolha deve ser revogado enquanto o dispositivo está comprometido.</span><span class="sxs-lookup"><span data-stu-id="0f4ad-115">For example, if a connected Mobile Threat Defense app reports to the Mobile Threat Defense vendor that a phone on your network is currently connected to a network which is vulnerable to Man in the Middle attacks, this information is shared with and categorized to an appropriate risk level (low/medium/high) – which can then be compared with your configured risk level allowances in Intune to determine if access to certain resources of your choice should be revoked while the device is compromised.</span></span>

## <span data-ttu-id="0f4ad-116">Cenários de exemplo</span><span class="sxs-lookup"><span data-stu-id="0f4ad-116">Sample scenarios</span></span>
<a id="sample-scenarios" class="xliff"></a>

<span data-ttu-id="0f4ad-117">Quando um dispositivo é considerado infectado pela solução de Defesa Contra Ameaças Móveis:</span><span class="sxs-lookup"><span data-stu-id="0f4ad-117">When a device is considered infected by the Mobile Threat Defense solution:</span></span>

![Dispositivo infectado na Defesa contra Ameaças Móveis](./media/MTD-image-1.png)

<span data-ttu-id="0f4ad-119">O acesso é concedido quando o dispositivo é corrigido:</span><span class="sxs-lookup"><span data-stu-id="0f4ad-119">Access is granted when the device is remediated:</span></span>

![Acesso concedido na Defesa contra Ameaças Móveis](./media/MTD-image-2.png)

## <span data-ttu-id="0f4ad-121">Parceiros de Defesa Contra Ameaças Móveis</span><span class="sxs-lookup"><span data-stu-id="0f4ad-121">Mobile Threat Defense partners</span></span>
<a id="mobile-threat-defense-partners" class="xliff"></a>

<span data-ttu-id="0f4ad-122">Saiba como proteger o acesso a recursos da empresa com base em riscos de dispositivo, rede e aplicativo com:</span><span class="sxs-lookup"><span data-stu-id="0f4ad-122">Learn how to protect access to company resource based on device, network, and application risk with:</span></span>

- [<span data-ttu-id="0f4ad-123">Lookout</span><span class="sxs-lookup"><span data-stu-id="0f4ad-123">Lookout</span></span>](lookout-mobile-threat-defense-connector.md)
- [<span data-ttu-id="0f4ad-124">Skycure</span><span class="sxs-lookup"><span data-stu-id="0f4ad-124">Skycure</span></span>](skycure-mobile-threat-defense-connector.md)