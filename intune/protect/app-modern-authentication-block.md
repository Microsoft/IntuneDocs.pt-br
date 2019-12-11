---
title: Bloquear aplicativos sem autenticação moderna no Intune
titleSuffix: Microsoft Intune
description: Saiba mais sobre os aplicativos e a autenticação moderna (ADAL) que usam o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/15/2019
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 81c7746985bd3449ce4e5f2d90780bcd117069eb
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72509666"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Bloquear aplicativos que não usam autenticação moderna (ADAL)

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

O Acesso Condicional baseado em aplicativo com as políticas de proteção de aplicativo depende de aplicativos que usam a [autenticação moderna](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), que é uma implementação do OAuth2. Atualmente, a maioria dos aplicativos móveis e para desktop do Office usa autenticação moderna. No entanto, há aplicativos de terceiros e aplicativos do Office mais antigos que usam outros métodos de autenticação, como autenticação básica e autenticação baseada em formulários.

## <a name="block-access-to-apps"></a>Bloquear o acesso a aplicativos

Para bloquear o acesso a aplicativos que não usam a autenticação moderna, use as políticas de proteção do aplicativo do Intune para implementar a condição de acesso. Saiba mais em [Acesso Condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Informações adicionais

Saiba mais sobre o Acesso Condicional do Azure AD nos tópicos a seguir:
- [O que é o Acesso Condicional no Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Como funciona o Acesso Condicional baseado no aplicativo](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Configurar o SharePoint Online e o Exchange Online para Acesso Condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Próximas etapas

- [Acesso Condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
