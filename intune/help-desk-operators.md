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
ms.openlocfilehash: 7aad054f0861522174faa01b979083a818c106af
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2017
---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Ajudar os usuários com o portal de solução de problemas no Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O portal de solução de problemas permite que os operadores de suporte técnico e os administradores do Intune exibam informações do usuário para resolver solicitações de ajuda do usuário. As organizações que incluem operadores de suporte técnico em sua equipe podem atribuir o **Operador do suporte técnico** a um grupo de usuários, o qual poderá usar a folha Solução de Problemas para ajudar os usuários.

Por exemplo, quando um usuário contata o suporte com um problema técnico com o Intune, o operador do suporte técnico digita o nome do usuário. O Intune mostra dados úteis que podem ajudar a solucionar muitos problemas de nível 1 incluindo:
- Status do usuário
- Atribuições
- Falha na instalação do aplicativo
- Problemas de conformidade
- O dispositivo não está respondendo
-   O dispositivo não consegue obter configurações de VPN ou Wi-Fi
-   Falha na instalação do aplicativo


## <a name="add-help-desk-operators"></a>Adicionar operadores de suporte técnico
Como um administrador do Intune, você pode atribuir a função de Operador de suporte técnico para um grupo de usuários. Os membros desse grupo podem usar o portal de administração para solucionar problemas dos usuários. Cada operador de suporte técnico deve ter uma licença do Intune para acessar o Portal do Intune. Saiba como [atribuir licenças do Intune](licenses-assign.md).

Para adicionar usuários do suporte técnico:
1. [Adicione um usuário ao Intune](users-add.md) se necessário
2. [Crie um grupo de suporte técnico](groups-add.md) e adicione usuários ao grupo
3. [Atribua a função de Operador de Suporte Técnico RBAC](role-based-access-control.md#built-in-roles) ou [crie uma função personalizada](role-based-access-control.md#custom-roles) com as seguintes permissões:
  - MobileApps: leitura
  - ManagedApps: leitura
  - ManagedDevices: leitura
  - Organization: leitura
  - DeviceCompliancePolices: leitura
  - DeviceConfigurations: leitura

  ![Captura de tela do Portal do Intune que mostra as funções do Intune realçadas e uma lista de funções internas, incluindo Operador de suporte técnico](./media/help-desk-user-add.png)

4. Para conceder permissão de operadores de suporte técnico para exibir a integridade do serviço e abrir tíquetes de suporte para o Intune, [conceda permissões de administrador aos usuários](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal) como um **Administrador de serviços**. Não conceda a permissão de **Administrador de Serviços do Intune** porque essa função do diretório tem mais direitos do que o necessário para os operadores de suporte técnico.

## <a name="access-the-troubleshooting-portal"></a>Acessar o portal de solução de problemas

A equipe de suporte técnico e os administradores do Intune podem acessar o portal de solução de problemas de duas maneiras:
- Abra [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) em um navegador da Web para exibir apenas o portal de solução de problemas.
  ![Captura de tela do console de Solução de problemas](./media/help-desk-console.png)
- Entre no Portal do Azure, escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune** e vá até **Ajuda e Suporte** > **Solucionar Problemas**.

Clique em **Selecionar usuário** para exibir um usuário e os detalhes dele.

![Captura de tela da carga de trabalho de solução de problemas do Microsoft Intune com o link Selecionar Usuário](media/help-desk-user.png)

## <a name="use-the-troubleshooting-portal"></a>Usar o portal de solução de problemas

No portal de solução de problemas, escolha **Selecionar Usuário** para exibir as informações dos usuários. As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos. O portal de solução de problemas mostra os seguintes detalhes de solução de problemas:
- **Status da conta**
- **Status do usuário**
- **Dispositivos** com ações de dispositivo
- **Associação a um grupo**
- **Status de proteção de aplicativo**