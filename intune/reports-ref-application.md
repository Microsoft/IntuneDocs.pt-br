---
title: Aplicativo | Microsoft Docs
description: "Tópico de referência para a categoria de Aplicativo de coleções de entidade na API Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2e12792445b36ba6657cbe6b2f6c924f6d97fe3c
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2017
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
| AppKey |Identificador exclusivo do aplicativo |123 |
| ApplicationId |Identificador exclusivo do aplicativo – semelhante ao AppKey, mas essa chave é um natural. |b66bc706-ffff-7437-0340-032819502773 |
| Revisão |A versão como mencionada pelo administrador durante o carregamento do binário |2 |
| Título |Título do aplicativo |Excel |
| Editor |Editor do aplicativo |Microsoft |
| UploadState |Estado de upload do aplicativo |1 |
| AppTypeKey |Referência ao AppType descrito na próxima seção. | |
| VppProgramTypeKey |Referência ao VppProgramType descrito abaixo | |
| CreationTime |A hora da criação esta revisão |23/11/2016 12:00:00 AM |
| ModifiedTime |Última vez em que qualquer coisa relacionada a esta revisão foi alterada |23/11/2016 12:00:00 AM |
| Tamanho |Tamanho do binário | |
| StartDateInclusiveUTC |Data e hora em UTC quando a revisão desse aplicativo foi criada no data warehouse |23/11/2016 12:00:00 AM |
| EndDateExclusiveUTC |Data e hora em UTC em que a revisão desse aplicativo se tornou obsoleta |23/11/2016 12:00:00 AM |
| IsCurrent |Indica se a versão desse aplicativo está atualizada ou não no data warehouse |Verdadeiro/Falso |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que a versão desse aplicativo foi modificada no data warehouse |23/11/2016 12:00:00 AM |

## <a name="appinstallertypes"></a>AppInstallerTypes

A entidade **AppInstallerTypes** lista a origem da instalação de um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| AppTypeID |ID do tipo |
| AppTypeKey |Chave substituta para a chave |
| AppTypeName |Tipo de aplicativo |

## <a name="example"></a>Exemplo

| AppTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Aplicativos da loja Android |Um aplicativo da loja Android |
| 1 |Aplicativos LOB para Android |Um aplicativo de linha de negócios Android |
| 2 |Aplicativo gerenciado da loja do Android (MAM) |Um aplicativo da loja Android que tem o gerenciamento habilitado |
| 3 |Aplicativo da loja iOS |Um aplicativo da loja iOS |
| 4 |Aplicativo LOB para iOS |Um aplicativo de linha de negócios para iOS |
| 5 |Aplicativo gerenciado de loja do iOS (MAM?) |Um aplicativo da loja iOS que tem o gerenciamento habilitado |
| 6 |O365 Pro Plus Suite |O Office 365 Pro Plus Suite para Windows 10 |
| 7 |Aplicativo Web |Um aplicativo Web |
| 8 |Aplicativo da loja do Windows Phone 8.1 |Um aplicativo da loja do Windows Phone 8.1 |
| 9 |Aplicativo da Windows Store |Um aplicativo da Windows Store |
| 10 |Aplicativos LOB para Windows |Um aplicativo de linha de negócios AppX do Windows |
| 11 |Windows Mobile MSI |Um aplicativo de linha de negócios para MSI |
| 12 |Aplicativo LOB para Windows Phone |Um aplicativo de linha de negócios para Windows Phone |

## <a name="applicationtypes"></a>ApplicationTypes

A entidade **ApplicationTypes** lista os tipos possíveis para um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| ApplicationTypeID |ID do tipo |
| ApplicationTypeKey |Chave substituta para a chave |
| ApplicationTypeName |Tipo de aplicativo |

## <a name="example"></a>Exemplo

| ApplicationTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Interna |Um aplicativo desenvolvido internamente |
| 1 |DeepLink |Um link para um aplicativo em uma loja de aplicativos |
| 2 |WebLink |Um link para o aplicativo Web |

## <a name="managedsoftwaretypes"></a>ManagedSoftwareTypes

A entidade **ManagedSoftwareTypes** lista os tipos de software gerenciado possíveis para um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| SoftwareTypeID |ID do tipo |
| SoftwareTypeKey |Chave substituta para a chave |
| SoftwareTypeName |Tipo de software |

## <a name="example"></a>Exemplo

| SoftwareTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Área de Trabalho |Um aplicativo de área de trabalho |
| 2 |Atualização |Uma atualização de janela |
| 5 |SideCarAgent | |
| 1 |Celular |Um aplicativo móvel |
| 3 |WebLink |Um webLink |
| 4 |VppDeepLink |Um link para um aplicativo na loja de aplicativos que faz parte de um VPP (Programa de compra de volume) |

## <a name="vppprogramtypes"></a>VppProgramTypes

A entidade **VppProgramTypes** lista os possíveis tipos de programa VPP para um aplicativo.

| Propriedade  | Descrição |
|---------|------------|
| VppProgramTypeID |ID do tipo |
| VppProgramTypeKey |Chave substituta para a chave |
| VppProgramTypeName |Tipo de programa Vpp |

## <a name="example"></a>Exemplo

| VppProgramID  | Nome | Descrição |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 |Microsoft |Programa VPP da Microsoft |
| 00000000-0000-0000-0000-000000000000 |Ainda não disponível |Valor padrão, Não VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B |Apple |Programa VPP da Apple |
