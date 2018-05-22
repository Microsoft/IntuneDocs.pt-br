---
title: Bloquear aplicativos sem autenticação moderna no Intune
titleSuffix: Microsoft Intune
description: Saiba mais sobre o bloqueio de aplicativos que não usam autenticação moderna (ADAL).
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dcdc7628f75221228d788c2cb1995189ea8f81f0
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Bloquear aplicativos que não usam autenticação moderna (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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
[Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
