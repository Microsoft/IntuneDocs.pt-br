---
title: Dispositivos – Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Tópico de referência para a categoria de Dispositivos de coleções de entidade na API Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.openlocfilehash: 3993cb4e7ccbc04ccc1d341a9bd72594948f3262
ms.sourcegitcommit: e9ba1280b95565a5c5674b825881655d0303e688
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54297512"
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
| 15 |HoloLens |Dispositivo Holo Lens |
| 16 |SurfaceHub |Dispositivo Surface Hub |
| 17 |AndroidForWork |Gerenciado pelo dispositivo Android usando o proprietário do perfil do Android |
| 100 |BlackBerry |Dispositivo Blackberry |
| 101 |Palm |Dispositivo Palm |
| 255 |Unknown |Tipo de dispositivo desconhecido |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

A entidade **ClientRegistrationStateTypes** representa o tipo de registro referenciado por outras tabelas do data warehouse.

| Propriedade  | Descrição |
|---------|------------|
| clientRegisterationStateID |Identificador exclusivo para o estado do registro |
| clientRegisterationStateKey |Identificador exclusivo do estado do registro dispositivo no data warehouse – chave substituta |
| clientRegisterationStateName |Estado do Registro |

### <a name="example"></a>Exemplo

| ClientRegisterationStateID  | Nome | Descrição |
|---------|------------|--------|
| 0 |NotRegistered |Não registrado |
| 1 |SMSIDConflict |Conflito de ID de SMS |
| 2 |Registrada |Registrada |
| 3 |Revogado |Estado significa que o administrador de TI bloqueou o cliente e o cliente pode ser desbloqueado. Um dispositivo também pode estar no estado revogado depois que ele for apagado ou desativado. |
| 4 |KeyConflict |Conflito de chave |
| 5 |ApprovalPending |Aprovação pendente |
| 6 |ResetCert |Redefinir certificado |
| 7 |NotRegisteredPendingEnrollment |Inscrição pendente não registrada |
| 8 |Unknown |Estado desconhecido |

## <a name="enrollmentactivities"></a>enrollmentActivities 
A entidade **EnrollmentActivity** indica a atividade de um registro de dispositivo.

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

## <a name="enrollmenttypes"></a>EnrollmentTypes

A entidade **EnrollmentTypes** indica cmo um dispositivo foi inscrito. O tipo de registro captura o método de registro. Exemplos listam os diferentes tipos de registro e o que eles significam.

| Propriedade  | Descrição |
|---------|------------|
| managementStateID |Identificador exclusivo do estado do gerenciamento. |
| managementStateKey |Identificador exclusivo do estado de gerenciamento no data warehouse – chave substituta. |
| managementStateName |Indica o estado da ação remota aplicada a esse dispositivo. |

### <a name="example"></a>Exemplo

| enrollmentTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Unknown |O tipo de registro não foi coletado |
| 1 |UserEnrollment |Registro iniciado pelo usuário |
| 2 |DeviceEnrollment |Registro de dispositivo com o perfil sem usuário |
| 3 |DeviceEnrollmentWithUDA |Registro de dispositivo com o perfil UDA. |
| 4 |AzureDomainJoined |Registro do dispositivo iniciado pelo usuário por meio do Azure Active Directory |
| 5 |UserEnrollmentWithServiceAccount |Registro iniciado pelo usuário por meio da conta de serviço |
| 6 |DepDeviceEnrollment |Registro de dispositivo DEP com o perfil sem usuário |
| 7 |DepDeviceEnrollmentWithUDA |Registro de dispositivo DEP com o perfil UDA |
| 8 |AutoEnrollment |Registro de MDM e DRS combinados para o cenário BYOD |

## <a name="ownertypes"></a>OwnerTypes

A entidade **EnrollmentTypes** indica se um dispositivo é corporativo, pessoal ou desconhecido.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| ownerTypeID |Identificador exclusivo do tipo de proprietário. | |
| ownerTypeKey |Identificador exclusivo do tipo de proprietário no data warehouse – chave alternativa. | |
| ownerTypeName |Representa o tipo de proprietário dos dispositivos:  <br>Empresa – o dispositivo é de propriedade da empresa. <br>Pessoal – o dispositivo de propriedade pessoal (BYOD).  <br>Desconhecido – não há informações sobre este dispositivo. |Equipe da empresa desconhecida |

## <a name="mdmstatuses"></a>MdmStatuses

A entidade **MdmStatuses** indica o estado de conformidade do dispositivo.

| Propriedade  | Descrição |
|---------|------------|
| MdmStatusID |Identificador exclusivo do estado de conformidade |
| MdmStatusKey |Identificador exclusivo do estado de conformidade no data warehouse – chave substituta | 
| ComplianceStatus |Estado de conformidade do dispositivo. Deve ter um dos valores da tabela a seguir | 


### <a name="example"></a>Exemplo

| MdmStatusID  | ComplianceStatus | Descrição |
|---------|------------|--------|
| 0 |Unknown |O estado de conformidade do dispositivo é desconhecido. |
| 1 |Compatível |O dispositivo está em conformidade. |
| 2 |Fora de Conformidade |O dispositivo não está compatível. |
| 3 |Conflito |A conformidade do dispositivo resultou em um conflito. |
| 4 |Erro do |Ocorreu um erro na leitura do estado de conformidade do dispositivo. |


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

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

A entidade **WorkPlaceJoinStateTypes** representa o estado de ingresso no local de trabalho do Azure Active Directory.  O fluxo de trabalho do registro pode usar um ou mais certificados para verificar ou autenticar. Quando o Local de trabalho de um dispositivo é registrado, esses certificados são usados para validar o usuário e o dispositivo. A emissão de certificados é fornecida por meio de um servidor de protocolo SCEP (Ponto de registro de certificado simples). Os valores da entidade indicam vários estados que um dispositivo pode ter conforme ele passa por esse processo. Alguns desses estados incluem falha de ingresso de local de trabalho devido à falha na emissão de um certificado necessário (de um servidor de protocolo SCEP). Se um dispositivo nunca tiver passado por esse fluxo de trabalho, o valor será definido como Desconhecido.

| Propriedade  | Descrição |
|---------|------------|
| WorkPlaceJoinStateID | Identificador exclusivo do estado de ingresso do local de trabalho |
| WorkPlaceJoinStateKey | Identificador exclusivo do estado de ingresso do local de trabalho no data warehouse – chave substituta |
| WorkPlaceJoinStateName | Estado do ingresso do local de trabalho |

### <a name="example"></a>Exemplo

| workPlaceJoinStateID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Unknown |Se um dispositivo não estiver ingressado no local de trabalho, ele estará em estado Desconhecido |
| 1 |Bem-sucedido |Ingresso de local de trabalho bem-sucedido |
| 2 |FailureToGetScepMetadata |Falha ao obter metadados de protocolo SCEP |
| 3 |FailureToGetScepChallenge |Falha ao obter o desafio de protocolo SCEP |
| 4 |DeviceFailureToInstallScepCommand |Falha ao instalar o comando de protocolo SCEP no dispositivo |
| 5 |DeviceFailureToGetCertificate |O dispositivo falhou ao obter certificado por meio do protocolo SCEP |
| 6 |DeviceScepPending |Estado pendente; o dispositivo ainda está realizando o protocolo SCEP |
| 7 |DeviceScepFailed |O dispositivo falhou ao instalar o certificado por meio do protocolo SCEP |
| 8 |AADValidationFailed |Falha ao validar se o dispositivo existe no AAD |

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
| ClientRegisterationStateKey | Chave do atributo de estado do registro do cliente para este dispositivo. |
| OwnerTypeKey | Chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido. |
| objectSourceKey | Ignore essa coluna. |
| CreatedDate | Data em que o dispositivo foi registrado. |
| LastContact | Último check-in conhecido do dispositivo no Intune. |
| LastContactNotification | Última vez que o Intune notificou o dispositivo para fazer check-in no Intune. |
| LastContactWorkplaceJoin | O carimbo de data/hora que indica o último estado conhecido de ingresso no local de trabalho para este dispositivo. |
| ManagementAgentKey | Chave do agente de gerenciamento associado a esse dispositivo. |
| ManagementStateKey | Chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado. |
| ReferenceId | A ID do dispositivo no Azure Active Directory. |
| WorkPlaceJoinStateKey | Chave do estado de ingresso de local de trabalho associada a esse dispositivo. |
| CategoryId | Ignore essa coluna. |
| EnrollmentTypeKey | Chave do tipo de registro associada a este dispositivo, que indica o método de registro. |
| CertExpirationDate | Data de expiração do certificado de gerenciamento do MDM. |
| MdmStatusKey | Uma chave para MdmStatus. |
| OSFamily | Família do sistema operacional (Windows, iOS, Android etc.) |
| OSVersion | Versão do SO |
| OSMajorVersion | Componente de versão principal da versão do SO (major.minor.build.revision). |
| OSMinorVersion | Componente de versão secundária da versão do SO (major.minor.build.revision). |
| OSBuildNumber | Componente de versão de build da versão do SO (major.minor.build.revision). |
| OSRevisionNumber | Componente de versão de revisão da versão do SO (major.minor.build.revision). |
| EasID | A ID de EAS destesdispositivos, se o dispositivo for gerenciado pelo Exchange Active Sync. |
| GraphDeviceIsManaged | O último status de gerenciamento que o Intune definiu no Azure AD. |
| GraphDeviceIsCompliant | O último estado de conformidade que Intune definiu no Azure AD. |
| SerialNumber | Número de série do dispositivo, se disponível. |
| EnrolledByUser | A ID do usuário que registrou esse dispositivo que referencia a coluna userID na tabela de Usuário. |
| RowLastModifiedDateTimeUTC | Última vez em que este registro foi modificado. |
| ProcessorArchitecture | Arquitetura do processador. |
| DeviceAction | Última ação de dispositivo emitida, ignorar por enquanto. |
| Fabricante | Fabricante do dispositivo. |
| Modelo | Modelo do dispositivo. |
| LastPolicyUpdateUtc | Última vez em que a política foi atualizada no dispositivo. |
| LastExchangeStatusUtc | Última vez em que o dispositivo sincronizou com o Exchange. |
| IsDeleted | Defina como True se o dispositivo não for mais gerenciado pelo Intune. Preserva o último estado conhecido. |
| AndroidSecurityPatchLevel |A data do patch de segurança mais recente do dispositivo. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

A entidade **DevicePropertyHistory** tem as mesmas propriedades que a tabela de dispositivos e instantâneos diários de cada registro de dispositivo por dia dos últimos 90 dias. A coluna DateKey indica o dia para cada linha.

| Propriedade  | Descrição |
|---------|------------|
| DateKey |Referência à tabela de data que indica o dia. |
| DeviceKey |Identificador exclusivo do dispositivo no data warehouse – chave substituta. Esta é uma referência à tabela Dispositivo que contém a ID do dispositivo do Intune. |
| DeviceName |Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| DeviceTypeKey |Chave do atributo de tipo de dispositivo para este dispositivo. |
| ClientRegisterationStateKey |Chave do atributo de estado do registro do cliente para este dispositivo. |
| OwnerTypeKey |Chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido. |
| objectSourceKey |Ignore essa coluna. |
| CreatedDate |Data em que o dispositivo foi registrado. |
| LastContact |Último check-in conhecido do dispositivo no Intune. |
| LastContactNotification |Última vez que o Intune notificou o dispositivo para fazer check-in no Intune. |
| LastContactWorkplaceJoin |O carimbo de data/hora que indica o último estado conhecido de ingresso no local de trabalho para este dispositivo. |
| ManagementAgentKey |Chave do agente de gerenciamento associado a esse dispositivo. |
| ManagementStateKey |Chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado. |
| ReferenceId |A ID do dispositivo no Azure Active Directory. |
| WorkPlaceJoinStateKey |Chave do estado de ingresso de local de trabalho associada a esse dispositivo. |
| CategoryId |Ignore essa coluna. |
| EnrollmentTypeKey |Chave do tipo de registro associada a este dispositivo, que indica o método de registro. |
| CertExpirationDate |Data de expiração do certificado de gerenciamento do MDM. |
| MdmStatusKey |Uma chave para MdmStatus. |
| OSFamily |Família do sistema operacional (Windows, iOS, Android etc.) |
| OSVersion |Versão do SO. |
| OSMajorVersion |Componente de versão principal da versão do SO (major.minor.build.revision). |
| OSMinorVersion |Componente de versão secundária da versão do SO (major.minor.build.revision). |
| OSBuildNumber |Componente de versão de build da versão do SO (major.minor.build.revision). |
| OSRevisionNumber |Componente de versão de revisão da versão do SO (major.minor.build.revision). |
| EasID |A ID de EAS destesdispositivos, se o dispositivo for gerenciado pelo Exchange Active Sync. |
| GraphDeviceIsManaged |O último status de gerenciamento que o Intune definiu no Azure AD. |
| GraphDeviceIsCompliant |O último estado de conformidade que Intune definiu no Azure AD. |
| SerialNumber |Número de série do dispositivo, se disponível. |
| EnrolledByUser |A ID do usuário que registrou esse dispositivo que referencia a coluna userID na tabela de Usuário. |
| RowLastModifiedDateTimeUTC |Última vez em que este registro foi modificado. |
| ProcessorArchitecture |Arquitetura do processador. |
| DeviceAction |Última ação de dispositivo emitida, ignorar por enquanto. |
| Fabricante |Fabricante do dispositivo. |
| Modelo |Modelo do dispositivo. |
| LastPolicyUpdateUtc |Última vez em que a política foi atualizada no dispositivo. |
| LastExchangeStatusUtc |Última vez em que o dispositivo sincronizou com o Exchange. |

## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

A entidade **MdmDeviceInventoryHistories** contém instantâneos diários de dados de inventário de dispositivos gerenciados pelo MDM dos últimos 90 dias. A coluna DateKey indica o dia para a linha. Algumas propriedades podem não ser aplicáveis nem preenchidas para todos os dispositivos, por isso, consulte esta página para obter mais detalhes. Para obter mais informações, consulte [Compreenda seus dispositivos com um inventário no Microsoft Intune](device-inventory.md).

| Propriedade  | Descrição |
|---------|------------|
| DateKey | Referência à tabela de data que indica o dia. |
| DeviceKey |Identificador exclusivo do dispositivo no data warehouse – chave substituta. Esta é uma referência à tabela Dispositivo que contém a ID do dispositivo do Intune. |
| DeviceModel |Modelo do dispositivo. |
| SO |SO do dispositivo. |
| DeviceName |Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| SoftwareVersion |Na maioria dos casos, essa é a versão de sistema operacional, exceto em plataformas Apple, em que é diferente da versão do sistema operacional. |
| Imei |Número IMEI |
| HardwareInventoryTimeUtc |A primeira vez em que o inventário foi relatado para este dispositivo. |
| InventoryModifiedTimeUtc |A última vez em que o inventário foi armazenado quando esse instantâneo foi criado. |
| InventoryReportingTimeUtc |A última vez em que o inventário foi coletado para este dispositivo. |
| ExchangeActiveSyncId |ID do dispositivo do Exchange ActiveSync. |
| ComputerSystemDescription |Descrição do sistema. |
| ComputerSystemName |Nome do sistema. |
| ComputerSystemManufacturer |Fabricante do sistema. |
| ComputerSystemModel |Modelo do sistema. |
| UserName |Nome de usuário. |
| OSType |Tipo de SO. |
| OSCaption |Legenda do SO. |
| OSName |Nome do SO. |
| OSManufacturer |Fabricante do SO. |
| OSProductSuite |Pacote de produtos do SO. |
| OSProductType |Tipo de produto do SO. |
| Localidade |Localidade do SO. |
| PhysicalMemoryCapacity |Capacidade de memória física (em bytes). |
| PhysicalMemoryRemovable |Memória removível física (em bytes). |
| SystemEnclosureChassisTypesInnerText |Define o tipo de chassi do sistema para este dispositivo. Os números indicam os seguintes valores:  <br>0 ou vazio = desconhecido   <br>1 = é uma área de trabalho   <br>2 = é um laptop  <br>3 = é uma estação de trabalho  <br>4 = é um servidor corporativo  <br>100 = é um telefone  <br>101 = é um tablet  <br>102/103 = outro tipo desconhecido de dispositivo móvel |
| SystemEnclosureModel |Modelo de compartimento do sistema. |
| SystemEnclosureSerialNumber |Número de série do compartimento do sistema. |
| NetworkAdapterConfigurationText |Texto de configuração do adaptador de rede. |
| MacAddress |Endereço MAC. |
| SmsID |ID do dispositivo do Intune. |
| CertExpiry |Data de expiração do certificado de gerenciamento do MDM. |
| DeviceClientAgentVersion |Versão do agente cliente. |
| DeviceClientID |ID do cliente do dispositivo. |
| SerialNumber |Número de série. |
| DeviceManufacturer |Fabricante do dispositivo. |
| DMVersion |Versão de DM. |
| FirmwareVersion |Versão do firmware. |
| HardwareVersion |Versão do hardware. |
| PlatformType |Tipo de plataforma. |
| ProcessorLevel |Nível do processador. |
| ProcessorRevision |Revisão do processador. |
| Produto |Produto. |
| ProductVersion |Versão do produto. |
| OEM |Fabricante de equipamento original. |
| DeviceBuildVersion |Versão de build do dispositivo. |
| Meid |Identificador de equipamentos móveis. |
| PhoneNumber |Número do telefone. |
| SubscriberCarrierNetwork |Nome da rede da operadora de telefone. |
| CellularTechnology |Tipo de rede da operadora de telefone (CDMA/GSM). |
| Imsi |Número IMSI. |
| Com jailbreak |Verdadeiro se o dispositivo estiver desbloqueado ou for modificado. |
| IsActivationLockEnabled |Verdadeiro se o Bloqueio de ativação estiver habilitado |
| DeviceType |Tipo de dispositivo |
| IsSupervised |É supervisionado |
| DeviceDisplayNumberOfColors |Número de cores da tela do dispositivo |
| HorizontalResolution |Resolução horizontal da tela do dispositivo |
| VerticalResolution |Resolução vertical da tela do dispositivo |
| StorageFree |Armazenamento livre (em bytes) |
| StorageTotal |Armazenamento total (em bytes) |
| ProgramFree |Memória de programa livre (em bytes) |
| ProgramTotal |Memória de programa total (em bytes) |
| RemovableStorageFree |Armazenamento removível livre (em bytes) |
| RemovableStorageTotal |Armazenamento removível total (em bytes) |
| DeviceMemoryDeviceCapacity |Capacidade de memória do dispositivo |
| DeviceMemoryAvailableDeviceCapacity |Capacidade disponível de memória do dispositivo |
| DeviceOSVersion |Versão do SO |
| DeviceOSPlatform |Plataforma do sistema operacional |
| DeviceOSLanguage |Idioma do sistema operacional |
| PasswordMaxAttemptsBeforeWipe |Máximo de tentativas de senha permitidas antes do apagamento do dispositivo |
| PasswordMinComplexChars |Número mínimo de caracteres complexos necessários na senha |
| PasswordMinLength |Comprimento mínimo necessário de senha |
| PasswordHistory |Senha – mínimo de senhas de histórico inaceitável |
| PasswordEnabled |Senha – Habilitada? |
| PasswordExpiration |Senha – data de expiração. |
| AllowRecoveryPassword |Permitir recuperação de senha. |
| PasswordAutoLockTimeout |Senha – tempo limite de bloqueio automático. |
| PasswordType |Tipo de senha. |
| BacklightACTimeout |Tempo limite da luz de fundo atingido quando conectado à fonte de alimentação. |
| BacklightBatTimeout |Tempo limite da luz de fundo funcionando com bateria. |
| PowerBackupPercent |Porcentagem de backup de energia. |
| BatteryPercent |Porcentagem restante da bateria. |
| PlatformID |ID da plataforma. |
| ExchangeDeviceID |ID do dispositivo do Exchange. |
| SmsProcessorDescription |Descrição do processador. |
| OwnerEmailAddress |Endereço de email do proprietário. |
| DeviceOSName |Nome do SO. |
| WifiMac |Endereço Mac do Wi-Fi. |
| EthernetMac |Endereço MAC da Ethernet. |
| RequireEncryption |Indica se o dispositivo é criptografado ou não. |
| ActivationLockBypassCode |Código de bypass do bloqueio de ativação. |

## <a name="applicationinventory"></a>ApplicationInventory

A entidade **ApplicationInventory** lista os aplicativos encontrados no dispositivo no momento da coleta de inventário.


|      Propriedade      |                       Descrição                        |
|--------------------|----------------------------------------------------------|
|     DeviceKey      |              Uma referência à tabela de dispositivos.               |
|   ApplicationKey   | ? (copiado de ExchangeDeviceService\DeviceApplication). |
|  ApplicationName   | ? (copiado de ExchangeDeviceService\DeviceApplication). |
| ApplicationVersion | ? (copiado de ExchangeDeviceService\DeviceApplication). |
|     BundleSize     | ? (copiado de ExchangeDeviceService\DeviceApplication). |

