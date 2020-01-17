---
title: Usar o Intune Data Warehouse
titleSuffix: Microsoft Intune
description: Use o Intune Data Warehouse para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa.
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/04/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: developer
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 58c4db1f4c778050bc91bde79494742e018f5329
ms.sourcegitcommit: a82d25d98fdf0ba766f8f074871d4f13725e23f9
ms.translationtype: MTE75
ms.contentlocale: pt-BR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75547897"
---
# <a name="use-the-microsoft-intune-data-warehouse"></a>Usar o Microsoft Intune Data Warehouse

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Use o Intune Data Warehouse para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa. Por exemplo, alguns dos relatórios incluem:
- Tendência de registro de usuários no Intune para que você possa otimizar sua compra de licenças
- Análise de versões de aplicativo e sistema operacional para que você possa examinar o status dos dispositivos móveis
- Tendências de conformidade de registro e do dispositivo para que você possa implantar perfeitamente atualizações de política

## <a name="data-warehouse-benefits"></a>Benefícios do Data Warehouse

O Data Warehouse fornece acesso a mais informações sobre seu ambiente móvel do que o portal do Azure. Com o Intune Data Warehouse, você pode acessar:

- Dados históricos do Intune
- Dados atualizados em um ritmo diário
- Um modelo de dados usando o padrão OData

> [!Note]
> Se estiver usando o MDM (gerenciamento de dispositivo móvel) cogerenciado com o Microsoft Endpoint Configuration Manager e o Microsoft Intune, você precisará recuperar seus dados do Configuration Manager. O Data Warehouse do Intune contém apenas dados do Intune. Você pode usar um dashboard do Power BI para o Configuration Manager para relatórios personalizados. Para obter mais informações, consulte "[Anunciando o modelo de solução do Power BI para o Configuration Manager](https://powerbi.microsoft.com/blog/sccm-solution-template) e "[Conteúdo do Power BI para Dynamics 365](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/power-bi-home-page)."

> [!Important]  
> Agora é possível usar a versão v1.0 do Intune Data Warehouse, definindo o parâmetro de consulta  `api-version=v1.0`. As atualizações em coleções no Data Warehouse são suplementares por natureza e não interrompem cenários existentes.<br><br>
> Você pode testar a funcionalidade mais recente do Data Warehouse usando a versão beta. Para usar a versão beta, a URL deve conter o parâmetro de consulta  `api-version=beta`. A versão beta oferece recursos antes que eles estejam disponíveis como um serviço com suporte. Como o Intune adiciona novos recursos, a versão beta pode ter dados e o comportamento diferentes dos contratos. Qualquer código personalizado ou quaiquer ferramentas de relatório dependentes da versão beta de relatório podem ser corrompidas com atualizações contínuas.

## <a name="next-steps"></a>Próximas etapas

- Obtenha um link e use o Power BI para obter informações. Para obter instruções, consulte [Conectar o Intune Data Warehouse com o Power BI](reports-proc-get-a-link-powerbi.md).
- Com o link, crie um relatório personalizado com o Power BI. Para obter instruções, consulte [Create a report from the OData feed with Power BI](reports-proc-create-with-odata.md) (Criar um relatório do feed OData com o Power BI).
- Obtenha mais informações sobre a API do Intune Data Warehouse, o modelo de dados e relações entre entidades<!-- , and an example of creating a custom client to retrieve data,--> Veja [API do Intune Data Warehouse](reports-nav-intune-data-warehouse.md).
