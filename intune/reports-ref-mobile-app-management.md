---
title: MAM (Gerenciamento de Aplicativo Móvel)
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria de Gerenciamento de aplicativos móveis de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: eb9f63199063db34361c7d463b8cef37bb8bfa1f
ms.sourcegitcommit: 21db583d6a9d3c15a8a8ee5579309dff1cfe1f8b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2018
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Referência para entidades de MAM (gerenciamento de aplicativo móvel)

A categoria **Gerenciamento de aplicativo móvel** contém entidades para aplicativos móveis, como:

  -  Aplicativos
  -  Instâncias
  -  Status de check-in
  -  Status de integridade
  -  Status de política
  -  Status do registro
  -  Tipos de plataforma

## <a name="mamapplication"></a>MamApplication

A entidade **MamApplication** lista aplicativos de linha de negócios (LOB) que são gerenciados pelo gerenciamento de aplicativo móvel (MAM) sem registro em sua empresa.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| ApplicationKey |Identificador exclusivo do aplicativo de MAM no data warehouse. |123 |
| ApplicationName |Nome do aplicativo de MAM. |"Palavra" |
| ApplicationId |ID do aplicativo de MAM. |b66bc706-ffff-7437-0340-032819502773 |
| IsDeleted |Indica se o registro desse aplicativo MAM foi atualizado. <br>Verdadeiro – o aplicativo MAM tem um novo registro com campos atualizados nesta tabela. <br>Falso – o registro mais recente para este aplicativo MAM. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC em que esse aplicativo de MAM foi criado no data warehouse. |23/11/2016 12:00:00 AM |
| DeletedDateUTC |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que esse aplicativo de MAM foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mamapplicationinstance"></a>MamApplicationInstance

A entidade **MamApplicationInstance** lista aplicativos de Gerenciamento de aplicativo móvel (MAM) gerenciados como instâncias singulares por usuário por dispositivo. Todos os usuários e dispositivos listados com a entidade são protegidos e, portanto, têm pelo menos uma política de MAM atribuída a eles.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| ApplicationInstanceKey |Identificador exclusivo da instância do aplicativo de MAM no data warehouse – chave alternativa. |123 |
| UserId |ID de usuário que tem esse aplicativo de MAM instalado. |b66bc706-ffff-7437-0340-032819502773 |
| ApplicationInstanceId |Identificador exclusivo da instância do aplicativo de MAM – semelhante a ApplicationInstanceKey, mas o identificador é uma chave natural. |b66bc706-ffff-7437-0340-032819502773 |
| ApplicationId |ID de aplicativo desse aplicativo MAM |com.microsoft.groupies-daily.<IOS> |
| ApplicationVersion |Versão deste aplicativo de MAM. |2 |
| CreatedDate |Data em que este registro da instância do aplicativo MAM foi criado. O valor pode ser nulo. |23/11/2016 12:00:00 AM |
| Plataforma |Plataforma do dispositivo no qual este aplicativo de MAM está instalado. |2 |
| PlatformVersion |Versão da plataforma do dispositivo no qual este aplicativo de MAM está instalado. |2.2 |
| SdkVersion |A versão do SDK do MAM com o qual esse aplicativo de MAM foi encapsulado. |3.2 |
| DeviceId |ID do dispositivo no qual este aplicativo de MAM está instalado. |b66bc706-ffff-7437-0340-032819502773 |
| DeviceName |Nome do dispositivo no qual este aplicativo de MAM está instalado. |"MyDevice" |
| IsDeleted |Indica se o registro de instância desse aplicativo MAM foi atualizado. <br>Verdadeiro – a instância desse aplicativo MAM tem um novo registro com campos atualizados nesta tabela. <br>Falso – o registro mais recente para a instância deste aplicativo MAM. |Verdadeiro/Falso |
| StartDateInclusiveUtc |Data e hora em UTC em que a instância desse aplicativo de MAM foi criada no data warehouse. |23/11/2016 12:00:00 AM |
| DeletedDateUtc |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUtc |Data e hora em UTC em que a instância desse aplicativo de MAM foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mamcheckin"></a>MamCheckin

A entidade **MamCheckin** representa os dados reunidos quando uma instância de aplicativo de Gerenciamento de aplicativo móvel (MAM) foi marcada com o Intune Service. 

> [!Note]  
> Quando uma instância do aplicativo faz check-in várias vezes ao dia, o data warehouse a armazena como se fosse um único check-in.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data em que o check-in do aplicativo de MAM foi registrado no data warehouse. | 20160703 |
| ApplicationInstanceKey |Chave da instância do aplicativo associada ao check-in desse aplicativo de MAM. |5/2/1900 12:00:00 AM |
| UserKey |Chave do usuário associada ao check-in desse aplicativo de MAM. |1/12/1900 12:00:00 AM |
| ApplicationKey |Chave do aplicativo de MAM que fez check-in. |1/10/1900 12:00:00 AM |
| DeviceHealthKey |Chave do DeviceHealth associada ao check-in desse aplicativo de MAM. |1/2/1900 12:00:00 AM |
| PlatformKey |Representa a plataforma do dispositivo associado ao check-in desse aplicativo de MAM. |1/1/1900 12:00:00 AM |
| EffectiveAppliedPolicyKey |Representa a política aplicada efetivada associada ao aplicativo MAM que fez check-in. Uma política aplicada efetivada resulta da mesclagem de todas as políticas relevantes para um determinado aplicativo e usuário. |5/2/1900 12:00:00 AM |
| LastCheckInDate |Data e hora em que este aplicativo MAM fez check-in pela última vez. O valor pode ser nulo. |23/11/2016 12:00:00 AM |

## <a name="mamdevicehealth"></a>MamDeviceHealth

A entidade **MamDeviceHealth** representa os dispositivos que têm políticas de Gerenciamento de aplicativo móvel (MAM) implantadas neles, mesmo que estejam desbloqueados.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| DeviceHealthKey |Identificador exclusivo do dispositivo e sua integridade associada no data warehouse – chave alternativa. |1/1/1900 12:00:00 AM |
| DeviceHealth |Identificador exclusivo do dispositivo e sua integridade associada – semelhante a DeviceHealthKey, mas o identificador é uma chave natural. |1/1/1900 12:00:00 AM |
| DeviceHealthName |Representa o status do dispositivo. <br>Não disponível – não há informações sobre este dispositivo. <br>Íntegro – o dispositivo não está desbloqueado. <br>Não íntegro – o dispositivo está desbloqueado. |Não disponível Íntegro Não íntegro |
| RowLastModifiedDateTimeUtc |Data e hora em UTC em que a Integridade desse dispositivo de MAM específico foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mameffectivepolicy"></a>MamEffectivePolicy

A entidade **MamEffectivePolicy** lista todas as políticas efetivas de Gerenciamento de aplicativo móvel (MAM) aplicadas em sua organização. Uma política aplicada efetivada resulta da mesclagem de todas as políticas relevantes para um determinado aplicativo e usuário.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| EffectivePolicyKey |Identificador exclusivo da política efetiva de MAM no data warehouse. |2 |
| RealPolicyKey |Identificador exclusivo da política de MAM criada por profissionais de TI. |1 |
| RowCreatedDateTimeUtc |Data e hora em UTC em que essa política efetiva de MAM foi criada no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mamglobalapplication"></a>MamGlobalApplication

A entidade **MamGlobalApplication** lista aplicativos da loja que são gerenciados pelo Gerenciamento de aplicativo móvel (MAM) sem registro em sua empresa.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| ApplicationKey |Identificador exclusivo do aplicativo da loja no data warehouse, conhecido como chave substituta. |123 |
| ApplicationId |Identificador exclusivo do aplicativo da loja. O identificador é semelhante ao ApplicationKey, mas é uma chave natural. |com.microsoft.skydrive.<ios> |
| ApplicationName |Nome do aplicativo global MAM. |Skydrive |
| RowLastModifiedDateTimeUtc |Data e hora em UTC em que esse Aplicativo global MAM específico foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mamplatform"></a>MamPlatform

A entidade **MamPlatform** lista nomes e tipos de plataforma nos quais um aplicativo de Gerenciamento de aplicativo móvel (MAM) foi instalado.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| PlatformKey |Identificador exclusivo da plataforma no data warehouse – chave alternativa. |123 |
| Plataforma |Identificador exclusivo da plataforma – semelhante a PlatformKey, mas é uma chave natural. |123 |
| PlatformName |Nome da plataforma |Não disponível <br>Nenhum <br>Windows <br>IOS <br>Android. |
| RowLastModifiedDateTimeUtc |Data e hora em UTC em que essa plataforma foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |
