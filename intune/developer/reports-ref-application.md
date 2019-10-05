---
title: Referência para entidades de aplicativo
titleSuffix: Microsoft Intune
description: Tópico de referência para a categoria de Aplicativo de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1e737f1cce594b5dd40b2f43048ba37578f5d7c9
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940436"
---
# <a name="reference-for-application-entities"></a>Referência para entidades de aplicativo

A categoria **Aplicativo** contém entidades para dispositivos móveis que rastreiam informações como:

- Versões de um aplicativo
- Origem de instalação de um aplicativo
- Tipo de desenvolvedores que criaram um aplicativo
- Tipos de software gerenciado para um aplicativo, por exemplo **secundários** ou **área de trabalho**
- Estado do programa de compra de volume (VPP) de um aplicativo

## <a name="apprevisions"></a>appRevisions

A entidade **appRevision** lista todas as versões de aplicativos.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| appKey |Identificador exclusivo do aplicativo. |123 |
| applicationId |Identificador exclusivo do aplicativo – semelhante ao AppKey, mas essa chave é um natural. |b66bc706-ffff-7437-0340-032819502773 |
| revisão |A versão mencionada pelo administrador durante o carregamento do binário. |2 |
| title |Título do aplicativo. |Excel |
| editor |Editor do aplicativo. |Microsoft |
| uploadState |Estado de upload do aplicativo. |1 |
| appTypeKey |Referência ao AppType descrito na próxima seção. | |
| vppProgramTypeKey |Referência ao VppProgramType descrito abaixo. | |
| creationTime |A hora em que esta revisão foi criada. |23/11/2016 12:00:00 AM |
| modifiedTime |Última vez em que qualquer coisa relacionada a esta revisão foi alterada. |23/11/2016 12:00:00 AM |
| tamanho |Tamanho do binário. | |
| startDateInclusiveUTC |Data e hora em UTC em que essa revisão de aplicativo foi criada no data warehouse. |23/11/2016 12:00:00 AM |
| endDateExclusiveUTC |Data e hora em UTC em que essa revisão de aplicativo se tornou obsoleta. |23/11/2016 12:00:00 AM |
| isCurrent |Indica se a versão desse aplicativo está atualizada ou não no data warehouse. |Verdadeiro/Falso |
| rowLastModifiedDateTimeUTC |Data e hora em UTC em que a versão desse aplicativo foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="apptypes"></a>appTypes

A entidade **appType** lista a origem da instalação de um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| appTypeID |ID do tipo |
| appTypeKey |Chave substituta para a chave |
| appTypeName |Tipo de aplicativo |

### <a name="example"></a>Exemplo

| AppTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Aplicativos da loja Android | Um aplicativo da loja Android. |
| 1 |Aplicativos LOB para Android | Um aplicativo Android de linha de negócios. |
| 2 |Aplicativo gerenciado da loja do Android (MAM) | Um aplicativo da loja Android que tem o gerenciamento habilitado. |
| 3 |Aplicativo da loja iOS | Um aplicativo da loja iOS. |
| 4 |Aplicativo LOB para iOS | Um aplicativo iOS de linha de negócios. |
| 5 |Aplicativo gerenciado de loja do iOS (MAM?) | Um aplicativo da loja do iOS que tem o gerenciamento habilitado. |
| 6 |O365 Pro Plus Suite | O Pacote do Office 365 Pro Plus para Windows 10. |
| 7 |Aplicativo Web | Um aplicativo Web. |
| 8 |Aplicativo da loja do Windows Phone 8.1 | Um aplicativo da loja do Windows Phone 8.1. |
| 9 |Aplicativo da Windows Store | Um aplicativo da Windows Store. |
| 10 |Aplicativos LOB para Windows | Um aplicativo de linha de negócios AppX do Windows. |
| 11 |Windows Mobile MSI | Um aplicativo de linha de negócios do MSI. |
| 12 |Aplicativo LOB para Windows Phone | Um aplicativo de linha de negócios do Windows Phone. |


## <a name="vppprogramtypes"></a>vppProgramTypes

A entidade **vppProgramType** lista os possíveis tipos de programa VPP para um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| vppProgramTypeID | ID do tipo. |
| vppProgramTypeKey | Chave alternativa para a chave. |
| vppProgramTypeName | Tipo de programa do VPP. |

### <a name="example"></a>Exemplo

| VppProgramID  | Nome | Descrição |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Programa VPP da Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Ainda não disponível | Valor padrão, não VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Programa VPP da Apple. |



## <a name="applicationinventories"></a>applicationInventories

A entidade **applicationInventory** lista os aplicativos encontrados no dispositivo no momento da coleta de inventário.

| Propriedade  | Descrição |
|---------|------------|
| deviceKey | Esta é uma referência à tabela de dispositivo que contém a ID do dispositivo do Intune. |
| dateKey | Referência à tabela de data que indica o dia do inventário. |
| applicationName | Nome do aplicativo. |
| applicationVersion | Versão do aplicativo. |
| bundleSize | O tamanho do aplicativo em bytes. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates

A entidade **mobileAppInstallState** representa o estado de instalação de um aplicativo móvel após sua atribuição a um grupo que contém dispositivos, usuários ou ambos.

| Propriedade | Descrição |
|---|---|
| appInstallStateKey | A ID exclusiva do estado de instalação do aplicativo para sua conta. |
| appInstallState | Valor de enumeração do estado de instalação do aplicativo. |
| appInstallStateName | Nome do estado de instalação do aplicativo. |



