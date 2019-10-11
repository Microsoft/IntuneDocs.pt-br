---
title: Renomear um dispositivo com o Microsoft Intune – Azure | Microsoft Docs
description: Renomeie um dispositivo por meio do Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/05/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 35fae5ea1b3294772db4f4db51179892e08ed5d1
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71728501"
---
# <a name="rename-a-device-in-intune"></a>Renomear um dispositivo no Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

A ação **Renomear dispositivo** permite renomear um dispositivo registrado no Intune. O nome do dispositivo é alterado no Intune e no dispositivo.

Você pode renomear os seguintes tipos de dispositivos:
- Windows de propriedade corporativa 
- iOS supervisionado
- MacOS 10 de propriedade corporativa

No momento, esse recurso não dá suporte à renomeação de dispositivos Windows do Azure AD híbrido.

## <a name="rename-a-device"></a>Renomear um dispositivo

1. Conecte-se ao [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Escolha **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo > **Mais** > **Renomear dispositivo**.
4. Na folha **Renomear dispositivo**, digite o novo nome na caixa de texto. Use letras, números e hifens. O nome deve conter pelo menos uma letra ou um hífen.
5. Se você quiser reiniciar o dispositivo após renomeá-lo, escolha **Sim** ao lado de **Reinicializar após a renomeação**.
6. Escolha **Renomear**.



## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação **Renomear** dispositivo, verifique a página **Visão geral** do dispositivo.
