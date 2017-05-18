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
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 0f192c0e41cf3b639cbfdac3f8c4fc3b8167266d
ms.lasthandoff: 04/25/2017


---

# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Bloquear aplicativos que não usam autenticação moderna (ADAL)

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O acesso condicional baseado em aplicativo com políticas de proteção de aplicativo depende de aplicativos usando a [autenticação moderna](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) que é uma implementação do OAuth2. Os aplicativos do Office mais recentes, tanto os móveis como os de área de trabalho, usam autenticação moderna; no entanto, há aplicativos de terceiros e aplicativos do Office mais antigos que usam outros métodos de autenticação, como autenticação básica e autenticação baseada em formulários.

Para bloquear o acesso a esses aplicativos, recomendamos o seguinte:

* Configure as regras de declarações do ADFS para bloquear protocolos de autenticação não moderna. Instruções detalhadas são fornecidas no cenário 3 – [bloquear todo o acesso ao O365, exceto aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).
* Para o **SharePoint Online**, desabilite a autenticação não moderna no serviço SharePoint Online usando o commandlet do PowerShell [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) para definir a propriedade dos protocolos de autenticação herdados como falso:

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false

```


>[!IMPORTANT]
>O AC baseado em aplicativo não deve ser usado com a autenticação baseada em certificado do Azure AD (Azure Active Directory). Só é possível ter um deles configurado de cada vez.

### <a name="see-also"></a>Consulte também
[Permitir que somente aplicativos em que há suporte para o Intune acessem os serviços do O365](allow-policy-managed-apps-access-to-o365.md)

