---
title: "Compreenda seus dispositivos com um inventário"
description: "Use o Intune para exibir informações sobre o hardware dos dispositivos que você gerencia."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c6d3e7638ecbd58a9d9d50cadde85188b873c05f
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2017
---
# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a>Compreenda seus dispositivos com um inventário no Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

O Microsoft Intune permite que você exiba o inventário de dispositivos e computadores Windows registrados que executam o software cliente do Intune.
O Intune normalmente coleta o inventário de dispositivos gerenciados a cada sete dias. Por isso, pode haver um atraso antes que os relatórios mostrem os resultados das alterações recentes nos dispositivos; por exemplo, uma alteração no nome do dispositivo ou o espaço de armazenamento livre.

## <a name="whats-collected-from-enrolled-devices"></a>O que é coletado dos dispositivos registrados?
Para exibir o inventário coletado por dispositivos móveis, execute os [Relatórios de inventário de dispositivos móveis](understand-microsoft-intune-operations-by-using-reports.md). O Intune coleta o seguinte inventário dos dispositivos registrados:

|Propriedade|Coletado por|
|------------|-----------------------|
|**Nome**|Todos os dispositivos|
|**Sistema operacional**|Todos os dispositivos|
|**Fabricante**|Todos os dispositivos|
|**Modelo**|Todos os dispositivos|
|**Canal de gerenciamento**|Todos os dispositivos|
|**Registrado no AAD**|Todos os dispositivos, exceto o Mac OS X|
|**Compatível**|Todos os dispositivos|
|**EAS ativado**|Todos os dispositivos, exceto o Mac OS X|
|**ID de ativação de EAS**|Todos os dispositivos, exceto o Mac OS X|
|**Tempo de ativação de EAS**|Todos os dispositivos, exceto o Mac OS X|
|**Estado de gerenciamento**|Todos os dispositivos|
|**Endereço de email**|Todos os dispositivos|
|**ID do Exchange ActiveSync**|Todos os dispositivos|
|**Com jailbreak ou com raiz**|Somente os dispositivos iOS e Android|
|**ID exclusiva do dispositivo**|Todos os dispositivos, exceto o Exchange ActiveSync|
|**Número de série**|Dispositivos iOS, Mac OS X, Android, Windows 8.1 e Windows 10 Desktop|
|**Espaço de armazenamento total**|Dispositivos iOS, Mac OS X, Windows 8.1 e Windows 10 Desktop e Mobile|
|**Espaço de armazenamento livre**|Dispositivos iOS, Mac OS X, Windows 8.1 e Windows 10 Desktop|
|**Número de telefone**<br>Os telefones categorizados como Empresariais são identificados com o número de telefone completo (por exemplo, quando você executa um relatório de inventário de dispositivo móvel). Os números de telefone BYOD são mascarados com &#42;, e apenas os quatro últimos dígitos são exibidos.|Dispositivos iOS, Android e Windows Phone|
|**IMEI**|Dispositivos Exchange ActiveSync, iOS, Android e Windows Phone|
|**MEID**<br>Identificador de Equipamentos Móveis|Somente os dispositivos iOS|
|**Wi-Fi MAC**|Todos os dispositivos, exceto o Exchange ActiveSync|
|**Carrier do assinante**|Somente os dispositivos iOS e Android|
|**Tecnologia celular**|Somente os dispositivos iOS e Android|
|**Supervisionado**|Somente os dispositivos iOS|
|**Estado de Bloqueio de Ativação**|Somente os dispositivos iOS|
|**Data registrada**|Todos os dispositivos|
|**Última atualização**|Todos os dispositivos|
|**Ethernet MAC**|Somente os dispositivos Mac OS X|
|**Bloqueio de Ativação habilitado**|Somente os dispositivos iOS|
|**Criptografia habilitada**|Todos os dispositivos|

>[!NOTE]
>Alguns dos itens acima não podem ser coletados dependendo da operadora usada com o dispositivo.

## <a name="whats-collected-from-windows-pcs"></a>O que é coletado de computadores Windows?
> [!IMPORTANT]
> Esta seção se aplica somente aos computadores Windows que executam o software cliente do computador Windows com o Intune.

Para exibir o inventário coletado por computadores Windows, execute os [Relatórios de inventário de computador](understand-microsoft-intune-operations-by-using-reports.md). O Intune coleta o seguinte inventário dos computadores Windows:

-   **Nome**

-   **Tipo de chassi**

-   **Fabricante**

-   **Modelo**

-   **Sistema operacional**

-   **Versão do TPM**

-   **Espaço total em disco**

-   **Espaço em disco utilizado**

-   **Espaço livre em disco**

-   **Nome de disco do SO**

-   **Espaço em disco do SO**

-   **Espaço livre em disco do SO**

-   **Memória física**

-   **Nome do processador**

-   **Arquitetura do processador**

-   **Velocidade da CPU**

-   **Endereço IP**

-   **Número de série**

-   **Último usuário a fazer logon**

-   **Usuário atribuído**

-   **Última atualização**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
