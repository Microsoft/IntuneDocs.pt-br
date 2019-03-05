---
title: Referência para entidades de política
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria de Política de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/14/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: e28f5b7a37e1ed21c4680a57098bdd0a43a79346
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57238397"
---
# <a name="reference-for-policy-entities"></a>Referência para entidades de política

A categoria **Política** contém entidades para dispositivos móveis que rastreiam informações como:

  -  Inventário de perfis de configuração do dispositivo, perfis de configuração do aplicativo e as políticas de conformidade  
  -  Número de dispositivos com o estado de êxito, pendente, com falha, ou de erro por dia  
  -  Número de usuários com o estado de êxito, pendente, com falha, ou de erro por dia  
  -  Número acumulativo de dispositivos com o estado de êxito, pendente, com falha, ou de erro  

## <a name="policy"></a>Política

A entidade **Política** lista perfis de configuração do dispositivo, perfis de configuração do aplicativo e as políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| PolicyKey |Chave exclusiva para representar a política no data warehouse. |123 |
| PolicyId |Identificador exclusivo da política no data warehouse. |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Nome da política. |"Linha de base do Windows 10" |
| PolicyVersion |Versão da política. Quando a política for editada ou alterada, é criada uma versão mais recente. |1, 2, 3 |
| IsDeleted |Indica se o registro da Política foi atualizado.  <br>Verdadeiro – a política tem um novo registro com campos atualizados. <br>Falso – o registro mais recente para a política. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC e que a política foi criada no data warehouse. |23/11/2016 12:00:00 AM |
| DeletedDateUTC |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que a política foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="policytype"></a>PolicyType

A entidade **PolicyType** lista os tipos de perfis de configuração do dispositivo, perfis de configuração do aplicativo e políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| PolicyTypeId |Identificador exclusivo da política no sistema de origem. |123 |
| PolicyTypeKey |Identificador exclusivo da política no data warehouse. |1 |
| PolicyTypeName |Nome do tipo de política. |Política de conformidade do Windows 10. |

## <a name="deviceconfiguration"></a>DeviceConfiguration

A entidade **DeviceConfigurationProfileDeviceActivity** lista o número de dispositivos com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um dispositivo estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade lista quantos dispositivos estão em qual estado em um determinado dia nos últimos 30 dias.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse. |20160703 |
| Pending (Pendente) |Número de dispositivos exclusivos no estado pendente. |123 |
| Bem-sucedido |Número de dispositivos exclusivos no estado de êxito. |12 |
| Erro do |Número de dispositivos exclusivos no estado de erro. |10 |
| Failed (Falha) |Número de dispositivos exclusivos no estado de falha. |2 |



A entidade **DeviceConfigurationProfileUserActivity** lista o número de usuários com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um usuário estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito e o outro em um estado de erro, o usuário no estado de erro será contado.  A entidade **DeviceConfigurationProfileUserActivity** lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse. |20160703 |
| Pending (Pendente) |Número de usuários exclusivos no estado pendente. |123 |
| Bem-sucedido |Número de usuários exclusivos no estado de êxito. |12 |
| Erro do |Número de usuários exclusivos no estado de erro. |10 |
| Failed (Falha) |Número de usuários exclusivos no estado de falha. |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

A entidade **PolicyTypeActivity** lista o número acumulativo de dispositivos com o estado de êxito, pendente, com falha, ou de erro. Ela lista esses estados em relação a um perfil de configuração de dispositivo, perfil de configuração do aplicativo ou política de conformidade por dia.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse. |20160703 |
| PolicyKey |Chave de política, pode ser unida com a política para obter o policyName. |Linha de base do Windows 10 |
| PolicyTypeKey |Tipo de chave de política, pode ser unido com o tipo de política para obter o nome do tipo de política. |Política de conformidade do Windows10 |
| Pending (Pendente) |Número de dispositivos exclusivos no estado pendente. |123 |
| Bem-sucedido |Número de dispositivos exclusivos no estado de êxito. |12 |
| Erro do |Número de dispositivos exclusivos no estado de erro. |10 |
| Failed (Falha) |Número de dispositivos exclusivos no estado de falha. |2 |

## <a name="compliance-policy"></a>Política de Conformidade

A Referência de API de Política de Conformidade contém entidades que fornecem informações de status sobre as políticas de conformidade atribuídas aos dispositivos.

### <a name="compliancepolicystatusdeviceactivities"></a>CompliancePolicyStatusDeviceActivities

A tabela a seguir resume o status de atribuição de políticas de conformidade para dispositivos. Ela lista a contagem de dispositivos encontrados em cada estado de conformidade.


|Propriedade     |Descrição  |Exemplo  |
|---------|---------|---------|
|DateKey  |Chave de data quando o resumo foi criado para a política de conformidade.|20161204 |
|Unknown  |Número de dispositivos que estão offline ou falharam ao se comunicar com o Intune ou com o Azure AD por outras razões. |5|
|NotApplicable      |Número de dispositivos em que as políticas de conformidade do dispositivo direcionadas pelo administrador não são aplicáveis.|201 |
|Compatível      |Número de dispositivos que aplicaram com êxito uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador. |4083 |
|InGracePeriod      |Número de dispositivos que não estão em conformidade, mas estão em um período de carência definido pelo administrador. |57|
|NonCompliant      |Número de dispositivos que falharam ao aplicar uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador ou em que o usuário não está em conformidade com as políticas direcionadas pelo administrador.|43 |
|Erro do      |Número de dispositivos que falharam ao se comunicar com o Intune ou com o Azure AD e retornaram uma mensagem de erro. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>CompliancePolicyStatusDevicePerPolicyActivities 

A tabela a seguir resume o status de atribuição de políticas de conformidade para dispositivos por política e por tipo de política. Ela lista a contagem de dispositivos encontrados em cada estado de conformidade para cada política de conformidade atribuída.



|Propriedade  |Descrição  |Exemplo  |
|---------|---------|---------|
|DateKey  |Chave de data quando o resumo foi criado para a política de conformidade.|20161219|
|PolicyKey     |Chave para a política de conformidade para a qual o resumo foi criado. |10178 |
|PolicyPlatformKey      |Chave para o tipo de plataforma da política de conformidade para a qual o resumo foi criado.|5|
|Unknown     |Número de dispositivos que estão offline ou falharam ao se comunicar com o Intune ou com o Azure AD por outras razões.|13|
|NotApplicable     |Número de dispositivos em que as políticas de conformidade do dispositivo direcionadas pelo administrador não são aplicáveis.|3|
|Compatível      |Número de dispositivos que aplicaram com êxito uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador. |45|
|InGracePeriod      |Número de dispositivos que não estão em conformidade, mas estão em um período de carência definido pelo administrador. |3|
|NonCompliant      |Número de dispositivos que falharam ao aplicar uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador ou em que o usuário não está em conformidade com as políticas direcionadas pelo administrador.|7|
|Erro do      |Número de dispositivos que falharam ao se comunicar com o Intune ou com o Azure AD e retornaram uma mensagem de erro. |3|

### <a name="policyplatformtypes"></a>PolicyPlatformTypes

A tabela a seguir contém os tipos de plataforma de todas as políticas atribuídas. Os tipos de plataformas de políticas que nunca foram atribuídos a nenhum dispositivo não estão presentes nesta tabela.


|Propriedade  |Descrição  |Exemplo  |
|---------|---------|---------|
|PolicyPlatformTypeKey      |A chave exclusiva para o tipo de plataforma de política. |20170519 |
|PolicyPlatformTypeId      |O identificador exclusivo para o tipo de plataforma de política.|1|
|PolicyPlatformTypeName      |O nome para o tipo de plataforma de política.|AndroidForWork |

### <a name="policydeviceactivity"></a>PolicyDeviceActivity

A tabela a seguir lista o número de dispositivos com o estado de êxito, pendente, com falha, ou de erro por dia. O número reflete os dados por perfis de Tipo de Política. Por exemplo, se um dispositivo estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade PolicyDeviceActivity lista quantos dispositivos estão em qual estado em um determinado dia nos últimos 30 dias.

|Propriedade  |Descrição  |Exemplo  |
|---------|---------|---------|
|DateKey|Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse.|20160703|
|Pending (Pendente)|Número de dispositivos exclusivos no estado pendente.|123|
|Bem-sucedido|Número de dispositivos exclusivos no estado de êxito.|12|
PolicyKey|Chave de política, pode ser unida com a política para obter o policyName.|Linha de base do Windows 10|
|Erro do|Número de dispositivos exclusivos no estado de erro.|10|
|Failed (Falha)|Número de dispositivos exclusivos no estado de falha.|2|

### <a name="policyuseractivity"></a>PolicyUserActivity 

A tabela a seguir lista o número de usuários com o estado de êxito, pendente, com falha, ou de erro por dia. O número reflete os dados por perfis de Tipo de Política. Por exemplo, se um usuário estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito e o outro em um estado de erro, o usuário no estado de erro será contado. A entidade PolicyUserActivity lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias.


| Propriedade  |                                         Descrição                                         |       Exemplo       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  DateKey  | Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse. |      20160703       |
|  Pending (Pendente)  |                         Número de dispositivos exclusivos no estado pendente.                          |         123         |
| Bem-sucedido |                         Número de dispositivos exclusivos no estado de êxito.                          |         12          |
| PolicyKey |                Chave de política, pode ser unida com a política para obter o policyName.                 | Linha de base do Windows 10 |
|   Erro do   |                          Número de dispositivos exclusivos no estado de erro.                           |         10          |

