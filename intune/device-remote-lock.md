---
title: Bloquear dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Use a ação Bloquear remotamente no Microsoft Intune para bloquear um dispositivo protegido por um PIN ou por senha.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae114b9aec2794556a8162604a533c24c11bafba
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905131"
---
# <a name="remotely-lock-devices-with-intune"></a>Bloquear dispositivos remotamente com o Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação do dispositivo **Bloquear remotamente** bloqueia o dispositivo. Para desbloqueá-lo, o proprietário do dispositivo insere sua senha. Você pode bloquear remotamente os dispositivos que têm um PIN ou uma senha definida. Os dispositivos que não têm um PIN nem uma senha não podem ser bloqueados remotamente.

## <a name="supported-platforms"></a>Plataformas com Suporte

**Bloquear remotamente** é compatível com as seguintes plataformas:

- Android
- Dispositivos de quiosque Android Enterprise
- Dispositivos de perfil de trabalho Android Enterprise
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 e posterior

Não há suporte para **Bloqueio remoto** no:
- Windows 10 Desktop

> [!NOTE]
> Para dispositivos macOS, você define um PIN de recuperação de 6 dígitos. Quando o dispositivo está bloqueado, a **Visão geral do dispositivo** exibe o PIN até que outra ação do dispositivo seja enviada.

## <a name="remote-lock-a-device"></a>Bloquear um dispositivo remotamente

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e, em seguida, selecione **Microsoft Intune**.
3. Selecione **Dispositivos** > **Todos os dispositivos**.
4. Na lista de dispositivos, selecione um dispositivo e, em seguida, selecione a ação **Bloquear remotamente**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status dessa ação, selecione **Microsoft Intune** > **Dispositivos** > **Ações do dispositivo**. 
- Para ver mais ações que podem ajudá-lo a gerenciar seus dispositivos, consulte [Ações disponíveis](device-management.md).
