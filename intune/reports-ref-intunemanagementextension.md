---
title: Entidade IntuneManagementExtension
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria de coleções de entidade IntuneManagementExtension na API de Data Warehouse do Intune.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 48e08b93468fb177fd3a724e5bcc6758cf262e99
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189360"
---
# <a name="reference-for-intune-management-extension"></a>Referência para a extensão de gerenciamento do Intune

A categoria **IntuneManagementExtension** contém entidades para dispositivos móveis que acompanham informações como:

  -  Versões de um IntuneManagementExtension
  -  Status de instalação de um IntuneManagementExtension

## <a name="intunemanagementextensionversion"></a>IntuneManagementExtensionVersion

A entidade **IntuneManagementExtensionVersion** lista todas as versões usadas pelo IntuneManagementExtension.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| ExtensionVersionKey |Identificador exclusivo da versão IntuneManagementExtension. | 1 |
| ExtensionVersion |O número de versão de quatro dígitos. |1.0.2.0 |

## <a name="intunemanagementextensionhealthstate"></a>IntuneManagementExtensionHealthState

O **IntuneManagementExtensionHealthState** lista todos os estados de integridade possíveis da IntuneManagementExtension.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| ExtensionStateKey |Identificador exclusivo do estado de integridade. | 2 |
| ExtensionState |Estado de integridade de um IntuneManagementExtension. | Healthy |

## <a name="intunemanagementextension"></a>IntuneManagementExtension

O **IntuneManagementExtension** lista a integridade do IntuneManagementExtension em cada dispositivo Windows 10 por dia.
Os dados são retidos pelos últimos 60 dias. 


|      Propriedade       |                         Descrição                         | Exemplo |
|---------------------|-------------------------------------------------------------|---------|
|       DateKey       |               Identificador exclusivo da data.                |   123   |
|      TenantKey      |              Identificador exclusivo do locatário.               |   456   |
|      DeviceKey      |              Identificador exclusivo do dispositivo.               |   789   |
| ExtensionVersionKey | Identificador exclusivo da versão IntuneManagementExtension. |    1    |
|  ExtensionStateKey  |             Identificador exclusivo do estado de integridade.              |    2    |

