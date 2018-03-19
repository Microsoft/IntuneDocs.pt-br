---
title: "Bloquear dispositivos com o Microsoft Intune – Azure | Microsoft Docs"
description: "Use a ação Bloqueio Remoto no Microsoft Intune para bloquear um dispositivo que é protegido por um PIN ou uma senha."
keywords: 
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59a55de54a5a18f5fd1080fefa15c0e4801a1456
ms.sourcegitcommit: 9cf05d3cb8099e4a238dae9b561920801ad5cdc6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2018
---
# <a name="remotely-lock-devices-with-intune"></a>Bloquear dispositivos remotamente com o Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

O dispositivo **Bloqueio remoto** bloqueia o dispositivo. Para desbloqueá-lo, o proprietário do dispositivo insere sua senha. Você pode bloquear remotamente os dispositivos que têm um PIN ou uma senha definida. Os dispositivos que não têm um PIN nem uma senha não podem ser bloqueados remotamente.

## <a name="supported-platforms"></a>Plataformas com Suporte

O bloqueio remoto é compatível com as seguintes plataformas:

- Android
- iOS
- macOS
- Windows 10 Mobile
- Windows Phone 8.1 e posterior

**Não** é compatível com:
- Windows 10 Desktop

> [!NOTE]
> Para dispositivos macOS, você define um PIN de recuperação de 6 dígitos. Quando bloqueado, a **Visão geral do dispositivo** exibe o PIN até que outra ação de dispositivo seja enviada.

## <a name="remote-lock-a-device"></a>Bloquear um dispositivo remotamente

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Selecione **Todos os serviços**, filtre pelo **Intune** e selecione **Microsoft Intune**.
3. Selecione **Dispositivos** e, em seguida, selecione **Todos os dispositivos**.
4. Na lista de dispositivos, selecione um dispositivo e, em seguida, selecione a ação **Bloqueio remoto**.

## <a name="next-steps"></a>Próximas etapas

Para ver o status dessa ação, abra **Ações do dispositivo** (Microsoft Intune > Dispositivos). Confira [Ações disponíveis](device-management.md) para obter mais ações que ajudam a gerenciar seus dispositivos.