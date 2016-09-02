---
title: Recursos de gerenciamento do computador Windows | Microsoft Intune
description: Saiba mais sobre os recursos do Intune ao gerenciar computadores Windows com o software cliente do Intune.
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 08/04/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a6caef9e0f4d6235ecf1a89c1765d6c8e6ce1a7b
ms.openlocfilehash: e5e3833a38434d4fe55cae554fc49f567b606ad8


---

# Recursos de gerenciamento de computador Windows (com o cliente de computador do Microsoft Intune)
Na maioria dos cenários, você registrará os dispositivos no Microsoft Intune, que fornece um conjunto maior de recursos que o cliente de computador do Intune. No entanto, você também pode gerenciar computadores usando o cliente de computador do Intune, que fornece os seguintes recursos:

-   **Gerenciamento de atualizações de software** – Você pode manter os computadores atualizados e gerenciar quando as atualizações são aplicadas.

-   **Política do Firewall do Windows** – Ajuda a garantir que nenhum computador usado pela sua empresa tenha um Firewall do Windows inativo ou configurado incorretamente.

-   **Proteção antimalware** – O Intune conta com o Endpoint Protection, que ajuda a proteger seus computadores contra malware.

-   **Assistência remota** – O Intune permite que os usuários entrem em contato com a equipe de suporte de TI, que poderá fornecer assistência usando um recurso de área de trabalho remota que está incluso no Intune (requer o software TeamViewer).

-   **Gerenciamento de licenças de software** – Controle quantas licenças de software estão disponíveis e quantas licenças disponíveis estão sendo usadas.
-   **Implantação de aplicativo** – Implante software nos computadores que você gerencia. Alguns recursos de gerenciamento de aplicativo não estão disponíveis quando você gerencia computadores com o software cliente.


O Intune dá suporte à instalação do software cliente de computador em até 7.000 dispositivos Windows.

## Requisitos de sistema operacional
O Intune pode gerenciar computadores que executam as seguintes versões do Windows (32 e 64 bits):


-   **Windows Vista** - versões Business, Enterprise e Ultimate

-   **Windows 7** - Versões Pro, Enterprise e Ultimate (sem service pack ou com SP1)

-   **Windows 8** - Versões Pro e Enterprise

-   **Windows 8.1** - Versões Pro e Enterprise

- **Windows 10** - Versões Pro, Education e Enterprise


## Requisitos mínimos de hardware
Veja a seguir os requisitos mínimos de hardware para instalar o cliente de computador do Intune:

|Requisito|Detalhes|
|---------------|--------------------|
|Rede|O cliente requer que o PC tenha conectividade com a Internet.|
|Processador e memória|Consulte os requisitos de RAM e de processador para o sistema operacional do PC.|
|Espaço em disco|200 MB de espaço em disco disponível antes de instalar o software cliente.|

## Requisitos adicionais
Veja a seguir os requisitos de software para instalar o cliente de computador do Intune:

|Requisito|Detalhes|
|---------------|--------------------|
|Permissões administrativas|A conta que instalará o software cliente deve ter permissões de administrador local para esse computador.|
|Windows Installer 3.1|O PC deve ter, no mínimo, o Windows Installer 3.1.|
|Remover o software cliente incompatível|Antes de instalar o software cliente de computador do Intune, você deve desinstalar o seguinte software cliente do computador:<br /><br />- Qualquer versão do Configuration Manager<br />- Qualquer versão do Microsoft SMS (Systems Management Server)|

### Consulte também
[Recursos de gerenciamento de dispositivos móveis do Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)



<!--HONumber=Aug16_HO3-->


