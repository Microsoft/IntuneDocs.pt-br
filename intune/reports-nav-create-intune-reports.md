---
title: Usar o Intune Data Warehouse | Microsoft Docs
description: "Use o Intune Data Warehouse para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa."
keywords: Intune Data Warehouse
author: Erikre
ms.author: erikre
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 338536d975ca3810df3c909964ac13b396097db8
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2018
---
# <a name="use-the-intune-data-warehouse"></a>Usar o Intune Data Warehouse

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Use o Intune Data Warehouse para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa. Por exemplo, alguns dos relatórios incluem:
-   Tendência de registro de usuários no Intune para que você possa otimizar sua compra de licenças
-   Análise de versões de aplicativo e sistema operacional para que você possa examinar o status dos dispositivos móveis
-   Tendências de conformidade de registro e do dispositivo para que você possa implantar perfeitamente atualizações de política

O Data Warehouse fornece acesso a mais informações sobre seu ambiente móvel do que o portal do Azure. Com o Intune Data Warehouse, você pode acessar:

  -  Dados históricos do Intune
  -  Dados atualizados em um ritmo diário
  -  Um modelo de dados usando o padrão OData

> [!Note]
> Se você estiver usando o gerenciamento de dispositivo móvel (MDM) híbrido com o System Center Configuration Manager e o Microsoft Intune, desejará recuperar seus dados do SCCM. O Data Warehouse do Intune contém apenas dados do Intune. Você pode usar um dashboard do SCCM Power BI para relatórios personalizados. Para obter mais informações, consulte "[Anunciando o modelo de solução do Power BI para o System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template)." e "[Criar um dashboard e relatório do Power BI](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard)."


> [!Important]  
> Você pode testar a funcionalidade mais recente do Data Warehouse usando a versão beta. Para usar a versão beta, a URL deve conter o parâmetro de consulta `api-version=beta`. A versão beta oferece recursos antes que eles estejam disponíveis como um serviço com suporte. Como o Intune adiciona novos recursos, a versão beta pode ter dados e o comportamento diferentes dos contratos. Qualquer código personalizado ou quaiquer ferramentas de relatório dependentes da versão beta de relatório podem ser corrompidas com atualizações contínuas.

**Próximas etapas**

- Obtenha um link e use o Power BI para obter informações. Para obter instruções, consulte [Conectar o Intune Data Warehouse com o Power BI](reports-proc-get-a-link-powerbi.md).
- Com o link, crie um relatório personalizado com o Power BI. Para obter instruções, consulte [Create a report from the OData feed with Power BI](reports-proc-create-with-odata.md) (Criar um relatório do feed OData com o Power BI).
- Obtenha mais informações sobre a API do Intune Data Warehouse, o modelo de dados e relações entre entidades<!-- , and an example of creating a custom client to retrieve data,-->, consulte [API Intune Data Warehouse](reports-nav-intune-data-warehouse.md).