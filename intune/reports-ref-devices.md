---
title: Dispositivos | Microsoft Docs
description: "Tópico de referência para a categoria de Dispositivos de coleções de entidade na API Intune Data Warehouse."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6955E12D-70D7-4802-AE3B-8B276F01FA4F
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7730a799176a74f1ddb8e4b5e49a110229255428
ms.sourcegitcommit: 6fae2dfb3a5c8f2e5ccfd120fd15656b26e5d302
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2017
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

## <a name="example"></a>Exemplo

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
| 17 |AndroidForWork |Dispositivo Android gerenciado usando o Android para o proprietário do perfil de trabalho |
| 100 |BlackBerry |Dispositivo Blackberry |
| 101 |Palm |Dispositivo Palm |
| 255 |Desconhecido |Tipo de dispositivo desconhecido |

## <a name="clientregistrationstatetypes"></a>ClientRegistrationStateTypes

A entidade **ClientRegistrationStateTypes** representa o tipo de dispositivo referenciado por outras tabelas do data warehouse.

| Propriedade  | Descrição |
|---------|------------|
| clientRegisterationStateID |Identificador exclusivo para o estado do registro |
| clientRegisterationStateKey |Identificador exclusivo do estado do registro dispositivo no data warehouse – chave substituta |
| clientRegisterationStateName |Estado do Registro |

## <a name="example"></a>Exemplo

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
| 8 |Desconhecido |Estado desconhecido |

## <a name="enrollmenttypes"></a>EnrollmentTypes

A entidade **EnrollmentTypes** indica cmo um dispositivo foi inscrito. O tipo de registro captura o método de registro. Exemplos listam os diferentes tipos de registro e o que eles significam.

| Propriedade  | Descrição |
|---------|------------|
| managementStateID |Identificador exclusivo do estado do gerenciamento. |
| managementStateKey |Identificador exclusivo do estado de gerenciamento no data warehouse – chave substituta. |
| managementStateName |Indica o estado da ação remota aplicada a esse dispositivo. |

## <a name="example"></a>Exemplo

| enrollmentTypeID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Desconhecido |O tipo de registro não foi coletado |
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
| ownerTypeID |Identificador exclusivo do tipo de proprietário | |
| ownerTypeKey |Identificador exclusivo do tipo de proprietário no data warehouse – chave substituta | |
| ownerTypeName |Representa o tipo de proprietário dos dispositivos: empresa – o dispositivo é de propriedade da empresa. Pessoal – o dispositivo de propriedade pessoal (BYOD).  Desconhecido – não há informações sobre este dispositivo. |Equipe da empresa desconhecida |

## <a name="mdmstatuses"></a>MdmStatuses

A entidade **MdmStatuses** indica o estado de conformidade do dispositivo.

| Propriedade  | Descrição | Exemplo |
|---------|------------|--------|
| MdmStatusName |Identificador de MdmStatus |0 – Desconhecido 1 – Compatível 2 – Não compatível |
| MdmStatusKey |Identificador exclusivo do estado de conformidade no data warehouse – chave substituta | |

## <a name="managementstates"></a>ManagementStates

A entidade **ManagementStates** fornece detalhes sobre o estado do dispositivo. Detalhes podem ser úteis nos casos em que ações remotas são aplicadas, o dispositivo está desbloqueado ou modificado.

| Propriedade  | Descrição |
|---------|------------|
| managementStateID |Identificador exclusivo do estado do gerenciamento |
| managementStateKey |Identificador exclusivo do estado de gerenciamento no data warehouse – chave substituta |
| managementStateName |Indica o estado da ação remota aplicada a esse dispositivo. |

## <a name="example"></a>Exemplo

| managementStateID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Gerenciados |Gerenciados com nenhuma ação remota pendente. |
| 1 |RetirePending |Há um comando de desativação pendente para o dispositivo. |
| 2 |RetireFailed |O comando de desativação falhou no dispositivo. |
| 3 |WipePending |Há um comando de apagamento pendente para o dispositivo. |
| 4 |WipeFailed |O comando de apagamento falhou no dispositivo. |
| 5 |Unhealthy |Estado não íntegro |
| 6 |DeletePending |Há um comando de exclusão pendente para o dispositivo. |
| 7 |RetireIssued |Um comando de desativação foi emitido para o dispositivo. |
| 8 |WipeIssued |Um comando de apagamento foi emitido. |
| 9 |WipeCanceled |Um comando de apagamento foi cancelado. |
| 10 |RetireCanceled |Um comando de desativação foi cancelado. |
| 11 |Descoberto |O dispositivo foi recém-descoberto pelo Intune e, assim ele fizer check-in pela primeira vez, mudará para o estado Gerenciado |

## <a name="workplacejoinstatetypes"></a>WorkPlaceJoinStateTypes

A entidade **WorkPlaceJoinStateTypes** representa o estado de ingresso no local de trabalho do Azure Active Directory.  O fluxo de trabalho do registro pode usar um ou mais certificados para verificar ou autenticar. Quando o Local de trabalho de um dispositivo é registrado, esses certificados são usados para validar o usuário e o dispositivo. A emissão de certificados é fornecida por meio de um servidor de protocolo SCEP (Ponto de registro de certificado simples). Os valores da entidade indicam vários estados que um dispositivo pode ter conforme ele passa por esse processo. Alguns desses estados incluem falha de ingresso de local de trabalho devido à falha na emissão de um certificado necessário (de um servidor de protocolo SCEP). Se um dispositivo nunca tiver passado por esse fluxo de trabalho, o valor será definido como Desconhecido.

| Propriedade  | Descrição |
|---------|------------|
| WorkPlaceJoinStateID |Identificador exclusivo do estado de ingresso do local de trabalho |
| WorkPlaceJoinStateKey |Identificador exclusivo do estado de ingresso do local de trabalho no data warehouse – chave substituta |
| WorkPlaceJoinStateName |Estado do ingresso do local de trabalho |

## <a name="example"></a>Exemplo

| workPlaceJoinStateID  | Nome | Descrição |
|---------|------------|--------|
| 0 |Desconhecido |Se um dispositivo não estiver ingressado no local de trabalho, ele estará em estado Desconhecido |
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
| ManagementAgentTypeID |Identificador exclusivo do tipo de agente de gerenciamento |
| ManagementAgentTypeKey |Identificador exclusivo do tipo de agente de gerenciamento no data warehouse – chave substituta |
| ManagementAgentTypeName |Indica qual tipo de agente é usado para gerenciar o dispositivo. |

## <a name="example"></a>Exemplo

| ManagementAgentTypeID  | Nome | Descrição |
|---------|------------|--------|
| 1 |EAS |O dispositivo é gerenciado por meio do Exchange Active Sync |
| 2 |MDM |O dispositivo é gerenciado usando um agente MDM |
| 3 |EasMdm |O dispositivo é gerenciado pelo Exchange ActiveSync e por um agente MDM |
| 4 |IntuneClient |O dispositivo é gerenciado pelo agente do PC Intune |
| 5 |EasIntuneClient |O dispositivo é gerenciado pelo Exchange ActiveSync e pelo PC Intune |
| 8 |ConfigManagerClient |O dispositivo é gerenciado pelo agente do System Center Configuration Manager |
| 16 |Desconhecido |Tipo de agente de gerenciamento desconhecido |

## <a name="devices"></a>Dispositivos

A entidade **Dispositivos** lista todos os dispositivos registrados no gerenciamento e suas propriedades correspondentes.

| Propriedade  | Descrição |
|---------|------------|
| DeviceKey |Identificador exclusivo do dispositivo no data warehouse – chave substituta |
| DeviceId |Identificador exclusivo do dispositivo |
| DeviceName |Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| DeviceTypeKey |Chave do atributo de tipo de dispositivo para este dispositivo |
| ClientRegisterationStateKey |Chave do atributo de estado de registro de cliente para este dispositivo |
| OwnerTypeKey |Chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido. |
| objectSourceKey |Ignore essa coluna. |
| CreatedDate |Data em que o dispositivo foi registrado |
| LastContact |Último check-in de dispositivo conhecido com o Intune |
| LastContactNotification |Última vez em que o Intune notificou o dispositivo para fazer check-in no Intune |
| LastContactWorkplaceJoin |O carimbo de data/hora que indica o último estado conhecido de ingresso no local de trabalho para este dispositivo. |
| ManagementAgentKey |Chave do agente de gerenciamento associado a esse dispositivo. |
| ManagementStateKey |Chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado. |
| ReferenceId |A ID do dispositivo no Azure Active Directory |
| WorkPlaceJoinStateKey |Chave do estado de ingresso de local de trabalho associada a esse dispositivo. |
| CategoryId |Ignore essa coluna. |
| EnrollmentTypeKey |Chave do tipo de registro associada a este dispositivo, que indica o método de registro. |
| CertExpirationDate |Data de expiração do certificado de gerenciamento do MDM. |
| MdmStatusKey |Uma chave para MdmStatus |
| OSFamily |Família do sistema operacional (Windows, iOS, Android etc.) |
| OSVersion |Versão do SO |
| OSMajorVersion |Componente de versão principal da versão do sistema operacional (principal.secundária.build.revisão) |
| OSMinorVersion |Componente de versão secundária da versão do sistema operacional (major.minor.build.revision) |
| OSBuildNumber |Componente de versão build da versão do sistema operacional (major.minor.build.revision) |
| OSRevisionNumber |Componente de versão de revisão da versão do sistema operacional (major.minor.build.revision) |
| EasID |A ID de EAS destesdispositivos, se o dispositivo for gerenciado pelo Exchange Active Sync. |
| GraphDeviceIsManaged |O último status de gerenciamento que o Intune definiu no AAD |
| GraphDeviceIsCompliant |O último status de conformidade que o Intune definiu no AAD |
| SerialNumber |O número de série do dispositivo, se disponível |
| EnrolledByUser |A ID do usuário que registrou esse dispositivo que referencia a coluna userID na tabela de Usuário. |
| RowLastModifiedDateTimeUTC |Última vez em que este registro foi modificado. |
| ProcessorArchitecture |Arquitetura do processador |
| DeviceAction |Última ação de dispositivo emitida, ignorar por enquanto. |
| Fabricante |Fabricante do dispositivo |
| Modelo |Modelo do dispositivo |
| LastPolicyUpdateUtc |Última vez em que a política foi atualizada no dispositivo |
| LastExchangeStatusUtc |Última vez em que o dispositivo sincronizou com o Exchange. |
| IsDeleted |Defina como True se o dispositivo não for mais gerenciado pelo Intune. Preserva o último estado conhecido. |

## <a name="devicepropertyhistory"></a>DevicePropertyHistory

A entidade **DevicePropertyHistory** tem as mesmas propriedades que a tabela de dispositivos e instantâneos diários de cada registro de dispositivo por dia dos últimos 90 dias. A coluna DateKey indica o dia para cada linha.

| Propriedade  | Descrição |
|---------|------------|
| DateKey |Referência à tabela de datas que indica o dia |
| DeviceKey |Identificador exclusivo do dispositivo no data warehouse – chave substituta. Esta é uma referência à tabela de Dispositivo que contém a ID do dispositivo do Intune |
| DeviceName |Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| DeviceTypeKey |Chave do atributo de tipo de dispositivo para este dispositivo |
| ClientRegisterationStateKey |Chave do atributo de estado de registro de cliente para este dispositivo |
| OwnerTypeKey |Chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido. |
| objectSourceKey |Ignore essa coluna. |
| CreatedDate |Data em que o dispositivo foi registrado |
| LastContact |Último check-in de dispositivo conhecido com o Intune |
| LastContactNotification |Última vez em que o Intune notificou o dispositivo para fazer check-in no Intune |
| LastContactWorkplaceJoin |O carimbo de data/hora que indica o último estado conhecido de ingresso no local de trabalho para este dispositivo. |
| ManagementAgentKey |Chave do agente de gerenciamento associado a esse dispositivo. |
| ManagementStateKey |Chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado. |
| ReferenceId |A ID do dispositivo no Azure Active Directory |
| WorkPlaceJoinStateKey |Chave do estado de ingresso de local de trabalho associada a esse dispositivo. |
| CategoryId |Ignore essa coluna. |
| EnrollmentTypeKey |Chave do tipo de registro associada a este dispositivo, que indica o método de registro. |
| CertExpirationDate |Data de expiração do certificado de gerenciamento do MDM. |
| MdmStatusKey |Uma chave para MdmStatus |
| OSFamily |Família do sistema operacional (Windows, iOS, Android etc.) |
| OSVersion |Versão do SO |
| OSMajorVersion |Componente de versão principal da versão do sistema operacional (principal.secundária.build.revisão) |
| OSMinorVersion |Componente de versão secundária da versão do sistema operacional (major.minor.build.revision) |
| OSBuildNumber |Componente de versão build da versão do sistema operacional (major.minor.build.revision) |
| OSRevisionNumber |Componente de versão de revisão da versão do sistema operacional (major.minor.build.revision) |
| EasID |A ID de EAS destesdispositivos, se o dispositivo for gerenciado pelo Exchange Active Sync. |
| GraphDeviceIsManaged |O último status de gerenciamento que o Intune definiu no AAD |
| GraphDeviceIsCompliant |O último status de conformidade que o Intune definiu no AAD |
| SerialNumber |O número de série do dispositivo, se disponível |
| EnrolledByUser |A ID do usuário que registrou esse dispositivo que referencia a coluna userID na tabela de Usuário. |
| RowLastModifiedDateTimeUTC |Última vez em que este registro foi modificado. |
| ProcessorArchitecture |Arquitetura do processador |
| DeviceAction |Última ação de dispositivo emitida, ignorar por enquanto. |
| Fabricante |Fabricante do dispositivo |
| Modelo |Modelo do dispositivo |
| LastPolicyUpdateUtc |Última vez em que a política foi atualizada no dispositivo |
| LastExchangeStatusUtc |Última vez em que o dispositivo sincronizou com o Exchange. |
## <a name="mdmdeviceinventoryhistories"></a>MdmDeviceInventoryHistories

A entidade **MdmDeviceInventoryHistories** contém instantâneos diários de dados de inventário de dispositivos gerenciados pelo MDM dos últimos 90 dias. A coluna DateKey indica o dia para a linha. Algumas propriedades podem não ser aplicáveis nem preenchidas para todos os dispositivos, por isso, consulte esta página para obter mais detalhes. Para obter mais informações, consulte [Compreenda seus dispositivos com um inventário no Microsoft Intune](https://docs.microsoft.com/Intune-classic/deploy-use/understand-your-devices-with-inventory-in-microsoft-Intune).

| Propriedade  | Descrição |
|---------|------------|
| DateKey |Referência à tabela de datas que indica o dia |
| DeviceKey |Identificador exclusivo do dispositivo no data warehouse – chave substituta. Esta é uma referência à tabela de Dispositivo que contém a ID do dispositivo do Intune |
| DeviceModel |Modelo do dispositivo |
| SO |Sistema operacional do dispositivo |
| DeviceName |Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| SoftwareVersion |Na maioria dos casos, essa é a versão de sistema operacional, exceto em plataformas Apple, em que é diferente da versão do sistema operacional. |
| Imei |Número IMEI |
| HardwareInventoryTimeUtc |A primeira vez em que o inventário foi relatado para este dispositivo. |
| InventoryModifiedTimeUtc |A última vez em que o inventário foi armazenado quando esse instantâneo foi tirado |
| InventoryReportingTimeUtc |A última vez em que o inventário foi coletado para este dispositivo. |
| ExchangeActiveSyncId |ID do dispositivo do Exchange ActiveSync |
| ComputerSystemDescription |Descrição do sistema |
| ComputerSystemName |Nome do Sistema |
| ComputerSystemManufacturer |Fabricante do sistema |
| ComputerSystemModel |Modelo do sistema |
| UserName |Nome de usuário |
| OSType |Tipo de SO |
| OSCaption |Legenda do sistema operacional |
| OSName |Nome do sistema operacional |
| OSManufacturer |Fabricante do sistema operacional |
| OSProductSuite |Conjunto de produtos do sistema operacional |
| OSProductType |Tipo de produto do sistema operacional |
| Localidade |Localidade do sistema operacional |
| PhysicalMemoryCapacity |Capacidade de memória física (em bytes) |
| PhysicalMemoryRemovable |Memória removível física (em bytes) |
| SystemEnclosureChassisTypesInnerText |Define o tipo de chassi do sistema para este dispositivo. Os números indicam os seguintes valores: 0 ou vazio = Desconhecido 1 = é uma área de trabalho 2 = é um Laptop 3 = é uma Estação de trabalho 4 = é um Servidor de uma empresa 100 = é um Telefone 101 = é um Tablet 102/103 = outro tipo desconhecido de dispositivo móvel |
| SystemEnclosureModel |Modelo de compartimento do sistema |
| SystemEnclosureSerialNumber |Número de série do compartimento do sistema |
| NetworkAdapterConfigurationText |Texto de configuração do adaptador de rede |
| MacAddress |Endereço MAC |
| SmsID |ID do dispositivo Intune |
| CertExpiry |Data de expiração do certificado de gerenciamento do MDM |
| DeviceClientAgentVersion |Versão de agente do cliente |
| DeviceClientID |ID do cliente do dispositivo |
| SerialNumber |Número de Série |
| DeviceManufacturer |Fabricante do Dispositivo |
| DMVersion |Versão de DM |
| FirmwareVersion |Versão do Firmware |
| HardwareVersion |Versão de Hardware |
| PlatformType |Tipo de Plataforma |
| ProcessorLevel |Nível do processador |
| ProcessorRevision |Revisão do processador |
| Produto |Produto |
| ProductVersion |Versão do produto |
| OEM |Fabricante de equipamentos original |
| DeviceBuildVersion |Versão Build do dispositivo |
| Meid |Identificador de equipamentos móveis. |
| PhoneNumber |Número do telefone |
| SubscriberCarrierNetwork |Nome de rede da operadora de telefone |
| CellularTechnology |Tipo de rede da operadora de telefone (CDMA/GSM) |
| Imsi |Número IMSI |
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
| PasswordExpiration |Senha – data de expiração |
| AllowRecoveryPassword |Permitir recuperação de senha |
| PasswordAutoLockTimeout |Senha – tempo limite de bloqueio automático |
| PasswordType |Tipo de senha |
| BacklightACTimeout |Tempo limite de luz de fundo quando conectada a uma fonte de alimentação |
| BacklightBatTimeout |Tempo limite de luz de fundo na bateria |
| PowerBackupPercent |Porcentagem de backup de energia |
| BatteryPercent |Porcentagem restante da bateria. |
| PlatformID |ID da plataforma |
| ExchangeDeviceID |ID de dispositivo do Exchange |
| SmsProcessorDescription |Descrição do processador |
| OwnerEmailAddress |Endereço de email específico do proprietário |
| DeviceOSName |Nome do sistema operacional |
| WifiMac |Endereço MAC do WIFI |
| EthernetMac |Endereço MAC de Ethernet |
| RequireEncryption |Indica se o dispositivo é criptografado ou não. |
| ActivationLockBypassCode |Código de bypass do bloqueio de ativação |

## <a name="applicationinventory"></a>ApplicationInventory

A entidade **ApplicationInventory** lista os aplicativos encontrados no dispositivo no momento da coleta de inventário.

| Propriedade  | Descrição |
|---------|------------|
| DeviceKey |Uma referência à tabela de dispositivos |
| ApplicationKey |? (copiado do ExchangeDeviceService\DeviceApplication) |
| ApplicationName |? (copiado do ExchangeDeviceService\DeviceApplication) |
| ApplicationVersion |? (copiado do ExchangeDeviceService\DeviceApplication) |
| BundleSize |? (copiado do ExchangeDeviceService\DeviceApplication) |
