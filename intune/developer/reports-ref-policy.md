---
title: Referência para entidades de política
titleSuffix: Microsoft Intune
description: Tópico de referência para a categoria de Política de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 64fc1bab596715be80fd3a91c003cac1176fe787
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490267"
---
# <a name="reference-for-policy-entities"></a>Referência para entidades de política

A categoria **policies** contém entidades para dispositivos móveis que rastreiam informações como:

- Inventário de perfis de configuração do dispositivo, perfis de configuração do aplicativo e as políticas de conformidade  
- Número de dispositivos com o estado de êxito, pendente, com falha, ou de erro por dia  
- Número de usuários com o estado de êxito, pendente, com falha, ou de erro por dia  
- Número acumulativo de dispositivos com o estado de êxito, pendente, com falha, ou de erro  

## <a name="policies"></a>políticas

A entidade **policy** lista perfis de configuração do dispositivo, perfis de configuração do aplicativo e as políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| policyKey |Chave exclusiva para representar a política no data warehouse. |123 |
| policyId |Identificador exclusivo da política no data warehouse. |b66bc706-ffff-7437-0340-032819502773 |
| policyName |Nome da política. |"Linha de base do Windows 10" |
| policyVersion |Versão da política. Quando a política for editada ou alterada, é criada uma versão mais recente. |1, 2, 3 |
| isDeleted |Indica se o registro da Política foi atualizado.  <br>Verdadeiro – a política tem um novo registro com campos atualizados. <br>Falso – o registro mais recente para a política. |Verdadeiro/Falso |
| startDateInclusiveUTC |Data e hora em UTC e que a política foi criada no data warehouse. |23/11/2016 12:00:00 AM |
| deletedDateUTC |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| rowLastModifiedDateTimeUTC |Data e hora em UTC em que a política foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="policytypes"></a>policyTypes

A entidade **policyType** lista os tipos de perfis de configuração do dispositivo, perfis de configuração do aplicativo e políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| policyTypeId |Identificador exclusivo da política no sistema de origem. |123 |
| policyTypeKey |Identificador exclusivo da política no data warehouse. |1 |
| policyTypeName |Nome do tipo de política. |Política de conformidade do Windows 10. |

## <a name="device-configuration"></a>Configuração de dispositivo

A entidade **deviceConfigurationProfileDeviceActivity** lista o número de **dispositivos** com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um **dispositivo** estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade lista quantos dispositivos estão em qual estado em um determinado dia nos últimos 30 dias.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| dateKey |Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse. |20160703 |
| pending |Número de dispositivos exclusivos no estado pendente. |123 |
| bem-sucedido |Número de dispositivos exclusivos no estado de êxito. |12 |
| erro |Número de dispositivos exclusivos no estado de erro. |10 |
| falha |Número de dispositivos exclusivos no estado de falha. |2 |

A entidade **deviceConfigurationProfileUserActivity** lista o número de **usuários** com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um **usuário** estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito e o outro em um estado de erro, o usuário no estado de erro será contado.  A entidade **deviceConfigurationProfileUserActivity** lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| dateKey |Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse. |20160703 |
| pending |Número de usuários exclusivos no estado pendente. |123 |
| bem-sucedido |Número de usuários exclusivos no estado de êxito. |12 |
| erro |Número de usuários exclusivos no estado de erro. |10 |
| falha |Número de usuários exclusivos no estado de falha. |2 |

## <a name="policytypeactivities"></a>policyTypeActivities

A entidade **policyTypeActivity** lista o número acumulativo de dispositivos com o estado de êxito, pendente, com falha, ou de erro. Ela lista esses estados em relação a um perfil de configuração de dispositivo, perfil de configuração do aplicativo ou política de conformidade por dia.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| dateKey |A dateKey quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse. |20160703 |
| policyKey |A policyKey, pode ser unida com a política para obter o policyName. |Linha de base do Windows 10 |
| policyTypeKey |Tipo de chave de política, pode ser unido com o tipo de política para obter o nome do tipo de política. |Política de conformidade do Windows10 |
| pending |Número de dispositivos exclusivos no estado pendente. |123 |
| bem-sucedido |Número de dispositivos exclusivos no estado de êxito. |12 |
| erro |Número de dispositivos exclusivos no estado de erro. |10 |
| falha |Número de dispositivos exclusivos no estado de falha. |2 |

## <a name="compliance-policy"></a>Política de Conformidade

A Referência de API de Política de Conformidade contém entidades que fornecem informações de status sobre as políticas de conformidade atribuídas aos dispositivos.

### <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities

A tabela a seguir resume o status de atribuição de políticas de conformidade para dispositivos. Ela lista a contagem de dispositivos encontrados em cada estado de conformidade.


|Propriedade     |Descrição  |Exemplo  |
|---------|---------|---------|
|dateKey  |Chave de data quando o resumo foi criado para a política de conformidade.|20161204 |
|desconhecido  |Número de dispositivos que estão offline ou falharam ao se comunicar com o Intune ou com o Azure AD por outras razões. |5|
|notApplicable      |Número de dispositivos em que as políticas de conformidade do dispositivo direcionadas pelo administrador não são aplicáveis.|201 |
|conformidade      |Número de dispositivos que aplicaram com êxito uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador. |4083 |
|inGracePeriod      |Número de dispositivos que não estão em conformidade, mas estão em um período de carência definido pelo administrador. |57|
|fora de Conformidade      |Número de dispositivos que falharam ao aplicar uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador ou em que o usuário não está em conformidade com as políticas direcionadas pelo administrador.|43 |
|erro      |Número de dispositivos que falharam ao se comunicar com o Intune ou com o Azure AD e retornaram uma mensagem de erro. |3|

### <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities 

A tabela a seguir resume o status de atribuição de políticas de conformidade para dispositivos por política e por tipo de política. Ela lista a contagem de dispositivos encontrados em cada estado de conformidade para cada política de conformidade atribuída.



|Propriedade  |Descrição  |Exemplo  |
|---------|---------|---------|
|dateKey  |Chave de data quando o resumo foi criado para a política de conformidade.|20161219|
|policyKey     |Chave para a política de conformidade para a qual o resumo foi criado. |10178 |
|policyPlatformKey      |Chave para o tipo de plataforma da política de conformidade para a qual o resumo foi criado.|5|
|desconhecido     |Número de dispositivos que estão offline ou falharam ao se comunicar com o Intune ou com o Azure AD por outras razões.|13|
|notApplicable     |Número de dispositivos em que as políticas de conformidade do dispositivo direcionadas pelo administrador não são aplicáveis.|3|
|conformidade      |Número de dispositivos que aplicaram com êxito uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador. |45|
|inGracePeriod      |Número de dispositivos que não estão em conformidade, mas estão em um período de carência definido pelo administrador. |3|
|fora de Conformidade      |Número de dispositivos que falharam ao aplicar uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador ou em que o usuário não está em conformidade com as políticas direcionadas pelo administrador.|7|
|erro      |Número de dispositivos que falharam ao se comunicar com o Intune ou com o Azure AD e retornaram uma mensagem de erro. |3|

### <a name="policyplatformtypes"></a>policyPlatformTypes

A tabela a seguir contém os tipos de plataforma de todas as políticas atribuídas. Os tipos de plataformas de políticas que nunca foram atribuídos a nenhum dispositivo não estão presentes nesta tabela.


|Propriedade  |Descrição  |Exemplo  |
|---------|---------|---------|
|policyPlatformTypeKey      |A chave exclusiva para o tipo de plataforma de política. |20170519 |
|policyPlatformTypeId      |O identificador exclusivo para o tipo de plataforma de política.|1|
|policyPlatformTypeName      |O nome para o tipo de plataforma de política.|AndroidForWork |

### <a name="policydeviceactivities"></a>policyDeviceActivities

A tabela a seguir lista o número de dispositivos com o estado de êxito, pendente, com falha, ou de erro por dia. O número reflete os dados por perfis de Tipo de Política. Por exemplo, se um dispositivo estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade policyDeviceActivity lista quantos dispositivos estão em qual estado em determinado dia nos últimos 30 dias.

|Propriedade  |Descrição  |Exemplo  |
|---------|---------|---------|
|dateKey|Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse.|20160703|
|pending|Número de dispositivos exclusivos no estado pendente.|123|
|Bem-sucedido|Número de dispositivos exclusivos no estado de êxito.|12|
|policyKey|A policyKey, pode ser unida com a política para obter o policyName.|Linha de base do Windows 10|
|erro|Número de dispositivos exclusivos no estado de erro.|10|
|falha|Número de dispositivos exclusivos no estado de falha.|2|

### <a name="policyuseractivities"></a>policyUserActivities

A tabela a seguir lista o número de usuários com o estado de êxito, pendente, com falha, ou de erro por dia. O número reflete os dados por perfis de Tipo de Política. Por exemplo, se um usuário estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito e o outro em um estado de erro, o usuário no estado de erro será contado. A entidade PolicyUserActivity lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias.


| Propriedade  |                                         Descrição                                         |       Exemplo       |
|-----------|---------------------------------------------------------------------------------------------|---------------------|
|  dateKey  | Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse. |      20160703       |
|  pending  |                         Número de dispositivos exclusivos no estado pendente.                          |         123         |
| bem-sucedido |                         Número de dispositivos exclusivos no estado de êxito.                          |         12          |
| policyKey |                 A policyKey, pode ser unida com a política para obter o policyName.                 | Linha de base do Windows 10 |
|   erro   |                          Número de dispositivos exclusivos no estado de erro.                           |         10          |

