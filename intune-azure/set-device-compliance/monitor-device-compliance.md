---
title: Como monitorar a conformidade do dispositivo
titleSuffix: Intune Azure preview
description: "Versão prévia do Intune Azure: saiba como a monitorar a conformidade do dispositivo."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: d59d94aafa71a9891a6746902339255ea7a9ad15
ms.lasthandoff: 02/18/2017


---
# <a name="how-to-monitor-compliance-in-intune-azure-preview"></a>Como monitorar a conformidade na versão prévia do Intune Azure

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Você pode exibir o resumo do status dos seus **perfis de conformidade** na folha **Visão geral**.
Você pode clicar em interativamente nos gráficos para analisar os detalhes. Se você tiver vários perfis de conformidade configurados, também será possível exibir o status de cada política indo até a folha de política e escolhendo **Relatórios** na seção **Gerenciar**.  Os detalhes dos relatórios disponíveis para a versão prévia estão listados abaixo.

##  <a name="device-compliance"></a>Conformidade do dispositivo

A exibição resumida do relatório de conformidade do dispositivo começa mostrando as informações agregadas sobre o número de dispositivos que estão se comunicando como um dos seguintes:

- **Em conformidade**: o dispositivo foi avaliado quanto à conformidade recentemente e foi considerado em conformidade com as configurações do perfil de conformidade especificado.
- **Fora de conformidade**: o dispositivo foi avaliado e determinado como fora de conformidade.  Se havia um período de cortesia especificado no perfil, ele expirou e deixou o dispositivo fora de conformidade.
- **Período de cortesia**: o dispositivo foi avaliado e determinado como fora de conformidade. No entanto, o período de cortesia ainda se aplica antes de o dispositivo ser efetivamente marcado como fora de conformidade.

Você pode fazer uma busca detalhada em cada seção para ver mais detalhes sobre os usuários e dispositivos individuais.

## <a name="setting-compliance"></a>Conformidade da configuração

O relatório de conformidade de configuração fornece detalhes sobre cada configuração de conformidade, como:

- Número de dispositivos que não estão em conformidade com a configuração.
- A plataforma à qual a configuração é aplicada.

Você pode fazer uma busca detalhada em cada configuração para obter mais informações sobre os perfis nos quais essas configurações tem sido habilitadas e o valor definido da configuração.

