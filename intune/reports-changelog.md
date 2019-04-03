---
title: Log de alterações do Intune Data Warehouse
titlesuffix: Microsoft Intune
description: Este tópico fornece uma lista de alterações para a API do Microsoft Intune Data Warehouse.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/21/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: d7d69c602471e8508744f2a00008294cbd335204
ms.sourcegitcommit: 93286c22426dcb59191a99e3cf2af4ff6ff16522
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58358251"
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Log de alterações para a API do Intune Data Warehouse

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Manter-se atualizado sobre as atualizações para o Intune Data Warehouse.

## <a name="1903"></a>1903
_Lançado em março de 2019_

### <a name="v10-changes-reflecting-back-to-beta"></a>Alterações de v 1.0 refletir o beta
Quando a versão 1.0 foi introduzido pela primeira vez no 1808, eram diferentes de algumas maneiras significativas da versão beta API. 1903 essas alterações serão refletidas volta para a versão beta da API. Se você tiver relatórios importantes que usam a versão beta da API, é altamente recomendável alternar esses relatórios para v 1.0 para evitar alterações significativas. Consulte a [informações de versão de API](reports-api-url.md) para obter mais informações sobre as versões de API do Data Warehouse e para trás compatibilidade. 

## <a name="1902"></a>1902 
_Lançado em fevereiro de 2019_

### <a name="power-bi-compliance-app"></a>Aplicativo de conformidade do Power BI 

Acessar seu Data Warehouse do Intune no Power BI Online usando o [conformidade do Intune (Data Warehouse)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) aplicativo. Com este aplicativo do Power BI, agora você pode acessar e compartilhar relatórios previamente criados sem nenhuma configuração e sem sair do seu navegador da web. 

> [!NOTE]
> Há dois filtros adicionais, que você pode aplicar para o aplicativo de conformidade do Intune.

#### <a name="add-additional-filters-to-the-intune-compliance-app"></a>Adicionar filtros adicionais para o aplicativo de conformidade do Intune
1. Abra o [conformidade do Intune (Data Warehouse)](https://app.powerbi.com/groups/me/getapps/services/Intune_dw_compliance) aplicativo em seus navegadores da web.
2. Clique em **dispositivos não compatível** e selecione **incompatível** no **complianceStatus** filtro. 
3. Clique em **dispositivos desconhecidos** e selecione **ainda não está disponível** no **complianceStatus** filtro. 

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
 - A entidade [**MobileAppInstallState**](reports-ref-application.md#mobileappinstallstate), foi adicionada. A entidade **MobileAppInstallState** representa o estado de instalação de um aplicativo móvel após sua atribuição a um grupo que contém dispositivos, usuários ou ambos. 

## <a name="1710"></a>1710
_Lançado em novembro de 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Uma nova coleção de entidade chamada Usuário Atual é limitada a usuários ativos no momento <!-- 1544273 -->

A coleção de entidades **Usuários** contém todos os usuários do Azure Active Directory (Azure AD) com licenças atribuídas em sua empresa. Esses registros incluem estados do usuário durante o período de coleta de dados, mesmo se o usuário tiver sido removido. Por exemplo, um usuário pode ter sido adicionado ao Intune e, em seguida, removido durante o último mês. Embora esse usuário não esteja presente no momento do relatório, o usuário e o estado estão presentes nos dados. Você pode criar um relatório que mostra a duração da presença histórica do usuário em seus dados.

Em contraste, a nova coleção de entidade **Usuário Atual** contém apenas os usuários que não foram removidos. A coleção de entidade **Usuário Atual** contém apenas usuários ativos no momento. Para saber mais sobre a coleção de entidade **usuário atual**, veja [Referência para a entidade de usuário atual](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Lançado em outubro de 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Coleção de entidades de associação de dispositivo do usuário adicionada ao modelo de dados do Intune Data Warehouse <!-- 1187917 -->

Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo. O modelo de dados pode ser acessado por meio do arquivo do Power BI (PBIX) recuperado da página do Intune Data Warehouse, por meio do ponto de extremidade OData ou desenvolvendo um cliente personalizado. Para saber mais, veja a [Associação de dispositivo de usuário](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Novas entidades no modelo de dados do Data Warehouse <!-- 1479526 --><!-- -->

 - A entidade, [**UserDeviceAssociation**](reports-ref-user-device.md), adicionada. **UserDeviceAssociation** contém associações de dispositivo de usuário em sua organização. Agora você pode criar relatórios e visualizações de dados usando as informações de associação de dispositivo de usuário que associam as coleções de entidades do usuário e do dispositivo.  
 - A entidade, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), adicionada. **IntuneManagementExtension** contém entidade para dispositivos móveis que acompanham informações como versão e status de instalação.

## <a name="next-steps"></a>Próximas etapas
 - Conheça as [novidades de cada semana no Intune](whats-new.md). Saiba mais também sobre as próximas alterações, avisos importantes sobre o serviço e informações sobre versões anteriores.
 - Leia o [Blog do Microsoft Intune](https://go.microsoft.com/fwlink/?LinkID=273882).
