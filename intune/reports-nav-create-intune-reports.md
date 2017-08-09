---
title: Usar o Intune Data Warehouse | Microsoft Docs
description: "Use o Intune Data Warehouse para criar relatórios que fornecem informações sobre seu ambiente móvel da empresa."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: db6661dd92b890d711f655a60eb883b417a30d8a
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2017
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

> [!Important]  
> Você pode testar a funcionalidade mais recente do Data Warehouse usando a versão beta. Para usar a versão beta, a URL deve conter o parâmetro de consulta `api-version=beta`. A versão beta oferece recursos antes que eles estejam disponíveis como um serviço com suporte. Como o Intune adiciona novos recursos, a versão beta pode ter dados e o comportamento diferentes dos contratos. Qualquer código personalizado ou quaiquer ferramentas de relatório dependentes da versão beta de relatório podem ser corrompidas com atualizações contínuas. <!-- If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

**Próximas etapas**

- Obtenha um link e use o Power BI para obter informações. Para obter instruções, consulte [Conectar o Intune Data Warehouse com o Power BI](reports-proc-get-a-link-powerbi.md).
- Obtenha mais informações sobre a API do Intune Data Warehouse, o modelo de dados e relações entre entidades<!-- , and an example of creating a custom client to retrieve data,-->, consulte [API Intune Data Warehouse](reports-nav-intune-date-warehouse.md).