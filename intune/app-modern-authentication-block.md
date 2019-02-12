---
title: Bloquear aplicativos sem autenticação moderna no Intune
titleSuffix: Microsoft Intune
description: Saiba mais sobre o bloqueio de aplicativos que não usam a autenticação moderna (ADAL) com o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a651f926f8e8cc5beab80a70649c82677e0b2487
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55833045"
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a>Bloquear aplicativos que não usam autenticação moderna (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O acesso condicional baseado em aplicativo com as políticas de proteção de aplicativo depende de aplicativos que usam a [autenticação moderna](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), que é uma implementação do OAuth2. Atualmente, a maioria dos aplicativos móveis e para desktop do Office usa autenticação moderna. No entanto, há aplicativos de terceiros e aplicativos do Office mais antigos que usam outros métodos de autenticação, como autenticação básica e a autenticação baseada em formulários.

## <a name="block-apps"></a>Bloquear aplicativos

Para bloquear o acesso a aplicativos que não usam a autenticação moderna, recomendamos os seguintes métodos:

- Configure as regras de declarações do ADFS para bloquear protocolos de autenticação não moderna. Instruções detalhadas são fornecidas no cenário 3 – [bloquear todo o acesso ao O365, exceto aplicativos baseados em navegador](https://technet.microsoft.com/library/dn592182.aspx).
- Para o **Exchange e o SharePoint Online**, use o Acesso Condicional do Azure Active Directory e use o commandlet Set-SPOTenant do PowerShell para o SharePoint online. Para obter instruções detalhadas, confira [Configurar o SharePoint Online e o Exchange Online para acesso condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-no-modern-authentication#legacy-authentication-protocols).


>[!IMPORTANT]
>O AC baseado em aplicativo não deve ser usado com a autenticação baseada em certificado do Azure AD (Azure Active Directory). Só é possível ter um deles configurado de cada vez.

## <a name="next-steps"></a>Próximas etapas

- [Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
