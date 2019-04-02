---
title: Dispositivos – Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria de Dispositivos de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 29213400b5baf9705c188bb45b3666b65262d577
ms.sourcegitcommit: 93286c22426dcb59191a99e3cf2af4ff6ff16522
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58358226"
---
# <a name="reference-for-devices-entities"></a>Referência para entidades de dispositivos

A categoria **Dispositivos** contém entidades para dispositivos móveis que rastreiam informações como:

  -  Tipo de dispositivo
  -  Status de registro e registro do dispositivo
  -  Propriedade do dispositivo
  -  Estado de gerenciamento de dispositivo
  -  Status de associação de dispositivo para Azure AD
  -  Status do registro
  -  Informações históricas sobre o dispositivo
  -  Inventário de aplicativos no dispositivo

## <a name="devicetypes"></a>DeviceTypes

A entidade **DeviceTypes** representa o tipo de dispositivo referenciado por outras entidades do data warehouse. O tipo de dispositivo geralmente descreve o modelo do dispositivo, o fabricante ou uma combinação de ambos.

| Propriedade  | Descrição |
|---------|------------|
| DeviceTypeID |Identificador exclusivo do tipo de dispositivo |
| DeviceTypeKey |Identificador exclusivo do tipo de dispositivo no data warehouse – chave substituta |
| DeviceTypeName |Tipo de dispositivo |

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
A entidade **EnrollmentActivity** indica a atividade de um registro de dispositivo.

| Propriedade                      | Descrição                                                               |
|-------------------------------|---------------------------------------------------------------------------|
| dateKey                       | Chave da data em que essa atividade de registro foi gravada.               |
| deviceEnrollmentTypeKey       | Chave do tipo do registro.                                        |
| enrollmentEventStatusKey      | Chave do status indicando o êxito ou a falha do registro.    |
| enrollmentFailureCategoryKey  | Chave da categoria de falha do registro (se o registro falhou).        |
| enrollmentFailureReasonKey    | Chave do motivo da falha do registro (se o registro falhou).          |
| osVersion                     | A versão do sistema operacional do dispositivo.                               |
| count                         | Contagem total de atividades de registro correspondentes às classificações acima.  |

## <a name="enrollmenteventstatuses"></a>enrollmentEventStatuses 
A entidade **EnrollmentEventStatus** indica o resultado de um registro de dispositivo.

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
## <a name="ownertypes"></a>OwnerTypes

A entidade **EnrollmentTypes** indica se um dispositivo é corporativo, pessoal ou desconhecido.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| ownerTypeID |Identificador exclusivo do tipo de proprietário. | |
| ownerTypeKey |Identificador exclusivo do tipo de proprietário no data warehouse – chave alternativa. | |
| ownerTypeName |Representa o tipo de proprietário dos dispositivos:  <br>Corporativo – dispositivo é de propriedade da empresa. <br>Pessoal – o dispositivo de propriedade pessoal (BYOD).  <br>Desconhecido – não há informações sobre este dispositivo. |Desconhecido corporativo de pessoal |

> [!Note]  
> Para o `ownerTypeName` no Azure AD durante a criação de grupos dinâmicos para dispositivos, você precisará definir o valor do filtro `deviceOwnership` como `Company`. Para obter mais informações, consulte [regras para dispositivos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="managementstates"></a>ManagementStates

A entidade **ManagementStates** fornece detalhes sobre o estado do dispositivo. Detalhes podem ser úteis nos casos em que ações remotas são aplicadas, o dispositivo está desbloqueado ou modificado.

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

## <a name="managementagenttypes"></a>ManagementAgentTypes

A entidade **ManagementAgentTypes** representa os agentes usados para gerenciar um dispositivo.

| Propriedade  | Descrição |
|---------|------------|
| ManagementAgentTypeID | Identificador exclusivo do tipo de agente de gerenciamento. |
| ManagementAgentTypeKey | Identificador exclusivo do tipo de agente de gerenciamento no data warehouse – chave alternativa. |
| ManagementAgentTypeName |Indica qual tipo de agente é usado para gerenciar o dispositivo. |

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

## <a name="devices"></a>Dispositivos

A entidade **Dispositivos** lista todos os dispositivos registrados no gerenciamento e suas propriedades correspondentes.

| Propriedade  | Descrição |
|---------|------------|
| DeviceKey | Identificador exclusivo do dispositivo no data warehouse – chave substituta. |
| DeviceId | Identificador exclusivo do dispositivo. |
| DeviceName | Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| DeviceTypeKey | Chave do atributo de tipo de dispositivo para este dispositivo. |
| OwnerTypeKey | Chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido. |
| objectSourceKey | Ignore essa coluna. |
| ManagementAgentKey | Chave do agente de gerenciamento associado a esse dispositivo. |
| ManagementStateKey | Chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado. |
| OSVersion | Versão do SO |
| OSMajorVersion | Componente de versão principal da versão do SO (major.minor.build.revision). |
| OSMinorVersion | Componente de versão secundária da versão do SO (major.minor.build.revision). |
| OSBuildNumber | Componente de versão de build da versão do SO (major.minor.build.revision). |
| OSRevisionNumber | Componente de versão de revisão da versão do SO (major.minor.build.revision). |
| SerialNumber | Número de série do dispositivo, se disponível. |
| RowLastModifiedDateTimeUTC | Última vez em que este registro foi modificado. |
| DeviceAction | Última ação de dispositivo emitida, ignorar por enquanto. |
| Fabricante | Fabricante do dispositivo. |
| Modelo | Modelo do dispositivo. |
| IsDeleted | Defina como True se o dispositivo não for mais gerenciado pelo Intune. Preserva o último estado conhecido. |
| AndroidSecurityPatchLevel |A data do patch de segurança mais recente do dispositivo. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

A entidade **DevicePropertyHistory** tem as mesmas propriedades que a tabela de dispositivos e instantâneos diários de cada registro de dispositivo por dia dos últimos 90 dias. A coluna DateKey indica o dia para cada linha.

| Propriedade  | Descrição |
|---------|------------|
| DateKey |Referência à tabela de data que indica o dia. |
| DeviceKey |Identificador exclusivo do dispositivo no data warehouse – chave substituta. Esta é uma referência à tabela Dispositivo que contém a ID do dispositivo do Intune. |
| DeviceName |Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| OwnerTypeKey |Chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido. |
| objectSourceKey |Ignore essa coluna. |
| ManagementStateKey |Chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado. |
| OSVersion |Versão do SO. |
| OSMajorVersion |Componente de versão principal da versão do SO (major.minor.build.revision). |
| OSMinorVersion |Componente de versão secundária da versão do SO (major.minor.build.revision). |
| OSBuildNumber |Componente de versão de build da versão do SO (major.minor.build.revision). |
| DeviceAction |Última ação de dispositivo emitida, ignorar por enquanto. |

## <a name="applicationinventory"></a>ApplicationInventory

A entidade **ApplicationInventory** lista os aplicativos encontrados no dispositivo no momento da coleta de inventário.


|      Propriedade      |                       Descrição                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Uma referência à tabela de dispositivos.               |
|   ApplicationKey   | ? (copiado de ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (copiado de ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (copiado de ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (copiado de ExchangeDeviceService\DeviceApplication). |

