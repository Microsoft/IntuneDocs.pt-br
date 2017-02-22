---
title: "Como atribuir aplicativos a grupos | Versão prévia do Intune Azure | Microsoft Docs"
description: "Versão prévia do Intune Azure: depois de adicionar um aplicativo ao Intune, ele deverá ser atribuído a grupos de usuários ou dispositivos."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc349e22-9e1c-42ba-9e70-fb2ef980ef7a
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 424fae862592c1ab5b4221fb5ad40a52c39f6760
ms.openlocfilehash: 145f27e44d57e0f5ff7bbed76e14db713dd75286

---

# <a name="how-to-assign-apps-to-groups"></a>Como atribuir aplicativos aos grupos

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

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
|Desinstalar aplicativos|Sim|Sim|
|Os usuários finais instalam aplicativos disponíveis do aplicativo de Portal da Empresa|Sim|Não|
|Os usuários finais instalam aplicativos disponíveis do Portal da Empresa baseado na Web|Sim|Sim|

> [!NOTE]
> No momento, é possível atribuir aplicativos iOS e Android (tanto linha de negócios quanto comprados na loja) a dispositivos que não são registrados com o Intune.

## <a name="how-to-assign-an-app"></a>Como atribuir um aplicativo

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Gerenciar aplicativos**.
1. Na carga de trabalho **Gerenciar Aplicativos**, escolha **Gerenciar** > **Aplicativos**.
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

Consulte [Como monitorar aplicativos](monitor-apps.md) para obter informações para ajudá-lo a monitorar as atribuições de aplicativo.



<!--HONumber=Feb17_HO1-->


