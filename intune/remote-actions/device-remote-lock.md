---
title: Bloquear dispositivos com o Microsoft Intune – Azure | Microsoft Docs
description: Use a ação Bloquear remotamente no Microsoft Intune para bloquear um dispositivo protegido por um PIN ou por senha.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/07/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: bce5a89ecc49952f5c21536c429e9cd3309b13c3
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "73712261"
---
# <a name="remotely-lock-devices-with-intune"></a>Bloquear dispositivos remotamente com o Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

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

1. Entre no [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431).
3. Selecione **Dispositivos** > **Todos os dispositivos**.
4. Na lista de dispositivos, selecione um dispositivo e, em seguida, selecione a ação **Bloquear remotamente**.

## <a name="next-steps"></a>Próximas etapas

- Para ver o status dessa ação, selecione **Microsoft Intune** > **Dispositivos** > **Ações do dispositivo**. 
- Para ver mais ações que podem ajudá-lo a gerenciar seus dispositivos, consulte [Ações disponíveis](device-management.md).
