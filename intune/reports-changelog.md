---
title: "Log de Alterações do Intune Data Warehouse | Microsoft Docs"
description: "Uma lista de alterações na API do Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6d675a36cd5ea4c11d755174bf2b0bbc5d4b18ec
ms.sourcegitcommit: 5279a0bb8c5aef79aa57aa247ad95888ffe5a12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Log de alterações para a API do Intune Data Warehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Manter-se atualizado sobre as atualizações para o Intune Data Warehouse.

## <a name="1710"></a>1710
_Lançado em novembro de 2017_

### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Entidade de usuário contém dados mais recentes do usuário no modelo de dados do Data Warehouse <!-- 1544273 -->

A primeira versão do modelo de dados do Intune Data Warehouse continha somente dados históricos recentes do Intune. Os criadores de relatório não podiam capturar o estado atual de um usuário. Nesta atualização, a [**Entidade do usuário**](reports-ref-user.md) será preenchida com os dados mais recentes do usuário.

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Novas entidades no modelo de dados de Data Warehouse <!-- 1479526 --><!-- -->

 - A entidade, [**UserDeviceAssociation**](reports-ref-user-device.md), adicionada. **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização.
 - A entidade, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), adicionada. **IntuneManagementExtension** contém entidade para dispositivos móveis que acompanham informações como versão e status de instalação.

## <a name="next-steps"></a>Próximas etapas
 - Conheça as [novidades de cada semana no Intune](whats-new.md). Saiba mais também sobre as próximas alterações, avisos importantes sobre o serviço e informações sobre versões anteriores. 
 - Leia o [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).