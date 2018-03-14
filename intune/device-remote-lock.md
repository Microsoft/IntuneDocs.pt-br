---
title: Bloquear dispositivos gerenciados remotamente com o Intune
titlesuffix: Azure portal
description: Saiba como usar o Intune para bloquear os dispositivos gerenciados remotamente.
keywords: 
author: arob98
ms.author: angrobe
manager: dougeby
ms.date: 01/22/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0a8f3c93507cde4363570a9a39f8b3b1f69c07df
ms.sourcegitcommit: 7e5c4d43cbd757342cb731bf691ef3891b0792b5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Bloquear dispositivos gerenciados remotamente com o Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O dispositivo **Bloqueio remoto** bloqueia o dispositivo selecionado. O proprietário do dispositivo deve usar a senha para desbloqueá-lo. Você pode bloquear remotamente apenas um dispositivo que tenha um PIN ou senha definida.

## <a name="supported-platforms"></a>Plataformas com Suporte

O bloqueio remoto é compatível com as seguintes plataformas:

|Plataforma|Status de suporte|
|---|---|
|Android|Sim|
|iOS|Sim|
|macOS|Sim|
|Windows 10 Desktop|Não|
|Windows 10 Mobile|Sim|
|Windows Phone|Sim, para Windows Phone 8.1 e posterior|

> [!NOTE]  
> Para dispositivos macOS, você define um PIN de recuperação de 6 dígitos. Quando bloqueados, a folha de **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

## <a name="how-to-remote-lock-a-device"></a>Como bloquear um dispositivo remotamente

1. Entre no [portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços** > **Intune**. O Intune está localizado na seção **Monitoramento + Gerenciamento**.
3. Na folha **Intune**, escolha **Dispositivos**.
4. Na folha **Dispositivos**, escolha **Todos os dispositivos**.
5. Na lista de dispositivos gerenciados, escolha um dispositivo e, em seguida, escolha a ação remota de dispositivo **Bloqueio remoto**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação que você acabou de realizar, na folha **Dispositivos**, escolha **Ações do dispositivo**.
