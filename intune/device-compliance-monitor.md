---
title: Monitorar a conformidade do dispositivo
titlesuffix: Microsoft Intune
description: Saiba como monitorar a conformidade do dispositivo.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/07/2016
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0fec00b18bd63986a537549715af84cd44539fbb
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2018
---
# <a name="monitor-device-compliance-in-intune"></a>Monitorar a conformidade do dispositivo no Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Você pode exibir o resumo do status dos seus **perfis de conformidade** na folha **Visão geral**.
Você pode clicar em interativamente nos gráficos para analisar os detalhes. Se você tem vários perfis de conformidade configurados, você pode exibir o status da política na folha de política em **Gerenciar** > **Relatórios**.

##  <a name="device-compliance"></a>Conformidade do dispositivo

A exibição resumida do relatório de conformidade do dispositivo lista as informações agregadas sobre o número de dispositivos que estão enviando relatórios, de acordo com um dos seguintes estados:

- **Em conformidade**: o dispositivo foi avaliado recentemente e está de acordo com as configurações de perfil de conformidade especificadas.
- **Fora de conformidade**: o dispositivo foi avaliado e determinado como fora de conformidade.  Se havia um período de cortesia especificado no perfil, ele expirou e deixou o dispositivo fora de conformidade.
- **Período de cortesia**: o dispositivo foi avaliado e determinado como fora de conformidade. No entanto, o período de cortesia ainda se aplica antes de o dispositivo ser marcado como fora de conformidade.

Você pode fazer uma busca detalhada em cada seção para ver mais detalhes sobre os usuários e dispositivos individuais.

## <a name="setting-compliance"></a>Conformidade da configuração

O relatório de conformidade de configuração fornece detalhes sobre cada configuração de conformidade, como:

- Número de dispositivos que não estão em conformidade com a configuração.
- A plataforma à qual a configuração é aplicada.

Você pode fazer uma busca detalhada em cada configuração para obter mais informações sobre os perfis nos quais essas configurações tem sido habilitadas e o valor da configuração.
