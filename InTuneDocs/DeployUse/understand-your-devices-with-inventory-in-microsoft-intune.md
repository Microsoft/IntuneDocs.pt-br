---
title: "Compreender seus dispositivos com um inventário | Microsoft Intune"
description: "Use o Intune para exibir informações sobre o hardware dos dispositivos que você gerencia."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18ef1ca18244b202a35fc8fc23fc994105b7b47e
ms.openlocfilehash: ff55533499494488cd4cd692c6e36fe547ade3e4


---

# Compreenda seus dispositivos com um inventário no Microsoft Intune
O Microsoft Intune permite que você exiba o inventário de dispositivos e computadores Windows registrados que executam o software cliente do Intune.
O Intune normalmente coleta o inventário de dispositivos gerenciados a cada sete dias. Por isso, pode haver um atraso antes que os relatórios mostrem os resultados das alterações recentes nos dispositivos; por exemplo, uma alteração no nome do dispositivo ou o espaço de armazenamento livre.

## O que é coletado dos dispositivos registrados?
Para exibir o inventário coletado por dispositivos móveis, execute os [Relatórios de inventário de dispositivos móveis](understand-microsoft-intune-operations-by-using-reports.md). O Intune coleta o seguinte inventário dos dispositivos registrados:

|Propriedade|Coletado por|
|------------|-----------------------|
|**Nome**|Todos os dispositivos|
|**Sistema operacional**|Todos os dispositivos|
|**Fabricante**|Todos os dispositivos|
|**Modelo**|Todos os dispositivos|
|**Canal de Gerenciamento**|Todos os dispositivos|
|**Registrado no AAD**|Todos os dispositivos, exceto o Mac OS X|
|**Compatível**|Todos os dispositivos|
|**EAS ativado**|Todos os dispositivos, exceto o Mac OS X|
|**ID de ativação de EAS**|Todos os dispositivos, exceto o Mac OS X|
|**Tempo de ativação de EAS**|Todos os dispositivos, exceto o Mac OS X|
|**Estado de Gerenciamento**|Todos os dispositivos|
|**Endereço de email**|Todos os dispositivos|
|**ID do Exchange ActiveSync**|Todos os dispositivos|
|**Desbloqueado ou com raiz**|Somente os dispositivos iOS e Android|
|**Identificação de dispositivo exclusivo**|Todos os dispositivos, exceto o Exchange ActiveSync|
|**Número de série**|Dispositivos iOS, Mac OS X, Android, Windows 8.1 e Windows 10|
|**Espaço de armazenamento total**|Dispositivos iOS, Mac OS X, Windows 8.1 e Windows 10|
|**Espaço livre de armazenamento**|Dispositivos iOS, Mac OS X, Windows 8.1 e Windows 10|
|**Número do telefone**<br>Os telefones categorizados como Empresariais são identificados com o número de telefone completo (por exemplo, quando você executa um relatório de inventário de dispositivo móvel). Os números de telefone BYOD são mascarados com &#42;, e apenas os quatro últimos dígitos são exibidos.|Dispositivos iOS, Android e Windows Phone|
|**IMEI**|Dispositivos Exchange ActiveSync, iOS, Android e Windows Phone|
|**MEID**<br>Identificador de Equipamentos Móveis|Somente os dispositivos iOS|
|**MAC Wi-Fi**|Todos os dispositivos, exceto o Exchange ActiveSync|
|**Operadora do assinante**|Somente os dispositivos iOS e Android|
|**Tecnologia celular**|Somente os dispositivos iOS e Android|
|**Supervisionado**|Somente os dispositivos iOS|
|**Estado de Bloqueio de Ativação**|Somente os dispositivos iOS|
|**Data registrada**|Todos os dispositivos|
|**Última Atualização**|Todos os dispositivos|
|**Ethernet MAC**|Somente os dispositivos Mac OS X|
|**Bloqueio de ativação habilitado**|Somente os dispositivos iOS|
|**Criptografia habilitada**|Todos os dispositivos|

## O que é coletado de computadores Windows?
> [!IMPORTANT]
> Esta seção se aplica somente aos computadores Windows que executam o software cliente do computador Windows com o Intune.

Para exibir o inventário coletado por computadores Windows, execute os [Relatórios de inventário de computador](understand-microsoft-intune-operations-by-using-reports.md). O Intune coleta o seguinte inventário dos computadores Windows:

-   **Nome**

-   **Tipo de Chassi**

-   **Fabricante**

-   **Modelo**

-   **Sistema operacional**

-   **Versão do TPM**

-   **Espaço Total em Disco**

-   **Espaço em Disco Utilizado**

-   **Espaço Livre em Disco**

-   **Nome de Disco do SO**

-   **Espaço em Disco do SO**

-   **Espaço Livre em Disco do SO**

-   **Memória física**

-   **Nome do Processador**

-   **Arquitetura do processador**

-   **Velocidade da CPU**

-   **Endereço IP**

-   **Número de série**

-   **Último Usuário a Fazer Logon**

-   **Usuário Atribuído**

-   **Última Atualização**

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->



<!--HONumber=Aug16_HO5-->


