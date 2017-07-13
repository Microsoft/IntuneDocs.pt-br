---
title: "Bloquear aplicativos sem autenticação moderna"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 098b652c-01e0-45d1-a731-620b0d3dc7c1
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0f192c0e41cf3b639cbfdac3f8c4fc3b8167266d
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <span data-ttu-id="d5412-102">Bloquear aplicativos que não usam autenticação moderna (ADAL)</span><span class="sxs-lookup"><span data-stu-id="d5412-102">Block apps that do not use modern authentication (ADAL)</span></span>
<a id="block-apps-that-do-not-use-modern-authentication-adal" class="xliff"></a>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="d5412-103">O acesso condicional baseado em aplicativo com políticas de proteção de aplicativo depende de aplicativos usando a [autenticação moderna](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) que é uma implementação do OAuth2.</span><span class="sxs-lookup"><span data-stu-id="d5412-103">App-based conditional access with app protection policies rely on applications using [modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) which is an implementation of OAuth2.</span></span> <span data-ttu-id="d5412-104">Os aplicativos do Office mais recentes, tanto os móveis como os de área de trabalho, usam autenticação moderna; no entanto, há aplicativos de terceiros e aplicativos do Office mais antigos que usam outros métodos de autenticação, como autenticação básica e autenticação baseada em formulários.</span><span class="sxs-lookup"><span data-stu-id="d5412-104">Most current Office mobile and desktop applications use modern authentication, however there are third-party apps and older Office apps that user other authentication methods like basic authentication and forms based authentication.</span></span>

<span data-ttu-id="d5412-105">Para bloquear o acesso a esses aplicativos, recomendamos o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d5412-105">To block access to these apps we recommend the following:</span></span>

* <span data-ttu-id="d5412-106">Configure as regras de declarações do ADFS para bloquear protocolos de autenticação não moderna.</span><span class="sxs-lookup"><span data-stu-id="d5412-106">Set up ADFS claims rules to block non-modern authentication protocols.</span></span> <span data-ttu-id="d5412-107">Instruções detalhadas são fornecidas no cenário 3 – [bloquear todo o acesso ao O365, exceto aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).</span><span class="sxs-lookup"><span data-stu-id="d5412-107">Detailed instructions are provided in scenario 3 - [block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>
* <span data-ttu-id="d5412-108">Para o **SharePoint Online**, desabilite a autenticação não moderna no serviço SharePoint Online usando o commandlet do PowerShell [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) para definir a propriedade dos protocolos de autenticação herdados como falso:</span><span class="sxs-lookup"><span data-stu-id="d5412-108">For **SharePoint Online**, disable non-modern authentication in the SharePoint Online service using the PowerShell commandlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) to set the legacy authentication protocols property to false:</span></span>

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
><span data-ttu-id="d5412-109">O AC baseado em aplicativo não deve ser usado com a autenticação baseada em certificado do Azure AD (Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="d5412-109">App-based CA must not be used with Azure Active Directory (Azure AD) certificate based authentication.</span></span> <span data-ttu-id="d5412-110">Só é possível ter um deles configurado de cada vez.</span><span class="sxs-lookup"><span data-stu-id="d5412-110">You can only have one of these configured at a time.</span></span>

### <span data-ttu-id="d5412-111">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d5412-111">See also</span></span>
<a id="see-also" class="xliff"></a>
[<span data-ttu-id="d5412-112">Permitir que somente aplicativos em que há suporte para o Intune acessem os serviços do O365</span><span class="sxs-lookup"><span data-stu-id="d5412-112">Allow only apps supported by Intune to access O365 services</span></span>](allow-policy-managed-apps-access-to-o365.md)
