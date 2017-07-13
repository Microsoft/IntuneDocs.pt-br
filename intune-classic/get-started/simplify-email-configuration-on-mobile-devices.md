---
title: "Simplificar a configuração de email em dispositivos móveis"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 12/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1696c715-1e9a-401e-a530-77904fd189ad
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2fe65f3021596390af8262f83704d6e4ceaa1716
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="1e960-102">Guia de início rápido: Simplificar a configuração de email em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="1e960-102">Quick Start Guide: Simplify email configuration on mobile devices</span></span>
<a id="quick-start-guide-simplify-email-configuration-on-mobile-devices" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1e960-103">O Microsoft Intune economiza tempo e recursos de sua empresa permitindo que você implante perfis de email (bem como VPN e Wi-Fi) para dispositivos móveis Windows, iOS e Android gerenciados pelo serviço Intune.</span><span class="sxs-lookup"><span data-stu-id="1e960-103">Microsoft Intune saves your company time and resources by allowing you to deploy email (as well as VPN and WiFi) profiles to Windows, iOS and Android mobile devices managed by the Intune service.</span></span> <span data-ttu-id="1e960-104">Configurar perfis de email automaticamente pode aprimorar muito a experiência do usuário final e aumentar os níveis de satisfação, ao mesmo tempo em que reduz os custos de suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="1e960-104">Automatically configuring email profiles can greatly improve the end-user experience and increase satisfaction levels while at the same time reduce your helpdesk costs.</span></span>

## <span data-ttu-id="1e960-105">Este é o guia de início rápido certo para mim?</span><span class="sxs-lookup"><span data-stu-id="1e960-105">Is this quick start guide right for me?</span></span>
<a id="is-this-quick-start-guide-right-for-me" class="xliff"></a>
<span data-ttu-id="1e960-106">Você gostaria de reduzir o tempo e esforço que os usuários precisam dispender para definir novos perfis de email em dispositivos móveis enquanto também aumenta a segurança dos dados da empresa, permitindo que apenas dispositivos móveis gerenciados pelo Intune acessem o email da empresa?</span><span class="sxs-lookup"><span data-stu-id="1e960-106">Would like to reduce the time and effort required by your users to configure new email profiles on mobile devices from while also increasing your company’s data security by only allowing mobile devices managed by Intune to access your company email?</span></span>

<span data-ttu-id="1e960-107">Se sim, o Microsoft Intune poderá configurar automaticamente o email para os dispositivos de seus funcionários gerenciados pelo Intune implantando perfis de email em seus dispositivos para que eles não precisem configurar manualmente o acesso ao email da empresa.</span><span class="sxs-lookup"><span data-stu-id="1e960-107">If yes, Microsoft Intune can automatically configure email for your employees’ Intune-managed devices by deploying email profiles to their devices so that they don’t have to manually configure access to their company email.</span></span> <span data-ttu-id="1e960-108">Essa funcionalidade fornece uma melhor experiência ao usuário final e reduz os custos gerais de assistência técnica, reduzindo o número de encaminhamento de problemas de configuração de email de seus usuários de dispositivos Windows, iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="1e960-108">This capability provides a better end-user experience and reduces overall helpdesk costs by driving down the number of escalations for email configuration issues on your users Windows, iOS, and Android devices.</span></span>

<span data-ttu-id="1e960-109">Depois que o perfil de email é configurado, você pode restringir facilmente o acesso ao email da empresa e a serviços do Office 365 com as políticas de acesso condicional do Intune.</span><span class="sxs-lookup"><span data-stu-id="1e960-109">After the email profile is configured, you can easily restrict access to company email and Office 365 services with Intune conditional access policies.</span></span> <span data-ttu-id="1e960-110">Essas políticas permitem que você certifique-se de que o acesso ao seu email da empresa e serviços Office 365 seja restrito aos dispositivos que são compatíveis com as regras que você definir no Intune.</span><span class="sxs-lookup"><span data-stu-id="1e960-110">These policies allow you to make sure that access to your company email and Office 365 services is restricted to devices that are compliant with the rules that you set in Intune.</span></span>

## <span data-ttu-id="1e960-111">Como fazer isso?</span><span class="sxs-lookup"><span data-stu-id="1e960-111">How do I do it?</span></span>
<a id="how-do-i-do-it" class="xliff"></a>
1.  <span data-ttu-id="1e960-112">[Configure perfis de email do usuário final](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) automaticamente em dispositivos Windows, iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="1e960-112">Automatically [configure end-user email profiles](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) on Windows, iOS, and Android devices.</span></span>
2.  <span data-ttu-id="1e960-113">[Controle o acesso ao email da empresa](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) usando políticas de acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="1e960-113">[Control access to company email](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) using conditional access policies.</span></span>


### <span data-ttu-id="1e960-114">Informação adicional:</span><span class="sxs-lookup"><span data-stu-id="1e960-114">Additional information:</span></span>
<a id="additional-information" class="xliff"></a>
[<span data-ttu-id="1e960-115">Segurança e configurações de dispositivos do Intune</span><span class="sxs-lookup"><span data-stu-id="1e960-115">Intune device settings and security</span></span>](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)

## <span data-ttu-id="1e960-116">O que devo fazer em seguida?</span><span class="sxs-lookup"><span data-stu-id="1e960-116">What should I do next?</span></span>
<a id="what-should-i-do-next" class="xliff"></a>
[<span data-ttu-id="1e960-117">Implantar perfis VPN para dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="1e960-117">Deploy VPN profiles to managed devices</span></span>](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)

[<span data-ttu-id="1e960-118">Implantar perfis Wi-Fi para dispositivos gerenciados</span><span class="sxs-lookup"><span data-stu-id="1e960-118">Deploy Wi-Fi profiles to managed devices</span></span>](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)

[<span data-ttu-id="1e960-119">Proteger o acesso a recursos com perfis de certificado no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1e960-119">Secure resource access with certificate profiles in Microsoft Intune</span></span>](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)
