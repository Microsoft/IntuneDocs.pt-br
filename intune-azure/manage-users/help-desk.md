---
title: "Portal de solução de problemas do suporte técnico | Microsoft Docs"
titleSuffix: Intune Azure preview
description: "A equipe de suporte técnico usa o portal de solução de problemas para resolver problemas técnicos dos usuários"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/18/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: sumitp
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e0ecc775f70703574c4e1adf0f0aa204f2745b72
ms.openlocfilehash: 723830f686991fe13de13f75c6a5d1bc84e6920b
ms.lasthandoff: 04/20/2017

---
# <a name="help-users-with-the-troubleshooting-portal-in-microsoft-intune"></a>Ajudar os usuários com o portal de solução de problemas no Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

O portal de solução de problemas permite que operadores do suporte técnico e administradores do Intune vejam usuários e seus dispositivos e executem tarefas para resolver problemas técnicos do Intune.

## <a name="add-help-desk-operators"></a>Adicionar operadores de suporte técnico
Um administrador do Intune pode ajudar a atribuir permissão de operador de suporte técnico para os usuários. Os usuários de suporte técnico podem exibir o portal do Intune, mas não podem exibir ou executar tarefas administrativas fora da carga de trabalho de solução de problemas.

1. Como administrador do Intune, faça logon no [Portal do Azure](https:portal.azure.com), selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
2. Na folha de navegação à esquerda, selecione **Funções do Intune**.
3. Na carga de trabalho **Funções do Intune**, selecione **Operador de Suporte Técnico** e selecione **Atribuir**.
4. Digite um **Nome de atribuição** (obrigatório), uma **Descrição da atribuição** (opcional) e atribua **Membros (Grupos)** e **Escopo (Grupos)**.
5. Os membros da função Operador de Suporte Técnico agora podem usar o portal de solução de problemas.

Para saber mais sobre as funções do Intune, confira [Funções do Intune (RBAC)](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control).

## <a name="access-the-troubleshooting-portal"></a>Acessar o portal de solução de problemas

A equipe de suporte técnico e os administradores do Intune podem acessar o portal de solução de problemas de duas maneiras:
- No [Portal do Azure](https:portal.azure.com), selecione **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**e na folha de navegação à esquerda, selecione **Solucionar problemas**. Outras cargas de trabalho ficam visíveis na folha de navegação à esquerda, mas não estão disponíveis.
![Captura de tela da carga de trabalho de solução de problema do Intune com o link Selecionar Usuário](media/help-desk-user.png)
- Abra [http://aka.ms/intunetroubleshooting](http://aka.ms/intunetroubleshooting) em um navegador da Web. O portal de solução de problemas fica visível.

## <a name="use-the-troubleshooting-portal"></a>Usar o portal de solução de problemas

No portal de solução de problemas, selecione **Selecionar Usuário** para exibir informações dos usuários. As informações do usuário podem ajudar você a entender o estado atual dos usuários e seus dispositivos. O portal de solução de problemas mostra o seguinte usuário do Intune e os detalhes do dispositivo:
- Informações da conta de usuário
- Associação de grupo do usuário
- Detalhes do dispositivo

Os usuários do suporte técnico também podem executar tarefas remotas em dispositivos, como **Bloqueio remoto**.

