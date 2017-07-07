---
title: Redefinir dispositivos Windows 10 com o Intune
titleSuffix: Intune on Azure
description: "Saiba como usar o Novo Início para redefinir computadores Windows 10 que executam o Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 590472c0ab9f0103d72730b8ab01dc324c852a7a
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2017
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a>Usar o Novo Início para redefinir dispositivos Windows 10 com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

A ação de dispositivo **Novo Início** remove todos os aplicativos que foram instalados em um computador Windows 10 que executa a Atualização para Criadores e, em seguida, atualiza automaticamente o computador para a versão mais recente do Windows.
Isso pode ser usado para ajudar a remover aplicativos pré-instalados (OEM) que geralmente são fornecidos com um novo computador. Você pode configurar se os dados do usuário são mantidos quando essa ação do dispositivo é realizada. Nesse caso, os aplicativos e as configurações são removidas, mas o conteúdo da pasta base dos usuários é mantido.

1. Entre no portal do Azure.
2. Escolha **Mais Serviços** > **Monitoramento + Gerenciamento** > **Intune**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos e grupos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo do Windows 10 Desktop e, em seguida, escolha a ação remota de dispositivo **Novo Início**.

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos e grupos**, escolha **Ações de Dispositivo**.

