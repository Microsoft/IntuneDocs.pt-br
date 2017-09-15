---
title: "Portal de solução de problemas de suporte técnico"
titlesuffix: Azure portal
description: "A equipe de suporte técnico usa o portal de solução de problemas para resolver problemas técnicos dos usuários"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
ms.openlocfilehash: 14b47727428fcd6a16f9960e21f70ee64c7757d1
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2017
---
# <a name="use-the-troubleshooting-portal-to-help-users"></a>Usar o portal de solução de problemas para ajudar os usuários

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O portal de solução de problemas permite que os operadores de suporte técnico e os administradores do Intune exibam informações do usuário para atender às solicitações de ajuda do usuário. As organizações que incluem operadores de suporte técnico em sua equipe podem atribuir o **Operador do suporte técnico** a um grupo de usuários, o qual poderá usar a folha Solução de Problemas para ajudar os usuários.

Por exemplo, quando um usuário contata o suporte com um problema técnico com o Intune, o operador do suporte técnico digita o nome do usuário. O Intune mostra dados úteis que podem ajudar a solucionar muitos problemas de nível 1 incluindo:
- Status do usuário
- Atribuições
- Problemas de conformidade
- O dispositivo não está respondendo
-   O dispositivo não consegue obter configurações de VPN ou Wi-Fi
-   Falha na instalação do aplicativo

## <a name="add-help-desk-operators"></a>Adicionar operadores de suporte técnico
Como um administrador do Intune, você pode atribuir a função de Operador de suporte técnico para um grupo de usuários. Os membros desse grupo podem usar o Portal do Azure para solucionar problemas dos usuários. Cada operador de suporte técnico deve ter uma licença do Intune para acessar o Portal do Azure. Saiba como [atribuir licenças do Intune](licenses-assign.md).

Para adicionar usuários do suporte técnico:
1. [Adicione usuários ao Intune](users-add.md), se necessário.
2. [Crie um grupo de suporte técnico](groups-add.md) e adicione usuários ao grupo.
3. [Atribua a função Operador de Suporte Técnico do RBAC](role-based-access-control.md#built-in-roles).

  ![Captura de tela do Portal do Azure mostrando as funções do Intune realçadas e uma lista de funções internas, incluindo Operados de Suporte Técnico](./media/help-desk-user-add.png) Também é possível [criar uma função personalizada](role-based-access-control.md#custom-roles), que pode ser modificada futuramente para conceder acesso a operadores de suporte técnico.  Os operadores de suporte técnico precisam das seguintes permissões para ajudar a solucionar os problemas do usuário:
    - MobileApps: leitura
    - ManagedApps: leitura
    - ManagedDevices: leitura
    - Organization: leitura
    - DeviceCompliancePolices: leitura
    - DeviceConfigurations: leitura

4. Para conceder permissão de operadores de suporte técnico para exibir a integridade do serviço e abrir tíquetes de suporte para o Intune, [conceda permissões de administrador aos usuários](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) como um **Administrador de serviços**. Não conceda a permissão de **Administrador de Serviços do Intune** porque essa função do diretório tem mais direitos do que o necessário para os operadores de suporte técnico.

## <a name="access-the-troubleshooting-portal"></a>Acessar o portal de solução de problemas

A equipe de suporte técnico e os administradores do Intune podem acessar o portal de solução de problemas de duas maneiras:
- Abra [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) em um navegador da Web para exibir apenas o portal de solução de problemas.
  ![Captura de tela do console de Solução de problemas](./media/help-desk-console.png)
- Entre no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune** e vá até **Ajuda e Suporte** > **Solucionar Problemas**.

Clique em **Selecionar usuário** para exibir um usuário e os detalhes dele.

## <a name="use-the-troubleshooting-portal"></a>Usar o portal de solução de problemas

No portal de solução de problemas, escolha **Selecionar Usuário** para exibir as informações dos usuários. As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos. O portal de solução de problemas mostra os seguintes detalhes de solução de problemas:
- **Status da conta**
- **Status do usuário**
- **Dispositivos** com ações de dispositivo
- **Associação a um grupo**
- **Status de proteção de aplicativo**
