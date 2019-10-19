---
title: Dispositivos – Intune Data Warehouse
titleSuffix: Microsoft Intune
description: Tópico de referência para a categoria de Dispositivos de coleções de entidade na API Intune Data Warehouse.
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
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 36407bda1f74d0c4601f78cedc2af5426e944fee
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72503425"
---
# <a name="reference-for-devices-entities"></a>Referência para entidades de dispositivos

A categoria **devices** contém entidades para dispositivos móveis que rastreiam informações como:

- Tipo de dispositivo
- Status de registro e registro do dispositivo
- Propriedade do dispositivo
- Estado de gerenciamento de dispositivo
- Status de associação de dispositivo para Azure AD
- Status do registro
- Informações históricas sobre o dispositivo
- Inventário de aplicativos no dispositivo

## <a name="devicetypes"></a>deviceTypes

A entidade **deviceTypes** representa o tipo de dispositivo referenciado por outras entidades do data warehouse. O tipo de dispositivo geralmente descreve o modelo do dispositivo, o fabricante ou uma combinação de ambos.

| Propriedade  | Descrição |
|---------|------------|
| deviceTypeID |Identificador exclusivo do tipo de dispositivo |
| deviceTypeKey |Identificador exclusivo do tipo de dispositivo no data warehouse – chave substituta |
| deviceTypeName |Tipo de dispositivo |

### <a name="example"></a>Exemplo

| deviceTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Área de Trabalho |Dispositivo do Windows Desktop |
| 1 |WindowsRT |Dispositivo WindowsRT |
| 2 |WinMO6 |Dispositivo Windows Mobile 6.0 |
| 3 |Nokia |Dispositivo Nokia |
| 4 |WindowsPhone |Dispositivo Windows Phone |
| 5 |Mac |Dispositivo Mac |
| 6 |WinCE |Dispositivo Windows CE |
| 7 |WinEmbedded |Dispositivo Windows Embedded |
| 8 |IPhone |Dispositivo iPhone |
| 9 |IPad |Dispositivo iPad |
| 10 |IPod |Dispositivo iPod |
| 11 |Android |Dispositivo gerenciado Android usando o administrador do dispositivo |
| 12 |ISocConsumer |Dispositivo iSoc Consumer |
| 14 |MacMDM |Dispositivo Mac OS X gerenciado com o agente MDM interno |
| 15 |HoloLens |Dispositivos do HoloLens |
| 16 |SurfaceHub |Dispositivo Surface Hub |
| 17 |AndroidForWork |Gerenciado pelo dispositivo Android usando o proprietário do perfil do Android |
| 100 |BlackBerry |Dispositivo Blackberry |
| 101 |Palm |Dispositivo Palm |
| 255 |Unknown |Tipo de dispositivo desconhecido |

## <a name="enrollmentactivities"></a>enrollmentActivities 
A entidade **enrollmentActivity** indica a atividade de um registro de dispositivo.

| Propriedade                      | Descrição                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Chave da data em que essa atividade de registro foi gravada.               |
| deviceEnrollmentTypeKey       | Chave do tipo do registro.                                        |
| deviceTypeKey                 | Chave do tipo de dispositivo.                                                |
| enrollmentEventStatusKey      | Chave do status indicando o êxito ou a falha do registro.    |
| enrollmentFailureCategoryKey  | Chave da categoria de falha do registro (se o registro falhou).        |
| enrollmentFailureReasonKey    | Chave do motivo da falha do registro (se o registro falhou).          |
| osVersion                     | A versão do sistema operacional do dispositivo.                               |
| count                         | Contagem total de atividades de registro correspondentes às classificações acima.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
A entidade **enrollmentEventStatus** indica o resultado de um registro de dispositivo.

| Propriedade                   | Descrição                                                                       |
|----------------------------|-----------------------------------------------------------------------------------|
| enrollmentEventStatusKey   | Identificador exclusivo do status de registro no data warehouse (chave alternativa)  |
| enrollmentEventStatusName  | O nome do status de registro. Veja exemplos abaixo.                            |

### <a name="example"></a>Exemplo

| enrollmentEventStatusName  | Descrição                            |
|----------------------------|----------------------------------------|
| Êxito                    | Um registro de dispositivo bem-sucedido         |
| Failed (Falha)                     | Um registro de dispositivo com falha             |
| Não disponível              | O status de registro é não disponível.  |

## <a name="enrollmentfailurecategories"></a>enrollmentFailureCategories 
A entidade **EnrollmentFailureCategory** indica o motivo da falha de um registro de dispositivo. 

| Propriedade                       | Descrição                                                                                 |
|--------------------------------|---------------------------------------------------------------------------------------------|
| enrollmentFailureCategoryKey   | Identificador exclusivo da categoria de falha do registro no data warehouse (chave alternativa)  |
| enrollmentFailureCategoryName  | O nome da categoria de falha do registro. Veja exemplos abaixo.                            |

### <a name="example"></a>Exemplo

| enrollmentFailureCategoryName   | Descrição                                                                                                   |
|---------------------------------|---------------------------------------------------------------------------------------------------------------|
| Não Aplicável                  | A categoria de falha do registro não é aplicável.                                                            |
| Não disponível                   | A categoria de falha do registro não está disponível.                                                             |
| Unknown                         | Erro desconhecido.                                                                                                |
| Autenticação                  | Falha na autenticação.                                                                                        |
| Authorization                   | A chamada foi autenticada, mas não está autorizada a se registrar.                                                         |
| AccountValidation               | Falha ao validar a conta para o registro. (Conta bloqueada, registro não habilitado)                      |
| UserValidation                  | Não foi possível validar o usuário. (O usuário não existe; licença ausente)                                           |
| DeviceNotSupported              | Não há suporte para o dispositivo no gerenciamento de dispositivo móvel.                                                         |
| InMaintenance                   | A conta está em manutenção.                                                                                    |
| BadRequest                      | O cliente enviou uma solicitação que não é compreendida pelo serviço nem compatível com ele.                                        |
| FeatureNotSupported             | Não há suporte para os recursos usados por este registro nesta conta.                                        |
| EnrollmentRestrictionsEnforced  | As restrições de registro configuradas pelo administrador bloquearam esse registro.                                          |
| ClientDisconnected              | O cliente atingiu o tempo limite ou o registro foi anulado pelo usuário final.                                                        |
| UserAbandonment                 | O registro foi abandonado pelo usuário final. (O usuário final iniciou a integração, mas não conseguiu concluí-la em tempo hábil)  |

## <a name="enrollmentfailurereasons"></a>enrollmentFailureReasons  
A entidade **EnrollmentFailureReason** indica um motivo mais detalhado para uma falha de registro de dispositivo em determinada categoria de falha.  

| Propriedade                     | Descrição                                                                               |
|------------------------------|-------------------------------------------------------------------------------------------|
| enrollmentFailureReasonKey   | Identificador exclusivo do motivo da falha do registro no data warehouse (chave alternativa)  |
| enrollmentFailureReasonName  | O nome do motivo da falha do registro. Veja exemplos abaixo.                            |

### <a name="example"></a>Exemplo

| enrollmentFailureReasonName      | Descrição                                                                                                                                                                                            |
|----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Não Aplicável                   | O motivo da falha do registro não é aplicável.                                                                                                                                                       |
| Não disponível                    | O motivo da falha do registro não está disponível.                                                                                                                                                        |
| Unknown                          | Erro Desconhecido.                                                                                                                                                                                         |
| UserNotLicensed                  | O usuário não foi encontrado no Intune ou não tem uma licença válida.                                                                                                                                     |
| UserUnknown                      | O usuário não é conhecido para o Intune.                                                                                                                                                                           |
| BulkAlreadyEnrolledDevice        | Apenas um usuário pode registrar um dispositivo. Este dispositivo foi registrado anteriormente por outro usuário.                                                                                                                |
| EnrollmentOnboardingIssue        | A autoridade de MDM (gerenciamento de dispositivo móvel) do Intune ainda não está configurada.                                                                                                                                 |
| AppleChallengeIssue              | A instalação do perfil de gerenciamento do iOS está atrasada ou falhou.                                                                                                                                         |
| AppleOnboardingIssue             | Um Apple MDM Push Certificate é necessário para se registrar no Intune.                                                                                                                                       |
| DeviceCap                        | O usuário tentou registrar mais dispositivos do que o máximo permitido.                                                                                                                                        |
| AuthenticationRequirementNotMet  | O serviço de registro do Intune não pôde autorizar esta solicitação.                                                                                                                                            |
| UnsupportedDeviceType            | Este dispositivo não atende aos requisitos mínimos para registro do Intune.                                                                                                                                  |
| EnrollmentCriteriaNotMet         | Este dispositivo não pôde se registrar devido a uma regra de restrição de registro configurada.                                                                                                                          |
| BulkDeviceNotPreregistered       | O IMEI (identificador internacional de equipamento móvel) ou o número de série do dispositivo não foi encontrado.  Sem esse identificador, os dispositivos são reconhecidos como dispositivos pessoais que atualmente estão bloqueados.  |
| FeatureNotSupported              | O usuário estava tentando acessar um recurso que ainda não foi liberado para todos os clientes ou que não é compatível com a configuração do Intune.                                                            |
| UserAbandonment                  | O registro foi abandonado pelo usuário final. (O usuário final iniciou a integração, mas não conseguiu concluí-la em tempo hábil)                                                                                           |
| APNSCertificateExpired           | Os dispositivos Apple não podem ser gerenciados com um Apple MDM Push Certificate expirado.                                                                                                                            |
## <a name="ownertypes"></a>ownerTypes

A entidade **enrollmentType** indica se um dispositivo é corporativo, pessoal ou desconhecido.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| ownerTypeID |Identificador exclusivo do tipo de proprietário. | |
| ownerTypeKey |Identificador exclusivo do tipo de proprietário no data warehouse – chave alternativa. | |
| ownerTypeName |Representa o tipo de proprietário dos dispositivos:  <br>Corporativo – o dispositivo é de propriedade da empresa. <br>Pessoal – o dispositivo de propriedade pessoal (BYOD).  <br>Desconhecido – não há informações sobre este dispositivo. |Corporativo Pessoal Desconhecido |

> [!Note]  
> Para o `ownerTypeName` no Azure AD durante a criação de Grupos Dinâmicos para dispositivos, você precisará definir o valor do filtro `deviceOwnership` como `Company`. Para obter mais informações, veja [Regras para dispositivos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>managementStates

A entidade **managementStates** fornece detalhes sobre o estado do dispositivo. Detalhes podem ser úteis nos casos em que ações remotas são aplicadas, o dispositivo está desbloqueado ou modificado.

| Propriedade  | Descrição |
|---------|------------|
| managementStateID | Identificador exclusivo do estado do gerenciamento. |
| managementStateKey | Identificador exclusivo do estado de gerenciamento no data warehouse – chave substituta. |
| managementStateName | Indica o estado da ação remota aplicada a esse dispositivo. |

### <a name="example"></a>Exemplo

| managementStateID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Gerenciados | Gerenciados com nenhuma ação remota pendente. |
| 1 |RetirePending | Há um comando de desativação pendente para o dispositivo. |
| 2 |RetireFailed | O comando de desativação falhou no dispositivo. |
| 3 |WipePending | Há um comando de apagamento pendente para o dispositivo. |
| 4 |WipeFailed | O comando de apagamento falhou no dispositivo. |
| 5 |Unhealthy | Estado não íntegro. |
| 6 |DeletePending | Há um comando de exclusão pendente para o dispositivo. |
| 7 |RetireIssued | Um comando de desativação foi emitido para o dispositivo. |
| 8 |WipeIssued | Um comando de apagamento foi emitido. |
| 9 |WipeCanceled | Um comando de apagamento foi cancelado. |
| 10 |RetireCanceled | Um comando de desativação foi cancelado. |
| 11 |Descoberto | O dispositivo foi recém-descoberto pelo Intune e, assim ele fizer check-in pela primeira vez, mudará para o estado Gerenciado. |

## <a name="managementagenttypes"></a>managementAgentTypes

A entidade **ManagementAgentType** representa os agentes usados para gerenciar um dispositivo.

| Propriedade  | Descrição |
|---------|------------|
| managementAgentTypeID | Identificador exclusivo do tipo de agente de gerenciamento. |
| managementAgentTypeKey | Identificador exclusivo do tipo de agente de gerenciamento no data warehouse – chave alternativa. |
| managementAgentTypeName |Indica qual tipo de agente é usado para gerenciar o dispositivo. |

### <a name="example"></a>Exemplo

| ManagementAgentTypeID  | Nome | Descrição |
|---------|------------|--------|
| 1 |EAS | O dispositivo é gerenciado por meio do Exchange Active Sync |
| 2 |MDM | O dispositivo é gerenciado usando um agente MDM |
| 3 |EasMdm | O dispositivo é gerenciado pelo Exchange ActiveSync e por um agente MDM |
| 4 |IntuneClient | O dispositivo é gerenciado pelo agente do PC Intune |
| 5 |EasIntuneClient | O dispositivo é gerenciado pelo Exchange ActiveSync e pelo PC Intune |
| 8 |ConfigManagerClient | O dispositivo é gerenciado pelo agente do System Center Configuration Manager |
| 16 |Unknown | Tipo de agente de gerenciamento desconhecido |

## <a name="devices"></a>dispositivos

A entidade **devices** lista todos os dispositivos registrados no gerenciamento e suas propriedades correspondentes.

|          Propriedade          |                                                                                       Descrição                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| deviceKey                  | O identificador exclusivo do dispositivo no data warehouse – chave substituta.                                                                                                               |
| deviceId                   | O identificador exclusivo do dispositivo.                                                                                                                                                     |
| deviceName                 | O nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome com base em outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| deviceTypeKey              | A chave do atributo de tipo de dispositivo para este dispositivo.                                                                                                                                    |
| deviceRegistrationState    | A chave do atributo de estado do registro do cliente para este dispositivo.                                                                                                                      |
| ownerTypeKey               | A chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido.                                                                                                    |
| enrolledDateTime           | A data e hora em que este dispositivo foi registrado.                                                                                                                                         |
| lastSyncDateTime           | O último check-in conhecido do dispositivo no Intune.                                                                                                                                              |
| managementAgentKey         | A chave do agente de gerenciamento associado a esse dispositivo.                                                                                                                             |
| managementStateKey         | A chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado.                                                |
| azureADDeviceId            | A ID de dispositivo do Azure para este dispositivo.                                                                                                                                                  |
| azureADRegistered          | Se o dispositivo está registrado no Azure Active Directory.                                                                                                                             |
| deviceCategoryKey          | A chave da categoria associada a este dispositivo.                                                                                                                                     |
| deviceEnrollmentType       | A chave do tipo de registro associada a este dispositivo, que indica o método de registro.                                                                                             |
| complianceStateKey         | A chave do estado de conformidade associado a este dispositivo.                                                                                                                             |
| osVersion                  | Versão do sistema operacional do dispositivo.                                                                                                                                                |
| easDeviceId                | A ID do Exchange ActiveSync do dispositivo.                                                                                                                                                  |
| serialNumber               | SerialNumber                                                                                                                                                                           |
| userId                     | O identificador exclusivo do usuário associado ao dispositivo.                                                                                                                           |
| rowLastModifiedDateTimeUTC | A data e a hora em UTC em que este dispositivo foi modificado pela última vez no data warehouse.                                                                                                       |
| fabricante               | Fabricante do dispositivo                                                                                                                                                             |
| modelo                      | Modelo do dispositivo                                                                                                                                                                    |
| operatingSystem            | Sistema operacional do dispositivo. Windows, iOS etc.                                                                                                                                   |
| isDeleted                  | Binário para mostrar se o dispositivo foi excluído ou não.                                                                                                                                 |
| androidSecurityPatchLevel  | Nível de patch de segurança do Android                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Estado de dispositivo não supervisionado                                                                                                                                                               |
| freeStorageSpaceInBytes    | Armazenamento livre em bytes.                                                                                                                                                                 |
| totalStorageSpaceInBytes   | Armazenamento total em bytes.                                                                                                                                                                |
| encryptionState            | Estado de criptografia no dispositivo.                                                                                                                                                      |
| subscriberCarrier          | A operadora do assinante do dispositivo                                                                                                                                                       |
| phoneNumber                | O número de telefone do dispositivo                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| cellularTechnology         | Tecnologia celular do dispositivo                                                                                                                                                    |
| WiFiMacAddress             | MAC Wi-Fi                                                                                                                                                                              |
| ICCD                       | Identificador de placa de circuito integrado                                                                                                                                                     |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

A entidade **devicePropertyHistory** tem as mesmas propriedades que a tabela de dispositivos e instantâneos diários de cada registro de dispositivo por dia dos últimos 90 dias. A coluna DateKey indica o dia para cada linha.

|          Propriedade          |                                                                                      Descrição                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| dateKey                    | Referência à tabela de data que indica o dia.                                                                                                                                          |
| deviceKey                  | O identificador exclusivo do dispositivo no data warehouse – chave alternativa. Esta é uma referência à tabela Dispositivo que contém a ID do dispositivo do Intune.                               |
| deviceName                 | Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| deviceRegistrationStateKey | A chave do atributo de estado do registro do dispositivo.                                                                                                                    |
| ownerTypeKey               | A chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido.                                                                                                  |
| managementStateKey         | A chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado.                                                |
| azureADRegistered          | Se o dispositivo está registrado no Azure Active Directory.                                                                                                                             |
| complianceStateKey         | Uma chave para ComplianceState.                                                                                                                                                            |
| OSVersion                  | Versão do SO.                                                                                                                                                                          |
| jailBroken                 | Se o dispositivo foi desbloqueado por jailbreak ou por rooting.                                                                                                                                         |
| deviceCategoryKey          | A chave do atributo de categoria deste dispositivo. 

