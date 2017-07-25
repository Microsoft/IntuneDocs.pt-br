---
title: Acesso condicional baseado no aplicativo com o Intune
description: Entenda os conceitos de como o acesso condicional baseado no aplicativo funciona com o Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0893d511c73e4154c61063d96e26937ea2825467
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Acesso condicional baseado no aplicativo com o Intune
<a id="app-based-conditional-access-with-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

As [políticas de Proteção de Aplicativo do Intune](app-protection-policy.md) ajudam a proteger os dados da empresa nos dispositivos registrados no Intune. Use também as políticas de proteção de aplicativo em dispositivos dos funcionários que não estão registrados no gerenciamento do Intune. Nesse caso, mesmo que sua empresa não gerencie o dispositivo, ainda é necessário verificar se os dados e recursos da empresa estão protegidos.

O acesso condicional baseado no aplicativo e o gerenciamento de aplicativo móvel adicionam uma camada de segurança garantindo que apenas os aplicativos móveis que dão suporte às políticas de Proteção de Aplicativo do Intune podem acessar o Exchange Online e outros serviços do Office 365.

> [!NOTE]
> Um aplicativo gerenciado é um aplicativo que tem políticas de proteção de aplicativo aplicadas e que pode ser gerenciado pelo Intune.

Você poderá bloquear os aplicativos de email internos no iOS e no Android quando permitir que apenas o aplicativo Microsoft Outlook acesse o Exchange Online. Além disso, bloqueie o acesso ao SharePoint Online por aplicativos que não têm as políticas de Proteção de Aplicativo do Intune aplicadas.

## Pré-requisitos
<a id="prerequisites" class="xliff"></a>
Antes de criar uma política de acesso condicional baseado no aplicativo, você deve ter:

- Uma **assinatura do Enterprise Mobility + Security ou do Azure Active Directory Premium** e os usuários devem ser licenciados para o EMS ou o Azure AD.
    - Para obter mais detalhes, veja a [página de preços do Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) ou a [página de preços do Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).

## Aplicativos com suporte
<a id="supported-apps" class="xliff"></a>

- **Exchange Online**:
    - Microsoft Outlook para Android e iOS.
<br></br>
- **SharePoint Online**
    - Microsoft Word para iOS e Android
    - Microsoft Excel para iOS e Android
    - Microsoft PowerPoint para iOS e Android
    - Microsoft OneDrive para Empresas para iOS e Android
    - Microsoft OneNote para iOS
<br></br>
- **Microsoft Teams**

    > [!NOTE] 
    > O acesso condicional baseado no aplicativo [também dá suporte a aplicativos LOB](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), mas esses aplicativos precisam usar a [autenticação moderna do Office 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).

## Como funciona o acesso condicional baseado no aplicativo
<a id="how-app-based-conditional-access-works" class="xliff"></a>

Neste exemplo, o administrador tem políticas de proteção de aplicativo aplicadas ao aplicativo Outlook seguidas por uma regra de acesso condicional que adiciona o aplicativo Outlook a uma lista aprovada de aplicativos que podem ser usados ao acessar o email corporativo.

> [!NOTE] 
> A estrutura de fluxograma abaixo pode ser usada para outros aplicativos gerenciados.

![Fluxograma da AC baseada no aplicativo com o Intune](./media/ca-intune-common-ways-3.png)

1.  O usuário tenta se autenticar no Azure AD por meio do aplicativo Outlook.

2.  O usuário é redirecionado para a loja de aplicativos para instalar um aplicativo agente ao tentar se autenticar pela primeira vez. O aplicativo agente pode ser o Microsoft Authenticator para iOS ou o portal da Empresa da Microsoft para dispositivos Android.

    > [!NOTE]
    > Nesse cenário, se os usuários tentarem usar um aplicativo de email nativo, eles serão redirecionados para a loja de aplicativos para, em seguida, instalarem o aplicativo Outlook.

3.  O aplicativo agente é instalado no dispositivo.

4.  O aplicativo agente inicia o processo de registro do Azure AD que cria um registro de dispositivo no Azure AD. Isso não é o mesmo que o processo de registro do MDM (gerenciamento de dispositivo móvel), mas esse registro é necessário para que as políticas de acesso condicional possam ser impostas no dispositivo.

5.  O aplicativo agente verifica a identidade do aplicativo. Há uma camada de segurança para que o aplicativo agente possa validar se o aplicativo está autorizado a ser usado pelo usuário.

6.  O aplicativo agente envia a ID do Cliente do Aplicativo para o Azure AD como parte do processo de autenticação do usuário para verificar se ele está na lista aprovada de políticas.

7.  O Azure AD permite ao usuário se autenticar e usar o aplicativo com base na lista aprovada de políticas. Se o aplicativo não estiver na lista aprovada de políticas, o Azure AD negará o acesso ao aplicativo.

8.  O aplicativo Outlook se comunica com o Serviço de Nuvem do Outlook para iniciar a comunicação com o Exchange Online.

9.  O Serviço de Nuvem do Outlook se comunica com o Azure AD para recuperar o token de acesso do serviço Exchange Online para o usuário.

10.  O aplicativo Outlook se comunica com o Exchange Online para recuperar o email corporativo do usuário.

11.  O email corporativo é entregue à caixa de correio do usuário.

## Próximas etapas
<a id="next-steps" class="xliff"></a>
[Criar uma política de acesso condicional baseado no aplicativo](app-based-conditional-access-intune-create.md)

[Bloquear aplicativos que não têm autenticação moderna](app-modern-authentication-block.md)
