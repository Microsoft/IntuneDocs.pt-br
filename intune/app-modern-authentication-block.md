---
title: Bloquear aplicativos sem autenticação moderna no Intune
titleSuffix: Microsoft Intune
description: Saiba mais sobre o aplicativo e a autenticação moderna (ADAL) usando o Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/03/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.topic: conceptual
ms.technology: ''
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9ca96f36f8813d80c7ebb07bfb3bd65f8aa0b392
ms.sourcegitcommit: 71314481e644025c005019b478b4cbeaf2390ea9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59569097"
---
# <a name="block-apps-that-dont-use-modern-authentication-adal"></a>Bloquear aplicativos que não usam autenticação moderna (ADAL)

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

O acesso condicional baseado em aplicativo com as políticas de proteção de aplicativo depende de aplicativos que usam a [autenticação moderna](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a), que é uma implementação do OAuth2. Atualmente, a maioria dos aplicativos móveis e para desktop do Office usa autenticação moderna. No entanto, há aplicativos de terceiros e aplicativos do Office mais antigos que usam outros métodos de autenticação, como autenticação básica e a autenticação baseada em formulários.

## <a name="block-access-to-apps"></a>Bloquear o acesso a aplicativos

Para bloquear o acesso a aplicativos que não usam a autenticação moderna, use as políticas de proteção do aplicativo do Intune para implementar a condição de acesso. Saiba mais em [Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md).

## <a name="additional-information"></a>Informações adicionais

Saiba mais sobre o Acesso Condicional do Azure AD nos tópicos a seguir:
- [O que é o acesso condicional no Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
- [Como funciona o acesso condicional baseado no aplicativo](app-based-conditional-access-intune.md#how-app-based-conditional-access-works)
- [Configurar o SharePoint Online e o Exchange Online para acesso condicional do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/conditional-access-for-exo-and-spo)

## <a name="next-steps"></a>Próximas etapas

- [Acesso condicional baseado no aplicativo com o Intune](app-based-conditional-access-intune.md)
