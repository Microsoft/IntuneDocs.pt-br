---
title: Acesso Condicional baseado no aplicativo com o Intune
titleSuffix: Microsoft Intune
description: Saiba como funciona o Acesso Condicional baseado no aplicativo no Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/11/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 46ff51c872c2e8c87d044bde3c262203d5f55e8e
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71723054"
---
# <a name="app-based-conditional-access-with-intune"></a>Acesso Condicional baseado no aplicativo com o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

As [políticas de Proteção de Aplicativo do Intune](../apps/app-protection-policy.md) ajudam a proteger os dados da empresa nos dispositivos registrados no Intune. Use também as políticas de proteção de aplicativo em dispositivos dos funcionários que não estão registrados no gerenciamento do Intune. Nesse caso, mesmo que sua empresa não gerencie o dispositivo, ainda é necessário verificar se os dados e recursos da empresa estão protegidos.

O Acesso Condicional baseado no aplicativo e o gerenciamento de aplicativo cliente adicionam uma camada de segurança, garantindo que apenas os aplicativos cliente que são compatíveis com as políticas de proteção de aplicativo do Intune possam acessar o Exchange Online e outros serviços do Office 365.

> [!NOTE]
> Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativo aplicadas e que pode ser gerenciado pelo Intune.

Será possível bloquear os aplicativos de email internos no iOS e no Android quando você permitir que apenas o aplicativo Microsoft Outlook acesse o Exchange Online. Além disso, bloqueie o acesso ao SharePoint Online por aplicativos que não têm as políticas de Proteção de Aplicativo do Intune aplicadas.

## <a name="prerequisites"></a>Pré-requisitos
Antes de criar uma política de Acesso Condicional baseado no aplicativo é necessário ter:

- **Enterprise Mobility + Security (EMS)** ou um **assinatura Premium do Azure Active Directory (AAD)**
- Os usuários devem estar licenciados para usar o EMS ou o Azure AD

Para saber mais, confira os [preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou os [preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

## <a name="supported-apps"></a>Aplicativos com suporte

Para ver uma lista de aplicativos compatíveis com Acesso Condicional baseado no aplicativo, confira [Documentação técnica de referência sobre Acesso Condicional do Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)

O Acesso Condicional baseado no aplicativo [também é compatível com aplicativos de linha de negócios](app-modern-authentication-block.md), mas esses aplicativos precisam usar a [autenticação moderna do Office 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a). 

## <a name="how-app-based-conditional-access-works"></a>Como funciona o Acesso Condicional baseado no aplicativo

Neste exemplo, o administrador aplicou políticas de proteção de aplicativo ao aplicativo Outlook, seguidas por uma regra de Acesso Condicional que adiciona o aplicativo Outlook a uma lista aprovada de aplicativos que podem ser usados ao acessar o email corporativo.

> [!NOTE]
> A estrutura de fluxograma abaixo pode ser usada para outros aplicativos gerenciados.

![Processo de Acesso Condicional baseado no aplicativo ilustrado em um fluxograma](./media/app-based-conditional-access-intune/ca-intune-common-ways-3.png)

1. O usuário tenta se autenticar no Azure AD por meio do aplicativo Outlook.

2. O usuário é redirecionado para a loja de aplicativos para instalar um aplicativo agente ao tentar se autenticar pela primeira vez. O aplicativo agente pode ser o Microsoft Authenticator para iOS ou o portal da Empresa da Microsoft para dispositivos Android.

   Se os usuários tentarem usar um aplicativo de email nativo, eles serão redirecionados para a loja de aplicativos para, em seguida, instalarem o aplicativo Outlook.

3. O aplicativo agente é instalado no dispositivo.

4. O aplicativo agente inicia o processo de registro do Azure AD que cria um registro de dispositivo no Azure AD. Isso não é o mesmo que o processo de registro do MDM (gerenciamento de dispositivo móvel), mas esse registro é necessário para que as políticas de Acesso Condicional possam ser impostas no dispositivo.

5. O aplicativo agente verifica a identidade do aplicativo. Há uma camada de segurança para que o aplicativo agente possa validar se o aplicativo está autorizado a ser usado pelo usuário.

6. O aplicativo agente envia a ID do Cliente do Aplicativo para o Azure AD como parte do processo de autenticação do usuário para verificar se ele está na lista aprovada de políticas.

7. O Azure AD permite ao usuário se autenticar e usar o aplicativo com base na lista aprovada de políticas. Se o aplicativo não estiver na lista, o Azure AD negará o acesso ao aplicativo.

8. O aplicativo Outlook se comunica com o Serviço de Nuvem do Outlook para iniciar a comunicação com o Exchange Online.

9. O Serviço de Nuvem do Outlook se comunica com o Azure AD para recuperar o token de acesso do serviço Exchange Online para o usuário.

10. O aplicativo Outlook se comunica com o Exchange Online para recuperar o email corporativo do usuário.

11. O email corporativo é entregue à caixa de correio do usuário.

## <a name="next-steps"></a>Próximas etapas
[Criar uma política de Acesso Condicional baseado no aplicativo](app-based-conditional-access-intune-create.md)

[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)