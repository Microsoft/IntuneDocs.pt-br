---
title: Processamento e armazenamento de dados no Intune
description: Saiba como os dados pessoais são armazenados e processados no Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/18/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: edb07842-6a16-482e-8c1d-541a29e169a8
ms.reviewer: angerobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f7c24775f03011bd936b22e41cfd318e92b5d64
ms.sourcegitcommit: 07528df71460589522a2e1b3e5f9ed63eb773eea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "34474642"
---
# <a name="data-storage-and-processing-in-intune"></a>Processamento e armazenamento de dados no Intune

Depois que o Intune [coleta os dados](privacy-data-collect.md), o armazenamento e o processamento dos dados continuam, conforme detalhado abaixo.

## <a name="storing-personal-data"></a>Armazenando dados pessoais

Todos os dados não telemétricos coletados são processados por meio do serviço Intune e são armazenados em um ou mais dos seguintes locais de armazenamento: 

- SQLAzure 
- Coleções Confiáveis (Service Fabric)  
- Armazenamento do Azure 

A telemetria (logs de serviço, logs de desempenho, erros e assim por diante) que é essencial para o monitoramento e a prestação de um serviço estável é enviada para os armazenamentos de dados telemétricos da Microsoft.

### <a name="storage-locations"></a>Locais de armazenamento

A Microsoft oferece e opera os serviços do Intune em várias regiões do mundo todo. O Intune respeita as escolhas de local de armazenamento feitas pelo administrador de Dados do Cliente.

Para obter mais informações, confira [Microsoft Intune – em que local estão meus dados do cliente?](For more information, see Microsoft Intune Where is my customer data?)

### <a name="personal-data-retention"></a>Retenção de dados pessoais

Em geral, os dados pessoais são retidos pelo Intune até trinta dias depois que o usuário é removido do gerenciamento do Intune.

Os dados telemétricos coletados como parte do uso do Intune são retidos por um período máximo de trinta dias.

Os logs de auditoria são retidos por até um ano.

## <a name="processing-personal-data"></a>Processando dados pessoais

O Intune processa os dados pessoais com sistemas certificados pela ISO. Para obter mais informações, confira o [Portal de Confiança do Serviço](https://www.microsoft.com/en-us/TrustCenter/stp).

### <a name="profiling-and-marketing"></a>Criação de perfil e marketing

O Microsoft Intune não usa os dados pessoais coletados como parte da prestação do serviço para fins de criação de perfil ou marketing. 

### <a name="restrict-processing-of-personal-data"></a>Restringir o processamento de dados pessoais

Para restringir o processamento de dados pessoais do usuário, você pode excluir a conta dos usuários:
1. Exportando uma cópia eletrônica dos dados pessoais do usuário, incluindo
    - contas
    - dados de serviço
    - logs associados
2. Excluindo a conta do usuário e os dados associados do Intune.

## <a name="next-steps"></a>Próximas etapas

Saiba mais sobre como o Intune [protege e compartilha](privacy-data-secure-share.md) dados pessoais. 