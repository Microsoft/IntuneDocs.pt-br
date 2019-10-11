---
title: Configurar política de Acesso Condicional baseada em aplicativo com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba como criar uma política de Acesso Condicional baseada em aplicativo com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d9cbe57d0cf69f036cd36d2c1b95c48b198645e7
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723080"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Configurar políticas de Acesso Condicional baseadas em aplicativo com o Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Configure políticas de Acesso Condicional baseadas em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

> [!IMPORTANT]
> Este artigo explica as etapas para adicionar uma política de Acesso Condicional baseada em aplicativo. Você pode usar as mesmas etapas ao adicionar aplicativos como o SharePoint Online, o Microsoft Teams e o Microsoft Exchange Online da lista de aplicativos aprovados.

## <a name="create-app-based-conditional-access-policies"></a>Criar políticas de Acesso Condicional baseadas em aplicativo
O Acesso Condicional é uma tecnologia do Azure AD (Azure Active Directory). O nó Acesso Condicional acessado no *Intune* é o mesmo nó que o acessado no *Azure AD*. Isso significa que você não precisa alternar entre o Intune e o Azure AD para configurar políticas.

> [!IMPORTANT]
> É necessário ter uma licença do Azure AD Premium para criar políticas de Acesso Condicional no Portal do Intune.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Para criar uma política de Acesso Condicional baseada em aplicativo

> [!IMPORTANT]
> É necessário ter [políticas da Proteção de Aplicativo do Intune](../apps/app-protection-policies.md) aplicadas aos aplicativos para usar políticas de Acesso Condicional baseadas em aplicativo.

1. No **Painel do Intune**, selecione **Acesso condicional**.

2. No painel **Políticas**, escolha **Nova política** para criar a nova política de Acesso Condicional baseada em aplicativo.

4. Depois de inserir um nome para a política e definir as configurações disponíveis na seção **Atribuições**, escolha **Conceder** na seção **Controles de acesso**.

5. Escolha **Exigir o aplicativo do cliente aprovado**, escolha **Selecionar** e, em seguida, escolha **Criar** para salvar a nova política.

## <a name="next-steps"></a>Próximas etapas
[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)

## <a name="see-also"></a>Consulte também

[Proteger dados de aplicativo com políticas de proteção de aplicativo](../apps/app-protection-policies.md)
[Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
