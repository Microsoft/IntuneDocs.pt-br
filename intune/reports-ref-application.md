---
title: Aplicativo
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria de Aplicativo de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e27b07b18991ebd930bac6ed70fa489d27aa22ba
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2018
---
# <a name="reference-for-application-entities"></a>Referência para entidades de aplicativo

A categoria **Aplicativo** contém entidades para dispositivos móveis que rastreiam informações como:

  -  Versões de um aplicativo
  -  Origem de instalação de um aplicativo
  -  Tipo de desenvolvedores que criaram um aplicativo
  -  Tipos de software gerenciado para um aplicativo, por exemplo **secundários** ou **área de trabalho**
  -  Estado do programa de compra de volume (VPP) de um aplicativo

## <a name="apprevision"></a>AppRevision

A entidade **AppRevision** lista todas as versões de aplicativos.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| AppKey |Identificador exclusivo do aplicativo. |123 |
| ApplicationId |Identificador exclusivo do aplicativo – semelhante ao AppKey, mas essa chave é um natural. |b66bc706-ffff-7437-0340-032819502773 |
| Revisão |A versão mencionada pelo administrador durante o carregamento do binário. |2 |
| Título |Título do aplicativo. |Excel |
| Editor |Editor do aplicativo. |Microsoft |
| UploadState |Estado de upload do aplicativo. |1 |
| AppTypeKey |Referência ao AppType descrito na próxima seção. | |
| VppProgramTypeKey |Referência ao VppProgramType descrito abaixo. | |
| CreationTime |A hora em que esta revisão foi criada. |23/11/2016 12:00:00 AM |
| ModifiedTime |Última vez em que qualquer coisa relacionada a esta revisão foi alterada. |23/11/2016 12:00:00 AM |
| Tamanho |Tamanho do binário. | |
| StartDateInclusiveUTC |Data e hora em UTC em que essa revisão de aplicativo foi criada no data warehouse. |23/11/2016 12:00:00 AM |
| EndDateExclusiveUTC |Data e hora em UTC em que essa revisão de aplicativo se tornou obsoleta. |23/11/2016 12:00:00 AM |
| IsCurrent |Indica se a versão desse aplicativo está atualizada ou não no data warehouse. |Verdadeiro/Falso |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que a versão desse aplicativo foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="apptypes"></a>AppTypes

A entidade **AppTypes** lista a origem da instalação de um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| AppTypeID |ID do tipo |
| AppTypeKey |Chave substituta para a chave |
| AppTypeName |Tipo de aplicativo |

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


## <a name="vppprogramtypes"></a>VppProgramTypes

A entidade **VppProgramTypes** lista os possíveis tipos de programa VPP para um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| VppProgramTypeID | ID do tipo. |
| VppProgramTypeKey | Chave alternativa para a chave. |
| VppProgramTypeName | Tipo de programa do VPP. |

### <a name="example"></a>Exemplo

| VppProgramID  | Nome | Descrição |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | Programa VPP da Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Ainda não disponível | Valor padrão, não VPP. |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | Programa VPP da Apple. |



## <a name="applicationinventory"></a>ApplicationInventory

A entidade **ApplicationInventory** lista os aplicativos encontrados no dispositivo no momento da coleta de inventário.

| Propriedade  | Descrição |
|---------|------------|
| DeviceKey | Esta é uma referência à tabela de dispositivo que contém a ID do dispositivo do Intune. |
| DateKey | Referência à tabela de data que indica o dia do inventário. |
| ApplicationName | Nome do aplicativo. |
| ApplicationVersion | Versão do aplicativo. |
| BundleSize | O tamanho do aplicativo em bytes. |

## <a name="mobileappinstallstate"></a>MobileAppInstallState

A entidade **MobileAppInstallState** representa o estado de instalação de um aplicativo móvel após sua atribuição a um grupo que contém dispositivos, usuários ou ambos.

| Propriedade | Descrição |
|---|---|
| AppInstallStateKey | A ID exclusiva do estado de instalação do aplicativo para sua conta. |
| AppInstallState | Valor de enumeração do estado de instalação do aplicativo. |
| AppInstallStateName | Nome do estado de instalação do aplicativo. |

## <a name="mobileappdeviceuserinstallstatus"></a>MobileAppDeviceUserInstallStatus

O **MobileAppDeviceUserInstallStatus** representa um status de instalação de aplicativo móvel para um determinado dispositivo e usuário.


|      Propriedade      |                                                         Descrição                                                         |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------|
|      DateKey       |                                  Chave da data quando o status de instalação do aplicativo foi registrado.                                  |
|       AppKey       |                             Chave do aplicativo móvel usado para identificar uma instância de AppRevision.                              |
|     DeviceKey      |                              Chave de um dispositivo direcionado usado para identificar uma instância do Dispositivo.                               |
|      UserKey       |                                Chave de um usuários direcionado usado para identificar uma instância do Usuário.                                 |
| AppInstallStateKey |                     Chave do estado de instalação do aplicativo usada para identificar uma instância de MobileAppInstallState.                     |
|     Código de Erro      | O código de erro retornado pelo instalador do aplicativo, a plataforma móvel ou o serviço referente à instalação do aplicativo. |

