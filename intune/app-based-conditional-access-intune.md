---
title: Acesso condicional baseado no aplicativo com o Intune
description: Saiba como o acesso condicional baseado no aplicativo funciona no Intune.
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 604eb86e6ae712bac360ecf45dd8f20e611bc52a
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="app-based-conditional-access-with-intune"></a>Acesso condicional baseado no aplicativo com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As [políticas de Proteção de Aplicativo do Intune](app-protection-policy.md) ajudam a proteger os dados da empresa nos dispositivos registrados no Intune. Use também as políticas de proteção de aplicativo em dispositivos dos funcionários que não estão registrados no gerenciamento do Intune. Nesse caso, mesmo que sua empresa não gerencie o dispositivo, ainda é necessário verificar se os dados e recursos da empresa estão protegidos.

O acesso condicional baseado no aplicativo e o gerenciamento de aplicativo móvel adicionam uma camada de segurança, garantindo que apenas os aplicativos móveis que dão suporte às políticas de proteção de aplicativo do Intune podem acessar o Exchange Online e outros serviços do Office 365.

> [!NOTE]
> Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativo aplicadas e que pode ser gerenciado pelo Intune.

Será possível bloquear os aplicativos de email internos no iOS e no Android quando você permitir que apenas o aplicativo Microsoft Outlook acesse o Exchange Online. Além disso, bloqueie o acesso ao SharePoint Online por aplicativos que não têm as políticas de Proteção de Aplicativo do Intune aplicadas.

## <a name="prerequisites"></a>Pré-requisitos
Antes de criar uma política de acesso condicional baseado no aplicativo, é necessário ter:

- **Enterprise Mobility + Security (EMS)** ou um **assinatura Premium do Azure Active Directory (AAD)**
- Os usuários devem estar licenciados para usar o EMS ou o Azure AD

Para obter mais detalhes, consulte os [preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou os [preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

## <a name="supported-apps"></a>Aplicativos com suporte

Para ver uma lista de aplicativos compatíveis com acesso condicional baseado em aplicativo, confira [Documentação técnica de referência sobre acesso condicional do Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)

O acesso condicional baseado no aplicativo [também dá suporte a aplicativos LOB](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), mas esses aplicativos precisam usar a [autenticação moderna do Office 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).

## <a name="how-app-based-conditional-access-works"></a>Como funciona o acesso condicional baseado no aplicativo

Neste exemplo, o administrador aplicou políticas de proteção de aplicativo ao aplicativo Outlook seguidas por uma regra de acesso condicional que adiciona o aplicativo Outlook a uma lista aprovada de aplicativos que podem ser usados ao acessar o email corporativo.

> [!NOTE]
> A estrutura de fluxograma abaixo pode ser usada para outros aplicativos gerenciados.

![Processo de acesso condicional baseado no aplicativo ilustrado em um fluxograma](./media/ca-intune-common-ways-3.png)

1.  O usuário tenta se autenticar no Azure AD por meio do aplicativo Outlook.

2.  O usuário é redirecionado para a loja de aplicativos para instalar um aplicativo agente ao tentar se autenticar pela primeira vez. O aplicativo agente pode ser o Microsoft Authenticator para iOS ou o portal da Empresa da Microsoft para dispositivos Android.

 Se os usuários tentarem usar um aplicativo de email nativo, eles serão redirecionados para a loja de aplicativos para, em seguida, instalarem o aplicativo Outlook.

3.  O aplicativo agente é instalado no dispositivo.

4.  O aplicativo agente inicia o processo de registro do Azure AD que cria um registro de dispositivo no Azure AD. Isso não é o mesmo que o processo de registro do MDM (gerenciamento de dispositivo móvel), mas esse registro é necessário para que as políticas de acesso condicional possam ser impostas no dispositivo.

5.  O aplicativo agente verifica a identidade do aplicativo. Há uma camada de segurança para que o aplicativo agente possa validar se o aplicativo está autorizado a ser usado pelo usuário.

6.  O aplicativo agente envia a ID do Cliente do Aplicativo para o Azure AD como parte do processo de autenticação do usuário para verificar se ele está na lista aprovada de políticas.

7.  O Azure AD permite ao usuário se autenticar e usar o aplicativo com base na lista aprovada de políticas. Se o aplicativo não estiver na lista, o Azure AD negará o acesso ao aplicativo.

8.  O aplicativo Outlook se comunica com o Serviço de Nuvem do Outlook para iniciar a comunicação com o Exchange Online.

9.  O Serviço de Nuvem do Outlook se comunica com o Azure AD para recuperar o token de acesso do serviço Exchange Online para o usuário.

10.  O aplicativo Outlook se comunica com o Exchange Online para recuperar o email corporativo do usuário.

11.  O email corporativo é entregue à caixa de correio do usuário.

## <a name="next-steps"></a>Próximas etapas
[Criar uma política de acesso condicional baseado no aplicativo](app-based-conditional-access-intune-create.md)

[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)
