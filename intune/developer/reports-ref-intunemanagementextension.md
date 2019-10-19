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
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae99e747f9c0540418c15f24fbe0c27c585f869c
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490312"
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

