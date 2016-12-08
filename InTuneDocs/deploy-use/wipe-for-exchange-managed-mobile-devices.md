---
title: "Apagamento de dispositivos móveis gerenciados pelo Exchange | Microsoft Intune"
description: "O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector"
keywords: 
author: staciebarker
ms.author: staciebarker
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ms.reviewer: lancecra
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: cba0d6d781d3050f4dd8aabd661d677ae849eff1
ms.openlocfilehash: 22ec027fabb560ee0ce9c02b10f78a7100cf9e8d


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices
O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector. A tabela a seguir descreve os recursos de apagamento disponíveis por meio do Exchange ActiveSync:

|Tipo de apagamento|Windows 8.1 e Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Apagamento completo|Remove a conta de email e os emails armazenados em cache.|Redefinição XFactory.|Redefinição de fábrica.|
|Apagamento seletivo/email|Remove conta de email.|Não há suporte.|Não há suporte.|
|Apagamento seletivo/políticas|Aplicação de políticas é removida, mas as configurações não são alteradas|Aplicação XFactory é removida, mas as configurações não são alteradas.|A aplicação da política é removida, mas as configurações não são alteradas.|



<!--HONumber=Nov16_HO2-->


