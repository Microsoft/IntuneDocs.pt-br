---
title: Como atribuir aplicativos a grupos | Microsoft Docs
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: depois de adicionar um aplicativo ao Intune, ele deverá ser atribuído a grupos de usuários ou dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 1246ef539c044b894b4e4a93f449e60e6462600a
ms.contentlocale: pt-br
ms.lasthandoff: 05/23/2017

---

# <a name="how-to-assign-apps-to-groups-with-microsoft-intune"></a>Como atribuir aplicativos a grupos com o Microsoft Intune

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Depois de adicionar um aplicativo ao Intune, ele deverá ser distribuído para usuários e dispositivos. Para fazer isso, atribua-o.

Aplicativos podem ser atribuídos aos dispositivos sejam eles gerenciados pelo Intune ou não. Use a tabela a seguir para ajudar a compreender as várias opções para atribuir aplicativos a usuários e dispositivos:

||||
|-|-|-|-|
|&nbsp;|Dispositivos registrados com o Intune|Dispositivos não registrados com o Intune|
|Atribuir a usuários|Sim|Sim|
|Atribuir a dispositivos|Sim|Não|
|Atribuir aplicativos encapsulados ou aqueles que incorporam o SDK do Intune (para políticas de proteção de aplicativo)|Sim|Sim|
|Atribuir aplicativos conforme a disponibilidade|Sim|Sim|
|Atribuir aplicativos conforme necessário|Sim|Não|
|Desinstalar aplicativos|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do aplicativo de Portal da Empresa|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web|Sim|Sim|

> [!NOTE]
> No momento, é possível atribuir aplicativos iOS e Android (tanto linha de negócios quanto comprados na loja) a dispositivos que não são registrados com o Intune.

## <a name="changes-to-how-you-assign-apps-to-groups-in-the-intune-preview"></a>Mudanças na forma de atribuir aplicativos a grupos na visualização do Intune

Na visualização do Intune Azure, você não usa mais os grupos do Intune para atribuir aplicativos, agora você usa os grupos de segurança do Azure AD (Azure Active Directory). Por isso, você precisará conhecer algumas alterações para a forma como as atribuições do aplicativo funcionam, particularmente quando tiver atribuído aplicativos a grupos filho do Intune.
O mais importante a ser observado é que o conceito de grupos filho não existe no Azure AD. No entanto, alguns grupos podem conter os mesmos membros. Nesse caso, o comportamento entre o Intune clássico e a visualização do Intune Azure é diferente. A tabela a seguir ilustra isso:

||||||
|-|-|-|-|-|
|**Intune clássico (antes da migração de locatário)**|-|**Intune Azure (após locatário migração ser concluída)**|-|**Mais informações**|
|**Intenção de atribuição de grupo pai**|**Intenção de atribuição de grupo filho**|**Tentativa de atribuição resultante para membros comuns do grupo pai e filho anterior**|**Ação de tentativa de atribuição resultante para membros do grupo pai**|-|
|Disponível|Necessária|Necessária e Disponível|Disponível|Necessária e Disponível significa que os aplicativos atribuídos conforme necessário também podem ser vistos no aplicativo Portal da Empresa.
|Não Aplicável|Disponível|Não Aplicável|Não Aplicável|Solução alternativa: remova a tentativa de atribuição 'Não Aplicável' do grupo pai do Intune.
|Necessária|Disponível|Necessária e Disponível|Necessária|-|
|Necessária e Disponível<sup>1</sup>|Disponível|Necessária e Disponível|Necessária e Disponível|-|
|Necessária|Não Aplicável|Necessária|Necessária|-|
|Necessária e Disponível|Não Aplicável|Necessária e Disponível|Necessária e Disponível|-|
|Necessária|Desinstalar|Necessária|Necessária|-|
|Necessária e Disponível|Desinstalar|Necessária e Disponível|Necessária e Disponível|-|
<sup>1</sup> Apenas para aplicativos da iOS Store gerenciados, quando você os adiciona ao Intune e os atribui como Necessários, eles são criados automaticamente com as tentativas Necessária e Disponível.

Você pode executar as seguintes ações para evitar conflitos de atribuição:

1.    Se você tiver atribuído aplicativos para grupos pai e filho do Intune relacionados, considere remover essas atribuições antes de começar a migração do locatário.
2.    Remover grupos filho de grupos pai e criar um novo grupo que contém os membros do grupo filho antigo. Você pode, então, criar uma nova atribuição de aplicativo para esse grupo.
Observações: se o grupo pai anterior era "Todos os Usuários", você precisará criar um novo grupo dinâmico que não inclui membros do grupo filho.
É necessário fazer alterações em grupos no [Portal do Azure](https://portal.azure.com/) para grupos de usuários e de dispositivos. O [Portal Clássico do Azure](https://manage.windowsazure.com/) permitirá que você faça alterações apenas em grupos de usuários.


## <a name="how-to-assign-an-app"></a>Como atribuir um aplicativo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Aplicativos móveis**.
1. Na carga de trabalho **Aplicativos Móveis**, escolha **Gerenciar** > **Aplicativos**.
2. Na folha da lista de aplicativos, escolha o aplicativo que você deseja atribuir.
3. Na folha <*nome do aplicativo*> – **Visão Geral**, escolha **Gerenciar** > **Atribuições**.
4. Escolha **Selecionar Grupos** e, na folha **Selecionar grupos**, escolha os grupos do Azure AD aos quais você deseja atribuir o aplicativo.
5. Para cada aplicativo que você escolher, selecione um **tipo de atribuição** para o aplicativo dentre:
    - **Disponível** – Os usuários instalam o aplicativo no site ou aplicativo do Portal da Empresa.
    - **Não Aplicável** – O aplicativo não é instalado nem é mostrado no Portal da Empresa.
    - **Obrigatório** – O aplicativo é instalado nos dispositivos dos grupos selecionados.
    - **Desinstalar** – O aplicativo é desinstalado dos dispositivos nos grupos selecionados.
    - **Disponível com ou sem registro** – Atribua este aplicativo a grupos de usuários cujos dispositivos não são registrados com o Intune. Consulte a tabela acima para obter ajuda.
6. Quando terminar, escolha **Salvar**.

Agora, o aplicativo foi atribuído ao grupo escolhido.

Consulte [Como monitorar aplicativos](apps-monitor.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.

