---
title: Log de alterações do Intune Data Warehouse
titleSuffix: Microsoft Intune
description: Este tópico fornece uma lista de alterações para a API do Microsoft Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/23/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: f9740eed3ab727d76a9af4e46642d8279b310fd9
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72490532"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Log de alterações para a API do Intune Data Warehouse

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Manter-se atualizado sobre as atualizações para o Intune Data Warehouse.

## <a name="1903-part-2"></a>1903 (Parte 2)
_Lançado em abril de 2019_

### <a name="beta-changes"></a>Alterações beta

A tabela a seguir lista as coleções removidas recentes e as coleções de substituições no Intune Data Warehouse.

|    Coleta                          |    Alteração     |    Informações adicionais                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------|---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    mobileAppDeviceUserInstallStatus    |    Removido    |    Use [mobileAppInstallStatusCounts](intune-data-warehouse-collections.md#mobileappinstallstatuscounts) em vez disso.                                                                                                                                                                                                                                                                     |
|    enrollmentTypes                     |    Removido    |    Use [deviceEnrollmentTypes](intune-data-warehouse-collections.md#deviceenrollmenttypes) em vez disso.                                                                                                                                                                                                                                                                                      |
|    mdmStatuses                         |    Removido    |    Use [complianceStates](intune-data-warehouse-collections.md#compliancestates) em vez disso.                                                                                                                                                                                                                                                                                               |
|    workPlaceJoinStateTypes             |    Removido    |    Use a propriedade `azureAdRegistered` nas coleções [devices](intune-data-warehouse-collections.md#devices) e [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) em vez disso.                                                                                                                                                                                                             |
|    clientRegistrationStateTypes        |    Removido    |    Use [deviceRegistrationStates](intune-data-warehouse-collections.md#deviceregistrationstates) em vez disso.                                                                                                                                                                                                                                                                             |
|    currentUser                         |    Removido    |    Use a coleção [users](intune-data-warehouse-collections.md#users) em vez disso.                                                                                                                                                                                                                                                                                                      |
|    mdmDeviceInventoryHistories         |    Removido    |    Muitas das propriedades eram redundantes ou agora podem ser encontradas nas coleções [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories) ou [devices](intune-data-warehouse-collections.md#devices). Qualquer propriedade **mdmDeviceInventoryHistories** que ainda não esteja listadas com essas duas coleções não estão mais disponíveis. Veja os detalhes abaixo.    |

A tabela a seguir lista as propriedades anteriormente antigas encontradas na coleção **mdmDeviceInventoryHistories** e a alteração/substituição. Todas as propriedades que estavam em **mdmDeviceInventoryHistories**, mas não listadas abaixo, foram removidas.

|    Propriedade antiga                |    Alteração/substituição                                                           |
|--------------------------------|---------------------------------------------------------------------------------|
|    cellularTechnology          |    cellularTechnology na coleção devices                                     |
|    deviceClientId              |    deviceId na coleção devices                                               |
|    deviceManufacturer          |    fabricante na coleção devices                                           |
|    deviceModel                 |    modelo na coleção devices                                                  |
|    deviceName                  |    deviceName na coleção devices                                             |
|    deviceOsPlatform            |    deviceTypeKey na coleção devices                                          |
|    deviceOsVersion             |    osVersion na coleção devicePropertyHistories                              |
|    deviceType                  |    deviceTypeKey na coleção devices, fazendo referência à coleção deviceTypes    |
|    encryptionState             |    propriedade encryptionState na coleção devices                           |
|    exchangeActiveSyncId        |    propriedade easDeviceId na coleção devices                               |
|    exchangeDeviceId            |    easDeviceId na coleção devices                                            |
|    imei                        |    imei na coleção devices                                                   |
|    isSupervised                |    propriedade isSupervised na coleção devices                              |
|    jailBroken                  |    jailBroken na coleção devicePropertyHistories                             |
|    meid                        |    propriedade meid na coleção devices                                      |
|    oem                         |    fabricante na coleção devices                                           |
|    osName                      |    deviceTypeKey na coleção devices, fazendo referência à coleção deviceTypes    |
|    phoneNumber                 |    phoneNumber na coleção devices                                            |
|    platformType                |    modelo na coleção devices                                                  |
|    product                     |    deviceTypeKey na coleção devices                                          |
|    productVersion              |    osVersion na coleção devicePropertyHistories                              |
|    serialNumber                |    serialNumber na coleção devices                                           |
|    storageFree                 |    propriedade freeStorageSpaceInBytes na coleção devices                   |
|    storageTotal                |    propriedade totalStorageSpaceInBytes na coleção devices                |
|    subscriberCarrierNetwork    |    propriedade subscriberCarrier na coleção devices                         |
|    wifimac                     |    wiFiMacAddress na coleção devices                                         |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [devicePropertyHistories](intune-data-warehouse-collections.md#devicepropertyhistories): 

|    Propriedade antiga                  |    Alteração/substituição                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, fazendo referência à coleção deviceCategories       |
|    certExpirationDate            |    Removido                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime na coleção devices                           |
|    deviceTypeKey                 |    deviceTypeKey na coleção devices                              |
|    easID                         |    easDeviceId na coleção devices                                |
|    enrolledByUser                |    userId na coleção devices                                     |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey na coleção devices                    |
|    graphDeviceIsCompliant        |    Removido                                                          |
|    graphDeviceIsManaged          |    Removido                                                          |
|    lastContact                   |    lastSyncDateTime na coleção devices                           |
|    lastContactNotification       |    Removido                                                          |
|    lastContactWorkplaceJoin      |    Removido                                                          |
|    lastExchangeStatusUtc         |    Removido                                                          |
|    lastModifiedDateTimeUTC       |    Removido                                                          |
|    lastPolicyUpdateUtc           |    Removido                                                          |
|    managementAgentKey            |    managementStateKey                                               |
|    fabricante                  |    fabricante na coleção devices                               |
|    mdmStatusKey                  |    complianceStateKey, fazendo referência à coleção complianceStates    |
|    modelo                         |    modelo na coleção devices                                      |
|    osFamily                      |    operatingSystem na coleção devices                            |
|    osRevisionNumber              |    osVersion na coleção devices                                  |
|    processorArchitecture         |    Removido                                                          |
|    referenceId                   |    azureAdDeviceId na coleção devices                            |
|    serialNumber                  |    serialNumber na coleção devices                               |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [devices](intune-data-warehouse-collections.md#devices): 

|    Propriedade antiga                  |    Alteração/substituição                                               |
|----------------------------------|---------------------------------------------------------------------|
|    categoryId                    |    deviceCategoryKey, fazendo referência à coleção deviceCategories       |
|    certExpirationDate            |    Removido                                                          |
|    clientRegistrationStateKey    |    deviceRegistrationStateKey                                       |
|    createdDate                   |    enrolledDateTime                                                 |
|    easId                         |    easDeviceId                                                      |
|    enrolledByUser                |    userId                                                           |
|    enrollmentTypeKey             |    deviceEnrollmentTypeKey                                          |
|    graphDeviceIsCompliant        |    Removido                                                          |
|    graphDeviceIsManaged          |    Removido                                                          |
|    lastContact                   |    lastSyncDateTime                                                 |
|    lastContactNotification       |    Removido                                                          |
|    lastContactWorkplaceJoin      |    Removido                                                          |
|    lastExchangeStatusUtc         |    Removido                                                          |
|    lastPolicyUpdateUtc           |    Removido                                                          |
|    mdmStatusKey                  |    complianceStateKey, fazendo referência à coleção complianceStates    |
|    osFamily                      |    operatingSystem                                                  |
|    processorArchitecture         |    Removido                                                          |
|    referenceId                   |    azureAdDeviceId                                                  |
|    workplaceJoinStateKey         |    azureAdRegistered                                                |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities): 

|    Propriedade antiga         |    Alteração/substituição         |
|-------------------------|-------------------------------|
|    enrollmentTypeKey    |    deviceEnrollmentTypeKey    |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [mamApplications](intune-data-warehouse-collections.md#mamapplications): 

|    Propriedade antiga       |    Alteração/substituição    |
|-----------------------|--------------------------|
|    applicationKey     |    mamApplicationKey     |
|    applicationName    |    mamApplicationName    |
|    applicationId      |    mamApplicationId      |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [mamApplicationInstances](intune-data-warehouse-collections.md#mamapplicationinstances): 

|    Propriedade antiga     |    Alteração/substituição    |
|---------------------|--------------------------|
|    applicationId    |    mamApplicationId      |
|    deviceId         |    mamDeviceId           |
|    deviceType       |    mamDeviceType         |
|    deviceName       |    mamDeviceName         |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [mamCheckins](intune-data-warehouse-collections.md#mamcheckins): 

|    Propriedade antiga      |    Alteração/substituição    |
|----------------------|--------------------------|
|    applicationKey    |    mamApplicationKey     |

A tabela a seguir lista as alterações a propriedades encontradas na coleção [users](intune-data-warehouse-collections.md#users): 

|    Propriedade antiga             |    Alteração/substituição    |
|-----------------------------|--------------------------|
|    startDateInclusiveUtc    |    Removido               |
|    endDateInclusiveUtc      |    Removido               |
|    isCurrent                |    Removido               |

## <a name="1903"></a>1903
_Lançado em março de 2019_

### <a name="v10-changes-reflecting-back-to-beta"></a>Alterações à V1.0 refletindo-se em beta
Quando a V1.0 foi introduzida pela primeira vez em 1808, ela tinha algumas diferenças da API beta. Em 1903, essas alterações serão refletidas novamente para a versão beta da API. Se você tem relatórios importantes que usam a versão beta da API, recomendamos expressamente alternar esses relatórios para a V1.0 a fim de evitar alterações da falha. Consulte as [informações sobre versão da API](../reports-api-url.md) para obter mais informações sobre as versões da API do Data Warehouse e compatibilidade com versões anteriores. 

## <a name="1902"></a>1902 
_Lançado em fevereiro de 2019_

### <a name="power-bi-compliance-app"></a>Aplicativo de Conformidade do Power BI 

Acesse o Intune Data Warehouse no Power BI Online usando o aplicativo [Conformidade do Intune (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp). Com esse aplicativo do Power BI, agora você pode acessar e compartilhar relatórios pré-criados sem nenhuma configuração e sem sair do navegador da Web. 

> [!NOTE]
> Há dois filtros adicionais que você pode aplicar ao aplicativo Conformidade do Intune.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Adicionar mais filtros ao aplicativo Conformidade do Intune
1. Abra o aplicativo [Conformidade do Intune (Data Warehouse)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) em seus navegadores da Web.
2. Clique em **Dispositivos Não em Conformidade** e selecione **Não em Conformidade** no filtro **complianceStatus**. 
3. Clique em **Dispositivos Desconhecidos** e selecione **Ainda Não Está Disponível** no filtro **complianceStatus**. 

## <a name="1812"></a>1812 
_Lançado em dezembro de 2018_

### <a name="enrollment-activities-collection-released-to-v10"></a>Coleção de Atividades de Registro lançada como v1.0 

A coleção de Atividades de Registro agora está disponível na v1.0. Use essa coleção para entender o volume de falhas de registro e as tendências em seu ambiente. Para obter mais informações, confira [enrollmentActivities](intune-data-warehouse-collections.md#enrollmentactivities), [enrollmentEventStatuses](intune-data-warehouse-collections.md#enrollmenteventstatuses), [enrollmentFailureCategories](intune-data-warehouse-collections.md#enrollmentfailurecategories) e [enrollmentFailureReasons](intune-data-warehouse-collections.md#enrollmentfailurereasons).

## <a name="1808"></a>1808
_Lançado em agosto de 2018_

### <a name="v10-collections"></a>Coleções da v1.0  

Agora é possível usar a versão v1.0 do Intune Data Warehouse, definindo o parâmetro de consulta `api-version=v1.0`. As atualizações em coleções no Data Warehouse são suplementares por natureza e não interrompem cenários existentes.

### <a name="enrollment-activities-collection-released-to-beta"></a>Coleção de Atividades de Registro lançada como beta

A nova coleção `Enrollment Activities` foi lançada como beta. Você pode usar essa coleção para entender a situação do seu registro, exibindo as falhas mais comuns. 


## <a name="1805"></a>1805
_Lançamento: maio de 2018_

### <a name="correction-to-device-count-in-devices-collection"></a>Correção da contagem de dispositivos na coleção **Dispositivos** 

Fizemos uma correção na coleção de **Dispositivos** que pode diminuir a contagem total de dispositivos filtrados pelo atributo `isDeleted`. Essa lista é resultado da correção, e não um erro. Para saber mais sobre a coleção de **Dispositivos**, confira [Referência para entidades de dispositivo](reports-ref-devices.md). 


## <a name="1801"></a>1801
_Lançado em janeiro de 2018_

### <a name="intune-data-warehouse-application-only-authentication----1867540---"></a>Autenticação somente no aplicativo Intune Data Warehouse <!-- 1867540 -->

Você pode configurar um aplicativo usando o Azure Active Directory (Azure AD) e autenticar para o Intune Data Warehouse. Para obter mais informações, consulte [Autenticação somente no aplicativo Intune Data Warehouse](data-warehouse-app-only-auth.md).

### <a name="azure-ad-and-intune-credential-requirements----2077525---"></a>Requisitos de credencial do Intune e Azure AD <!-- 2077525 -->

- Já não é mais necessário atribuir uma licença do Intune ao acessar o Intune Data Warehouse (incluindo a API).
- O nome da função do Intune foi alterado de **Relatórios** para **Intune data warehouse**. 

    Para mais informações, consulte [Requisitos de credencial do Intune e do Azure AD](reports-api-url.md#azure-ad-and-intune-credential-requirements).

### <a name="odata-query-options----2077711---"></a>Opções de consulta de OData <!-- 2077711 -->

Você pode usar <code>$select</code> como um parâmetro de consulta do OData. A versão atual é compatível com os seguintes parâmetros de consulta OData: <code>$filter</code>, <code>$orderby</code>, <code>$select</code>, <code>$skip</code> e <code>$top</code>. Para obter mais informações, consulte [Opções de consulta OData](reports-api-url.md#odata-query-options).

### <a name="new-entities-in-the-in-data-warehouse-data-model----2077804---"></a>Novas entidades no modelo de dados do Data Warehouse <!-- 2077804 -->

- A entidade [**MobileAppDeviceuserInstallStatus**](reports-ref-application.md), foi adicionada. O **MobileAppDeviceUserInstallStatus** representa um status de instalação de aplicativo móvel para um determinado dispositivo e usuário.
- A entidade [**MobileAppInstallStates**](reports-ref-application.md#mobileappinstallstates) foi adicionada. A entidade **MobileAppInstallState** representa o estado de instalação de um aplicativo móvel após sua atribuição a um grupo que contém dispositivos, usuários ou ambos. 

## <a name="1710"></a>1710
_Lançado em novembro de 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Uma nova coleção de entidade chamada Usuário Atual é limitada a usuários ativos no momento <!-- 1544273 -->

A coleção de entidades **Usuários** contém todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa. Esses registros incluem estados do usuário durante o período de coleta de dados, mesmo se o usuário tiver sido removido. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

Em contraste, a nova coleção de entidade **Usuário Atual** contém apenas os usuários que não foram removidos. A coleção de entidade **Usuário Atual** contém apenas usuários ativos no momento. Para saber mais sobre a coleção de entidade **usuário atual**, veja [Referência para a entidade de usuário atual](../reports-ref-current-user.md).

## <a name="1709"></a>1709
_Lançado em outubro de 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->

Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado. Para saber mais, veja a [Associação de dispositivo de usuário](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Novas entidades no modelo de dados do Data Warehouse <!-- 1479526 --><!-- -->

- A entidade, [**UserDeviceAssociation**](reports-ref-user-device.md), adicionada. **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização. Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo.  
- A entidade, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), adicionada. **IntuneManagementExtension** contém entidade para dispositivos móveis que acompanham informações como versão e status de instalação.

## <a name="next-steps"></a>Próximas etapas
- Conheça as [novidades de cada semana no Intune](../fundamentals/whats-new.md). Saiba mais também sobre as próximas alterações, avisos importantes sobre o serviço e informações sobre versões anteriores.
- Leia o [Blog do Microsoft Intune](https://go.microsoft.com/fwlink/?LinkID=273882).
