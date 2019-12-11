---
title: Apagar um dispositivo macOS
titleSuffix: Microsoft Intune
description: Saiba como apagar todos os dados, incluindo o sistema operacional, de um dispositivo macOS.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/31/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: remote-actions
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ab396092-907a-44b7-a157-aabee62176a9
ms.reviewer: coferro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6bc2ba86ddb36355bca8328b9c205047abf1b4ff
ms.sourcegitcommit: ec69e7ccc6e6183862a48c1b03ca6a3bf573f354
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/07/2019
ms.locfileid: "74907263"
---
# <a name="erase-all-data-from-a-macos-device"></a>Apagar todos os dados de um dispositivo macOS

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Você pode apagar todos os dados de um dispositivo macOS, incluindo o sistema operacional. O dispositivo também será removido do gerenciamento do Intune. Nenhum aviso será dado ao usuário final.

1. No [Centro de Administração do Gerenciador de Ponto de Extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431), selecione **Dispositivos** > **Todos os dispositivos** > escolha o dispositivo a apagar.
2. Clique em **Mais** > **Apagar** > forneça um número de 6 dígitos para o **PIN de recuperação**. Este é o PIN que você deve fornecer ao usuário para que ele possa reinstalar o sistema operacional no dispositivo. Certifique-se de anotar esse PIN porque ele não ficará visível após a conclusão da ação de apagar.
![Captura de tela](./media/device-erase/providepin.png)
3. Clique em **OK** apagar o dispositivo.
