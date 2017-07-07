---
title: Remover dados da empresa de dispositivos com o Intune
titleSuffix: Intune on Azure
description: Saiba como remover apenas os dados da empresa de dispositivos gerenciados com o Intune.
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f021e95f-157f-4e8a-9253-1cff03d6ee3e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 39acd12333e9685f94d23416fb1a61ce93f45476
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="remove-company-data-from-intune-managed-devices"></a>Remover dados da empresa de dispositivos gerenciados pelo Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A opção **Remover dados da empresa** remove somente os dados da empresa de dispositivos gerenciados pelo Intune. Não remove dados pessoais do dispositivo. O dispositivo não será mais gerenciado pelo Intune e não será capaz de acessar recursos corporativos (sem suporte para dispositivos Windows que fazem parte do Azure Active Directory).

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Remover dados da empresa**.

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.
