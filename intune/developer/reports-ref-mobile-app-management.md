---
title: MAM (Gerenciamento de Aplicativo Móvel)
titleSuffix: Microsoft Intune
description: Tópico de referência para a categoria de Gerenciamento de aplicativos móveis de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 084F11AD-F7BA-45A4-8424-45E6E4564930
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f06d2b4b61d522dced12e5d08cd1e854aefd9de8
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71939937"
---
# <a name="reference-for-mobile-app-management-mam-entities"></a>Referência para entidades de MAM (gerenciamento de aplicativo móvel)

A categoria **Gerenciamento de aplicativo móvel** contém entidades para aplicativos móveis, como:

- Aplicativos
- Instâncias
- Status de check-in
- Status de integridade
- Status de política
- Status do registro
- Tipos de plataforma

## <a name="mamapplications"></a>mamApplications

A entidade **mamApplication** lista aplicativos de linha de negócios (LOB) que são gerenciados pelo gerenciamento de aplicativo móvel (MAM) sem registro em sua empresa.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| mamApplicationKey |Identificador exclusivo do aplicativo MAM. | 432 |
| mamApplicationName |Nome do aplicativo MAM. |Exemplo de Nome de Aplicativo MAM |
| mamApplicationId |ID do aplicativo referente ao aplicativo MAM. | 123 |
| isDeleted |Indica se o registro desse aplicativo MAM foi atualizado. <br>Verdadeiro – o aplicativo MAM tem um novo registro com campos atualizados nesta tabela. <br>Falso – o registro mais recente para este aplicativo MAM. |Verdadeiro/Falso |
| startDateInclusiveUTC |Data e hora em UTC em que esse aplicativo de MAM foi criado no data warehouse. |23/11/2016 12:00:00 AM |
| deletedDateUTC |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| rowLastModifiedDateTimeUTC |Data e hora em UTC em que esse aplicativo de MAM foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |


## <a name="mamapplicationinstances"></a>mamApplicationInstances

A entidade **mamApplicationInstance** lista aplicativos de Gerenciamento de aplicativo móvel (MAM) gerenciados como instâncias singulares por usuário por dispositivo. Todos os usuários e dispositivos listados com a entidade são protegidos e, portanto, têm pelo menos uma política de MAM atribuída a eles.


|          Propriedade          |                                                                                                  Descrição                                                                                                  |               Exemplo                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   applicationInstanceKey   |                                                               Identificador exclusivo da instância do aplicativo de MAM no data warehouse – chave alternativa.                                                                |                 123                  |
|           userId           |                                                                              A ID de usuário que tem esse aplicativo de MAM instalado.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   applicationInstanceId    |                                              Identificador exclusivo da instância do aplicativo de MAM – semelhante a ApplicationInstanceKey, mas o identificador é uma chave natural.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | ID do aplicativo referente ao Aplicativo Mam para o qual esta Instância de Aplicativo Mam foi criada.   | 23/11/2016 12:00:00 AM   |
|     applicationVersion     |                                                                                     Versão deste aplicativo de MAM.                                                                                      |                  2                   |
|        createdDate         |                                                                 Data em que este registro da instância do aplicativo MAM foi criado. O valor pode ser nulo.                                                                 |        23/11/2016 12:00:00 AM        |
|          plataforma          |                                                                          Plataforma do dispositivo no qual este aplicativo de MAM está instalado.                                                                           |                  2                   |
|      platformVersion       |                                                                      Versão da plataforma do dispositivo no qual este aplicativo de MAM está instalado.                                                                       |                 2.2                  |
|         sdkVersion         |                                                                            A versão do SDK do MAM com o qual esse aplicativo de MAM foi encapsulado.                                                                            |                 3.2                  |
| mamDeviceId | ID do dispositivo referente ao dispositivo com o qual a Instância do Aplicativo MAM está associada.   | 23/11/2016 12:00:00 AM   |
| mamDeviceType | Tipo de dispositivo referente ao dispositivo com o qual a Instância do Aplicativo MAM está associada.   | 23/11/2016 12:00:00 AM   |
| mamDeviceName | Nome de dispositivo referente ao dispositivo com o qual a Instância do Aplicativo MAM está associada.   | 23/11/2016 12:00:00 AM   |
|         isDeleted          | Indica se o registro de instância desse aplicativo MAM foi atualizado. <br>Verdadeiro – a instância desse aplicativo MAM tem um novo registro com campos atualizados nesta tabela. <br>Falso – o registro mais recente para a instância deste aplicativo MAM. |              Verdadeiro/Falso              |
|   startDateInclusiveUtc    |                                                              Data e hora em UTC em que a instância desse aplicativo de MAM foi criada no data warehouse.                                                               |        23/11/2016 12:00:00 AM        |
|       deletedDateUtc       |                                                                             Data e hora em UTC em que IsDeleted foi alterado para True.                                                                              |        23/11/2016 12:00:00 AM        |
| rowLastModifiedDateTimeUtc |                                                           Data e hora em UTC em que a instância desse aplicativo de MAM foi modificada pela última vez no data warehouse.                                                            |        23/11/2016 12:00:00 AM        |


## <a name="mamcheckins"></a>mamCheckins

A entidade **mamCheckin** representa os dados reunidos quando uma instância de aplicativo de Gerenciamento de aplicativo móvel (MAM) foi marcada com o Intune Service. 

> [!Note]  
> Quando uma instância do aplicativo faz check-in várias vezes ao dia, o data warehouse a armazena como se fosse um único check-in.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| dateKey |Chave de data em que o check-in do aplicativo de MAM foi registrado no data warehouse. | 20160703 |
| applicationInstanceKey |Chave da instância do aplicativo associada ao check-in desse aplicativo de MAM. | 123 |
| userKey |Chave do usuário associada ao check-in desse aplicativo de MAM. | 4323 |
| mamApplicationKey |Chave de Aplicativo referente ao Aplicativo associado com o check-in do Aplicativo MAM. | 432 |
| deviceHealthKey |Chave do DeviceHealth associada ao check-in desse aplicativo de MAM. | 321 |
| platformKey |Representa a plataforma do dispositivo associado ao check-in desse aplicativo de MAM. |123 |
| effectiveAppliedPolicyKey |Representa a política aplicada efetivada associada ao aplicativo MAM que fez check-in. Uma política aplicada efetivada resulta da mesclagem de todas as políticas relevantes para um determinado aplicativo e usuário. | 322 |
| pastCheckInDate |Data e hora em que este aplicativo MAM fez check-in pela última vez. O valor pode ser nulo. |23/11/2016 12:00:00 AM |


## <a name="mamdevicehealth"></a>mamDeviceHealth

A entidade **mamDeviceHealth** representa os dispositivos que têm políticas de Gerenciamento de aplicativo móvel (MAM) implantadas neles, mesmo que estejam desbloqueados.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| deviceHealthKey |Identificador exclusivo do dispositivo e sua integridade associada no data warehouse – chave alternativa. |123 |
| deviceHealth |Identificador exclusivo do dispositivo e sua integridade associada – semelhante a DeviceHealthKey, mas o identificador é uma chave natural. |b66bc706-ffff-7777-0340-032819502773 |
| deviceHealthName |Representa o status do dispositivo. <br>Não disponível – não há informações sobre este dispositivo. <br>Íntegro – o dispositivo não está desbloqueado. <br>Não íntegro – o dispositivo está desbloqueado. |Não disponível Íntegro Não íntegro |
| rowLastModifiedDateTimeUtc |Data e hora em UTC em que a Integridade desse dispositivo de MAM específico foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mameffectivepolicies"></a>mamEffectivePolicies

A entidade **mamEffectivePolicy** lista todas as políticas efetivas de Gerenciamento de aplicativo móvel (MAM) aplicadas em sua organização. Uma política aplicada efetivada resulta da mesclagem de todas as políticas relevantes para um determinado aplicativo e usuário.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| effectivePolicyKey |Identificador exclusivo da política efetiva de MAM no data warehouse. |2 |
| realPolicyKey |Identificador exclusivo da política de MAM criada por profissionais de TI. |1 |
| rowCreatedDateTimeUtc |Data e hora em UTC em que essa política efetiva de MAM foi criada no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mamplatforms"></a>mamPlatforms

A entidade **mamPlatform** lista nomes e tipos de plataforma nos quais um aplicativo de Gerenciamento de aplicativo móvel (MAM) foi instalado.


|          Propriedade          |                                    Descrição                                    |                         Exemplo                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        platformKey         |     Identificador exclusivo da plataforma no data warehouse – chave alternativa.      |                           123                           |
|          plataforma          | Identificador exclusivo da plataforma – semelhante a PlatformKey, mas é uma chave natural. |                           123                           |
|        platformName        |                                   Nome da plataforma                                   | Não disponível <br>Nenhum <br>Windows <br>IOS <br>Android. |
| rowLastModifiedDateTimeUtc | Data e hora em UTC em que essa plataforma foi modificada pela última vez no data warehouse.  |                 23/11/2016 12:00:00 AM                  |

