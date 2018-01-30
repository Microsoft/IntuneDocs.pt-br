---
title: "Log de Alterações do Intune Data Warehouse | Microsoft Docs"
description: "Uma lista de alterações na API do Intune Data Warehouse."
keywords: Intune Data Warehouse
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 306cceb704c1153b5691181d576561d9c93a36d3
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Log de alterações para a API do Intune Data Warehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Manter-se atualizado sobre as atualizações para o Intune Data Warehouse.

## <a name="1710"></a>1710
_Lançado em novembro de 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Uma nova coleção de entidade chamada Usuário Atual é limitada a usuários ativos no momento <!-- 1544273 -->

A coleção de entidades **Usuários** contém todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa. Esses registros incluem estados do usuário durante o período de coleta de dados, mesmo se o usuário tiver sido removido. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

Em contraste, a nova coleção de entidade **Usuário Atual** contém apenas os usuários que não foram removidos. A coleção de entidade **Usuário Atual** contém apenas usuários ativos no momento. Para saber mais sobre a coleção de entidade **usuário atual**, veja [Referência para a entidade de usuário atual](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Lançado em outubro de 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->

Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado. Para saber mais, veja a [Associação de dispositivo de usuário](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Novas entidades no modelo de dados de Data Warehouse <!-- 1479526 --><!-- -->

 - A entidade, [**UserDeviceAssociation**](reports-ref-user-device.md), adicionada. **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização. Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo.  
 - A entidade, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), adicionada. **IntuneManagementExtension** contém entidade para dispositivos móveis que acompanham informações como versão e status de instalação.

## <a name="next-steps"></a>Próximas etapas
 - Conheça as [novidades de cada semana no Intune](whats-new.md). Saiba mais também sobre as próximas alterações, avisos importantes sobre o serviço e informações sobre versões anteriores.
 - Leia o [Blog do Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=273882).
