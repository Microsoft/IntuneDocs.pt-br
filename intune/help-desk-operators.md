---
title: "Portal de solução de problemas de suporte técnico"
titleSuffix: Intune on Azure
description: "A equipe de suporte técnico usa o portal de solução de problemas para resolver problemas técnicos dos usuários"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 7a61c3703cd1016ef63c8baa371c3a21dca127fc
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# Ajudar os usuários com o portal de solução de problemas no Microsoft Intune
<a id="help-users-with-the-troubleshooting-portal-in-microsoft-intune" class="xliff"></a>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O portal de solução de problemas permite que os operadores de suporte técnico e os administradores do Intune exibam informações do usuário para resolver solicitações de ajuda do usuário. As organizações que incluem operadores de suporte técnico em sua equipe podem atribuir o **Operador do suporte técnico** a um grupo de usuários, o qual poderá usar a folha Solução de Problemas para ajudar os usuários.

Por exemplo, quando um usuário contata o suporte com um problema técnico com o Intune, o operador do suporte técnico digita o nome do usuário. O Intune exibe informações pertinentes que podem ajudar a resolver muitos problemas de nível 1, como status do usuário, falha de instalação do aplicativo ou problemas de conformidade. Os problemas tratados podem incluir:
- O dispositivo não está respondendo
-   O dispositivo não consegue obter configurações de VPN ou Wi-Fi
-   Falha na instalação do aplicativo


## Adicionar operadores de suporte técnico
<a id="add-help-desk-operators" class="xliff"></a>
Um administrador do Intune pode atribuir a permissão de operador de suporte técnico para os usuários de duas maneiras:
- Atribuir a função **Operador do suporte técnico** interna
- Criar e atribuir uma função personalizada

## Atribuir função de operador de suporte técnico
<a id="assign-help-desk-operator-role" class="xliff"></a>
Como um administrador do Intune, você pode atribuir a função de Operador de suporte técnico para um grupo de usuários. Membros desse grupo podem usar o portal de administração. Cada operador de suporte técnico deve ter uma licença do Intune para acessar o Portal do Intune. Saiba como [atribuir licenças do Intune](licenses-assign.md).

1. Como administrador do Intune, faça logon no Portal do Intune e selecione **Funções do Intune**.
2. Na carga de trabalho **Funções do Intune**, selecione **Operador de Suporte Técnico** > **Atribuições** e selecione **Atribuir**.
  ![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico, com Atribuições realçado e uma caixa vermelha ao redor de Atribuir](./media/help-desk-user-assign.png)
3. Digite um **Nome de atribuição** (obrigatório), uma **Descrição da atribuição** (opcional) e atribua **Membros (Grupos)** e **Escopo (Grupos)**.
4. Os membros da função Operador de Suporte Técnico agora podem usar o portal de solução de problemas.

Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](role-based-access-control.md).

## Criar uma função personalizada para solução de problemas
<a id="create-a-custom-role-for-troubleshooting" class="xliff"></a>
Como um administrador do Intune, você pode criar uma função personalizada que permite aos usuários a usar o portal de solução de problemas com permissões adequadas para as necessidades da sua organização. Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](role-based-access-control.md).

![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico](./media/help-desk-user-add.png)

Para usar o console do Intune para uma exibição de suporte técnico, uma função de suporte técnico personalizada deve ter as seguintes permissões:
- MobileApps: leitura
- ManagedApps: leitura
- ManagedDevices: leitura
- Organization: leitura

## Acessar o portal de solução de problemas
<a id="access-the-troubleshooting-portal" class="xliff"></a>

A equipe de suporte técnico e os administradores do Intune podem acessar o portal de solução de problemas de duas maneiras:
- Abra [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) em um navegador da Web.
- No Portal do Intune, acesse **Ajuda e Suporte** > **Solucionar Problemas**.

![Captura de tela da carga de trabalho de solução de problemas do Microsoft Intune com o link Selecionar Usuário](media/help-desk-user.png)

## Usar o portal de solução de problemas
<a id="use-the-troubleshooting-portal" class="xliff"></a>

No portal de solução de problemas, escolha **Selecionar Usuário** para exibir as informações dos usuários. As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos. O portal de solução de problemas mostra os seguintes detalhes de solução de problemas:
- **Status do locatário**
- **Status do usuário**
- **Dispositivos** e ações de dispositivo
- **Associação a um grupo**
- **Status de proteção de aplicativo**
