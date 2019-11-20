---
title: Configurar política de Acesso Condicional baseada em aplicativo com o Microsoft Intune
titleSuffix: Microsoft Intune
description: Saiba como criar uma política de Acesso Condicional baseada em aplicativo com o Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/06/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 465f8b0001e5e2a049a3ffe12469bdb5057854ec
ms.sourcegitcommit: 28622c5455adfbce25a404de4d0437fa2b5370be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73712844"
---
# <a name="set-up-app-based-conditional-access-policies-with-intune"></a>Configurar políticas de Acesso Condicional baseadas em aplicativo com o Microsoft Intune

Configure políticas de Acesso Condicional baseadas em aplicativo para aplicativos que fazem parte da lista de aplicativos aprovados. A lista de aplicativos aprovados consiste em aplicativos que foram testados pela Microsoft.

Para usar políticas de Acesso Condicional baseadas em aplicativo, é necessário configurar [Políticas da proteção de aplicativo do Intune](../apps/app-protection-policies.md) para os aplicativos.

> [!IMPORTANT]
> Este artigo explica as etapas para adicionar uma política de Acesso Condicional baseada em aplicativo. Você pode usar as mesmas etapas ao adicionar aplicativos como o SharePoint Online, o Microsoft Teams e o Microsoft Exchange Online da lista de aplicativos aprovados.

## <a name="create-app-based-conditional-access-policies"></a>Criar políticas de Acesso Condicional baseadas em aplicativo

O Acesso Condicional é uma tecnologia do Azure AD (Azure Active Directory). O nó de Acesso condicional acessado no *Intune* é o mesmo nó acessado no *Azure AD*. Por ser o mesmo nó, você não precisa alternar entre o Intune e o Azure AD para configurar políticas.

Antes de poder criar políticas de Acesso Condicional do Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft, você deve ter uma licença Azure AD Premium.

### <a name="to-create-an-app-based-conditional-access-policy"></a>Para criar uma política de Acesso Condicional baseada em aplicativo

1. Entrar no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431)

2. Selecione **Segurança de ponto de extremidade** > **Acesso condicional** > **Nova política**.

3. Insira **Nome** da política e em *Atribuições*, selecione **Usuários e grupos**. Use as opções Incluir ou Excluir para adicionar os grupos para a política e selecione **Concluído**.

4. Selecione **Aplicativos de nuvem ou ações** e escolha quais aplicativos proteger. Por exemplo, escolha **Selecionar aplicativos** e selecione **Office 365 SharePoint Online** e **Exchange Online do Office 365**.

   Selecione **Concluído** para salvar suas alterações.

5. Selecione **Condições** > **Aplicativos do cliente** para aplicar a política para aplicativos e navegadores. Por exemplo, selecione **Sim** e, em seguida, habilitar **Navegador** e **Aplicativos móveis e clientes de área de trabalho**.

   Selecione **Concluído** para salvar suas alterações.

6. Em *Controle de acesso*, selecione **Conceder** para aplicar Acesso Condicional baseado na conformidade do dispositivo. Por exemplo, selecione **Conceder acesso** > **Exigir que o dispositivo seja marcado como compatível**.

   Marque **Selecionar** para salvar suas alterações.

7. Para **Habilitar a política**, selecione **Ativado** e **Criar** para salvar as alterações.





## <a name="next-steps"></a>Próximas etapas
[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)

## <a name="see-also"></a>Consulte também

[Proteger dados de aplicativo com políticas de proteção de aplicativo](../apps/app-protection-policies.md)
[Acesso condicional no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
