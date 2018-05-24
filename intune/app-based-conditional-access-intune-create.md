---
title: Configurar política de acesso condicional baseada em aplicativo com o Intune
description: Saiba como criar uma política de acesso condicional baseada em aplicativo com o Intune.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 05/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c505e881fe06d6f4da217533d0507731ac22a29f
ms.sourcegitcommit: 698bd1488be3a269bb88c077eb8d99df6e552a9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Configurar políticas de acesso condicional baseadas em aplicativo com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Este artigo descreve como configurar políticas de acesso condicional baseadas em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

> [!IMPORTANT]
> Este artigo explica as etapas para adicionar uma política de acesso condicional com base no aplicativo. Observe que você pode usar as mesmas etapas ao adicionar aplicativos como o SharePoint Online, Microsoft Teams e Microsoft Exchange Online da lista de aplicativos aprovados.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Criar políticas de acesso condicional baseadas em aplicativo em cargas de trabalho do Azure AD

Os administradores de TI podem criar políticas de acesso condicional com base no aplicativo usando a carga de trabalho do Azure AD. Esse recurso traz facilidade, pois você não precisa alternar entre as cargas de trabalho do Azure e do Intune.

> [!IMPORTANT]
> Você precisa ter uma licença Premium do Azure AD para criar políticas de acesso condicional do Azure AD no portal do Intune no Azure.

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
