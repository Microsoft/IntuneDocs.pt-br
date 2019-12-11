---
title: Dados enviados pela Google ao Intune
titleSuffix: Microsoft Intune
description: Lista de dados que a Google envia para o Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/18/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: c379c8db-788a-454e-9098-665ea3bc7b56
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 914ce3aa15099b7692d524dbfa368f99f0d092e8
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "72504499"
---
# <a name="data-google-sends-to-intune"></a>Dados enviados pela Google ao Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Quando o gerenciamento de dispositivo Android enterprise está habilitado em um dispositivo, o Microsoft Intune estabelece uma conexão com o Google e as informações de dispositivo e do usuário são compartilhadas entre o Intune e o Google. Antes que o Microsoft Intune estabeleça uma conexão, você deve criar uma conta do Google.

A tabela a seguir lista os dados que a Google envia ao Intune quando o gerenciamento de dispositivo está habilitado em um dispositivo:


| Dados enviados pela Google ao Intune | Detalhes | Usada para | Exemplo |
|:---:|:---:|:---:|:---:|
| Dados empresariais | Identificadores empresariais do cliente no Google. | Vincula as informações do cliente entre o Intune e o Google. | Exemplo de **enterpriseId**: LC04eik8a6.<br>**Nome**. O nome do administrador conforme inserido ao configurar o Android enterprise. Exemplo: Davi Barros.<br>**Email do administrador**. YourAdmin@gmail.com usado durante a configuração do Android enterprise. |
| Dados de aplicativos | Dados para aplicativos gerenciados do Play Store. | Direcionando o aplicativo para usuários ou dispositivos como disponível ou necessário. | Exemplo de **Nome do Aplicativo**: Aplicativo de Inventário do Armazém da Contoso.<br>Exemplo de **Identificador Exclusivo para representar o aplicativo**: app:com.Contoso.Warehouse.InventoryTracking |
| Conta de serviço | Conta interna exclusiva de serviço do Google para uso com chamadas de cliente específicas. | Usado para fazer chamadas no Google em nome do cliente (para exibir os aplicativos, os dispositivos e muito mais) | Exemplo de **Nome**: InternalAccount@InternalService.com.<br>Exemplo de **Chaves**: SenhaContaServiço |


Para parar de usar o gerenciamento de dispositivos Android enterprise com o Microsoft Intune e excluir os dados, você deve desabilitar o gerenciamento de dispositivos Android enterprise do Microsoft Intune e também excluir a sua conta do Google. Consulte a conta do Google para saber como executar o gerenciamento de contas.


