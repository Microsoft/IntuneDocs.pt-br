---
title: Entidade IntuneManagementExtension
titleSuffix: Microsoft Intune
description: Tópico de referência para a categoria de coleções de entidade IntuneManagementExtension na API de Data Warehouse do Intune.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19b63172c8901059239c44aaf56fc49f0d7a01ad
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940410"
---
# <a name="reference-for-intune-management-extensions"></a>Referência para as extensões de gerenciamento do Intune

A categoria **IntuneManagementExtensions** contém entidades para dispositivos móveis que acompanham informações como:

- Versões de um IntuneManagementExtension
- Status de instalação de um IntuneManagementExtension

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions

A entidade **intuneManagementExtensionVersion** lista todas as versões usadas pelo intuneManagementExtensions.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| extensionVersionKey |Identificador exclusivo da versão intuneManagementExtensions. | 1 |
| extensionVersion |O número de versão de quatro dígitos. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates

O **intuneManagementExtensionHealthState** lista todos os estados de integridade possíveis da intuneManagementExtensions.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| extensionStateKey |Identificador exclusivo do estado de integridade. | 2 |
| extensionState |Estado de integridade de um IntuneManagementExtension. | Íntegros |

## <a name="intunemanagementextensions"></a>intuneManagementExtensions

A **intuneManagementExtension** lista a integridade da IntuneManagementExtensions em cada dispositivo Windows 10 por dia.
Os dados são retidos pelos últimos 60 dias. 


|      Propriedade       |                         Descrição                         | Exemplo |
|---------------------|-------------------------------------------------------------|---------|
|       dateKey       |               Identificador exclusivo da data.                |   123   |
|      tenantKey      |              Identificador exclusivo do locatário.               |   456   |
|      deviceKey      |              Identificador exclusivo do dispositivo.               |   789   |
| extensionVersionKey | Identificador exclusivo da versão intuneManagementExtension. |    1    |
|  extensionStateKey  |             Identificador exclusivo do estado de integridade.              |    2    |

