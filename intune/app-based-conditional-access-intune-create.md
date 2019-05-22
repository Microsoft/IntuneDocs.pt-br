---
title: Configurar política de acesso condicional baseada em aplicativo com o Intune
titleSuffix: Microsoft Intune
description: Saiba como criar uma política de acesso condicional baseada em aplicativo com o Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1514fe9dfcd09e2b77967b0fed8c36fb7a06634f
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2019
ms.locfileid: "59567485"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Configurar políticas de acesso condicional baseadas em aplicativo com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Configure políticas de acesso condicional com base em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

> [!IMPORTANT]
> Este artigo explica as etapas para adicionar uma política de acesso condicional com base no aplicativo. Você pode usar as mesmas etapas ao adicionar aplicativos como o SharePoint Online, o Microsoft Teams e o Microsoft Exchange Online da lista de aplicativos aprovados.

## <a name="create-app-based-conditional-access-policies"></a>Criar políticas de acesso condicional baseado em aplicativo
O Acesso Condicional é uma tecnologia do Azure AD (Azure Active Directory). O nó Acesso Condicional acessado no *Intune* é o mesmo nó que o acessado no *Azure AD*. Isso significa que você não precisa alternar entre o Intune e o Azure AD para configurar políticas.

> [!IMPORTANT]
> Você precisa ter uma licença do Azure Active Directory Premium para criar políticas de acesso condicional no portal do Intune.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Para criar uma política de acesso condicional baseado no aplicativo

> [!IMPORTANT]
> Você precisa ter [políticas de proteção de aplicativo do Intune](app-protection-policies.md) aplicadas aos seus aplicativos antes de usar políticas de acesso condicional baseadas em aplicativo.

1. No **Painel do Intune**, escolha **Acesso condicional**.

2. No painel **Políticas**, escolha **Nova política** para criar a nova política de acesso condicional baseada em aplicativo.

4. Depois de inserir um nome para a política e definir as configurações disponíveis na seção **Atribuições**, escolha **Conceder** na seção **Controles de acesso**.

5. Escolha **Exigir o aplicativo do cliente aprovado**, escolha **Selecionar** e, em seguida, escolha **Criar** para salvar a nova política.

## <a name="next-steps"></a>Próximas etapas
[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)

### <a name="see-also"></a>Consulte também

[Proteger dados de aplicativo com políticas de proteção de aplicativo](app-protection-policies.md)
[Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
