---
title: Coleções do Intune Date Warehouse
titleSuffix: Microsoft Intune
description: As coleções do Intune Data Warehouse oferecem detalhes relacionados à API do Data Warehouse.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/09/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 29f09230-dc56-43db-b599-d961967bda49
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune
ms.collection: M365-identity-device-management
ms.openlocfilehash: 00a0bd4936d1ad8ba8dd52f1839e7d42505db60e
ms.sourcegitcommit: 601327125ac8ae912d8159422de8aac7dbdc25f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59429217"
---
#  <a name="intune-data-warehouse-collections"></a>Coleções do Intune Data Warehouse

As coleções do Intune Data Warehouse a seguir oferecem propriedades, descrições e exemplos para coleções v 1.0 das entidades da API do Data Warehouse. 

## <a name="apprevisions"></a>appRevisions
A entidade **appRevision** lista todas as versões de aplicativos.

|          Propriedade          |                                      Descrição                                      |                Exemplo               |
|:--------------------------:|:-------------------------------------------------------------------------------------:|:------------------------------------:|
| AppKey                     | Identificador exclusivo do aplicativo.                                                         | 123                                  |
| ApplicationId              | Identificador exclusivo do aplicativo – semelhante a AppKey, mas é uma chave natural.        | b66bc706-ffff-7437-0340-032819502773 |
| Revisão                   | A versão mencionada pelo administrador durante o carregamento do binário.                   | 2                                    |
| Título                      | Título do aplicativo.                                                                     | Excel                                |
| Editor                  | Editor do aplicativo.                                                                 | Microsoft                            |
| UploadState                | Estado de upload do aplicativo.                                                              | 1                                    |
| AppTypeKey                 | Referência ao AppType descrito na próxima seção.                            | 1                                    |
| VppProgramTypeKey          | Referência ao VppProgramType descrito abaixo.                                        | 30876                                |
| CreationTime               | A hora em que esta revisão foi criada.                                            | 23/11/2016 0:00                      |
| ModifiedTime               | Última vez em que qualquer coisa relacionada a esta revisão foi alterada.                            | 23/11/2016 0:00                      |
| Tamanho                       | Tamanho do binário em bytes.                                                          | 120.392.000                          |
| StartDateInclusiveUTC      | A data e a hora em UTC em que essa revisão de aplicativo foi criada no data warehouse.      | 23/11/2016 0:00                      |
| EndDateExclusiveUTC        | A data e a hora em UTC em que essa revisão de aplicativo se tornou obsoleta.                        | 23/11/2016 0:00                      |
| IsCurrent                  | Indica se a versão desse aplicativo está atualizada ou não no data warehouse.         | Verdadeiro/Falso                           |
| RowLastModifiedDateTimeUTC | A data e a hora em UTC em que a versão desse aplicativo foi modificada pela última vez no data warehouse. | 23/11/2016 0:00                      |

## <a name="apptypes"></a>appTypes
A entidade **appType** lista a origem da instalação de um aplicativo.

|   Propriedade  |        Descrição        |
|:-----------:|:-------------------------:|
| AppTypeID   | ID do tipo           |
| AppTypeKey  | Chave substituta para a chave |
| AppTypeName | Tipo de aplicativo                  |

### <a name="example"></a>Exemplo

| AppTypeID |                Nome               |                     Descrição                     |
|:---------:|:---------------------------------:|:---------------------------------------------------:|
| 0         | Aplicativo da loja Android               | Um aplicativo da loja Android.                             |
| 1         | Aplicativo LOB para Android                 | Um aplicativo Android de linha de negócios.                  |
| 2         | Aplicativo gerenciado da Android Store (MAM) | Um aplicativo da loja Android que tem o gerenciamento habilitado. |
| 3         | Aplicativo da iOS Store                   | Um aplicativo da iOS Store.                                 |
| 4         | Aplicativo LOB para iOS                     | Um aplicativo iOS de linha de negócios.                      |
| 5         | Aplicativo gerenciado da iOS Store (MAM)     | Um aplicativo da iOS Store habilitado para gerenciamento.       |
| 6         | O365 Pro Plus Suite             | O Pacote do Office 365 Pro Plus para Windows 10.     |
| 7         | Aplicativo Web                         | Um aplicativo Web.                                        |
| 8         | Aplicativo da Windows Phone 8.1 Store     | Um aplicativo da Windows Phone 8.1 Store.                    |
| 9         | Aplicativo da Windows Store               | Um aplicativo da Windows Store.                              |
| 10        | Aplicativos LOB para Windows                | Um aplicativo de linha de negócios AppX do Windows.              |
| 11        | Windows Mobile MSI              | Um aplicativo de linha de negócios do MSI.                      |
| 12        | Aplicativo LOB para Windows Phone           | Um aplicativo de linha de negócios do Windows Phone.             |

## <a name="compliancepolicystatusdeviceactivities"></a>compliancePolicyStatusDeviceActivities
A tabela a seguir resume o status de atribuição de políticas de conformidade para dispositivos. Ela lista a contagem de dispositivos encontrados em cada estado de conformidade.

|    Propriedade   |                                                                                      Descrição                                                                                     |  Exemplo |
|:-------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey       | A chave de data quando o resumo foi criado para a política de conformidade.                                                                                                                   | 20161204 |
| Unknown       | O número de dispositivos que estão offline ou falharam ao se comunicar com o Intune ou com o Azure AD por outras razões.                                                                           | 5        |
| NotApplicable | O número de dispositivos em que as políticas de conformidade do dispositivo direcionadas pelo administrador não são aplicáveis.                                                                                     | 201      |
| Compatível     | O número de dispositivos que aplicaram com êxito uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador.                                                                        | 4083     |
| InGracePeriod | O número de dispositivos que não estão em conformidade, mas estão em um período de carência definido pelo administrador.                                                                                  | 57       |
| NonCompliant  | O número de dispositivos que falharam ao aplicar uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador ou em que o usuário não está em conformidade com as políticas direcionadas pelo administrador. | 43       |
|    Erro do      |    O número de dispositivos que falharam ao se comunicar com o Intune ou com o Azure AD e retornaram uma mensagem de erro.                                                                          |    3     |

## <a name="compliancepolicystatusdeviceperpolicyactivities"></a>compliancePolicyStatusDevicePerPolicyActivities
A tabela a seguir resume o status de atribuição de políticas de conformidade para dispositivos por política e por tipo de política. Ela lista a contagem de dispositivos encontrados em cada estado de conformidade para cada política de conformidade atribuída.

|      Propriedade     |                                                                                      Descrição                                                                                     |  Exemplo |
|:-----------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------:|
| DateKey           | A chave de data quando o resumo foi criado para a política de conformidade.                                                                                                                   | 20161219 |
| PolicyKey         | A chave para a política de conformidade para a qual o resumo foi criado.                                                                                                                   | 10178    |
| PolicyPlatformKey | A chave para o tipo de plataforma da política de conformidade para a qual o resumo foi criado.                                                                                            | 5        |
| Unknown           | O número de dispositivos que estão offline ou falharam ao se comunicar com o Intune ou com o Azure AD por outras razões.                                                                           | 13       |
| NotApplicable     | O número de dispositivos em que as políticas de conformidade do dispositivo direcionadas pelo administrador não são aplicáveis.                                                                                     | 3        |
| Compatível         | O número de dispositivos que aplicaram com êxito uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador.                                                                        | 45       |
| InGracePeriod     | O número de dispositivos que não estão em conformidade, mas estão em um período de carência definido pelo administrador.                                                                                  | 3        |
| NonCompliant      | O número de dispositivos que falharam ao aplicar uma ou mais políticas de conformidade do dispositivo direcionadas pelo administrador ou em que o usuário não está em conformidade com as políticas direcionadas pelo administrador. | 7        |
| Erro do             | O número de dispositivos que falharam ao se comunicar com o Intune ou com o Azure AD e retornaram uma mensagem de erro.                                                                             | 3        |
## <a name="compliancestates"></a>complianceStates

|      Propriedade      |                       Descrição                      |
|:------------------:|:------------------------------------------------------:|
| complianceStatus   | Status de conformidade dos dispositivos com mdmStatusKey       |
| complianceStateKey | A chave de conformidade para corresponder o dispositivo com o status de conformidade |
| complianceStateID  | A ID para corresponder a esse estado de conformidade                |

### <a name="example"></a>Exemplo

|  complianceStatus  |                       Descrição                      |
|:------------------:|:------------------------------------------------------:|
|    Unknown         |    Desconhecido.                                                                        |
|    Compatível       |    Compatível.                                                                      |
|    Fora de Conformidade    |       O dispositivo não está em conformidade e é bloqueado de recursos corporativos.             |
|    Conflito        |    Está em conflito com outras regras.                                                      |
|    Erro do           |       Erro.                                                                       |
|    ConfigManager   |    Gerenciado pelo Config Manager.                                                      |
|    InGracePeriod   |       O dispositivo não está em conformidade, mas ainda tem acesso a recursos corporativos          |

## <a name="dates"></a>datas
A entidade **data** representa datas que são referenciadas em várias entidades do data warehouse.

|     Propriedade    |                       Descrição                      |    Exemplo    |
|:---------------:|:------------------------------------------------------:|:-------------:|
| DateKey         | Identificador exclusivo desta data no data warehouse. | 20160703      |
| FullDate        | Esta data representada no formato de data/hora completo.        | 03/07/2016 0:00 |
| DayOfWeek       | Dia da semana                                            | 1             |
| DayOfMonth      | Dia do mês                                           | 3             |
| DayOfYear       | Dia do ano                                            | 185           |
| WeekOfYear      | Semana do ano                                           | 28            |
| MonthOfYear     | Mês do ano                                      | 7             |
| CalendarQuarter | Trimestre calendário                                       | 3             |
| CalendarYear    | Ano calendário                                          | 2016          |
| DateKey         | Identificador exclusivo desta data no data warehouse. | 20160703      |
| FullDate        | Esta data representada no formato de data/hora completo.        | 03/07/2016 0:00 |
| DayOfWeek       | Dia da semana                                            | 1             |
| DayOfMonth      | Dia do mês                                           | 3             |
| DayOfYear       | Dia do ano                                            | 185           |
| WeekOfYear      | Semana do ano                                           | 28            |
| MonthOfYear     | Mês do ano                                      | 7             |
| CalendarQuarter | Trimestre calendário                                       | 3             |
| CalendarYear    | Ano calendário                                          | 2016          |

## <a name="devicecategories"></a>deviceCategories

|      Propriedade      |                                    Descrição                                   |                Exemplo               |
|:------------------:|:--------------------------------------------------------------------------------:|:------------------------------------:|
| deviceCategoryID   | O identificador exclusivo da categoria do dispositivo.                                       | fb415ba2-7c08-41f6-a5e5-685b50da2c4c |
| deviceCategoryKey  | Identificador exclusivo da categoria do dispositivo no data warehouse – chave substituta | 1                                    |
| deviceCategoryName | Nome de exibição da categoria do dispositivo.                                            | Smartphones                          |

## <a name="deviceconfigurationprofiledeviceactivities"></a>deviceConfigurationProfileDeviceActivities
A entidade **DeviceConfigurationProfileDeviceActivity** lista o número de dispositivos com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um dispositivo estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade lista quantos dispositivos estão em qual estado em um determinado dia nos últimos 30 dias.

|  Propriedade |                                          Descrição                                          |  Exemplo |
|:---------:|:---------------------------------------------------------------------------------------------:|:--------:|
| DateKey   | A chave de data quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse. | 20160703 |
| Pending (Pendente)   | Número de dispositivos exclusivos no estado pendente.                                                    | 123      |
| Bem-sucedido | Número de dispositivos exclusivos no estado de êxito.                                                    | 12       |
| Erro do     | Número de dispositivos exclusivos no estado de erro.                                                      | 10       |
| Failed (Falha)    | Número de dispositivos exclusivos no estado de falha.                                                     | 2        |

## <a name="deviceconfigurationprofileuseractivities"></a>deviceConfigurationProfileUserActivities 
A entidade **DeviceConfigurationProfileUserActivity** lista o número de usuários com o estado de êxito, pendente, com falha ou de erro por dia. O número reflete os perfis de configuração do Dispositivo atribuídos à entidade. Por exemplo, se um usuário estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito e o outro em um estado de erro, o usuário no estado de erro será contado. A entidade **DeviceConfigurationProfileUserActivity** lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias. 

| Propriedade  | Descrição  | Exemplo  |
|------------|----------------------------------------------------------------------------------------------|-----------|
| DateKey  | Chave de data quando o check-in do perfil de configuração do dispositivo foi registrado no data warehouse.  | 20160703  |
| Pending (Pendente)  | Número de usuários exclusivos no estado pendente.  | 123  |
| Bem-sucedido  | Número de usuários exclusivos no estado de êxito.  | 12  |
| Erro do  | Número de usuários exclusivos no estado de erro.  | 10  |
| Failed (Falha)  | Número de usuários exclusivos no estado de falha.  | 2  |

## <a name="devicepropertyhistories"></a>devicePropertyHistories

|          Propriedade          |                                                                                      Descrição                                                                                     |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DateKey                    | Referência à tabela de data que indica o dia.                                                                                                                                          |
| DeviceKey                  | Identificador exclusivo do dispositivo no data warehouse – chave substituta. Esta é uma referência à tabela Dispositivo que contém a ID do dispositivo do Intune.                               |
| DeviceName                 | Nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome de outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| DeviceRegistrationStateKey | A chave do atributo de estado do registro do dispositivo.                                                                                                                    |
| OwnerTypeKey               | A chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido.                                                                                                  |
| ManagementStateKey         | A chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado.                                                |
| AzureADRegistered          | Se o dispositivo está registrado no Azure Active Directory.                                                                                                                             |
| ComplianceStateKey         | Uma chave para ComplianceState.                                                                                                                                                            |
| OSVersion                  | Versão do SO.                                                                                                                                                                          |
| Com jailbreak                 | Se o dispositivo foi desbloqueado por jailbreak ou por rooting.                                                                                                                                         |
| DeviceCategoryKey          | A chave do atributo de categoria deste dispositivo.                                                                                                                                    |
## <a name="deviceregistrationstates"></a>deviceRegistrationStates
A entidade **DeviceRegistrationState** representa o tipo de registro referenciado por outras coleções do data warehouse. 

|           Propriedade          |                                     Descrição                                     |
|:---------------------------:|:-----------------------------------------------------------------------------------:|
| deviceRegistrationStateID   | Identificador exclusivo para o estado do registro                                            |
| deviceRegistrationStateKey  | O identificador exclusivo do estado do registro dispositivo no data warehouse – chave substituta |
| deviceRegistrationStateName | Estado do Registro                                                                  |
|    NotRegistered                     |    Não registrado                                                                                                                                                                  |
|    Registrada                        |       Registrada                                                                                                                                                                   |
|    Revogado                           |       O estado significa que o administrador de TI bloqueou o cliente e o cliente pode ser desbloqueado. Um dispositivo também poderá estar no estado Revogado depois de apagado ou desativado.        |
|    KeyConflict                       |    Conflito de chave                                                                                                                                                                    |
|    ApprovalPending                   |    Aprovação pendente                                                                                                                                                                |
|    CertificateReset                  |    Redefinir certificado                                                                                                                                                               |
|    NotRegisteredPendingEnrollment    |    Inscrição pendente não registrada                                                                                                                                               |
|    Unknown                           |    Estado desconhecido                                                                                                                                                                   |

## <a name="devices"></a>dispositivos
A entidade **dispositivo** lista todos os dispositivos registrados no gerenciamento e suas propriedades correspondentes.

|          Propriedade          |                                                                                       Descrição                                                                                      |
|:--------------------------:|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|
| DeviceKey                  | O identificador exclusivo do dispositivo no data warehouse – chave substituta.                                                                                                               |
| DeviceId                   | O identificador exclusivo do dispositivo.                                                                                                                                                     |
| DeviceName                 | O nome do dispositivo em plataformas que permitem a nomeação de um dispositivo. Em outras plataformas, o Intune cria um nome com base em outras propriedades. Esse atributo pode não estar disponível para todos os dispositivos. |
| DeviceTypeKey              | A chave do atributo de tipo de dispositivo para este dispositivo.                                                                                                                                    |
| DeviceRegistrationState    | A chave do atributo de estado do registro do cliente para este dispositivo.                                                                                                                      |
| OwnerTypeKey               | A chave do atributo de tipo de proprietário para este dispositivo: corporativo, pessoal ou desconhecido.                                                                                                    |
| EnrolledDateTime           | A data e hora em que este dispositivo foi registrado.                                                                                                                                         |
| LastSyncDateTime           | O último check-in conhecido do dispositivo no Intune.                                                                                                                                              |
| ManagementAgentKey         | A chave do agente de gerenciamento associado a esse dispositivo.                                                                                                                             |
| ManagementStateKey         | A chave do estado de gerenciamento associado a esse dispositivo, que indica o estado mais recente de uma ação remota ou se foi ele desbloqueado/modificado.                                                |
| AzureADDeviceId            | A ID de dispositivo do Azure para este dispositivo.                                                                                                                                                  |
| AzureADRegistered          | Se o dispositivo está registrado no Azure Active Directory.                                                                                                                             |
| DeviceCategoryKey          | A chave da categoria associada a este dispositivo.                                                                                                                                     |
| DeviceEnrollmentType       | A chave do tipo de registro associada a este dispositivo, que indica o método de registro.                                                                                             |
| ComplianceStateKey         | A chave do estado de conformidade associado a este dispositivo.                                                                                                                             |
| OSVersion                  | Versão do sistema operacional do dispositivo.                                                                                                                                                |
| EasDeviceId                | A ID do Exchange ActiveSync do dispositivo.                                                                                                                                                  |
| SerialNumber               | SerialNumber                                                                                                                                                                           |
| UserId                     | O identificador exclusivo do usuário associado ao dispositivo.                                                                                                                           |
| RowLastModifiedDateTimeUTC | A data e a hora em UTC em que este dispositivo foi modificado pela última vez no data warehouse.                                                                                                       |
| Fabricante               | Fabricante do dispositivo                                                                                                                                                             |
| Modelo                      | Modelo do dispositivo                                                                                                                                                                    |
| OperatingSystem            | Sistema operacional do dispositivo. Windows, iOS etc.                                                                                                                                   |
| IsDeleted                  | Binário para mostrar se o dispositivo foi excluído ou não.                                                                                                                                 |
| AndroidSecurityPatchLevel  | Nível de patch de segurança do Android                                                                                                                                                           |
| MEID                       | MEID                                                                                                                                                                                   |
| isSupervised               | Estado de dispositivo não supervisionado                                                                                                                                                               |
| FreeStorageSpaceInBytes    | Armazenamento livre em bytes.                                                                                                                                                                 |
| TotalStorageSpaceInBytes   | Armazenamento total em bytes.                                                                                                                                                                |
| EncryptionState            | Estado de criptografia no dispositivo.                                                                                                                                                      |
| SubscriberCarrier          | A operadora do assinante do dispositivo                                                                                                                                                       |
| PhoneNumber                | O número de telefone do dispositivo                                                                                                                                                             |
| IMEI                       | IMEI                                                                                                                                                                                   |
| CellularTechnology         | Tecnologia celular do dispositivo                                                                                                                                                    |
| WiFiMacAddress             | MAC Wi-Fi                                                                                                                                                                              |


## <a name="devicetypes"></a>deviceTypes
A entidade **deviceType** representa o tipo de dispositivo referenciado por outras entidades do data warehouse. O tipo de dispositivo geralmente descreve o modelo do dispositivo, o fabricante ou uma combinação de ambos.

|    Propriedade    |                                  Descrição                                 |
|:--------------:|:----------------------------------------------------------------------------:|
| DeviceTypeID   | Identificador exclusivo do tipo de dispositivo                                       |
| DeviceTypeKey  | Identificador exclusivo do tipo de dispositivo no data warehouse – chave substituta |
| DeviceTypeName | O tipo de dispositivo                                                                |

### <a name="example"></a>Exemplo

| deviceTypeID |        Nome       |                      Descrição                      |
|:------------:|:-----------------:|:-----------------------------------------------------:|
| -1           | Não disponível   | O tipo de dispositivo está indisponível.                     |
| 0            | Área de Trabalho           | Dispositivo do Windows Desktop                              |
| 1            | Windows           | Dispositivo Windows                                      |
| 2            | WinMO6            | Dispositivo Windows Mobile 6.0                           |
| 3            | Nokia             | Dispositivo Nokia                                        |
| 4            | WindowsPhone      | Dispositivo Windows Phone                                |
| 5            | Mac               | Dispositivo Mac                                          |
| 6            | WinCE             | Dispositivo Windows CE                                   |
| 7            | WinEmbedded       | Dispositivo Windows Embedded                             |
| 8            | IPhone            | Dispositivo iPhone                                       |
| 9            | IPad              | Dispositivo iPad                                         |
| 10           | IPod              | Dispositivo iPod                                         |
| 11           | Android           | Dispositivo gerenciado Android usando o administrador do dispositivo   |
| 12           | ISocConsumer      | Dispositivo iSoc Consumer                                |
| 13           | Unix              | Dispositivo Unix                                         |
| 14           | MacMDM            | Dispositivo Mac OS X gerenciado com o agente MDM interno |
| 15           | HoloLens          | Dispositivos do HoloLens                                       |
| 16           | SurfaceHub        | Dispositivo Surface Hub                                  |
| 17           | AndroidForWork    | Gerenciado pelo dispositivo Android usando o proprietário do perfil do Android  |
| 18           | AndroidEnterprise | Dispositivo Android Enterprise.                          |
| 100          | BlackBerry        | Dispositivo Blackberry                                   |
| 101          | Palm              | Dispositivo Palm                                         |
| 255          | Unknown           | O tipo de dispositivo desconhecido                                 |

## <a name="deviceenrollmenttypes"></a>deviceEnrollmentTypes
A entidade **deviceEnrollmentType** indica como um dispositivo foi inscrito. O tipo de registro captura o método de registro. Exemplos listam os diferentes tipos de registro e o que eles significam.

|         Propriedade         |                                    Descrição                                    |
|:------------------------:|:---------------------------------------------------------------------------------:|
| deviceEnrollmentTypeID   | Identificador exclusivo do tipo de registro.                                       |
| deviceEnrollmentTypeKey  | Identificador exclusivo do tipo de registro no data warehouse – chave alternativa. |
| deviceEnrollmentTypeName | Nome do tipo de registro.                                                           |

### <a name="example"></a>Exemplo

| enrollmentTypeID |                Nome                |                                        Descrição                                       |
|:----------------:|:----------------------------------:|:----------------------------------------------------------------------------------------:|
| 0                | Unknown                            | O tipo de registro não foi coletado                                                      |
| 1                | UserEnrollment                     | Registro orientado por usuário por meio do canal BYOD.                                           |
| 2                | DeviceEnrollmentManager            | Registro de usuário com uma conta de gerenciador de registro do dispositivo.                              |
| 3                | AppleBulkWithUser                  | Registro em massa da Apple com desafio de usuário. (DEP, Apple Configurator)                   |
| 4                | AppleBulkWithoutUser               | Registro em massa da Apple sem desafio de usuário.   (DEP, Apple Configurator, Mobile Config) |
| 5                | WindowsAzureADJoin                 | Ingresso no Azure AD do Windows 10.                                                                |
| 6                | WindowsBulkUserless                | Registro em massa do Windows 10 por meio do ICD com certificado.                               |
| 7                | WindowsAutoEnrollment              | Registro automático do Windows 10.   (Adicionar conta de trabalho)                                    |
| 8                | WindowsBulkAzureDomainJoin         | Ingresso em massa no Azure AD do Windows 10.                                                           |
| 9                | WindowsCoManagement                | Cogerenciamento do Windows 10 disparado por AutoPilot ou por Política de Grupo.                       |
| 10               | WindowsAzureADJoinsUsingDeviceAuth | Ingresso no Azure AD do Windows 10 usando Device Auth.                                            |

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

## <a name="intunemanagementextensions"></a>intuneManagementExtensions
A **intuneManagementExtension** lista a integridade da **intuneManagementExtension** em cada dispositivo Windows 10 por dia. Os dados são retidos pelos últimos 60 dias.

|       Propriedade      |                          Descrição                          | Exemplo |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| DateKey             | Identificador exclusivo da data.                                | 123     |
| TenantKey           | Identificador exclusivo do locatário.                              | 456     |
| DeviceKey           | Identificador exclusivo do dispositivo.                              | 789     |
| ExtensionVersionKey | Identificador exclusivo da versão IntuneManagementExtension. | 1       |
| ExtensionStateKey   | Identificador exclusivo do estado de integridade.                            | 2       |

## <a name="intunemanagementextensionhealthstates"></a>intuneManagementExtensionHealthStates
O **IntuneManagementExtensionHealthState** lista todos os estados de integridade possíveis da **IntuneManagementExtension**.

|      Propriedade     |                   Descrição                  | Exemplo |
|:-----------------:|:----------------------------------------------:|:-------:|
| ExtensionStateKey | Identificador exclusivo do estado de integridade.           | 2       |
| ExtensionState    | Estado de integridade de um IntuneManagementExtension. | Íntegros |

## <a name="intunemanagementextensionversions"></a>intuneManagementExtensionVersions
A entidade **IntuneManagementExtensionVersion** lista todas as versões usadas pelo **IntuneManagementExtension**.

|       Propriedade      |                          Descrição                          | Exemplo |
|:-------------------:|:-------------------------------------------------------------:|:-------:|
| ExtensionVersionKey | Identificador exclusivo da versão IntuneManagementExtension. | 1       |
| ExtensionVersion    | O número de versão de quatro dígitos.                                   | 1.0.2.0 |

## <a name="mamapplications"></a>MamApplications

A entidade **MamApplication** lista aplicativos de linha de negócios (LOB) que são gerenciados pelo gerenciamento de aplicativo móvel (MAM) sem registro em sua empresa.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| mamApplicationKey |Identificador exclusivo do aplicativo MAM. | 432 |
| mamApplicationName |Nome do aplicativo MAM. |Exemplo de Nome de Aplicativo MAM |
| mamApplicationId |ID do aplicativo referente ao aplicativo MAM. | 123 |
| IsDeleted |Indica se o registro desse aplicativo MAM foi atualizado. <br>Verdadeiro – o aplicativo MAM tem um novo registro com campos atualizados nesta tabela. <br>Falso – o registro mais recente para este aplicativo MAM. |Verdadeiro/Falso |
| StartDateInclusiveUTC |Data e hora em UTC em que esse aplicativo de MAM foi criado no data warehouse. |23/11/2016 12:00:00 AM |
| DeletedDateUTC |Data e hora em UTC em que IsDeleted foi alterado para True. |23/11/2016 12:00:00 AM |
| RowLastModifiedDateTimeUTC |Data e hora em UTC em que esse aplicativo de MAM foi modificado pela última vez no data warehouse. |23/11/2016 12:00:00 AM |


## <a name="mamapplicationinstances"></a>MamApplicationInstances

A entidade **MamApplicationInstance** lista aplicativos de Gerenciamento de aplicativo móvel (MAM) gerenciados como instâncias singulares por usuário por dispositivo. Todos os usuários e dispositivos listados com a entidade são protegidos e, portanto, têm pelo menos uma política de MAM atribuída a eles.


|          Propriedade          |                                                                                                  Descrição                                                                                                  |               Exemplo                |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------|
|   ApplicationInstanceKey   |                                                               Identificador exclusivo da instância do aplicativo de MAM no data warehouse – chave alternativa.                                                                |                 123                  |
|           UserId           |                                                                              A ID de usuário que tem esse aplicativo de MAM instalado.                                                                              | b66bc706-ffff-7437-0340-032819502773 |
|   ApplicationInstanceId    |                                              Identificador exclusivo da instância do aplicativo de MAM – semelhante a ApplicationInstanceKey, mas o identificador é uma chave natural.                                              | b66bc706-ffff-7437-0340-032819502773 |
| mamApplicationId | ID do aplicativo referente ao Aplicativo Mam para o qual esta Instância de Aplicativo Mam foi criada.   | 23/11/2016 12:00:00 AM   |
|     ApplicationVersion     |                                                                                     Versão deste aplicativo de MAM.                                                                                      |                  2                   |
|        CreatedDate         |                                                                 Data em que este registro da instância do aplicativo MAM foi criado. O valor pode ser nulo.                                                                 |        23/11/2016 12:00:00 AM        |
|          Plataforma          |                                                                          Plataforma do dispositivo no qual este aplicativo de MAM está instalado.                                                                           |                  2                   |
|      PlatformVersion       |                                                                      Versão da plataforma do dispositivo no qual este aplicativo de MAM está instalado.                                                                       |                 2.2                  |
|         SdkVersion         |                                                                            A versão do SDK do MAM com o qual esse aplicativo de MAM foi encapsulado.                                                                            |                 3.2                  |
| mamDeviceId | ID do dispositivo referente ao dispositivo com o qual a Instância do Aplicativo MAM está associada.   | 23/11/2016 12:00:00 AM   |
| mamDeviceType | Tipo de dispositivo referente ao dispositivo com o qual a Instância do Aplicativo MAM está associada.   | 23/11/2016 12:00:00 AM   |
| mamDeviceName | Nome de dispositivo referente ao dispositivo com o qual a Instância do Aplicativo MAM está associada.   | 23/11/2016 12:00:00 AM   |
|         IsDeleted          | Indica se o registro de instância desse aplicativo MAM foi atualizado. <br>Verdadeiro – a instância desse aplicativo MAM tem um novo registro com campos atualizados nesta tabela. <br>Falso – o registro mais recente para a instância deste aplicativo MAM. |              Verdadeiro/Falso              |
|   StartDateInclusiveUtc    |                                                              Data e hora em UTC em que a instância desse aplicativo de MAM foi criada no data warehouse.                                                               |        23/11/2016 12:00:00 AM        |
|       DeletedDateUtc       |                                                                             Data e hora em UTC em que IsDeleted foi alterado para True.                                                                              |        23/11/2016 12:00:00 AM        |
| RowLastModifiedDateTimeUtc |                                                           Data e hora em UTC em que a instância desse aplicativo de MAM foi modificada pela última vez no data warehouse.                                                            |        23/11/2016 12:00:00 AM        |

## <a name="mamcheckins"></a>MamCheckins

A entidade **MamCheckin** representa os dados reunidos quando uma instância de aplicativo de Gerenciamento de aplicativo móvel (MAM) foi marcada com o Intune Service. 

> [!Note]  
> Quando uma instância do aplicativo faz check-in várias vezes ao dia, o data warehouse a armazena como se fosse um único check-in.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| DateKey |Chave de data em que o check-in do aplicativo de MAM foi registrado no data warehouse. | 20160703 |
| ApplicationInstanceKey |Chave da instância do aplicativo associada ao check-in desse aplicativo de MAM. | 123 |
| UserKey |Chave do usuário associada ao check-in desse aplicativo de MAM. | 4323 |
| mamApplicationKey |Chave de Aplicativo referente ao Aplicativo associado com o check-in do Aplicativo MAM. | 432 |
| DeviceHealthKey |Chave do DeviceHealth associada ao check-in desse aplicativo de MAM. | 321 |
| PlatformKey |Representa a plataforma do dispositivo associado ao check-in desse aplicativo de MAM. |123 |
| LastCheckInDate |Data e hora em que este aplicativo MAM fez check-in pela última vez. O valor pode ser nulo. |23/11/2016 12:00:00 AM |

## <a name="mamdevicehealths"></a>MamDeviceHealths

A entidade **MamDeviceHealth** representa os dispositivos que têm políticas de Gerenciamento de aplicativo móvel (MAM) implantadas neles, mesmo que estejam desbloqueados.

| Propriedade | Descrição | Exemplo |
|---------|------------|--------|
| DeviceHealthKey |Identificador exclusivo do dispositivo e sua integridade associada no data warehouse – chave alternativa. |123 |
| DeviceHealth |Identificador exclusivo do dispositivo e sua integridade associada – semelhante a DeviceHealthKey, mas o identificador é uma chave natural. |b66bc706-ffff-7777-0340-032819502773 |
| DeviceHealthName |Representa o status do dispositivo. <br>Não disponível – não há informações sobre este dispositivo. <br>Íntegro – o dispositivo não está desbloqueado. <br>Não íntegro – o dispositivo está desbloqueado. |Não disponível Íntegro Não íntegro |
| RowLastModifiedDateTimeUtc |Data e hora em UTC em que a Integridade desse dispositivo de MAM específico foi modificada pela última vez no data warehouse. |23/11/2016 12:00:00 AM |

## <a name="mamplatforms"></a>MamPlatforms

A entidade **MamPlatform** lista nomes e tipos de plataforma nos quais um aplicativo de Gerenciamento de aplicativo móvel (MAM) foi instalado.


|          Propriedade          |                                    Descrição                                    |                         Exemplo                         |
|----------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------|
|        PlatformKey         |     Identificador exclusivo da plataforma no data warehouse – chave alternativa.      |                           123                           |
|          Plataforma          | Identificador exclusivo da plataforma – semelhante a PlatformKey, mas é uma chave natural. |                           123                           |
|        PlatformName        |                                   Nome da plataforma                                   | Não disponível <br>Nenhum <br>Windows <br>IOS <br>Android. |
| RowLastModifiedDateTimeUtc | Data e hora em UTC em que essa plataforma foi modificada pela última vez no data warehouse.  |                 23/11/2016 12:00:00 AM                  |

## <a name="managementagenttypes"></a>managementAgentTypes
A entidade **managementAgentType** representa os agentes usados para gerenciar um dispositivo.

|         Propriedade        |                                       Descrição                                       |
|:-----------------------:|:---------------------------------------------------------------------------------------:|
| ManagementAgentTypeID   | Identificador exclusivo do tipo de agente de gerenciamento.                                         |
| ManagementAgentTypeKey  | Identificador exclusivo do tipo de agente de gerenciamento no data warehouse – chave alternativa. |
| ManagementAgentTypeName | Indica qual tipo de agente é usado para gerenciar o dispositivo.                              |

### <a name="example"></a>Exemplo

| ManagementAgentTypeID |                Nome               |                                  Descrição                                 |
|:---------------------:|:---------------------------------:|:----------------------------------------------------------------------------:|
| 1                     | EAS                               | O dispositivo é gerenciado por meio do Exchange Active Sync                         |
| 2                     | MDM                               | O dispositivo é gerenciado usando um agente MDM                                   |
| 3                     | EasMdm                            | O dispositivo é gerenciado pelo Exchange ActiveSync e por um agente MDM        |
| 4                     | IntuneClient                      | O dispositivo é gerenciado pelo agente do PC Intune                               |
| 5                     | EasIntuneClient                   | O dispositivo é gerenciado pelo Exchange ActiveSync e pelo PC Intune |
| 8                     | ConfigManagerClient               | O dispositivo é gerenciado pelo agente do System Center Configuration Manager     |
| 10                    | ConfigurationManagerClientMdm     | O dispositivo é gerenciado pelo Configuration Manager e MDM.                    |
| 11                    | ConfigurationManagerCLientMdmEas  | O dispositivo é gerenciado pelo Configuration Manager, pelo MDM e pelo Exchange Active Sync.               |
| 16                    | Unknown                           | O tipo de agente de gerenciamento desconhecido                                              |
| 32                    | Jamf                              | Os atributos do dispositivo serão buscados no Jamf.                               |
| 64                    | GoogleCloudDevicePolicyController |  O dispositivo é gerenciado pelo CloudDPC do Google.                                 |

## <a name="managementstates"></a>managementStates
A entidade **ManagementState** fornece detalhes sobre o estado do dispositivo. Detalhes podem ser úteis nos casos em que ações remotas são aplicadas, o dispositivo está desbloqueado ou modificado.

|       Propriedade      |                                     Descrição                                    |
|:-------------------:|:----------------------------------------------------------------------------------:|
| managementStateID   | Identificador exclusivo do estado do gerenciamento.                                       |
| managementStateKey  | Identificador exclusivo do estado de gerenciamento no data warehouse – chave substituta. |
| managementStateName | Indica o estado da ação remota aplicada a este dispositivo.                 |

### <a name="example"></a>Exemplo

| managementStateID |      Nome      |                                                   Descrição                                                   |
|:-----------------:|:--------------:|:---------------------------------------------------------------------------------------------------------------:|
| 0                 | Gerenciados        | Gerenciados com nenhuma ação remota pendente.                                                                       |
| 1                 | RetirePending  | Há um comando de desativação pendente para o dispositivo.                                                             |
| 2                 | RetireFailed   | O comando de desativação falhou no dispositivo.                                                                      |
| 3                 | WipePending    | Há um comando de apagamento pendente para o dispositivo.                                                               |
| 4                 | WipeFailed     | O comando de apagamento falhou no dispositivo.                                                                        |
| 5                 | Unhealthy      | Estado não íntegro.                                                                                              |
| 6                 | DeletePending  | Há um comando de exclusão pendente para o dispositivo.                                                             |
| 7                 | RetireIssued   | Um comando de desativação foi emitido para o dispositivo.                                                               |
| 8                 | WipeIssued     | Um comando de apagamento foi emitido.                                                                               |
| 9                 | WipeCanceled   | Um comando de apagamento foi cancelado.                                                                               |
| 10                | RetireCanceled | Um comando de desativação foi cancelado.                                                                             |
| 11                | Descoberto     | O dispositivo foi recém-descoberto pelo Intune e, assim ele fizer check-in pela primeira vez, mudará para o estado Gerenciado. |

## <a name="mobileappinstallstates"></a>mobileAppInstallStates
A entidade MobileAppInstallState representa o estado de instalação de um aplicativo móvel após sua atribuição a um grupo que contém dispositivos, usuários ou ambos.

|       Propriedade      |                        Descrição                       |
|:-------------------:|:--------------------------------------------------------:|
| AppInstallStateKey  | A ID exclusiva do estado de instalação do aplicativo para sua conta. |
| AppInstallState     | Valor de enumeração do estado de instalação do aplicativo.                     |
| AppInstallStateName | Nome do estado de instalação do aplicativo.                           |

## <a name="mobileappinstallstatuscounts"></a>mobileAppInstallStatusCounts
Representa um status de instalação do aplicativo móvel para um tipo de dispositivo de destino usando o Gerenciamento de aplicativo móvel por meio do Microsoft Intune.

|      Propriedade      |                                                          Descrição                                                          |
|:------------------:|:-----------------------------------------------------------------------------------------------------------------------------:|
| DateKey            | Chave da data quando o status de instalação do aplicativo foi registrado.                                                                     |
| AppKey             | A chave do aplicativo móvel usado para identificar uma instância de AppRevision.                                                          |
| DeviceTypeKey      | A chave do tipo de dispositivo associado ao aplicativo móvel.                                                              |
| AppInstallStateKey | A chave do estado de instalação do aplicativo usada para identificar uma instância de MobileAppInstallState.                                         |
| ErrorCode          | O código de erro retornado pelo instalador do aplicativo, a plataforma móvel ou o serviço referente à instalação do aplicativo. |
| Contagem              | Contagem total.                                                                                                                  |

## <a name="ownertypes"></a>ownerTypes
A entidade **ownerType** indica se um dispositivo é corporativo, pessoal ou desconhecido.

|    Propriedade   |                                                                                     Descrição                                                                                    |           Exemplo          |
|:-------------:|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:--------------------------:|
| ownerTypeID   | Identificador exclusivo do tipo de proprietário.                                                                                                                                               |                            |
| ownerTypeKey  | Identificador exclusivo do tipo de proprietário no data warehouse – chave alternativa.                                                                                                       |                            |
| ownerTypeName | Representa o tipo de proprietário dos dispositivos: corporativo– o dispositivo é de propriedade da empresa.  Pessoal – o dispositivo de propriedade pessoal (BYOD).   Desconhecido – não há informações sobre este dispositivo. | Corporativo Pessoal Desconhecido |

> [!Note]  
> Para o filtro `ownerTypeName` no Azure AD durante a criação de Grupos Dinâmicos para dispositivos, você precisará definir o valor de `deviceOwnership` como `Company`. Para obter mais informações, veja [Regras para dispositivos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices). 

## <a name="policies"></a>políticas
A entidade **Política** lista perfis de configuração do dispositivo, perfis de configuração do aplicativo e as políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

|          Propriedade          |                                                                       Descrição                                                                      |                Exemplo               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| PolicyKey                  | Chave exclusiva para representar a política no data warehouse.                                                                                              | 123                                  |
| PolicyId                   | Identificador exclusivo da política no data warehouse.                                                                                                 | b66bc706-ffff-7437-0340-032819502773 |
| PolicyName                 | Nome da política.                                                                                                                                    | "Linha de base do Windows 10"                |
| PolicyVersion              | Versão da política. Quando a política for editada ou alterada, será criada uma versão mais recente.                                                             | 1, 2, 3                              |
| IsDeleted                  | Indica se o registro da Política foi atualizado.  Verdadeiro – a política tem um novo registro com campos atualizados.  Falso – o registro mais recente para a política. | Verdadeiro/Falso                           |
| StartDateInclusiveUTC      | A data e a hora em UTC e que a política foi criada no data warehouse.                                                                              | 23/11/2016 0:00                      |
| DeletedDateUTC             | Data e hora em UTC em que IsDeleted foi alterado para True.                                                                                                   | 23/11/2016 0:00                      |
| RowLastModifiedDateTimeUTC | A data e a hora em UTC em que a política foi modificada pela última vez no data warehouse.                                                                        | 23/11/2016 0:00                      |

## <a name="policydeviceactivities"></a>policyDeviceActivities
A tabela a seguir lista o número de dispositivos com o estado de êxito, pendente, com falha, ou de erro por dia. O número reflete os dados por perfis de Tipo de Política. Por exemplo, se um dispositivo estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um dispositivo tem dois perfis atribuídos a ele, um no estado de êxito e outro em um estado de erro, a entidade incrementa o contador de Êxito e coloca o dispositivo no estado de erro. A entidade **policyDeviceActivity** lista quantos dispositivos estão em qual estado em determinado dia nos últimos 30 dias.

|  Propriedade |                                           Descrição                                           |        Exemplo        |
|:---------:|:-----------------------------------------------------------------------------------------------:|:---------------------:|
| DateKey   | A chave de data quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse. | 20160703              |
| Pending (Pendente)   | O número de dispositivos exclusivos no estado pendente.                                                    | 123                   |
| Bem-sucedido | O número de dispositivos exclusivos no estado de êxito.                                                    | 12                    |
| PolicyKey | A chave de política, pode ser unida com a política para obter o policyName.                                  | A linha de base do Windows 10 |
| Erro do     | O número de dispositivos exclusivos no estado de erro.                                                      | 10                    |
| Failed (Falha)    | O número de dispositivos exclusivos no estado de falha.                                                     | 2                     |

## <a name="policyplatformtypes"></a>policyPlatformTypes

|        Propriedade        |                      Descrição                      |     Exemplo    |
|:----------------------:|:-----------------------------------------------------:|:--------------:|
| PolicyPlatformTypeKey  | A chave exclusiva para o tipo de plataforma de política.        | 20170519       |
| PolicyPlatformTypeId   | O identificador exclusivo para o tipo de plataforma de política. | 1              |
| PolicyPlatformTypeName | O nome para o tipo de plataforma de política.              | AndroidForWork |

## <a name="policytypeactivities"></a>policyTypeActivities
A entidade **PolicyTypeActivity** lista o número acumulativo de dispositivos com o estado de êxito, pendente, com falha, ou de erro. Ela lista esses estados em relação a um perfil de configuração de dispositivo, perfil de configuração do aplicativo ou política de conformidade por dia.

|    Propriedade   |                                          Descrição                                          |           Exemplo           |
|:-------------:|:---------------------------------------------------------------------------------------------:|:---------------------------:|
| DateKey       | A chave de data quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse. | 20160703                    |
| PolicyKey     | A chave de política, pode ser unida com a política para obter o policyName.                                | Linha de base do Windows 10         |
| PolicyTypeKey | O tipo de chave de política, pode ser unido com o tipo de política para obter o nome do tipo de política.             | Política de conformidade do Windows10 |
| Pending (Pendente)       | Número de dispositivos exclusivos no estado pendente.                                                    | 123                         |
| Bem-sucedido     | Número de dispositivos exclusivos no estado de êxito.                                                    | 12                          |
| Erro do         | Número de dispositivos exclusivos no estado de erro.                                                      | 10                          |
| Failed (Falha)        | Número de dispositivos exclusivos no estado de falha.                                                     | 2                           |

## <a name="policytypes"></a>policyTypes
A entidade **PolicyType** lista os tipos de perfis de configuração do dispositivo, perfis de configuração do aplicativo e políticas de conformidade. Você pode atribuir as políticas com o Gerenciamento de dispositivo móvel (MDM) a um grupo em sua empresa.

|    Propriedade    |                       Descrição                      |            Exemplo            |
|:--------------:|:------------------------------------------------------:|:-----------------------------:|
| PolicyTypeId   | Identificador exclusivo da política no sistema de origem.  | 123                           |
| PolicyTypeKey  | Identificador exclusivo da política no data warehouse. | 1                             |
| PolicyTypeName | Nome do tipo de política.                               | Política de conformidade do Windows 10. |

## <a name="policyuseractivities"></a>policyUserActivities
A tabela a seguir lista o número de usuários com o estado de êxito, pendente, com falha, ou de erro por dia. O número reflete os dados por perfis de Tipo de Política. Por exemplo, se um usuário estiver no estado de êxito para todas as suas políticas atribuídas, ele incrementará o contador com êxito em um para esse dia. Se um usuário tiver dois perfis atribuídos a ele, um no estado de êxito e o outro em um estado de erro, o usuário no estado de erro será contado. A entidade **PolicyUserActivity** lista quantos usuários estão em qual estado em um determinado dia nos últimos 30 dias.

|  Propriedade |                                          Descrição                                          |       Exemplo       |
|:---------:|:---------------------------------------------------------------------------------------------:|:-------------------:|
| DateKey   | A chave de data quando o check-in do perfil de Configuração do dispositivo foi registrado no data warehouse. | 20160703            |
| Pending (Pendente)   | Número de dispositivos exclusivos no estado pendente.                                                    | 123                 |
| Bem-sucedido | Número de dispositivos exclusivos no estado de êxito.                                                    | 12                  |
| PolicyKey | A chave de política, pode ser unida com a política para obter o policyName.                                | Linha de base do Windows 10 |
| Erro do     | Número de dispositivos exclusivos no estado de erro.                                                      | 10                  |

## <a name="termsandconditions"></a>termsAndConditions
Uma entidade **termsAndConditions** representa os metadados e conteúdos de determinada política de termos e condições (T&C). Os conteúdos das políticas de T&C são apresentados aos usuários após a primeira tentativa de registro no Intune e, posteriormente, após as edições em que um administrador solicite uma nova aceitação. Eles permitem que os administradores comuniquem as cláusulas que um usuário precisa aceitar para registrar dispositivos no Intune.

|    Propriedade        |    Descrição    |    Exemplo        |
|----------------------------------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------|
|    termsAndConditionsKey    |    Uma chave correspondente a uma entrada na coleção "userTermsAndConditionsAcceptances"    |    123    |
|    termsAndCondidionsId    |    A ID para esta entrada termsAndConditions    |    276edcb7-7440-4339-b6c5-8b6fc556fee6    |
|    termsAndConditionsVersion    |    A versão desta entrada de termos e condições    |    1    |
|    name    |    O nome desta entrada de termsAndConditions.        |    Termos de uso do Intune     |
|    descrição    |    A descrição desses termos e condições.     |         |
|    title    |    O título desses termos e condições.     |    Política corporativa de gerenciamento de dispositivos        |
|    summaryOfTerms    |    O resumo dos termos fornecidos ao usuário.     |    Eu concordo com os termos e condições.    |
|    termsAndConditionsBodyText    |    O corpo do texto desses termos e condições.       |    *Criptografia do dispositivo* Imposição de PIN de seis dígitos    |
|    isDeleted    |    Valor de Verdadeiro ou Falso para indicar se esse valor foi excluído.     |    Falso    |
|    startDateInclusiveUTC    |    A data de início desses termos e condições.     |    23/08/2018 4:01:34    |
|    endDateEclusiveUTC    |    A data de término desses termos e condições.     |    31/12/9999 12:00    |

## <a name="userdeviceassociations"></a>userDeviceAssociations
A entidade **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização.

|        Nome        |                                             Descrição                                            |     Exemplo     |
|:------------------:|:--------------------------------------------------------------------------------------------------:|:---------------:|
| UserKey            | Identificador exclusivo do usuário no data warehouse.   (Chave substituta).                            | 123             |
| DeviceKey          | Identificador exclusivo do dispositivo no data warehouse.                                             | 123             |
| CreatedDateTimeUTC | A data e a hora em que a associação de dispositivo de usuário foi criada. Usa o formato UTC.                     | 23/11/2016 0:00 |
| IsDeleted          | Indica que o usuário cancelou o registro desse dispositivo e que a associação não está mais em vigor. | Verdadeiro/Falso      |
| EndedDateTimeUTC   | Data e hora em UTC em que IsDeleted foi alterado para True.                                               | 23/06/2017 0:00  |

## <a name="users"></a>usuários
A entidade **usuário** lista todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa.

A coleção de entidades **usuário** contém dados do usuário. Esses registros incluem estados do usuário durante o período de coleta de dados, mesmo se o usuário tiver sido removido. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados do mês anterior. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

|          Propriedade          |                                                                                                           Descrição                                                                                                          |                Exemplo               |
|:--------------------------:|:------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------:|:------------------------------------:|
| UserKey                    | Identificador exclusivo do usuário no data warehouse – chave alternativa.                                                                                                                                                         | 123                                  |
| UserId                     | O identificador exclusivo do usuário – semelhante à UserKey, mas é uma chave natural.                                                                                                                                                    | b66bc706-ffff-7437-0340-032819502773 |
| UserEmail                  | Endereço de email do usuário.                                                                                                                                                                                                     | John@constoso.com                    |
| userPrincipalName                        | Nome UPN do usuário.                                                                                                                                                                                               | John@constoso.com                    |
| DisplayName                | Nome de exibição do usuário.                                                                                                                                                                                                      | John                                 |
| IntuneLicensed             | Especifica se este usuário é Intune licenciado ou não.                                                                                                                                                                              | Verdadeiro/Falso                           |
| IsDeleted                  | Indica se todas as licenças do usuário expiraram e se o usuário foi, portanto, removido do Intune. Para um único registro, esse sinalizador não é alterado. Em vez disso, um novo registro é criado para um novo estado do usuário. | Verdadeiro/Falso                           |
| RowLastModifiedDateTimeUTC | A data e a hora em UTC de quando o registro foi modificado pela última vez no data warehouse                                                                                                                                                 | 23/11/2016 0:00                      |

## <a name="usertermsandconditionsacceptances"></a>userTermsAndConditionsAcceptances
Uma entidade **userTermsAndConditionsAcceptance** representa o status de aceitação de determinada política de termos e condições (T&C) por um usuário. Os usuários precisam aceitar a versão mais atualizada dos termos para manter o acesso ao Portal da Empresa.

|    Propriedade    |    Descrição    |    Exemplo    |
|-------------------------------|--------------------------------------------------------------------------------|----------------------------|
|    dateKey    |    Uma chave correspondente a um valor de data na coleção "datas".     |    20180823    |
|    userKey    |    Um mapeamento de chave para um usuário na coleção "usuários".     |    20000    |
|    termsAndConditionsKey    |    Uma chave correspondente a uma entrada na coleção "termsAndConditions"    |    1    |
|    acceptedDateTimeUTC    |    O momento em que o usuário aceitou esses termos e condições    |    23/08/2018 4:01:34    |
|    lastModifiedDateTimeUTC    |    A última vez que essa entrada foi modificada.     |    23/08/2018 4:01:34    |

## <a name="vppprogramtypes"></a>vppProgramTypes 
A entidade **vppProgramType** lista os possíveis tipos de programa VPP para um aplicativo.

|      Propriedade      |          Descrição         |
|:------------------:|:----------------------------:|
| VppProgramTypeID   | ID do tipo.           |
| VppProgramTypeKey  | A chave alternativa para a chave. |
| VppProgramTypeName | O tipo de programa do VPP.          |

### <a name="example"></a>Exemplo

|             VppProgramID             |         Nome        | Descrição                |
|:------------------------------------:|:-------------------:|----------------------------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft           | O programa VPP da Microsoft. |
| 00000000-0000-0000-0000-000000000000 | Ainda não disponível | O valor padrão, não VPP.   |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple               | O programa VPP da Apple.     |

## <a name="next-steps"></a>Próximas etapas

Para saber mais sobre o Intune Data Warehouse, veja [Modelo de dados do Data Warehouse](https://docs.microsoft.com/intune/reports-ref-data-model).

