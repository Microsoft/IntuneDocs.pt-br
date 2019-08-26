---
title: Políticas de proteção do aplicativo para extensões
titleSuffix: Microsoft Intune
description: Este tópico descreve a APP (política de proteção do aplicativo) para extensões.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: demerson
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: f38f22d7aaf03f278fad86061aa8198c8e37f31f
ms.sourcegitcommit: b1ddc7f4a3d520b7d6755c7a423a46d1e2548592
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69655187"
---
# <a name="protecting-application-extensions"></a>Como proteger as extensões de aplicativo

Este artigo descreve as políticas de proteção do aplicativo para extensões no Microsoft Intune.

## <a name="add-ins-for-outlook-app"></a>Suplementos do aplicativo do Outlook

Os suplementos do Outlook permitem integrar aplicativos populares ao cliente de email. Os suplementos para Outlook estão disponíveis na Web, Windows, Mac e Outlook para Android e iOS. O SDK de APP e as políticas de proteção de aplicativo do Intune não incluem suporte para gerenciamento de suplementos do Outlook, mas há outras maneiras de limitar o uso. Como os suplementos são gerenciados pelo Microsoft Exchange, os usuários poderão compartilhar dados e mensagens entre o Outlook e aplicativos de suplementos não gerenciados, a menos que os suplementos sejam desativados para o usuário pelo Exchange.

Se você quiser impedir que os usuários finais acessem e instalem suplementos do Outlook (isso afeta todos os clientes do Outlook), verifique se você tem as seguintes alterações em funções no Centro de administração do Exchange:

- Para impedir que os usuários instalem os suplementos da Office Store, remova a função My Marketplace deles.
- Para impedir que usuários carreguem suplementos lateralmente, remova a função de Meus Aplicativos Personalizados deles.
- Para impedir que os usuários instalem todo e qualquer suplemento, remova ambas as funções Meus Aplicativos Personalizados e My Marketplace deles.

Essas instruções se aplicam ao Office 365, Exchange 2016 e Exchange 2013 no Outlook na Web, Windows, Mac e dispositivos móveis.

- Saiba mais sobre [suplementos do Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Saiba mais sobre [como especificar os administradores e usuários que podem instalar e gerenciar suplementos para aplicativos do Outlook](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).

## <a name="linkedin-account-connections-for-microsoft-apps"></a>Conexões de conta do LinkedIn para aplicativos da Microsoft

Conexões de conta do LinkedIn permitem que os usuários vejam as informações de perfil do LinkedIn públicas em determinados aplicativos da Microsoft. Por padrão, seus usuários podem optar por conectar as próprias contas corporativas ou de estudante do LinkedIn e da Microsoft para verem informações adicionais do perfil do LinkedIn. 

> [!NOTE]
> A integração do LinkedIn não está disponível no momento para clientes do Governo dos Estados Unidos e para organizações com caixas de correio do Exchange Online hospedadas na Austrália, no Canadá, na China, na França, na Alemanha, na Índia, na Coreia do Sul, no Reino Unido, no Japão e na África do Sul.

O SDK e as políticas de proteção de aplicativo do Intune não incluem suporte para gerenciamento de conexões de conta do LinkedIn, mas há outras maneiras de gerenciá-las. Você pode desabilitar conexões de conta LinkedIn para toda a organização, ou pode habilitar conexões de conta do LinkedIn para grupos de usuários selecionados em sua organização. Essas configurações afetam as conexões do LinkedIn em aplicativos do Office 365 em todas as plataformas (web, móveis e desktop). Você pode:

- Habilitar ou desabilitar conexões de conta do LinkedIn para seu locatário no portal do Azure. 
- Habilitar ou desabilitar conexões de conta do LinkedIn para os aplicativos do Office 2016 da sua organização usando a Política de Grupo.

Se a integração do LinkedIn estiver habilitada para seu locatário, quando os usuários na sua organização conectarem as contas corporativas ou de estudante do LinkedIn e da Microsoft, eles terão duas opções: 

- Poderão dar permissão para compartilhar dados entre as duas contas. Isso significa que eles dão permissão para que a conta do LinkedIn compartilhe dados com a conta corporativa ou de estudante da Microsoft deles, bem como para que a conta corporativa ou de estudante da Microsoft compartilhe dados com a conta do LinkedIn deles. Os dados compartilhados com LinkedIn saem os serviços online. 
- Eles podem dar permissão para compartilhar dados somente da conta do LinkedIn para a conta corporativa e de estudante da Microsoft

Se um usuário concordar em compartilhar dados entre contas, como acontece suplementos do Office, a integração do LinkedIn usará as APIs do Microsoft Graph existentes. A integração do LinkedIn usa apenas um subconjunto das APIs disponíveis para suplementos do Office e é compatível com várias exclusões.


|Permissões do Microsoft Graph  |Descrição  |
|---------|---------|
|Permissões de leitura para [Pessoas](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#people-permissions)     |Permite que o aplicativo leia uma lista classificada de pessoas relevantes para o usuário conectado. A lista pode incluir contatos locais, contatos de redes sociais ou do diretório da sua organização e pessoas de comunicações recentes (como email e Skype).         |
|Permissões de leitura para [Calendários](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#calendars-permissions)     |Permite que o aplicativo leia eventos em calendários do usuário. Inclui as reuniões em calendários do usuário conectado, seus horários, locais e participantes.         |
|Permissões de leitura para [Perfil do Usuário](https://developer.microsoft.com/graph/docs/concepts/permissions_reference#user-permissions)     |Permite que os usuários entrem no aplicativo e que o aplicativo leia o perfil dos usuários conectados. Também permite que o aplicativo leia informações básicas da empresa para usuários conectados.         |
|Subscriptions     |Esse escopo não está disponível e ainda não está em uso. Inclui assinaturas fornecidas pela organização do usuário para aplicativos e serviços da Microsoft, como o Office 365.         |
|Insights     |Esse escopo não está disponível e ainda não está em uso. Inclui os interesses associados à conta do usuário conectado com base no uso de serviços da Microsoft.         |

### <a name="learn-more"></a>Saiba mais

- Saiba mais sobre [Informações e recursos do LinkedIn em seus aplicativos Microsoft](https://go.microsoft.com/fwlink/?linkid=850740).
- Saiba mais sobre a versão de conexões de conta do LinkedIn na [página Roteiro do Office 365](https://products.office.com/en-US/business/office-365-roadmap?filters=%26freeformsearch=linkedin#abc). 
- Saiba mais sobre [Como configurar conexões da conta do LinkedIn](https://docs.microsoft.com/azure/active-directory/linkedin-integration).
- Para obter mais informações sobre os dados compartilhados entre usuários do LinkedIn e contas corporativas ou de estudante da Microsoft, consulte [LinkedIn em aplicativos da Microsoft em sua empresa ou escola](https://www.linkedin.com/help/linkedin/answer/84077).

