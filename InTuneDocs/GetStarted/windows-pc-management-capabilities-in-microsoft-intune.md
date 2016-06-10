---
# required metadata

title: Recursos de gerenciamento do computador Windows | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 77fa5c66-a87c-47df-964c-800eea509b33

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Recursos de gerenciamento de computador Windows (com o cliente de computador do Microsoft Intune)
Na maioria dos cenários, você registrará os dispositivos no Microsoft Intune, que fornece um conjunto maior de recursos que o cliente de computador do Intune. No entanto, você também pode gerenciar computadores usando o cliente de computador do Intune, que fornece os seguintes recursos:

-   **Gerenciamento de atualizações de software** – Você pode manter os computadores atualizados e gerenciar quando as atualizações são aplicadas.

-   **Política do Firewall do Windows** – Ajuda a garantir que nenhum computador usado pela sua empresa tenha um Firewall do Windows inativo ou configurado incorretamente.

-   **Proteção antimalware** – O Intune conta com o Endpoint Protection, que ajuda a proteger seus computadores contra malware.

-   **Assistência remota** – O Intune permite que os usuários entrem em contato com a equipe de suporte de TI, que poderá fornecer assistência usando um recurso de área de trabalho remota que está incluso no Intune (requer o software TeamViewer).

-   **Gerenciamento de licenças de software** – Controle quantas licenças de software estão disponíveis e quantas licenças disponíveis estão sendo usadas.
-   **Implantação de aplicativo** – Implante software nos computadores que você gerencia. Alguns recursos de gerenciamento de aplicativo não estão disponíveis quando você gerencia computadores com o software cliente.


## Requisitos de sistema operacional
O Intune pode gerenciar computadores que executam as seguintes versões do Windows (x86 e x64):


-   **Windows Vista** - versões Business, Enterprise e Ultimate.

-   **Windows 7** - Versões Pro, Enterprise e Ultimate (sem service pack ou com SP1).

-   **Windows 8** - Versões Pro e Enterprise.

-   **Windows 8.1** - Versões Pro e Enterprise.

- **Windows 10** - Versões Home, Pro, Education e Enterprise.


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
|Permissões administrativas|A conta que instalará o software cliente deve ter permissões de administrador local para esse PC.|
|Windows Installer 3.1|O computador deve ter, no mínimo, o Windows Installer 3.1 instalado.|
|Remover o software cliente incompatível|Antes de instalar o software cliente de computador do Intune, você deve desinstalar o seguinte software cliente do computador:<br /><br />- Qualquer versão do Configuration Manager<br />- Qualquer versão do Microsoft SMS (Systems Management Server)|

### Consulte também
[Recursos de gerenciamento de dispositivos móveis do Microsoft Intune](./mobile-device-management-capabilities-in-microsoft-intune.md)


<!--HONumber=May16_HO3-->


