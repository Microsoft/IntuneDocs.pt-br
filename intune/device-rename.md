---
title: Renomear um dispositivo Windows 10 com o Microsoft Intune – Azure | Microsoft Docs
description: Renomeie um dispositivo Windows usando o Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/26/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8dfdc3641d583fc045346034ee8543feff1e7cbf
ms.sourcegitcommit: 1144247aa7f042eb1b99d8fd8dd17b909eae38c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2019
ms.locfileid: "59567095"
---
# <a name="rename-a-windows-device-in-intune"></a>Renomear um dispositivo Windows no Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

A ação **Renomear dispositivo** permite que você renomeie um dispositivo Windows corporativo registrado no Intune. O nome do dispositivo é alterado no Intune e no dispositivo. 

No momento, esse recurso não dá suporte à renomeação de dispositivos Windows do Azure AD híbrido.

## <a name="rename-a-device"></a>Renomear um dispositivo

1. Entre no [Portal do Azure](https://portal.azure.com).
2. Escolha **Todos os serviços**, filtre pelo **Intune** e escolha **Microsoft Intune**.
3. Escolha **Dispositivos** > **Todos os dispositivos** > escolha um dispositivo do Windows > **Mais** > **Renomear dispositivo**.
4. Na folha **Renomear dispositivo**, digite o novo nome na caixa de texto. Use letras, números e hifens. O nome deve conter pelo menos uma letra ou um hífen.
5. Se você quiser reiniciar o dispositivo após renomeá-lo, escolha **Sim** ao lado de **Reinicializar após a renomeação**.
6. Escolha **Renomear**.



## <a name="next-steps"></a>Próximas etapas

Para ver o status da ação **Renomear** dispositivo, verifique a página **Visão geral** do dispositivo.
