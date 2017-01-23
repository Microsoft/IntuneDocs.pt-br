---
title: "Apagamento de dispositivos móveis gerenciados pelo Exchange | Microsoft Docs"
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
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 5f8da4e28f3b680d7b5b42c1c54fac4c9c43fbe2


---


# <a name="wipe-for-exchange-managed-mobile-devices"></a>Wipe for Exchange-managed mobile devices

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune permite apagar ou redefinir dispositivos móveis que são gerenciados usando o EAS (Exchange ActiveSync) com o Intune Exchange Connector. A tabela a seguir descreve os recursos de apagamento disponíveis por meio do Exchange ActiveSync:

|Tipo de apagamento|Windows 8.1 e Windows RT 8.1|iOS|Android|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|Apagamento completo|Remove a conta de email e os emails armazenados em cache.|Redefinição XFactory.|Redefinição de fábrica.|
|Apagamento seletivo/email|Remove conta de email.|Não há suporte.|Não há suporte.|
|Apagamento seletivo/políticas|Aplicação de políticas é removida, mas as configurações não são alteradas|Aplicação XFactory é removida, mas as configurações não são alteradas.|A aplicação da política é removida, mas as configurações não são alteradas.|



<!--HONumber=Dec16_HO2-->


