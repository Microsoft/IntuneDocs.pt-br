---
title: "Política | Microsoft Docs"
description: "Tópico de referência para a categoria de Política de coleções de entidade na API Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6af0ff1f463c153e62f6df63ce811076c5f692f2
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2017
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
| PolicyKey |Chave exclusiva para representar a política no data warehouse |123 |
| PolicyId |Identificador exclusivo da Política no data warehouse |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Nome da política |"Linha de base do Windows 10" |
| PolicyVersion |Versão da política. Quando a política for editada ou alterada, é criada uma versão mais recente. |1, 2, 3 |
| IsDeleted |Indica se o registro da Política foi atualizado.  Verdadeiro – a política tem um novo registro com campos atualizados. Falso – o registro mais recente para a política. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC quando essa política foi criada no data warehouse |23/11/2016 12:00:00 AM |
| DeletedDateUTC |Data e hora em UTC quando IsDeleted foi alterado para Verdadeiro |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Data e hora em UTC quando a política foi modificada pela última vez no data warehouse |23/11/2016 12:00:00 AM |

## <a name="policytype"></a>PolicyType

A entidade **PolicyType** lista os tipos de perfis de configuração do dispositivo, perfis de configuração do aplicativo e políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| PolicyTypeId |Identificador exclusivo da política no sistema de origem |123 |
| PolicyTypeKey |Identificador exclusivo da política no data warehouse |1 |
| PolicyTypeName |Nome do tipo de política. |Política de conformidade do Windows 10 |

## <a name="deviceconfiguration"></a>DeviceConfiguration

A entidade **DeviceConfigurationProfileDeviceActivity** lista o número de dispositivos com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um dispositivo estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade lista quantos dispositivos estão em qual estado em um determinado dia nos últimos 30 dias.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data quando o check-in do Perfil de configuração do dispositivo foi registrado no data warehouse |20160703 |
| Pending (Pendente) |Número de Dispositivos exclusivos no estado pendente |123 |
| Bem-sucedido |Número de Dispositivos exclusivos no estado de êxito |12 |
| Erro |Número de Dispositivos exclusivos no estado de erro |10 |
| Failed (Falha) |Número de Dispositivos exclusivos no estado com falha |2 |

## <a name="userconfiguration"></a>UserConfiguration

A entidade **UserConfigurationProfileDeviceActivity** lista o número de usuários com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um usuário estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito, enquanto o outro estiver em um estado de erro, poderemos contar o usuário no estado de erro.  A entidade **UserConfigurationProfileDeviceActivity** lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data quando o check-in do Perfil de configuração do dispositivo foi registrado no data warehouse |20160703 |
| Pending (Pendente) |Número de Usuários exclusivos no estado pendente |123 |
| Bem-sucedido |Número de Usuários exclusivos no estado de êxito |12 |
| Erro |Número de Usuários exclusivos no estado de erro |10 |
| Failed (Falha) |Número de Usuários exclusivos no estado com falha |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

A entidade **PolicyTypeActivity** lista o número acumulativo de dispositivos com o estado de êxito, pendente, com falha, ou de erro. Ela lista esses estados em relação a um perfil de configuração de dispositivo, perfil de configuração do aplicativo ou política de conformidade por dia.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse |20160703 |
| PolicyKey |Chave de política, pode ser unida com a Política para obter o policyName |Linha de base do Windows 10 |
| PolicyTypeKey |Tipo de Chave de política, pode ser unido com o Tipo de política para obter o nome do tipo de política |Política de Windows10Compliance |
| Pending (Pendente) |Número de dispositivos exclusivos no estado pendente |123 |
| Bem-sucedido |Número de dispositivos exclusivos no estado de êxito |12 |
| Erro |Número de dispositivos exclusivos no estado de erro |10 |
| Falha - |Número de dispositivos exclusivos no estado com falha |2 |